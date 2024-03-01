# 操作系统第一次实验报告

## 实验目的

> 利用QEMU模拟器（UTM也可)创建X86虚拟机（BIOS方式启动)并创建对应的虚拟磁盘（raw格式），先后安装windows和linux操作系统（两种操作系统版本不限），注意windows安装时需要先分区，并预留给linux操作系统分区。读取虚拟磁盘的MBR，配合gcc反汇编工具(如objdump)，进行观察与分析，并说明其大致工作过程与内容。

## 实验过程

-   利用qemu-img创建50G的空虚拟磁盘
    
```
 .\qemu-img create -f raw mydisk.raw 50G
```
-   安装操作系统, 利用`qemu\share\bios.bin`文件进行bios启动
    
    -   windows(这里选择win7SP1 x64 微软官方的2019英文旗舰版), 留下8G作为运行内存, 安装过程中留下20G空闲空间给linux
      ```  
         .\qemu-system-x86_64 -bios "D:\App\qemu\share\bios.bin" -drive file=mydisk.raw -cdrom "D:\eagedownload\7601.24214.180801-1700.win7sp1_ldr_escrow_client_ultimate_x64fre_en-us.iso" -m 8G -vga std
        
   
    -   linux(这里选择ubuntu22.04), 同样用8G作为运行内存，加上`-boot order=d`表示优先从镜像文件中启动
        ```
         .\qemu-system-x86_64 -bios "D:\App\qemu\share\bios.bin" -drive file=mydisk.raw -cdrom "D:\eagedownload\ubuntu-22.04.4-desktop-amd64 (1).iso" -m 8G -vga std -boot order=d```
        
-   下载dd for windows, 使用dd命令读取虚拟磁盘前512个字节
    
  ```   .\dd if=mydisk.raw of=mbr.bin bs=512 count=1```
    
-   使用objump对读取的mbr.bin文件进行反汇编操作
    ```
    objdump -D -b binary -m i386 --adjust-vma=0x7c00 mbr.bin
    ```
    

## 实验结果

window安装成功

![image-20240228220408328](file://D:/myblog/source/images/%E5%AE%9E%E9%AA%8C%E6%8A%A5%E5%91%8A/image-20240228220408328.png?lastModify=1709254721)

linux安装成功

![image-20240229143333324](file://D:/myblog/source/images/%E5%AE%9E%E9%AA%8C%E6%8A%A5%E5%91%8A/image-20240229143333324.png?lastModify=1709254721)

grub界面可以正常切换os

![image-20240229142253728](file://D:/myblog/source/images/%E5%AE%9E%E9%AA%8C%E6%8A%A5%E5%91%8A/image-20240229142253728.png?lastModify=1709254721)

**使用objump进行读取虚拟磁盘的MBR结果**
```
mbr.bin:     file format binary  
​  
Disassembly of section .data:  
​  
00007c00 <.data>:  
    7c00:       eb 63                   jmp    0x7c65  
    7c02:       90                      nop  
    7c03:       d0 bc 00 7c 8e c0 8e    sarb   -0x713f7184(%eax,%eax,1)  
    7c0a:       d8 be 00 7c bf 00       fdivrs 0xbf7c00(%esi)  
    7c10:       06                      push   %es  
    7c11:       b9 00 02 fc f3          mov    $0xf3fc0200,%ecx  
    7c16:       a4                      movsb  %ds:(%esi),%es:(%edi)  
    7c17:       50                      push   %eax  
    7c18:       68 1c 06 cb fb          push   $0xfbcb061c  
    7c1d:       b9 04 00 bd be          mov    $0xbebd0004,%ecx  
    7c22:       07                      pop    %es  
    7c23:       80 7e 00 00             cmpb   $0x0,0x0(%esi)  
    7c27:       7c 0b                   jl     0x7c34  
    7c29:       0f 85 0e 01 83 c5       jne    0xc5837d3d  
    7c2f:       10 e2                   adc    %ah,%dl  
    7c31:       f1                      int1  
    7c32:       cd 18                   int    $0x18  
    7c34:       88 56 00                mov    %dl,0x0(%esi)  
    7c37:       55                      push   %ebp  
    7c38:       c6 46 11 05             movb   $0x5,0x11(%esi)  
    7c3c:       c6 46 10 00             movb   $0x0,0x10(%esi)  
    7c40:       b4 41                   mov    $0x41,%ah  
    7c42:       bb aa 55 cd 13          mov    $0x13cd55aa,%ebx  
    7c47:       5d                      pop    %ebp  
    7c48:       72 0f                   jb     0x7c59  
    7c4a:       81 fb 55 aa 75 09       cmp    $0x975aa55,%ebx  
    7c50:       f7 c1 01 00 74 03       test   $0x3740001,%ecx  
    7c56:       fe 46 10                incb   0x10(%esi)  
    7c59:       66 00 80 01 00 00 00    data16 add %al,0x1(%eax)  
    7c60:       00 00                   add    %al,(%eax)  
    7c62:       00 00                   add    %al,(%eax)  
    7c64:       ff                      (bad)  
    7c65:       fa                      cli  
    7c66:       90                      nop  
    7c67:       90                      nop  
    7c68:       f6 c2 80                test   $0x80,%dl  
    7c6b:       74 05                   je     0x7c72  
    7c6d:       f6 c2 70                test   $0x70,%dl  
    7c70:       74 02                   je     0x7c74  
    7c72:       b2 80                   mov    $0x80,%dl  
    7c74:       ea 79 7c 00 00 31 c0    ljmp   $0xc031,$0x7c79  
    7c7b:       8e d8                   mov    %eax,%ds  
    7c7d:       8e d0                   mov    %eax,%ss  
    7c7f:       bc 00 20 fb a0          mov    $0xa0fb2000,%esp  
    7c84:       64 7c 3c                fs jl  0x7cc3  
    7c87:       ff 74 02 88             push   -0x78(%edx,%eax,1)  
    7c8b:       c2 52 bb                ret    $0xbb52  
    7c8e:       17                      pop    %ss  
    7c8f:       04 f6                   add    $0xf6,%al  
    7c91:       07                      pop    %es  
    7c92:       03 74 06 be             add    -0x42(%esi,%eax,1),%esi  
    7c96:       88 7d e8                mov    %bh,-0x18(%ebp)  
    7c99:       17                      pop    %ss  
    7c9a:       01 be 05 7c b4 41       add    %edi,0x41b47c05(%esi)  
    7ca0:       bb aa 55 cd 13          mov    $0x13cd55aa,%ebx  
    7ca5:       5a                      pop    %edx  
    7ca6:       52                      push   %edx  
    7ca7:       72 3d                   jb     0x7ce6  
    7ca9:       81 fb 55 aa 75 37       cmp    $0x3775aa55,%ebx  
    7caf:       83 e1 01                and    $0x1,%ecx  
    7cb2:       74 32                   je     0x7ce6  
    7cb4:       31 c0                   xor    %eax,%eax  
    7cb6:       89 44 04 40             mov    %eax,0x40(%esp,%eax,1)  
    7cba:       88 44 ff 89             mov    %al,-0x77(%edi,%edi,8)  
    7cbe:       44                      inc    %esp  
    7cbf:       02 c7                   add    %bh,%al  
    7cc1:       04 10                   add    $0x10,%al  
    7cc3:       00 66 8b                add    %ah,-0x75(%esi)  
    7cc6:       1e                      push   %ds  
    7cc7:       5c                      pop    %esp  
    7cc8:       7c 66                   jl     0x7d30  
    7cca:       89 5c 08 66             mov    %ebx,0x66(%eax,%ecx,1)  
    7cce:       8b 1e                   mov    (%esi),%ebx  
    7cd0:       60                      pusha  
    7cd1:       7c 66                   jl     0x7d39  
    7cd3:       89 5c 0c c7             mov    %ebx,-0x39(%esp,%ecx,1)  
    7cd7:       44                      inc    %esp  
    7cd8:       06                      push   %es  
    7cd9:       00 70 b4                add    %dh,-0x4c(%eax)  
    7cdc:       42                      inc    %edx  
    7cdd:       cd 13                   int    $0x13  
    7cdf:       72 05                   jb     0x7ce6  
    7ce1:       bb 00 70 eb 76          mov    $0x76eb7000,%ebx  
    7ce6:       b4 08                   mov    $0x8,%ah  
    7ce8:       cd 13                   int    $0x13  
    7cea:       73 0d                   jae    0x7cf9  
    7cec:       5a                      pop    %edx  
    7ced:       84 d2                   test   %dl,%dl  
    7cef:       0f 83 d0 00 be 93       jae    0x93be7dc5  
    7cf5:       7d e9                   jge    0x7ce0  
    7cf7:       82 00 66                addb   $0x66,(%eax)  
    7cfa:       0f b6 c6                movzbl %dh,%eax  
    7cfd:       88 64 ff 40             mov    %ah,0x40(%edi,%edi,8)  
    7d01:       66 89 44 04 0f          mov    %ax,0xf(%esp,%eax,1)  
    7d06:       b6 d1                   mov    $0xd1,%dh  
    7d08:       c1 e2 02                shl    $0x2,%edx  
    7d0b:       88 e8                   mov    %ch,%al  
    7d0d:       88 f4                   mov    %dh,%ah  
    7d0f:       40                      inc    %eax  
    7d10:       89 44 08 0f             mov    %eax,0xf(%eax,%ecx,1)  
    7d14:       b6 c2                   mov    $0xc2,%dh  
    7d16:       c0 e8 02                shr    $0x2,%al  
    7d19:       66 89 04 66             mov    %ax,(%esi,%eiz,2)  
    7d1d:       a1 60 7c 66 09          mov    0x9667c60,%eax  
    7d22:       c0 75 4e 66             shlb   $0x66,0x4e(%ebp)  
    7d26:       a1 5c 7c 66 31          mov    0x31667c5c,%eax  
    7d2b:       d2 66 f7                shlb   %cl,-0x9(%esi)  
    7d2e:       34 88                   xor    $0x88,%al  
    7d30:       d1 31                   shll   (%ecx)  
    7d32:       d2 66 f7                shlb   %cl,-0x9(%esi)  
    7d35:       74 04                   je     0x7d3b  
    7d37:       3b 44 08 7d             cmp    0x7d(%eax,%ecx,1),%eax  
    7d3b:       37                      aaa  
    7d3c:       fe c1                   inc    %cl  
    7d3e:       88 c5                   mov    %al,%ch  
    7d40:       30 c0                   xor    %al,%al  
    7d42:       c1 e8 02                shr    $0x2,%eax  
    7d45:       08 c1                   or     %al,%cl  
    7d47:       88 d0                   mov    %dl,%al  
    7d49:       5a                      pop    %edx  
    7d4a:       88 c6                   mov    %al,%dh  
    7d4c:       bb 00 70 8e c3          mov    $0xc38e7000,%ebx  
    7d51:       31 db                   xor    %ebx,%ebx  
    7d53:       b8 01 02 cd 13          mov    $0x13cd0201,%eax  
    7d58:       72 1e                   jb     0x7d78  
    7d5a:       8c c3                   mov    %es,%ebx  
    7d5c:       60                      pusha  
    7d5d:       1e                      push   %ds  
    7d5e:       b9 00 01 8e db          mov    $0xdb8e0100,%ecx  
    7d63:       31 f6                   xor    %esi,%esi  
    7d65:       bf 00 80 8e c6          mov    $0xc68e8000,%edi  
    7d6a:       fc                      cld  
    7d6b:       f3 a5                   rep movsl %ds:(%esi),%es:(%edi)  
    7d6d:       1f                      pop    %ds  
    7d6e:       61                      popa  
    7d6f:       ff 26                   jmp    *(%esi)  
    7d71:       5a                      pop    %edx  
    7d72:       7c be                   jl     0x7d32  
    7d74:       8e 7d eb                mov    -0x15(%ebp),%?  
    7d77:       03 be 9d 7d e8 34       add    0x34e87d9d(%esi),%edi  
    7d7d:       00 be a2 7d e8 2e       add    %bh,0x2ee87da2(%esi)  
    7d83:       00 cd                   add    %cl,%ch  
    7d85:       18 eb                   sbb    %ch,%bl  
    7d87:       fe 47 52                incb   0x52(%edi)  
    7d8a:       55                      push   %ebp  
    7d8b:       42                      inc    %edx  
    7d8c:       20 00                   and    %al,(%eax)  
    7d8e:       47                      inc    %edi  
    7d8f:       65 6f                   outsl  %gs:(%esi),(%dx)  
    7d91:       6d                      insl   (%dx),%es:(%edi)  
    7d92:       00 48 61                add    %cl,0x61(%eax)  
    7d95:       72 64                   jb     0x7dfb  
    7d97:       20 44 69 73             and    %al,0x73(%ecx,%ebp,2)  
    7d9b:       6b 00 52                imul   $0x52,(%eax),%eax  
    7d9e:       65 61                   gs popa  
    7da0:       64 00 20                add    %ah,%fs:(%eax)  
    7da3:       45                      inc    %ebp  
    7da4:       72 72                   jb     0x7e18  
    7da6:       6f                      outsl  %ds:(%esi),(%dx)  
    7da7:       72 0d                   jb     0x7db6  
    7da9:       0a 00                   or     (%eax),%al  
    7dab:       bb 01 00 b4 0e          mov    $0xeb40001,%ebx  
    7db0:       cd 10                   int    $0x10  
    7db2:       ac                      lods   %ds:(%esi),%al  
    7db3:       3c 00                   cmp    $0x0,%al  
    7db5:       75 f4                   jne    0x7dab  
    7db7:       c3                      ret  
    7db8:       3a fc                   cmp    %ah,%bh  
    7dba:       c3                      ret  
    7dbb:       c9                      leave  
    7dbc:       00 00                   add    %al,(%eax)  
    7dbe:       00 20                   add    %ah,(%eax)  
    7dc0:       21 00                   and    %eax,(%eax)  
    7dc2:       07                      pop    %es  
    7dc3:       df 13                   fists  (%ebx)  
    7dc5:       0c 00                   or     $0x0,%al  
    7dc7:       08 00                   or     %al,(%eax)  
    7dc9:       00 00                   add    %al,(%eax)  
    7dcb:       20 03                   and    %al,(%ebx)  
    7dcd:       00 00                   add    %al,(%eax)  
    7dcf:       df 14 0c                fists  (%esp,%ecx,1)  
    7dd2:       07                      pop    %es  
    7dd3:       fe                      (bad)  
    7dd4:       ff                      (bad)  
    7dd5:       ff 00                   incl   (%eax)  
    7dd7:       28 03                   sub    %al,(%ebx)  
    7dd9:       00 00                   add    %al,(%eax)  
    7ddb:       d8 bc 03 80 fe ff ff    fdivrs -0x180(%ebx,%eax,1)  
    7de2:       ef                      out    %eax,(%dx)  
    7de3:       fe                      (bad)  
    7de4:       ff                      (bad)  
    7de5:       ff 00                   incl   (%eax)  
    7de7:       00 c0                   add    %al,%al  
    7de9:       03 00                   add    (%eax),%eax  
    7deb:       08 10                   or     %dl,(%eax)  
    7ded:       00 00                   add    %al,(%eax)  
    7def:       fe                      (bad)  
    7df0:       ff                      (bad)  
    7df1:       ff 05 fe ff ff fe       incl   0xfefffffe  
    7df7:       0f d0                   (bad)  
    7df9:       03 02                   add    (%edx),%eax  
    7dfb:       e8 6f 02 55 aa          call   0xaa55806f
```
### **MBR结构及功能分析:**

----------

MBR主要包括

-   引导加载程序: 通常占用了前446个字节. 负责在计算机启动时加载操作系统, 从硬盘的指定分区中读取os的引导扇区, 将其加载到内存中启动执行. 对于反汇编的代码
    
    -   `jmp 0x7c65`表示跳转到**0x7c65**地址, 将引导加载程序的执行流程转移到其他位置,
        
    -   `push %es、push $0xf3fc0200`等指令可能会用于准备环境, 设置参数等, 是引导加载程序的一部分.
        
    -   `movsb %ds:(%esi),%es:(%edi)` 表示数据传送, 将源地址一个字节复制到目标地址, 可能用于引导加载程序的内存复制操作.
        
    -   `sar`、`fdivrs`、`mov`、`movsb`、`pop`、`cmpb`、`jl`、`jne`等指令：这些指令组成了引导加载程序和其他代码的主要功能部分。其中包含数据移动、寄存器操作、条件跳转等操作。
        
-   分区表: 紧随引导加载程序之后的64个字节（16字节 * 4个分区）。每个分区表项16个字节，用于描述硬盘上的分区情况。每个分区表项包含分区的起始位置、大小和类型等信息。
    
    -   `jmp 0x7c79`：跳转到`0x7c79`处执行。这可能是一个关键的跳转点，用于引导加载程序的流程控制。
        
    -   `cli`：禁用中断，通常在引导加载程序的末尾执行，以确保加载操作系统时不受到中断的干扰。
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTgyNzY0NDkyM119
-->
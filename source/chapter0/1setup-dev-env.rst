实验环境配置
============

.. toctree::
   :hidden:
   :maxdepth: 4
   
本节我们将完成环境配置。整个流程分为下面几个部分：

- 获取 `LoongArch` CPU设计 实验包
- 安装Vivado开发工具
- 安装 `LoongArch32r` GNU 工具链 

目前实验支持 Windows 和 Linux 操作系统。对于 Linux 操作系统上的开发流程，已经经过作者验证， Windows 上的开发流程经过了同学验证。

.. tip:: 环境配置对于部分实验(如实验1)而言不是必须的，可以等到需要完成该实验时，再进行配置

获取 `LoongArch` CPU设计 实验包
-------------------------------

获取实验包可以从下面三个途径之一获取

1. `gitee实验包源码仓库 <https://gitee.com/loongson-edu/cdp_ede_local>`_
2. `gitee实验发行包 <https://gitee.com/loongson-edu/cdp_ede_local/releases>`_
3. 找实验老师要

.. note::
   实验发行包 和 实验包源码 的区别
   
   如果使用 实验包源码，需要自行编译构建一部分文件，而 实验发行包 包含了被构建好的二进制文件。如果可以，应该优先以老师发布的软件包优先

安装Vivado开发工具
-------------------------------------------

首先获取 `Vivado安装包 <https://china.xilinx.com/support/download.html>`_

对于实验要求，我们建议安装 2019.2 版本的Vivado

- `Vivado2019.2 Windows 网络安装 <https://china.xilinx.com/member/forms/download/xef.html?filename=Xilinx_Unified_2019.2_1106_2127_Win64.exe>`_ 
- `Vivado2019.2 Linux 网络安装 <https://china.xilinx.com/member/forms/download/xef.html?filename=Xilinx_Unified_2019.2_1106_2127_Lin64.bin>`_ 
- `Vivado2019.2 全平台离线安装包 <https://china.xilinx.com/member/forms/download/xef.html?filename=Xilinx_Vivado_2019.2_1106_2127.tar.gz>`_ 

.. tip:: Vivado体积较大，并且下载安装需要注册AMD官网账号。

.. warning:: 

    如果使用其他版本的Vivado，在使用过程中可能出现一些问题问题，问题的解决方案如下

    IP核版本锁定 TODO

安装 `LoongArch32r` GNU 工具链 
---------------------------------------------------------------------

.. tip:: 安装编译工具链的目的是对LoongArch32R源程序进行编译，如果难以安装，可以选择下载 `gitee实验发行包 <https://gitee.com/loongson-edu/cdp_ede_local/releases>`_
   内部包含编译好的.coe文件

在进行 实验2 和 实验3 的过程中，如果需要自行编译 func 程序需要使用 LoongArch32R 的 GCC 交叉编译工具。该工具链的安装可以通过
`源代码编译安装 <https://gitee.com/loongson-edu/la32r-toolchains>`_ 
也可以使用编译好的
`二进制文件安装 <https://gitee.com/loongson-edu/la32r-toolchains/releases>`_
下面主要介绍第二种安装方式

**Linux下工具链安装**

首先下载编译好的 `LoongArch32R 交叉编译工具链(Linux) <https://gitee.com/loongson-edu/la32r-toolchains/releases/download/v0.0.3/loongson-gnu-toolchain-8.3-x86_64-loongarch32r-linux-gnusf-v2.0.tar.xz>`_

在终端当中执行下面命令，以安装工具链

.. code-block:: bash

   # 下面的命令将解压到/opt/目录
   $ sudo tar zxvf loongarch32r-linux-gnusf-*.tar.gz -C /opt/
   # 将工具链位置添加到环境变量
   $ echo “ export PATH=/opt/loongarch32r-linux-gnusf-*/bin/:$PATH ” >> ~/.bashrc
   # 检验工具链是否安装正确
   $ loongarch32r-linux-gnusf-gcc --version
   # 如果安装正确，你应当看到如下输出结果
   loongarch32r-linux-gnusf-gcc (LoongArch GNU toolchain LA32 v2.0 (20230903)) 8.3.0
   Copyright (C) 2018 Free Software Foundation, Inc.
   This is free software; see the source for copying conditions.  There is NO
   warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.

**Windows下工具链安装(未经测试)**

首先下载编译好的 `LoongArch32R 交叉编译工具链(Windows) <https://gitee.com/loongson-edu/la32r-toolchains/releases/download/v0.0.3/loongson-gnu-toolchain-8.3-i686-mingw-loongarch32r-linux-gnusf-v2.0.zip>`_

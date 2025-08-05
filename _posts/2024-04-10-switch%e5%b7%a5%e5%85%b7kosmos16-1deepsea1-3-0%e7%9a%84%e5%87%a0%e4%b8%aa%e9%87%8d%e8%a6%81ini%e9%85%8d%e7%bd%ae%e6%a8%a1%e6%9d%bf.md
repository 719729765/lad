---
title: "[switch工具]kosmos16.1/deepsea1.3.0的几个重要ini配置模板"
date: 2024-04-10
tags: []
categories: ["switch教程"]
excerpt: "　　[switch工具]kosmos16.1/deepsea1.3.0的几个重要ini配置模板 　　kosmos和deepsea都是基于大气层内核，统称大气层阵营，和大气层整合包都是差不多的使用。 　　大气层和kosmos或者deepsea整合包，就是payload和fss0引导的区别。 　　首先第&hellip;"
layout: post
---

 <p>　　[switch工具]kosmos16.1/deepsea1.3.0的几个重要ini配置模板</p> <p align="center"><img align="" border="0" src="https://lad.sfcrom.cn/wp-content/uploads/2024/04/20240410_66162c222dc89.webp" width="481" alt="[switch工具]kosmos16.1/deepsea1.3.0的几个重要ini配置模板" /></p> <p>　　kosmos和deepsea都是基于大气层内核，统称大气层阵营，和大气层整合包都是差不多的使用。</p> <p>　　大气层和kosmos或者deepsea整合包，就是payload和fss0引导的区别。</p> <p>　　首先第一次payload都是hekate的注入bin文件</p> <p>　　(1)刺心用的是二次payload大气层原版fusee-primary.bin，所以之后默认开启配置。所以添加es/fs插件全部在atmosphere/下。只要有对应的ips就行了。</p> <p>　　(2)对于已经停更的kosmos和接下来发布的deepsea整合包，用的是hekate解析fss0引导大气层fusee-secondary.bin，然后可以实现自定义的多重引导，其中fs插件就位于bootloader/patch.ini，目前有haruko接替joonie86提供这个patch.ini文件。</p> <p>　　两种类型整合包的配置文件，其中位于atmosphere/config/bct.ini，override_config.ini和system_settings.ini三个ini配置文件通用</p> <p>　　位于根目录的exosphere.ini是fusee-primary.bin所用。</p> <p>　　两种类型的引导其实都差不多，你可以近似理解两种差不多的root工具，最终游戏体验上也差不多。只要你了解hekate这个多功能的配置方法，你可以自定义配置，比如既可以大气层原版引导，也可以通过deepsea这样解析实现引导本机真实系统。不同的cfw就是引导方式不同，payload或fss0亦或txos都是差不多的作用，选择什么cfw都由玩家自己决定，一切实测为准。</p> <p>　　【补充一下ES/FS插件】作用不多讲了，ES插件支持魔改游戏，FS插件，那强大了，就靠它。</p> <p>　　(1)目前acid补丁已经集成在系统模块里，那么es插件的话，和switch系统大版本有关，比如9.0，10.0这样。不管是payload还是fss0引导都一样。</p> <p>　　(2)有关fs插件，因为运行备份游戏和未签名nsp都靠它。9.2.0及以下系统就是位于atmosphere/kip_patches/fs_patches</p> <p>　　但是10.0及以上开始，在kip_patches/下新增loader_patches。这两块都是需要payload原版fusee-primary.bin所必须的</p> <p>　　(3)根据haruko给的sigpatch，发现loader patches和大气层内核有关，0.11.0，0.11.1和0.12.0。所以当前的loader patch一共是3个ips。至于kosmos或deepsea整合包，因为是通过hekate的fss0引导，所以通过bootloader/patch.ini配置进行解析，这就是kosmos的fs插件。所以它的fs插件不以ips形式存放在kip_patches/下。</p> <p>　　(4)近期发现patch.ini给hekate解析时发现，引导真实系统cfw导致fs插件不能生效的bug，最明显的就是tinfoil8.1无法运行，安装部分nsp无法运行(有部分nsp却可以)，但是引导虚拟系统cfw一切正常。解决办法很简单，在bootloader/hekate_ipl.ini中的cfw-sysnand(引导cfw真实系统)段落中添加loader.kip</p> <p>　　这里感谢论坛技术支持geminize兄弟的解释，他查看了patch.ini的内容，他估计haruko在编写patch.ini的时候可能把偏移地址写错，虚拟系统直接根据备份出来的文件计算的，文件尾有对齐的空白，用到真实系统上可能有差异，比如说真实系统nand128m，虚拟系统文件可能是128.01m。</p> <p><h4>下载地址(由网友<font color="red">z734516156</font>发布)：</h4></p> 

---
📖 **下载地址/原文地址：** 本文最初发布于我的博客网站：[https://lad.sfcrom.cn/2024/04/156284/](https://lad.sfcrom.cn/2024/04/156284/)

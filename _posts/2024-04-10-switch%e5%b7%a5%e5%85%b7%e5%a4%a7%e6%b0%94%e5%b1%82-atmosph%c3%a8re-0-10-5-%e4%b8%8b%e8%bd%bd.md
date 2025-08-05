---
title: "[switch工具]大气层 Atmosphère 0.10.5 下载"
date: 2024-04-10
tags: []
categories: ["switch教程"]
excerpt: "　　[switch工具]大气层 Atmosph&egrave;re 0.10.5 下载。 　　0.10.5 is Atmosph&egrave;re&#039;s twenty-eighth official release. 　　fusee-primary was last updated in: &hellip;"
layout: post
---

 <p>　　[switch工具]大气层 Atmosph&egrave;re 0.10.5 下载。</p> <p align="center"><img align="" border="0" src="https://lad.sfcrom.cn/wp-content/uploads/2024/04/20240410_66162c215173f.webp" width="500" alt="[switch工具]大气层 Atmosphère 0.10.5 下载" /></p> <p>　　0.10.5 is Atmosph&egrave;re&#39;s twenty-eighth official release.</p> <p>　　fusee-primary was last updated in: 0.10.4.</p> <p>　　With thanks to the@switchbrewteam, Atmosph&egrave;re 0.10.5 is bundled withhbl2.3, andhbmenu3.2.0.</p> <p>　　The following was changed since the last release:</p> <p>　　Changes were made to the way fs.mitm builds images when providing a layeredfs romfs.</p> <p>　　Building romfs metadata previously had a memory cost of about ~4-5x the file table size.</p> <p>　　This caused games that have particularly enormous file metadata tables (&gt; 4 MB) to exhaust fs.mitm&#39;s 16 MB memory pool.</p> <p>　　The code that creates romfs images was thus changed to be significantly more memory efficient, again.</p> <p>　　Memory requirements have been lowered from ~4x file table size to ~2x file table size + 0.5 MB.</p> <p>　　There is a slight speed penalty to this, but testing on Football Manager 2020 only took an extra ~1.5 seconds for the game to boot with many modded files.</p> <p>　　This shouldn&#39;t be noticeable thanks to the async changes made in 0.10.2.</p> <p>　　If you encounter a game that exhausts ams.mitm&#39;s memory (crashing it) when loading layeredfs mods, please contact SciresM.</p> <p>　　Romfs building can be made even more memory efficient, but unless games show up with even more absurdly huge file tables it seems not worth the speed trade-off.</p> <p>　　A bug was fixed that caused Atmosphere&#39;s fatal error context to not dump TLS for certain processes.</p> <p>　　General system stability improvements to enhance the user&#39;s experience.</p> <p><h4>下载地址(由网友<font color="red">why2228288760</font>发布)：</h4></p> 

---
📖 **下载地址/原文地址：** 本文最初发布于我的博客网站：[https://lad.sfcrom.cn/2024/04/7418/](https://lad.sfcrom.cn/2024/04/7418/)

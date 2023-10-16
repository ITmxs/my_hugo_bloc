---
title: "Arkui X"
subtitle: ""
date: 2023-10-15T13:23:26+08:00
lastmod: 2023-10-15T13:23:26+08:00
draft: false
author: "坚果"
authorLink: "https://gitee.com/jianguo888/"
description: ""
license: ""
images: []
resources:
- name: "featured-image"
  src: "hobust.png"
tags: ["OpenHarmony","HarmonyOS"]
categories: ["OpenHarmony","HarmonyOS"]

featuredImage: ""
featuredImagePreview: ""

hiddenFromHomePage: false
hiddenFromSearch: false
twemoji: false
lightgallery: true
ruby: true
fraction: true
fontawesome: true
linkToMarkdown: true
rssFullText: false

toc:
  enable: true
  auto: true
code:
  copy: true
  maxShownLines: 50
math:
  enable: false
  # ...
mapbox:
  # ...
share:
  enable: true
  # ...
comment:
  enable: true
  # ...
library:
  css:
    # someCSS = "some.css"
    # located in "assets/"
    # Or
    # someCSS = "https://cdn.example.com/some.css"
  js:
    # someJS = "some.js"
    # located in "assets/"
    # Or
    # someJS = "https://cdn.example.com/some.js"
seo:
  images: []
  # ...
---

![ArkUI跨平台架构图](https://luckly007.oss-cn-beijing.aliyuncs.com/uPic/ArkUI-X-20231015132816847-20231015132931528.png)

<!--more-->

## ArkUI-X项目介绍

ArkUI是一套构建分布式应用的声明式UI开发框架。它具备简洁自然的UI信息语法、丰富的UI组件、多维的状态管理，以及实时界面预览等相关能力，帮助您提升应用开发效率，并能在多种设备上实现生动而流畅的用户体验。

ArkUI-X进一步将ArkUI扩展到了多个OS平台：目前支持OpenHarmony、HarmonyOS、Android、 iOS，后续会逐步增加更多平台支持。开发者基于一套主代码，就可以构建支持多平台的精美、高性能应用。

## 关键特征

ArKUI跨平台框架关键特征如下：

1. 简洁自然的声明式语法。
2. 高效的渲染管线以及平台一致性的渲染机制。
3. 高效的方舟编译器以及运行时。
4. 统一的跨平台API能力集以及扩展机制。

## 技术架构

![ArkUI跨平台架构图](https://luckly007.oss-cn-beijing.aliyuncs.com/uPic/ArkUI-X-20231015132931655.png)

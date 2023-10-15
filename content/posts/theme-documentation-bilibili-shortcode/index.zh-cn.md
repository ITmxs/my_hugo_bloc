---
weight: 9
title: "OpenHarmony学习路线，哔哩哔哩"
date: 2020-03-03T11:29:41+08:00
lastmod: 2020-03-03T12:29:41+08:00
draft: false
author: "坚果"
authorLink: "https://gitee.com/jianguo888/"
description: "bilibili shortcode 提供了一个内嵌的用来播放 bilibili 视频的响应式播放器."
images: ["https://luckly007.oss-cn-beijing.aliyuncs.com/uPic/hobust.png"]
resources:
- name: "featured-image"
  src: "https://luckly007.oss-cn-beijing.aliyuncs.com/uPic/hobust.png"

tags: ["shortcodes"]
categories: ["documentation"]



---

`bilibili` shortcode 提供了一个内嵌的用来播放 bilibili 视频的响应式播放器.

![hobust](https://luckly007.oss-cn-beijing.aliyuncs.com/uPic/hobust.png)

<!--more-->

如果视频只有一个部分, 则仅需要视频的 BV `id`, 例如:

```code
https://www.bilibili.com/video/BV1mj411r7ar
```

一个 `bilibili` 示例:

```markdown
{{</* bilibili BV1Th4y1Z7mL */>}}
或者
{{</* bilibili id=BV1Th4y1Z7mL */>}}
```

呈现的输出效果如下:

{{< bilibili id=BV1Th4y1Z7mL >}}

如果视频包含多个部分, 则除了视频的 BV `id` 之外, 还需要 `p`, 默认值为 `1`, 例如:

```code
https://www.bilibili.com/video/BV1Th4y1Z7mL?p=3
```

一个带有 `p` 参数的 `bilibili` 示例:

```markdown
{{</* bilibili BV1Th4y1Z7mL 3 */>}}
或者
{{</* bilibili id=BV1Th4y1Z7mL p=3 */>}}
```

呈现的输出效果如下:

{{< bilibili id=BV1Th4y1Z7mL p=3 >}}



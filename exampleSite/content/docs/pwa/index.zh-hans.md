+++
title = "渐进式 web 应用程序"
linkTitleIcon = '<i class="fas fa-th-large fa-fw"></i>'
date = 2021-12-03T19:39:01+08:00
featured = false
comment = true
toc = true
reward = true
categories = [
  "PWA"
]
tags = [
  "Manifest",
  "离线",
  "预载"
]
series = [
  "文档"
]
images = []
aliases = [
  "/zh-cn/posts/pwa"
]
authors = ["RazonYang"]
[menu.footer]
  parent = "features"
  weight = 2
+++

PWAs([渐进式 web 应用程序](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps)) 是使用一些特定的技术和标准模式开发的，允许它们同时利用 web 和本机应用程序功能。

我们正处于 PWA 的实验阶段，但添加了一些主要功能，如将站点安装到主屏幕、预缓存文件和离线可用。

<!--more-->

## 站点配置

首先，我们需要指定 `pwa` 参数，即使为空。

| 名称 | 类型 | 默认值 | 描述
|---|:-:|:-:|---
| `pwa` | Object | - |
| `pwa.manifest` | Object | - | [Web app manifest](https://developer.mozilla.org/en-US/docs/Web/Manifest)
| `pwa.manifest.name` | String | - | 默认为站点标题
| `pwa.manifest.short_name` | String | - | 站点短名称
| `pwa.manifest.display` | String | `standalone` |
| `pwa.manifest.description` | String | - | 默认为站点描述
| `pwa.manifest.theme_color` | String | - |
| `pwa.manifest.background_color` | String | - |
| `pwa.manifest.icons` | Array | - |
| `pwa.manifest.icons.sizes` | String | - | 图标尺寸，如："96x96"
| `pwa.manifest.icons.src` | String | - | 图标 URL
| `pwa.precache` | Object | - | Precache assets
| `pwa.precache.fonts` | Array | - | Precache fonts
| `pwa.precache.images` | Array | - | Precache images
| `pwa.precache.pages` | Array | - | Precache pages
| `pwa.precache.scripts` | Array | - | Precache scripts
| `pwa.precache.styles` | Array | - | Precache styles

## Manifest

主题会自动生成 `manifest.json`。

## 离线

如果在没有网络的情况下请求新页面，将显示脱机页面。

我们需要在 `content` 目录中创建一个名为 `offline/index.md` 的脱机页面，其首要内容如下。

```toml
+++
title = 'Offline'
layout = 'offline'
+++
```

## 预载

{{< code-toggle filename="params">}}
{{% code/pwa-precache %}}
{{< /code-toggle >}}
<h2 align="center">linuxdo 增强插件（linuxdo-scripts）</h2>
<p align="center">脚本持续更新，欢迎提出 issues，提交 pr ~</p>

<p align="center">
<img src="https://img.shields.io/github/v/release/dlzmoe/linuxdo-scripts">
<img src="https://img.shields.io/github/last-commit/dlzmoe/linuxdo-scripts">
<img src="https://img.shields.io/github/commit-activity/t/dlzmoe/linuxdo-scripts">
<img src="https://img.shields.io/github/forks/dlzmoe/linuxdo-scripts?style=flat">
<img src="https://img.shields.io/github/stars/dlzmoe/linuxdo-scripts?style=flat">
<img src="https://img.shields.io/github/license/dlzmoe/linuxdo-scripts">
</p>

linux.do 增强插件，话题列表显示创建时间，显示楼层数，新标签页打开话题，强制 block（拉黑屏蔽）某人的话题，话题快捷回复（支持自定义），优化签名图显示防止图裂，功能设置面板导入导出，楼层抽奖等，功能持续更新，欢迎提出。

[Github 仓库](https://github.com/dlzmoe/linuxdo-scripts) | ~~[油猴安装地址](https://greasyfork.org/zh-CN/scripts/501827-linuxdo-%E5%A2%9E%E5%BC%BA%E6%8F%92%E4%BB%B6)~~ | [开发计划](https://github.com/users/dlzmoe/projects/2)

**greasyfork 市场停更说明：** 由于 greasyfork 官方限制，使用 vue 开发打包后的代码无法上传。所以该脚本在 [greasyfork](https://greasyfork.org/zh-CN/scripts/501827-linuxdo-%E5%A2%9E%E5%BC%BA%E6%8F%92%E4%BB%B6/) 版本停留在 0.0.27（旧版本）。

---

## 0. 使用方法

1. 前往 [Releases](https://github.com/dlzmoe/linuxdo-scripts/releases) 下载最新稳定版本 js，拖拽到油猴管理器中。
2. 拉取代码自行打包。


**推荐使用：** 还有个最简单的方式，直接用下面这个脚本，会自动引入我的最新版本 js。

```js
// ==UserScript==
// @name         linuxdo 增强插件
// @namespace    https://github.com/dlzmoe/linuxdo-scripts
// @version      0.0.0
// @description  linux.do 增强插件，话题列表显示创建时间，显示楼层数，新标签页打开话题，强制 block（拉黑屏蔽）某人的话题，话题快捷回复（支持自定义），优化签名图显示防止图裂，功能设置面板导入导出，楼层抽奖等，功能持续更新，欢迎提出。
// @author       dlzmoe
// @match        *://linux.do/*
// @icon         https://cdn.linux.do/uploads/default/optimized/3X/9/d/9dd49731091ce8656e94433a26a3ef36062b3994_2_32x32.png
// @license      Apache-2.0 license
// ==/UserScript==

(function () {
  'use strict';
  window.addEventListener('load', function () {

    var script = document.createElement('script');
    script.src = 'https://linuxo-scripts.netlify.app/app.bundle.js';
    document.body.appendChild(script);

  });
})();
```

## 1. 功能特性

- [x] 话题列表显示创建时间
- [x] 显示楼层数
- [x] 新标签页打开话题
- [x] 强制 block（拉黑屏蔽）某人的话题
- [x] 话题快捷回复（支持自定义）
- [x] 优化签名图显示防止图裂
- [x] 功能设置面板导入导出
- [x] 楼层抽奖
- [x] 只看楼主切换功能
- [x] 自动滚动阅读
- [x] 脚本版本更新检测
- [x] 黑夜模式

## 3. 开发说明

```
node: v16.15.1
```

功能以组件形式展开，每次新增一个功能，注册一个新的组件避免冲突。

1. 安装本仓库并下载依赖，执行运行代码

```shell
git clone https://github.com/dlzmoe/linuxdo-scripts
npm i # 安装依赖
npm run dev # 本地运行
npm run build # 打包构建
```

2. 将 `tampermonkey.js` 代码复制到油猴管理器中。
3. 启用脚本后前往 `linux.do`，刷新页面。

## 2. 版本日志

## 0.1.3

1. 新增黑夜模式适配
2. 优化 UI 显示，设置按钮融合进网站。

<details>
<summary>历史版本日志</summary>

## 0.1.2

1. 修复浏览量显示时间的 bug
2. 新增只看楼主功能（可设置）

## 0.1.1

使用 vue 重构插件，优化了代码，方便开发。
  
## 0.0.27

优化楼层号显示。

## 0.0.26

自动滚动阅读，开启后显示在右下角，优化了其他代码。

## 0.0.25

新增列表话题预览功能。

## 0.0.24

优化代码。

## 0.0.23

优化代码。

## 0.0.22

新增话题提醒（默认关闭），在浏览器别的网页时，如果 linuxdo 来了新话题，会修改 title 提醒。

## 0.0.21

优化了一些未知的 bug。

## 0.0.20

可选择隐藏话题详情顶部大标题。

## 0.0.19

在设置面板中新增楼层抽奖入口。

## 0.0.18

修复快捷回复内容过长导致网页变形的 bug。

## 0.0.17

自动展开回复，优化其他代码。

功能灵感来源于 https://linux.do/t/topic/164863

## 0.0.16

1. 优化了签名图的判断，识别了网站域名。
2. 设置面板新增导入导出功能，备份更方便了。

## 0.0.15

签名小尾巴如果不是图片格式，转成文字避免图裂。

## 0.0.14

自定义快捷回复设置，优化了其他问题。

## 0.0.13

新增话题快捷回复，暂不可自定义，后续会增加这个计划。

## 0.0.12

新增悬浮面板（可隐藏），设置屏蔽用户名单不看他的话题。

## 0.0.11

修复了一些 bug。

## 0.0.9

1. 新标签页打开话题。

## 0.0.8

1. 新增点击 logo 进入新话题（默认关闭）。

## 0.0.7

1. 优化代码，提升运行性能。

## 0.0.6

删除..

## 0.0.5

1. 聊天频道显示发言时间（默认不显示）。

## 0.0.4

1. 新增是否将浏览量替换为时间配置。
2. 新增楼层号显示。

## 0.0.3

1. 优化坟贴显示。
2. 新增隐藏签名小尾巴功能。

## 0.0.2

1. 优化时间颜色，并对三个月以上的帖子显示坟头。
2. 将功能写成配置项，未来可添加更多可配置功能。

## 0.0.1

如题，linux.do 帖子列表显示创建时间。

欢迎提交修改代码。

</details>

## 3. 开源协议

[Apache-2.0 license](./LICENSE)
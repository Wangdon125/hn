# 矿用产品统一刷题

矿用产品培训题库刷题 Web 应用（单文件、纯前端、可离线使用）。

## 线上地址

https://4m9c9mu8059kn.doubao.link/app/app_17g38ftp1s7

> 应用带访问口令验证，进入前需输入口令。口令常量位于 `index.html` 中 `const ACCESS_CODE = '...'`，校验时对输入做 `trim().toUpperCase()` 处理，因此大小写不敏感；修改口令只需改该常量并重新发布。

## 功能

- 8 个科目：通讯、液控、电控、自动化、组合开关、配套工程、KTC256、VOIP
- 4 种题型：选择、判断、填空、简答
- 题库共 1111 题
- 顺序练习 / 随机练习 / 错题本
- 答题进度与错题本保存在浏览器 `localStorage`（`mineQuizProgress_v1`），刷新不丢失
- 自带 `manifest.webmanifest` 与 `sw.js`，可添加到桌面离线使用

## 文件结构

```
index.html            主程序（单文件自包含：页面、样式、脚本、题库数据）
manifest.webmanifest  PWA 清单
sw.js                 离线缓存 Service Worker
icons/icon-192.png    应用图标
```

## 本地使用

直接用浏览器打开 `index.html` 即可，无需服务器、无需联网。

## 部署

本应用托管于妙搭（Miaoda），类型为 modern_html。发布时上传 `index.html` 即可，附属资源随目录一并发布。

## 说明

- 题库数据内联在 `index.html` 的 `const DATA = {...}` 中，更新题库直接改这一处。
- 口令为前端轻量防护，源码可见，适合内部培训场景；如需更强权限控制需改用带后端的方案。
---
date: '2025-03-21T08:43:40+08:00'
draft: false
title: '前端面试题集'
tags: ["hugo","markdown"]
---

##  前言

都是面试被问过的东西，留着做个 backup

面试经验集 ×

面试丢人集 √

##  z-index 有什么作用 \#css \#z-index

z-index 用于表示当前元素的层级，层级越低越优先显示在前

##  z-index 通常都与什么属性配合使用 \#css \#z-index

z-index 只能作用于已经定义了 position 的元素（通常指 absolute, fixed, relative, sticky 等定位属性，static 是 position 的默认值所以也对 z-index 无效）

##  隐匿一个元素的方法 \#css

1.  display: none
2.  visibility: hidden
3.  opacity: 0
4.  rgba(0,0,0,0) \| 重点在最后一个参数，其作用于 opacity 相同
5.  position: absolute; left: -9999px; \| 通过绝对的定位手法将元素抛至九霄云外（最神人的方式）

##  防抖？节流？都是些什么？ \#JS \#javascript \#防抖 \#节流

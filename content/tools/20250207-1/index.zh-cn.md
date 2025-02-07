---
title: "Windows下GitHub可网页访问不可本地拉取推送"
date: 2025-02-07
description: "GitHub可网页访问不可本地拉取推送"
tags: ["git", "github", "ping", "pull"]
type: 'blog'
---

# 1. 问题描述
- GitHub可以网页访问

- GitHub不可本地拉取推送

- GitHub网址本地ping不通

- 报错如下

  ```bash
  $ git pull
  ssh: connect to host github.com port 22: Connection timed out
  fatal: Could not read from remote repository.
  
  Please make sure you have the correct access rights
  and the repository exists.
  
  $ ping github.com
  正在 Ping github.com [20.205.243.166] 具有 32 字节的数据:
  请求超时。
  请求超时。
  请求超时。
  请求超时。
  ```

  

# 2. 修复
## 2.1 查看GitHub动态IP写入hosts
- [查询网址](https://www.ipaddress.com/website/www.github.com/)

- 写入hosts

  ```ini
  140.82.112.3 github.com
  ```

## 2.2 修复效果

- 可以正常ping通以及拉取代码了

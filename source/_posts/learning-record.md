---
title: 寒假打卡记录
author: yuri2078
avatar: https://cdn.jsdelivr.net/gh/yuri2078/images/img/custom/avatar.jpg
authorLink: https://2078.site
authorAbout: 一般过路人
authorDesc: 一般过路人
categories: 小记
comments: true
description: 我的爱宛如孤岛之花，不为人知的绽放,不为人知的凋零！
photos: https://cdn.jsdelivr.net/gh/yuri2078/images/headPictures/15.png
date: 2023-01-05 20:19:01
tags:
keywords:
---

# 我的寒假学习打卡记录

## 2023 1 5 周四

### apollo 常用文件路径/命令

1. ` sudo systemctl restart docker` 重新启动docker服务
2. `docker ps -a` 查看所有容器
3. `docker start apollo_dev_用户名` 启动apollo容器
4. `bash docker/scripts/dev_into.sh` 在当前终端中进入apollo docker容器
5. `bash scripts/bootstrap.sh` 启动dreamview 
6. `bash scripts/bootstrap.sh stop` 停止dreamview



### leetcode 第29题

> 两数相除

解题思路 ： 二分法 + 快速乘法 

通过二分法找到需要的结果，通过快速乘法判断是否是我们需要的结果。另外的可能数据溢出的情况特殊考虑即可

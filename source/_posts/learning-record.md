---
title: 寒假打卡记录
author: yuri2078
avatar: https://cdn.jsdelivr.net/gh/yuri2078/images/img/custom/avatar.jpg
authorLink: https://2078.site
authorAbout: yuri
authorDesc: y
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



## 2023 1 6 周五

### leetcode 2180题

> 给你一个正整数 `num` ，请你统计并返回 **小于或等于** `num` 且各位数字之和为 **偶数** 的正整数的数目。
>
> 正整数的 **各位数字之和** 是其所有位上的对应数字相加的结果。

解题思路： 直接从1循环到num 然后依次判断是否符合条件就行

```c++
class Solution
{
public:
	int countEven(int num)
	{
		int res = 0;
		for (int i = 1; i <= num; i++) {
			if (!result(i)) {
				res++;
			}
		}
		return res;
	}

	bool result(int x)
	{
		int ans = 0;
		while (x) {
			ans += x % 10;
			x /= 10;
		}
		return ans % 2;
	}
};
```

### apollo **LaneChangeDecider**

>  **LaneChangeDecider 是lanefollow 场景下，所调用的第一个task，它的作用主要有两点：**

- **判断当前是否进行变道，以及变道的状态，并将结果存在变量lane_change_status中；**
- **变道过程中将目标车道的reference line放置到首位，变道结束后将当前新车道的reference line放置到首位**

[原文连接](https://zhuanlan.zhihu.com/p/496498679)

### 总结

1. stage阶段会调用每个 task 的 Execute() 函数 

2. LaneChangeDecider继承自 Decider 类，Decider继承自基类 task 类，并且override了Execute() 方法；

3.  task 里 的 Execute 函数原型 

   ```
   virtual common::Status Execute(Frame* *frame*);
   
   // decider.h 中的Execute重写函数。他调用完原来的Execute函数后，返回调用task 的 Process函数。
   apollo::common::Status Decider::Execute(Frame* frame) {
     Task::Execute(frame);
     return Process(frame);
   }
   ```

   

4. 每个task 继承自decider类，并且重写了虚继承的Process 函数。所以函数每次task 调用，实则主要逻辑在task 的 Process函数中

   ```c++
    // 重写Process 方法，用于每次调用
   common::Status Process( Frame* frame,
         ReferenceLineInfo* const      current_reference_line_info) override;
   ```

   

## 2023 1 7 周六

1. 进行绕行障碍物仿真调试
2. 升级apollo 8.0
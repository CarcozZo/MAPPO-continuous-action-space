# MAPPO with Continuous Actions (Tanh Squash)  
MAPPO连续动作版本（Tanh压缩）

> ⭐ PyTorch implementation of Multi-Agent Proximal Policy Optimization (MAPPO)  
> Supports **continuous action spaces** with Normal distribution + tanh squash, including log_prob correction.

> ⭐ 基于PyTorch实现的多智能体近端策略优化（MAPPO）  
> 支持**连续动作空间**，采用Normal分布+Tanh压缩，并进行log_prob修正。

---

## ✅ Features / 主要特性

- Continuous actions: Actor outputs mean and log_std  
  连续动作：Actor输出均值mean和对数标准差log_std  
- Actions squashed into [-1, 1] by tanh  
  动作通过tanh函数限制在[-1,1]范围内  
- Correct log_prob correction for PPO loss calculation  
  正确修正log_prob，适用于PPO损失计算  
- Uses a custom environment built on OpenAI Gym  
  基于 OpenAI Gym 框架自定义环境

---

## 🧠 Core Idea / 核心原理

- Actor outputs mean and log_std  
  Actor输出均值和对数标准差  
- Constructs Normal(mean, std) distribution  
  构建Normal(mean, std)正态分布  
- Sample raw_action with rsample(), then squash with tanh to [-1,1]  
  使用rsample()采样原始动作，再用tanh压缩到[-1,1]  
- Correct log_prob to account for tanh transformation:  
  修正log_prob以考虑tanh变换：  

## reward
<img width="518" height="351" alt="image" src="https://github.com/user-attachments/assets/70852486-f402-4259-bf1d-125024263726" />

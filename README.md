# MAPPO with Continuous Actions (Tanh Squash)  
MAPPO连续动作版本（Tanh压缩）

> ⭐ PyTorch implementation of Multi-Agent Proximal Policy Optimization (MAPPO)  
> Supports **continuous action spaces** with Normal distribution + tanh squash, including log_prob correction.

> ⭐ 基于PyTorch实现的多智能体近端策略优化（MAPPO）  
> 支持**连续动作空间**，采用Normal分布+Tanh压缩，并进行log_prob修正。

---

## Features / 主要特性

- Continuous actions: Actor outputs mean and log_std  
  连续动作：Actor输出均值mean和对数标准差log_std  
- Actions squashed into [-1, 1] by tanh  
  动作通过tanh函数限制在[-1,1]范围内  
- Correct log_prob correction for PPO loss calculation  
  正确修正log_prob，适用于PPO损失计算  
- Uses a custom environment built on OpenAI Gym  
  基于 OpenAI Gym 框架自定义环境
- Added act_dim in the constructor to represent the dimensionality of continuous actions (i.e., action vectors instead of discrete indices).
  在构造函数中新增 act_dim，用于指定每个动作向量的维度。连续动作通常是一个向量，而非单一离散动作编号。
- Changed the shape of a_n from (batch_size, episode_len, num_agents) to (batch_size, episode_len, num_agents, act_dim) to support continuous action vectors.
  将原来 a_n 的形状从 (B, T, N) 改为 (B, T, N, act_dim)，以适配每个 agent 的连续动作向量。

---

## reward
<img width="518" height="351" alt="image" src="https://github.com/user-attachments/assets/70852486-f402-4259-bf1d-125024263726" />

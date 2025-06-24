# AHMAPPO: Advanced Hierarchical Multi-Agent PPO for Financial Trading

A research-level trading simulation pipeline combining multi-agent reinforcement learning (PPO) with large language model (LLM)-based sentiment analysis.

## 🌟 Highlights
- Designed a custom Gym environment simulating financial markets with multiple RL agents.
- Integrated LLM (GPT-3.5) sentiment labeling for 100+ financial headlines.
- Trained multi-agent PPO models achieving:
  - 🎯 Avg. Reward: 60.7K
  - 📈 Sharpe Ratio: > 1.5
  - 🔍 Price Movement Recall: 83.7%
- Engineered feature space with RSI, Moving Averages, Momentum from 8 years of AAPL data.

## 📊 Project Overview
| Component | Description |
|----------|-------------|
| Environment | Custom Gym-based multi-agent simulation |
| Model      | PPO (Stable-Baselines3) with hierarchical agents |
| NLP        | GPT-3.5 for financial sentiment extraction |
| Results    | High return + Sharpe ratio, strong recall metrics |

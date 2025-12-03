# Reinforcement Learning for Prompt Engineering & Optimization

A curated collection of research implementations exploring Reinforcement Learning approaches for automated prompt engineering and optimization with Large Language Models.

## Overview

This repository aggregates cutting-edge work on using RL to discover, optimize, and refine prompts for LLMs. Instead of manual prompt engineering or gradient-based methods, these approaches treat prompt optimization as a sequential decision-making problem solved through reinforcement learning.

## Why RL for Prompts?

- **Automated Discovery**: Systematically explore prompt space without manual enumeration
- **Discrete & Interpretable**: Generate human-readable (or interestingly, non-human) text prompts
- **Model-Agnostic**: Work without gradient access or model fine-tuning
- **Transferable**: Prompts often generalize across different LLMs
- **Task-Flexible**: Apply to classification, generation, style transfer, and more

## Research Works

### RLPrompt: Optimizing Discrete Text Prompts with Reinforcement Learning
- **Paper**: [arXiv:2205.12548](https://arxiv.org/abs/2205.12548) | [PDF](docs/papers/rlprompt.pdf)
- **Code**: [rlprompt/](rlprompt/)
- **Highlights**: 
  - Parameter-efficient policy network generates discrete prompts
  - Reward stabilization handles LM environment complexity
  - Works with both masked (BERT) and autoregressive (GPT) models
  - Key finding: Optimal prompts are often ungrammatical "gibberish" yet transfer well between models
- **Tasks**: Few-shot classification, unsupervised text style transfer

---

### Prompt-OIRL: Query-Dependent Prompt Evaluation and Optimization with Offline Inverse RL
- **Paper**: [arXiv:2309.06553](https://arxiv.org/abs/2309.06553) | [PDF](docs/papers/prompt-oirl.pdf)
- **Code**: [Prompt-oirl/](Prompt-oirl/) | [Original Repo](https://github.com/vanderschaarlab/Prompt-OIRL)
- **Highlights**: 
  - Query-dependent optimization: Selects different prompts for different input queries rather than one-size-fits-all
  - Offline inverse RL: Learns from existing prompt benchmarking data without expensive online interactions
  - Resource-efficient: Avoids costly LLM interactions during training by leveraging offline demonstration data
  - Prompt evaluation: Addresses the challenge of evaluating prompts at inference time without ground truth
  - Published at ICLR 2024
- **Tasks**: Zero-shot arithmetic reasoning, query-specific prompt selection

---


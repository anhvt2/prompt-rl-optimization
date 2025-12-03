# RL for Prompt Engineering & Optimization

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

---

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

### StablePrompt: Automatic Prompt Tuning using Reinforcement Learning
- **Paper**: [arXiv:2410.07652](https://arxiv.org/abs/2410.07652) | [PDF](docs/papers/stableprompt.pdf)
- **Code**: [Stableprompt/](Stableprompt/) | [Original Repo](https://github.com/kmc0207/Stableprompt)
- **Highlights**: 
  - Addresses RL training instability through Adaptive Proximal Policy Optimization (APPO)
  - Introduces LLM anchor model to adaptively adjust policy update rates
  - Balances training stability with flexible prompt search space exploration
  - Preserves linguistic abilities of pre-trained LLMs during optimization
  - Extension: TTE-StablePrompt generates input-dependent prompts for complex tasks
  - Published at EMNLP 2024
- **Tasks**: Text classification, question answering, text generation

---

### Prompt-R1: Collaborative Automatic Prompting Framework via End-to-end RL
- **Paper**: [arXiv:2511.01016](https://arxiv.org/abs/2511.01016) | [PDF](docs/papers/Prompt-r1.pdf)
- **Code**: [Prompt-R1/](Prompt-R1/) | [Original Repo](https://github.com/QwenQKing/Prompt-R1)
- **Highlights**: 
  - Multi-agent collaboration: Small-scale LLM (agent) generates prompts for large-scale LLM (environment)
  - Multi-turn interaction: Iterative prompt refinement through agent-environment dialogue
  - Dual-constrained reward: Optimizes for correctness, generation quality, and reasoning accuracy
  - Plug-and-play framework: Supports both inference and training with various large-scale LLMs
  - Replaces user interaction: Automatically formulates effective prompts for complex tasks
  - Published November 2025
- **Tasks**: Complex reasoning tasks, multi-turn problem solving

---

### Prompt-oirl: Query-Dependent Prompt Evaluation and Optimization with Offline Inverse RL
- **Paper**: [arXiv:2309.06553](https://arxiv.org/abs/2309.06553) | [PDF](docs/papers/Prompt-oirl.pdf)
- **Code**: [Prompt-oirl/](Prompt-oirl/) | [Original Repo](https://github.com/vanderschaarlab/Prompt-oirl)
- **Highlights**: 
  - Query-dependent optimization: Selects different prompts for different input queries rather than one-size-fits-all
  - Offline inverse RL: Learns from existing prompt benchmarking data without expensive online interactions
  - Resource-efficient: Avoids costly LLM interactions during training by leveraging offline demonstration data
  - Prompt evaluation: Addresses the challenge of evaluating prompts at inference time without ground truth
  - Published at ICLR 2024
- **Tasks**: Zero-shot arithmetic reasoning, query-specific prompt selection

---

## Common Themes Across Works

- **Policy-based optimization**: Treating prompt generation as a sequential decision process
- **Black-box optimization**: Operating without access to model internals
- **Emergence**: Discovering non-intuitive prompt patterns that outperform human designs
- **Cross-model transfer**: Prompts optimized for one LLM often work on others

## Contributing

To add a new research work:

1. Add as submodule: `git submodule add <repo-url> <work-name>/`
2. Add paper to `docs/papers/`
3. Update this README with highlights and links
4. Ensure the submodule has clear documentation

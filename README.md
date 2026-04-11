# Build a Large Language Model (From Scratch) - 学习笔记

基于 Sebastian Raschka 的 [Build a Large Language Model (From Scratch)](https://github.com/rasbt/LLMs-from-scratch) 一书的实践项目。

## 项目结构

```
buildLLM/
├── ch01_understanding_llms/      # 第1章：理解大语言模型
├── ch02_working_with_text/       # 第2章：文本数据处理
├── ch03_attention_mechanisms/    # 第3章：注意力机制
├── ch04_gpt_architecture/        # 第4章：从零实现 GPT 架构
├── ch05_pretraining/             # 第5章：预训练
├── ch06_classification_finetuning/ # 第6章：分类微调
├── ch07_instruction_finetuning/  # 第7章：指令微调
├── data/                         # 数据文件
├── notebooks/                    # Jupyter 实验笔记
├── utils/                        # 工具函数
└── pyproject.toml                # 项目依赖
```

## 环境

- Python 3.11
- PyTorch 2.x
- 包管理：uv

## 快速开始

```bash
# 激活虚拟环境
source .venv/bin/activate

# 运行某章节代码
python ch02_working_with_text/tokenizer.py
```

## 学习进度

- [ ] Chapter 1: Understanding Large Language Models
- [ ] Chapter 2: Working with Text Data
- [ ] Chapter 3: Coding Attention Mechanisms
- [ ] Chapter 4: Implementing a GPT Model from Scratch
- [ ] Chapter 5: Pretraining on Unlabeled Data
- [ ] Chapter 6: Fine-tuning for Classification
- [ ] Chapter 7: Fine-tuning to Follow Instructions

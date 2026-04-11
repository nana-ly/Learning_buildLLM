# Build a Large Language Model (From Scratch) - 学习实践

基于 Sebastian Raschka 的 **[Build a Large Language Model (From Scratch)](https://www.manning.com/books/build-a-large-language-model-from-scratch)** 一书的动手实践项目。

每章一个 Jupyter Notebook，包含**概念讲解 + 代码实现 + 动手练习**，适合跟着书逐章学习。

## 前置要求

| 项目 | 要求 |
|------|------|
| **Python** | >= 3.11 |
| **包管理** | [uv](https://docs.astral.sh/uv/)（推荐）或 pip |
| **硬件** | CPU 即可完成全部练习（有 GPU 更好） |
| **前置知识** | Python 基础、了解 NumPy、一点点深度学习概念 |

## 快速开始

### 1. Fork & Clone

```bash
# 在 GitHub 上点 Fork，然后 clone 你自己的仓库
git clone https://github.com/funfungo/Learning_buildLLM
cd buildLLM
```

### 2. 安装环境

**方式一：使用 uv（推荐，速度快）**

```bash
# 安装 uv（如果还没有）
curl -LsSf https://astral.sh/uv/install.sh | sh

# 安装所有依赖（会自动创建 .venv 并安装正确的 Python 版本）
uv sync
```

**方式二：使用 pip**

```bash
# 先确保你的 Python 版本 >= 3.11
python3 --version

# 创建并激活虚拟环境
python3 -m venv .venv
source .venv/bin/activate   # macOS/Linux
# .venv\Scripts\activate    # Windows

# 安装依赖
pip install torch numpy tiktoken matplotlib pandas tqdm jupyterlab ipykernel
```

### 3. 启动 Jupyter Lab

```bash
# 使用 uv
uv run jupyter lab

# 或者激活虚拟环境后直接运行
source .venv/bin/activate
jupyter lab
```

### 4. 开始学习

在 Jupyter Lab 中按章节顺序打开 notebook：

```
ch02_working_with_text/ch02_working_with_text.ipynb   ← 从这里开始
```

> **提示：** 第 1 章是纯概念章（LLM 概述），没有代码。从第 2 章开始动手。

## 项目结构

```
buildLLM/
├── ch01_understanding_llms/        # 第1章：理解大语言模型（概念）
├── ch02_working_with_text/         # 第2章：文本数据处理
│   ├── ch02_working_with_text.ipynb  ← Jupyter Notebook（主要学习文件）
│   └── STUDY_GUIDE.md                ← 学习路线图（快速参考）
├── ch03_attention_mechanisms/      # 第3章：注意力机制
├── ch04_gpt_architecture/          # 第4章：从零实现 GPT 架构
├── ch05_pretraining/               # 第5章：预训练
├── ch06_classification_finetuning/ # 第6章：分类微调
├── ch07_instruction_finetuning/    # 第7章：指令微调
├── data/                           # 样本数据文件
│   └── the-verdict.txt               ← 第2章用到的小说文本
├── notebooks/                      # 自由实验用
├── utils/                          # 公共工具函数
├── pyproject.toml                  # 项目依赖定义
└── uv.lock                         # 依赖锁定文件
```

## 章节学习路线

| 章节 | 主题 | 核心内容 | 预计时间 |
|:----:|------|----------|:--------:|
| 1 | Understanding LLMs | LLM 全景概述、Transformer 架构概念 | 1 天 |
| 2 | Working with Text Data | 分词、BPE、DataLoader、Embedding | 2-3 天 |
| 3 | Attention Mechanisms | 点积注意力 → Causal Mask → Multi-Head | 2-3 天 |
| 4 | GPT Architecture | 组装完整 GPT 模型 | 2 天 |
| 5 | Pretraining | 训练循环、损失函数、加载 GPT-2 权重 | 2-3 天 |
| 6 | Classification Fine-tuning | 冻结 backbone + 分类头 | 1-2 天 |
| 7 | Instruction Fine-tuning | 指令数据集 + ChatGPT 式训练 | 2-3 天 |

## 学习建议

1. **逐 cell 运行** — 不要一次性 Run All，逐个 cell 执行并理解每步的输出
2. **修改参数做实验** — 改维度、改 batch_size、改 stride，观察变化
3. **完成练习** — 每节末尾都有 ✏️ 练习，这是加深理解最好的方式
4. **对照原书** — 遇到困难可参考 [作者的官方仓库](https://github.com/rasbt/LLMs-from-scratch)
5. **记笔记** — 在 `notebooks/` 目录下新建 notebook 记录你自己的思考

## 学习进度

用来跟踪你的进度，完成后打勾：

- [ ] Chapter 1: Understanding Large Language Models
- [ ] Chapter 2: Working with Text Data
- [ ] Chapter 3: Coding Attention Mechanisms
- [ ] Chapter 4: Implementing a GPT Model from Scratch
- [ ] Chapter 5: Pretraining on Unlabeled Data
- [ ] Chapter 6: Fine-tuning for Classification
- [ ] Chapter 7: Fine-tuning to Follow Instructions

## 常见问题

<details>
<summary><b>Q: 没有 GPU 能学吗？</b></summary>

可以。本项目所有练习都在小规模数据上运行，CPU 完全够用。第 5 章预训练时如果想跑更大数据，建议用 Google Colab 的免费 GPU。
</details>

<details>
<summary><b>Q: uv sync 报错怎么办？</b></summary>

确保 uv 版本 >= 0.4：
```bash
uv self update
uv sync
```
或者跳过 uv，用 pip 方式安装（见上方「方式二」）。
</details>

<details>
<summary><b>Q: Jupyter Lab 找不到 kernel？</b></summary>

```bash
# 确保在虚拟环境中安装 ipykernel
source .venv/bin/activate
python -m ipykernel install --user --name buildllm --display-name "BuildLLM (Python 3.11)"
```
然后在 Jupyter Lab 中选择 "BuildLLM (Python 3.11)" kernel。
</details>

<details>
<summary><b>Q: torch 安装很慢/失败？</b></summary>

如果在中国大陆，可以使用镜像源：
```bash
pip install torch -i https://pypi.tuna.tsinghua.edu.cn/simple
```
</details>

## 参考资源

- [Build a Large Language Model (From Scratch)](https://www.manning.com/books/build-a-large-language-model-from-scratch) — 原书
- [rasbt/LLMs-from-scratch](https://github.com/rasbt/LLMs-from-scratch) — 作者官方代码仓库
- [The Illustrated Transformer](https://jalammar.github.io/illustrated-transformer/) — 经典图解文章
- [tiktoken](https://github.com/openai/tiktoken) — OpenAI 的 BPE 分词库

## License

本项目仅用于个人学习目的。书籍版权归 Sebastian Raschka 和 Manning 出版社所有。

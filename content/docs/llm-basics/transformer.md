---
title: "Transformer 架构"
weight: 1
---

# Transformer 架构

Transformer 是现代大语言模型的核心架构，由 Google 在 2017 年的论文《Attention Is All You Need》中提出。

## 核心组件

### Self-Attention（自注意力机制）

自注意力机制允许模型在处理每个 token 时关注输入序列中的所有其他 token。

计算过程：
1. 将输入向量分别乘以三个权重矩阵，得到 **Query (Q)**、**Key (K)**、**Value (V)**
2. 计算注意力分数：`Attention(Q, K, V) = softmax(QK^T / √d_k) V`

### Multi-Head Attention（多头注意力）

将注意力机制并行运行多次，每个"头"学习不同的注意力模式：

```
MultiHead(Q, K, V) = Concat(head_1, ..., head_h) W^O
```

### Feed-Forward Network（前馈网络）

每个 Transformer 层都包含一个两层的前馈网络：

```
FFN(x) = max(0, xW_1 + b_1) W_2 + b_2
```

## Encoder vs Decoder

| 类型 | 代表模型 | 适用任务 |
|------|---------|---------|
| Encoder-only | BERT | 文本分类、NER |
| Decoder-only | GPT | 文本生成 |
| Encoder-Decoder | T5 | 翻译、摘要 |

## 位置编码

由于 Transformer 本身不包含序列顺序信息，需要通过位置编码引入位置信息。常见方法：

- **正弦位置编码**：原始 Transformer 使用的固定编码
- **RoPE（旋转位置编码）**：LLaMA 等模型使用，支持更好的长度外推

---
title: "主流框架对比"
weight: 1
---

# 主流 AI 框架对比

## 模型推理 & 部署

| 框架 | 语言 | 特点 | 适用场景 |
|------|------|------|---------|
| vLLM | Python | 高吞吐 PagedAttention | 大规模 LLM 推理 |
| Ollama | Go | 一键本地部署 | 个人/开发环境 |
| llama.cpp | C++ | CPU 推理，量化支持 | 边缘设备部署 |
| TGI | Python | HuggingFace 官方 | 生产环境推理 |

## 应用开发框架

| 框架 | 特点 | 适用场景 |
|------|------|---------|
| LangChain | 模块化组合，生态丰富 | 快速原型开发 |
| LlamaIndex | 专注 RAG，数据索引强 | 知识库问答 |
| Semantic Kernel | 微软出品，企业级 | .NET/Java 生态 |
| Dify | 可视化编排，低代码 | 快速搭建应用 |

## 向量数据库

| 数据库 | 语言 | 特点 |
|--------|------|------|
| Milvus | Go/C++ | 高性能，分布式 |
| Chroma | Python | 轻量，易上手 |
| Qdrant | Rust | 高性能，过滤强 |
| Weaviate | Go | 多模态支持 |
| Pinecone | 托管服务 | 免运维 |

## 推荐组合

**入门学习：** Ollama + LangChain + Chroma

**生产部署：** vLLM + LlamaIndex + Milvus

---

title: 理解与配置 DocsGPT 中的嵌入模型
description: 了解嵌入模型及其在 DocsGPT 中的重要性，以及如何配置以获得最佳性能。
---

# 理解与配置 DocsGPT 中的嵌入模型

嵌入模型是 DocsGPT 的核心组件，为其提供了强大的文档理解与问答能力。本指南将阐述嵌入模型的概念、其在 DocsGPT 中的关键作用以及配置方法。

## 什么是嵌入模型？

简而言之，嵌入模型是一种将文本转换为数值向量的语言模型。这些被称为嵌入的向量能够捕捉文本的语义信息。可以将其理解为将单词和句子翻译成计算机能够通过数学方式理解的语言，其中语义相近的内容在向量空间中表现为彼此接近的向量。

**为什么嵌入模型对 DocsGPT 至关重要？**

DocsGPT 依赖嵌入模型完成多项关键任务：

*   **语义搜索:** 当您将文档上传至 DocsGPT 时，应用程序会使用嵌入模型为每个文档片段生成嵌入向量。这些向量存储在向量数据库中。当您提出问题时，您的查询也会被转换为嵌入向量。DocsGPT 随后在向量数据库中进行语义搜索，找出与您查询向量最相似的文档片段。这使得 DocsGPT 能够基于问题和文档的*语义*关联性（而非仅关键词匹配）检索相关信息。
*   **文档理解:** 嵌入向量帮助 DocsGPT 理解文档的深层含义，使其即便在检索到的文档片段中未出现提问的精确关键词时，仍能给出准确且符合语境的回答。

本质上，嵌入模型是使 DocsGPT 能够理解人类语言细微差别，并将您的问题与文档中相关信息连接起来的桥梁。

## DocsGPT 开箱即用的嵌入模型支持

DocsGPT 设计灵活，默认支持多种嵌入模型。目前提供对以下两大来源模型的原生支持：

*   **Sentence Transformers:** DocsGPT 支持通过 [Sentence Transformers library](https://www.sbert.net/) 提供的所有模型。该库提供了大量预训练的嵌入模型，这些模型在各种语义任务中以质量和效率著称。
*   **OpenAI 嵌入:** DocsGPT 同样支持使用 OpenAI 的嵌入模型，特别是 `text-embedding-ada-002` 模型，这是 OpenAI API 中一个功能强大且广泛使用的嵌入模型。

## 配置 Sentence Transformer 模型

要在 DocsGPT 中使用 Sentence Transformer 模型，您需要按照以下步骤操作：

1. **下载模型：** Sentence Transformer 模型通常托管在 Hugging Face Model Hub 上。您需要下载所选模型并放置到 DocsGPT 项目根目录的 `model/` 文件夹中。

    例如，要使用 `all-mpnet-base-v2` 模型，您需要按以下说明设置 `EMBEDDINGS_NAME`，并确保模型文件在本地可用（如果未找到模型，DocsGPT 会尝试自动下载，但建议在开发和离线使用时预先本地下载）。

2. **在 `.env`（或 `settings.py`）中设置 `EMBEDDINGS_NAME`：** 您需要在 `.env` 文件（或 `settings.py`）中配置 `EMBEDDINGS_NAME` 参数，指向所需的 Sentence Transformer 模型。

    * **使用 `model/` 文件夹中预下载的模型：** 可以指定 `model/` 目录内已下载模型的路径。例如，如果您下载了 `all-mpnet-base-v2` 并放在 `model/all-mpnet-base-v2` 中，可以使用如下相对路径（不过通常直接使用模型名称即可）：

        ```
        EMBEDDINGS_NAME=huggingface_sentence-transformers/all-mpnet-base-v2
        ```
        或直接使用模型标识符：
        ```
        EMBEDDINGS_NAME=sentence-transformers/all-mpnet-base-v2
        ```

    * **直接从 Hugging Face Model Hub 使用模型：** 可以直接指定 Hugging Face Model Hub 中的模型标识符：

        ```
        EMBEDDINGS_NAME=huggingface_sentence-transformers/all-mpnet-base-v2
        ```

## 使用 OpenAI 嵌入模型

要使用 OpenAI 的 `text-embedding-ada-002` 嵌入模型，需将 `EMBEDDINGS_NAME` 设为 `openai_text-embedding-ada-002`，并通过 `.env` 文件中的 `API_KEY` 正确配置 OpenAI API 密钥（若未使用 Azure OpenAI）。

**OpenAI 嵌入模型的示例 `.env` 配置：**

```
LLM_PROVIDER=openai
API_KEY=YOUR_OPENAI_API_KEY # Your OpenAI API Key
EMBEDDINGS_NAME=openai_text-embedding-ada-002
```

## 添加对其他嵌入模型的支持

如需使用非开箱即用的嵌入模型，可参考 `application/vectorstore` 目录下的 `base.py` 文件作为自定义嵌入模型支持的实现起点。

特别关注 `EmbeddingsWrapper` 和 `EmbeddingsSingleton` 类：`EmbeddingsWrapper` 提供了将不同嵌入模型库封装为统一接口的方法；`EmbeddingsSingleton` 负责管理嵌入模型实例的初始化与获取。通过理解这些类及现有实现，可为任意嵌入模型库创建自定义集成方案。
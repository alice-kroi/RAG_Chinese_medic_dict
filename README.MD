# 中华药典智能问答系统 - RAG实战项目

基于检索增强生成（RAG）架构的药学知识问答系统，结合Elasticsearch结构化检索与FAISS语义检索，实现对中华药典的高效查询。

**开发者**：我 & 可乐  
仅做分享与学习用

## 🌟 核心功能

### 混合检索引擎
- **Elasticsearch**：精确匹配药品说明书中的结构化内容  
- **FAISS**：基于`paraphrase-multilingual`模型的语义相似度检索  
- **智能路由**：自动选择最佳检索策略

### 安全机制
- 🛡️ 问题分类过滤（`classify_pharmacy_query`函数）
- 🔒 敏感词替换机制（GMP/GSP相关术语自动脱敏）
- ⚠️ 非药学问题直接调用OpenAI

## 🚀 快速开始

### 依赖安装
```bash
pip install -e .
```
### 服务启动
```bash
python -m rag_project_zhyd.pkg.webrun
```

⚙️ 系统配置


# 默认配置（生产环境需修改）
ES_HOST = '192.168.110.28'  # 内网ES地址
ES_PORT = 9200
ES_AUTH = ('elastic', )  # 请及时更改密码

### 向量数据库

# 默认存储路径
./embeddings2.npz  # 包含预训练的语义索引
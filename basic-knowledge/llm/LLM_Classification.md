# 大模型分类


## LLM
（基座模型）


### 定义：未经任务微调的通用预训练语言模型，具备基础语言能力


### 训练：大规模无监督预训练


### 示例：GPT-3、Qwen-7B


### 场景：模型预研、基础文本生成底座


## LLM-Instruct
（指令模型）


### 定义：擅长理解执行自然语言指令的任务导向模型


### 训练：SFT+RLHF，对话数据增强


### 示例：Kimi-K2-Instruct、Qwen3-4B-Instruct-2507 


### 场景：代码生成、信息提取、专项任务


## LLM-Chat
（对话模型）


### 定义：针对多轮对话优化，可上下文感知的交互模型


### 训练：SFT+RLHF，指令-响应数据增强


### 示例：ChatGPT、Qwen-7B-Chat


### 场景：智能客服、闲聊机器人、对话交互


## LLM-Thinking
（推理模型）


### 定义：具逻辑推理能力，可分步思考的模型


### 训练：思维链微调、RLHF等


### 示例：LongCat-Flash-Thinking、Qwen3-4B-Thinking-2507


### 场景：数学解题、逻辑分析、复杂问题拆解


## LLM-Agentic
（Agent模型）


### 定义：强化自主决策、工具调用与多步推理的智能体模型


### 训练：Agentic CPT、Agentic SFT、Agentic RL


### 示例：Tongyi-DeepResearch-30B-A3B


### 场景：复杂研究、金融分析、多工具协同等需深度推理场景


## LLM-Domain
（领域模型）


### 定义：针对特定领域知识优化的专业语言模型


### 训练：领域知识CPT、领域指令SFT


### 示例：Qwen2.5-Coder-32B、medgemma-4b


### 场景：代码编程、医疗辅助、法律解读、金融咨询等垂直领域


## LLM-Distill
(蒸馏模型)


### 定义：压缩大模型知识至小模型的轻量化模型


### 训练：KD知识蒸馏


### 示例：DeepSeek-R1-Distill-Qwen-7B、DeepSeek-R1-Distill-Llama-8B


### 场景：边缘设备、移动端等低算力场景


# WebWalker QA数据集格式解析


## 0.数据集文件


### hugging face的dataset开源数据集main-00000-of-00001.jsonl



### 采用JSON Lines（.jsonl）格式（每行对应一个独立的 QA 样本），共包含 680 个经过严格标注的高质量问答对，用于评估 LLM 网页遍历能力（Web Traversal 任务）的核心数据载体。


## 1. 核心字段结构（JSON格式）

### question：待回答的Web遍历查询
（如“ACL 2025 Industry Track的论文提交截止日期是什么？”）


#### 要求：需通过多步网页导航解决，避免无实际意义的路径类问题

### answer：标准答案


#### 约束：实体类简短内容（如日期、名称、数值），无长文本

### root_url：初始网站URL（如“https://2025.aclweb.org/”）


#### 作用：WebWalker框架垂直探索的起点

### info：元数据集合（核心子字段如下）


## 2. Info子字段详情

### type：任务类型标识（“single-source”/“multi-source”）


#### 单源：标注为“single_sourcei”（i∈[2,4]，i为子页面深度）

#### 多源：标注为“multi_sourcei”（i∈[2,8]，i为两个子页面深度之和）

### domain：数据领域（4类）


#### conference（会议，24.0%）、organization（组织，7.9%）

#### education（教育，46.3%）、game（游戏，24.0%）

### lang：数据语言（双语）


#### 中文（60.5%）、英文（39.5%），基于初始网站语言分类

### difficulty_Level：难度等级（3级）


#### 单源：easy（i=2）、medium（i=3）、hard（i=4）

#### 多源：easy（i=2-4）、medium（i=4-6）、hard（i=6-8）

### source_website：答案来源网页URL列表


#### 单源：1个URL；多源：2个及以上URL（如“https://2025.aclweb.org/calls/industry_track/”“https://2025.aclweb.org/venue/”）

### golden_path：正确导航路径列表


#### 格式：“root-&gt;子页面1-&gt;子页面2...”（如“root-&gt;call&gt;student_research_workshop”“root-&gt;venue”）

## 3. 数据规模与质量控制

### 总规模：680个高质量QA对（含单源440个、多源240个）

#### 单源难度分布：easy（80）、medium（140）、hard（120）

#### 多源难度分布：easy（80）、medium（140）、hard（120）

### 质量控制：两阶段标注（GPT-4o初始标注→人工校验改写）

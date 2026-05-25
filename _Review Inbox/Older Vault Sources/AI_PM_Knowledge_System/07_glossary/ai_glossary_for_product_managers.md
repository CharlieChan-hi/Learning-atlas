> **写给谁：** 完全零基础的传统互联网产品经理
> **怎么用：** 遇到不懂的术语，按字母查找即可
> **词条格式：** 中文名 → 一句话解释 → PM 需要知道的点
> **收录数量：** 60 个核心术语，按英文字母排列

---

## 使用指南

每个词条包含四行信息：

1. **中文名**（English Name, 缩写）
2. 一句话中文解释
3. *One-line English explanation*
4. 💡 PM要知道的：一句实用建议

> 🌐 **In English:** Each entry has 4 lines — Chinese name, Chinese explanation, English explanation, and a practical PM tip.

---

## A

---

**智能体**（Agent）

能自主规划、决策并调用工具完成复杂任务的 AI 系统，不只是"问一句答一句"。

*An AI system that can autonomously plan, make decisions, and use tools to accomplish complex tasks.*

💡 PM要知道的：Agent 是 2024-2025 年最大的产品趋势，理解它等于理解下一代 AI 产品形态。

---

**对齐**（Alignment）

让 AI 的行为符合人类意图和价值观的技术，确保 AI "听话"且"不作恶"。

*The process of ensuring AI systems behave in accordance with human intentions and values.*

💡 PM要知道的：对齐直接影响产品安全性，如果 AI 输出不当内容，就是对齐没做好。

---

**应用程序接口**（API, Application Programming Interface）

软件之间互相通信的标准接口，调用 AI 能力的主要方式。

*A standardized interface that allows different software systems to communicate with each other.*

💡 PM要知道的：大多数 AI 产品都是通过 API 接入大模型能力的，你需要了解调用成本和速率限制。

---

**注意力机制**（Attention Mechanism）

让 AI 在处理文本时，能"重点关注"最相关部分的核心技术。

*A technique that allows AI to focus on the most relevant parts of the input when processing text.*

💡 PM要知道的：这是 Transformer 的核心，理解它能帮你理解为什么 AI 有时会"忽略"长文本的中间部分。

---

## B

---

**基准测试**（Benchmark）

用标准化测试集衡量 AI 模型能力的方法，类似于"模型的高考成绩"。

*A standardized test used to measure and compare AI model performance across specific tasks.*

💡 PM要知道的：不要只看跑分选模型，要关注跟你业务场景最接近的测试结果。

---

## C

---

**思维链**（Chain-of-Thought, CoT）

让 AI 一步步展示推理过程的提示技术，而不是直接给答案。

*A prompting technique that encourages the AI to show its step-by-step reasoning process.*

💡 PM要知道的：在产品中让 AI "展示思考过程"，用户信任度会大幅提高。

---

**Claude**

Anthropic 公司开发的大语言模型系列，以安全性和长文本能力著称。

*A family of large language models developed by Anthropic, known for safety and long-context capabilities.*

💡 PM要知道的：Claude 的上下文窗口很大（最高 200K tokens），适合处理长文档场景。

---

**上下文窗口**（Context Window）

AI 模型一次能"看到"和处理的最大文本长度，类似于"工作记忆容量"。

*The maximum amount of text an AI model can process in a single interaction — its working memory.*

💡 PM要知道的：上下文窗口决定了产品能处理多长的文档，直接影响产品设计和用户体验。

---

**计算机使用**（Computer Use）

AI 能像人一样操作电脑界面的能力，包括点击、输入、浏览网页等。

*The ability of AI to interact with computer interfaces like a human — clicking, typing, and browsing.*

💡 PM要知道的：这是 AI Agent 的基础能力之一，意味着 AI 可以替用户完成操作性工作。

---

## D

---

**数据集**（Dataset）

用于训练或测试 AI 模型的结构化数据集合。

*A structured collection of data used to train or evaluate AI models.*

💡 PM要知道的：数据质量决定模型质量。做 AI 产品，首先要想清楚"数据从哪来"。

---

**蒸馏**（Distillation）

把大模型的知识"压缩"到小模型中的技术，让小模型也有大模型的部分能力。

*A technique to transfer knowledge from a large model into a smaller one, preserving capability at lower cost.*

💡 PM要知道的：蒸馏让端侧 AI（手机、嵌入式设备）成为可能，意味着更低成本和更快速度。

---

## E

---

**嵌入**（Embedding）

把文字、图片等内容转化为数字向量的技术，让 AI 能计算内容之间的"相似度"。

*Converting text, images, or other content into numerical vectors so AI can measure similarity between them.*

💡 PM要知道的：搜索、推荐、知识库问答等功能的底层都依赖 Embedding。

---

**评测**（Evals / Evaluation）

系统化地测试和衡量 AI 模型在特定任务上表现的过程。

*The systematic process of testing and measuring AI model performance on specific tasks.*

💡 PM要知道的：上线 AI 功能前必须做评测，这是你确保产品质量的核心手段。

---

## F

---

**微调**（Fine-tuning）

在预训练模型基础上，用特定领域数据进一步训练，让模型更擅长某个专业任务。

*Additional training on domain-specific data to specialize a pre-trained model for particular tasks.*

💡 PM要知道的：微调成本高、周期长，先试 Prompt Engineering 和 RAG，不行再考虑微调。

---

**少样本学习**（Few-shot Learning）

在 Prompt 中给 AI 几个示例，让它学会新任务的模式，不需要重新训练。

*Providing a few examples in the prompt so the AI learns the pattern without retraining.*

💡 PM要知道的：这是最实用的提示技巧之一，产品中可以内置好示例来稳定 AI 输出格式。

---

**基础模型**（Foundation Model）

在海量数据上预训练的大规模通用模型，可以适配到各种下游任务。

*A large-scale model pre-trained on vast data that can be adapted to a wide range of downstream tasks.*

💡 PM要知道的：GPT、Claude、Gemini 都是基础模型，你的产品是在它们之上构建应用层。

---

**函数调用**（Function Calling）

让 AI 模型能够调用外部函数或 API 的能力，实现与外部系统的交互。

*The ability for AI models to invoke external functions or APIs, enabling interaction with outside systems.*

💡 PM要知道的：Function Calling 是 AI 产品连接真实业务系统的关键桥梁。

---

## G

---

**生成式 AI**（Generative AI, GenAI）

能创造新内容（文字、图片、代码、音视频等）的 AI 技术总称。

*AI technology that can create new content — text, images, code, audio, video, and more.*

💡 PM要知道的：当前 AI 产品热潮的主角，但不是所有场景都适合用"生成"，有些场景用"检索"更靠谱。

---

**GPT**（Generative Pre-trained Transformer）

OpenAI 开发的生成式预训练 Transformer 模型系列，也常被泛指大语言模型。

*A family of generative pre-trained transformer models by OpenAI, often used as a generic term for LLMs.*

💡 PM要知道的："GPT"已经成为大众对 AI 的代名词，但市场上有很多同等优秀的竞品。

---

**落地/接地**（Grounding）

让 AI 的回答基于真实数据和事实，而不是凭空生成，减少幻觉。

*Anchoring AI responses in real data and facts rather than generating from learned patterns alone.*

💡 PM要知道的：Grounding 是提高 AI 回答准确性的关键策略，通常与 RAG 配合使用。

---

**护栏**（Guardrails）

限制 AI 输出范围和行为的安全机制，防止不当内容、格式错误等问题。

*Safety mechanisms that constrain AI outputs and behavior to prevent harmful or incorrect responses.*

💡 PM要知道的：每个 AI 产品都必须设计护栏，这是产品经理的核心职责之一。

---

## H

---

**幻觉**（Hallucination）

AI "一本正经地胡说八道"——生成看似合理但实际不正确的内容。

*When AI generates content that sounds plausible but is factually incorrect — confidently making things up.*

💡 PM要知道的：幻觉是 AI 产品最大的风险之一，产品设计中必须有校验机制。

---

**人在回路中**（Human-in-the-loop, HITL）

在 AI 流程中保留人工审核和干预环节，确保关键决策由人做最终判断。

*Keeping humans involved in AI workflows to review, validate, or override AI decisions at critical points.*

💡 PM要知道的：高风险场景（医疗、金融、法律）必须有 HITL，这是合规要求也是产品底线。

---

## I

---

**推理**（Inference）

已训练好的 AI 模型处理输入并生成输出的过程，也就是模型"干活"的阶段。

*The process where a trained AI model processes input and generates output — the model doing its job.*

💡 PM要知道的：推理需要算力和时间，直接影响产品的响应速度和使用成本。

---

**上下文学习**（In-context Learning, ICL）

AI 通过 Prompt 中提供的信息和示例，临时学会新任务，无需重新训练。

*The AI learns to perform new tasks from information and examples provided in the prompt, without retraining.*

💡 PM要知道的：这是大模型最神奇的能力之一，意味着你可以通过精心设计 Prompt 来"教会" AI 做新事情。

---

**指令微调**（Instruction Tuning）

用"指令-回答"配对数据训练模型，让模型更擅长理解和执行人类指令。

*Training a model with instruction-response pairs to improve its ability to follow human instructions.*

💡 PM要知道的：经过指令微调的模型才会"听话"，原始基础模型其实并不擅长按指令做事。

---

## J

---

**JSON 模式**（JSON Mode）

让 AI 模型以结构化 JSON 格式输出结果，方便程序解析和处理。

*A mode that forces the AI to output results in structured JSON format for easy programmatic parsing.*

💡 PM要知道的：AI 功能要集成到产品中，结构化输出是必须的，JSON Mode 大幅降低了解析出错率。

---

## K

---

**知识截止日期**（Knowledge Cutoff）

AI 模型训练数据的截止时间，模型不知道这个日期之后发生的事情。

*The date when the AI's training data ends — the model has no knowledge of events after this point.*

💡 PM要知道的：这解释了为什么 AI 有时回答不了最近的事。需要结合 RAG 或联网搜索来补充。

---

## L

---

**大语言模型**（LLM, Large Language Model）

在海量文本上训练的超大规模语言模型，具备理解和生成自然语言的能力。

*A very large neural network trained on massive text data, capable of understanding and generating natural language.*

💡 PM要知道的：LLM 是当前 AI 产品的核心引擎，你要了解不同 LLM 的能力边界和成本差异。

---

**延迟**（Latency）

从用户发送请求到收到 AI 响应的时间间隔。

*The time delay between sending a request to the AI and receiving the response.*

💡 PM要知道的：延迟直接影响用户体验。流式输出（Streaming）可以大幅改善感知延迟。

---

**低秩适配**（LoRA, Low-Rank Adaptation）

一种高效微调技术，只训练模型的一小部分参数，大幅降低微调成本。

*An efficient fine-tuning method that trains only a small subset of model parameters, drastically reducing cost.*

💡 PM要知道的：LoRA 让中小公司也能负担得起模型定制，是降低 AI 产品成本的重要技术。

---

**LangChain**

一个帮助开发者快速构建 LLM 应用的开源框架，提供链式调用、记忆管理等能力。

*An open-source framework that helps developers build LLM-powered applications with chaining, memory, and tools.*

💡 PM要知道的：如果团队在用 LangChain，说明他们在搭建 AI 应用的"中间层"，了解它的概念有助于沟通。

---

## M

---

**MCP**（Model Context Protocol）

Anthropic 提出的标准协议，让 AI 模型能以统一方式连接和使用外部工具与数据源。

*A protocol by Anthropic that standardizes how AI models connect to and use external tools and data sources.*

💡 PM要知道的：MCP 正在成为 AI 连接外部世界的行业标准，类似于"AI 时代的 USB 接口"。

---

**模型**（Model）

经过训练后能执行特定任务的 AI 程序，是 AI 产品的核心"大脑"。

*A trained AI program capable of performing specific tasks — the core brain behind AI products.*

💡 PM要知道的：选择合适的模型是 AI 产品最重要的技术决策之一，要平衡能力、成本和速度。

---

**多模态**（Multimodal）

AI 能同时处理和生成多种类型内容（文本、图片、音频、视频）的能力。

*The ability of AI to process and generate multiple types of content — text, images, audio, and video.*

💡 PM要知道的：多模态正在打破"AI只能聊天"的局限，产品可以支持图文混合输入和输出了。

---

**记忆**（Memory）

AI 系统在多轮对话或多次会话中记住上下文和用户偏好的能力。

*The ability of AI to retain context and user preferences across conversation turns or sessions.*

💡 PM要知道的：记忆能力直接影响用户的"被理解感"，是 AI 产品差异化竞争的关键点。

---

**多智能体**（Multi-agent）

多个 AI Agent 协作完成复杂任务的系统架构，每个 Agent 负责不同的子任务。

*A system where multiple AI agents collaborate on complex tasks, each handling different sub-tasks.*

💡 PM要知道的：复杂业务流程可以拆成多个 Agent 协作处理，但也增加了系统复杂度和调试难度。

---

## N

---

**神经网络**（Neural Network）

模仿人脑神经元连接方式的计算模型，是现代 AI 的基础架构。

*A computing model inspired by the structure of the human brain — the foundation of modern AI.*

💡 PM要知道的：你不需要理解数学原理，但要知道"模型越大（参数越多），通常能力越强，成本也越高"。

---

**自然语言处理**（NLP, Natural Language Processing）

让计算机理解、处理和生成人类语言的技术领域。

*The field of technology enabling computers to understand, process, and generate human language.*

💡 PM要知道的：NLP 是个老概念了，LLM 的出现让 NLP 从"勉强能用"变成了"真正好用"。

---

## O

---

**开源模型**（Open Source Model）

代码和权重公开的 AI 模型，任何人都可以下载、使用和修改。

*AI models with publicly available code and weights that anyone can download, use, and modify.*

💡 PM要知道的：开源模型意味着更低成本和更高灵活性，但也需要更多技术能力来部署和维护。

---

**输出 Token**（Output Token）

AI 模型生成的回答中包含的 Token 数量，直接影响使用费用。

*The number of tokens in the AI's generated response, directly affecting usage cost.*

💡 PM要知道的：输出 Token 通常比输入 Token 贵 2-4 倍，控制输出长度是控制成本的关键。

---

## P

---

**提示词**（Prompt）

用户输入给 AI 的指令或问题，是控制 AI 行为的最直接方式。

*The instruction or question given to an AI — the most direct way to control AI behavior.*

💡 PM要知道的：Prompt 的质量直接决定 AI 输出的质量，产品中的预设 Prompt 需要精心打磨。

---

**提示词工程**（Prompt Engineering）

通过精心设计和优化 Prompt，让 AI 产出更准确、更有用结果的技术和方法。

*The art and science of designing and optimizing prompts to get better, more reliable AI outputs.*

💡 PM要知道的：Prompt Engineering 是 PM 最应该掌握的 AI 技能，不需要写代码也能做。

---

**预训练**（Pre-training）

在大规模数据上对模型进行初始训练的过程，让模型获得通用的语言理解能力。

*The initial training of a model on massive data to develop general language understanding capabilities.*

💡 PM要知道的：预训练成本极高（数千万到数亿美元），这是为什么只有大公司才能训练基础模型。

---

**参数**（Parameter）

模型中用于存储学习到的知识的数值，参数越多通常意味着模型越大、能力越强。

*Numerical values in a model that store learned knowledge — more parameters generally means greater capability.*

💡 PM要知道的：参数量是模型规模的粗略指标（如 7B = 70亿参数），但不要唯参数量论。

---

## R

---

**检索增强生成**（RAG, Retrieval-Augmented Generation）

让 AI 先检索相关资料再回答问题的技术，大幅减少幻觉，提高准确性。

*A technique where AI retrieves relevant documents before answering, greatly reducing hallucination.*

💡 PM要知道的：RAG 是当前 AI 产品中最实用的技术之一。做知识库问答、客服机器人首选 RAG。

---

**基于人类反馈的强化学习**（RLHF, Reinforcement Learning from Human Feedback）

通过人类评估员的反馈来训练 AI 的技术，让 AI 的回答更符合人类偏好。

*Training AI using human evaluator feedback to align model outputs with human preferences.*

💡 PM要知道的：RLHF 是让 AI 从"能说话"变成"说人话"的关键技术，直接影响用户体验。

---

**推理能力**（Reasoning）

AI 模型进行逻辑思考、分析和推导的能力，而不只是模式匹配。

*The AI's ability to think logically, analyze, and deduce — beyond simple pattern matching.*

💡 PM要知道的：推理能力强的模型适合复杂决策场景，但推理越复杂、响应越慢、成本越高。

---

## S

---

**技能**（Skills）

AI 系统中预定义的特定能力模块，可以被 Agent 调用来完成专项任务。

*Pre-defined capability modules in an AI system that can be invoked by agents for specialized tasks.*

💡 PM要知道的：将产品功能封装为"技能"，可以让 AI Agent 灵活组合使用，提高产品扩展性。

---

**流式输出**（Streaming）

AI 一边生成一边实时传输结果给用户，而不是等全部生成完再显示。

*Delivering AI output in real-time as it is generated, rather than waiting for the complete response.*

💡 PM要知道的：流式输出是改善用户等待体验的标配方案，几乎所有聊天类 AI 产品都在用。

---

**安全性**（Safety）

确保 AI 系统不会产生有害、不当或危险输出的各项措施和技术。

*Measures and techniques ensuring AI systems do not produce harmful, inappropriate, or dangerous outputs.*

💡 PM要知道的：AI 安全不只是技术问题，也是产品和法律问题。上线前必须做安全测试（红队测试）。

---

**规模定律**（Scaling Law）

AI 模型性能与数据量、模型大小、算力之间存在的可预测的数学关系。

*The predictable mathematical relationship between AI model performance, data size, model size, and compute.*

💡 PM要知道的：Scaling Law 意味着"更大的模型通常更强"，但也有边际递减，关注性价比。

---

**系统提示词**（System Prompt）

开发者预设的隐藏指令，定义 AI 的角色、行为规则和回答风格。

*Hidden instructions set by developers that define the AI's role, behavior rules, and response style.*

💡 PM要知道的：System Prompt 是 PM 定义"AI 产品人格"的核心工具，写好它等于做好了产品设计的一半。

---

## T

---

**Token**

AI 处理文本的基本单位，大约 1 个英文单词 = 1 Token，1 个中文字 = 1.5-2 Token。

*The basic unit AI uses to process text — roughly 1 English word or 1.5-2 Chinese characters per token.*

💡 PM要知道的：Token 直接关系到成本计算。了解 Token 定价是做 AI 产品商业模型的基础。

---

**Transformer**

2017 年 Google 提出的神经网络架构，几乎所有现代大语言模型都基于它。

*A neural network architecture proposed by Google in 2017 that underlies virtually all modern large language models.*

💡 PM要知道的：你不需要懂 Transformer 的数学，但要知道"注意力机制"是它的核心创新。

---

**温度**（Temperature）

控制 AI 输出随机性的参数。温度越低越确定，温度越高越有创意。

*A parameter controlling output randomness — lower values are more deterministic, higher values more creative.*

💡 PM要知道的：写代码、做分析用低温度（0-0.3），写创意文案用高温度（0.7-1.0），这是产品调参的基本技巧。

---

**工具使用**（Tool Use）

AI 模型调用外部工具（搜索引擎、计算器、数据库等）来增强自身能力的功能。

*The AI model's ability to invoke external tools like search engines, calculators, and databases to enhance itself.*

💡 PM要知道的：Tool Use 让 AI 从"只会聊天"进化为"能做事"，是构建 AI Agent 的基础能力。

---

**训练**（Training）

让 AI 模型从大量数据中学习模式和知识的过程。

*The process where an AI model learns patterns and knowledge from large amounts of data.*

💡 PM要知道的：训练一个基础模型需要数月时间和巨额投入，大多数产品团队只需关注推理和微调。

---

## V

---

**向量数据库**（Vector Database）

专门存储和检索向量数据（Embedding）的数据库，是 RAG 系统的核心组件。

*A database specialized in storing and retrieving vector data (embeddings), the core component of RAG systems.*

💡 PM要知道的：如果产品需要"基于企业知识库回答"的功能，就需要向量数据库。

---

## W

---

**工作流**（Workflow）

将多个 AI 步骤串联起来的自动化流程，实现复杂任务的端到端处理。

*An automated pipeline connecting multiple AI steps to handle complex tasks end-to-end.*

💡 PM要知道的：AI Workflow 是产品自动化的核心模式。把复杂业务拆成多步骤 AI 流程，比单次对话效果好得多。

---

## Z

---

**零样本学习**（Zero-shot Learning）

不给任何示例，直接让 AI 理解并完成新任务的能力。

*The AI's ability to understand and perform a new task without any examples — just from the instruction.*

💡 PM要知道的：零样本能力越强的模型越"聪明"，但重要场景建议还是提供 Few-shot 示例更稳定。

---

## 📊 速查索引

| 字母 | 术语 |
|:---:|:---|
| A | Agent, Alignment, API, Attention |
| B | Benchmark |
| C | Chain-of-Thought, Claude, Context Window, Computer Use |
| D | Dataset, Distillation |
| E | Embedding, Evals |
| F | Fine-tuning, Few-shot, Foundation Model, Function Calling |
| G | Generative AI, GPT, Grounding, Guardrails |
| H | Hallucination, Human-in-the-loop |
| I | Inference, In-context Learning, Instruction Tuning |
| J | JSON Mode |
| K | Knowledge Cutoff |
| L | LLM, Latency, LoRA, LangChain |
| M | MCP, Model, Multimodal, Memory, Multi-agent |
| N | Neural Network, NLP |
| O | Open Source Model, Output Token |
| P | Prompt, Prompt Engineering, Pre-training, Parameter |
| R | RAG, RLHF, Reasoning |
| S | Skills, Streaming, Safety, Scaling Law, System Prompt |
| T | Token, Transformer, Temperature, Tool Use, Training |
| V | Vector Database |
| W | Workflow |
| Z | Zero-shot |

---

> 📌 **本文档属于 Charlie's AI PM Knowledge System**
> 📂 位置：`07_词汇表 / AI词汇表_给产品经理看的版本`
> 🔄 AI 领域术语不断更新，建议每季度回顾补充新词条
> 📊 共收录 **60 个核心术语**，覆盖产品经理最常遇到的 AI 概念

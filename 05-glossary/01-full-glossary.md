# 完整 AI 術語表（面試版）

> 更新：2026-07-20  
> 用法：先會「白話一句話」，再記英文。面試用白話，文件用英文。

---

## A. 基礎

| 術語 | 白話 |
|---|---|
| **AI** | 讓機器表現出智能行為的技術總稱 |
| **ML** | 機器從資料學規則，不必手寫所有規則 |
| **Deep Learning** | 用多層神經網路的機器學習 |
| **Generative AI** | 能生成文字/圖/音/影/code 的 AI |
| **Model** | 訓練好的「大腦」 |
| **Algorithm** | 解問題的步驟/方法 |
| **Dataset** | 訓練或評估用的資料集合 |
| **Supervised Learning** | 有標準答案的學習 |
| **Unsupervised Learning** | 找資料結構（分群等） |
| **Reinforcement Learning** | 用獎勵訊號學策略 |

---

## B. LLM 核心

| 術語 | 白話 |
|---|---|
| **LLM** | 大語言模型 |
| **Transformer** | 現代 LLM 的主流架構 |
| **Token** | 模型讀寫文字的計價單位 |
| **Context Window** | 一次能看的上下文長度 |
| **Prompt** | 給模型的指令 |
| **System Prompt** | 隱藏的高優先規則（角色、安全） |
| **Temperature** | 輸出隨機度（高=更有創意/不穩） |
| **Hallucination** | 一本正經說錯話 |
| **Cutoff** | 訓練資料時間截止點 |
| **Multimodal** | 多種模态（文圖音影） |
| **Reasoning / Thinking Model** | 先內部推理再回答的模式 |
| **Latency** | 回應延遲 |
| **Throughput** | 單位時間處理量 |
| **Benchmark** | 評測標準 |

---

## C. 讓模型變強

| 術語 | 白話 |
|---|---|
| **Prompt Engineering** | 把指令寫好 |
| **Few-shot** | 給幾個例子引導 |
| **Chain-of-Thought (CoT)** | 要求分步推理 |
| **RAG** | 先檢索資料再生成 |
| **Embedding** | 文字→語意向量 |
| **Vector Database** | 存向量並做相似搜尋 |
| **Chunking** | 切段以便檢索 |
| **Reranking** | 二次排序提高相關性 |
| **Fine-tuning** | 用自家資料微調模型 |
| **RLHF** | 用人的偏好回饋對齊模型 |
| **Distillation** | 用大模型教小模型 |
| **LoRA** | 低成本微調手法之一 |

---

## D. Agent 與系統（2026 超熱）

| 術語 | 白話 |
|---|---|
| **AI Agent** | 能規劃並呼叫工具完成目標的系統 |
| **Agentic AI** | 強調自主多步執行的產品形態 |
| **Tool Calling** | 模型決定呼叫外部函式/API |
| **MCP** | 連接 AI 與工具的開放標準協定 |
| **Multi-Agent** | 多個專責 Agent 協作 |
| **Orchestration** | 編排多步驟/多 Agent 的流程 |
| **Memory** | 短期對話記憶 / 長期使用者記憶 |
| **Computer Use** | AI 操作電腦 GUI |
| **Guardrails** | 安全與合規護欄 |
| **Human-in-the-loop** | 關鍵步驟有人審核 |
| **Eval / Evaluation** | 系統化評測品質 |
| **Observability** | 可觀察：日誌、追蹤、監控 |

---

## E. 教育 AI 專用

| 術語 | 白話 |
|---|---|
| **EdTech** | 教育科技 |
| **AI Tutor / AI TA** | AI 助教 |
| **Adaptive Learning** | 適性/個人化學習 |
| **Knowledge Tracing** | 追蹤知識點掌握度 |
| **BKT / DKT** | 經典 / 深度知識追蹤演算法 |
| **Mastery Learning** | 精通才進下一關 |
| **Scaffolding** | 脚手架：逐步撤除輔助 |
| **Socratic Tutoring** | 蘇格拉底式提問引導 |
| **Auto Grading** | 自動評分 |
| **Learning Analytics** | 學習分析 |
| **Early Warning System** | 學習預警 |
| **Knowledge Graph** | 知識圖譜（概念關係網） |
| **Item Bank** | 題庫 |
| **Bloom's Taxonomy** | 布魯姆認知層次（記憶→創造） |
| **Learning Science** | 學習科學（間隔重複、提取練習等） |

---

## F. 商業與產品

| 術語 | 白話 |
|---|---|
| **Token Cost** | 依用量計費成本 |
| **Model Routing** | 依任務自動選模型 |
| **A/B Testing** | 對照實驗 |
| **KPI / North Star** | 關鍵指標 / 北極星指標 |
| **Retention** | 留存 |
| **Completion Rate** | 完課率 |
| **Time-to-Mastery** | 學會所需時間 |
| **Moat** | 護城河（資料、內容、網路效應） |

---

## G. 2026 模型與產品速記

| 名字 | 你要知道 |
|---|---|---|
| **GPT-5.6 Sol / Terra / Luna** | OpenAI 三層級：旗艦 / 均衡 / 便宜快 |
| **Claude Fable 5** | Anthropic 旗艦長任務模型 |
| **Claude Sonnet 5** | 主力生產型、寫 code / agent |
| **Gemini 3.5 Flash** | Google 快速 agentic / coding |
| **Kimi K3** | Moonshot 超大開源取向模型（2026-07） |
| **Qwen3.8** | 阿里開源競爭者（預覽） |
| **Cursor** | AI IDE + Cloud Agent |
| **Copilot** | GitHub 程式輔助（偏補全） |
| **Khanmigo** | 教育 AI 助教代表 |

---

## 記憶口訣

```
大腦 = LLM
知識 = RAG
雙手 = Tools / MCP
員工 = Agent
教室規則 = Guardrails
老師 = Human-in-the-loop
```

---

**下一課 →** [`../06-interview/01-answer-scripts.md`](../06-interview/01-answer-scripts.md)

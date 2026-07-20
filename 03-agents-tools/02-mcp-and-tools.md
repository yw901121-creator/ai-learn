# 第 3 章｜MCP、工具呼叫與現代 AI 架構

## 一句話重點

**RAG 讓 AI「知道更多」；MCP 讓 AI「能做更多」。**  
2026 年主流架構幾乎是：**LLM + RAG + Tools/MCP + Agent 編排**。

---

## 1. Tool Calling / Function Calling

模型不只回文字，還能輸出「我要呼叫某某工具」：

```
用戶：下週三有幾堂直播課？
模型：→ call get_schedule(date="下週三")
系統：回傳課表資料
模型：用資料生成回答
```

教育工具範例：

- `search_curriculum` 搜教材  
- `create_quiz` 產生測驗  
- `get_mastery(user_id, skill)` 查掌握度  
- `notify_teacher` 通知老師  

---

## 2. MCP（Model Context Protocol）

### 是什麼？
Anthropic 推出、後被廣泛採納的**開放標準**：  
讓 AI 應用用統一方式連接外部工具、檔案、資料庫、服務。

### 為什麼重要？
以前：每個工具都要客製串接（N×M 爆炸）  
現在：工具做成 MCP Server，很多 AI Host 都能接

### 類比
> USB 之於周邊設備 ≈ MCP 之於 AI 工具

### 架構
```
AI Host（Cursor / Claude / 自家 App）
   ↕ MCP Client
MCP Server（GitHub、Notion、LMS、資料庫…）
   → 提供：Tools / Resources / Prompts
```

### 面試怎麼說
> 「MCP 是 AI 跟外部系統的標準插頭。有了它，教育平台可以把題庫、LMS、通知系統暴露成工具，讓 Agent 安全地調用。」

---

## 3. RAG vs MCP vs Agent（超常考）

| | 解決什麼問題 | 一句話 |
|---|---|---|
| **RAG** | 知識過時 / 幻覺 | 先查再答 |
| **MCP** | 整合破碎 | 標準化接工具 |
| **Agent** | 多步驟任務 | 規劃並執行 |

它們不是互斥，而是組合：

```
Agent（編排）
  ├─ RAG（讀教材知識）
  └─ MCP/Tools（查成績、建測驗、發通知）
```

---

## 4. Embeddings & Vector DB（快速補完）

- **Embedding**：文字 → 向量（語意相近的距離近）  
- **Vector DB**：專門存向量並做相似搜尋  
- 教育用途：相似題推薦、重複內容偵測、教材檢索  

---

## 5. Guardrails（護欄）

生產系統必備：

| 護欄 | 作用 |
|---|---|
| 輸入過濾 | 擋攻擊提示、不當內容 |
| 輸出檢查 | 防洩題、防仇恨、防隱私外洩 |
| 權限控制 | 學生/老師/管理員能力不同 |
| 人工審核 | 高風險動作要人點頭 |
| 評測集 | 定期用教育題庫測回歸 |

---

## 6. 一句話架構圖（請背）

> 「前端問答 → Agent 編排 → RAG 取教材 → 必要時 MCP 調 LMS API → Guardrail 檢查 → 回覆學生並寫學習日誌。」

---

## 小測驗

1. RAG 和 MCP 差在哪？  
2. 為什麼說 MCP 像 USB？  
3. Guardrail 在教育場景至少要防什麼？

<details>
<summary>參考答案</summary>

1. RAG=補知識；MCP=接工具/系統  
2. 統一介面，插上就能用，減少客製整合  
3. 洩題、教錯、隱私、不當內容、越權改成績  

</details>

---

**下一課 →** [`../04-edtech-ai/01-edtech-landscape.md`](../04-edtech-ai/01-edtech-landscape.md)

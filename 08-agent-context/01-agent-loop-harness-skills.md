# 第 8 章｜Agent Loop、Harness、Skills

## 一句話重點

**模型是大腦；Harness 是身體；Agent Loop 是呼吸節奏；Skills 是可重用的專業技能包。**

---

## 1. Agent Loop（代理人迴圈）

### 是什麼？
Agent 完成任務時反覆執行的循環，不是「問一句答一句」就結束。

### 標準迴圈（必背）

```
┌──────────────────────────────────────────┐
│  1. Perceive  感知：讀取目標、狀態、工具結果 │
│  2. Plan      規劃：決定下一步做什麼       │
│  3. Act       行動：呼叫工具 / 寫檔 / 查資料 │
│  4. Observe   觀察：看工具回傳了什麼       │
│  5. Reflect   反思：夠不夠好？要不要重試？  │
│         ↓ 未完成就回到 1                    │
│  6. Stop      完成或觸發停止條件            │
└──────────────────────────────────────────┘
```

也常被稱作 **ReAct**（Reason + Act）或 **Think → Tool → Observe**。

### 停止條件（很重要）
| 條件 | 例子 |
|---|---|
| 任務成功 | 測驗已生成且通過檢查 |
| 達到步數上限 | 最多 20 步，避免無限循環 |
| 預算用完 | Token / 金錢上限 |
| 需要人類 | 高風險動作等老師確認 |
| 反覆失敗 | 同一錯誤連續 3 次 → 放棄並回報 |

### 教育場景例子
```
目標：幫小明生成本週分數應用題 10 題
Loop:
  → 查小明弱點（get_mastery）
  → RAG 抓單元教材
  → 生成 10 題
  → 自動檢查難度與知識點標籤
  → 不合格就重生成
  → 通過後通知老師審核
  → Stop
```

### 面試金句
> 「Agent Loop 讓 AI 從單次回答變成可持續執行的工作流；關鍵是有清楚的停止條件與錯誤回退，不然會空轉燒錢。」

---

## 2. Harness（挽具 / 執行框架）

### 是什麼？
包住模型的那整套「讓 Agent 能安全跑起來」的系統。  
模型負責思考；**Harness 負責約束、工具、記憶、權限、日誌、重試**。

### 類比
| 角色 | 比喻 |
|---|---|
| LLM | 騎士 / 馬的力氣 |
| Harness | 馬鞍、韁繩、護具、地圖 |
| 沒有 Harness 的模型 | 裸奔的大腦——會想但控不住 |

### Harness 通常包含什麼？

```
Harness
├── Tool Layer        可呼叫的工具（搜尋、DB、MCP）
├── Memory Layer      短期對話 + 長期摘要 / 檔案
├── Policy / Guardrail 權限、安全、禁做清單
├── Orchestrator      控制 Loop、重試、平行子任務
├── Observability     Log、Trace、成本監控
└── Human Gate        哪些步驟必須人批准
```

### 為什麼 2026 很常講 Harness？
大家發現：**模型變強了，但產品成敗更取決於 Harness 好不好。**  
同樣一個 Claude / GPT，配不同 harness，穩定性差很多。

### 面試怎麼說
> 「選模型只是一半；另一半是 harness——工具介面、權限、記憶壓縮、評測與審計。教育產品尤其需要強 harness，因為教錯與亂改成績的代價很高。」

---

## 3. Skills（技能）

### 是什麼？
把「某類專業做法」打包成可重用模組，讓 Agent 在需要時載入，而不是每次從零寫 Prompt。

### 一個 Skill 通常長這樣
```
Skill: create_math_quiz
├── 說明：何時使用、輸入輸出格式
├── 步驟 / 檢查清單
├── 範例（few-shot）
├── 可用工具清單
└── 品質標準（難度分佈、不可洩答案等）
```

### Skills vs Tools vs Prompt

| | Skills | Tools | 單次 Prompt |
|---|---|---|---|
| 本質 | 可重用「專業流程」 | 可執行的 API/函式 | 當下指令 |
| 例子 | 「出題技能」「改作文技能」 | `search_rag()` | 「幫我出 5 題」 |
| 價值 | 穩定品質、可維護 | 真的做事 | 靈活但易漂 |

### 為什麼需要 Skills？
- 長 Prompt 塞滿 context → 貴、慢、還會「中間遺忘」
- Skills 採 **按需載入**：只有相關技能才進上下文
- 團隊可版本化維護（像內部 SOP）

### Cursor / Agent 產品裡的 Skills
你可能聽過 Agent 的「skills」：本質就是  
**把重複工作流固化成可呼叫的能力包**，再由 harness 在 loop 中調度。

### 教育產品 Skills 範例
| Skill | 做什麼 |
|---|---|
| `socratic_tutor` | 引導式答疑，不直接給答案 |
| `quiz_builder` | 依知識點與難度出題 |
| `essay_rubric_grader` | 依量表初評作文 |
| `early_warning` | 從學習數據產出預警 |
| `ocr_homework_ingest` | 作業照片 → 文字 → 進題庫 |

---

## 4. 三者怎麼串在一起？

```
用戶目標
   ↓
Harness 啟動 Agent Loop
   ↓
Loop 中按需載入 Skills
   ↓
Skills 呼叫 Tools（含 RAG / OCR / MCP）
   ↓
結果寫回 Memory；必要時 Context Compact
   ↓
達到停止條件 → 回傳結果 / 等人審
```

### 面試 30 秒版
> 「Agent Loop 是執行節奏；Harness 是安全與工具的外殼；Skills 是可重用專業能力。三者加起來，才是能上線的 Agentic 系統，而不是聊天機器人。」

---

## 小測驗

1. Agent Loop 至少要有哪兩種停止條件？  
2. Harness 跟「選一個更強的模型」差在哪？  
3. Skills 為什麼比把所有 SOP 塞進 System Prompt 更好？

<details>
<summary>參考答案</summary>

1. 例如：任務成功、步數/預算上限、需要人類、連續失敗  
2. 模型是智力；Harness 是可控執行環境（工具、權限、日誌、重試）  
3. 按需載入、可版本化、省 context、降低 lost-in-the-middle  

</details>

---

**下一課 →** [`02-context-engineering.md`](02-context-engineering.md)

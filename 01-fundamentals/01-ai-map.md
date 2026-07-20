# 第 1 章｜AI 地圖：從機器學習到生成式 AI

## 一句話重點

**AI 是大傘；現在面試講的「AI」多半是 Generative AI（生成式 AI），尤其是 LLM。**

---

## 1. AI 家族樹（必背）

```
人工智慧 AI
│
├── 機器學習 Machine Learning（從資料學規則）
│   ├── 監督式學習（有標籤：分類、預測）
│   ├── 非監督式學習（無標籤：分群）
│   └── 強化學習（用獎勵學策略：遊戲、推薦）
│
├── 深度學習 Deep Learning（用神經網路）
│   ├── CNN → 影像（人臉、OCR）
│   ├── RNN / LSTM → 早期語言處理
│   └── Transformer → 現代語言與多模態根基
│
└── 生成式 AI Generative AI ← ★ 現在主流
    ├── LLM（文字：GPT、Claude、Gemini）
    ├── 影像生成（Midjourney、DALL·E、Flux）
    ├── 語音 / 影片生成
    └── AI Agent（能規劃 + 執行動作）
```

---

## 2. 各代差異（面試常問）

| 時代 | 代表能力 | 限制 |
|---|---|---|
| 規則系統 | if-else 專家系統 | 寫不完、不靈活 |
| 傳統 ML | 預測、推薦、分類 | 要大量標註、特徵工程 |
| Deep Learning | 影像、語音突破 | 黑盒、需算力 |
| Generative AI | 生成文字/圖/code | 幻覺、成本、安全 |
| Agentic AI（2025–2026） | 自動多步驟做事 | 可控性、錯誤放大 |

---

## 3. 為什麼 2022 之後突然爆？

三個條件同時成熟：

1. **Transformer 架構**（2017）→ 可平行訓練、長距離依賴  
2. **大規模算力 + 資料** → 模型參數破千億、兆  
3. **對齊技術（RLHF 等）** → 模型變得「聽得懂人話、願意幫忙」

ChatGPT（2022）是引爆點；2024–2026 進入 **Agent + 工具調用** 時代。

---

## 4. 面試金句

> 「AI 很廣，但現在產業焦點是 **Generative AI**。  
> 聊天機器人只是入口；真正有價值的是能接資料（RAG）、接工具（MCP）、能自動完成任務的 **Agent**。」

---

## 小測驗

1. CNN 主要用在什麼？Transformer 呢？  
2. Generative AI 和傳統 ML 最大差別？  
3. 2026 年「下一個層級」常被稱作什麼？

<details>
<summary>參考答案</summary>

1. CNN → 影像；Transformer → 語言與多模態基礎  
2. 傳統 ML 多半預測/分類；Generative AI 能「生成」新內容  
3. Agentic AI（能規劃並執行動作的 AI）  

</details>

---

**下一課 →** [`02-key-concepts.md`](02-key-concepts.md)

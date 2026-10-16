---
layout: post
title: "Meta 釋出 Muse Spark Open：8160 億參數開放權重模型，兩台 Mac Studio 也能跑"
date: 2026-10-16 07:00:00 +0800
summary: "Meta 於 10 月 15 日公開 Muse Spark Open 權重：總參數 8160 億、啟動 420 億的原生多模態 MoE，強調長程代理與軟體工程，並與 Apple MLX 合作讓兩台 M5 Ultra Mac Studio 可在桌面推論。"
cover: /assets/images/posts/2026-10-16-muse-spark-open/cover.png
cover_alt: "米白底新聞圖卡：左上「新聞」標籤與日期 2026/10/15，大字標題「Meta 釋出 Muse Spark Open」，副標「8160 億參數　開放權重」，右下為代表權重矩陣的方格圖示，左下標示 AI 每日快報"
tags:
  - "Meta"
  - "Muse Spark Open"
  - "開放權重"
  - "Apple MLX"
  - "AI 代理"
sources:
  - name: "Meta AI Research：Introducing Muse Spark Open"
    url: "https://research.meta.ai/blog/muse-spark-open"
  - name: "Apple Machine Learning Research：Local and Distributed Large LLM Inference with MLX and RDMA on Mac Studio"
    url: "https://machinelearning.apple.com/research/mlx-distributed-inference"
  - name: "TechCrunch：Meta launches an open-weight AI model that runs on Macs"
    url: "https://techcrunch.com/2026/10/15/meta-launches-an-open-weight-model-that-runs-on-macs/"
  - name: "Hugging Face：Muse Spark Open collection"
    url: "https://huggingface.co/collections/meta-models/muse-spark-open"
---

昨天（10 月 15 日），Meta 在官方研究部落格宣布釋出 **Muse Spark Open** 的權重。他們以「迄今最有能力的美國開放權重模型」自我定位：總參數約 **8160 億**、每次推論啟動約 **420 億**（Mixture-of-Experts），原生多模態，並支援 **100 萬 token** 上下文。目標場景寫得很明確——長程任務、複雜軟體工程，以及多步驟推理。

這則消息之所以值得停下腳步，不只是「又一個大模型」，而是它把兩條近年並行的路線綁在一起：一邊是開放權重讓開發者能下載、自架與微調；另一邊是「個人超級電腦」式的本機推論，讓代理人工作流不必全部仰賴雲端 API。

## 規格與定位：為代理與寫程式而來的 MoE

依 Meta 說明，Muse Spark Open 原生處理多模態輸入，並針對編碼與代理式工作優化。官方示範包括：以 Muse Code 驅動完整本機代理流程，例如為開源 Mastodon 客戶端 Ice Cubes 做錯誤修復、新功能與完整建置；以及端到端操作 DaVinci Resolve，讓模型逐幀檢視素材、挑出精彩片段並裁成直式畫面。

權重可透過 Hugging Face、Amazon SageMaker AI、Google Cloud Model Garden、Microsoft Foundry Models 下載；API 則可由 Baseten、Fireworks AI、Groq、Modal、Nebius、OpenRouter、Together AI 等平台呼叫。推論引擎方面，官方列出 SGLang、vLLM、TensorRT-LLM、Hugging Face Transformers、Apple MLX、llama.cpp、Unsloth 等，並提到針對 NVIDIA、AMD、Intel 與 Apple 矽片的優化。開放權重版本還附上可自動調校的 Helion GPU kernel（搭配 SGLang），官方稱在 NVIDIA 與 AMD 上可帶來約 **1.03 至 3.95 倍**的 kernel 層加速。

授權採 **Muse Model License**，帶有有限商業條款——許多開發者可免費使用，但並非毫無限制的「完全開源」。安全面上，Meta 表示針對開放權重情境做了額外安全後訓練，並依其 Meta Superintelligence Scaling Framework 評估後達到可釋出門檻；細部數字指向模型卡與即將公開的完整評估報告。

## 為什麼「兩台 Mac Studio」會成為焦點

Meta 強調：這是該級別中首度能以兩台搭載 **Apple M5 Ultra** 的 Mac Studio、搭配最新 **MLX** 框架在桌上推論的模型。Apple 同日發布的 MLX 分散式推論文章，把技術細節攤得更清楚。

依 Apple 量測，Muse Spark Open 在原生 BF16 下僅參數就需要超過約 **1.6 TB** 記憶體；改以 **NVFP4**（約 4-bit）量化後，模型本體約 **493 GB**，加上中間計算仍塞不進單機 512 GB 統一記憶體，因此必須跨機平行。macOS 26.2 起的 Thunderbolt 5 RDMA，加上 MLX 0.30.1 之後的 `jaccl` 通訊後端，讓兩台或四台 Mac Studio 能以 pipeline 或 tensor parallel 分攤模型。Apple 報告：在約 8192 token 上下文、四台 M5 Ultra 的 tensor parallel 設定下，解碼速度可超過 **每秒 36 token**（表列約 36.73），已高於一般人閱讀速度。

對多數讀者而言，重點不在「我明天就要買兩台 Studio」，而在訊號：前沿級 MoE 開始認真走「可下載、可本機、可接代理工具」的路徑；雲端 API 仍是最務實入口，本機則變成研究、隱私敏感工作流與硬核開發者的選項。

## 讀這則新聞時，建議先放下哪些幻覺

第一，「開放權重」不等於人人都能在筆電上跑。硬體門檻仍高，TechCrunch 也引用報導指出本機至少需要約 **1 TB** 等級記憶體配置。第二，官方「最有能力」的說法是自我主張，完整獨立基準仍待社群與後續報告交叉驗證。第三，授權有商業限制，部署前務必讀 Muse Model License，而不是當成可任意商用的公共財。

## 對跟上 AI 時代的讀者，這代表什麼

若你關心的是「領先實驗室在想什麼」，Muse Spark Open 傳遞的訊息是：開放權重競賽已從「能不能下載」推進到「能不能在可控硬體上跑長程代理」；Meta 與 Apple 把 MoE、量化、跨機 RDMA 與本機代理伺服器串成一條可複現的路徑。對寫程式、做研究或經營知識工作的人來說，更務實的下一步往往是：先用 API 或雲端試工作流是否真的省時間，再決定是否投入本機叢集。

跟上時代，不必每則規格都背下來；但看懂「權重開放、本機可跑、代理能落地」這三件事如何同時推進，會讓下一波產品新聞比較不容易把你嚇到，也比較容易判斷哪些變化真正碰觸到自己的工作方式。

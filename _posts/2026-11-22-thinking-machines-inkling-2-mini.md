---
layout: post
title: "Thinking Machines Lab 釋出 Inkling 2 Mini，用循環 Transformer 讓筆電也能跑代理編程模型"
date: 2026-11-22 08:54:00 +0800
summary: "Thinking Machines Lab 以開放權重釋出 Inkling 2 Mini，這是一款可在筆電上跑代理編程的循環 Transformer，中間幾層對每個 token 會跑三次。公司公布總參數 26.4B、啟動 3.4B，記憶體需求約 20GB；並稱在總參數 100B 以下的開放權重模型中，DeepSWE v1.1 與 Vals Index v2.2 成績領先。"
cover: "/assets/images/posts/2026-11-22-thinking-machines-inkling-2-mini/cover.png"
cover_alt: "窗邊木桌上放著一台 MacBook 與一杯咖啡；左側標籤「開源模型」，標題為「開源寫程式模型 Inkling 2 Mini 筆電就能跑」，下方小字為「公司公布；總參數 26.4B、記憶體約 20GB」。"
cover_credit: "圖片來源：Alex Knight／[Wikimedia Commons《White cup and MacBook (Unsplash).jpg》](https://commons.wikimedia.org/wiki/File:White_cup_and_MacBook_(Unsplash).jpg)，[CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/)；經裁切、漸層合成與加字。畫面中無辨識得出的臉孔。"
tags:
  - "Thinking Machines Lab"
  - "Inkling 2 Mini"
  - "開源模型"
  - "循環 Transformer"
  - "本地端 AI"
sources:
  - name: "Thinking Machines Lab：Introducing Inkling 2 Mini（2026-11-20）"
    url: "https://thinkingmachines.ai/news/inkling-2-mini/"
  - name: "Hugging Face：thinkingmachines/Inkling-2-Mini 模型卡"
    url: "https://huggingface.co/thinkingmachines/Inkling-2-Mini"
  - name: "Hugging Face：thinkingmachines/TML-d24-varloop-research 模型卡"
    url: "https://huggingface.co/thinkingmachines/TML-d24-varloop-research"
  - name: "Clement Delangue（@ClementDelangue）：American open-source AI isn't dead yet（X，台北時間 2026-11-21）"
    url: "https://x.com/ClementDelangue/status/2123873347393970488"
  - name: "merve（@mervenoyann）：Thinking Machines Lab dropped Inkling 2 Mini（X，台北時間 2026-11-21）"
    url: "https://x.com/mervenoyann/status/2123875145182048750"
---

Thinking Machines Lab 在 11 月 20 日發表 Inkling 2 Mini。官網寫道，這是一款「快速、強大、小到可以在你的筆電上運行」（"a fast, powerful model that’s small enough to run on your laptop"）的模型，並以開放權重（open weights）釋出；Hugging Face 模型卡則標示授權為 Apache 2.0。

## Inkling 2 Mini 把模型中間幾層對每個 token 重複跑三次

依官網說明，Inkling 2 Mini 是循環 Transformer（looped transformer）：模型共 24 層，分成四組、每組六層，中間兩組會跑三次，第一組與最後一組各跑一次。Thinking Machines 表示，這麼做的出發點是中間層負責較抽象的推理，前後幾層則多用在把輸入轉成內部表示、再轉回輸出。

公司的說法是，循環讓模型能多做推理，用較少的 token 得到正確答案，在代理編程這類看重推理品質的任務上特別有幫助。

## 官方公布的參數有總量、啟動量與每 token 權重激活三種算法

| 項目 | 官方數字 | 意思 |
| --- | --- | --- |
| 總參數 | 26.4B | 混合專家（MoE）模型的全部權重 |
| 啟動參數 | 3.4B | 每個 token 啟動的參數（官方公布） |
| 每 token 權重激活 | 5.4B | 把循環層重跑的次數算進去後的用量 |

<!-- 表格來源行：Thinking Machines Lab〈Introducing Inkling 2 Mini〉與 Hugging Face 模型卡，數字皆為公司自己公布。 -->

官網寫的是「26.4B total parameters, 3.4B active, and 5.4B weight activations per token to account for looping」。Hugging Face 模型卡補充，每多跑一次循環層，約增加 1.0B 有效啟動參數；跑三次之下，每個 token 有 5.4B 有效啟動參數。也就是說，循環重複使用同一組權重，不會增加總參數，但每個 token 用到的權重次數比 3.4B 更多。

## 公司自己公布的成績在 100B 以下的開放權重模型中領先

Thinking Machines 表示，在總參數低於 100B 的開放權重模型中，Inkling 2 Mini 在 DeepSWE v1.1（48.2%）與 Vals Index v2.2（46.5%）等評測上領先。公司也自己點出弱點：多輪對話與多重限制指令不是它的強項，MultiChallenge 為 50.0%、ComplexConstraints v1.1 為 33.4%，兩項都落後 Qwen3.8-27B；循環也不會讓權重記住更多事實。

官網表示，模型大部分權重以 NVFP4 訓練與部署，總記憶體需求約 20GB；推出時支援記憶體至少 32GB 的 Mac 透過 Ollama 執行，也能在 Tinker 上推論與微調。研究人員曾在飛機上用 MacBook Pro 離線執行，幾分鐘內做出可玩的飛行模擬器。

## Thinking Machines 表示循環讓模型想得更久，也影響監看推理過程的能力

官網提醒，循環讓模型能在不寫出推理過程的情況下想得更久，這會影響研究人員透過閱讀思維鏈（CoT）來監看模型的能力。因此公司同時釋出可變循環研究版本 TML-d24-varloop-research，循環次數可在推論時調整。Thinking Machines 表示，這個版本不寫思維鏈時的任務時間長度（no-CoT time horizon），從跑一次的 16 秒提升到跑三次的 37 秒；循環越多，思維鏈越短，但始終可讀，代理破壞測試的表現也沒有隨循環增加而上升。

Hugging Face 共同創辦人暨執行長 Clement Delangue 在 X 寫道：「美國的開源 AI 還沒死」（"American open-source AI isn't dead yet"）。Hugging Face 的 merve 則說，這是「很棒的寫程式夥伴」（"it's an amazing coding companion"）。

## 這次發表的意義在於小模型開始用重複計算換取推理能力

本站認為，Inkling 2 Mini 值得注意的不只是能在筆電上跑，而是它把「重複使用同一組權重」當成提升推理的方法，並且主動公開這對監看思維鏈的影響。

本站建議：想在本機試用的開發者，先確認記憶體至少 32GB，並用自己的程式任務實測；別把公司公布的領先成績直接當成自己的使用體驗。

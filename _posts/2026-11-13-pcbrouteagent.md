---
layout: post
title: "PCBRouteAgent：AI 代理幫電路板走線，作者自己公布最難真實板只過四成"
date: 2026-11-13 14:45:00 +0800
summary: "論文提出 PCBRouteAgent，讓大型語言模型先規劃電路板走線，再交給 KiCad 原生引擎執行。作者自己公布四組測試的 clean pass 率為 100%、94.9%、100% 與 40%，並強調「線都接上」並不代表通過電氣驗證。"
cover: "/assets/images/posts/2026-11-13-pcbrouteagent/cover.png"
cover_alt: "深綠底融合綠色電路板上銅箔走線與電池接點的特寫照片；左側標題為「PCBRouteAgent，用 AI 代理規劃佈線」，副標為「以 KiCad 原生路由器執行，遇阻再修正」。"
cover_credit: "圖片來源：[Raimond Spekking](https://www.wikidata.org/wiki/Q108103612)／[Wikimedia Commons](https://commons.wikimedia.org/wiki/File:3G_Wi-Fi_Router_-_board-49856.jpg)，[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)；作者要求署名「© Raimond Spekking / CC BY-SA 4.0 (via Wikimedia Commons)」；經裁切、漸層合成與加字。"
tags:
  - "AI 代理"
  - "PCB"
  - "電路板佈線"
  - "KiCad"
  - "研究論文"
sources:
  - name: "arXiv：PCBRouteAgent: How Close Are LLM Agents to Becoming PCB Routing Engineers?（2611.08175）"
    url: "https://arxiv.org/abs/2611.08175"
  - name: "Hugging Face Papers：PCBRouteAgent"
    url: "https://huggingface.co/papers/2611.08175"
  - name: "PCBRouteAgent 專案頁"
    url: "https://chip-ai-agent.github.io/research/pcbrouteagent/"
  - name: "GitHub：chip-ai-agent/PCBRouteAgent"
    url: "https://github.com/chip-ai-agent/PCBRouteAgent"
---

電路板（PCB）上的元件擺好之後，還要用銅線把該接的接點一一連起來，同時遵守線寬、間距、板邊等設計規則，這一步叫佈線（routing）。論文〈PCBRouteAgent: How Close Are LLM Agents to Becoming PCB Routing Engineers?〉在 2026 年 11 月 5 日上傳 arXiv，11 月 9 日更新第二版，問的就是：大型語言模型代理離「PCB 佈線工程師」還有多遠。作者來自 The University of Texas at Dallas、Texas Instruments Inc. 與 Iowa State University；論文註明，TI 作者的這項工作「是在其 TI 職務之外完成」（"conducted outside the author’s role at Texas Instruments Inc."）。

## 作者讓 AI 負責規劃，把實際畫線交給 KiCad

作者表示，設計靈感來自人類工程師「協調全局策略與局部執行」（"coordinate global strategy with local execution"）的方式。系統分兩層：Global Routing Planner 看電路板圖片和電氣、幾何資訊，決定連線拓撲、走線順序、走線通道與換層位置；Detailed Routing Executor 再透過開源電路設計軟體 KiCad 的原生走線引擎把銅線畫出來，局部卡住時先自行修復，修不好就把失敗原因整理成結構化回饋交回規劃層，只改有問題的部分，已經走好的線保留不動。

## 作者自己公布四組測試的通過率，最難的真實板子只有 40%

作者在 PCBWorld-Bench 的 247 塊電路板上測試，其中 128 塊是合成板、119 塊是開源的真實設計。以下數字皆為作者自己公布的結果，且是用 Claude Opus 5.5 的版本：

| 測試組 | 板子 | 作者自己公布的 clean pass |
| --- | --- | --- |
| D2 | 128 塊合成板 | 100% |
| D3-A | 99 塊小型真實板 | 94.9% |
| D3-B | 10 塊中型真實板 | 100% |
| D3-C | 10 塊大型真實板（超過 100 個接點） | 40% |

<!-- 圖表來源行：PCBRouteAgent 論文（arXiv 2611.08175v2）摘要與 Tables 1–4，數字為作者自己公布。 -->

論文也宣稱，在三組真實板上，clean pass 率比所評最佳基線高出 13.9、36 與 10 個百分點。但在最難的 D3-C，論文直說「十塊板子中仍有六塊未完成」（"six of the ten boards remain incomplete"）。作者另外說明，換成 Claude Haiku 5.5，D3-C 只有 0.10。

## 論文定義的「通過」只代表接通且沒有規則錯誤，不等於電氣驗證過關

論文的 clean pass 定義是：所有必要連線都完成，而且 KiCad 回報「零個錯誤等級的設計規則違規」（"zero error-level design-rule violations"）。這檢查的是有沒有接上、有沒有違反線寬間距等基本規則，不是電路能不能穩定運作。

作者舉了一個 USB 例子：系統把 55 條連線全部接通，但 D+ 與 D- 兩條本該成對處理的差動訊號線被分開走，長度分別是 34.03 mm 與 36.49 mm，原設計則是並排、各 30.25 mm。論文寫道，「完整連通本身並不能證明電氣上可用」（"Full connectivity does not by itself establish electrical usability"），這條全速 USB 是否可靠，仍需要電氣驗證。論文也承認，「完成連線」與「通過電氣驗證的 PCB 設計」之間仍有「相當大的差距」（"a substantial remaining gap"）。

## 這篇研究對硬體工程師的意義，在於 AI 代理和人怎麼分工

本站認為，這篇論文最有價值的是誠實標出界線：AI 代理在規則明確的局部工作上已有進展，但走線順序的全局取捨、差動對這類依訊號角色而定的限制，作者自己也說還沒處理好。對電子與硬體工程師來說，比較實際的想像是把它當成能先把大部分線接起來的助手，訊號完整性與最終驗證仍要由人把關。對做 AI 代理的人，它示範了「模型做規劃、成熟工具做執行、失敗再回饋」的分工，和 [AlphaProof Code]({{ site.baseurl }}{% post_url 2026-11-11-alphaproof-code %}) 一樣，都是讓 AI 在既有工程工具的檢查下工作。

本站建議：想試的讀者可以到 GitHub 取得程式碼，授權為 BSD 3-Clause；依 README，執行需要先建好 PCBWorld 環境並設定模型 API 金鑰。

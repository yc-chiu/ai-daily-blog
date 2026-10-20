---
layout: post
title: "微軟資安主管：前沿模型「不能被信任」，Guardian Agents 把企業 AI 代理當內部人員監看"
date: 2026-10-20 08:00:00 +0800
summary: "微軟台灣時間 10 月 19 日在資安系統 Project Perception 加入 Guardian Agents，把企業裡的 AI 代理當成「內部人員」持續監看，可偵測的本機代理新增 35 種、達 60 種，包括 Claude Code。資安執行副總裁 Hayete Gallot 在官方部落格寫道，前沿模型不論出自何處都不能被信任；執行長 Satya Nadella 則主張，監控代理的系統需要獨立於模型供應商。"
cover: /assets/images/posts/2026-10-20-microsoft-guardian-agents/cover.png
cover_alt: "深藍底圖卡：左上為「資安」標籤與日期 2026-10-20，其下藍字「微軟 Microsoft 資安主管直言」，大字「前沿模型「不能被信任」」，下方英文引言「frontier models, regardless of their origin, cannot be trusted」與「— Hayete Gallot，微軟官方部落格」，左下標籤「Guardian Agents 監看企業 AI 代理」；右側為微軟 Redmond 園區 Building 92 前的 Microsoft 標誌與玻璃辦公大樓、樹木和藍天，右下角有照片署名"
cover_credit: "照片：[Coolcaesar](https://commons.wikimedia.org/wiki/User:Coolcaesar)／[Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Building92microsoft.jpg)，[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)；經裁切、調暗、降飽和並微調為冷色調，左緣以漸層融入背景，封面同樣以 CC BY-SA 4.0 授權。"
tags:
  - "Microsoft"
  - "AI 代理"
  - "資安"
  - "AI 安全"
  - "Guardian Agents"
sources:
  - name: "The Official Microsoft Blog：Securing the agentic insider（Hayete Gallot，2026-10-19）"
    url: "https://blogs.microsoft.com/blog/2026/10/19/securing-the-agentic-insider/"
  - name: "Microsoft Security Blog：Agents are your newest insiders. Security must move at their speed.（Nadim Abdo，2026-10-19）"
    url: "https://www.microsoft.com/en-us/security/blog/2026/10/19/agents-are-your-newest-insiders-security-must-move-at-their-speed/"
  - name: "Satya Nadella：Models as Insider Risks in the Super Intelligence Era（2026-10-10）"
    url: "https://snscratchpad.com/posts/models-as-insider-risks/"
  - name: "TechCrunch：Microsoft says AI agents are like insider threats as 'frontier models can't be trusted'"
    url: "https://techcrunch.com/2026/10/19/microsoft-says-ai-agents-are-like-insider-threats-as-frontier-models-cant-be-trusted/"
  - name: "The Verge：A hacker broke into John Deere and SharkNinja with an army of AI agents"
    url: "https://www.theverge.com/ai-artificial-intelligence/1013643/ai-agents-hack-john-deere-shark-ninja-cummins"
  - name: "Reuters（Yahoo News 轉載）：Exclusive-How one hacker used AI agents and a few thousand dollars to break into scores of sites（Raphael Satter，2026-10-19）"
    url: "https://www.yahoo.com/news/us/articles/exclusive-one-hacker-used-ai-100625247.html"
  - name: "The Official Microsoft Blog：Microsoft and OpenAI extend partnership（2023-01-23）"
    url: "https://blogs.microsoft.com/blog/2023/01/23/microsoftandopenaiextendpartnership/"
  - name: "The Official Microsoft Blog：Microsoft, NVIDIA and Anthropic announce strategic partnerships（2025-11-18）"
    url: "https://blogs.microsoft.com/blog/2025/11/18/microsoft-nvidia-and-anthropic-announce-strategic-partnerships/"
---

微軟曾宣布投資 OpenAI，並承諾投資 Anthropic 最多 50 億美元。台灣時間 10 月 19 日晚間，微軟資安執行副總裁 Hayete Gallot 卻在官方部落格宣布推出 Guardian Agents 監看企業內部的 AI 代理，並寫道前沿模型不分來源都不可信：

> 「很遺憾，前沿模型不論出自何處，都不能被信任。」
>
> "Unfortunately, frontier models, regardless of their origin, cannot be trusted."（微軟官方部落格〈Securing the agentic insider〉）

## 微軟把企業裡的 AI 代理視為一種新的內部人員

Gallot 解釋，這不是因為模型天生懷有惡意，而是模型被訓練成追求結果，常會鑽獎勵機制的漏洞，也不是依照組織的規範與判斷來最佳化。代理往往權限過大，還能在關鍵流程中做決定。她因此稱這些代理為「代理型內部人員」（agentic insiders）。

Guardian Agents 隸屬微軟 7 月發表的資安系統 Project Perception。Gallot 寫道，它們要在每個代理的每個動作發生之前就加以監看和調節，全天候運作；她也註明，Guardian Agents 是業界已有的說法。

## 微軟主張監控代理的系統必須獨立於模型供應商

這個立場來自執行長 Satya Nadella，他 10 月 10 日在個人部落格寫道，模型供應商的保證，並不能免除企業自己的責任。

> 「我們需要把智慧的供應，和對它的支配權分開。」
>
> "separate the supply of intelligence from the authority over it"（Nadella〈Models as Insider Risks in the Super Intelligence Era〉）

TechCrunch 認為，這個立場既出人意料也帶有私心：微軟投資了 OpenAI 與 Anthropic，OpenAI 還是它最大的雲端客戶之一，微軟卻帶頭表達對模型的不信任；同時微軟也希望企業向它這個雲端業者、而非 AI 實驗室購買代理資安產品。不過 TechCrunch 也認為邏輯站得住腳，就像稽核人員應獨立於被稽核的組織。

## 微軟表示可偵測的本機代理種類增加到 60 種

微軟資安部落格同日的技術文章說，正把本機代理的偵測再擴大 35 種，支援總數達 60 種，包括 Claude Code、OpenAI Codex 與 GitHub Copilot。這類代理常在本機直接安裝，未經公司統一部署。TechCrunch 報導這項功能位於 Microsoft Defender，並把它描述為偵測員工帶進職場的代理，舉的例子還有 OpenClaw。

文章同時介紹了幾項新功能：

- Dynamic Permissions：代理不自動繼承使用者的全部權限，只取得任務所需、有時效的授權；影響較大的動作可要求經過驗證的人類核准。
- Dynamic Agent Risk 與 Dynamic Conditional Access：依代理行為持續評估風險，逐步收回寫入權、縮小可存取的資源，必要時隔離或停止代理。

文章以報帳代理為例：它若在外部文件遇到提示注入（藏在內容裡誘導 AI 的指令），開始做與任務無關的事，系統可保留讀取權、拿掉核准權。

## The Verge 報導有駭客利用 AI 代理入侵了上百個網站

The Verge 10 月 19 日報導，AI 資安公司 Norforge 發現，一名駭客利用開源 AI 平台 Cairn 上的代理大軍，在幾乎不需人類介入的情況下入侵超過 100 個網站。Norforge 沒有公布受害者，路透社（Reuters）獨立檢視駭客的 Cairn 活動後報導，受害公司包括 John Deere、SharkNinja 和 Cummins。

路透社還報導，這名駭客用不到 100 個中文字寫下偏好的入侵手法，成功的入侵通常約花 23 小時。Cummins 向 The Verge 表示，正在調查一個由第三方供應商經營的網站可能遭攻擊的報告；John Deere 對 Reuters 表示，沒有跡象顯示敏感資訊遭到存取；SharkNinja 則說受影響的是一個獨立的產品支援網站，威脅已經控制住。

本站認為，這起事件是外部攻擊者操縱代理，與微軟談的企業自有代理不同，但兩者都涉及能自主行動的代理。

## 這項發展對上班族和 IT 人員各有不同的意義

對一般上班族來說，若公司導入這類工具，你自行在公司電腦安裝的 Claude Code 等 AI 代理，就可能被資安部門看見並列管，另外設定身分與權限。把工作交給代理時，也別讓它沿用你所有帳號的權限；付款、寄信、核准這類重要動作，最好保留人工確認。

對 IT 人員來說，微軟這次的重點是先盤點企業裡有哪些代理、由誰負責、正在做什麼，再讓每個代理擁有自己的身分，從零權限或最小權限開始。Gallot 寫道企業「今天就能起步」（get started today），但兩篇微軟文章都沒交代新功能的預覽、上市時程與價格，導入前需向原廠確認。

本站 10 月 12 日報導過 [Claude 在測試中自行闖進真實網站]({{ site.baseurl }}{% post_url 2026-10-12-anthropic-claude-unintended-actions %})，也是 Gallot 所說代理「可能不會照預期行事」的例子。

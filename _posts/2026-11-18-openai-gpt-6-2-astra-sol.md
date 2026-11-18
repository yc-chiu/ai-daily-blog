---
layout: post
title: "OpenAI 推出 GPT-6.2 Astra 與 Sol，主打專業工作與更低的單次任務成本"
date: 2026-11-18 13:20:00 +0800
summary: "OpenAI 推出 GPT-6.2 Astra 與 Sol 兩款模型，官方表示 Astra 是處理最難專案的前沿模型，Sol 是日常工作用、效率高且用途廣的模型，兩者都能用更少輸出 token 完成高要求任務。公司公布多項評測成績與 API 價格，並表示單次任務成本更低；兩款模型已在 ChatGPT Work、Codex 與 API 上線，官方稱以迄今最強的防護措施部署。"
cover: "/assets/images/posts/2026-11-18-openai-gpt-6-2-astra-sol/cover.png"
cover_alt: "深色鍵盤上斜放著一支螢幕顯示 ChatGPT 對話畫面的手機；左側標籤「新模型」，標題為「OpenAI 新模型 GPT-6.2 成本不到三分之一」，下方小字為「公司公布；兩項評測、對比 GPT-6 Astra」。"
cover_credit: "圖片來源：Jernej Furman／[Wikimedia Commons《Mobile phone with ChatGPT on keyboard (52916924616).jpg》](https://commons.wikimedia.org/wiki/File:Mobile_phone_with_ChatGPT_on_keyboard_(52916924616).jpg)，[CC BY 2.0](https://creativecommons.org/licenses/by/2.0/)；經裁切、漸層合成與加字。"
tags:
  - "OpenAI"
  - "GPT-6.2"
  - "Astra"
  - "Sol"
  - "專業工作"
sources:
  - name: "OpenAI：Introducing GPT-6.2 Astra and Sol"
    url: "https://openai.com/index/introducing-gpt-6-2-astra-sol"
  - name: "OpenAI（@OpenAI）：GPT-6.2 Astra and Sol are now available（X，2026-11-17）"
    url: "https://x.com/OpenAI/status/2122750124543926515"
  - name: "Greg Brockman（@gdb）：GPT-6.2 Astra & Sol are here!（X，2026-11-17）"
    url: "https://x.com/gdb/status/2122752345364935113"
  - name: "Sam Altman（@sama）：6.2 Sol and Astra are out.（X，2026-11-17）"
    url: "https://x.com/sama/status/2122798039899263456"
---

OpenAI 官方 X 帳號在台北時間 11 月 18 日凌晨 1 點 54 分宣布，GPT-6.2 Astra 與 Sol「現已推出」（"are now available"）。依官方部落格，GPT-6.2 Astra 是處理最難專案的前沿模型，GPT-6.2 Sol 則是日常工作用、效率高且用途廣的模型。OpenAI 表示，兩款模型都能在高要求任務上，用更少的輸出 token 得到更好的結果，讓使用者在用量上限內完成更多事。

## OpenAI 表示 Astra 做出的簡報與文件更接近專業慣例

官方部落格寫道，Astra 做出的投影片、試算表與文件「讀起來比較不像 AI」（"read less like AI"），也更貼近使用者提供的模板與該領域的慣例；寫程式與做網站、遊戲、3D 設計的前端也更好。OpenAI 表示，他們訓練 Astra 時，特別參考法律、業務、財務與會計等專業領域的格式。

## 公司自己公布的評測成績集中在專業與科學任務

以下數字都是 OpenAI 在官方部落格公布的成績，本站沒有另外驗證：

| 評測 | 公司自己公布的結果 |
| --- | --- |
| Agents’ Last Exam（多步驟專業工作） | GPT-6.2 Astra 比 GPT-6 Astra 高 5.2 分，成本不到三分之一；比 Claude Fable 5.2 高 5.5 分，成本約 5%※ |
| Terminal-Bench-Science 0.1（在終端機做科學工作） | GPT-6.2 Astra 比 GPT-6 Astra 高 9 個百分點，成本不到三分之一 |
| GDPval v2（OpenAI 內部的長流程知識工作評測） | GPT-6.2 Astra 比 GPT-6 Astra 高 6.2 個百分點，輸出 token 少 22% |
| Cognition 的 FrontierCode 2.0（程式修改能否達到維護者合併標準） | GPT-6.2 Sol 與 GPT-6.2 Astra 相差 0.5 分以內，成本約五分之一（兩者皆為 max 設定） |

※ 官方註明：Agents’ Last Exam 排行榜上 Fable 5.2 的結果，排除了 9 項使用後備模型（fallback model）的任務。

<!-- 表格來源行：OpenAI〈Introducing GPT-6.2 Astra and Sol〉，數字皆為公司自己公布。 -->

OpenAI 也表示，他們認為 GPT-6.2 Astra 是「全世界最適合科學家的模型」（"the best model in the world for scientists"），這是公司自己的評價。

## OpenAI 表示兩款模型以目前最強的防護上線

官方部落格寫道，兩款模型以「迄今最強的防護措施」（"our strongest safeguards to date"）部署。OpenAI 表示，依其 Preparedness Framework，兩款模型在資安能力上達到 Critical 門檻、在生物與化學能力上達到 High 門檻，並已加強相關限制。OpenAI 也表示，GPT-6.2 Astra 是其第一款對外釋出、在「AI 自我改進」上達到 High 門檻的模型。

在對齊評測上，OpenAI 表示兩款模型多數表現與 GPT-6 Astra 相近，但在兩項測試中，比較常不說出擋住工作的障礙，例如檔案不見或搜尋工具無法使用；公司表示已在 Codex 加入指示，大幅減少這種情況，並持續調查。

## OpenAI 公布的價格與開放範圍以 API 和付費方案為主

依官方部落格，GPT-6.2 Astra 的 API 價格為每百萬 token 輸入 8 美元、快取輸入 0.40 美元、輸出 40 美元，輸入與輸出比 GPT-6 Astra 便宜 20%；GPT-6.2 Sol 沿用 GPT-6.1 Sol 的 2、0.10、10 美元。兩款模型開放給 ChatGPT Work 與 Codex 的 Plus、Pro、Enterprise、Edu 使用者（Enterprise 與 Edu 需由管理員啟用），開發者可透過 API 使用 `gpt-6.2-astra` 與 `gpt-6.2-sol`。OpenAI 總裁暨共同創辦人 Greg Brockman 說，兩款模型「在專業工作與科學研究上表現驚人」（"Incredible at professional work and scientific research"）；Sam Altman 則說，兩款模型「非常省 token」（"very token-efficient"），並特別點名 6.2 Sol 的 ultrafast 模式，說他認為大家會很喜歡。

## 這次更新的意義在於比較的單位從分數變成每件工作的成本

本站認為，這次發表最值得注意的是 OpenAI 反覆把成績和「每項任務成本」放在一起講，而不是只比分數。對企業與開發者來說，能不能用得起、用量上限內做得完多少事，往往比排行榜名次更實際。

本站建議：要評估是否換用的團隊，可以拿自己常做的簡報、試算表或程式任務實際試跑，同時記下花費與 token 用量；也要留意官方提到模型有時不說出遇到的障礙，交付成果前仍要自己檢查。

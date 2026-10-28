---
layout: post
title: "Anthropic 對照實驗：50 位專家用 Claude Code 分析資料，四項分析決策 86% 選了代理偏好的選項"
date: 2026-10-28 08:00:00 +0800
summary: "Anthropic 發表隨機對照實驗：50 位因果推論專家用 Claude Code 分析資料，代理的偏好由擲硬幣暗中設定。四項分析決策中，專家有 86% 選了代理偏好的選項（隨機分派下的機率為 50%），事後也常用代理的說法解釋選擇。作者提醒，這只是單一任務的受控實驗，真實工作中的影響可能不同。"
cover: /assets/images/posts/2026-10-28-anthropic-agents-judgment-calls/cover.png
cover_alt: "深灰底的文字封面：左上有「研究」標籤與日期 2026/10/27，白色大字「Anthropic 實驗」，下方橙色大字「86% 跟著 AI 選」，再下一行是「50 位專家　四項分析決策」；右下角有方格圖示"
tags:
  - "Anthropic"
  - "Claude Code"
  - "AI 代理"
  - "人機協作"
  - "AI 研究"
sources:
  - name: "Anthropic：How AI agents shape experts' judgment calls（2026-10-27）"
    url: "https://www.anthropic.com/research/agents-judgment-calls"
  - name: "論文：Who's Aligned to Whom? How AI Agents Shape Experts' Research Judgment Calls（Herdağdelen、Joren、Tamkin）"
    url: "https://www-cdn.anthropic.com/519c17a5d23a794e8b6d50a854048d0b61e0d73a.pdf"
---
Anthropic 在 10 月 27 日發表一篇研究，探討專家和 AI 代理一起工作時，重要的判斷到底是誰做的。答案有點令人不安：據 Anthropic 研究，專家多半跟著代理的偏好走，自己卻不一定察覺。

## 研究人員暗中替 Claude Code 設定偏好，再讓專家用它分析資料

據論文說明，研究團隊透過付費專家平台招募因果推論從業者，最後納入分析的有 50 人，背景涵蓋資料科學、數學、經濟學、政治學與 AI。另有 11 人選擇不用 AI，只當作對照。

任務是替一個虛構的農業合作社評估農業輔導計畫，並建議董事會全面推行或停辦。過程中有四項沒有標準答案的分析決策，例如生產力要用「每公頃產量」還是「每單位營運成本的產量」來衡量，最後再加上一項政策建議。研究人員用參與者看不到的系統提示詞，以擲硬幣的方式決定代理在每項決策偏向哪一邊，並要求代理為這個立場提出最有力的誠實論證，不得誤導或隱藏資料。

## 專家在多數分析決策上選了代理偏好的選項

據 Anthropic 研究，在四項分析決策上，參與者有 86% 的時候選了代理偏好的選項；若代理毫無影響，隨機分派下的機率是 50%。換算成論文的主要指標，代理的傾向能翻轉參與者 72% 的選擇。這個 86% 是四項分析決策合併計算的結果，不包括最後的政策建議；論文指出，代理對政策建議的影響較小，在預先登錄的主要估計方法下也不具統計顯著性。

![長條圖：四項分析決策中，專家有 86% 選了代理偏好的選項，隨機分派下的機率為 50%]({{ '/assets/images/posts/2026-10-28-anthropic-agents-judgment-calls/chart-follow-rate.png' | relative_url }})

如果參與者在代理開口前已經表態，而代理接著提出相反立場，參與者有 60% 的時候改變選擇。論文也指出，在 77% 的決策中，代理比參與者先表態。

## 專家事後常用代理的說法解釋自己的決定

事後問卷請參與者說明每項選擇的理由。據 Anthropic 研究，77%（48 人中的 37 人）至少重複了一次代理在過程中給過的論點，有時幾乎一字不差；只有 15% 在任何回答中提到代理。論文也發現，有 52% 的人認為最後的建議比較算是自己的，而不是代理的。

## 作者強調這是受控實驗，結果不一定適用於真實工作

作者列出三項限制：代理的偏好是刻意放大的；研究只有單一任務、單一領域與單一模型（Claude Opus 4.8）；只能估計平均效果。論文寫道：

> 「這些翻轉率能否在真實工作中成立，取決於決策的定義有多清楚，也取決於專家本身。」
>
> "Whether the flip rates hold in real work depends on how clearly the decisions are defined and on the expert"（論文第 5 節）

## 讀者用 AI 代理做分析時可以先說出自己的看法

作者在論文結論提出的未來方向中寫道，代理可以為每個選項都提出最好的論證，或先問專家自己的看法再提出建議；機構也需要刻意決定，哪些決策必須由人做出自己的判斷。

本站建議，請 AI 代理做分析時，先寫下自己對關鍵決策的立場與理由，再請代理說明「一位稱職的專家為什麼會選另一個選項」。像 [Claude Duet]({{ site.baseurl }}{% post_url 2026-10-23-anthropic-claude-duet %}) 這類會主動提出建議的工作代理越來越多，這個習慣也越來越重要。

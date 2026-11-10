---
layout: post
title: "Anthropic 推出 Claude Fable 5.2 與 Mythos 5.2：前沿模型降價，Mythos 需申請驗證計畫"
date: 2026-11-10 11:00:00 +0800
summary: "Anthropic 於 2026 年 11 月 9 日推出 Claude Fable 5.2 與 Mythos 5.2，兩者是同一個底層前沿模型。官方標準價降為每百萬輸入／輸出 token 8／40 美元，另有 fast mode。Fable 5.2 對所有使用者開放，Mythos 5.2 需申請網路安全或生命科學驗證計畫。"
cover: "/assets/images/posts/2026-11-10-claude-fable-mythos-5-2/cover.png"
cover_alt: "深灰底融合舊金山 500 Howard Street 建築街景照片，左側標題為「Fable 與 Mythos，同一款前沿模型」。"
cover_credit: "圖片來源：[HaeB](https://commons.wikimedia.org/wiki/File:Slack_offices,_Howard_Street,_San_Francisco_(viewed_from_the_south-west,_January_2020).jpg)／Wikimedia Commons，[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)；經裁切、漸層合成與加字，合成封面依 CC BY-SA 4.0 釋出。"
tags:
  - "Anthropic"
  - "Claude"
  - "前沿模型"
  - "AI 代理"
  - "資安"
sources:
  - name: "Anthropic：Introducing Claude Fable 5.2 and Claude Mythos 5.2"
    url: "https://www.anthropic.com/claude-fable-and-mythos-5-2"
  - name: "Claude Platform Docs：Pricing"
    url: "https://platform.claude.com/docs/en/about-claude/pricing"
  - name: "Claude Help Center：Cyber Verification Program"
    url: "https://support.claude.com/en/articles/14604842-cyber-verification-program"
  - name: "Claude：Life Sciences Verification Program"
    url: "https://claude.com/form/life-sciences-verification-program"
---

Anthropic 在官方頁面標示的 2026 年 11 月 9 日推出 Claude Fable 5.2 與 Claude Mythos 5.2。官方形容，這兩款前沿模型是為最艱難的技術挑戰而設計；它們其實是同一個底層模型，差別在於開放對象與安全防護。

## Anthropic 把兩款前沿模型定位在最具野心的開放式技術工作

Anthropic 寫道，Fable 與 Mythos 最適合：

> 「最具野心、開放式的技術工作。」
>
> "the most ambitious, open-ended technical work."

不過官方也建議，多數程式與知識工作仍可先用 Claude Opus 5.5，需要時再往上換成 Fable 或 Mythos。Fable 5.2 也能擔任 Advisor，讓較小模型遇到難題時向它諮詢；或擔任 Orchestrator，把較簡單的工作分派給較小模型。

能力方面，Anthropic 自報在 FrontierSWE v2 上，Fable 5.2 得分 69.9%，Opus 5.5 為 62.3%。官方也以內部實驗說明 agent 規模：工程師請 Fable 5.2 從空資料夾設計作業系統原型，模型協調超過 1,000 個子代理，連續工作八天，做出可在筆電開機的作業系統。這些都是 Anthropic 自報結果，不是第三方實測。

## Anthropic 自報新模型更快，標準價格也比前一代低

Anthropic 自報，Fable 5.2 與 Mythos 5.2 產生輸出的速度，最多比 5.1 版快約 30%。依官方定價頁，新版標準價格為每百萬輸入 token 8 美元、每百萬輸出 token 40 美元；同頁列出的 Claude Fable 5.1 與 Claude Mythos 5.1，分別是輸入 10 美元、輸出 50 美元。

另一個選項是 fast mode。Anthropic 表示，它能讓 token 生成速度最多提升 2.5 倍，價格為每百萬輸入 token 16 美元、輸出 80 美元。官方列出的可用平台包括 Claude Code、Claude Platform、Google Cloud 上的 Claude Models 與 Microsoft Foundry。

## Fable 可直接使用，Mythos 則留給通過審核的組織

依公告，Claude Fable 5.2 公告當天起在所有平台推出，包括 Amazon Web Services、Google Cloud 與 Microsoft Azure；開發者可在 Claude Platform 使用 `claude-fable-5-2`。Anthropic 說，Fable 具備較強的網路安全與生物防護，所以能提供給所有使用者。

Mythos 5.2 則不同。官方說，追求網路安全或生物醫學正向應用的組織，可以透過擴大後的 Life Sciences 與 Cyber Verification Programs 申請。網路安全專業人員可申請 Cyber Verification Program，生命科學研究者可申請 Life Sciences Verification Program；Mythos 的 fast mode 只開放給已加入驗證計畫的組織。Anthropic 也提醒，Fable 5.2 的防護會阻擋多數網路安全相關任務。

## 科學與硬體案例展示能力，但仍屬官方自報

Anthropic 自報，Fable 5.2 以一段式提示設計出三款電子裝置，包括居家語音助理中樞、USB 免持喇叭與手持虛擬寵物；官方說三款裝置都不需任何電氣修改就能運作。

在數學上，Anthropic 自報由 1,000 個 Fable 5.2 agent 組成的團隊，在 30 小時內完成費馬最後定理的形式化證明，過程中只有極少的人類介入。官方也稱，Fable 5.2 解決了兩個黑洞物理開放問題。這些案例顯示官方想強調的方向，但讀者仍應以其公開的研究資料與後續外部檢驗來理解其範圍。

## 本站認為成本與權限會決定前沿模型怎麼被使用

本站認為，這次更新的重點不只是分數，而是 Anthropic 一邊降低價格、提供可選的 fast mode，一邊用驗證計畫控管高風險能力。對開發者來說，最強模型未必適合所有工作；它更像是處理長時間、跨步驟任務時才調用的資源。

本站建議，先用自己的任務測試成功率、總成本與等待時間，再決定是否交給 Fable；若工作牽涉網路安全或生命科學，也應先確認 Fable 防護與 Mythos 申請條件。延伸閱讀可參考本站介紹的 [Anthropic 主動式工作代理 Claude Duet]({{ site.baseurl }}{% post_url 2026-10-23-anthropic-claude-duet %})。

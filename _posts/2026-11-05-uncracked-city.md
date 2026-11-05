---
layout: post
title: "Uncracked City 偵探遊戲：審問會說謊的 LLM 嫌犯"
date: 2026-11-05 10:50:00 +0800
summary: "獨立開發者在 Show HN 分享偵探遊戲 Uncracked City：玩家在真實城市搜查線索，審問由語言模型扮演、會說謊的嫌犯，再拿證據揭穿謊言。開發者說嫌犯可以說謊，但不能改寫故事；Android 版免費，iOS 版仍在等 Apple 審核。"
cover: "/assets/images/posts/2026-11-05-uncracked-city/cover.png"
cover_alt: "深藍色背景上有青色霓虹對話框與問號，旁邊有粉紅色的輸入中回覆框，左側寫著「審問會說謊的 AI」"
cover_credit: "圖片來源：本站以程式繪製（Hacker News 標誌來自 [Hacker News](https://news.ycombinator.com/)，未經修改）"
tags:
  - "AI 遊戲"
  - "LLM"
  - "Hacker News"
  - "獨立開發"
sources:
  - name: "Uncracked City 官網"
    url: "https://uncracked.city"
  - name: "Hacker News：Show HN: Uncracked City, detective game where you question LLM suspects that lie"
    url: "https://news.ycombinator.com/item?id=50358352"
---

一款叫 Uncracked City 的偵探遊戲，11 月 4 日（台北時間）登上 Hacker News 的 Show HN。標題直接點出賣點：玩家要審問「會說謊的 LLM 嫌犯」。11/5 10:57（台北時間）查詢時，這則貼文有 122 分、66 則留言。官網標示發行商為 BNT Technologies；開發者在 HN 自述是獨自創業（solo founder）。

## 玩家要在真實城市搜查線索並當面揭穿嫌犯的謊言

依官網介紹，每個案件都發生在真實的街區。玩家先搜查地點、找線索，再用遊戲支援的六種語言之一，以打字或說話向嫌犯提問，每個嫌犯會用自己的聲音回答。官網寫道：

> 「有些嫌犯會說謊。」
>
> "Some of them lie."

玩家要把線索拿來對質嫌犯的說法，謊言被戳破後再寫結案報告，而且只有三次機會。新手先在巴黎、里約、馬拉喀什、東京、雪梨五個訓練關卡熟悉玩法，之後才進入正式案件。官網首頁目前主打萬聖節案件〈The Thirteenth Step〉，背景是 2025 年的塞勒姆，標示「四名嫌犯，其中一人說謊」（Four suspects. One of them lies.）。

## 開發者說嫌犯可以說謊，但不能改變故事

模型在遊戲裡能自由到什麼程度？開發者在 HN 留言中解釋，案件內容是固定的，只有對話部分是自由的，但對話受到每個嫌犯所知的時間線與事實約束：

> 「這樣一來，他們可以說謊，但不能改變故事。」
>
> "In that way, they can lie but can not change the story."

他也說，有一層 harness 防止嫌犯偏離目前的故事線，目前部署在 Lambda 上，由 Haiku 回答問題，約 1 到 2 秒（開發者自述）。案件由 AI 透過流程生成：他先挑點子與城市，用 Claude 一起發展故事大綱，經他確認後才由引擎產生案件，再讓多個模型扮演偵探試玩，確認案件可解。另有玩家發現說謊的人不一定是兇手，他回應這是刻意設計：「有些謊言和案件無關，有些有關。」（Some lies are not related to the case, some are.）有留言建議官網應揭露遊戲使用 LLM，他回應會加上一行說明，表示嫌犯是由語言模型扮演。官網則提供在嫌犯回覆下按「Flag」直接回報的功能。

## Android 版已免費上架而 iOS 版仍在等待審核

官網目前提供 Google Play 下載連結，App Store 則標示「Coming to the App Store」。開發者在 Show HN 貼文中說，遊戲在 Android 上免費，iOS 版仍在等 Apple 審核；他也在留言說，因為 App Store 審核很慢，會很快推出網頁版。推論成本目前由他自己負擔，他自述每年營運成本是「幾千」（a few thousand a year）。

## 本站認為會說謊的模型反而讓推理遊戲更有意思

一般我們希望 AI 誠實，但在這款遊戲裡，說謊正是玩法的核心；關鍵在於謊言被限制在固定的事實與時間線裡，玩家才有破綻可抓。本站認為，這種「讓模型自由說話、但不准改寫事實」的設計，也是很多 AI 應用面對的共同課題。

本站建議，對 AI 互動敘事有興趣的開發者，可以讀一讀這則 Show HN 的討論串，開發者回覆了不少設計細節。他也自述這是密集使用 AI 的一個月成果，和 [Karpathy 用 Claude Code 做出 HackerTube]({{ site.baseurl }}{% post_url 2026-11-02-karpathy-hackertube %}) 一樣，是一人搭配 AI 開發的案例。

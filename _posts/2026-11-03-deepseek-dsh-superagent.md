---
layout: post
title: "DeepSeek 開源 dsh-superagent 研究原型：主動式程式代理何時動手，由人事先設定"
date: 2026-11-03 16:00:00 +0800
summary: "deepseek-ai 組織以 MIT 授權開源 dsh-superagent-prototype，是會監聽 GitHub、在有權限的人請求時自己開工並回覆（例如 pull request）的程式代理。README 明寫這是僅供參考的研究原型，不是 DeepSeek 正式產品；誰能觸發它、能否主動做事，都由團隊事先設定。"
cover: "/assets/images/posts/2026-11-03-deepseek-dsh-superagent/cover.png"
cover_alt: "深藍底圖卡，左側大字「DeepSeek 開源程式代理 研究原型」與「非正式產品」「MIT 授權」標籤，右側為終端機視窗，列出被授權的人提出請求、開工作項目、回覆（例如 pull request）三個步驟"
cover_credit: "AI 每日快報製圖；DeepSeek 標誌取自 [deepseek-ai GitHub 組織](https://github.com/deepseek-ai)，為 DeepSeek 商標，未經修改"
tags:
  - "DeepSeek"
  - "AI 代理"
  - "開發工具"
  - "開源"
  - "GitHub"
sources:
  - name: "GitHub：deepseek-ai/dsh-superagent-prototype（README、SETUP.md、docs/）"
    url: "https://github.com/deepseek-ai/dsh-superagent-prototype"
  - name: "智東西：DeepSeek又开源了！公布Super agent架构（2026-11-01）"
    url: "https://zhidx.com/p/606311.html"
---

GitHub 上的 deepseek-ai 組織開源了 dsh-superagent-prototype。依 GitHub API 資料，這個 repo 建立於 10 月 31 日 17:32（台北時間），目前只有一個提交，授權為 MIT，主要語言是 TypeScript；11/3 09:32（台北時間）查詢時 ★13,300、1,386 forks。

## 官方 README 明寫這是研究原型而不是正式產品

README 開頭第一句就說：

> 「僅供參考的研究原型，不是 DeepSeek 的正式產品。」
>
> "Research prototype for reference only, not an official DeepSeek product."

README 也說，這份程式碼來自團隊的日常開發，大部分工程由程式代理完成，應視為研究程式碼而非可上線的軟體，可能還有錯誤，使用前要自行審查與調整。README 還提醒，公開版與團隊內部版本、以及團隊文章《Exploring Super-agent Design》描述的實作並不相同，文章中有些設計只是未來方向，原型裡並沒有實作。

## 這個代理會在有人請它時自己接下 GitHub 上的工作

依 README 的說明，dsh-superagent 是給單一 GitHub repo 用的「主動式程式代理」，以 DeepSeek Harness 外掛包的形式提供。它會監聽 GitHub，也可選擇接上飛書；當有權限的人向它提出請求時，它會開一個工作項目，在自己的代理會話與目錄中處理，再回到原本的對話交付結果，例如開一個 pull request。另有網頁面板列出需要人處理的事項。

安裝方式也很「代理化」：README 建議直接請你的程式代理讀 SETUP.md，由它一步步陪你完成設定。

據智東西報導，DeepSeek Harness 團隊同時發表文章介紹 Super-agent 架構，把排程、快取、存算分離與看門狗等電腦系統的經典做法搬進代理設計；報導也提到該插件只是驗證技術路線的原型。

## 團隊把「少占用人的注意力」當成核心原則

README 與 docs/000-philosophy.md 寫道，它的核心原則是「盡可能少占用人的注意力，盡可能多提供價值」（take as little human attention as possible, and give as much value as possible）。文件說，代理只在被請求、或團隊寫下的規則允許時才行動，也只在有人必須處理或能用上結果時才發言。

## 誰能觸發代理、能否主動做事，仍由人來設定

依 docs/002-authorization.md，預設情況下，名單上的人直接點名代理才算明確請求；bot 的訊息則不能成為明確請求，也不能停止工作。沒人要求的主動工作，必須符合團隊寫下的規則，而且預設模式是 observe，只記錄「本來會接受」的判斷，不會真的動手，團隊檢查過紀錄後才切到 auto。文件也要求操作者「從窄處開始」（start narrow）、不要拿它大量產出 PR 或廣播訊息，並對代理以團隊每天看到的帳號發出的內容負責（own what it says）。依 SETUP.md，建立代理專用帳號、接受 repo 邀請與登入 CLI 等步驟，也要由操作者本人完成。

## 開發者可以把它當成設計參考，而不是直接上線的工具

本站認為，這個原型最值得看的不是「AI 自己接工作」，而是它把權限、觸發條件與「何時該閉嘴」寫成明確規則。這和我們先前介紹的 [Anthropic Claude Duet]({{ site.baseurl }}{% post_url 2026-10-23-anthropic-claude-duet %}) 一樣，都在處理主動式代理該在什麼條件下自己行動、什麼時候要先問人。

本站建議，想試用的開發者先在測試 repo 上、用短名單和預設的 observe 模式跑一段時間，確認它的判斷可靠再放寬；畢竟官方已明說這不是正式產品。

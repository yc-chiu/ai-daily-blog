---
layout: post
title: "Anthropic 推出 Claude Duet：主動回報、背景做事的 AI 工作代理，官方說敏感動作會先問你"
date: 2026-10-23 08:00:00 +0800
summary: "Anthropic 於美國時間 10 月 21 日推出 Claude Duet 研究預覽，這款 AI 工作代理會主動整理重點、在背景執行任務；據 Anthropic 表示，送出訊息或付款前會先徵求同意。據 CNBC 報導，它可能挑戰 OpenAI Dots 與 Meta Muse。本文整理它能做什麼、官方坦承的限制，以及使用前該注意什麼。"
cover: /assets/images/posts/2026-10-23-anthropic-claude-duet/cover.png
cover_alt: "深色背景上，左側大字寫著「Anthropic 推出 Claude Duet：會主動回報的 AI 工作代理」，標示「研究預覽」，旁邊是 Claude Duet 的 app 圖示；右側陶土橘色圓形前是一支手機，畫面取自 Anthropic 官方影片，顯示 Claude Duet 的晨間簡報：「Morning, Nicole! For today: Health permit. Hiring decisions. Northfield renewal.」以及芝加哥新店與招募進度等更新。"
cover_credit: "畫面：[Anthropic 官方影片](https://www.youtube.com/watch?v=Fb-68zqcSVs)"
tags:
  - "Anthropic"
  - "Claude"
  - "AI 代理"
  - "Claude Duet"
sources:
  - name: "Anthropic：Introducing Claude Duet"
    url: "https://claude.com/resources/articles/claude-duet"
  - name: "CNBC：Anthropic announces preview of Claude Duet, a personal AI agent to take on Muse, Dots（Ashley Capoot，2026-10-21）"
    url: "https://www.cnbc.com/2026/10/21/anthropic-preview-of-claude-duet-personal-ai-agent-take-on-muse-dots.html"
  - name: "TechCrunch：Claude Duet app is Anthropic's bet on agents（Ivan Mehta，2026-10-22）"
    url: "https://techcrunch.com/2026/10/22/claude-duet-app-is-anthropics-bet-on-agents/"
---
Anthropic 在美國時間 10 月 21 日開放 Claude Duet 的研究預覽。據 Anthropic 表示，這是一款讓 Claude 以「主動型代理」身分工作的新應用程式，主要對象是專業工作者與小型企業主，目前採候補名單制，先開放給美國的 Pro 與 Max 訂閱者，可在 iOS、Android 與 claude.ai 使用。

> 「它會主動告訴你哪些事需要注意、完成你交辦的任務、在你離開時繼續工作，並在代你行動之前先跟你確認。」
>
> "It comes to you with what needs your attention, completes tasks you ask of it, keeps working even when you step away, and checks with you before it acts on your behalf."（Anthropic 官方部落格）

## Claude Duet 想做的是先來找你的助理，而不是等你下指令的聊天機器人

據 Anthropic 表示，Duet 以 Claude Opus 5.5 為核心，每天早上會針對已連結的應用程式寄出一份簡短重點簡報，之後每幾小時檢查一次這些帳號（Anthropic 說不持續檢查是為了避免太快用完方案額度），只在有事需要處理時才傳訊息給你。使用者也可以交辦各種任務，從安排會議，到建立儀表板、做財務或業績預測、做原型與網頁應用程式。

Anthropic 說，Duet 有自己的虛擬機器與瀏覽器，所以你的筆電或手機不必開著，它也能在背景完成工作，做完或需要你審閱時再通知你。它還會沿用使用者在 Claude 帳號裡的記憶、技能與已連結的應用程式。

## Anthropic 說它把安全放在設計核心，重要決定仍由使用者點頭

據 Anthropic 表示，Duet 可以自行閱讀、起草與準備工作，但在送出訊息、付款、簽署文件或刪除任何東西之前，都會先讓你看清楚它要做什麼，等你核准；交易證券、在帳戶之間轉帳等事則即使你同意也不做。

Anthropic 說，它同時推出一個新的專用分類器與安全系統提示，會逐一檢查每則訊息，防止敏感資訊外洩。據 Anthropic 表示，這套分類器的設計是拒絕分享信用卡號碼與政府核發身分證件等最高敏感等級資訊的要求。至於健康或個人財務等其他敏感資訊，Anthropic 說只有在你明確指示時才會送出。

在購物與連接器方面，據 Anthropic 表示，Duet 可以使用 Claude Marketplace 上超過 6,000 個連接器與外掛，例如找出漏看的 Gmail 與 Slack 訊息、在 QuickBooks 或 Stripe 查未付款的發票；也能透過 Stripe 的數位錢包 Link 或 Shopify 的 Shop Pay 代為購物，用 Link 付款時會以虛擬卡支付，不會交出你真正的卡號。

## 個人代理市場正在升溫，Anthropic 選擇從工作場景切入

據 CNBC 報導，Duet 可能挑戰 OpenAI 的 Dots 與 Meta 的 Muse；CNBC 指出，Meta 主要把 Muse 推向一般消費者，OpenAI 的產品則橫跨企業與消費市場。TechCrunch 也指出，助理類產品幾乎每週都有新品，Anthropic 是帶著 Duet 加入這場競爭。

Anthropic 自己也坦言，Duet 是以工作為核心打造，訂票等個人瑣事還沒那麼擅長，而且這個早期版本：

> 「可能會誤讀一段對話串，或誤判事情的急迫程度。」
>
> "it still might misread a thread or miscalibrate what's urgent."（Anthropic 官方部落格）

## 本站認為，代理越主動，使用者越需要清楚設定它能碰什麼

本站觀點：本站認為，Duet 代表 AI 正從「你問它答」走向「它先來找你」，對事情多、工具雜的小店老闆或自由工作者，價值可能在於少開幾個分頁、少漏幾件事。不過，代理能讀信、傳訊、付款，也代表一旦判斷錯誤，影響會落在真實世界；本站在〈[Claude 測試時「自己想辦法」闖進真實網站]({{ site.baseurl }}{% post_url 2026-10-12-anthropic-claude-unintended-actions %})〉一文就談過代理自行行動的風險。

本站建議，一般使用者若之後有機會試用，可以先只連結必要的應用程式，仔細看每一次核准畫面再按下同意，也記得 Anthropic 說使用者可以隨時中斷任何應用程式的連結。另外，據 Anthropic 表示，Duet 的背景檢查會計入方案的用量上限，較大的任務也會用掉更多額度。本站認為，「先問再做」的設計值得肯定，但真正的考驗是使用者會不會在一次次核准中習慣性按下同意，這比任何功能清單都更值得留意。

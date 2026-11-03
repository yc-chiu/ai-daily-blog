---
layout: post
title: "Karpathy 自述用 Claude Code 約兩小時做出 HackerTube：不再寫程式，但仍親手做了三件事"
date: 2026-11-02 12:00:00 +0800
summary: "Andrej Karpathy 在個人部落格自述，他受不了 YouTube 的推薦，用 Claude Code 與 Opus 5.5 做出 HackerTube，收錄他稱由 Hacker News 網友推薦的 6,454 支 YouTube 影片，並說整個過程約兩小時。他自述已不再讀寫程式、只與 Claude 對話，但建立 API 金鑰、開 VPS 與買網域這三件事仍親手完成。"
cover: "/assets/images/posts/2026-11-02-karpathy-hackertube/cover.png"
cover_alt: "淺藍底封面，右側是 Andrej Karpathy 演講時的照片，他穿深色毛衣、手持簡報筆；左側深藍色大字寫「用 Claude Code 約 2 小時做出」，橘色字為「HackerTube」，下方小字說明 API 金鑰、VPS 與網域仍是他親手做的，左上角標籤為「Karpathy 自述」"
cover_credit: "圖片來源：Sk aman khan／[Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Andrej_karpathy_2016.webp)，CC0 1.0（已裁切、調色並加上文字）"
tags:
  - "Andrej Karpathy"
  - "Claude Code"
  - "AI 代理"
  - "人機協作"
sources:
  - name: "Andrej Karpathy：HackerTube（karpathy.bearblog.dev，2026-10-31）"
    url: "https://karpathy.bearblog.dev/hacker-tube/"
---

Andrej Karpathy 在 10 月 31 日的個人部落格文章中，分享他在週六早上動手，用 AI 代理做出一個影片網站的經過。這篇文章引人注意的地方，不只是速度，而是他很具體地列出了哪些事交給 AI、哪些事仍由自己動手。

## Karpathy 因為受不了 YouTube 的推薦而決定自己做一個

Karpathy 自述，週五晚上 11 點他累了，打開 YouTube 想看點東西，卻發現眼前是一整面浮誇縮圖與老套推薦。他說：

> 「我相信這套演算法對網路上的一般人很有效，但對我來說絕對不管用。」
>
> "I'm sure this algorithm works well for the median person on the internet, but it definitely does not work for me."

於是隔天週六早上，他交給 Opus 5.5 一個任務：根據 Hacker News 上被推薦過的影片，做一個自己的 YouTube 複製品。成果就是 hackertube.org。

## Karpathy 自述 AI 從 Hacker News 留言篩出 6,454 支影片

據 Karpathy 描述，Opus 下載了 Hacker News 的所有留言並加以篩選，再在 Claude Code 的 Workflow 功能中讓 Sonnet 處理這些留言、清掉垃圾留言，最後篩出 4 萬則推薦 YouTube 影片的留言：

> 「總共得到 6,454 支 YouTube 影片，它們在 2007 到 2026 年間被 HN 上的幾個人推薦過，橫跨 150 個主題。」
>
> "In total, we get 6,454 YouTube videos that have been recommended by a few people on HN from 2007-2026 across 150 topics."

他列出的功能包括：改用影片 50% 位置的畫面當縮圖、不需要帳號就能用的「為你推薦」（狀態存在瀏覽器工作階段）、鍵盤快捷鍵，以及可以匯出網站資料，交給你自己的 AI 代理做出自己的版本。他寫道：「現在這只要大約兩小時。」（This takes ~2 hours now.）並接著說「我又能好好呼吸了」（I can breathe again）。

## Karpathy 說他不再做傳統工程，只跟 Claude 對話

Karpathy 在文末補充，他用的是 Mac 桌面版 Claude Code，預設使用 Medium effort 的 Opus 5.5。他說：

> 「我實際上已經不再做任何像傳統工程的事了（讀寫程式、在終端機下指令等等），我只跟 Claude 對話，讓它做所有事。」
>
> "I don't actually do anything resembling traditional engineering anymore (read/write code, run commands in a terminal, or etc.), I only talk to Claude and have it do everything."

## Karpathy 自述這次仍有三件手動工作由他親手完成

換句話說，他說自己沒碰的範圍，是讀寫程式、在終端機下指令這類傳統工程工作，並不是整件事都沒有動手。Karpathy 自述，這次唯一的「手動工作」（manual work）有三件：

1. 在 Google Cloud 介面建立 API 金鑰，用來向 YouTube 查詢影片資料（"create some kind of API key from Google Cloud UI to query YouTube for video metadata"）。
2. 開一台 VPS 主機（"I booted up a VPS box"）。
3. 購買網域（"I bought the domain name"）。

他說，這些事是在 Claude 工作的空檔裡做的，「所以感覺還是有點像團隊合作」（so it still feels a little bit like team work）。主機開好後，他把 IP 交給 Claude，請它更新、部署、加固與最佳化程式碼，剩下的都由 Claude 完成。

## 讀者可以從這個案例看出人還得負責哪些事

Karpathy 沒有解釋這三件事為何要由他來做，但它們有一個共通點：都牽涉帳號、付款或對外的身分與權限。本站認為，這正是目前 AI 代理和人類分工的界線：寫程式與部署可以交給代理，但開帳號、花錢、取得金鑰，仍是人要自己決定、也要自己負責的部分。

本站建議，想仿效的讀者先從個人小工具開始；HackerTube 本身就提供網站資料匯出，Karpathy 說可以把它交給你的代理，輕鬆做出自己的版本（to give to your agent to easily create your own version），是很好的練習起點。動手時，請把 API 金鑰、主機與網域這類權限自己掌握好；交給代理部署前，也記得確認它會用到哪些權限。Karpathy 先前也分享過[讓 LLM 輸出更好懂的方法]({{ site.baseurl }}{% post_url 2026-10-14-karpathy-understanding-llm-output %})，可以搭配閱讀。

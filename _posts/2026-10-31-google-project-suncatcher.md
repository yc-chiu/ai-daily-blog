---
layout: post
title: "Google Suncatcher 原型衛星傳回首個 AI 回應：軌道上的 TPU 用 Gemma 4 寫俳句"
date: 2026-10-31 08:00:00 +0800
summary: "Google 在 2026 年 10 月 30 日的官方部落格表示，Project Suncatcher 原型衛星已完成啟用檢查，並從軌道上傳回第一個 AI 回應：星上的 Gemma 4 開放模型依地面提示寫出一首太空俳句。Google 稱 Suncatcher 是探索在太空為 AI 運算供電的長期研究登月計畫，下一步將測試 TPU 在熱應力與輻射下的表現。"
cover: "/assets/images/posts/2026-10-31-google-project-suncatcher/cover.png"
cover_alt: "從國際太空站放出的小型衛星，背景是黑色太空與地球邊緣，旁邊寫著『太空中的 TPU Hello World』"
cover_credit: "照片：NASA（國際太空站 Expedition 38 組員拍攝）／[Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Planet_Labs_satellite_launch_from_ISS.jpg)，公有領域（已裁切、調色並加上文字）"
tags:
  - "Google"
  - "Project Suncatcher"
  - "TPU"
  - "Gemma"
  - "AI 基礎建設"
sources:
  - name: "Google：We've received our first response from the Project Suncatcher prototype satellite.（Travis Beals，2026-10-30）"
    url: "https://blog.google/innovation-and-ai/models-and-research/google-research/project-suncatcher-satellite-response/"
  - name: "Google：Our Project Suncatcher prototype satellite is in orbit.（Travis Beals，2026-10-01）"
    url: "https://blog.google/innovation-and-ai/models-and-research/google-research/project-suncatcher-prototype/"
  - name: "TechCrunch：Google's first data center satellite is online and writing poetry（Tim Fernholz，2026-10-30）"
    url: "https://techcrunch.com/2026/10/30/googles-first-data-center-satellite-is-online-and-writing-poetry/"
---
Google 想知道，太空有沒有可能在未來承載可擴展的機器學習基礎設施。Google 資深總監 Travis Beals 在 10 月 30 日的官方部落格表示，原型衛星已經從軌道上回傳第一個 AI 回應。

## Google 表示軌道上的 TPU 首次回應了地面送出的提示

Google 表示，這顆原型衛星與 Planet 合作打造，在 10 月 1 日搭乘 SpaceX 的 Transporter-18 共乘任務升空。Google 當時寫道，「有些事情只能在太空中測試」（Some things can only be tested in space），並表示相關研究已發表在同儕審查期刊 Joule。過去幾週，團隊完成了啟用檢查，包括啟動主機與 TPU 模組，並成功執行初步的機器學習測試。

Google 說，本週團隊達成了「Hello World」里程碑，也就是軌道上的資料中心等級 TPU 首次產生 AI 回應。團隊在地面站通訊時段上傳第一個提示，請星上的 Gemma 4 開放模型寫一首關於身在太空的俳句；衛星飛過挪威斯瓦爾巴群島（Svalbard）時，傳回了這首詩：

> 「腳下是藍色彈珠／資料在靜默中優雅流動／星光滋養我的核心。✨」
>
> "Blue marble below / Data streams in silent grace / Starlight feeds my core. ✨"（Google 官方部落格）

Google 表示，之後團隊也測試了以太空為題的打油詩，以及回報酬載系統技術狀態的遙測提示。

## 據 TechCrunch 報導，這顆衛星一次只能開一顆 TPU

據 TechCrunch 報導，這顆衛星搭載四顆 TPU，最高可發電 1 kW，但因為 TPU 耗電，一次只能開啟一顆、每次約 20 分鐘，讓太空與地面之間的通訊更加複雜。TechCrunch 也引述 Google 發言人表示，衛星運作正常。TechCrunch 指出，輻射可能造成記憶體「位元翻轉」，在一般監控工具沒有察覺的情況下損壞資料；地面測試顯示，輻射對推論的影響應該很小，對訓練模型的影響較大，現在團隊終於能在真實太空環境中驗證。

## Google 說這只是長期研究計畫的第一步

Google 把 Suncatcher 稱為「長期研究登月計畫」（long-term research moonshot），探索在太空為 AI 運算供電的可能。Google 表示，下一步會進行一系列測試，評估 TPU 在軌道上的熱應力與輻射暴露下表現如何；確認 TPU 能在太空中可靠執行工作，將為下一個里程碑鋪路，也就是 2027 年的兩顆互連衛星。據 TechCrunch 報導，這兩顆衛星將支援更高的發電量，並展示衛星之間的光學通訊鏈路。

據 TechCrunch 報導，Suncatcher 的研究人員在本月發表的同儕審查分析中估計，SpaceX 的 Starship 需要飛行 1,800 次，才能達到它過去在其他火箭上看到的、靠經驗累積帶來的成本下降；TechCrunch 也指出，Google 關注的是在 2030 年代具經濟效益的基礎設施。

## 讀者可以把這則新聞看成 AI 電力瓶頸的一種長期解方

AI 資料中心越蓋越多，電力已成為瓶頸之一，例如 Amazon 執行長 Jassy 就談過[算力與電力不足的問題]({{ site.baseurl }}{% post_url 2026-10-24-andy-jassy-a16z %})。本站認為，Suncatcher 這次證明的是 TPU 能在軌道上開機並執行模型，離真正的太空資料中心還很遠；它更像是對未來十年電力限制的長期押注，而不是近期能分擔 AI 資本支出壓力的方案。

---
layout: post
title: "Gemini 4 Carbon 發表：Google 自報資安基準成績，目前僅開放部分資安防禦者"
date: 2026-10-29 08:00:00 +0800
summary: "Google DeepMind 發表 Gemini 4 Carbon，主打資安防禦與長時程任務。Google 自報它在找漏洞、驗證與修補三項資安基準的成績為 88.2%、54.8%、71.0%（未啟用防護機制下測得），尚無第三方驗證；目前只先開放給部分資安防禦者，開發者、企業與一般使用者還要再等。"
cover: /assets/images/posts/2026-10-29-gemini-4-carbon/cover.png
cover_alt: "Google 與 DeepMind 位於倫敦 6 Pancras Square 的辦公大樓入口，玻璃帷幕上亮著 Google 招牌；左側深色底上有大字「Gemini 4 Carbon」、「主打資安與長時程任務」與「Google 自報 AA 指數 59 分」"
cover_credit: "照片：[Gciriani](https://commons.wikimedia.org/wiki/File:Google-Deep_Mind_headquarters_in_London,_6_Pancras_Square.jpg)／Wikimedia Commons，[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)（已裁切、調色並加上文字）"
tags:
  - "Google"
  - "Gemini"
  - "Gemini 4 Carbon"
  - "資安"
  - "AI 安全"
sources:
  - name: "Google DeepMind：Gemini 4 Carbon: our next frontier model（Koray Kavukcuoglu，2026-10-28）"
    url: "https://deepmind.google/blog/gemini-4-carbon-our-next-frontier-model/"
  - name: "Google DeepMind：Fairwind Program"
    url: "https://deepmind.google/fairwind-program/"
---
Google DeepMind 在 10 月 28 日發表 Gemini 4 Carbon。Google DeepMind 資深副總裁 Koray Kavukcuoglu 在官方部落格寫道，這是「我們最強的模型，具備最先進的資安與長時程能力」（our strongest model with state-of-the-art cybersecurity and long horizon capabilities）。Carbon 距離上一代 [Gemini 4 Argon]({{ site.baseurl }}{% post_url 2026-10-14-gemini-4-argon %}) 推出只隔兩週。

## Carbon 目前只先開放給一部分資安防禦者使用

Google 表示，從本週開始，Carbon 會先提供給「一部分網路防禦者」（a subset of cyber defenders），之後再透過 Fairwind Program 逐步開放給更多受信任的合作夥伴。Google 也說，它正積極參與美國政府自願性的模型發布前測試流程，並會繼續蒐集回饋、調整防護機制，再「盡快」透過產品開放給開發者、企業與一般使用者。官方沒有公布確切的開放日期。

價格方面，Google 表示 Carbon 推出時會沿用 Argon 的導入期價格，每百萬輸入 token 2 美元、每百萬輸出 token 10 美元；導入期結束後，改為輸入 4 美元、輸出 20 美元。

## Google 說 Carbon 能連續工作好幾天處理複雜的工程問題

據 Google 表示，Carbon 是為長時間持續運作的代理式工作流程而設計。Google 說，內部團隊曾看到 Carbon 連續執行好幾天，在碰壁後仍持續嘗試，處理像是在大型程式碼庫與底層系統中找出細微錯誤的根本原因並加以修補這類多步驟工程任務。Google 也表示，這次針對寫程式、代理任務、科學任務、全端網頁開發與多模態理解都做了改進。

## Google 公布 Carbon 在找漏洞、驗證與修補三個環節的資安基準成績

Google 把資安防禦分成三個環節，並公布 Carbon 在外部基準測試上的成績。Google 註明，這些成績是在沒有啟用防護機制的情況下測得：

- **找出漏洞**：SEC-bench Pro 達 88.2%。
- **用攻擊驗證風險**：ExploitGym 達 54.8%，可用來判斷哪些漏洞真的能被利用、應該先修。
- **從根本修補**：Collinear 的 CWE-bench 達 71.0%。

Google 也自報，Carbon 在更新後的 Artificial Analysis Intelligence Index v5.0 拿下 59 分、排名第一；在 WebDev Arena 上進步 89 個 Elo 分，以 1768 分排第 4。Google 說，內部基準顯示 Carbon 產生安全程式碼的成功率是 Argon 的兩倍以上；Chrome 團隊也回報，Carbon 產生高品質修補程式的表現，比另一家實驗室的大型前沿模型好 10 倍以上。Google 稱為自家雲端資安平台的 Wiz 則觀察到，Carbon 在網頁滲透測試的基準上領先。

![長條圖：Google 自報 Gemini 4 Carbon 在未啟用防護機制下的資安基準成績，找漏洞（SEC-bench Pro）88.2%、驗證（ExploitGym）54.8%、修補（CWE-bench）71.0%]({{ '/assets/images/posts/2026-10-29-gemini-4-carbon/chart-security-bench.png' | relative_url }})

## Google 說 Carbon 更少走捷徑，也更少捏造

Google 表示，Carbon 在 Terminal-Bench 4.0 上的成功作弊率降到 0.0%，嘗試作弊的比例降到 0.4%；在內部團隊的實際寫程式環境中，高嚴重度的失準警示減少將近 80%。Google 也說，Carbon 的無根據說法比 Argon 少了大約一半，執行多步驟計畫時，越權行為減少 26%、做得不夠的情況減少 29%；遇到模糊不清的需求時，Carbon 會先查找相關資料、把矛盾之處告訴使用者，而不是自己亂猜。此外，在 Gray Swan 的間接提示注入基準上，攻擊成功率從 Argon 的 0.7% 降到 0.0%。

## 讀者可以先關注 Carbon 開放後的第三方實測

本站認為，Google 先把資安能力強的模型交給防禦者，是一種「先讓防守方領先」的做法；但上述成績都是 Google 自行公布，實際表現仍有待開放後的第三方測試確認。本站建議，負責資安的團隊可以留意 Fairwind Program 的申請資格，一般開發者則等官方公布正式開放時間再評估。

---
layout: post
title: "LangChain 執行長 Harrison Chase 上 20VC：模型路由該放進 harness，代理記憶層仍沒人解開｜訪談精讀"
date: 2026-10-18 08:00:00 +0800
summary: "LangChain 共同創辦人暨執行長 Harrison Chase 上《20VC》：做垂直領域代理，模型路由應放在 harness；代理記憶層仍大幅懸而未解，LangChain 也收掉了自家商用記憶方案。他估計公司約三成工程薪資花在寫程式工具上，一個外掛設定失誤曾一週燒掉 4 萬；他也坦言，一年半前決定不做 gateway 是錯誤的決定。"
cover: /assets/images/posts/2026-10-18-harrison-chase-20vc/cover.png
cover_alt: "赤陶色底圖卡：左上為「訪談精讀」標籤與日期 2026-10-18，下方一個大引號，大字「代理的記憶層 仍然大幅懸而未解。」，其下英文引言「this memory layer for agents is still massively unsolved」，再下方「LangChain 執行長 Harrison Chase（29:12）」與「Podcast · 20VC」；右上角有一個淡色大圓形裝飾"
tags:
  - "訪談精讀"
  - "AI 代理"
  - "LangChain"
  - "AI 成本"
  - "開發工具"
sources:
  - name: "20VC（YouTube）：The Future of Inference Market & Model Routing: Commodity or Increasing in Value? | LangChain CEO"
    url: "https://www.youtube.com/watch?v=1jDCPEHwQfI"
  - name: "20VC Podcast（Libsyn 單集頁）：Horizontal vs Vertical Agents: Who Wins | Model Routing: Commodity or Increasing in Value | The Future of the Inference Market | Why Founders Should Take Discounts for Tier 1 Firms with Harrison Chase, LangChain"
    url: "https://thetwentyminutevc.libsyn.com/20vc-horizontal-vs-vertical-agents-who-wins-model-routing-commodity-or-increasing-in-value-the-future-of-the-inference-market-why-founders-should-take-discounts-for-tier-1-firms-with-harrison-chase-langchain"
  - name: "20VC Podcast 音檔（MP3，同一集）"
    url: "https://traffic.libsyn.com/secure/thetwentyminutevc/The_Memo__Harrison_Chase__Langchain.mp3"
  - name: "LangChain：LangChain raises $125M to build the platform for agent engineering（2025-10-20）"
    url: "https://www.langchain.com/blog/series-b"
  - name: "LangChain：Open SWE: An Open-Source Framework for Internal Coding Agents（2026-03-17）"
    url: "https://www.langchain.com/blog/open-swe-an-open-source-framework-for-internal-coding-agents"
  - name: "The Verge：Websites are closing their doors to AI agents（2026-10-17）"
    url: "https://www.theverge.com/ai-artificial-intelligence/1013195/ai-agents-blocked-web"
---

這次「訪談精讀」的主角是 LangChain 共同創辦人暨執行長 Harrison Chase。LangChain 在 2022 年以開源專案起家，提供開發者打造 AI 代理（agent）的框架，另有可觀測與評估平台 LangSmith。公司在 2025 年 10 月宣布完成 1.25 億美元 B 輪募資，估值 12.5 億美元。節目是創投 Podcast《20VC》，由 Harry Stebbings 主持，YouTube 版長約 63 分鐘，於台灣時間 10 月 17 日上架。

這集值得看，因為 Chase 站在模型和企業之間，天天看到大家怎麼打造代理、又怎麼為帳單頭痛。他談的路由、記憶與成本，正是近來業界爭論最多的題目。

以下依 Podcast 音檔與 YouTube 影片自行轉錄整理，引述片段都已對照原音。說話者依問答脈絡與畫面判斷；中文為本站翻譯，引號內為原句，時間碼以 YouTube 版為準。

<div style="position:relative;width:100%;aspect-ratio:16/9;"><iframe src="https://www.youtube-nocookie.com/embed/1jDCPEHwQfI" title="20VC：The Future of Inference Market & Model Routing | LangChain CEO Harrison Chase" style="position:absolute;inset:0;width:100%;height:100%;border:0;" loading="lazy" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe></div>

## 這集訪談有五個核心觀點

### 一、Chase 認為垂直代理的模型路由應該放在 harness 裡

主持人問，依請求挑選模型的「模型路由」價值有多大。Chase 先拆出一個問題：路由該放在 harness，還是 gateway？harness 是包在模型外面、負責呼叫工具與管理狀態的程式；gateway 則是統一轉接各家模型的 API 服務。放在 gateway 的好處是不必改程式碼，任何 harness 都能接上。他偏向 harness，因為 harness 掌握更多狀態，能顧好提示快取（prompt cache），也能依不同模型改寫提示。

> 「我相當堅定地認為，做路由必須了解 harness。」
>
> "I pretty strongly believe that like routing, you have to be harness aware" — [16:58](https://www.youtube.com/watch?v=1jDCPEHwQfI&t=1018s)

他的結論是看場景：做垂直領域的代理，路由需要放在 harness 裡（"routing needs to be in the harness"，[19:28](https://www.youtube.com/watch?v=1jDCPEHwQfI&t=1168s)）；一般聊天或寫程式這類水平任務，放在 gateway 或許可行。他也猜測 OpenRouter 的用量多半來自單純的模型存取，而不是智慧路由，但強調這只是他的推測（[16:21](https://www.youtube.com/watch?v=1jDCPEHwQfI&t=981s)）。

### 二、他坦言代理的記憶層至今仍沒有人解開

被問到哪些事今天聽來瘋狂、兩三年後會很普遍，他選了記憶：

> 「我認為代理的記憶層仍然大幅懸而未解。」
>
> "this memory layer for agents is still massively unsolved" — [29:12](https://www.youtube.com/watch?v=1jDCPEHwQfI&t=1752s)

他說 LangChain 和外界談記憶已約兩年，也在開源專案中嘗試，還推出過商用記憶方案的 alpha 版，後來又收掉（[29:43](https://www.youtube.com/watch?v=1jDCPEHwQfI&t=1783s)）。主持人追問原因：

> 「我們收掉它，是因為沒有找到產品市場契合。」
>
> "We killed it because we didn't find product market fit" — [30:45](https://www.youtube.com/watch?v=1jDCPEHwQfI&t=1845s)

他檢討當初做得太通用（"too general"，[30:50](https://www.youtube.com/watch?v=1jDCPEHwQfI&t=1850s)）。他認為記憶最難的是判斷該記住什麼的那套流程（[31:07](https://www.youtube.com/watch?v=1jDCPEHwQfI&t=1867s)），而且高度依領域而定，個人助理、法律、金融需要的記憶都不一樣。

### 三、LangChain 估計約三成工程薪資花在寫程式工具上

主持人問 LangChain 花多少工程薪資在寫程式工具上：

> 「我們大概花了約 30% 的工程薪資在寫程式工具上。」
>
> "roughly 30% of our engineering salary on coding tools" — [38:54](https://www.youtube.com/watch?v=1jDCPEHwQfI&t=2334s)

這是他的估計，隨後對話中也稱之為粗估（"guesstimate"，[41:43](https://www.youtube.com/watch?v=1jDCPEHwQfI&t=2503s)）。他說近兩個月這筆支出反而下降，用掉的 token 卻增加了，靠的是三個步驟：先讓花費看得見、再設預算上限、最後改進 harness 本身（[39:04](https://www.youtube.com/watch?v=1jDCPEHwQfI&t=2344s)）。

### 四、一個外掛設定失誤曾讓公司一週燒掉約 4 萬

花費看得見之後，他發現花最多的人不一定最有效。有些資深工程師花很多，他完全信任；但也有設定不當造成的暴衝。有一兩個前端任務用了某個外掛，每一輪都把網頁截圖或 DOM 快照傳回代理，形成巨大迴圈：

> 「我想我們在那一件事上一週就花了 4 萬。」
>
> "we spent 40K in a week on that one thing" — [41:12](https://www.youtube.com/watch?v=1jDCPEHwQfI&t=2472s)

他沒有說明幣別，語氣也是概略數字。他強調這不是惡意，甚至不算預期中的用法，只是個失誤，所以能及早抓出來非常值得。

### 五、他說一年半前決定不做 gateway 是完全錯誤的判斷

快問快答時，主持人問他過去 12 個月最大的轉念。他說推論（inference）市場非常龐大，並回憶一年半前曾和董事會討論要不要做 gateway，當時看不出能比 OpenRouter 多提供什麼價值：

> 「我認為那是百分之百錯誤的決定。」
>
> "that was 100% the wrong decision" — [1:01:20](https://www.youtube.com/watch?v=1jDCPEHwQfI&t=3680s)

## 訪談中提到了這些工具與用法

- **Open SWE**：LangChain 自建的雲端寫程式代理。Chase 說這已是他唯一的寫程式方式，在 Slack 傳訊息就能啟動任務（[39:48](https://www.youtube.com/watch?v=1jDCPEHwQfI&t=2388s)）；團隊在這個 harness 裡加入提示快取與路由來控制成本。依官方部落格，Open SWE 已開源，建立在 Deep Agents 與 LangGraph 之上，每個任務在獨立的雲端沙箱執行。
- **LangSmith**：LangChain 把所有寫程式代理的用量導入這個平台，分析誰花了多少、花在哪裡。
- **預算上限**：他舉例，可以叫代理去訂位，但花費不得超過 5 美元（[37:01](https://www.youtube.com/watch?v=1jDCPEHwQfI&t=2221s)）。公司內部也設了預算，超過就找工程副總，對方幾乎都會放行，用意是防止代理跑進錯誤迴圈。
- **提示快取**：他提到模型供應商開始允許在任務中途更換代理可用的工具而不破壞快取，以往這會讓成本大增（[37:35](https://www.youtube.com/watch?v=1jDCPEHwQfI&t=2255s)）。

## 產業脈動顯示網站正對 AI 代理關上大門

談到網站會不會放行代理，Chase 認為未來各家服務會推出自己的代理，讓使用者的通用代理去和它對話：

> 「我認為未來是服務提供者推出自己的代理。」
>
> "the future is providers exposing their own agent" — [34:45](https://www.youtube.com/watch?v=1jDCPEHwQfI&t=2085s)

主持人質疑這會讓網站失去廣告與加購收入。他回答，垂直代理可以把推薦放進回覆裡，和底層系統互動也比第三方代理更有效率。

The Verge 10 月 17 日報導，Meta Muse、xAI Grok、OpenAI Dots、Instinct 等代理的使用者回報在大型網站受阻：Yelp 只開放給付費參加資料授權計畫的代理，Delta 航空不讓代理代訂機票，摩根大通與嘉信理財以資安為由封鎖代理存取帳戶，Amazon 也說 Muse 的持續存取違反網站政策。Meta 則改與 Walmart、Gap、Sephora、Best Buy 等零售商合作，Shopify 也向代理開放店面。報導也指出，就算網站沒有明文封鎖，代理仍可能觸發反機器人機制。

本站觀察：網站想要的是自己掌控的入口，這和 Chase 的預測方向一致，但過渡期顯然會很混亂。Dots 的背景可參考本站的 [Greg Brockman 訪談]({{ site.baseurl }}{% post_url 2026-10-16-greg-brockman-no-priors %})。

## 這些觀點對你有三層意義

- **開發者**：做特定領域的代理時，路由、提示快取與記憶都該當成 harness 的一部分設計，不要全交給外部服務。本站先前的 [Claude Code 工程師訪談]({{ site.baseurl }}{% post_url 2026-10-13-claude-code-bitter-lesson %})也提醒，harness 會隨模型快速過時，設計時要保留替換空間。
- **主管與資訊人員**：導入寫程式代理前，可以照 Chase 的三步驟走：先看得見花費、再設預算、最後優化 harness。30% 只是 LangChain 自己的粗估，不代表業界平均；但一個外掛一週燒掉 4 萬的例子說明，沒有監控就很難及早發現問題。
- **一般上班族**：個人代理能不能幫你訂位、購物，短期內要看網站願不願意配合。代理被擋時，不一定是代理不好，也可能是網站政策使然。

節目尾聲，主持人問他有哪個關於代理的信念是多數人不同意的。他的回答很樸素：代理至今依然非常難做（[1:00:58](https://www.youtube.com/watch?v=1jDCPEHwQfI&t=3658s)）。

---
layout: post
title: "Sam Altman 上 Cheeky Pint：他說本機 AI 推論的 DRAM 多半閒置，應在雲端追求最大使用率｜訪談精讀"
date: 2026-11-01 08:00:00 +0800
summary: "OpenAI 執行長 Sam Altman 上《Cheeky Pint》表示，從全球分配的角度看，讓每台電腦為本機 AI 推論放著有限的 DRAM，他估計只用約 5% 的時間，相當糟糕，應在雲端追求最大使用率。他也談到 OpenAI 刻意讓數學研究「失控一週」，以及為何寧願要一兆個略超越人類的 AI。"
cover: "/assets/images/posts/2026-11-01-sam-altman-cheeky-pint/cover.png"
cover_alt: "深色底封面，右側是記憶體模組的特寫，可見綠色電路板、多顆記憶體晶片與底部金色接點，左側白色大字寫著「全球 DRAM 供給有限」，下方金色字為「本機推論值得嗎？」。"
cover_credit: "照片：PantheraLeo1359531／[Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Micron_MTC40F204681RC48BA1R_20240407_076.jpg)，CC BY 4.0（已裁切、調色並加上文字）"
tags:
  - "訪談精讀"
  - "OpenAI"
  - "Sam Altman"
  - "AI 基礎建設"
  - "DRAM"
sources:
  - name: "Cheeky Pint（YouTube）：Why Sam Altman is against a single superintelligence"
    url: "https://www.youtube.com/watch?v=iMsUcCYNKqY"
  - name: "Cheeky Pint #39：Why Sam Altman is against a single superintelligence"
    url: "https://cheekypint.transistor.fm/39"
  - name: "Cheeky Pint #39 官方逐字稿"
    url: "https://cheekypint.transistor.fm/39/transcript"
  - name: "The Verge：Sam Altman says it's better for RAM to be in a data center than on your desk（Stevie Bonifield）"
    url: "https://www.theverge.com/ai-artificial-intelligence/1023820/sam-altman-ram-shortage-cloud-servers"
  - name: "The Verge：Sam Altman sympathizes with mathematicians, but says OpenAI's math onslaught won't stop（Robert Hart）"
    url: "https://www.theverge.com/ai-artificial-intelligence/1023054/altman-cheeky-pint-ai-math-interview"
---

OpenAI 執行長 Sam Altman 上了 Stripe 共同創辦人 John Collison 主持的 Podcast《Cheeky Pint》，這集是第 39 集，10 月 29 日上架，長約 53 分鐘。兩人邊喝啤酒邊聊，話題從資安漏洞、AI 數學一路談到算力短缺。這集值得看，是因為 Altman 把「AI 該在哪裡跑」說成一個資源分配問題，而這個問題正牽動記憶體價格，也牽動你下一台電腦的售價。

<div style="position:relative;width:100%;aspect-ratio:16/9;"><iframe src="https://www.youtube-nocookie.com/embed/iMsUcCYNKqY" title="Cheeky Pint：Why Sam Altman is against a single superintelligence" style="position:absolute;inset:0;width:100%;height:100%;border:0;" loading="lazy" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe></div>

以下引述皆出自節目官方逐字稿；時間連結指向官方影片說明中的章節起點，不是引述的精確秒數。

## Altman 在這集訪談提出了五個核心觀點

### 一、Altman 認為本機 AI 推論讓有限的 DRAM 大多時間閒置

Collison 問到記憶體等供應鏈短缺時，Altman 舉了一個他認為「非常不直觀」的例子：很多人想要本機推論，以為有了開源模型、能在自己電腦上跑，就不再需要資料中心。他的看法正好相反。他談的是為了在本機跑 AI 模型而配置的 DRAM，不是電腦裡所有記憶體的用途：

> 「從全球分配的角度來看，讓每個人的電腦裡都放著一堆全球供給有限的 DRAM……而且只有 5% 的時間在用，其實相當糟糕。」
>
> "from a global allocation perspective, actually, it's quite terrible to have everybody have a bunch of the world's limited supply of DRAM sitting in their own computer. And, being used— … 5% of the time." — [〈Compute〉章節 25:17](https://www.youtube.com/watch?v=iMsUcCYNKqY&t=1517s)

他接著說，在供給這麼吃緊的環境下，應該「在雲端追求最大使用率」（You want maximum utilization in the cloud），而很多人的直覺正好與此相反。

### 二、Altman 認為記憶體市場的「看不見的手」正在失靈

Collison 說，高價本該引來更多記憶體產能。Altman 回答「很糟」，並認為看不見的手目前「不太管用」。他解釋，長期以來，DRAM 廠商投入 200 億美元資本支出只賺回 190 億美元，在景氣循環中起起落落；如今這些廠商一年各自可能賺進約 1,000 億美元自由現金流，但都記得過去差點因過度蓋廠而破產，所以擴產很保守。

> 「我認為看不見的手現在正在失靈。」
>
> "I think the invisible hand is failing right now." — [〈Compute〉章節 25:17](https://www.youtube.com/watch?v=iMsUcCYNKqY&t=1517s)

### 三、Altman 承認 OpenAI 讓數學研究「失控了一週」，而且是刻意的

談到數學，Altman 說 OpenAI 曾刻意放手讓團隊不計成本地探索，因為新典範出現時，不試就不知道能走多遠：

> 「我們確實讓數學那邊失控了一週，而且是刻意的。」
>
> "we did let it get out of control for one week on the math. Intentionally so" — [〈Math〉章節 15:47](https://www.youtube.com/watch?v=iMsUcCYNKqY&t=947s)

Altman 口述，Navier–Stokes 證明的花費大約是「一千萬美元量級」，「也許多一點」；Collison 追問數學上是否總共花了數億美元，Altman 表示同意，並說這也包含許多尚未公布的發現。他也估計，在完成一年後，大概能用百分之一的成本重做 Navier–Stokes。對於數學家的反彈，他說自己仍認為世界有權理解宇宙如何運作，「但我確實對這種方式有同理心」（But I do have empathy for the method）。

### 四、Altman 寧願要一兆個略超越人類的 AI，而不是一個超級 AI

從安全角度，Altman 說他看好「代理團隊」（他不喜歡「代理群」這個說法），因為多個代理彼此制衡的性質，很像人類社會靠多元與民主維持的韌性：

> 「直覺上，我寧願讓一兆個略超越人類智慧的 AI 加入社會，也不要一個 IQ 一兆的 AI 加入社會。」
>
> "I would much rather intuitively have a trillion AIs of slightly superhuman intelligence join society than one AI of 1 trillion IQ join society." — [〈Agent swarms〉章節 23:12](https://www.youtube.com/watch?v=iMsUcCYNKqY&t=1392s)

### 五、Altman 認為每 GW 算力的成本應該大幅下降

Altman 說，各方對每 GW 算力五年總持有成本的估法不一，他以 700 億美元為例，認為若能降到 200 億美元，大家應該會開心得多，而且每年仍應要求更聰明的模型帶來 10 倍效能。他自稱支持「通縮型技術」（Pro-deflationary technology），但也說要降到 200 億美元，能源得更便宜，從「熔化沙子」到產出 token 之間層層疊加的毛利也必須壓縮。

## Altman 提到可以直接替 AI 代理設定算力預算

Altman 說，可以直接告訴 AI 代理「用 1 萬美元的算力盡力做到最好」，代理能理解這種預算限制。他也提到 OpenAI 內部不獎勵大量使用算力，沒有 token 排行榜，排名太高反而有點扣分；但只要證明在做重要的事，就會得到支持。

談到個人代理，Altman 認為 OpenAI 的 Dots 等產品雖然受歡迎，但還沒有人做出讓人「無法想像沒有它」的版本；他說，這距離成為超級主流產品只差「少數幾個點子」（a small number of ideas away），關鍵是要「真的能用」、穩定可靠。

## 算力短缺正推動 OpenAI 自建晶片、資料中心與機器人

資安也是這集的開場話題。Altman 說，模型找漏洞的能力仍在快速進步，而且過去很少人真的用它們去檢查網路上所有的程式碼；他認為，我們會發現自己身處一個嚴重漏洞比預期多得多的世界。

Altman 說 OpenAI 做了一顆主打每瓦智慧效能的晶片，正在學習自建資料中心，也有機器人計畫要用來大量建造資料中心。他提到外界很少討論「自我複製的資料中心」，也就是用 AI 控制機器人、經營晶圓廠、造渦輪與太陽能板，再蓋出資料中心。算力與電力的瓶頸，Amazon 執行長 Jassy 也談過，可參考[本站的 Jassy 訪談精讀]({{ site.baseurl }}{% post_url 2026-10-24-andy-jassy-a16z %})；Google 則試著把運算搬上太空，見[本站的 Project Suncatcher 報導]({{ site.baseurl }}{% post_url 2026-10-31-google-project-suncatcher %})。

據 The Verge 報導，OpenAI 的大舉採購正擠壓全球 RAM 供給；三星與 SK 海力士已和雲端業者及 OpenAI 的 Stargate 等計畫簽下長期合約，預留未來幾年大量 RAM 產出，這也是筆電、手機等產品變貴的原因。換句話說，主張 DRAM 該集中到雲端的人，本身就是大量採購 RAM 的一方。

## 這集訪談對讀者的意義在於重新思考算力的使用率

如果你正考慮買高記憶體的電腦來跑本機模型，Altman 的說法值得當作一個角度參考，但不必照單全收：本機推論的隱私、離線與延遲優勢，並不在他這番「全球分配」的算式裡。Altman 自己在節目中談到企業 AI 支出時也承認「我非常有偏見」（I'm very biased）。

本站認為，這集最值得帶走的是「使用率」這個視角：無論是公司的 GPU 預算還是個人的硬體，閒置的算力都是成本。本站建議，評估 AI 工具時，除了看模型多強，也想想你的運算資源有多少時間真正在工作。

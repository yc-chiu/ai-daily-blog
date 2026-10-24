---
layout: post
title: "Amazon 執行長 Jassy 上 a16z：他說今年投入約 2,200 億美元資本支出，仍接不住 AI 需求｜訪談精讀"
date: 2026-10-24 08:00:00 +0800
summary: "Amazon 執行長 Andy Jassy 上《a16z Podcast》表示，Amazon 今年預計投入約 2,200 億美元資本支出，仍有相當多 AI 需求接不住，2026 年算力已賣光。他也說明為何認為美國非蓋資料中心不可、自研晶片如何壓低推論成本、為何投資 Anthropic 與 OpenAI，並預測 AI 會讓團隊變小、資安反應必須以分鐘計。"
cover: /assets/images/posts/2026-10-24-andy-jassy-a16z/cover.png
cover_alt: "從空中俯瞰美國奧勒岡州 AWS us-west-2 區域的資料中心園區，右側是數棟大型機房與一棟興建中的建築；左側深藍底上以橘色大字寫著 Amazon，標題為『執行長 Jassy：為何重押 AI 基礎建設？』，並標註 a16z 專訪。"
cover_credit: "照片：Tedder / Wikimedia Commons，CC BY-SA 4.0（裁切並加上漸層，衍生作品依 CC BY-SA 4.0 釋出）"
tags:
  - "訪談精讀"
  - "Amazon"
  - "AWS"
  - "AI 基礎建設"
sources:
  - name: "a16z（YouTube）：Amazon CEO Andy Jassy on the Infrastructure the AI Era Needs"
    url: "https://www.youtube.com/watch?v=-YMMRQ1qscI"
  - name: "a16z Podcast（Simplecast）：Amazon CEO Andy Jassy on the $220 Billion AI Buildout"
    url: "https://a16z.simplecast.com/episodes/amazon-ceo-220-billion-still-cant-meet-ai-demand-3QzhqLQK"
---

這次「訪談精讀」的主角是 Amazon 執行長 Andy Jassy。他在 2021 年正式接任執行長，訪談中也回顧了當年 Amazon 創立 AWS 的經驗。這集是《a16z Podcast》，依影片說明，與他對談的是 a16z 共同創辦人 Ben Horowitz 和主持人 Erik Torenberg。YouTube 版於台灣時間 10 月 23 日 23:40 上架，長約 1 小時。

這集值得看，是因為 AI 基礎建設要花多少錢、蓋得夠不夠，現在是整個科技業和金融市場最關心的問題，而 Jassy 掌管的 Amazon 旗下就有 AWS 這個雲端事業。他不只給數字，也說明 Amazon 是怎麼判斷需求、怎麼取捨的。

以下依 YouTube 音檔自行轉錄整理，引述片段都已對照原音。中文為本站翻譯，引號內為原句，時間碼以 YouTube 版為準。

<div style="position:relative;width:100%;aspect-ratio:16/9;"><iframe src="https://www.youtube-nocookie.com/embed/-YMMRQ1qscI" title="a16z：Amazon CEO Andy Jassy on the Infrastructure the AI Era Needs" style="position:absolute;inset:0;width:100%;height:100%;border:0;" loading="lazy" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe></div>

## Jassy 在這集訪談提出了五個核心觀點

### 一、Jassy 認為就算花 2,200 億美元，Amazon 還是接不住所有 AI 需求

Jassy 說，Amazon 已表示 2026 年預計投入約 2,200 億美元的資本支出。他回憶 15 年前的主管早餐會上，大家還不敢相信電信公司一年花 500 億美元，如今這些數字「令人難以置信」。但他接著說：

> 「即使今年花了 2,200 億美元的資本支出，我們還是有相當多的需求接不住。」
>
> "even spending 220 billion dollars in CapEx this year, we're leaving a meaningful amount of demand on the table" — [13:54](https://www.youtube.com/watch?v=-YMMRQ1qscI&t=834s)

他敢這樣投資，理由是 AWS 對客戶需求有很好的能見度。他解釋，資料中心要提前大約兩年投資，伺服器與網路設備則只要提前幾個月。他也說，AWS 的 AI 業務在生成式 AI 浪潮的頭三年，年化營收已超過 250 億美元，成長速度是 AWS 草創期的：

> 「快了好幾百倍。」
>
> "several hundred times faster" — [13:13](https://www.youtube.com/watch?v=-YMMRQ1qscI&t=793s)

### 二、Jassy 說未來幾年的算力幾乎已經被訂光

被問到算力短缺時，Jassy 描述的景況是：

> 「2026 年顯然已經賣光了。」
>
> "26 is obviously at this point sold out" — [25:05](https://www.youtube.com/watch?v=-YMMRQ1qscI&t=1505s)

他接著說 2027 年大致賣光，2028 年也有一大塊已經賣出（[25:09](https://www.youtube.com/watch?v=-YMMRQ1qscI&t=1509s)）。依他的說法，Amazon 一定會保留一部分給隨需使用的客戶，而且不會為了把算力賣給出價更高的 AI 實驗室，去排擠長期在 AWS 上運作核心業務的客戶。他也不認為短缺會很快結束：

> 「我真希望能告訴你，供應限制只是 2027 年的問題。我想接下來好幾年，我們都會在不同零組件上看到它。」
>
> "I wish I could tell you that I thought that the supply constraints would be just a 2027 issue. I think we'll see them in different components for several years." — [27:30](https://www.youtube.com/watch?v=-YMMRQ1qscI&t=1650s)

### 三、Jassy 主張美國不能不蓋資料中心

談到美國社會對資料中心的反彈，Jassy 先把 AI 定位為：

> 「我們這個時代最大的技術轉型。」
>
> "AI is the biggest technology transformation of our time" — [17:08](https://www.youtube.com/watch?v=-YMMRQ1qscI&t=1028s)

他把這波建設比作 1950 年代美國興建高速公路與橋梁，並說：

> 「美國尤其承擔不起不蓋資料中心的後果。」
>
> "the US specifically cannot afford not to build data centers" — [17:42](https://www.youtube.com/watch?v=-YMMRQ1qscI&t=1062s)

他的理由是，否則像中國這樣的國家就會主導 AI 的領導地位與規範。他也認為外界有些說法介於迷思與不實之間，舉例說，依他的說法高爾夫球場的用水量是 Amazon 所有資料中心的 200 倍（[18:36](https://www.youtube.com/watch?v=-YMMRQ1qscI&t=1116s)）。不過他也承認業界可以做得更好，必須和當地社區建立公私協力的關係。

### 四、Jassy 認為推論成本還太高，而自研晶片是把成本壓下來的關鍵

主持人提到 Amazon 在 2015 年收購 Annapurna Labs。Jassy 說明，當初收購最初是為了把虛擬化、網路等工作從伺服器卸載出去。之後團隊做出 Graviton 處理器，他說前 1,000 大 EC2 客戶中有 99% 在使用，價格效能比其他 x86 處理器好約 40%（[31:19](https://www.youtube.com/watch?v=-YMMRQ1qscI&t=1879s)）。這些都是他本人的說法。他指出，推論成本這幾年雖然降了不少，但要讓 AI 普及到所有應用還是太貴（[32:50](https://www.youtube.com/watch?v=-YMMRQ1qscI&t=1970s)），而 Amazon 的晶片業務正是降低推論成本的重要一環。

至於投資 Anthropic 與 OpenAI，他說看重的是團隊、技術，以及雙方的合作關係。他提到 Anthropic 長期在 Trainium 晶片上開發，並說：

> 「我認為客戶在 Bedrock 上執行 Anthropic 最成功。」
>
> "I think customers are most successful running Anthropic in Bedrock" — [35:43](https://www.youtube.com/watch?v=-YMMRQ1qscI&t=2143s)

這是 Jassy 對自家服務的說法。OpenAI 方面，他說很多 AWS 客戶早就想用，經過數個月的協商，如今 OpenAI 模型也能在 Bedrock 上執行。

### 五、Jassy 認為 AI 會讓團隊變小，資安反應也必須快到以分鐘計算

主持人在節目中提到，Bedrock 團隊用 6 名工程師、76 天重寫了推論引擎。Jassy 說這個故事讓公司內部大開眼界，並預測：

> 「我認為團隊會比現在小得多。」
>
> "I think the teams will be, um, much smaller than they are right now" — [40:42](https://www.youtube.com/watch?v=-YMMRQ1qscI&t=2442s)

依他的描述，未來的成員要能跨職能工作，因為模型能先幫各職能完成大部分工作。他也認為，業界對 AI 風險的討論太集中在科幻情境，反而忽略了：

> 「更迫切的近期風險，主要就在資安。」
>
> "the more immediate term risks, which are really around cybersecurity" — [43:00](https://www.youtube.com/watch?v=-YMMRQ1qscI&t=2580s)

他的理由是，模型找到的漏洞遠多於過去。他說，應用程式面對迫在眉睫的威脅，必須在幾分鐘內做出回應（[43:20](https://www.youtube.com/watch?v=-YMMRQ1qscI&t=2600s)），沒有改寫成能讓代理更新的系統，就沒有機會。

## Jassy 看見的趨勢是企業的主力工作負載還沒真正用上 AI

Jassy 用「槓鈴」形容現在的 AI 需求：一端是大量消耗算力的 AI 實驗室與少數爆紅應用，另一端是企業用 AI 自動化客服、防詐等工作來節省成本。他說，中間的企業既有正式工作負載，絕大多數還沒有全面用上推論，而他認為這會是未來最大的一塊市場（[22:22](https://www.youtube.com/watch?v=-YMMRQ1qscI&t=1342s)）。這也是他一再強調必須降低推論成本的原因。

## Jassy 對未來的判斷是 AI 會改寫每一種顧客體驗，但取代不了思考

Jassy 認為，我們身處 AI、機器人與太空開發三大轉型同時發生的時代，每一種顧客體驗都會被推論與 AI 重新打造。給 18 歲年輕人的建議，他說自己告訴孩子的是：

> 「你逃避不了它。」
>
> "you can't run away from it" — [54:16](https://www.youtube.com/watch?v=-YMMRQ1qscI&t=3256s)

但他也說，把各種線索拼成策略、計畫或新產品，

> 「我不認為 AI 會替大多數人、在大多數時候做到這件事。」
>
> "I don't think AI is going to do that for most people most of the time." — [56:04](https://www.youtube.com/watch?v=-YMMRQ1qscI&t=3364s)

## 本站認為這集訪談給讀者三個值得帶走的提醒

- **關注基礎建設的讀者**：Jassy 的訊號很清楚，在他看來，算力、電力與記憶體的瓶頸會持續好幾年。本站認為，與其只看資本支出的數字，更值得追蹤的是「已經賣出多少產能」這類需求面的說法。
- **企業決策者**：他把企業既有的核心系統視為最大的未開發市場，而推論成本是門檻。本站認為，現在就盤點哪些流程等成本再降一階就能導入，會比等到價格降下來才開始規劃更有利。
- **工程師與學生**：團隊變小、跨職能、資安更新以分鐘計，是他對工作型態的預測。本站認為，學會和 AI 協作是基本功，但能把零散資訊組成判斷的思考能力，才是他眼中不會被取代的部分。

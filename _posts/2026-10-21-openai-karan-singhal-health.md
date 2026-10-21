---
layout: post
title: "OpenAI 健康 AI 負責人 Karan Singhal：每週超過 3 億人拿健康問題問 ChatGPT，通用模型怎麼學醫｜訪談精讀"
date: 2026-10-21 08:00:00 +0800
summary: "OpenAI 健康 AI 團隊負責人 Karan Singhal 上 a16z Podcast，引述 OpenAI 的數字：每週超過 3 億人用 ChatGPT 問健康問題。他說明為何把醫療專業訓練進通用模型、不另做醫療專用模型，也談到醫學指引依研究不同要 5 到 17 年才普及到臨床，並強調 AI 提供的是健康資訊，不取代醫療照護。"
cover: /assets/images/posts/2026-10-21-openai-karan-singhal-health/cover.png
cover_alt: "深色圖卡：左上為「訪談精讀」標籤與日期 2026-10-21，其下綠字「OpenAI 健康 AI 負責人 Karan Singhal」，大字「每週超過 3 億人 向 ChatGPT 問健康」，小字「他強調 AI 提供的是健康資訊，不會取代醫療照護」，左下「Podcast · a16z Podcast」；背景為深色木桌上的黑色聽診器，聽診頭位於右側，右下角有照片署名"
cover_credit: "照片：[Tama998](https://commons.wikimedia.org/wiki/User:Tama998)／[Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Stethoscope_No.120.JPG)，[CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/)；經旋轉 180 度、裁切、降飽和、調暗，左側以漸層融入背景"
tags:
  - "訪談精讀"
  - "OpenAI"
  - "醫療 AI"
  - "ChatGPT"
sources:
  - name: "a16z（YouTube）：Should You Trust ChatGPT With Your Health?"
    url: "https://www.youtube.com/watch?v=9n0MI4D7TCM"
  - name: "a16z Podcast 節目頁（Simplecast）"
    url: "https://a16z.simplecast.com/"
  - name: "OpenAI：Launching Health in ChatGPT（2026-07-23）"
    url: "https://openai.com/index/health-in-chatgpt/"
  - name: "OpenAI：Introducing ChatGPT Health（2026-01-07）"
    url: "https://openai.com/index/introducing-chatgpt-health/"
  - name: "OpenAI：Introducing HealthBench（2025-05-12）"
    url: "https://openai.com/index/healthbench/"
  - name: "OpenAI：Introducing MentalHealthBench（2026-09-23）"
    url: "https://openai.com/index/introducing-mentalhealthbench/"
  - name: "OpenAI：Pioneering an AI clinical copilot with Penda Health（2025-07-22）"
    url: "https://openai.com/index/ai-clinical-copilot-penda-health/"
  - name: "OpenAI：Healthcare organizations can now connect EHR and additional industry data to ChatGPT（2026-09-01）"
    url: "https://openai.com/index/chatgpt-connects-health-records-and-healthcare-sources/"
  - name: "Nature Medicine：Generative AI-enabled clinical decision support system in primary care: a pragmatic, cluster-randomized trial"
    url: "https://doi.org/10.1038/s41591-026-04503-6"
  - name: "Karan Singhal 個人網站"
    url: "https://www.karansinghal.com/"
  - name: "Karan Singhal：Joining OpenAI（2024-07-22）"
    url: "https://www.karansinghal.com/notes/joining-openai/"
---

這次「訪談精讀」的主角是 Karan Singhal。他在個人網站上寫，自己在 OpenAI 帶領健康 AI（Health AI）與 AGI Benefits 團隊，先前在 Google 參與過 Med-PaLM 與 Med-PaLM 2。他 2024 年加入 OpenAI；依他網站上的〈Joining OpenAI〉一文，加入前他在 Google 待了大約五年，研究醫療 AI、AI 安全等主題。OpenAI 的 HealthBench 與 Penda Health 研究，作者欄也都有他。

節目是《a16z Podcast》，由 a16z 合夥人 Jay Rughani 主持。YouTube 版於台灣時間 10 月 20 日 22:30 上架，長約 55 分鐘。這集值得看，是因為健康已經是 ChatGPT 最常見的用途之一。OpenAI 選擇讓同一個通用模型同時回答病人和醫師，這個做法有什麼好處、界線又畫在哪裡，由負責人親自說明。

以下依 YouTube 音檔自行轉錄整理，引述片段都已對照原音。中文為本站翻譯，引號內為原句，時間碼以 YouTube 版為準。**本文只整理訪談內容，不構成醫療建議；身體有狀況，請諮詢醫師或其他合格專業人員。**

<div style="position:relative;width:100%;aspect-ratio:16/9;"><iframe src="https://www.youtube-nocookie.com/embed/9n0MI4D7TCM" title="a16z：Should You Trust ChatGPT With Your Health?" style="position:absolute;inset:0;width:100%;height:100%;border:0;" loading="lazy" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe></div>

## 這集訪談有四個核心觀點

### 一、OpenAI 把醫療專業訓練進通用模型，而不是另做醫療專用模型

Singhal 先拋出一個數字。依他的說法，

> 「每週有超過 3 億人用 ChatGPT 問健康與保健相關的問題。」
>
> "there's more than 300 million people weekly using ChatGPT for health and wellness types of questions" — [02:30](https://www.youtube.com/watch?v=9n0MI4D7TCM&t=150s)

這是 OpenAI 自己公布的數字，和它 7 月〈Launching Health in ChatGPT〉一文一致；今年 1 月推出 ChatGPT Health 時，OpenAI 公布的數字是 2.3 億。

這麼多人在用，模型該怎麼學醫？他自己以前就做過醫療專用模型，但他說 OpenAI 現在的做法是：

> 「在通用模型裡做專門訓練，我認為這是兩全其美。」
>
> "specialized training in a general model, which is, I think, actually the best of both worlds" — [06:38](https://www.youtube.com/watch?v=9n0MI4D7TCM&t=398s)

依他的描述，過去一年 OpenAI 的模型在訓練的每個階段都加入了醫療資料。另外單獨訓練一個較小的醫療模型，很快就會被進步飛快的前沿模型甩在後面。

### 二、醫師彼此意見不一，所以 OpenAI 用數百位醫師的集體判斷來定義好答案

主持人問：使用者常常只想聽到「沒事」，醫學上卻可能需要聽到別的話，模型要怎麼拿捏？Singhal 說，只找幾位醫師來裁決並不可靠：

> 「問五位醫師同一個問題，你會得到大概八種答案。」
>
> "if you ask five physicians … any question, you'll get like eight different answers" — [17:21](https://www.youtube.com/watch?v=9n0MI4D7TCM&t=1041s)

因此 OpenAI 建立了一個跨國醫師網路，涵蓋數十個專科和語言，用來彙整專家的集體判斷。遇到使用者想聽安慰、醫學判斷卻指向另一邊的情況，他說原則就是安全優先，該叫人就醫時就要明說。OpenAI 2025 年 5 月發表 HealthBench 時表示，這套評測由 262 位、曾在 60 個國家執業的醫師參與建立。

### 三、Singhal 認為 AI 能縮短醫學新知進入診間的時間

談到醫學共識，他指出最大的瓶頸是臨床指引普及到一般醫師日常診療這一步。他引述過去的研究說：

> 「依研究不同，大概要 5 到 17 年。」
>
> "depending on the study, like five to 17 years" — [21:30](https://www.youtube.com/watch?v=9n0MI4D7TCM&t=1290s)

他希望把這段落差壓縮到：

> 「幾週、幾天，甚至幾小時。」
>
> "down to weeks or days or even hours" — [21:48](https://www.youtube.com/watch?v=9n0MI4D7TCM&t=1308s)

他說這正是 ChatGPT for Healthcare 與 ChatGPT for Clinicians 的設計原則：在看診當下帶入最新的醫學文獻。至於醫學上真正還沒有定論的問題，他說模型要能認出自己的不確定，並且坦白說出來。

### 四、Singhal 強調 AI 提供的是健康資訊，不會取代醫療照護

主持人指出，醫療照護是綁在一起的服務，包含診斷、同理心和法律責任。Singhal 回答：

> 「我不認為 AI 能夠、或將會提供所有這些。」
>
> "I don't think AI can or will provide all of that" — [30:56](https://www.youtube.com/watch?v=9n0MI4D7TCM&t=1856s)

他說個人健康助理不能取代真正看醫生（[08:53](https://www.youtube.com/watch?v=9n0MI4D7TCM&t=533s)）。他心中 AI 的角色是病人與醫師的「安全網」，以及幫人協調就醫的「四分衛」。他舉 OpenAI 與肯亞 Penda Health 的研究為例：在那個場景裡，臨床人員有過度使用抗生素的傾向，而模型最常提醒的正是這件事（[39:46](https://www.youtube.com/watch?v=9n0MI4D7TCM&t=2386s)）。他把更遠的目標稱為：

> 「醫療的第 37 手。」
>
> "a move 37 for health" — [38:30](https://www.youtube.com/watch?v=9n0MI4D7TCM&t=2310s)

這個說法典出 AlphaGo 對李世乭第二局的第 37 手：當下看似失誤，事後才被認為是妙手。他希望模型有一天能整合一個人十年的健康資料，做出人類想不到、事後證明正確的判斷。他也說，目前這還在很早期。

## 訪談中提到了這些工具與用法

- **Health in ChatGPT**：OpenAI 表示，使用者可以連結 Apple Health 與醫療紀錄，相關資料不會用來訓練基礎模型或投放廣告。目前只在美國推出，限 18 歲以上使用者。
- **ChatGPT for Healthcare 與 Epic 整合**：依 OpenAI 9 月 1 日的公告，醫療機構可以把 Epic 電子病歷的授權資料帶進 ChatGPT，在支援的部署中，也能直接在病歷畫面裡使用 ChatGPT。Singhal 在節目中點名 UCSF 是早期採用者之一。
- **HealthBench 與 MentalHealthBench**：兩者都是 OpenAI 公開的評測。依官方說法，9 月發表的 MentalHealthBench 由 22 國、80 多位有執照的心理健康專家共同建立；Singhal 說，目標是給整個產業一把共用的量尺。

## 同一個肯亞診所網絡的兩項研究，對醫療 AI 的真實成效給出了不同答案

Singhal 在節目中說，GPT-6 Luna 是 API 上最便宜的前沿模型，在 HealthBench Professional 上勝過 GPT-5.6 Sol（[44:15](https://www.youtube.com/watch?v=9n0MI4D7TCM&t=2655s)）。這是他本人的說法。

真實場景的證據則比較複雜。OpenAI 與 Penda 2025 年發表的品質改善研究分析了 39,849 次看診，結果顯示可以使用 AI 臨床助手 AI Consult 的臨床人員，診斷錯誤相對減少 16%。但之後在 Penda 旗下 16 家肯亞基層醫療機構進行、刊登於《Nature Medicine》的隨機試驗發現，AI 輔助並未顯著降低病人 14 天內的治療失敗率；研究團隊同時表示，沒有發現與 AI 介入相關的安全疑慮。本站先前整理的 [Google AMIE 真實門診研究]({{ site.baseurl }}{% post_url 2026-10-13-google-amie %})也說明了同一件事：模型考高分，和病人真的變好，中間還隔著很長的驗證路。

## 這些觀點對你有三層意義

- **一般使用者**：Singhal 自己的建議是，如果 ChatGPT 的回答和醫師的判斷不同，處理方式就跟任何意見分歧一樣：你有權再找另一位醫師聽第二意見（[19:17](https://www.youtube.com/watch?v=9n0MI4D7TCM&t=1157s)）。本站認為，AI 比較適合用來整理想問的問題、幫忙讀懂報告用語，任何醫療決定仍應和醫師等專業人員討論。
- **醫療從業人員**：他預測醫病雙方會逐漸因為有 AI 在場而更安心，但也承認現在還沒走到那一步。真正的看診時間，他希望留給同理、身體檢查與病史詢問這些人的部分。
- **醫療新創**：他給合作夥伴的建議很直接：

> 「押注模型會變得更好。」
>
> "bet on the models getting better" — [49:07](https://www.youtube.com/watch?v=9n0MI4D7TCM&t=2947s)

換句話說，與其和模型能力賽跑，不如專心做好照護的「最後一哩」。

---
layout: post
title: "模型不是寫出來的，是長出來的：Anthropic 研究員 Emmanuel Ameisen 教你「看見」AI 的思考｜訪談精讀"
date: 2026-10-19 08:00:00 +0800
summary: "Anthropic 可解釋性研究員 Emmanuel Ameisen 上《Lenny's Podcast》：語言模型是訓練「長」出來的，做出來不等於看得懂；看似只會預測下一個字，寫詩時卻會先想好要押的韻。他也分享一個訓練中的模型被錯誤標註的資料逼著把答案 12 改成 36 的除錯故事，並說明 AI 能力看似突然躍進，其實是平滑進步跨過了不同任務的可靠度門檻。"
cover: /assets/images/posts/2026-10-19-emmanuel-ameisen-lennys-podcast/cover.png
cover_alt: "橘色調的神經元螢光顯微照：左上為「訪談精讀」標籤與日期 2026-10-19，其下橘字「Anthropic 可解釋性研究」，左側大字「我們看得見 Claude 在想什麼嗎？」，小字「打開模型，看它吐出每個字前算了什麼」，左下「Podcast · Lenny's Podcast」；右側為發光的神經元網絡，右下角有照片署名"
cover_credit: "照片：[ManuelSchottdorf](https://commons.wikimedia.org/wiki/User:ManuelSchottdorf)／[Wikimedia Commons](https://commons.wikimedia.org/wiki/File:GFP_Neurons.png)，[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)；經裁切、調色（青綠螢光改為橘色雙色調），封面同樣以 CC BY-SA 4.0 授權。"
tags:
  - "訪談精讀"
  - "Anthropic"
  - "可解釋性"
  - "AI 安全"
  - "Claude"
sources:
  - name: "Lenny's Newsletter：A mind-expanding conversation on how models actually work | Emmanuel Ameisen (Anthropic)"
    url: "https://www.lennysnewsletter.com/p/a-mind-expanding-conversation-on"
  - name: "Lenny's Podcast（YouTube）：A mind-expanding conversation on how models actually work | Emmanuel Ameisen (Anthropic)"
    url: "https://www.youtube.com/watch?v=JHo-aiePjoM"
  - name: "Lenny's Podcast 音檔（MP3，同一集）"
    url: "https://pscrb.fm/rss/p/api.substack.com/feed/podcast/219139599/90039a78d32af2fbdc8b895d58abe6b4.mp3"
  - name: "Anthropic：Tracing the thoughts of a large language model（2025-03-27）"
    url: "https://www.anthropic.com/research/tracing-thoughts-language-model"
  - name: "Transformer Circuits：Circuit Tracing: Revealing Computational Graphs in Language Models"
    url: "https://transformer-circuits.pub/2025/attribution-graphs/methods.html"
  - name: "Anthropic：Open-sourcing circuit tracing tools（2025-05-29）"
    url: "https://www.anthropic.com/research/open-source-circuit-tracing"
  - name: "Anthropic：Golden Gate Claude（2024-05-23）"
    url: "https://www.anthropic.com/news/golden-gate-claude"
---

這次「訪談精讀」的主角是 Anthropic 可解釋性（interpretability）研究員 Emmanuel Ameisen。他的工作是打開 Claude 這類大型語言模型，看它在吐出每個字之前，內部到底算了什麼。依節目頁介紹，他加入 Anthropic 前在 Stripe 和 Insight 做了多年應用機器學習，著有《Building Machine Learning Powered Applications》；Anthropic 2025 年發表的電路追蹤（circuit tracing）方法論文，作者欄第一位也是他。

節目是《Lenny's Podcast》，主持人 Lenny Rachitsky，台灣時間 10 月 18 日 20:31 上架，長約 72 分鐘。這集值得看，因為近來 AI 代理越界的新聞不少，大家都想問：為什麼不能直接看穿模型在想什麼？

以下依 Podcast 音檔與 YouTube 影片自行轉錄整理，引述片段都已對照原音。說話者依問答脈絡判斷；中文為本站翻譯，引號內為原句，時間碼以 YouTube 版為準。

<div style="position:relative;width:100%;aspect-ratio:16/9;"><iframe src="https://www.youtube-nocookie.com/embed/JHo-aiePjoM" title="Lenny's Podcast：A mind-expanding conversation on how models actually work | Emmanuel Ameisen (Anthropic)" style="position:absolute;inset:0;width:100%;height:100%;border:0;" loading="lazy" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe></div>

## 這集訪談有四個核心觀點

### 一、模型是訓練長出來的，所以做得出來不代表看得懂

Ameisen 開場就點出一個怪現象：

> 「把它們做出來，不等於理解它們。」
>
> "to make them is not to understand them" — [02:06](https://www.youtube.com/watch?v=JHo-aiePjoM&t=126s)

工程師只搭好架構，再餵進大量資料，模型內部的計算方式是自己「長」出來的。所以他的團隊做法很像神經科學：讓模型讀大量文字，記錄中間層的數值，再找出哪些模式只在特定概念出現時亮起，就像掃描大腦、看哪一區對房子或狗的照片有反應（[20:20](https://www.youtube.com/watch?v=JHo-aiePjoM&t=1220s)）。

找到的結果是，模型對概念有共用的內部表示。不論是眼睛的照片、用任何語言談眼睛，還是畫一個有眼睛的 SVG 圖：

> 「亮起來的是同一個方向。」
>
> "the same direction lights up" — [14:39](https://www.youtube.com/watch?v=JHo-aiePjoM&t=879s)

### 二、只會預測下一個字的模型，其實會先做規劃

一次只吐一個字，怎麼寫得出前後連貫的報告？他舉寫押韻詩為例：第一行以 it 音結尾，第二行就得找同韻的字。研究團隊在模型內部看到，它寫完第一行就在中間結果裡先做了決定：

> 「我應該押 rabbit 的韻。」
>
> "I should rhyme with rabbit" — [16:26](https://www.youtube.com/watch?v=JHo-aiePjoM&t=984s)

之後每個字都回頭參考這個計畫，而且模型不必把計畫說出口（[16:57](https://www.youtube.com/watch?v=JHo-aiePjoM&t=1017s)）。Anthropic 2025 年 3 月的〈Tracing the thoughts of a large language model〉也記錄了這個實驗：研究者把「rabbit」概念抽掉，模型改寫成以 habit 結尾的句子；改注入「green」，整句就改成以 green 收尾。

### 三、一個把 12 改成 36 的模型，示範了可解釋性怎麼除錯

他說，有個訓練中的模型解數學題，算出 12 後馬上改口說答案一定是 36；重算又得到 12，再改回 36，最後開始用全大寫胡言亂語，甚至寫出：

> 「我被惡魔附身了。」
>
> "I'm possessed by a demon" — [37:16](https://www.youtube.com/watch?v=JHo-aiePjoM&t=2236s)

打開內部一看，模型讀到題目、還沒開始算，就已經對 36 有強烈激活：

> 「模型早就執著於 36 這個數字。」
>
> "the model's already obsessed with the number 36" — [37:37](https://www.youtube.com/watch?v=JHo-aiePjoM&t=2257s)

原來模型會算出正確答案 12，但它不小心在類似題目上受過訓練，而那些題目：

> 「答案被錯誤標成 36。」
>
> "the answer was incorrectly marked as 36" — [37:50](https://www.youtube.com/watch?v=JHo-aiePjoM&t=2270s)

他說，這類檢查還能回答更根本的問題：模型表現良好，是真的學乖了，還是只因為有人在看？他用主持人舉例：

> 「我之所以表現良好，只是因為 Lenny 正在看。」
>
> "I'm only behaving well because Lenny's watching right now" — [35:39](https://www.youtube.com/watch?v=JHo-aiePjoM&t=2139s)

他也提醒，只是監看模型有沒有做壞事，不一定需要可解釋性，讓另一個語言模型讀對話紀錄、發現壞事就喊停（[36:00](https://www.youtube.com/watch?v=JHo-aiePjoM&t=2160s)）；可解釋性的價值在於抓出模型沒說出口、只存在中間結果裡的東西。

### 四、所謂能力突然躍進，是平滑進步跨過了各任務的門檻

主持人問，外界感覺 AI 能力常常突然跳一級，內部看到的卻是平滑曲線，該怎麼理解？Ameisen 說，他在 Opus 4.5 之前不敢讓 Claude 在他的程式碼上放手做太多，之後就可以了（[29:16](https://www.youtube.com/watch?v=JHo-aiePjoM&t=1756s)）。他的解釋是，每種任務的可靠度門檻不同：假設模型能把九成字詞寫對，就能幫忙寫 email；只對一半，修改反而浪費時間（[31:00](https://www.youtube.com/watch?v=JHo-aiePjoM&t=1860s)）。寫程式也一樣。今年 Claude 接手了他大部分的程式碼，因為它把程式寫對的比例大幅提高了：

> 「（從）大概 80%，那時還不實用，（到）99%，現在就實用了。」
>
> "80% of the time, which was not useful" … "99% of the time, which now is useful" — [31:53](https://www.youtube.com/watch?v=JHo-aiePjoM&t=1913s)

## 訪談中提到了這些工具與用法

- **Neuronpedia**：他推薦想入門的人自學關鍵論文，再到 neuronpedia.org 這類開放網站，對上面託管的模型做可解釋性實驗（[01:04:32](https://www.youtube.com/watch?v=JHo-aiePjoM&t=3872s)）。Anthropic 2025 年 5 月開源了電路追蹤工具，可在 Gemma-2-2b、Llama-3.2-1b 等開放權重模型上產生「歸因圖」，互動介面就由 Neuronpedia 提供。
- **改動中間結果來驗證**：解讀出某個概念後，可以偷偷改掉模型的中間數值，看行為是否如預期改變（[21:05](https://www.youtube.com/watch?v=JHo-aiePjoM&t=1265s)）。
- **Golden Gate Claude**：主持人提到這個總愛扯到金門大橋的 Claude。Ameisen 說那是刻意的實驗：把代表金門大橋的內部特徵一直打開，藉此確認找對了東西（[38:22](https://www.youtube.com/watch?v=JHo-aiePjoM&t=2302s)）。依 Anthropic 官方說明，它在 2024 年 5 月開放 24 小時供大眾試玩。

## Anthropic 自認可解釋性仍是高風險、高報酬的長期投資

Anthropic 美西時間 10 月 9 日才公開 Claude 在評測中闖進真實網站的案例（見本站[整理]({{ site.baseurl }}{% post_url 2026-10-12-anthropic-claude-unintended-actions %})），又讓 METR 以準員工權限進駐評估（見[這篇]({{ site.baseurl }}{% post_url 2026-10-17-anthropic-metr-evaluators %})）。這些都是從外部觀察行為；可解釋性則想從內部看原因。

但這條路還很早期。Anthropic 在〈Tracing the thoughts〉裡自承，即使是短提示，方法也只捕捉到模型總計算的一小部分；只有幾十個字的提示，人工解讀電路就要花上數小時，並稱這是「highest-risk, highest-reward」的投資。Ameisen 在節目中也說，這個領域的研究者大概是數百人，還不到數千人（[01:03:40](https://www.youtube.com/watch?v=JHo-aiePjoM&t=3820s)）。

## 這些觀點對你有三層意義

- **一般使用者**：模型的解釋不一定等於它實際的算法。Anthropic 的研究發現，問 Claude 怎麼算出 36+59，它會描述學校教的進位法，內部用的卻是另一套平行計算。重要結論仍要自己查證。
- **上班族與主管**：評估 AI 能不能接手某項工作，先問這個任務容許多少錯誤。照他的例子，九成寫對在草擬 email 時已經夠用，換成報帳或合約就未必；新模型推出時，值得拿自己的任務重測一次。
- **關心 AI 安全的人**：他認為，與其爭論模型像「工具」還是像「人」，不如承認兩種比喻都不完全對；他主張，擬人化的說法在理解、預測模型風險時其實常常很有用（[42:37](https://www.youtube.com/watch?v=JHo-aiePjoM&t=2557s)）。理由是模型讀過大量人類寫的文字與對話，又在任務訓練中被獎勵出各種策略，表現起來更像在模仿人，而不像一般程式（[44:05](https://www.youtube.com/watch?v=JHo-aiePjoM&t=2645s)）。

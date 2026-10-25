---
layout: post
title: "Block 發表全雙工語音模型 Dessa：能邊聽邊說、會插話附和，官方說只用人類對話訓練"
date: 2026-10-25 08:00:00 +0800
summary: "Square 與 Cash App 的母公司 Block 發表全雙工語音模型 Dessa。Block 說，它能同時聽和說、適時插話附和，而且只用人類對話從零訓練，可在 MacBook Pro M4 Max 或更高階機種上本機執行；官方表示，目前先讓一小群 AI 安全研究者搶先試用。本文說明全雙工是什麼、為何重要，以及媒體試聽後的評價。"
cover: /assets/images/posts/2026-10-25-block-dessa/cover.png
cover_alt: "Block 共同創辦人 Jack Dorsey 在麥克風前的側面照，位於畫面右側；左側深色底上有「Block 新語音 AI Dessa」大字、「會插話、會附和，邊聽邊說」與「全雙工模型：你說話時，它也在聽」，右下角有照片署名"
cover_credit: "照片：[Senator Mark Warner](https://www.flickr.com/photos/senatormarkwarner/44538272181/)／[Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Jack_Dorsey_in_Washington_D.C._-_2018_(MRW_4445)_(44538272181).jpg)，[CC BY 2.0](https://creativecommons.org/licenses/by/2.0/)；經裁切、調暗，左側以漸層融入背景"
tags:
  - "Block"
  - "Dessa"
  - "語音 AI"
  - "AI 安全"
sources:
  - name: "Block：Dessa - the Conversation Model trained only on speech"
    url: "https://block.xyz/dessa"
  - name: "TechCrunch：Block's new voice model sounds eerily human（Ivan Mehta，2026-10-24）"
    url: "https://techcrunch.com/2026/10/24/blocks-new-voice-model-sounds-eerily-human/"
  - name: "The Verge：Jack Dorsey's Block made an AI model that talks to you like an awkward new friend（Jay Peters，2026-10-23）"
    url: "https://www.theverge.com/ai-artificial-intelligence/1017906/jack-dorsey-block-dessa-ai-voice-speech"
---
Block 旗下的一個小型 AI 研究團隊發表了語音模型 Dessa。據 Block 說法，這是一個「語音進、語音出」的模型，訓練時完全只用人類對話，沒有用文字，也沒有用任何預訓練模型。Block 表示，這個團隊直接向 Block 共同創辦人 Jack Dorsey 報告。

> 「我們完全只用人類對話，從零開始訓練 Dessa。」
>
> "We trained Dessa from scratch on nothing but human conversation."（Block 官方網站）

## 全雙工代表 AI 可以像人一樣邊聽邊說，而不是輪流發言

現在多數語音助理採「輪流制」：你說完一句，它把語音轉成文字、想好答案，再念給你聽；你說話時它在等，它說話時你很難打斷。全雙工則像打電話，雙方的聲音可以同時進出，所以能被打斷、能搶話，也能在對方說話時回一聲「嗯」「對啊」表示在聽，這叫附和（back-channeling）。

> 「它是全雙工的，所以會像你一樣，同時聽和說。」
>
> "It’s full-duplex, so it listens and talks at the same time, like you do."（Block 官方網站）

Block 表示，Dessa 從真實對話中學會何時該插話、何時該附和，推論速度比即時還快，因此不會出現尷尬的等待；Block 也說，它可以在 MacBook Pro M4 Max 或更高階的機器上本機執行。Block 認為，先把語音轉成文字，會丟掉語氣、嘆氣、笑聲與哽咽等資訊，這正是許多語音 AI 聽起來生硬又惱人的原因。據 Block 說法，Dessa 只用一套 NVIDIA GB200 NVL72 就完成訓練。

想親耳聽聽全雙工的效果，可以到 Block 官網試聽這幾段錄音：

- [「Talking about the release」](https://block.xyz/dessa)：據 Block 官網說明，Dessa 聽到好笑的地方，話說到一半就會笑出來；請它說大聲一點，它也會提高音量。
- [「Remembering a movie」](https://block.xyz/dessa)：據 Block 官網說明，對方一時想不起電影片名，Dessa 就幫忙把話接完。
- [「An anniversary surprise」](https://block.xyz/dessa)：據 Block 官網說明，Dessa 聽到驚喜時低聲驚呼「oh my god」，接著用聽起來像是含淚感激的語氣回應。

[到 Block 官網聽更多範例](https://block.xyz/dessa)

## 媒體實際聽過示範後，覺得很像真人但偶爾也有點怪

TechCrunch 形容，Dessa 帶著笑聲、停頓與哭腔，聽起來異常像人；但 TechCrunch 也指出，目前還不清楚這些情緒是否由某種標籤在背後操控。The Verge 則認為，Block 分享的對話有時有點尷尬、詭異，例如模型一開始把說話者誤認成名叫「Ronaldo」的人；不過 The Verge 也說，在 Dessa 與 OpenAI 的 GPT-Live-1 對話的示範中，Dessa 顯得比較自然。

## Block 把 AI 聽不出人類情緒，看成一個安全問題

Block 說，做 Dessa 有三個理由：好奇心、讓人類與 AI 更了解彼此，以及安全。在安全這點上，Block 是這樣說的：

> 「AI 的能力和自主性不斷增加，卻幾乎聽不見我們聲音裡的情緒。想像你正承受劇烈痛苦，語音 AI 卻毫無察覺、照樣講下去。這就是安全問題。」
>
> "AI keeps gaining power and independence, and it’s still nearly deaf to the emotion in our voices. Imagine being in serious pain while a voice AI has no idea and just keeps going. That’s the safety problem."（Block 官方網站）

Block 表示，目前會先讓一小群 AI 安全研究者搶先使用，找出團隊沒預料到的風險。TechCrunch 指出，Dessa 目前沒有公開開放，並推測這可能是為了測試語音代理可能欺騙對話另一端的人的情境。

## 本站認為，會聽語氣的 AI 更貼心，也更需要被提防

本站觀點：本站認為，Dessa 最值得注意的不是「像真人」，而是它示範了語音 AI 可以不經過文字、直接聽懂語氣。對使用者來說，這可能代表未來的客服或助理更能察覺你在生氣或難過，對話也不必再一問一答地卡頓。

但同一種能力也有另一面。一個能即時附和、聽起來帶著情緒的聲音，更容易讓人放下戒心。本站建議讀者，往後接到聲音再自然的來電，涉及金錢或個資時，仍要用其他管道確認對方身分。本站也認為，Block 先讓一小群安全研究者搶先試用，是較負責任的做法，值得其他語音 AI 業者參考。

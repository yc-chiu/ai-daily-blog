---
layout: post
title: "Tulsee Doshi 談 AI 產品管理：PM 不只寫需求｜Lenny 訪談精讀"
date: 2026-11-09 10:30:30 +0800
summary: "Google 前沿模型（含 Gemini）產品負責人 Tulsee Doshi 在 Lenny 訪談中，分享 PM 如何理解模型手感、親手建立評估，並以原型與資料支撐判斷。她也說明如何兼顧今天可用的功能與未來能力，讓產品隨模型進步保持彈性。"
cover: "/assets/images/posts/2026-11-09-tulsee-doshi-frontier-models/cover.png"
cover_alt: "深藍底配 Google Mountain View 園區招牌實景，左側標題為「前沿模型，如何變成產品」。"
cover_credit: "圖片來源：[brionv](https://commons.wikimedia.org/wiki/File:Google_Sign.jpg)／Wikimedia Commons，[CC BY-SA 2.0](https://creativecommons.org/licenses/by-sa/2.0/)；經裁切、漸層合成與加字，合成封面依 CC BY-SA 2.0 釋出。"
tags:
  - "訪談精讀"
  - "Gemini"
  - "Google"
  - "產品管理"
  - "AI 評估"
sources:
  - name: "Lenny's Podcast：Why PMs are suddenly valuable again｜Tulsee Doshi（YouTube 原集及英文自動字幕）"
    url: "https://www.youtube.com/watch?v=qGf2Yvan4Wg"
  - name: "Lenny Rachitsky：Why PMs are suddenly valuable again（原集介紹頁）"
    url: "https://www.lennysnewsletter.com/p/what-it-actually-takes-to-build-frontier"
---

當 AI 讓製作原型變得容易，產品經理還能提供什麼？Lenny Rachitsky 在這集 Lenny’s Podcast 訪問 Tulsee Doshi，從模型研發一路談到產品判斷。Lenny 介紹她是 Google 前沿模型的產品負責人，涵蓋 Gemini；她也談到生成式媒體、Gemma 與音訊模型。這集於 11 月 8 日（台北時間）發布，長 58 分 33 秒，重點不是哪個模型贏榜單，而是人如何定義值得做的產品、判斷模型好壞，並為持續變動的能力設計。

<div style="position:relative;width:100%;aspect-ratio:16/9;"><iframe src="https://www.youtube-nocookie.com/embed/qGf2Yvan4Wg" title="Lenny's Podcast：Why PMs are suddenly valuable again | Tulsee Doshi" style="position:absolute;inset:0;width:100%;height:100%;border:0;" loading="lazy" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe></div>

## Doshi 認為模型有目標，卻不會完全照規格長出來

Doshi 把模型開發比喻為石內卜的魔藥課：研究者放入材料、有意識地設定目標，但最後仍會有意外。她說：「模型並不可預測。」（the model isn't predictable.）[回看 03:16](https://www.youtube.com/watch?v=qGf2Yvan4Wg&t=196s)

她並非說訓練只能碰運氣。依她描述，研究團隊持續監看訓練、追蹤指標並介入；PM 則不能只管輸入，也要探索產出的模型在哪裡特別出色、哪些行為令人驚喜，再把這些能力轉成使用者真正想用的體驗。她談的模型「手感」，包括回應方式、角色個性與能力在實際情境中的表現，不只是評測分數。

## Doshi 認為製作變容易之後，品味與整合能力更重要

Lenny 問起 PM 價值回升，Doshi 回應：「品味現在真的很重要。」（taste is now really important.）[回看 20:40](https://www.youtube.com/watch?v=qGf2Yvan4Wg&t=1240s)

她認為，當什麼都能輕易做出來，能挑出有價值的訊號、找到解鎖好體驗的洞察，就成了獨特貢獻。另一項價值是把人集合起來、形成共識，將混亂整理成秩序；速度若沒有清楚方向，反而會製造混亂。

因此，她找的 PM 不是只會寫需求的人，而是每天玩模型、帶著自己的案例測試、願意看資料和建立評估的人，也要能持續追問團隊正在做什麼、為什麼做，而非假設路線圖永遠不變。

## Doshi 建議先用少量提示詞把好壞標準說清楚

對第一次寫 eval 的人，她的建議很直接：「先從五個提示詞開始就好。」（start with even just five prompts,）[回看 23:32](https://www.youtube.com/watch?v=qGf2Yvan4Wg&t=1412s)

Doshi 說，不必一開始就做大型基準測試；即使擴到約二十個提示詞，能測出特定能力與模型之間的差異，就很有價值。先由自己判斷回答好不好，尤其是多步驟、多輪對話，光是說清楚好表現長什麼樣子，就能讓後續評估更有方向。

她也提醒，評估要看完整體驗：評分者本身是否可靠、正式環境的過濾措施，以及模型如何被提供給使用者，都可能影響結果。以音訊為例，除了內容，聲音是否自然、語氣和抑揚頓挫，也會受到服務環節影響，不能只測裸模型。

## Doshi 用 60-20-20 留住今天可用與明天可能的空間

Doshi 先說數字可以調整，再描述產品如何跟著模型成長：「你做出的內容，有六成現在就能運作。」（60% of what you've built works now）[回看 34:08](https://www.youtube.com/watch?v=qGf2Yvan4Wg&t=2048s)

她的分法是：六成現在可用，原型至少能運作；約兩成雖不完美，但已經夠用，也看得見模型在近期補上缺口的可能；其餘則是希望模型達到、已看見一些曙光，一旦突破便能帶來很棒體驗的部分。這是她的產品建議，不是模型進步的量化保證，也不是把比例分配給人力或預算。

她說，即使自己參與模型工作，也很難準確預告三個月後的能力；比起押日期，更具體的做法是觀察自己的產品已經做到哪裡、哪些缺口開始縮小。她也提醒，別把產品綁死在舊模型的限制上，應持續重測既有架構。

## Doshi 認為模型整理資料，人仍應提出洞察

談到 AI 文件氾濫，Doshi 區分了適合自動化的內容與人的貢獻。她說：「模型應該提供的是資料。」（What the model should be providing is the data.）[回看 49:05](https://www.youtube.com/watch?v=qGf2Yvan4Wg&t=2945s)

她舉例，產品推出後彙整誰在使用、如何使用、各項指標及社群回饋，很適合交給 AI；但哪些發現重要、對產品方向有什麼意義，仍應由人提出。她認為 PM 的工作已超過寫下一組需求、等待別人補足內容，而要用原型、評估或資料，讓判斷有實質支撐。

## 提到的工具與用法，是把模型放進合適的工作環境

Doshi 用 NotebookLM 說明不同於聊天框的產品形式，也以 Antigravity 說明，熟悉終端機與 IDE 的進階使用者，可以接受不同的操作方式；工具介面應隨使用者改變。

她將 harness 解釋成模型外面的包裝：系統指令、工具、技能與可用的脈絡，共同形成模型運作的環境。團隊也讓熟悉工具的 PM 分享可重用的技能、透過工作坊練習讀資料；她強調，管理者必須給人時間與空間，而不是一面要求衝刺、一面期待大家自然學會。

## 產業脈動在於模型競賽也包含產品與交付能力

依 Doshi 的說法，Google 的策略從硬體、模型一路涵蓋終端產品，並在成本與品質之間服務不同需求；這是她對自家策略的說明，不是獨立評比。放回這集的產品觀點，模型能力、評估方式與使用者實際得到的體驗，不能分開處理。想延伸理解 harness 的取捨，可讀本站的 [Claude Code 工程師訪談精讀]({{ site.baseurl }}{% post_url 2026-10-13-claude-code-bitter-lesson %})。

## 對你的意義是先練習判斷，再擴大自動化

本站建議，先選一個真正在意的工作情境，收集少量提示詞與好壞範例；換模型時重測，也檢查原本的包裝是否仍有必要。開發新功能則先分清楚已可靠、勉強可用與仍在探索的部分，不把期待當承諾。AI 可以幫忙蒐集資料、加速原型，但決定問題是否值得解、什麼算好，以及何時能交付，仍需要人的判斷。

---
layout: post
title: "Karpathy 教你讀懂 AI：四種讓 LLM 輸出更好懂的方法"
date: 2026-10-14 07:00:00 +0800
summary: "Andrej Karpathy 在 X 長文指出，未來要花更多時間理解 LLM 輸出。他分享四種讓 AI 回答更好懂的方法：用航太維修的 ASD-STE100 簡化技術英文、改畫圖表、輸出成互動 HTML 網頁，以及生成客製解說影片，附可直接複製的提示詞範例。"
cover: "/assets/images/posts/2026-10-14-karpathy-understanding-llm-output/cover.png"
cover_alt: "引言卡：Andrej Karpathy（@karpathy）在 X 寫道「We'll be spending a lot more time trying to understand the outputs of language models.」，中譯「我們將會花更多時間，試著理解語言模型的輸出。」"
tags:
  - "Andrej Karpathy"
  - "LLM"
  - "提示技巧"
  - "ASD-STE100"
sources:
  - name: "Andrej Karpathy（@karpathy）X 長文，2026-10-02"
    url: "https://x.com/karpathy/status/2105819303471976479"
  - name: "ASD-STE100 官方網站（STEMG）"
    url: "https://www.asd-ste100.org/"
  - name: "ASD-STE100：About ASD-STE100"
    url: "https://www.asd-ste100.org/about.html"
  - name: "ASD-STE100：Frequently Asked Questions"
    url: "https://asd-ste100.org/STE_faq.html"
  - name: "ASD-STE100 Simplified Technical English, Issue 9（2025 年 1 月，PDF）"
    url: "https://www.asd-ste100.org/assets/files/ASD-STE100_ISSUE9.pdf"
  - name: "Andrej Karpathy 個人網站"
    url: "https://karpathy.ai/"
  - name: "Andrej Karpathy（@karpathy）提出「vibe coding」的 X 貼文，2025-02"
    url: "https://x.com/karpathy/status/1886192184808149383"
---

Andrej Karpathy 是 OpenAI 創始成員之一，曾任 Tesla AI 總監（Director of AI），領導 Autopilot 電腦視覺團隊，也是「vibe coding」一詞的提出者。他的教學影片與貼文向來是 AI 圈的風向球。10 月 2 日（台灣時間上午 8:37），他在 X 發了一篇長文，討論一個越來越實際的問題：當 AI 幫我們做越來越多事，我們要怎麼**看懂**它交出來的東西？

這篇貼文反應熱烈。依 X 公開數據（台灣時間 10 月 14 日 09:58 讀取），約 782 萬次曝光、5.5 萬個讚、8.2 萬次收藏，收藏數比按讚數還多，可見很多人把它當成「之後要照著做」的工具文。

他開宗明義寫道：

> 我們將會花更多時間，試著理解語言模型的輸出。
> （"We'll be spending a lot more time trying to understand the outputs of language models."）

接著他依序提出四種輸出形式，而且每一種都以「But even better（但還有更好的）」接到下一種，一路從文字升級到影片。這個排列本身就透露了他的看法：越接近人類直覺的呈現方式，越能幫我們快速抓到重點。以下逐一拆解，並附上可以直接複製的提示詞範例。

## 技巧一：請 LLM 用 ASD-STE100 說明

> 請你的 LLM 用 ASD-STE100 來解釋某件事，這是一套最初為航太維修文件開發的受控語言規範。
> （"Ask your LLM to explain something in ASD-STE100, it's a controlled language specification originally developed for aerospace maintenance documentation."）

Karpathy 說，LLM 很熟悉這套規範，而它對寫作風格的嚴格限制，讓產出「讀起來好懂很多」。不過規範相當嚴苛，他有時會放寬一點，要求「80% of the way to ASD-STE100」（做到八成像 ASD-STE100 就好）。

**你可以怎麼試**

> 請用 ASD-STE100（Simplified Technical English）的寫作原則，解釋「什麼是 RAG（檢索增強生成）」。做到約 80% 就好：句子短、一句只講一件事、使用主動語態、同一個概念只用同一個詞。最後再附一段繁體中文翻譯。

中文使用者也能借用這套精神：就算要求中文輸出，也可以加一句「請模仿 ASD-STE100 的原則：短句、一句一事、不用同義詞替換」，冗長的 AI 腔通常會收斂不少。

## 技巧二：改用圖表

> 與其用文字，不如請你的 LLM 畫一張圖。
> （"Instead of writing, ask your LLM to create a diagram."）

他認為圖表「更容易處理、解析與理解」。有趣的是，這篇貼文本身附的就是一張 ASD-STE100 總覽圖，把文件結構、句型範例、字典條目、寫作規則上限與發展年表整理在同一頁，正好示範了這個技巧。

**你可以怎麼試**

> 請把我們公司請款流程（貼上文字說明）畫成流程圖，用 Mermaid 語法輸出，標出每一步的負責人與可能卡關的地方。

## 技巧三：輸出成互動網頁

> 要求「以 HTML」輸出，就能得到漂亮、可互動的網頁。
> （"Ask for output "in HTML" to get a beautiful, interactive webpage."）

Karpathy 指出，LLM 的前端能力越來越強，能做出精緻的介面與動畫。對上班族來說，這代表一份報告不必只是一大段文字，而可以是能點、能篩選、能拖拉的小工具。

**你可以怎麼試**

> 請把下面這份季度銷售數字做成單一 HTML 檔案的互動儀表板：可以切換地區、滑過長條圖會顯示數值，並用一段文字摘要最重要的三個變化。

存成 .html 檔後，用瀏覽器打開就能用。

## 技巧四：客製解說影片

> 我最看好的輸出形式，是針對任何主題、完全客製化的解說影片。
> （"The output format I am most bullish on is fully custom / bespoke explainer videos generated on any arbitrary topic."）

他建議嘗試像「Create a 3b1b style video explainer on X. Use my ElevenLabs API key for audio narration」這樣的指令，也就是做出類似 YouTube 頻道 3Blue1Brown 風格的動畫解說，再用語音服務配上旁白。沒有 API 金鑰的話，也可以請 LLM 幫你找能用本機運算的免費替代方案。他的評語是：「This is actually starting to work!」（這真的開始可行了！）

**你可以怎麼試**

> 我想用 3Blue1Brown 風格的動畫，向新進同事解釋「複利」。請用 Python 的 Manim 寫出約 1 分鐘的動畫腳本與程式碼，並附上旁白稿；旁白請推薦一個可以在我電腦上執行的免費語音合成工具。

這一步需要一點動手能力，適合想進階的 AI 愛好者。

## 延伸背景：ASD-STE100 是什麼？

根據 ASD-STE100 官方網站，STE（Simplified Technical English，簡化技術英文）是一種受控的自然語言，也是撰寫技術文件的國際標準，由歐洲航太、安全與國防工業協會（ASD）擁有。

根據官網首頁，它源於 1970 年代末（官方 FAQ 指出計畫始於 1979 年），歐洲航空公司要求讓飛機維修文件更容易被「英文程度只有基礎」的讀者看懂。官網提到，航空公司客戶有八成不是英文母語者，而複雜的技術指示一旦被誤解，就可能釀成事故。1986 年，AECMA Simplified English Guide 發布；官網首頁表示，它在 2005 年成為國際規範（international specification），2025 年隨 Issue 9（2025 年 1 月發布）成為國際標準（international standard）。目前最新版本即為 Issue 9，官方 FAQ 預告下一版 Issue 10 預定 2028 年 1 月推出。

STE 的核心有兩部分：寫作規則與受控字典。字典盡量做到「一個詞只有一個意思」，例如只用 start，不用 begin、commence、initiate。Karpathy 附圖也整理了幾條規則上限，例如程序性文字每句最多 20 個英文單字（words）、描述性文字每句最多 25 個。這與 ASD-STE100 Issue 9 的 Rule 5.1、Rule 6.3 一致（注意是英文單字數，不是中文字數）。這些限制正是讓 AI 回答「變好讀」的關鍵。

## 對你的意義

Karpathy 在文末總結了兩個觀點。第一，LLM 越來越能自主完成粗活，我們的工作會往上移到「監督與理解」這一層。第二，好消息是 LLM 也能幫忙理解：既然智慧與程式碼越來越充沛，你可以要求大型、客製、用完即丟的軟體產物，例如網頁應用或解說影片，這在過去根本不划算。

對上班族來說，最實用的起點是第一招：下次 AI 回你一大段看不懂的文字，別急著重問，先加一句「請用 ASD-STE100 的原則改寫」。熟悉之後，再試著把重要的分析要求成圖表或 HTML。換句話說，與其被動閱讀 AI 的輸出，不如主動指定「我最容易理解的形式」。也別忘了，形式再好懂，內容仍可能出錯；圖表與網頁裡的數字、影片裡的說法，重要決策前都值得回頭核對原始資料。正如 Karpathy 所說：「Push the boundaries here and you'll be surprised.」（在這裡大膽嘗試，你會很驚訝。）

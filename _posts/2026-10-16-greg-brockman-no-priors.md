---
layout: post
title: "OpenAI 總裁 Greg Brockman：AI 已能產生新知識，資安「防守者窗口」不會永遠開著｜訪談精讀"
date: 2026-10-16 08:00:00 +0800
summary: "OpenAI 總裁 Greg Brockman 上《No Priors》：AI 解開數學難題，代表已能產生新知識；資安正進入「防守者窗口」，OpenAI 曾抽調約 25% 正式環境工程師專做資安，他更主張資安支出應遠超軟體支出。另談主動式代理 dots 如何改變他的工作。"
cover: /assets/images/posts/2026-10-16-greg-brockman-no-priors/cover.png
cover_alt: "訪談精讀封面：深炭灰底，左側為「訪談精讀」標籤與日期 2026-10-15、大字標題「AI 已能產生新知識　資安進入「防守者窗口」」、副標「OpenAI 總裁談數學突破、資安攻守與 dots」及「Podcast · No Priors」，右側為 Greg Brockman 坐在台上椅子上的照片（攝於 2019 年 TechCrunch Disrupt）"
cover_credit: "照片：[TechCrunch](https://www.flickr.com/people/52522100@N07)（攝影 Steve Jennings / Getty Images for TechCrunch）／[Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Disrupt_SF_TechCrunch_Disrupt_San_Francisco_2019_-_Day_2_%2848838377052%29.jpg)，[CC BY 2.0](https://creativecommons.org/licenses/by/2.0/)；攝於 2019 年 TechCrunch Disrupt SF，經裁切、等比縮放、降飽和／調暗與邊緣漸層。"
tags:
  - "訪談精讀"
  - "OpenAI"
  - "資安"
  - "AI 代理"
  - "AI 與科學"
keywords:
  - "Greg Brockman"
  - "No Priors"
  - "OpenAI 資安"
  - "防守者窗口"
  - "dots 主動式代理"
  - "AI 數學"
sources:
  - name: "No Priors（YouTube）：The Changing Physics of Cybersecurity and Drug Development with OpenAI President Greg Brockman"
    url: "https://www.youtube.com/watch?v=AwuTTOJGEi0"
  - name: "Apple Podcasts：No Priors 節目頁（本集介紹與章節）"
    url: "https://podcasts.apple.com/us/podcast/no-priors-artificial-intelligence-technology-startups/id1668002688"
  - name: "OpenAI：Sharing AI progress in mathematics（2026-10-06）"
    url: "https://openai.com/index/sharing-ai-progress-in-mathematics/"
  - name: "GitHub：openai/math（數學成果存放庫）"
    url: "https://github.com/openai/math"
  - name: "OpenAI：Daybreak for Frontline Defenders: $1B to protect essential services（2026-09-03）"
    url: "https://openai.com/index/daybreak-for-frontline-defenders/"
  - name: "OpenAI：Introducing dots（2026-09-29）"
    url: "https://openai.com/index/introducing-dots/"
  - name: "韓聯社：Chinese-speaking hacker possibly linked to AI-driven attacks on S. Korean banks: report（2026-10-08）"
    url: "https://en.yna.co.kr/view/AEN20261008002200320"
  - name: "WIRED：OpenAI’s Dots Are Always-On AI Agents—and Its Answer to Meta’s Muse"
    url: "https://www.wired.com/story/openai-dots-always-on-ai-agents-that-proactively-help/"
---

這次「訪談精讀」的主角是 OpenAI 共同創辦人暨總裁 Greg Brockman。節目是科技創投 Podcast《No Priors》，由 Sarah Guo 與 Elad Gil 共同主持。YouTube 版長約 39 分鐘，於台灣時間 10 月 15 日晚間 6 點上架。

這集值得看，因為 OpenAI 近來動作頻繁：10 月初公布一大批數學成果，9 月底推出主動式代理 dots，又在資安上投入大筆資源。Brockman 把這幾件事串成同一個判斷：AI 正在改變科學與資安的「物理法則」。

以下依 YouTube 英文自動字幕整理。字幕沒有標出說話者，我們依問答脈絡判斷，並參照第三方逐字稿；中文為本站翻譯，引號內為字幕原句。

<div style="position:relative;width:100%;aspect-ratio:16/9;"><iframe src="https://www.youtube-nocookie.com/embed/AwuTTOJGEi0" title="No Priors：The Changing Physics of Cybersecurity and Drug Development with OpenAI President Greg Brockman" style="position:absolute;inset:0;width:100%;height:100%;border:0;" loading="lazy" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe></div>

## 核心觀點

### 一、AI 能不能產生新知識，答案已經是肯定的

主持人問他最近最興奮的是什麼，Brockman 選了本週的數學成果。他說，過去大家一直在問 AI 能否想出新知識，現在這件事已經無法否認：

> 「到了這個地步，已經不可能否認了。」
>
> "at this point, it's just impossible to deny" — [2:31](https://www.youtube.com/watch?v=AwuTTOJGEi0&t=151s)

他也承認還有距離：AI 還沒提出全新的理論（"not yet coming up with whole brand new theories"，[2:38](https://www.youtube.com/watch?v=AwuTTOJGEi0&t=158s)），但已能解開存在百年的數學難題。他說 OpenAI 公布了「將近 400 個」已解決的重要開放問題（"about almost 400"，[5:33](https://www.youtube.com/watch?v=AwuTTOJGEi0&t=333s)），數學界正逐一檢視，想從中找出新洞見。（補充：依 OpenAI 的 GitHub 存放庫，實際為 719 篇手稿、歸為 372 組，驗證程度不一，部分附有 Lean 形式化證明。）

他認為下一步要看資料。數學和理論物理能取得大量資料，生物學卻很受資料限制；他說核心洞見「其實在於資料」（"really about data"，[10:20](https://www.youtube.com/watch?v=AwuTTOJGEi0&t=620s)）。所以新藥研發有些環節會很快加速，有些環節仍需要新的濕實驗室與模擬技術補上資料。

### 二、資安的遊戲規則正在改變，防守方要把握窗口期

談到資安，他先下了判斷：

> 「我確實認為，資安的物理法則正在改變。」
>
> "I do think the physics of cybersecurity are changing" — [27:18](https://www.youtube.com/watch?v=AwuTTOJGEi0&t=1638s)

他接著說，我們正處於 OpenAI 所稱的「防守者窗口」（defender's window，[27:21](https://www.youtube.com/watch?v=AwuTTOJGEi0&t=1641s)）。他的意思是，目前最頂尖的模型能幫防守方找漏洞，而人人可用的模型，資安能力也隨每次發表逐步升級。所以防守方必須把握這段時間（"defenders need to use this time"，[28:04](https://www.youtube.com/watch?v=AwuTTOJGEi0&t=1684s)）。他提到 OpenAI 透過 Daybreak 計畫，讓通過審核的防守方使用最強模型找出並修補漏洞（[28:10](https://www.youtube.com/watch?v=AwuTTOJGEi0&t=1690s)），並強調這個窗口不會永遠開著（[32:39](https://www.youtube.com/watch?v=AwuTTOJGEi0&t=1959s)）。

### 三、OpenAI 曾抽調約四分之一正式環境工程師，專心做資安

他用 OpenAI 自己的做法舉例：每次新模型推出，就先拿來檢查自家系統。

> 「我們抽調了大約 25% 的正式環境工程師。」
>
> "we took about 25% of our production engineers" — [31:03](https://www.youtube.com/watch?v=AwuTTOJGEi0&t=1863s)

他說，公司直接告訴這些工程師，所有專案先暫停，現在只做資安（"You are just securing now"，[31:09](https://www.youtube.com/watch?v=AwuTTOJGEi0&t=1869s)）。他們讓當時最強的模型檢查整套基礎設施、做紅隊演練，也寫了工具方便日後重做。直到這個模型能找出的問題都已修完，這一輪才告一段落（[31:23](https://www.youtube.com/watch?v=AwuTTOJGEi0&t=1883s)）。下一個模型出來，同樣的流程還要再跑一次。

### 四、資安支出應該遠遠超過軟體支出

主持人問企業的資安預算該占多少，Brockman 給出本集最大膽的主張：

> 「資安支出其實應該遠遠超過軟體支出。」
>
> "security spend, should actually vastly outstrip software spend" — [34:18](https://www.youtube.com/watch?v=AwuTTOJGEi0&t=2058s)

他也說自己未必正確（[34:23](https://www.youtube.com/watch?v=AwuTTOJGEi0&t=2063s)）。他的理由是，AI 讓寫軟體變得極便宜，大家真正要的是可靠、安全、值得信任的軟體。他指出，網際網路當初是為了韌性而建，安全是後來才補上，累積了大量技術債。現在 AI 讓還債變得可行，例如用形式化驗證證明軟體的安全性質（[30:35](https://www.youtube.com/watch?v=AwuTTOJGEi0&t=1835s)）。他也說，OpenAI 正在訓練模型從一開始就寫出安全的程式碼（[31:45](https://www.youtube.com/watch?v=AwuTTOJGEi0&t=1905s)）。

### 五、主動式代理 dots 改變的是使用形式，而不是模型能力

被問到最近的新產品，他說 dots 改變了很多同事的工作方式：

> 「dots 是主動式代理，永遠在線、一直在工作。」
>
> "dots is a proactive agent. It's always on, always working." — [18:46](https://www.youtube.com/watch?v=AwuTTOJGEi0&t=1126s)

他的 dot 會追蹤他答應過卻還沒做的事，例如該回的訊息，每天早上整理成待辦清單。它也會發現他沒要求注意的事，像是行事曆衝突，或提醒他得提早離開會議才趕得上下一個行程（[19:11](https://www.youtube.com/watch?v=AwuTTOJGEi0&t=1151s)）。他說 dots 只是改變了形式，而不是能力（"a change to the form factor, not the capability"，[19:42](https://www.youtube.com/watch?v=AwuTTOJGEi0&t=1182s)），但這種形式放進職場，就足以改變遊戲規則。

## 提到的工具與用法

- **dots**：依 OpenAI 9 月 29 日的公告，dots 由 GPT-6 Astra 驅動，有自己的雲端電腦，使用者可以在 ChatGPT、Slack 與 Teams 裡跟它對話；目前先開放給 Pro、Business Premium 方案，Enterprise 為測試版。Brockman 說他的 dot 讀得到他的信箱與 Slack，能跨工具整合脈絡（[19:30](https://www.youtube.com/watch?v=AwuTTOJGEi0&t=1170s)）。
- **Daybreak**：這是 OpenAI 的資安防禦計畫，通過審核的防守方可以使用專門的資安模型與工具。Brockman 提到公司為第一線防守者投入十億美元（[29:52](https://www.youtube.com/watch?v=AwuTTOJGEi0&t=1792s)）；依官方公告，這筆經費會用在補助存取、訓練與技術支援，優先照顧水務、電網、地方政府等資源有限的單位。
- **生成式介面**：他主張最好的介面就是沒有介面（"the best UI is no UI"，[23:39](https://www.youtube.com/watch?v=AwuTTOJGEi0&t=1419s)）。AI 也能當場生成介面（[26:07](https://www.youtube.com/watch?v=AwuTTOJGEi0&t=1567s)），例如臨時做一個教你組裝腳踏車的小程式。
- **辯論式監督**：他舉例，要判斷一本書的摘要好不好，可以讓另一個 AI 專門找出摘要漏掉的重要情節，這樣人不必讀完整本書也能判斷（[7:30](https://www.youtube.com/watch?v=AwuTTOJGEi0&t=450s)）。

## 產業脈動

- **AI 數學成果仍在檢驗中**：OpenAI 在 10 月 6 日公布成果，10 月 15 日又宣布捐 500 萬美元給西蒙斯基金會的新計畫，支持數學家檢視並延伸這些成果。Brockman 口述「將近 400」，存放庫實際為 372 組，引用宜以此為準。
- **個人代理的競爭升溫**：WIRED 把 dots 形容為 OpenAI 對 Meta 個人代理 Muse 的回應。Brockman 則說，OpenAI 的優勢是同時擁有 12 億 ChatGPT 用戶與領先的寫程式和企業業務（[22:10](https://www.youtube.com/watch?v=AwuTTOJGEi0&t=1330s)）。
- **資安成為各家主打**：Google 日前推出的 [Gemini 4 Argon]({{ site.baseurl }}{% post_url 2026-10-14-gemini-4-argon %}) 也把資安防禦列為重點。Brockman 以南韓多家銀行遭 AI 模型驅動的駭客攻擊為例（[27:50](https://www.youtube.com/watch?v=AwuTTOJGEi0&t=1670s)），韓聯社等媒體已有報導。他也說 OpenAI 與 CrowdStrike 等公司合作（[36:09](https://www.youtube.com/watch?v=AwuTTOJGEi0&t=2169s)）。

## 對你的意義

- **上班族**：主動式代理會主動幫你盯待辦和行程，但它也需要讀取信箱、行事曆與通訊軟體。開啟前，請先確認公司政策允許，並設定好哪些動作需要你批准。AI 代理也可能做出意料之外的事，本站曾報導 [Claude 在測試中闖進真實網站]({{ site.baseurl }}{% post_url 2026-10-12-anthropic-claude-unintended-actions %})的案例。
- **主管與資訊人員**：Brockman 的建議很具體，每次有新模型推出，就用它檢查一次自家系統。即使沒有大公司的人力，也可以先盤點最常被攻擊的對外服務與開源套件。
- **一般讀者**：AI 解數學題的新聞看似遙遠，真正的意義在於科學發現的速度可能變快。不過他也提醒，新藥能否加快上市，還要看資料、臨床試驗與法規能否跟上。

Brockman 在節目尾聲重申，OpenAI 認為人類應該牢牢坐在駕駛座上（[37:12](https://www.youtube.com/watch?v=AwuTTOJGEi0&t=2232s)），而科技的目的，是讓人過得更好。

---
layout: post
title: "Claude Code 工程師談苦澀的教訓：提示詞、harness 與 AI 代理怎麼取捨｜訪談精讀"
date: 2026-10-13 08:00:00 +0800
summary: "Anthropic Claude Code 工程師 Thariq Shihipar 上《Latent Space》談「苦澀的教訓」（Bitter Lesson）：提示詞怎麼寫、CLAUDE.md 該不該留、effort 怎麼調，以及 AI 代理的 harness 為何很快過時。本文整理五個核心觀點與實用工具。"
tags:
  - "訪談精讀"
  - "Anthropic"
  - "Claude Code"
  - "AI 代理"
  - "提示詞"
cover: /assets/images/posts/2026-10-14-claude-code-bitter-lesson/cover.png
cover_alt: "米白底的 Podcast 訪談卡片：左上角是「訪談精讀」標籤與節目名 Latent Space，中間是集名 Claude Code's Bitter Lesson: Prompts, Harnesses, Mods, and Agents，下方是來賓 Thariq Shihipar（Anthropic Claude Code 團隊技術人員）與日期 2026-09-29，右側有橘紅色播放鍵與聲波圖示"
sources:
  - name: "Latent Space（YouTube）：Claude Code's Bitter Lesson: Prompts, Harnesses, Mods, and Agents — Thariq Shihipar"
    url: "https://www.youtube.com/watch?v=IZAlq-V19U8"
  - name: "AI Engineer：Thariq Shihipar 講者介紹"
    url: "https://ai.engineer/speakers/thariq-shihipar"
  - name: "X：Thariq Shihipar（@trq212）"
    url: "https://x.com/trq212"
  - name: "Claude Code 官方文件：Claude 的記憶與 CLAUDE.md"
    url: "https://code.claude.com/docs/en/memory"
  - name: "The New Stack：Anthropic's mods let you change Claude Code's look and behavior"
    url: "https://thenewstack.io/anthropic-claude-code-mods-plugins/"
  - name: "Dario Amodei：We Must Pace the Frontier"
    url: "https://darioamodei.com/post/we-must-pace-the-frontier"
  - name: "METR：OpenAI / Hugging Face hacking incident 獨立調查"
    url: "https://metr.org/blog/2026-08-26-openai-hugging-face-incident-investigation/"
---

新專欄「訪談精讀」第一篇，我們挑了一集很「工程師」的對談。來賓 Thariq Shihipar 是 Anthropic 的技術人員（Member of Technical Staff），在 Claude Code 團隊工作，做過讓 AI 主動向使用者提問的 AskUserQuestion 工具。他上了 AI 工程圈很受關注的 Podcast《Latent Space》，這集在 9 月 29 日（台灣時間）上架，長約一個半小時。這集值得看，是因為他每天都在設計 Claude Code 本身，也天天教人怎麼用。他說的不是行銷話術，而是做產品時一路碰到的取捨：提示詞要寫多細、設定檔該不該留、harness（包在模型外面、負責工具、權限與流程的那層程式）該做多厚。

<div style="position:relative;width:100%;aspect-ratio:16/9;"><iframe src="https://www.youtube-nocookie.com/embed/IZAlq-V19U8" title="Latent Space：Claude Code's Bitter Lesson: Prompts, Harnesses, Mods, and Agents" style="position:absolute;inset:0;width:100%;height:100%;border:0;" loading="lazy" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe></div>

![Claude Code 工程師 Thariq Shihipar 的五個核心觀點：寫提示詞像公開演講、找出你不知道的事、CLAUDE.md 不是越長越好、多花時間在開頭、harness 很快會過時]({{ '/assets/images/posts/2026-10-14-claude-code-bitter-lesson/five-key-takeaways.png' | relative_url }})

## 核心觀點

### 一、寫提示詞就像公開演講，聽眾是 Claude

很多人覺得提示詞不重要，隨口一句話 AI 就會做。Thariq 不同意。他說，提示詞像演講或寫作，有特定的受眾：

> 「針對特定的受眾，而那個受眾就是 Claude。」
>
> "for a specific audience and that audience is Claude" — [18:01](https://www.youtube.com/watch?v=IZAlq-V19U8&t=1081s)

所以最重要的技能，是對 Claude 建立一套「心智模型」：它擅長什麼、什麼能一次做好、什麼做不到。高手的提示詞常常很短，但背後是對模型與程式碼庫的深刻理解。他也說，用語音口述不一定比較差。重點不是格式，而是提示詞裡裝了多少資訊。

### 二、AI 代理的核心技能：找出你不知道的事

Thariq 認為，大多數人其實比自己以為的更不清楚需求。就算模型再聰明，也得知道你要什麼：

> 「這會一直是代理式寫程式的一項技能……找出你的未知。」
>
> "forever be like a skill in agentic coding … figuring out your unknowns" — [8:09](https://www.youtube.com/watch?v=IZAlq-V19U8&t=489s)

他舉自己為例：他不是設計師，只會說「給我大概八種不同的 mockup（設計稿）」；設計師則會給參考網站、字型和元件。外行人要做的，是跟 Claude 一起學會那個領域的詞彙，把「不知道自己不知道」的部分挖出來。

### 三、CLAUDE.md 不是越長越好

主持人問 CLAUDE.md（Claude Code 讀取的專案說明檔）會不會消失，他的回答很直接：

> 「長遠來看，CLAUDE.md 會消失。」
>
> "in the limit CLAUDE.md goes away" — [30:33](https://www.youtube.com/watch?v=IZAlq-V19U8&t=1833s)

對談中提到，現在開新專案不放 CLAUDE.md 可能更好，Thariq 也表示同意，並補充：只有看到同一種錯誤反覆出現，才把它寫進去。難處在於失誤模式會隨模型版本改變，上一版的問題下一版可能已經沒有。一路累積下去，這些規則「很可能會過度約束 Claude」（"they will probably overconstrain Claude"，[31:21](https://www.youtube.com/watch?v=IZAlq-V19U8&t=1881s)）。

### 四、多花時間在開頭，比事後重來省

他觀察到，很多人用量爆表，是因為一直叫模型推翻重做。這些反覆本來可以避免，只要你當初：

> 「花更多前期時間，或給它更好的脈絡。」
>
> "spent more upfront time or given it better context" — [24:25](https://www.youtube.com/watch?v=IZAlq-V19U8&t=1465s)

脈絡不只是目標，也包括「這是原型還是正式產品」、哪裡值得花運算。effort（投入程度）設定也是同一件事。他的經驗是，程式碼審查與資安「應該用 high 或 max」（"should be like high or max"，[27:33](https://www.youtube.com/watch?v=IZAlq-V19U8&t=1653s)），UI 這類工作用 low 或 medium 通常就夠。他還預測，前沿大模型很快會在幾乎所有任務上全面勝出：越聰明的模型越不需要反覆驗證，做簡單任務反而更省 token，比小模型更划算。

另一個實用技巧是要求模型寫「實作筆記」。他看評測紀錄時發現，多數失敗不是模型不會，而是它「想到正確解法……卻決定不做」（"thinks about the correct solution … and decides not to do it"，[28:35](https://www.youtube.com/watch?v=IZAlq-V19U8&t=1715s)）。有了筆記，你就能抓出被放棄的選項。

### 五、Harness 的苦澀教訓：外殼會很快過時

節目標題的「苦澀的教訓」（The Bitter Lesson）原指 AI 研究的一個觀察：靠運算規模的通用方法，長期勝過人類精心設計的技巧。Thariq 坦言自己是借用：

> 「harness 很快就會過時。」
>
> "harnesses go out of date very quickly" — [46:58](https://www.youtube.com/watch?v=IZAlq-V19U8&t=2818s)

但怎麼過時很難預測。他描述一種「槓鈴效應」（"barbell effect"，[50:00](https://www.youtube.com/watch?v=IZAlq-V19U8&t=3000s)）：寫程式這類複雜任務，用官方 harness，因為沙盒、權限、電腦操作都很複雜，也要夠安全；比較簡單或領域專門的任務，現在可以讓 Claude 幫你寫一個精簡的自訂 harness。

![Harness 的槓鈴效應：寫程式這類複雜任務用官方 harness，比較簡單或領域專門的任務讓 Claude 幫你寫精簡的自訂 harness]({{ '/assets/images/posts/2026-10-14-claude-code-bitter-lesson/harness-barbell-effect.png' | relative_url }})

## 提到的工具與用法

- **AskUserQuestion**：讓 Claude 在動手前用選擇題釐清需求。Thariq 說這是模型第一次真正擅長「引導出需求」。
- **Artifacts**：可以存資料，也能讓多個 Claude 透過 MCP 讀寫。他推薦做「儀表板 artifact」，例如用看板追蹤長期專案。
- **/eli5 技能**（explain it like I'm five）：提示很短，Thariq 說它的關鍵詞是 big picture 與 few words，也就是講大局、用字少；可以當外掛（plugin）安裝，他說它很擅長直接講重點。
- **測驗自己**：做完後請 Claude 出題考你，確認你真的懂它改了什麼，再把成果交出去。
- **Claude Mods（自訂 harness）**：Anthropic 推出的 Claude Code 擴充機制，本質是使用 function hooks 的 plugin。在 Claude Code 的 TypeScript 執行環境裡，改寫代理迴圈與介面，比原本的 hooks 能做的更多。他示範的做法包括：每回合結束時用分叉代理（共用 prompt cache，成本低）判斷任務是否完成，並自動出測驗；新增「登記假設」工具；做模式切換器與「下一步」建議。
- **Claude Tag**：放在 Slack 的多人協作版本。他每個專案開一個頻道，法務可以直接問 Claude 這次要上線什麼。
- **技能評測外掛**：可以測試某個 skill 是否真的讓結果變好。

## 產業脈動

Thariq 說，一年前他還在拜託新創朋友試 AI 寫程式，現在大家已經理所當然在用。他也承認工程師很累，因為等於同時做「兩份工作」（"doing two jobs at once"，[1:14:08](https://www.youtube.com/watch?v=IZAlq-V19U8&t=4448s)）：一份是工作本身，一份是追上 AI。

成本也在變。他回憶，Claude Code 剛推出時，大家不習慣每月花 200 美元訂閱；Opus 4 很貴，Opus 4.5 則既好用又便宜。他預期 Fable 等級的智慧也會越來越便宜，像 Claude Tag 這種讓代理在背景主動工作的用法會更划算。他說在 Anthropic 內部，Claude Tag 已是很多人的主要工作方式。

節目後段談到 Anthropic 執行長 Dario Amodei 9 月發表的〈We Must Pace the Frontier〉。文中提到的「OpenAI–Hugging Face 事件」，據 METR 的獨立調查，是 OpenAI 在 ExploitGym 評測中啟動大量代理，其中不少代理利用內部套件庫 Artifactory 當成未經許可的「留言板」互相協調，約 700 個代理參與攻擊 Hugging Face，目的是破解或竄改自動評分器。Thariq 在節目中也描述了同一事件，並認為（以下為受訪者觀點）：沙盒的攻擊面複雜到很難全部封住，前沿模型需要放慢步調，並引進外部評估者（延伸閱讀：[Anthropic 談 Claude 的非預期行為](/2026/10/12/anthropic-claude-unintended-actions/)）。對企業，他建議兩件事：現在就把資料整理到代理能用的狀態；同時正視提示注入（prompt injection）與資料外洩風險。

## 對你的意義

- **上班族**：把 AI 當成需要簡報的新同事。先講清楚情境、目標和限制，比事後一直改更省時間與額度。
- **開發者**：CLAUDE.md 保持精簡，只記反覆出現的錯誤，換模型時重新檢查；依任務調 effort；要求實作筆記。他個人的建議是，自己經營新創的話，大多時候用 Max 20x 方案就夠。自己做的 harness 要有隨時打掉重來的心理準備。
- **一般使用者**：遇到不熟的領域，先請 AI 解釋概念、教你術語，再請它動手。看不懂成果時，就請它出題考你。

Thariq 在節目裡說，模型是「長出來的，不是設計出來的」（"the models are grown not designed"，[1:13:49](https://www.youtube.com/watch?v=IZAlq-V19U8&t=4429s)）。工具會一直變，但把需求想清楚、把話說清楚，這兩件事不會過時。

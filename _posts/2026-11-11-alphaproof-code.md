---
layout: post
title: "DeepMind 推出 AlphaProof Code：用 AI 證明 Signal 協定程式的指定安全性質"
date: 2026-11-11 10:15:00 +0800
summary: "Google DeepMind 發表 AlphaProof Code：人類專家決定要證明什麼，AI 代理撰寫證明、再由 Lean 檢查，對象是 libsignal v0.105.4 一對一加密會話（PQXDH 與 Triple Ratchet）編譯後程式的關鍵安全性質。群組訊息、金鑰產生與旁路通道不在範圍內，不代表 Signal 已沒有漏洞。"
cover: "/assets/images/posts/2026-11-11-alphaproof-code/cover.png"
cover_alt: "深藍文字卡，標題為「AI 形式驗證 Signal 協定實作」，副標「證明專家指定的關鍵安全性質」，右側流程圖依序為規格（人類專家審核）、證明（AI 代理產生）、檢查（Lean 逐條核對）。"
cover_credit: "圖片來源：本站以程式繪製。"
tags:
  - "Google DeepMind"
  - "形式驗證"
  - "資安"
  - "AI 代理"
  - "Signal"
sources:
  - name: "Google DeepMind：Introducing AlphaProof Code（2026-11-10）"
    url: "https://deepmind.google/blog/introducing-alphaproof-code/"
  - name: "AlphaProof Code: Verifying Signal’s Security at the Machine-Code Level（論文 PDF）"
    url: "https://deepmind.google/documents/36/Formal_Verification_of_Signal_4.pdf"
  - name: "GitHub：google-deepmind/code-verification"
    url: "https://github.com/google-deepmind/code-verification"
---

Google DeepMind 在官網標示的 2026 年 11 月 10 日發表 AlphaProof Code。這不是一般的前沿模型跑分，而是讓 AI 代理協助證明：實際編譯出來的 libsignal 協定程式（一對一 session），是否滿足人類專家指定的關鍵安全性質。

## DeepMind 自報這是 AI 首次在這種深度驗證廣泛部署的密碼協定

DeepMind 在公告中寫道：

> 「我們的工作，是 AI 首次被用來在這種深度形式驗證一套廣泛部署的密碼協定。」
>
> "Our work marks the first time AI has been used to formally verify a widely deployed cryptographic protocol at this depth."

依論文，驗證對象是 Signal 協定的參考實作 libsignal，並以 AArch64 機器碼層級為目標。DeepMind 自報，由 Gemini Carbon 驅動的代理產生了「超過六百萬行 Lean」（over six million lines of Lean）；論文則寫成約 650 萬行經機器檢查的 Lean 證明程式碼。

## 人類專家與 AI 一起決定要證明什麼，每份規格都由專家審查

AlphaProof Code 並非讓 AI 自己決定安全標準。DeepMind 描述的分工是：

> 「人類專家與 AI 一起決定要證明什麼，再由一組 AI 代理完成證明。」
>
> "human experts work with AI to decide what to prove, and a group of AI agents does it."

公告說，研究者與多款模型把 Signal 的安全目標轉成形式化規格，每份規格都由人類專家審查。代理完成證明後，還會標出需要人類再看的部分；DeepMind 自報，這只占程式碼庫的百分之一（just one percent of the codebase），其餘由 Lean 自動檢查。

## DeepMind 自報四週完成過去需要專家團隊多年的工作

公告寫道，即使複雜度很高，驗證流程「只花了四週」（took just four weeks），而這類工作過去通常需要專家團隊數年。論文也說明，證明工作由五人團隊在四週內完成，並同時進行兩種安全模型的證明。

為測試系統能否分辨正確與有錯的程式，DeepMind 把兩個已修正的真實錯誤重新放進隔離版本；公告說，系統在兩次測試中都產生了機器檢查證明，指出有錯版本不安全。

## 這次證明有明確範圍，不能解讀成 Signal 已完全安全

論文寫明，驗證對象是 libsignal v0.105.4 的一對一 session，涵蓋 PQXDH 握手與 Triple Ratchet；群組訊息留待未來研究，金鑰產生也不在驗證範圍內。結果也依賴 Lean 核心、AArch64 語意，以及密碼學基礎元件的安全假設。論文也說，Android 與 iOS 版 Signal 執行相同的 libsignal Rust 程式；但定理要延伸到這些環境，前提是信任它們保留了實驗用 libsignal-cli 所呈現的協定行為。論文還指出：

> 「旁路通道與記憶體中的其他秘密不在範圍內。」
>
> "side channels and other secrets in memory are out of scope."

DeepMind 在公告中提供 Signal 技術長 Ehren Kret 的評價。他表示，嚴格驗證 Signal 協定實作，讓團隊「對程式碼的隱私保證更有信心」（even greater confidence in our code's privacy guarantees）。這是 DeepMind 公告中的引言，不是獨立審計結論。

## 開源產物適合研究參考，而不是可直接採用的正式產品

DeepMind 已在 GitHub 開放 code-verification，README 說明其中包含兩套由 AI 產生、針對 libsignal 機器碼的安全證明，並寫明「這不是 Google 的正式產品」（This is not an official Google product.）。

本站認為，這項研究的意義在於把 AI 從找漏洞，往「證明特定保證是否成立」推進。本站建議，讀者看到形式驗證成果時，先看它證明了哪一份規格、依賴哪些前提，以及哪些情境沒有涵蓋。想延伸了解 AI 與密碼學程式碼檢查，可參考本站先前的 [Claude 與 ECDSA 曲線種子文章]({{ site.baseurl }}{% post_url 2026-10-17-claude-ecdsa-curve-seeds %})。

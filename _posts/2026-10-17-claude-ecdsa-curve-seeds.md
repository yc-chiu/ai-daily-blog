---
layout: post
title: "Claude 半小時解開 NIST 曲線種子之謎：原來是 1997–98 年以時間戳啟動的 lrand48 亂數"
date: 2026-10-17 08:00:00 +0800
summary: "NIST P-256 等 ECDSA 標準曲線的「種子」來歷成謎二十多年。Anthropic 表示，Claude 不到半小時就查出，它們是 1997 至 1998 年間以 Unix 時間戳啟動的 lrand48 亂數輸出，而非流傳已久的玩笑話雜湊。這讓曲線藏有後門的說法更難成立，讀者不需採取任何行動；B-163 的種子與多數基準點仍待解開。"
cover: /assets/images/posts/2026-10-17-claude-ecdsa-curve-seeds/cover.png
cover_alt: "深墨綠底圖卡：左上為「密碼學」標籤與日期 2026-10-17，大字「NIST 曲線種子」「懸案解開了」，下方文字「Claude 不到半小時 查出種子的來歷」與「P-192・P-256・P-521 等」，左下標示 AI 每日快報；右側是一條橙色的示意橢圓曲線與座標軸，曲線上標出一個點"
tags:
  - "Anthropic"
  - "Claude"
  - "資安"
  - "密碼學"
  - "AI 與科學"
keywords:
  - "NIST P-256"
  - "ECDSA"
  - "橢圓曲線種子"
  - "lrand48"
  - "Claude"
  - "密碼學"
sources:
  - name: "Anthropic：Claude reveals ECDSA curve origins（2026-10-16）"
    url: "https://www.anthropic.com/research/ecdsa-curve-origins"
  - name: "Steve Weis（@sweis）X 貼文：CLAUDE FOUND THE SEEDS"
    url: "https://x.com/sweis/status/2111165738836717980"
  - name: "NIST：FIPS 186-5 Digital Signature Standard (DSS)"
    url: "https://csrc.nist.gov/pubs/fips/186-5/final"
  - name: "IETF RFC 8446：The Transport Layer Security (TLS) Protocol Version 1.3"
    url: "https://www.rfc-editor.org/rfc/rfc8446"
  - name: "Cloudflare：ECDSA: The digital signature algorithm of a better internet（2014-03-10）"
    url: "https://blog.cloudflare.com/ecdsa-the-digital-signature-algorithm-of-a-better-internet/"
---

密碼學界有個懸了二十多年的小謎題：網路上廣泛使用的幾條加密曲線，參數裡那串「種子」到底從哪來？Anthropic 10 月 16 日發表研究文章說，Claude 已經找到答案：種子是 1997 年前後一支常見亂數函式的輸出，啟動時用的是當下的時間。

先說結論：這不是破解加密，也沒有發現新弱點。Anthropic 在文章開頭就請讀者放心：

> 「不需要採取任何行動，也不必改變任何做法。」
>
> "There is no action to be taken or things to do differently."（原文開頭導言）

## 這些曲線是加密的基礎，種子來歷卻一直沒人說得清

ECDSA 是「橢圓曲線數位簽章演算法」，用來證明資料確實出自某人且未被竄改，網站憑證等許多地方都會用到。美國國家標準暨技術研究院（NIST）在 2000 年把它納入 FIPS 186-2 標準，並列出一組標準曲線，P-256 就是其中之一。

每條曲線的部分參數，是把一串公開的「種子」拿去雜湊（把資料打散成固定長度數字的運算）算出來的。問題在於，這些種子由美國國家安全局（NSA）提供，從未說明怎麼產生。外界因此懷疑，種子會不會是刻意挑過、藏有後門。

過去最流行的說法，來自 NSA 前員工 Jerry Solinas 在 2015 年的回憶：種子是一句玩笑話的雜湊值，例如「Give Bob and Jerry a raise」。他已在 2023 年過世，這條線索始終沒有結果，社群還為此設了懸賞。

## Claude 換個角度，查出種子是 1997 年的亂數輸出

Anthropic 幾位員工曾照這條線索找過，都沒成功。2026 年 10 月，一名員工請內部研究模型試試看，而且沒有給它這條線索。結果 Claude 不到半小時就查出 P-192、P-224、P-256、P-384 和 P-521 的種子來歷。

> 「它們全都不是任何雜湊演算法的結果。」
>
> "None of them were the results of any hash algorithm at all"（原文「Claude found the seeds」一節）

這些種子其實是 C 語言函式庫內建亂數函式 lrand48 的輸出，並以 Unix 時間戳（電腦記錄時間的數字）作為起點。程式每次抽出 20 個位元組當作候選種子，P-256 用的是第 1842 個候選。

## Claude 從老式亂數的「指紋」一路推回產生時間

Claude 先猜當年的軟體怎麼寫。1990 年代 C 語言內建的亂數函式很弱，輸出有可辨認的規律。它寫了掃描程式，比對 34 種組合，發現其中四顆種子每一段的最高位元都是 0，偶然出現的機率只有 5810 分之 1，這正是 lrand48 的特徵。

接著它還原亂數函式的內部狀態（質數體曲線種子要用「格」方法），再往回推出啟動時的時間戳。十顆質數體曲線種子（含五條 NIST 曲線）都對應到 1997 年 5 月到 1998 年 4 月之間；另外四顆二元體曲線的種子，推測對應到 1998 年 4 月 17 日。原文附有可重現的程式碼，本站執行後，P-256 的輸出確實和公開種子一致。

Claude 還查出包括 P-192 在內六條曲線的「基準點」（曲線固定使用的起始點）來源。Anthropic 說，就他們所知，這是 NIST 基準點首度得到解釋。

## 這項發現沒有削弱加密的安全性，反而讓 Anthropic 更相信曲線沒有後門

> 「這不是密碼學上的破解、新攻擊，也不是 ECDSA 曲線的弱點。」
>
> "This is not a cryptographic break, new attack, or weakness in the ECDSA curves."（原文「What this means」一節）

Anthropic 的解讀是，種子產生方式非常單純：一支常見的亂數函式從時鐘取值啟動，任何人都能重現。動手腳的空間因此小很多，曲線被刻意植入後門的說法更難成立，他們也因此更有把握這些參數是安全的。原文也說，多數研究者本來就信任這些曲線。

## 仍有一顆種子與多數 NIST 基準點的來歷沒有解開

原文也列出未解之處。第一，有些看起來可用的候選曲線被跳過了：P-256 的第 876 個候選也符合條件，最後卻用第 1842 個；P-224 跳過三條，ANSI X9.62 範例曲線又跳過七條。

> 「我們不知道當時用了什麼標準，也不知道這是不是無意間造成的結果。」
>
> "We do not know what criteria may have been used, or whether this was an unintentional artifact."（原文「Open questions」一節）

Anthropic 認為被跳過的數量很少，不太可能是刻意挑出弱曲線，但也承認理論上仍可能有人試過多個時間戳。第二，二元體曲線 B-163 的種子至今無法解釋。第三，P-224、P-256、P-384、P-521 與 NIST 二元體曲線的基準點怎麼產生，仍然不知道。

研究作者之一 Steve Weis 在他的 X 貼文中只寫了「CLAUDE FOUND THE SEEDS」（貼文連結列在文末來源），截至台灣時間 10 月 17 日下午 2 點 06 分，曝光次數已超過 320 萬。懸賞金 36,864 美元將捐給 Internet Security Research Group。

本站昨天報導 [OpenAI 總裁談 AI 已能產生新知識]({{ site.baseurl }}{% post_url 2026-10-16-greg-brockman-no-priors %})，這次是 AI 參與研究的另一例，而 Claude 解開的是一樁歷史懸案，現行加密的安全並未因此動搖。

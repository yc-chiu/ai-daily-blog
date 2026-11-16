---
layout: post
title: "Meta Superintelligence Labs 產品副總 Mona Sarantakos：消費級 AI 代理要先被信任才上線｜Lenny 訪談精讀"
date: 2026-11-16 09:51:00 +0800
summary: "Meta Superintelligence Labs 產品副總 Mona Sarantakos 上 Lenny's Podcast，談 Muse 這款消費級 AI 代理怎麼做出來。她表示，春天時已有完整可用的產品，之後把時間花在可靠度、安全與資安上，不急著上線；節目也談到讓代理屬於使用者、用代理群整理回饋，以及口耳相傳與第一個指令如何影響新用戶。"
cover: "/assets/images/posts/2026-11-16-meta-muse-mona-sarantakos/cover.png"
cover_alt: "深藍底融合 Meta 總部入口「1 Hacker Way」標示牌與樹木、天空的實拍照片；左側標題為「Lenny's Podcast 專訪 Meta 產品副總」，副標為「談 Muse 為何不急著上線」。"
cover_credit: "圖片來源：[LPS.1](https://commons.wikimedia.org/wiki/User:LPS.1)／[Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Meta_Platforms_Headquarters_Menlo_Park_California.jpg)，[CC0](https://creativecommons.org/publicdomain/zero/1.0/)；經裁切、漸層合成與加字。"
tags:
  - "訪談精讀"
  - "Lenny's Podcast"
  - "Muse"
  - "AI 代理"
  - "Meta"
sources:
  - name: "Lenny's Podcast：Meta's Muse: How we launched the most successful consumer product this year | Mona Sarantakos（YouTube）"
    url: "https://www.youtube.com/watch?v=WY0cdD4gNoQ"
  - name: "Lenny's Newsletter：Meta's Muse: How we launched the most successful consumer product this year（節目頁）"
    url: "https://www.lennysnewsletter.com/p/metas-muse-how-we-launched-the-most"
  - name: "Lenny's Podcast 公開逐字稿資料夾（Dropbox，檔案「Mona Sarantakos_V2.txt」）"
    url: "https://www.dropbox.com/scl/fo/yxi4s2w998p1gvtpu4193/AMdNPR8AOw0lMklwtnC0TrQ?rlkey=j06x0nipoti519e0xgm23zsn9&st=ahz0fj11&dl=0"
---

Muse 是 Meta 推出的個人 AI 代理；依訪談內容，使用者會讓它購物、規劃餐點、安排約診。節目介紹寫道，Muse 是 App Store 第一名的 App，並稱它「可說是史上成長最快的消費級 AI 產品」（"arguably the fastest-growing AI consumer product of all time"），這是節目方的說法。來賓 Mona Sarantakos 是 Meta Superintelligence Labs 產品副總（VP of Product），從第一天起就負責 Muse 的產品，節目介紹也說這是她第一次上 Podcast。這集 Lenny's Podcast 長 1 小時 27 分，談的不是模型規格，而是一款消費級代理從試作到上線，團隊怎麼做取捨。

本文引述皆出自 Lenny's Podcast 公開分享的[逐字稿資料夾](https://www.dropbox.com/scl/fo/yxi4s2w998p1gvtpu4193/AMdNPR8AOw0lMklwtnC0TrQ?rlkey=j06x0nipoti519e0xgm23zsn9&st=ahz0fj11&dl=0)中的「Mona Sarantakos_V2.txt」，時間點連結依逐字稿時間戳。

<div style="position:relative;width:100%;aspect-ratio:16/9;"><iframe src="https://www.youtube-nocookie.com/embed/WY0cdD4gNoQ" title="Lenny's Podcast：Meta's Muse: How we launched the most successful consumer product this year | Mona Sarantakos" style="position:absolute;inset:0;width:100%;height:100%;border:0;" loading="lazy" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe></div>

本站在 10 月寫過 [Muse Spark Open]({{ site.baseurl }}{% post_url 2026-10-16-muse-spark-open %})，那篇談的是開放權重模型；這集談的則是建在模型之上的 Muse 這款產品。Sarantakos 提到，團隊拿到的第一款 Muse Spark 模型，比預期更擅長代理式任務。

## Sarantakos 認為代理不被信任就不會有人用，所以寧可晚上線

Lenny 說，依他讀到的資料，Muse 從開始到上線花了七個月，比其他熱門 AI 助理久。Sarantakos 表示，春天時團隊已有完整可用的產品，之後大量時間花在可靠度、安全與資安上；每加一個功能，例如瀏覽器，就多出新的資安破口要堵。團隊內部有句話叫 trust is a must，她說：「如果你不信任這個代理，就永遠不會用它。」（"if you don't trust the agent, you're never going to use it"）[回看 12:54](https://www.youtube.com/watch?v=WY0cdD4gNoQ&t=774s)

她說，業界現有的基準測試不足以衡量一款握有個人資料、還能替人花錢的產品，團隊必須自己訂標準、花很多時間做紅隊測試；上線前也逐步擴大內部員工與外部測試者的人數，整個夏天都在收集真實回饋。她表示，團隊花了需要的時間才做到這一步，她很慶幸當時這麼做，因為到目前為止還沒有出過災難性的問題。

## Sarantakos 認為個人代理要屬於使用者，所以留下了 Jolly

Muse 介面上方的小角色 Jolly，原本只是設計師做原型時放的暫時圖案。Sarantakos 說，幾乎每隔幾個月就有人說不能帶著填充玩偶上線，但團隊堅持保留，因為和感覺很私人的對象對話時，「你最不想對著說話的就是企業標誌」（"the last thing you want to talk to is a corporate logo"）[回看 26:08](https://www.youtube.com/watch?v=WY0cdD4gNoQ&t=1568s)。

她把這歸結為產品原則：Meta 要退到後面，因為「代理要為你工作」（"the agent needs to work for you"）[回看 28:51](https://www.youtube.com/watch?v=WY0cdD4gNoQ&t=1731s)。使用者也能把頭像換成自己想要的樣子。

## Sarantakos 認為評估要靠真實資料，關鍵文字仍要人手寫

Sarantakos 表示，原本預期的重點用途是個人生產力、健康與個人理財，購物卻意外成為主要用途之一：「我沒想到購物會變成這麼大的用途」（"I did not think shopping was going to be as big of a use case as it's become"）[回看 32:04](https://www.youtube.com/watch?v=WY0cdD4gNoQ&t=1924s)。團隊因此回頭為購物補上評估。另一個難題是資料：她說過去 Meta AI 的對話多半一問一答，Muse 卻是來回多輪的長任務，手上沒有這類資料，所以靠代理群收集與整理，現在每遇到可疑問題，工程師就會「swarm it」去查。

她說，評估分成安全、能力、行為與用途幾大類，安全類是任何改動都必須通過的門檻。團隊大量使用代理協助，但有一條規矩：「我們的系統提示詞必須手寫」（"our system prompt has to be handwritten"）[回看 45:10](https://www.youtube.com/watch?v=WY0cdD4gNoQ&t=2710s)，行為規格也一樣。

## Sarantakos 認為新用戶卡在第一句話，口耳相傳最有效

談到怎麼讓新用戶真正用起來，她說：「最有效的槓桿是口耳相傳」（"the most effective lever out there is word of mouth"）[回看 47:21](https://www.youtube.com/watch?v=WY0cdD4gNoQ&t=2841s)。她舉例，一位家長把手機遞給其他家長看自己怎麼用 Muse，當場就有兩個人下載。

第二個槓桿是第一個指令，因為「大家在第一個指令就卡住」（"people freeze on the first prompt"）[回看 48:54](https://www.youtube.com/watch?v=WY0cdD4gNoQ&t=2934s)。她也表示，早期用戶本來就懂代理，後來的用戶則會問這和其他 AI 有什麼不同，所以團隊改用分層的新手引導。

## Sarantakos 認為 PM 最重要的能力變成產品品味

她說，原型人人都能做，討論從抽象變得具體，「產品品味現在是最重要的事」（"product taste now is the most important thing"）[回看 1:05:02](https://www.youtube.com/watch?v=WY0cdD4gNoQ&t=3902s)。原因是 AI 讓粗糙產品很容易推出去，PM 要替使用者把關品質。她也坦言，用的人越多責任越重，因為使用者交給代理的事情越來越多，例如一位單親媽媽讓代理幫忙找醫師、安排約診，她說看著覺得很了不起，同時也很害怕。

## 提到的工具與用法顯示團隊把代理也用在自己身上

- Sarantakos 說，起點是她在週末把 OpenClaw 架在樹莓派上，接上電子郵件與行事曆，週一早上收到它整理的學校通知摘要，後來才換成 Mac Mini。
- 代理群（agent swarms）：派出一群代理整理使用者對話與回饋，也能產生合成資料，用來補足多輪對話的評估資料。
- Muse 的「ideas」分頁提供預先包好的入門範例，使用者只要回一句「let's do it」，Muse 就開始動手；另有呈現使用者目標的「goals」分頁。
- Sentinel：她提到團隊做了一套獨立於 Muse 核心代理之外的防護機制。

## 產業脈動指向代理購物與隨身裝置

Sarantakos 預期，零售商與店家也會有自己的代理，消費者的代理和商家的代理可以直接溝通；但她認為逛街、找靈感的樂趣不該被拿掉。談到下一步，她說 Muse 目前「困在 App 裡」（"trapped in an app"）[回看 1:21:09](https://www.youtube.com/watch?v=WY0cdD4gNoQ&t=4869s)，之後應該出現在眼鏡等裝置上。她也坦言，現在照顧代理太花力氣：「如果我得一直照顧代理，那我還不如自己做」（"at the point where I'm babysitting an agent, I might as well do it myself"）[回看 1:22:11](https://www.youtube.com/watch?v=WY0cdD4gNoQ&t=4931s)。

Lenny 在節目後段也提到 Muse 是「史上成長最快的消費級 AI App，據說如此」（"the fastest growing AI consumer app in history, allegedly"）[回看 1:18:32](https://www.youtube.com/watch?v=WY0cdD4gNoQ&t=4712s)，這是主持人的說法。

## 對你的意義在於先想清楚信任與第一個任務

本站認為，這集最值得帶走的是 Muse 團隊對信任的態度：代理要能替人花錢、碰個人資料，上線前要先問「出錯時誰承擔」。本站建議，如果你正要讓團隊試用 AI 代理，先挑一件低風險、天天都會發生的小事，例如整理通知或排行程，讓大家先看到別人怎麼用；需要授權帳號或付款的任務，等確認防護機制之後再交給它。

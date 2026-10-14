---
layout: post
title: "AI 醫生助理走進真實診間：Google AMIE 登上 The Lancet，從模擬考到真病人的近三年路"
date: 2026-10-13 08:00:00 +0800
summary: "Google 的醫療對話 AI「AMIE」首度在真實基層門診接受前瞻性研究，成果刊登於 The Lancet：98 位病人完成全程，醫師監督員一次都不必喊停。本文帶你看懂這項研究、AMIE 的發展歷程，以及 AI 進入醫療時醫師角色與倫理的新問題。"
tags:
  - "Google"
  - "AMIE"
  - "醫療 AI"
  - "大型語言模型"
  - "AI 倫理"
cover: /assets/images/posts/2026-10-13-google-amie/cover.jpg
cover_alt: "聽診器放在筆記型電腦鍵盤上的特寫，象徵數位醫療（照片：Daniel Sone / National Cancer Institute，公有領域）"
cover_credit: "照片：Daniel Sone／美國國家癌症研究所（NCI），來源：[Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Stethoscope_and_Laptop_Computer_-_Nci-vol-9713-300.jpg)，公有領域；已裁切為 16:9 並縮放。"
sources:
  - name: "The Lancet：Conversational diagnostic artificial intelligence in ambulatory primary care: a prospective feasibility study"
    url: "https://doi.org/10.1016/S0140-6736(26)01535-7"
  - name: "PubMed：Conversational diagnostic artificial intelligence in ambulatory primary care（PMID 42849491）"
    url: "https://pubmed.ncbi.nlm.nih.gov/42849491/"
  - name: "Google Research：Conversational diagnostic AI in ambulatory primary care（論文摘要頁）"
    url: "https://research.google/pubs/a-prospective-clinical-feasibility-study-of-a-conversational-diagnostic-ai-in-an-ambulatory-primary-care-clinic/"
  - name: "Google Research Blog：Exploring the feasibility of conversational diagnostic AI in a real-world clinical study"
    url: "https://research.google/blog/exploring-the-feasibility-of-conversational-diagnostic-ai-in-a-real-world-clinical-study/"
  - name: "arXiv：A prospective clinical feasibility study of a conversational diagnostic AI in an ambulatory primary care clinic"
    url: "https://arxiv.org/abs/2603.08448"
  - name: "BIDMC 新聞稿（Newswise）：First Real-World Study of Safety and Quality of Patient-Facing AI in Primary Care"
    url: "https://www.newswise.com/articles/bidmc-researchers-conduct-first-real-world-study-of-safety-and-quality-of-patient-facing-ai-in-primary-care"
  - name: "ClinicalTrials.gov：NCT06911398"
    url: "https://clinicaltrials.gov/study/NCT06911398"
  - name: "arXiv：Towards Conversational Diagnostic AI（2024）"
    url: "https://arxiv.org/abs/2401.05654"
  - name: "Google Research Blog：AMIE: A research AI system for diagnostic medical reasoning and conversations"
    url: "https://research.google/blog/amie-a-research-ai-system-for-diagnostic-medical-reasoning-and-conversations/"
  - name: "Nature：Towards conversational diagnostic artificial intelligence"
    url: "https://www.nature.com/articles/s41586-025-08866-7"
  - name: "Nature：Towards accurate differential diagnosis with large language models"
    url: "https://www.nature.com/articles/s41586-025-08869-4"
  - name: "Google Research Blog：Advancing AMIE towards specialist care and real-world validation"
    url: "https://research.google/blog/advancing-amie-towards-specialist-care-and-real-world-validation/"
  - name: "Google Research Blog：From diagnosis to treatment: Advancing AMIE for longitudinal disease management"
    url: "https://research.google/blog/from-diagnosis-to-treatment-advancing-amie-for-longitudinal-disease-management/"
  - name: "Nature：Towards conversational artificial intelligence for disease management"
    url: "https://www.nature.com/articles/s41586-026-10764-5"
  - name: "Google Blog：New research shows how AMIE, our medical AI, could help manage health conditions"
    url: "https://blog.google/innovation-and-ai/models-and-research/google-research/amie-for-disease-management-in-nature/"
  - name: "Google Research Blog：AMIE gains vision: A research AI agent for multimodal diagnostic dialogue"
    url: "https://research.google/blog/amie-gains-vision-a-research-ai-agent-for-multi-modal-diagnostic-dialogue/"
  - name: "Nature Medicine：Advancing conversational diagnostic AI with multimodal reasoning"
    url: "https://www.nature.com/articles/s41591-026-04371-0"
  - name: "Google Research Blog：Enabling physician-centered oversight for AMIE"
    url: "https://research.google/blog/enabling-physician-centered-oversight-for-amie/"
  - name: "arXiv：Towards Expert-level Medical AI for Real-time Video Consultations"
    url: "https://arxiv.org/abs/2608.09861"
  - name: "WHO：Ethics and governance of artificial intelligence for health"
    url: "https://www.who.int/publications/i/item/9789240029200"
  - name: "WHO：Guidance on large multi-modal models"
    url: "https://www.who.int/publications/i/item/9789240084759"
  - name: "MIT OpenCourseWare：Machine Learning for Healthcare"
    url: "https://ocw.mit.edu/courses/6-s897-machine-learning-for-healthcare-spring-2019/"
  - name: "Coursera（Stanford Online）：AI in Healthcare Specialization"
    url: "https://www.coursera.org/specializations/ai-healthcare"
  - name: "臺大李宏毅：生成式 AI 與機器學習導論 2025 Fall"
    url: "https://speech.ee.ntu.edu.tw/~hylee/GenAI-ML/2025-fall.php"
  - name: "Elements of AI（赫爾辛基大學）"
    url: "https://www.elementsofai.com/"
  - name: "Google for Developers：Health AI Developer Foundations"
    url: "https://developers.google.com/health-ai-developer-foundations"
---

想像一下：你預約了家醫科門診，看診前幾天先在網頁上和一個 AI 聊天，它問你哪裡不舒服、症狀持續多久、有沒有吃什麼藥，最後整理成一份摘要交給醫師。等你走進診間，醫師已經掌握了大致情況。這不是科幻情節，而是 Google 的醫療對話 AI「AMIE」剛完成的一項真實研究。

## 這次發生了什麼：AMIE 第一次面對真病人

AMIE 是 Articulate Medical Intelligence Explorer 的縮寫，是 Google 打造的「研究用」醫療對話系統，並不是上市產品。美東時間 10 月 8 日，美國波士頓的貝斯以色列女執事醫療中心（BIDMC）發布新聞稿，宣布雙方合作的研究已於同日在頂尖醫學期刊 The Lancet 線上搶先刊出（DOI：10.1016/S0140-6736(26)01535-7；卷期尚未編定）。

這是一項「前瞻性、單中心、單臂可行性研究」。拆開來說：**前瞻性**是先設計好再招募病人、往後追蹤，而不是回頭翻舊病歷；**單臂**表示所有參與者都用 AMIE，沒有對照組；**可行性研究**的目的是確認「這件事能不能安全地做」，而不是證明「AI 能改善健康」。

研究於 2025 年 4 月到 11 月在 BIDMC 的基層門診進行，對象是因單一新症狀、預約非緊急門診的成年英語病人。他們在看診前最多 5 天用文字和 AMIE 對談，全程都有一位醫師透過視訊即時監看，一旦出現傷害風險、病人明顯情緒困擾、可能造成臨床危害或病人要求結束，就會按下「安全暫停」。主要結果如下：

- 共招募 114 人，其中 98 人完成 AMIE 對談與門診。
- 依預先設定的標準，**安全暫停次數為零**；不過監督醫師記錄到 1 次「幻覺」（AI 說出不正確的內容），並在 5 次對談中補充臨床資訊。
- 臨床評估者在 17 項指標上，有 87% 到 100% 的個案給予正面評價；病人在 16 項指標上的正面評價比例為 48% 到 96%。
- 病人對 AI 的態度在使用後變得更正面，看完醫師後仍維持。
- 在醫師事先看過對談紀錄的 44 個案例中，有 33 例認為有助於看診準備，25 例表示可能改變了自己的做法。

![The Lancet 研究重點數字：招募 114 人、98 人完成；安全暫停 0 次；監督醫師記錄到 1 次幻覺；醫師事先看過對談紀錄的 44 個案例中，33 例認為有助看診準備]({{ '/assets/images/posts/2026-10-13-google-amie/lancet-trial-key-numbers.png' | relative_url }})

Google 於 2026 年 3 月公開的預印本（arXiv 2603.08448，v3）與同期研究部落格還提到：以看診 8 週後的病歷回顧為準，AMIE 列出的「鑑別診斷」（可能疾病清單，最多前 7 名）在 90% 的個案中包含最終診斷，前三名命中率 75%；這兩個數字未出現在 The Lancet 正式版摘要中。同一份預印本的盲測評估中，雙方診斷與處置計畫的整體品質相近，但醫師在處置計畫的「實用性」與「成本效益」上明顯勝出。研究團隊解釋，AMIE 看不到電子病歷，也無法做身體檢查。

## 從模擬考到真實診間：AMIE 的研究時間線

![AMIE 研究時間線，2024 年 1 月首篇預印本到 2026 年 10 月登上 The Lancet，共十個里程碑]({{ '/assets/images/posts/2026-10-13-google-amie/amie-timeline-2024-2026.png' | relative_url }})

- **2024 年 1 月**：預印本〈Towards Conversational Diagnostic AI〉首度亮相。團隊讓 AMIE 在模擬環境中「自我對弈」（self-play），自己扮演醫師、病人與評論者來練習問診。測驗採醫學生熟悉的 OSCE（客觀結構式臨床測驗），由受訓演員扮演病人，與 20 位基層醫師進行雙盲比較。
- **2024 年 12 月**：Google 發表 AMIE 挑戰次專科的成果，與史丹佛合作評估遺傳性心肌病變的 204 個真實個案，並與休士頓衛理公會醫院合作釋出 50 個合成乳癌病例；同時宣布與 BIDMC 展開真實世界研究。
- **2025 年 3 月**：AMIE 從「診斷」延伸到「長期疾病管理」，以雙代理人架構跨多次回診追蹤病情，並參照英國 NICE、BMJ Best Practice 等臨床指引。
- **2025 年 4 月**：兩篇論文登上《Nature》。對話診斷論文的正式版包含 159 個情境，AMIE 在專科醫師評分的 32 項中有 30 項勝出；另一篇指出，在 302 個困難病例中，有 AMIE 協助的醫師前十名診斷準確率為 51.7%，高於只用搜尋工具的 44.4%。
- **2025 年 5 月**：「多模態 AMIE」能在對話中要求並判讀皮膚照片、心電圖和文件（2026 年 5 月刊登於《Nature Medicine》）。
- **2025 年 8 月**：「護欄版 AMIE」（g-AMIE）只負責問診、不給個人化醫療建議，再交由醫師審核、核可後才回覆病人。
- **2026 年 6 月**：疾病管理研究刊登於《Nature》，在 100 個多次回診情境中，AMIE 的管理推理不輸 21 位基層醫師。
- **2026 年 8 月**：預印本展示可即時視訊看診的 AMIE（Video）。
- **2026 年 10 月**：BIDMC 真實門診研究於 The Lancet 線上刊出。

## 小知識：AMIE 是怎麼「練習看病」的？

真實的醫病對話錄音很珍貴，但疾病種類有限，內容也充滿口語、打斷和雜訊。2024 年的第一篇論文因此設計了模擬練習場：AMIE 同時扮演醫師、病人和「主持人」，再由第四個角色擔任「評論者」，指出醫師角色哪裡問得不好，下一輪改進。改良後的對話再拿回來訓練模型，形成循環。回答病人前，AMIE 也會先在內部整理已知症狀、列出可能診斷、找出還缺什麼資訊，再組織回覆。在那份預印本中，AMIE 在 149 個情境裡，專科醫師評分 32 項中有 28 項、演員病人評分 26 項中有 24 項優於基層醫師。不過研究團隊自己也提醒：醫師不習慣純文字問診，這樣的比較可能對醫師不利。

## 誰在做這項研究？

AMIE 由 Google Research 與 Google DeepMind 共同研發，真實門診研究也有 Google for Health 團隊參與。臨床合作夥伴包括 BIDMC 與其所屬的 Beth Israel Lahey Health、哈佛醫學院，以及次專科研究中的史丹佛大學、休士頓衛理公會醫院。值得注意的是，這項研究由 Alphabet 出資，BIDMC 的共同主持人 Adam Rodman 醫師在研究期間曾擔任 Google 訪問研究員。讀研究時，知道「誰出錢、誰參與」是基本功。

## 可能用在哪裡？

- **看診前問診**：先整理病史，讓醫師把時間花在確認與討論。參與研究的基層醫師形容，看診從「蒐集資料」轉為「驗證資料」。
- **協助醫師鑑別診斷**：在困難病例中提供更完整的可能疾病清單。
- **補足專科人力缺口**：在缺乏次專科醫師的地方，協助一般醫師判斷是否需要轉診。
- **慢性病追蹤**：跨多次回診追蹤用藥與檢查，並對照臨床指引。

## 冷靜看待：醫師角色、風險與倫理

第一，**這不是「AI 取代醫師」**。在研究設計中，AMIE 一直處於醫師監督之下。BIDMC 基層醫療臨床主任、論文共同資深作者 Marc L. Cohen 醫師說，他們看見的未來是「病人、醫師、AI」三方合作。

第二，**限制很明確**。沒有對照組，無法證明 AMIE 能改善健康結果；只納入說英語的成人，參與者也比同期門診病人整體年輕；介面也只有文字。

第三，**信任與隱私**。病人對 AMIE 的傾聽與解說評價很高，但對「資料是否保密」和「AI 是否誠實」仍有疑慮。曾有醫師回報，AMIE 把淋巴癌列入可能診斷，讓病人感到焦慮。AI 說出的每一句話，都可能真實影響一個人的情緒與決定。

第四，**監督也有成本**。g-AMIE 研究發現，醫師審核 AI 筆記很耗腦力，AI 寫得太冗長也會拉長審核時間。「醫師把關」不是一句口號，而是需要設計的工作流程。

## 想深入了解？從這裡開始

**相關科系**：醫學系、資訊工程、生醫工程、生物醫學資訊、公共衛生與統計。醫療 AI 是典型的跨領域工作，懂臨床的人與懂模型的人缺一不可。

**公開課程與資源**：
- 臺大李宏毅教授的「生成式 AI 與機器學習導論」，有中文講解，適合入門。
- 赫爾辛基大學的 Elements of AI，給非理工背景讀者的免費 AI 入門課。
- MIT OpenCourseWare 的「Machine Learning for Healthcare」，進一步了解醫療資料的特性。
- Stanford Online 在 Coursera 開設的「AI in Healthcare」系列課程。
- 世界衛生組織（WHO）的醫療 AI 倫理與治理指引，以及針對大型多模態模型的補充指引。
- 想動手實作，可以參考 Google 的 Health AI Developer Foundations 開發資源。

如果只想讀一篇原文，推薦 Google Research 部落格上的這次研究說明，圖表清楚，也坦白交代了研究限制。

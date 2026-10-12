---
# 複製本檔到 _posts/，檔名必須是：
#   _posts/YYYY-MM-DD-英文代稱.md
# 例如 _posts/2026-10-13-model-roundup.md
# 檔名中的日期要和下面的 date 是同一天。時區用 +0800（台灣）。
# 尚未審閱的稿子先放 _drafts/，檔名規則相同，正式發布再移到 _posts/。
#
# 站內圖片請放到 assets/images/，cover 填 /assets/images/檔名.jpg
# 不要自己加上 /ai-daily-blog，版型會處理 baseurl。
# 外部封面可直接填 https 開頭的網址。

layout: post
title: "文章標題"
date: 2026-10-13 08:00:00 +0800
summary: "一兩句話摘要。會出現在首頁、文章開頭與 RSS，請用純文字，不要加 Markdown。"
tags:
  - "標籤一"
  - "標籤二"
# 若這篇只是格式示範，改成 sample: true。頁面會標示「範例文章」，並請搜尋引擎不要索引。
# sample: true
# cover: /assets/images/covers/example.jpg
# cover_alt: "封面圖說明"
sources:
  - name: "來源名稱"
    url: "https://example.com/original-article"
  - name: "第二個來源"
    url: "https://example.com/another-article"
---

在這裡用 Markdown 寫正文。

## 小標

- 重點一
- 重點二

文末的「參考來源」會依前言的 `sources` 自動產生，不必在正文再貼一次。

---
layout: post
title: "【範例文章】文章格式示範"
date: 2026-10-12 08:00:00 +0800
summary: "這篇只示範每日快報的版面與欄位，內容是占位文字，不是真實的人工智慧新聞。"
tags:
  - 範例
  - 格式說明
sample: true
sitemap: false
cover: /assets/images/sample-cover.png
cover_alt: "範例文章的封面，圖上寫著範例文章，不是新聞配圖。"
sources:
  - name: "（格式示範）OpenAI 新聞列表"
    url: "https://openai.com/news/"
  - name: "（格式示範）Google DeepMind 部落格"
    url: "https://deepmind.google/blog/"
  - name: "（格式示範）Anthropic 新聞"
    url: "https://www.anthropic.com/news"
  - name: "（格式示範）Meta AI 部落格"
    url: "https://ai.meta.com/blog/"
---

正式刊出的每日快報，會在人工審閱後用一篇文章整理當天值得知道的事。下面這些段落是占位文字，用來展示小標、清單與引用長什麼樣子。這裡沒有描述任何真實事件。

## 今日重點

這裡會寫當天的重點。本篇故意不放入事件、數字或引言。

- 第一則占位重點。
- 第二則占位重點。
- 第三則占位重點。

## 文章裡會看到的格式

> 引用會以這樣的方式呈現。正式文章若摘錄公開說法，會註明出處。

文末的參考來源來自前言的 `sources` 欄位，正文不必再列一次。上面的連結只指向各機構的公開列表頁，用來示範格式，並不對應某一則新聞。

新的一天，複製 `templates/post.md`，存成 `_posts/` 裡的新檔案即可。欄位說明寫在儲存庫的 README，網站背景見[關於本站]({{ '/about/' | relative_url }})。

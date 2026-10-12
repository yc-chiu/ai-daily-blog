# AI 每日快報

版式用 jf open 粉圓與暖米配色，深色模式跟著系統外觀。字級、欄寬與色彩記在 [DESIGN.md](DESIGN.md)。

繁體中文的人工智慧每日整理。一天一篇，每篇是一個 Markdown 檔。網站用 Jekyll 寫成，由 GitHub Pages 從 `main` 分支直接建置。

啟用 Pages 之後的網址：<https://yc-chiu.github.io/ai-daily-blog/>

RSS：<https://yc-chiu.github.io/ai-daily-blog/feed.xml>

## 啟用 GitHub Pages

這個儲存庫使用 GitHub 內建的 Jekyll，不需要另外寫部署腳本。請先把變更合併到 `main`，再打開 Pages 設定。

1. 打開 <https://github.com/yc-chiu/ai-daily-blog/settings/pages>
2. 在 **Build and deployment（組建和部署）** 的 **Source（來源）** 選擇 **Deploy from a branch（從分支部署）**。
3. **Branch（分支）** 選 `main`，資料夾選 `/ (root)`。
4. 按 **Save（儲存）**。
5. 等一兩分鐘，頁面上方會出現網站網址。第一次啟用時重新整理即可。

請讓儲存庫保持公開。免費方案不能替私有儲存庫開啟 GitHub Pages。

`_config.yml` 裡的 `url` 是 `https://yc-chiu.github.io`，`baseurl` 是 `/ai-daily-blog`。站內連結請寫 `/about/`、`/assets/...` 這種根路徑，不要自己加上 `/ai-daily-blog`。

儲存庫裡的 GitHub Actions 只在推送與 pull request 時檢查網站能不能建置，不會取代 Pages 的發布。

## 新增一篇每日文章

1. 複製 [`templates/post.md`](templates/post.md)。
2. 存成 `_posts/YYYY-MM-DD-英文代稱.md`。例如 `_posts/2026-10-13-model-roundup.md`。
3. 填標題、日期、摘要、標籤、來源。有封面再填 `cover` 與 `cover_alt`。
4. 用 Markdown 寫正文。
5. 提交並推送到 `main`。Pages 會自動重新建置，新文章會出現在首頁最上面。

檔名裡的日期要和前言的 `date` 是同一天，時區寫 `+0800`。代稱用英文，網址會用這個代稱，不會用中文標題。

還沒審完的稿子放在 `_drafts/`，檔名規則相同。草稿不會被發布。本地預覽草稿：

```bash
bundle exec jekyll serve --drafts
```

## 前言欄位

| 欄位 | 必填 | 說明 |
| --- | --- | --- |
| `layout` | 建議 | 填 `post`。沒填的話，文章也會使用文章版型。 |
| `title` | 是 | 文章標題。 |
| `date` | 是 | `2026-10-13 08:00:00 +0800` 這種寫法。 |
| `summary` | 是 | 純文字摘要。首頁、文章開頭和 RSS 都用這段。 |
| `tags` | 否 | 字串清單。標籤頁會自動彙整。 |
| `sources` | 否 | 清單。每一項有 `name` 和 `url`。文章頁底會變成「參考來源」。 |
| `cover` | 否 | 封面。站內路徑以 `/` 開頭，例如 `/assets/images/covers/example.jpg`；也可以填 `https://` 開頭的網址。 |
| `cover_alt` | 有封面時請填 | 封面的替代文字。 |
| `sample` | 否 | 設成 `true` 時，頁面會標示「範例文章」，並加上 `noindex`。 |

封面圖放在 `assets/images/`。橫圖約 1200×675 即可。

## 本地預覽

需要 Ruby 3.2 與 Bundler。

```bash
bundle install
bundle exec jekyll serve
```

瀏覽器打開 <http://127.0.0.1:4000/ai-daily-blog/>。

只建置、不開伺服器：

```bash
script/check
```

這個指令會建置網站，並確認首頁、文章頁、標籤頁、關於頁、RSS 與 `baseurl` 都正確。

## 目錄

```text
_config.yml          網站設定，含網址與 baseurl
_posts/              已發布的文章，一天一篇
_drafts/             審閱中的草稿，不會公開
templates/post.md    複製這份來寫新文章
_layouts/            版型
assets/              樣式、圖示、封面
about.md             關於頁
tags.html            標籤頁
feed.xml             RSS
index.html           首頁
```

## 範例文章

示範用的 `_posts/2026-10-12-sample-post.md` 與封面圖已刪除。新文章請複製 [`templates/post.md`](templates/post.md)。若某篇只是格式示範，在前言設 `sample: true`，頁面會標示「範例文章」。

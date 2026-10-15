---
layout: post
title: "Dyna Robotics 首席科學家 Jason Ma：讓機器人先「預測未來」，再走進鼎泰豐｜訪談精讀"
date: 2026-10-15 07:30:00 +0800
summary: "Dyna Robotics 共同創辦人暨首席科學家 Jason Ma 上《Latent Space》，談世界動作模型如何讓機器人先預測未來再行動、機器人沒有「網際網路」可學的資料瓶頸，以及從試點走到鼎泰豐規模化部署的距離。"
cover: /assets/images/posts/2026-10-15-dyna-robotics-jason-ma/cover.png
cover_alt: "深色背景上的 UR16e 協作機械手臂與操作面板，左側大字標題「讓機器人先「預測未來」再走進鼎泰豐」，下方為 Dyna Robotics 首席科學家 Jason Ma 與 YouTube 節目 Latent Space"
cover_credit: "照片：[Auledas](https://commons.wikimedia.org/wiki/User:Auledas)／[Wikimedia Commons](https://commons.wikimedia.org/wiki/File:UR16e_robot_arm.png)，[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)；已鋪深色底、裁切、調暗調色並加上文字，衍生封面同樣以 CC BY-SA 4.0 授權。"
tags:
  - "訪談精讀"
  - "機器人"
  - "實體 AI"
  - "世界模型"
  - "AI 代理"
sources:
  - name: "Latent Space（YouTube）：The Million-Hour Robot Brain: Dyna-2 & World Models — Jason Ma, Dyna Robotics"
    url: "https://www.youtube.com/watch?v=BHiYomkfoGQ"
  - name: "Latent Space：Dyna-2: General Purpose Physical Agents with Hour-Long Autonomy — Jason Ma, Dyna Robotics（含逐字稿）"
    url: "https://www.latent.space/p/dyna"
  - name: "DYNA：Dyna-2: A 1-Million-Hour Scaling Law for World-Action Models（2026 年 8 月）"
    url: "https://www.dyna.co/dyna-2"
  - name: "DYNA：Not Just a Model, But a Product（2026 年 8 月）"
    url: "https://www.dyna.co/research/scaling-customer-deployments"
  - name: "PR Newswire：Dyna Robotics Raises $23.5 Million to Commercialize Embodied AI with Low-Cost Robots（2025-03-25）"
    url: "https://www.prnewswire.com/news-releases/dyna-robotics-raises-23-5-million-to-commercialize-embodied-ai-with-low-cost-robots-302410263.html"
  - name: "PR Newswire：Dyna Robotics Raises $120 Million to Advance Robotic Foundation Models（2025-09-15）"
    url: "https://www.prnewswire.com/news-releases/dyna-robotics-raises-120-million-to-advance-robotic-foundation-models-on-the-path-to-physical-artificial-general-intelligence-302556817.html"
  - name: "arXiv：Eureka: Human-level Reward Design via Coding Large Language Models"
    url: "https://arxiv.org/abs/2310.12931"
---

這次「訪談精讀」的主角是 Dyna Robotics 共同創辦人暨首席科學家 Jason Ma。Dyna 是一家做通用機器人的灣區公司，另外兩位創辦人 Lindon Gao 與 York Yang 曾創辦智慧購物車公司 Caper AI，並以 3.5 億美元出售；Jason Ma 則曾在 Google DeepMind 擔任研究科學家，在 NVIDIA 時是 Eureka 論文的第一作者。

節目是 AI 工程師圈常聽的 Podcast《Latent Space》。主持人 swyx 與 Vibhu 直接到 Dyna 辦公室錄影。YouTube 版長約 1 小時 21 分，於台灣時間 10 月 14 日凌晨 1 點 42 分上架（美國時間 10 月 13 日）。值得看的原因很簡單：台灣人熟悉的鼎泰豐，美國分店正用 Dyna 的機器人摺餐巾。這集談的是機器人怎麼真正上工，而不只是 demo。

以下依 YouTube 英文字幕整理；字幕沒有標出說話者，我們對照 latent.space 官方逐字稿確認；中文為本站翻譯。

<div style="position:relative;width:100%;aspect-ratio:16/9;"><iframe src="https://www.youtube-nocookie.com/embed/BHiYomkfoGQ" title="Latent Space：The Million-Hour Robot Brain: Dyna-2 & World Models — Jason Ma, Dyna Robotics" style="position:absolute;inset:0;width:100%;height:100%;border:0;" loading="lazy" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe></div>

## 核心觀點

### 一、世界動作模型：先在腦中預演，再動手

Jason 說，Dyna 8 月發表的 Dyna-2 是一種「世界動作模型」（world action model）。輸入是攝影機畫面、機器人各關節的角度和語言指令；輸出除了動作，還能預測接下來的畫面。他用語言模型的「思維鏈」來比喻：

> 「這有點像思維鏈：模型先在視覺與物理的空間裡推理，再輸出動作。」
>
> "kind of analogous to … chain of thought" — [4:49](https://www.youtube.com/watch?v=BHiYomkfoGQ&t=289s)

他的理由是，人在行動時，腦中也會先推想世界會怎麼變化。談到另一條路線「視覺語言動作模型」（VLA），他認為 VLA 只預測動作或較抽象的表示，等於把人的偏見放進模型；最根本的做法是盡量預測整個世界，因為「你必須能預測未來」（"you need to be able to predict the future"，[56:51](https://www.youtube.com/watch?v=BHiYomkfoGQ&t=3411s)）。他也坦承自己可能錯在哪：如果有人做出「視覺加觸覺」的世界模型，資料效率可能高出百倍（[59:15](https://www.youtube.com/watch?v=BHiYomkfoGQ&t=3555s)）。（補充：Dyna 技術報告指出，用於規模實驗的版本推論時並不生成未來畫面，預測畫面主要在訓練時幫模型理解世界。）

### 二、機器人沒有網際網路，資料是最大的瓶頸

> 「跟語言模型不同，機器人沒有網際網路可以學。」
>
> "unlike language model, there is no internet" — [10:44](https://www.youtube.com/watch?v=BHiYomkfoGQ&t=644s)

他說，單一公司自己收集的資料遠遠不夠。Dyna 先用大量第一人稱視角的人類影片打底，讓模型懂得物理世界，再用少量機器人資料補上人機之間的動作差距。學新任務時，通常只要收集幾小時的遙控操作資料，有些任務甚至只要幾十分鐘（[32:04](https://www.youtube.com/watch?v=BHiYomkfoGQ&t=1924s)）；主持人 swyx 補充，切菜任務用了 45 分鐘（[32:11](https://www.youtube.com/watch?v=BHiYomkfoGQ&t=1931s)）。依 Dyna-2 技術報告，模型預訓練用了超過 100 萬小時的人類影片，相當於約 170 年的清醒時間。他也看好合成資料是「新的擴展維度」（[16:28](https://www.youtube.com/watch?v=BHiYomkfoGQ&t=988s)）。

### 三、機器人版的苦澀教訓：演算法越簡單越好，關鍵在選對資料

主持人 swyx 提到「苦澀的教訓」（Bitter Lesson，本站曾在[Claude Code 工程師談苦澀的教訓]({{ site.baseurl }}{% post_url 2026-10-13-claude-code-bitter-lesson %})介紹）。Jason 認為機器人一樣會隨資料規模進步，難的是「對的資料」取決於選了哪些感測器：

> 「讓演算法保持簡單，擴展對的資料。」
>
> "keep the algorithm simpler and scale the right kind of data" — [44:24](https://www.youtube.com/watch?v=BHiYomkfoGQ&t=2664s)

所以 Dyna 自己做硬體：光達這類成熟零件直接買，致動器自己做，身體比例也照真人量測，讓人類資料轉移得更好。他說，「最終是硬體承載智慧」（"it's hardware that carries intelligence"，[23:46](https://www.youtube.com/watch?v=BHiYomkfoGQ&t=1426s)）。Dyna 的機器人是「半人形」：上半身像人，腰部有四個自由度，下半身用輪子。不用腿，是因為用腿耗能更高、更不穩，也更難保證安全（[27:43](https://www.youtube.com/watch?v=BHiYomkfoGQ&t=1663s)）。他主張邊做邊改、實際交給客戶用，而不是花五到十年一次做出最終版人形機器人。

### 四、從一分鐘的單一技能，走向能連跑一小時的工作流程

節目裡的洗衣示範，跑完一整輪要一小時。機器人得判斷洗衣機還在跑時先做別的事，洗好就立刻把毛巾移進烘衣機。Jason 說這種高層決策若全交給底層動作模型去學，效率極差。所以 Dyna 在世界動作模型外面加了一層「代理框架」（agentic harness），就像語言模型從自動補完進化成寫程式代理。

> 「這不只是建模問題，而是系統問題。」
>
> "not just as a modeling problem but rather as a system problem" — [50:50](https://www.youtube.com/watch?v=BHiYomkfoGQ&t=3050s)

他認為價值在於能無人監督連跑數小時的工作流程（[50:45](https://www.youtube.com/watch?v=BHiYomkfoGQ&t=3045s)），而非三十秒的單一任務。

### 五、做試點不難，難的是規模化部署

> 「真正難的，不是把機器人放進一個地點或做一次試點。」
>
> "what's really hard is not putting your robot in one location or doing a pilot" — [39:40](https://www.youtube.com/watch?v=BHiYomkfoGQ&t=2380s)

真正難的，是讓客戶認可價值，並願意推廣到更多據點。他說鼎泰豐就是這樣：機器人每天在洛杉磯、紐約、西雅圖等地分店摺數千條餐巾，摺線位置要剛好落在放筷子的口袋下方幾公分（[40:12](https://www.youtube.com/watch?v=BHiYomkfoGQ&t=2412s)）。他認為通用模型比專用機器更快達到量產品質，因為軟物的形狀有無限多種。而且模型只是一組權重，各分店可以一次更新，摺法就能保持一致（[42:36](https://www.youtube.com/watch?v=BHiYomkfoGQ&t=2556s)）。他也提醒，機器人新創有一座「墳場」，很多機器人很炫，卻不是客戶要的（[55:50](https://www.youtube.com/watch?v=BHiYomkfoGQ&t=3350s)）。

## 提到的工具與用法

- **擴散 Transformer 加流匹配（flow matching）**：Transformer 能吸收最多資料，擴散讓動作精準、平滑；流匹配則是比較好調參的擴散變體（[7:11](https://www.youtube.com/watch?v=BHiYomkfoGQ&t=431s)、[8:01](https://www.youtube.com/watch?v=BHiYomkfoGQ&t=481s)）。
- **裝置端推論加蒸餾**：機器人不能拿著刀停三秒，物理和重力「不會等你」（"gravity doesn't wait for you"，[20:24](https://www.youtube.com/watch?v=BHiYomkfoGQ&t=1224s)）。所以先訓練最大的模型，再蒸餾成能在機器人上跑的版本，推論系統也自己打造（[21:03](https://www.youtube.com/watch?v=BHiYomkfoGQ&t=1263s)）。
- **遙控收資料加回饋迭代**：模型做到七、八成時，觀察它哪裡不行，補收資料再訓練。他把為機器人實際表現打分、拿來回訓的做法，比作機器人版的 RLHF（[33:19](https://www.youtube.com/watch?v=BHiYomkfoGQ&t=1999s)）。
- **用前沿模型生成模擬環境**：他在 NVIDIA 的 Eureka 專案讓 GPT-4 自己寫獎勵函數，讓模擬中的機械手學會轉筆（[1:03:28](https://www.youtube.com/watch?v=BHiYomkfoGQ&t=3808s)）。如今模型的視覺與 3D 能力大增，他認為已到臨界點；Dyna-2 也能生成自己的訓練資料，形成飛輪（[18:24](https://www.youtube.com/watch?v=BHiYomkfoGQ&t=1104s)）。
- **寫程式代理**：GPT-6 推出那一週，Dyna 辦了全公司黑客松，不少成果已經進到正式環境（[51:43](https://www.youtube.com/watch?v=BHiYomkfoGQ&t=3103s)）。

## 產業脈動

- **資金**：據 PR Newswire，Dyna 在 2025 年 3 月完成 2,350 萬美元種子輪，9 月完成 1.2 億美元 A 輪，投資人包括 NVIDIA 旗下的 NVentures、Amazon 與 Samsung Next 等。
- **部署**：Dyna 8 月的部署文章說，Dyna-2 每小時摺 95 條餐巾、93% 達標，換算每天約 1,590 條可直接上桌；加上飯店、物流與資料中心，預計 2027 年上半年機隊達數百台。Jason 在節目中說目前已部署數十台，明年目標數百台（[53:52](https://www.youtube.com/watch?v=BHiYomkfoGQ&t=3232s)）（皆為公司自述）。
- **路線之爭**：有人從影片模型轉做機器人，有人做 VLA，也有人只擴大機器人資料。Jason 說現在下定論「還太早」（"still a bit early to tell"，[55:08](https://www.youtube.com/watch?v=BHiYomkfoGQ&t=3308s)）。
- **硬體與供應鏈**：swyx 提到磁鐵供應瓶頸（Jason 補充：稀土）。Jason 說，目前美國沒有一家機器人公司真正在美國從零打造所有東西，原料仍仰賴全球供應鏈（[24:38](https://www.youtube.com/watch?v=BHiYomkfoGQ&t=1478s)）。他也點名靈巧手容易過熱，現場甚至得放冰袋（[36:10](https://www.youtube.com/watch?v=BHiYomkfoGQ&t=2170s)）。

## 對你的意義

- **上班族**：導入 AI 工具也一樣，試點成功不代表能推廣，關鍵在穩定、可複製、使用者願意買單；也別只比模型，要把模型、流程與工具當成一整套系統。
- **一般讀者**：實體 AI 正從展示影片走向有人付錢的工作，最先落地的是摺餐巾、摺毛巾這類重複勞動。Jason 提到，有些收資料的同事原本在零售業，後來也成了訓練機器人的好手（[1:09:57](https://www.youtube.com/watch?v=BHiYomkfoGQ&t=4197s)）。
- **關心產業的人**：他點名的瓶頸在靈巧手、致動器與觸覺感測，這些都是硬體問題。至於部署數字，目前多是公司自述，值得等待第三方驗證。

Jason 說，Dyna 這個名字一半來自強化學習先驅 Richard Sutton 的 Dyna 論文，講的是在世界模型中自我改進的代理；一半來自他出生那年在日本播出的超人力霸王（[1:11:20](https://www.youtube.com/watch?v=BHiYomkfoGQ&t=4280s)）。

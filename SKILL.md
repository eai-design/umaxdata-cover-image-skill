# cover-image-workflow

## 用途

根據公司標準封面圖版式，為網站文章與社交媒體自動生成封面圖片。工作流先產出三組不同右側素材圖對應的完整 16:9 封面，待使用者選定其中一組後，再延展輸出 1:1、4:5、9:16 等社交媒體尺寸。

## 觸發條件

當使用者要求：

- 生成公司網站標準封面圖
- 依文章標題製作 uMaxDATA / SIP 社交智能平台封面
- 生成多尺寸社交媒體封面
- 參考既有封面樣式批量產圖

## 固定品牌素材

- uMaxDATA logo：`/workspace/源大-uMaxData-2025-彩.png`
- SIP logo：`/workspace/SIP-c (3).png`
- uMaxDATA logo URL：`https://cms.ersinfotech.com/ersinfotech/wp-content/uploads/sites/11/2025/06/2024-hk-uMaxdata-LOGO-png.png`
- SIP logo URL：`https://cms.ersinfotech.com/ersinfotech/wp-content/uploads/sites/11/2025/07/SIP.png`
- 參考封面 URL：`https://files.umaxdata.com/af9bb15e-1e58-4380-a480-87afbf6f51be.PNG`
- 本地參考封面 fallback：`/workspace/af9bb15e-1e58-4380-a480-87afbf6f51be.png`
- 若 runtime 可調用外部圖片，優先使用參考封面 URL；若不可調用，則使用下方「參考版式 Prompt」描述，不強制依賴本地圖片

## 參考版式 Prompt

即使沒有參考圖片，也必須按以下版式生成：

- 16:9 橫向企業媒體封面，1280×720 或更高解析度等比例輸出
- 左側為淺藍灰背景品牌資訊區，約佔畫面 52%–55%
- 右側為主題素材圖區，約佔畫面 45%–48%
- 左側上半部放置 uMaxDATA logo 與 SIP 社交智能平台 logo，兩個 logo 橫向排列
- uMaxDATA logo 與 SIP logo 的視覺高度必須一致，需參考標準圖中的 logo 組合比例，不得一大一細
- 兩個 logo 需垂直居中對齊，主體高度一致，底部基線視覺平衡
- 主標題位於 logo 下方，靠左對齊，使用深青色 `#004f5d`，粗體現代中文黑體風格
- 右側素材圖與左側背景之間使用由左下往右上傾斜的斜切分隔
- 斜切分隔附近加入半透明淺藍灰玻璃疊片、細高光線與透明結構線，不能硬切
- 整體風格為香港企業科技媒體、乾淨、專業、留白充足

## 語言與地域語境

- 所有標題、副標題、標籤與任何可見文字必須使用繁體中文
- 文案語氣需符合香港本土語境，可使用香港常見新聞標題語感與粵語書面表達
- 不得輸出簡體中文、日文、韓文、亂碼、偽文字或非必要英文
- 如品牌名稱本身為英文，例如 uMaxDATA、SIP、Uber，可保留原文
- 本版本允許 image_generation 直接生成封面中的標題與 logo，但必須嚴格檢查文字與 logo 完整性
- 若出現方框字、缺字、亂碼、錯字、簡體字、logo 爛字或少詞，必須重新生成或改用後期合成修正
- 若標題或 logo 出現變形、壓縮、模糊、筆畫黏連、邊緣發虛或不可清晰辨讀，必須重新生成或改用後期合成修正

## 視覺規格

### 基準尺寸

- 主封面：1280 × 720
- 比例：16:9
- 所有最終交付圖片需為高清輸出；image_generation 優先使用 4K 解析度
- 若工具限制導致非目標像素，後處理輸出指定尺寸時必須保持等比例縮放，不得拉伸、壓扁或改變原圖比例
- 嚴禁使用直接 resize 到目標寬高的非等比縮放方式；只能使用等比縮放後中心裁切、等比縮放後補邊，或重新生成正確比例圖片
- 除 PNG 外，需額外導出 WebP 網頁格式
- 背景色：淺藍灰，建議 `#dceff2`
- 標題色：`#004f5d`
- 字體風格：粗體現代黑體，需接近參考圖中文粗黑字體
- 版式：左側品牌與標題，右側生成素材圖

### 標準 16:9 版式

- 畫布：1280 × 720
- 必須嚴格參考「參考封面 URL」或「參考版式 Prompt」的左右畫面比例與視覺重心
- 左側淺藍灰品牌資訊區約佔畫面 52%–55%，右側素材圖約佔 45%–48%
- 左側背景需延伸至畫面左邊界與底部，不得留白或裁切
- 右側素材圖從畫面右邊界延伸至斜切分隔線，不得壓縮變形
- 斜切分隔線位置需接近參考圖：上方約在 x=735px 附近，下方約在 x=655px 附近，形成由左下往右上傾斜的切面
- 斜切區必須包含參考圖中的特殊透明結構線條處理：主斜切邊界旁需加入 1–2 層半透明淺藍灰多邊形疊片、細窄高光線或玻璃感透明切面，使素材圖與文本區自然銜接
- 不得只使用硬切單一斜邊；透明結構需覆蓋右側素材圖少量邊緣，但不得遮擋 logo 或標題主體
- logo 區域位於左側上半部，約在 x=60–620px、y=195–265px 範圍內
- uMaxDATA logo 在左，SIP logo 在右，兩者視覺高度需一致，垂直居中對齊，不得一大一細，不得被拉伸
- logo 組合的高度、間距與基線需接近參考圖；uMaxDATA 與 SIP logo 主體高度應保持同級視覺權重
- 標題位於 logo 下方，約從 x=60px、y=300px 開始
- 標題區最大寬度約 590px，避免跨入右側素材圖

### 標題排版與語義斷行

- 標題可由 image_generation 直接生成，但必須使用繁體中文、香港本土語義與正確標點
- image_generation 需按語義自然斷行，不得逐字硬切
- 若模型生成文字不穩定，可退回後期合成方式，並使用支援繁體中文與香港常用字的字體
- 所有中文標題必須筆畫清晰、邊緣銳利、色彩鮮明、絕對清晰可讀
- 不允許出現文字模糊、邊緣糊化、筆畫缺失、筆畫黏連、錯字、亂碼、簡體字、缺字或多字
- 若 image_generation 不能穩定生成清晰中文字，必須改用後期文字合成；不可交付模糊文字版本
- 推薦字體優先級：
  - Source Han Sans TC Heavy / Bold
  - 思源黑體 TC Heavy / Bold
  - Noto Sans CJK TC Bold / Noto Sans TC Bold
  - PingFang TC Semibold / Heavy
  - Microsoft JhengHei Bold
  - Arial Unicode MS 或其他完整 CJK fallback
- 首選字體必須為 Source Han Sans TC / 思源黑體 TC；若不可用，才允許使用經驗證的完整 CJK TC 字體
- `Noto Sans` 普通拉丁字體不等於 `Noto Sans CJK TC`，不得作為繁中文字體 fallback
- 若系統只有不完整 Noto Sans、缺少 CJK TC 字體或 fc-match 回傳非 CJK 字體，不得直接輸出最終圖，需先安裝或指定完整中文字體
- 字體驗證需包含標題中的全部繁體中文、粵語字與標點，例如「點解」「喺」「嘅」「爆紅」等
- 若任何字元生成為 tofu 方框、空白、問號、亂碼、簡體或錯字，需停止交付並重新生成或改用後期排版修正
- 主標題使用粗體現代中文黑體，顏色固定為 `#004f5d`
- 字號需根據標題長度自動調整，優先確保可讀性與少量行數
- 16:9 主標題建議字號：
  - 10 字以內：70–82px
  - 11–18 字：58–70px
  - 19–28 字：48–60px
  - 29–40 字：40–50px
  - 超過 40 字：需摘要化或拆成主標題 + 副標題
- 主標題通常控制在 2 行，最多 3 行
- 不得逐字平均硬切，必須根據語義切分
- 優先在標點、冒號、問號前後、語義轉折處、品牌名後、議題分句處斷行
- 避免將固定詞組拆開，例如品牌名、政策名、平台名、人物名、事件名
- 若標題包含冒號，冒號前通常作為第一語義段，冒號後作為第二語義段
- 若標題包含問句，可將問題主體集中於最後一行，加強視覺重點
- 標題行距建議為字號的 1.05–1.15 倍
- 標題不得遮擋 logo，不得貼近畫布邊緣，不得跨越斜切分隔線

### 副標題規則

- 若使用者提供副標題，副標題放在主標題下方
- 副標題可由 image_generation 生成，但需完整、準確、非粗體且視覺權重低於主標題
- 副標題不使用粗體，使用中等或常規字重
- 副標題字號約為主標題的 38%–55%
- 副標題顏色可使用 `#004f5d` 的 80%–90% 透明度，或深灰藍色
- 副標題最多 1–2 行，需保持充足留白
- 副標題不得搶主標題視覺權重

### 社交媒體尺寸

每組右側素材圖需延展輸出：

- `16:9`：1280 × 720，網站封面
- `1:1`：1080 × 1080，Instagram / Facebook 方圖
- `4:5`：1080 × 1350，Instagram feed
- `9:16`：1080 × 1920，Story / Reels / Shorts

### 非 16:9 尺寸自適應版式

除 16:9 外，其他比例不得機械套用同一佈局，也不得簡單裁切。必須在不改變原有內容的前提下，按畫面比例重新安排 logo、標題、素材圖與留白。

- `1:1`：適合上文下圖或左上文字、右下素材的平衡構圖；素材圖佔畫面約 42%–52%，文字與 logo 區約 48%–58%；標題建議 3–4 行，字號中等偏大但不得壓迫畫面，避免單行過長
- `4:5`：適合社交 feed；素材圖佔畫面約 45%–55%，文字與 logo 區約 45%–55%；標題建議 3–4 行，行距略放鬆，字號不得過大，可用斜切或透明過渡銜接文字區與素材圖
- `9:16`：適合手機瀏覽；素材圖佔畫面約 45%–55%，不得只佔底部很小一塊；標題建議 4–5 行，字號需比 1:1/4:5 更克制但保持手機可讀，避免畫面頭重腳輕
- 所有比例均需根據標題長度重新計算字號與斷行；不同尺寸的標題行數、字號、行距可以不同
- 社媒尺寸標題字號不得機械放大；需優先確保畫面平衡、留白充足與手機可讀
- 若標題較長，1:1 / 4:5 / 9:16 應適度縮小字號並增加自然換行，不得讓標題佔滿畫面或壓迫 logo / 素材圖
- 標題換行必須符合語義與內容要求，優先在標點、冒號、破折號、語義轉折、品牌名或事件名之後斷行
- 不得拆散固定詞組、品牌名、活動名、專有名詞或完整語義短語，例如「The Big Bounce」「輿情溫度計」「事件分析」
- 每行長度需視覺均衡，不可出現單行過長或單字孤行
- 版式原則：保持同一品牌元素與同一素材圖，但每個比例都要獨立設計到視覺平衡
- 可使用半透明斜切、玻璃疊片、淺色遮罩或局部漸變改善素材與文字區銜接
- 若某尺寸中標題過長，優先調整斷行與字號，不得刪改原意

### Logo 完整性規則

- uMaxDATA logo 與 SIP logo 必須使用提供的原始品牌素材，不得由模型重新繪製文字
- 優先策略：使用原始 logo 圖片以貼圖/後期合成方式放入封面指定位置
- 若 runtime 可調用外部圖片，優先使用官方 URL 下載或引用 logo，再貼到封面圖 logo 位置
- 若 runtime 不可調用外部圖片，使用本地 logo 素材 `/workspace/源大-uMaxData-2025-彩.png` 與 `/workspace/SIP-c (3).png`
- 僅當無法使用貼圖合成時，才允許 image_generation 參考 logo，但仍需進行 logo 完整性驗證
- logo 必須完整呈現，不得爛字、少詞、漏字、變形、模糊、裁切或被元素遮擋
- logo 不得因尺寸調整而橫向壓扁、縱向拉伸或比例失真
- logo 內既有英文、中文與圖形標識不得被改寫
- 16:9 尺寸需嚴格參考標準封面中的 logo 位置、比例與視覺大小
- 16:9 尺寸中 uMaxDATA logo 與 SIP logo 的視覺高度必須一致，需像參考圖一樣保持同一水平排列與同級品牌權重
- 其他尺寸可依畫面比例等比例縮放，但必須保持清晰、完整與可讀
- logo 周圍需保留安全留白，不得貼邊或壓到標題
- 若 image_generation 無法穩定保持 logo，需使用後期合成方式覆蓋原始 logo 素材

## 工作流

### 1. 需求收集

必要輸入：

- 文章標題
- 文章主題或摘要
- 是否需要繁中、簡中、英文或雙語
- 是否沿用 uMaxDATA + SIP 雙 logo

缺少標題或主題時，先向使用者確認。

### 2. 第一階段：生成三組完整 16:9 候選封面

用戶提供主題或標題後，直接使用 image_generation 生成三組完整 16:9 候選封面，不再拆成「先生成素材圖、再合成封面」兩步；也不立即生成 1:1、4:5、9:16，避免一次輸出過多圖片。

「三組不同右側素材圖」的意思是：

- 三張均需與標題語義高度相關
- 三張素材圖需有不同視覺方向、構圖或敘事角度
- 三張素材圖需分別放入三個完整 16:9 封面版式中
- 三個 16:9 封面均需包含 logo、標題、背景、斜切透明結構與右側素材圖
- 標題與 logo 可由 image_generation 一次生成，但結果必須完整、準確、可讀

三組 16:9 封面生成後，必須向使用者反問：

```text
已生成 3 組完整 16:9 候選封面。
請選擇基於 Set 01 / Set 02 / Set 03 哪個版本生成 1:1、4:5、9:16 社媒尺寸；或提出修改方案 / 重新生成。
```

每張素材圖需：

- 與文章標題高度相關
- 適合香港 / 大灣區 / 商業科技語境
- 可用作右側視覺主圖
- 避免生成錯誤文字、錯誤 logo、錯誤品牌標識
- 不要把標題文字直接生成在素材圖內

### 2.1 反向 Prompt 與禁用內容

生成素材圖與封面時需加入反向 Prompt，避免以下內容：

- 敏感、血腥、暴力、災難傷亡、恐慌場景
- 政治宣傳、宗教衝突、仇恨符號、歧視性內容
- 可識別真人肖像、名人臉、藝人臉、真實公眾人物臉部特徵
- 未授權品牌 logo、錯誤商標、假冒平台標識
- 敏感文化建築、宗教建築、政府建築、軍事建築作為主視覺焦點
- 香港或其他地區的官方證件、車牌、政府文件、執法標識
- 亂碼、偽文字、簡體字、錯別字、非繁體中文文字
- 低清晰度、過度模糊、過度擁擠、裁切錯誤、畸形人物或錯誤肢體
- 任何可能導致誤導、冒充、欺詐或負面品牌聯想的元素

### 3. 第二階段：使用選定 16:9 封面延展社交尺寸

只有在使用者選定 16:9 候選封面後，才開始生成 1:1、4:5、9:16 社交媒體版式。

「輸出 16:9、1:1、4:5、9:16 封面」的意思是：

- 使用同一組已選定 16:9 封面的右側素材圖與品牌風格
- 使用同一組標題、logo、背景、品牌風格與視覺元素
- 標題與 logo 可由 image_generation 生成，但需沿用選定封面的文字、logo 與品牌視覺
- 針對不同平台比例重新排版
- 不是再生成四張不同主題圖
- 不是簡單裁切，而是同元素的不同分辨率版式

對使用者選定的一組 16:9 封面延展生成社交媒體尺寸。

該組需包含：

- 品牌 logo
- 標題
- 如有副標題，需以非粗體小字號呈現
- 右側素材圖
- 統一背景、字色、斜切分隔與留白
- 16:9 版本必須優先符合參考封面的左右比例，不得自由改版

### 4. 多尺寸輸出

同一張已選定素材圖需輸出所有目標比例。

不同尺寸需重排版，而不是簡單裁切：

- 16:9：左右分欄
- 1:1：上方品牌與標題，下方或右下為素材圖
- 4:5：上方品牌與標題，中下方素材圖
- 9:16：品牌置頂，標題居中偏上，素材圖置中下方

### 5. 驗證

交付前需檢查：

- 每張圖尺寸正確
- 每張圖必須保持正確比例，後處理不得造成畫面、logo 或文字壓扁/拉伸
- 第一階段輸出 3 張完整 16:9 候選封面 PNG，另加 3 張 WebP
- 第二階段只輸出使用者選定組別的 1:1、4:5、9:16 PNG，另加 3 張 WebP
- 標題無錯字
- 標題與副標題不可有方框字、亂碼、缺字或錯字
- 若 image_generation 文字失敗並改用後期修正，字體必須支援完整繁體中文與香港常用粵語字
- image_generation 生成的標題需完整、準確、繁體中文、符合香港語義
- 中文標題需筆畫清晰、邊緣銳利、色彩鮮明，不得模糊、發虛、壓扁、拉伸或難以辨讀
- 16:9 需包含參考圖式半透明斜切結構線條與玻璃過渡感
- 各尺寸版式需視覺協調，素材圖與文字區比例合理，不得頭重腳輕、素材過小或文字過密
- 社媒尺寸需檢查標題字號是否過大、換行是否符合語義、是否保留足夠留白
- logo 未變形
- logo 完整、無爛字、無少詞、無裁切
- image_generation 生成的 logo 需完整清晰；若 logo 爛字或缺字，需重新生成或改用原始素材貼圖修正
- logo 需保持原始寬高比例，不得因 resize 或輸出尺寸調整而變形
- 所有可見文字均為繁體中文或合法品牌英文
- 無敏感影像、敏感建築、可識別真人肖像或禁用元素
- 主色一致
- 右側素材圖不同且與主題相關
- 每張圖片同時提供 PNG 與 WebP 格式

### 6. 交付

所有輸出圖片需以清晰命名交付：

```text
cover_set_01_16x9.png
cover_set_01_1x1.png
cover_set_01_4x5.png
cover_set_01_9x16.png
cover_set_02_16x9.png
...
cover_set_03_9x16.png
```

## image_generation 完整 16:9 候選封面提示詞模板

```text
Create a complete 16:9 branded corporate article cover for a Hong Kong media article.

Topic: {{topic}}
Title: {{title}}
Visual set direction: {{set_direction}}

Cover requirements:
- generate a complete cover, not only a background visual
- include uMaxDATA logo and SIP Social Intelligence Platform logo
- include the full article title in accurate Traditional Chinese
- title color #004f5d
- bold modern Chinese sans-serif typography matching the reference
- light blue-gray left background
- right-side visual image area must be related to the title
- follow the reference 16:9 layout with diagonal translucent glass/structure transition
- Hong Kong / Greater Bay Area business environment
- realistic yet polished corporate editorial style
- strong relation to the article topic
- logo and title must be complete, readable, no broken text, no missing words
- Chinese title must have sharp strokes, crisp edges, vivid color, and be absolutely readable
- no blurred typography, no distorted typography, no squashed text, no stretched text
- no fake extra text, no watermark, no distorted signage
- professional lighting, premium corporate media look
- 4K high-resolution output

Negative prompt:
- no simplified Chinese, no fake text, no gibberish, no misspelled Traditional Chinese
- no broken logo text, missing logo words, corrupted title characters
- no blurry Chinese title, soft text edges, distorted title, stretched or squashed logos
- no recognizable real person, celebrity face, public figure likeness
- no sensitive political, religious, military, government or official-document elements
- no sensitive cultural or religious architecture as the main focus
- no violence, blood, disaster casualties, panic scenes, hate symbols
- no unauthorized logos, fake brands, distorted signage
- no low resolution, blur, cropped logos, broken text, deformed people
```

## 封面生成提示詞模板

```text
Generate a complete branded article cover image based on the reference layout.

Canvas ratio: {{ratio}}
Brand assets: uMaxDATA logo and SIP Social Intelligence Platform logo
Title: {{title}}

Style:
- light blue-gray background
- title color #004f5d
- bold modern Chinese sans-serif typography matching the reference
- analyze title semantics and split into 2–3 natural lines only
- choose title font size according to length and readability
- if subtitle exists, render it smaller and non-bold below the main title
- for 16:9, strictly match the reference cover's left-right content ratio and diagonal divider position
- clean corporate technology media design
- use the generated topic image as the visual area
- preserve accurate brand logo appearance
- logos must be placed from the original supplied assets, complete and readable, with no broken text or missing words
- all visible text must be Traditional Chinese suitable for Hong Kong local context, except official brand names
- do not generate title or subtitle text inside image_generation; reserve clean layout space for post-composited typography
- title and subtitle must be rendered later using a real Traditional Chinese font
- export PNG and WebP
- do not alter logo text
- no extra text other than the title and existing logo text

Negative prompt:
- no simplified Chinese, no fake characters, no corrupted logo text
- no recognizable real-person portrait or celebrity likeness
- no sensitive cultural, religious, government or military buildings as main visual focus
- no political propaganda, violence, blood, hate symbols, disaster casualties
- no unauthorized logos or misleading official symbols
```

## 建議執行策略

優先使用 image_generation 產生右側素材圖，再使用圖像編輯或版面合成工具完成品牌封面。若 image_generation 可直接生成完整封面，需使用參考圖與品牌 logo 作為 reference images，並嚴格指定尺寸比例。

## 成功標準

第一階段完成後，使用者應取得 3 張完整 16:9 候選封面，並選擇其中一組。第二階段完成後，使用者應取得該組對應的 1:1、4:5、9:16 封面 PNG 與 WebP。

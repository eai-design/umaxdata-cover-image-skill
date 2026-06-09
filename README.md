# uMaxDATA Cover Image Workflow Skill

用於生成 uMaxDATA / SIP 社交智能平台標準封面圖的 workflow-style skill。

## 用途

根據文章標題與主題，自動生成符合公司品牌風格的封面圖：

1. 先生成 3 組完整 16:9 候選封面
2. 用戶選擇 Set 01 / Set 02 / Set 03
3. 再基於所選版本生成 1:1、4:5、9:16 社媒尺寸
4. 每個尺寸輸出 PNG + WebP

## 使用範例

```text
標題：
網約車牌照即將發放：Uber 如何拆解新局面？

主題：
香港網約車牌照、Uber、的士市場、交通科技平台競爭、輿情分析
```

## 工作流

### Step 1：輸入標題與主題

使用者提供文章標題與主題描述。

### Step 2：生成 16:9 候選封面

Skill 會直接生成：

```text
Set 01 - 16:9 候選封面
Set 02 - 16:9 候選封面
Set 03 - 16:9 候選封面
```

每組封面包含：

- uMaxDATA logo
- SIP 社交智能平台 logo
- 文章標題
- 主題相關素材圖
- 淺藍灰品牌背景
- 斜切透明玻璃結構
- PNG + WebP

### Step 3：選擇下一步

生成 3 組 16:9 候選封面後，應詢問：

```text
請選擇基於 Set 01 / Set 02 / Set 03 哪個版本生成 1:1、4:5、9:16 社媒尺寸；或提出修改方案 / 重新生成。
```

### Step 4：生成社媒尺寸

若用戶選擇 Set 02，則生成：

```text
cover_selected_set_02_1x1.png
cover_selected_set_02_1x1.webp
cover_selected_set_02_4x5.png
cover_selected_set_02_4x5.webp
cover_selected_set_02_9x16.png
cover_selected_set_02_9x16.webp
```

## 尺寸規格

| 類型 | 尺寸 | 用途 |
|---|---:|---|
| 16:9 | 1280 × 720 | 網站封面 |
| 1:1 | 1080 × 1080 | 社交平台方圖 |
| 4:5 | 1080 × 1350 | Instagram / Facebook feed |
| 9:16 | 1080 × 1920 | Story / Reels / Shorts |

## 品牌規則

- 標題顏色：`#004f5d`
- 背景色：淺藍灰
- 所有文字使用繁體中文
- 文案需符合香港本土語境
- uMaxDATA logo 與 SIP logo 必須視覺高度一致
- uMaxDATA logo 與 SIP logo 必須垂直居中對齊
- logo 不得變形、模糊、缺字、爛字或裁切
- 中文標題需清晰銳利、無亂碼、無錯字、無簡體字

## 16:9 版式規則

- 左側品牌與標題區約佔 52%–55%
- 右側素材圖約佔 45%–48%
- 右側圖片與左側背景之間使用斜切分隔
- 斜切處需有半透明玻璃疊片 / 結構線條
- 不得硬切
- 不得壓扁或拉伸畫面
- 不得使用非等比縮放

## 社媒尺寸規則

1:1、4:5、9:16 不應直接套用 16:9 左右分欄版式，需重新設計：

- 保持畫面美觀、留白充足
- 標題字號不可過大
- 換行需符合語義
- 不得拆散固定詞組、品牌名、活動名或專有名詞
- 素材圖與文字區比例需協調
- 不得讓標題壓迫 logo 或素材圖
- 每個尺寸需根據畫面比例獨立排版

## 參考素材

### 參考封面

```text
https://files.umaxdata.com/af9bb15e-1e58-4380-a480-87afbf6f51be.PNG
```

### Logo

```text
uMaxDATA:
https://cms.ersinfotech.com/ersinfotech/wp-content/uploads/sites/11/2025/06/2024-hk-uMaxdata-LOGO-png.png

SIP:
https://cms.ersinfotech.com/ersinfotech/wp-content/uploads/sites/11/2025/07/SIP.png
```

## 輸出命名

### 第一階段

```text
cover_candidate_set_01_16x9.png
cover_candidate_set_01_16x9.webp
cover_candidate_set_02_16x9.png
cover_candidate_set_02_16x9.webp
cover_candidate_set_03_16x9.png
cover_candidate_set_03_16x9.webp
```

### 第二階段

```text
cover_selected_set_XX_1x1.png
cover_selected_set_XX_1x1.webp
cover_selected_set_XX_4x5.png
cover_selected_set_XX_4x5.webp
cover_selected_set_XX_9x16.png
cover_selected_set_XX_9x16.webp
```

## 文件說明

```text
SKILL.md        Skill 主規格
AGENT.md        Agent 執行流程
workflow.yaml   工作流配置
prompts.md      提示詞模板
```

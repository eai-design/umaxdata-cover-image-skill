# uMaxDATA Cover Image Workflow Skill

用於生成 uMaxDATA / SIP 社交智能平台標準封面圖的 workflow-style skill。

## 用途

根據文章標題與主題，自動生成符合公司品牌風格的封面圖：

1. 先生成 3 組完整 16:9 候選封面
2. 用戶選擇 Set 01 / Set 02 / Set 03
3. 再基於所選版本生成 1:1、4:5、9:16 社媒尺寸
4. 每個尺寸輸出 PNG + WebP

## 工作流

### Step 1：輸入標題與主題

```text
標題：


主題：



Step 2：生成 16:9 候選封面
Skill 會直接生成：
Set 01 - 16:9 候選封面
Set 02 - 16:9 候選封面
Set 03 - 16:9 候選封面

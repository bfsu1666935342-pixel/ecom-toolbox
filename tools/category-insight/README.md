# 亚马逊类目调研 · Category Insight

三份亚马逊类目 / 细分调研报告。每份都是独立的单文件页面，打开就能看，包含需求、竞争、产品、单位经济、供应链五层，以及可交互的价格 / 成本 / 广告假设。

线上入口：<https://bfsu1666935342-pixel.github.io/ecom-toolbox/tools/category-insight/>

## 报告列表

| 报告 | 口径 | 结论 | 版本 |
| --- | --- | --- | --- |
| [Drafting Chair](drafting-chair/) | Amazon US · Drafting Chairs · node 1069142 · Top100 | **No-Go 40/100**：$129 撑不起 $3.88 CPC | v0.4 |
| [Criss Cross Office Chair](criss-cross-chair/) | 关键词细分 · `criss cross office chair` · 17 ASIN 样本 | **有条件 69/100**：只做 $229–249 宽座/大体重 | v0.3 |
| [Gaming Chair](gaming-chair/) | Amazon US · Video Game Chairs · node 668180011 · Top100 | **No-Go 41/100**：需求下滑 + Amazon 39.5% | v0.2 |

每份报告里都有：

- 需求：24 个月趋势、季节性、核心词同比 / CPC / 转化
- 竞争：价格带、品牌/卖家集中度、评论墙、内容覆盖
- 产品：Top10 商品矩阵、供给空位、3 个产品概念
- 单位经济：改售价 / landed / CPC / CVR / 退货，实时重算
- 数据：覆盖范围、缺口、下一步需要补的数据

## 数据来源与口径

- 数据通过 **Sorftime MCP** 在 **2026-11-12** 拉取。
- Gaming / Drafting 是 Amazon 官方子类目，Top100 口径。
- Criss Cross 不是官方类目，是按核心词 `criss cross office chair` 定义的细分，17 个 ASIN 样本 + Top10 详情。
- **Sorftime 为第三方估算，不是 Amazon 官方数据。**
- 成本、FBA、广告 CPC/CVR、退货、供应链均为页面内假设，用于方向判断，不构成投资建议。
- 页面不含任何 API key；原始 CSV 放在 `data/` 下。

## 三个结论

### Drafting Chair

- 2026-10 销量 27,188，同比 **-35.5%**；ASP $109
- `drafting chair` 99,649/月、+7.9%，但 CPC **$3.88**、CVR 4.28%，广告单均 **$90.65**
- $129 单位贡献 **-$70.8 / -54.9%**
- $199 仍为负；$249 只有 11.1%；$299 才 23%，但类目最高价约 $270
- **类目级 No-Go**

### Criss Cross Office Chair

- 主词 `criss cross office chair` **177,750/月、+68.1%**
- 17 ASIN 样本 30,365 件 / $3.23M；TOP3 44.3%；Amazon Buy Box 35.3%
- $199 7.2% 不成立；$229 17.2%；$249 22.5%
- **有条件，只做 $229–249 宽座/大体重，先 300–500 件测试**

### Gaming Chair

- 2026-10 销量 78,570，同比 **-21.5%**
- TOP3 46.7%、Amazon 自营 39.5%；1001+ 评论 ASIN 贡献 49.2% 销量
- $229 毛利 12.4%；$120 均价结构性亏损
- 只有 `big and tall gaming chair` 搜索 +11.7%
- **类目级 No-Go**

## 目录结构

```
tools/category-insight/
├─ index.html                  # 入口页：三份报告
├─ preview.png                 # 入口预览
├─ drafting-chair/
│  ├─ index.html               # Drafting Chair v0.4
│  └─ preview.png
├─ criss-cross-chair/
│  ├─ index.html               # Criss Cross Office Chair v0.3
│  └─ preview.png
├─ gaming-chair/
│  ├─ index.html               # Gaming Chair v0.2
│  └─ preview.png
└─ data/
   ├─ drafting-chair-top100.csv
   ├─ criss-cross-sample.csv
   └─ gaming-chair-top100.csv
```

## 技术

- 纯 HTML + CSS + 原生 JavaScript，无构建、无 CDN 依赖
- 报告内所有交互只在本地浏览器计算，不上传数据
- 单份报告约 87–98 KB，预览图约 200 KB，原始 CSV 4–29 KB

## 授权

[MIT](../../LICENSE) © 2026 bfsu1666935342-pixel

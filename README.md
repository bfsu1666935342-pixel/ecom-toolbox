# 跨境电商工具箱 · Ecom Toolbox

自用的亚马逊 / 跨境电商小工具合集。每个工具都是一个**独立的纯静态单页**：打开就能用，不用登录、不用联网、不依赖后端，数据只存在你自己的浏览器里。

线上地址：<https://bfsu1666935342-pixel.github.io/ecom-toolbox/>

## 工具列表

| 工具 | 说明 | 版本 |
| --- | --- | --- |
| [广告结构反推测算](tools/ad-structure-calc/) | 按「层级 → 广告活动 → 关键词」反推日点击、花费、单量；新品 / 老品双模式，可导入西柚、SIF・卖家精灵、亚马逊 ABA 的搜索量表格自动填词库（按覆盖天数折算成月），算出平本花费 / ACoAS / 利润余量，案例与词库可导出 JSON 跨设备带走 | v6.1 |
| [流量承接诊断](tools/k-exposure/) | 导入搜索词报告 + 搜索量词库，算每个词的曝光覆盖率 k 与 CTR、CVR、CPA，判断是「没被看到」（k 低，抢位置）还是「看到了不点」（CTR 低，改主图/价格），逐词给结论 | v1.0 |

新工具加好后请同步更新这个表、[首页卡片](index.html) 和下面的目录树。

## 目录结构

```
ecom-toolbox/
├─ index.html                    # 首页：工具导航（GitHub Pages 入口）
├─ README.md                     # 本文件：仓库总览
├─ LICENSE
├─ .nojekyll                     # 让 Pages 原样输出，跳过 Jekyll
└─ tools/
   ├─ ad-structure-calc/         # 一个工具一个目录，互不干扰
   │  ├─ index.html              # 工具本体（自包含，无需构建）
   │  └─ README.md               # 工具说明：功能、算法、用法
   └─ k-exposure/
      ├─ index.html              # 流量承接诊断
      └─ README.md
```

一个工具的完整地址是 `/tools/<工具名>/`，因为每个目录里都有 `index.html`，所以 URL 不用带文件名。

## 加一个新工具的步骤

1. 新建 `tools/<kebab-case-名字>/index.html`，保持单文件自包含（样式、脚本内联），直接打开可用。
2. 同目录放一份 `README.md`，写清功能、核心算式、数据来源和已知限制。
3. 在根 `index.html` 的 `.tools` 里复制一张卡片，改图标、标题、描述、标签和链接。
4. 更新本文件顶部的工具表格。
5. 如果工具要存 `localStorage`，key 前缀统一用工具名，例如 `adstruct_*`，避免多个工具互相覆盖。

约定：**不引入构建工具、不引入 CDN 依赖**。哪天必须用库，就把库文件一起放进该工具的目录里，保证十年后 clone 下来双击还是能跑。

## 技术说明

- 纯 HTML + CSS + 原生 JavaScript，无构建、无第三方依赖。
- GitHub Pages 托管，`.nojekyll` 已就位，静态文件原样输出。
- 所有工具的数据都存在浏览器本地 `localStorage`，换浏览器或清缓存会丢失，重要数据请在工具内「保存为案例」。

## 授权

[MIT](LICENSE) © 2026 bfsu1666935342-pixel

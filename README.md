# 抽签 · 薯条盒

写下几个选项，晃一晃薯条盒，掉出来的那根薯条就是答案。

纯静态网页，无依赖、无构建步骤，直接打开 `index.html` 即可运行。

## 目录

```
index.html        页面、样式和全部逻辑
assets/
  bg.webp         背景（薯条盒已抠除）
  pile.webp       盒里的薯条堆
  front.webp      盒子正面
  long*.webp      抽出时的长薯条（R3 / L1 / R1 前排，B1 / B2 后排）
  fry*.webp       落地后的桌面透视薯条（A / C 前排，B1 / B2 后排）
```

## 本地预览

```bash
python3 -m http.server 8000
# 打开 http://localhost:8000
```

## 部署到 GitHub Pages

1. 把这个目录推到一个 GitHub 仓库（例如 `chouqian`）。
2. 仓库 Settings → Pages → Source 选 `Deploy from a branch`，分支选 `main`，目录选 `/ (root)`。
3. 稍等片刻，访问 `https://<你的用户名>.github.io/chouqian/`。

## 说明

- 选项保存在浏览器 localStorage，刷新不会丢失。
- 随机数使用 `crypto.getRandomValues`，无偏取样。
- 系统开启「减少动态效果」时，会跳过晃动和飞行动画，直接落地。

# my-site

Evan 的个人静态站 · nightweaver.top

纯前端静态 HTML，无后端、无构建步骤。push 到 GitHub 后由 EdgeOne Makers 自动同步上线。

## 目录约定

- **根目录放页面**：一个 html 就是一个网址，不按日期或编号分子目录。
- **`image/` 放所有图片**：页面里一律写相对路径 `image/xxx.png`，所以 html 和 `image/` 必须同级；唯一例外是根目录的站点标识 `logo.png`。
  - `logo.png` 放根目录是刻意的：首页、`github-terms.html`、`gpu-comparison.html` 页脚共用这一份，页面里直接写 `logo.png`（不带 `image/`）；原先 `image/logo.png` 是同一张图的冗余副本，已删除。**新增图片一律放 `image/`**。
- 每个页面的 CSS 和 JS 都内联在 html 里，**不需要额外上传 css / js 文件**。

## 命名约定

- 全小写英文 + 短横线（kebab-case）：`gpu-comparison.html`
- **不用流水编号**（`01-`、`02-`）：文件名就是网址，插一篇就得全部重排、链接全断，没有回报。
- **不带版本号**（`v1.2`）：版本号会过期，日期不会。
- 不用中文、空格、下划线：会变成 URL 编码，链接难看。
- **`index.html` 是首页，静态托管默认找它，唯一不能改名的文件。**
- 文章日期写在页面页头和首页列表的简介里，不塞进文件名（本站文章少，手写维护，不需要靠日期前缀排序）。

## 当前文件清单

| 文件 | 类型 | 说明 |
|---|---|---|
| `index.html` | 首页 | 唯一不能改名；**每加一个页面都要在这里补入口** |
| `essays.html` | 栏目页 | 随笔日志（时评 / 随笔 / 练笔） |
| `tools.html` | 栏目页 | 实用工具 |
| `practice.html` | 栏目页 | 个人练习区 |
| `github-terms.html` | 文章 | GitHub 高频术语表 |
| `local-ai-pick.html` | 文章 | 本地 AI 选型对比 |
| `gpu-comparison.html` | 文章 | 中高端主流显卡性能及价格对比（2026-11-24） |
| `logo.png` | 图片 | 站点标识，根目录唯一一份；首页 / 术语页 / 显卡对比页页脚共用，别删 |
| `image/` | 图片目录 | 文章配图、Banner 用 `mylogo.png`、天梯图 SVG |

两类要分清：**栏目页**长期不变、不标日期；**文章**有发布日期、靠首页列表串起来。

## 发一篇新文章的固定动作

1. 写 md，用本机的 `build.js` 生成 html（模板与规范见 `E:\WorkBuddySpace\My_Knowledge_Vault\出品规范\05-发文工作流.md`）。
2. html 放进本仓库**根目录**并改好名字；配图放进 `image/`。
3. 在 `index.html` 的「作品与练习」里补一条 `<li>`，新的放最上面。
4. `git add .` → `git commit` → `git push`；推完等 EdgeOne 自动同步。

## 什么时候改结构

现在不到 10 个页面，平铺是最省事的做法，不算乱。**到 15~20 个再分目录**：文章进 `posts/`、图片统一进 `assets/`。分目录时所有页面的相对路径要一起改，别在手写阶段提前折腾。

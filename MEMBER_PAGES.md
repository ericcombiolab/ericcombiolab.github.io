# Updating your own page / 更新你自己的主页

Everything about you on <https://ericcombiolab.github.io/people/> comes from one
file: `_people/<your-id>.md`. You do not need git installed, and you do not need
write access to this repository — GitHub will fork it for you.

页面上关于你的所有内容都来自一个文件：`_people/<你的 id>.md`。不需要装 git，
也不需要仓库权限——GitHub 会自动帮你 fork。

---

## Steps / 操作步骤

1. Open your file on GitHub: `_people/` → click your file (e.g. `dingyi.md`).
   在 GitHub 上打开 `_people/`，点开你的文件。
2. Click the **pencil icon** (Edit this file). GitHub creates a fork for you
   automatically the first time.
   点右上角**铅笔图标**。第一次会提示 fork，同意即可。
3. Edit the fields you want to change (see the reference below).
   修改你要改的字段。
4. Scroll to the bottom, write a one-line description of the change, and click
   **Propose changes** → **Create pull request**.
   拉到底部，写一句说明，点 **Propose changes** → **Create pull request**。
5. Eric reviews and merges. The site rebuilds itself within a few minutes.
   Eric 审核合并后，网站几分钟内自动更新。

---

## Fields / 字段说明

The block between the two `---` lines is the part the People page reads.

```yaml
---
layout: page
title: Ding Yi (丁毅)                        # English name (中文名)
description: PhD student (2023 Fall)         # role and start term
importance: 2023                             # start year — sorts the cards
category: Ph.D. Student                      # see the list below
related_publications: true                   # auto-lists your papers
img: assets/img/labmempic/dingyi.jpg          # your photo, optional
education: BSc, Jinan University             # degrees before HKBU
mail: dylan1021@comp.hkbu.edu.hk
office: DLB625
---
```

Anything you write **below** the closing `---` becomes your own page at
`/people/<your-id>/` — for example <https://ericcombiolab.github.io/people/wangjj/>.
The card on the People page links to it. This is the part you have the most
freedom over; see the template in the next section.

关闭的 `---` **下面**写的内容，就是你的个人页面
（例如 <https://ericcombiolab.github.io/people/wangjj/>），People 页面上的卡片
点进去就是它。这部分自由度最大，模板见下一节。

### `category`

Use exactly one of: `Postdoc`, `Ph.D. Student`, `MPhil Student`, `Alumni`.
必须是这四个之一，拼写要完全一致，否则你的卡片不会显示。

### `education`

Degrees earned **before** your current post at HKBU, most recent first,
separated by `; `. Use `PhD` / `MSc` / `BEng` / `BSc` — not `MS`, `BE` or `BS`.

加入 HKBU 之前的学历，最新的在前，用 `; ` 分隔。学位缩写统一用
`PhD` / `MSc` / `BEng` / `BSc`。

```
education: MSc, CUHK; BEng, Beihang University
```

### `img` — photo / 照片

- Put the file in `assets/img/labmempic/` and name it after your file id.
  放在 `assets/img/labmempic/`，文件名和你的 md 文件同名。
- **Portrait orientation, and under 200 KB.** The cards crop everything to 3:4,
  so a roughly 3:4 photo with your face in the upper half looks best. A 4 MB
  phone photo will be rejected by the size check — resize it to 600 px wide first.
  **竖构图，200 KB 以内。** 卡片按 3:4 裁切，脸在上半部分效果最好。
  手机原图（几 MB）会被检查拦下，先缩到 600 px 宽。

---

## Your own page / 你的个人页面

Copy this below the closing `---` and fill it in. Every section is optional —
delete what you do not need. Headings use `##`, list items start with `- `.

把下面这段复制到闭合的 `---` 之后再填写。每一节都是可选的，用不到就删掉。
`##` 是标题，`- ` 开头是列表项。

```markdown
I am a PhD student at Hong Kong Baptist University, supervised by Prof. Lu Zhang.
My research focuses on ... (one short paragraph about what you work on)

## Education
- Ph.D. in Computer Science, Hong Kong Baptist University, 2023 - present
- M.Sc. in ..., ... University, 2020 - 2023
- B.Eng. in ..., ... University, 2016 - 2020

## Research Experience
- **2024 - present: <project name>** — what you built or found, in one or two
  sentences. Mention the outcome (a paper, a tool, a dataset) if there is one.

## Awards
- Best Paper Award, <conference>, 2025

## Links
- [Personal website](https://example.com)
- [Google Scholar](https://scholar.google.com/citations?user=...)
- [GitHub](https://github.com/...)
```

### Publications / 论文列表

`related_publications: true` in the front matter already prints your **lab**
papers at the bottom of your page, under **References**, pulled from
`_bibliography/papers.bib`. Do not retype those — if one is missing there, tell
Eric so it gets added to the bibliography, which fixes the Publications page too.

Papers from **before you joined** are not in that bibliography, so list those
yourself under a heading that says so, e.g. `## Publications before joining the lab`.

front matter 里的 `related_publications: true` 会自动列出你在**本实验室**的论文，
显示在页面底部 **References**，数据来自 `_bibliography/papers.bib`。这部分不要
手写重复——缺了就告诉 Eric 补到文献库，Publications 页面也会一起修好。

**加入实验室之前**的论文不在那个文献库里，需要你自己写，建议用一个说明性的标题，
例如 `## Publications before joining the lab`。

### Preview before you submit / 提交前预览

In the GitHub editor, the **Preview** tab next to **Edit** renders your Markdown.
It will not show the site's styling, but it catches broken headings and links.

GitHub 编辑器里 **Edit** 旁边的 **Preview** 标签可以预览 Markdown 渲染效果。
样式和网站不完全一致，但足以发现标题、链接的格式错误。

---

## Notes / 注意

- Only edit **your own** file. If something about another member is wrong, tell
  Eric rather than editing their file.
  只改**你自己**的文件。别人的信息有误请告诉 Eric。
- The `Prettier` and `broken links` checks on your pull request were already
  failing before your change — you can ignore them. The check that matters is
  `Deploy site`.
  PR 上的 `Prettier` 和 `broken links` 检查在你改动之前就是失败的，可以忽略。
  要看的是 `Deploy site`。

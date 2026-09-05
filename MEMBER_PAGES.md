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

Anything you write **below** the closing `---` becomes the body of your own page
at `/people/<your-id>/` — research interests, education history, links, whatever
you like. Markdown works.

关闭的 `---` **下面**写的内容会成为你个人页面的正文，支持 Markdown。

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

## Notes / 注意

- Only edit **your own** file. If something about another member is wrong, tell
  Eric rather than editing their file.
  只改**你自己**的文件。别人的信息有误请告诉 Eric。
- The `Prettier` and `broken links` checks on your pull request were already
  failing before your change — you can ignore them. The check that matters is
  `Deploy site`.
  PR 上的 `Prettier` 和 `broken links` 检查在你改动之前就是失败的，可以忽略。
  要看的是 `Deploy site`。

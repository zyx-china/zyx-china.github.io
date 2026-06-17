# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 概述

张宇轩的 GitHub 个人主页，Jekyll + Minimal Mistakes 远程主题，部署于 GitHub Pages。
仓库：github.com/zyx-china/zyx-china.github.io，线上：zyx-china.github.io。

## 本地运行

```bash
bundle install
bundle exec jekyll serve
```

## 文件结构

- `_config.yml` — 站点配置（remote_theme、作者信息、导航、插件）
- `_data/navigation.yml` — 顶部导航菜单
- `index.md` — 首页（关于我、联系方式、教育背景）
- `cv.md` — 个人简历（教育、实习、科研、项目、获奖、技能）
- `projects.md` — 项目经历专题页（与 cv.md 有重叠内容，更详细的项目描述以 cv.md 为准）
- `about.md` — 关于本站
- `assets/images/bio-photo.jpg` — 头像

## 样式自定义

主题为远程主题，本地无 CSS 文件。自定义样式唯一有效的方式：**在 .md 文件 front matter 之后直接写 `<style>` 标签，属性需加 `!important`**。

目前所有页面统一 `html { font-size: 18px !important; }`，并调整了标题间距。

`_includes/head/custom.html` 方式已验证无效（CSS 被注入但被主题样式覆盖）。

## 注意事项

- **页面必须放在根目录**，不能放在 `_pages/` 等以下划线开头的目录中，GitHub Pages 默认不处理，会导致 404。
- 使用 `remote_theme: mmistakes/minimal-mistakes`，无需本地安装主题 gem。
- `Gemfile` 中保留 `github-pages` gem 以匹配线上环境。

## 更新流程

编辑对应文件 → `git add -A && git commit -m "..." && git push`，GitHub Pages 约 1-2 分钟后生效。

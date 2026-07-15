# 学习追踪

一个静态学习追踪器。

- `index.html`: PC 记录页，负责录入、编辑、同步。
- `mobile.html`: 手机只读看板，负责查看进度和复习重点。
- `learning.html`: 其他学习记录页，包含面试、C/C++、操作系统和内核四个模块。
- 算法数据保存在 GitHub Gist 的 `leetcode-tracker.json`。
- 其他学习记录保存在同一 Gist 的 `learning-notes.json`，两类数据互不覆盖。

## 使用顺序

1. 打开 `index.html`。
2. 第一次点击 `首次载入计划`。
3. 在 `云同步` 区域填写 GitHub Token。
4. 点击 `创建云端`，页面会生成 Gist ID。
5. 以后在 PC 上记录后点 `同步`。
6. 点击顶部的 `其他学习进展`，可记录面试笔记、C/C++、操作系统和内核学习内容。
7. 手机访问：

```text
https://locus-lyu.github.io/leetcode-tracker/mobile.html?gist=你的GistID&file=leetcode-tracker.json
```

## GitHub Pages 部署

把本文件夹里的文件上传到一个 GitHub 仓库，例如：

```text
leetcode-tracker
```

然后在仓库设置里开启 GitHub Pages，选择从 `main` 分支发布。

发布后：

```text
PC 页面：
https://locus-lyu.github.io/leetcode-tracker/

手机看板：
https://locus-lyu.github.io/leetcode-tracker/mobile.html?gist=你的GistID&file=leetcode-tracker.json

手机学习记录：
https://locus-lyu.github.io/leetcode-tracker/learning.html?mode=view&gist=你的GistID
```

## Token 注意

PC 端 Token 只保存在当前浏览器本地，用于创建/上传/下载 Gist。

手机端建议不填 Token，只读公开或 secret Gist。secret Gist 不会被公开搜索，但知道链接的人可以访问。

## 多电脑同步

每台电脑打开同一个 Pages 地址，填同一个 Gist ID 和 Token。

建议习惯：

```text
开始刷题前：先点 同步
记录完成后：再点 同步
```

当前版本是轻量同步，冲突策略是“更新时间较新的覆盖旧的”。

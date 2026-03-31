# claude-code-sourcemap

[![linux.do](https://img.shields.io/badge/linux.do-huo0-blue?logo=linux&logoColor=white)](https://linux.do)

> [!WARNING]
> This repository is **unofficial** and is reconstructed from the public npm package and source map analysis, **for research purposes only**.
> It does **not** represent the original internal development repository structure.
>
> 本仓库为**非官方**整理版，基于公开 npm 发布包与 source map 分析还原，**仅供研究使用**。
> **不代表**官方原始内部开发仓库结构。
> 一切基于L站"飘然与我同"的情报提供

## 概述

本仓库通过 npm 发布包（`@anthropic-ai/claude-code`）内附带的 source map（`cli.js.map`）还原的 TypeScript 源码，版本为 `2.1.88`。

## ⬇️ 下载方式 / How to Download

### 方式一：浏览器直接下载（推荐 / Recommended）

点击页面右上角绿色 **Code** 按钮 → 选择 **Download ZIP** 即可下载完整压缩包（约 77 MB）。

> ✅ 无需任何额外工具，解压后即可使用，与本地克隆内容完全一致。

---

### 方式二：Git 克隆（完整版含历史记录）

本仓库包含超过 30 MB 的大文件（`claude-code-2.1.88.tgz`），使用 **Git LFS** 存储。
普通 `git clone` **只会下载文件指针**，需要以下步骤才能获取完整文件：

```bash
# 第一步：安装 Git LFS（仅首次需要）
git lfs install

# 第二步：克隆仓库
git clone https://github.com/tom7749/claude-code-sourcemap.git

# 第三步：拉取 LFS 大文件（核心步骤！）
cd claude-code-sourcemap
git lfs pull
```

> ⚠️ 如果跳过 `git lfs pull`，`claude-code-2.1.88.tgz` 文件将只有几百字节（指针文件），而非真实内容。

---

## 来源

- npm 包：[@anthropic-ai/claude-code](https://www.npmjs.com/package/@anthropic-ai/claude-code)
- 还原版本：`2.1.88`
- 还原文件数：**4756 个**（含 1884 个 `.ts`/`.tsx` 源文件）
- 还原方式：提取 `cli.js.map` 中的 `sourcesContent` 字段

## 目录结构

```
restored-src/src/
├── main.tsx              # CLI 入口
├── tools/                # 工具实现（Bash、FileEdit、Grep、MCP 等 30+ 个）
├── commands/             # 命令实现（commit、review、config 等 40+ 个）
├── services/             # API、MCP、分析等服务
├── utils/                # 工具函数（git、model、auth、env 等）
├── context/              # React Context
├── coordinator/          # 多 Agent 协调模式
├── assistant/            # 助手模式（KAIROS）
├── buddy/                # AI 伴侣 UI
├── remote/               # 远程会话
├── plugins/              # 插件系统
├── skills/               # 技能系统
├── voice/                # 语音交互
└── vim/                  # Vim 模式
```

## 声明

- 源码版权归 [Anthropic](https://www.anthropic.com) 所有
- 本仓库仅用于技术研究与学习，请勿用于商业用途
- 如有侵权，请联系删除

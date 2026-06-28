# TYPING — 打字练习应用

## 项目概要

一个 **纯前端打字练习应用**，无后端依赖，所有逻辑写在单个 `index.html` 中。

| 项目 | 说明 |
|------|------|
| 开发者 | 樊 re (fanre) |
| GitHub | [reF0o0/codex-typing](https://github.com/reF0o0/codex-typing) |
| 技术栈 | 纯 HTML + CSS + JS（Vanilla），无框架 |
| 运行方式 | 直接在浏览器打开 `index.html`，无需构建步骤 |
| 本地依赖 | `package.json` 仅包含 `playwright`（用于测试/自动化），无其他运行时依赖 |

## 核心功能

### 打字练习
- 显示一段 **对话文本**（英文，职场/商务场景），用户输入对应文本进行练习
- 实时对比用户输入与目标文本：
  - 正确字符显示为 **绿色**
  - 错误字符显示为 **红色** 并加下划线
  - 未输入字符显示为 **灰色**

### 难度分级
| 级别 | 特征 |
|------|------|
| Easy | 简短日常对话（15 段） |
| Medium | 中等长度职场对话（15 段） |
| Hard | 长篇幅商务谈判/管理对话（15 段） |

### 时间限制
支持 15s / 30s / 60s（默认）/ 90s / 120s / 180s / Unlimited（不限时）

### 实时统计（练习中）
- 倒计时
- 实时 WPM（每分钟正确单词数）
- 实时准确率（%）
- 已输入字符数

### 结果展示（练习结束后）
- WPM
- 准确率
- 用时
- **Continue +30s**：时间到后可追加 30 秒继续
- **Try Again**：重新开始

### 历史记录
- 自动保存到 `localStorage`（上限 50 条）
- 显示日期、难度、时间限制、WPM、准确率、文本预览
- 可清空历史

## 项目历史（Git）

```
8792675 Initial commit: typing practice app
432ebcb update: add package.json and improve typing app
870e153 feat: add more time limit options (15s, 90s, 180s)
b1f1c89 gitignore: add .DS_Store
bde0ffe change typing content to workplace/business dialogues
83b4776 Merge branch 'codex/typing-content'
```

### 分支说明
- `codex/typing-content` — 分支名，内容已合并到主分支

## 远程仓库

```
Origin: git@github.com:reF0o0/codex-typing.git
```

## 运行环境（开发者本地）

| 信息 | 内容 |
|------|------|
| 系统用户名 | fanre |
| 设备 | fandeMacBook-Air.local |
| Shell | zsh |
| 包管理器 | npm（配置了 npmmirror 镜像） |
| Node 管理 | nvm |
| 操作系统 | macOS |

## 设计细节

- 配色：冷静的蓝白灰主题（`#f0f2f5` 背景，`#3b82f6` 主色）
- 字体：等宽字体（SF Mono / Fira Code / JetBrains Mono）用于打字区域
- 响应式：支持移动端布局（`max-width: 600px` 以下自适应）
- 模式：仅支持亮色模式

## 交互细节

- 练习中按 **Tab** 或错误的 **Enter** 会被阻止，防止打断输入流
- 时间少于 10 秒时，倒计时变红闪烁警示
- 输入框获得焦点后背景变深色（`#1e293b`），便于专注于输入
- 提供 **Exit** 按钮可随时退出当前练习回到待机状态

## 语料特点

所有语料均为 **职场/商务对话**（A/B 双人对话），内容涵盖：
日常办公、会议准备、项目管理、客户沟通、招聘面试、团队建设、财务报告、战略规划等真实职场场景。

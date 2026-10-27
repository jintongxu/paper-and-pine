# Paper & Pine

Paper & Pine 是一款面向技术笔记、项目文档和长期阅读的 Obsidian 主题。

它采用 **晴空蓝白** 视觉方向：白色正文、浅蓝界面、清晰的文件树路径、稳定的大纲面板，以及低干扰的代码块和引用样式。

## 功能特点

- 晴空蓝白色界面，适合长时间阅读和写作
- 当前文件路径增强：祖先目录、直接父目录和当前文件有明确层级
- 文件树不使用长引导线、箭头或装饰性方框
- 大纲面板使用白底和简洁的当前章节标识
- 普通引用使用冰蓝注释卡片
- 代码块使用浅蓝背景和语法高亮
- 代码复制按钮默认弱化，悬停时增强
- 低对比度滚动条
- 支持浅色模式和深色模式基础变量
- 支持窄窗口的基础适配

## 安装方式

### 方式一：下载 ZIP 安装

1. 打开仓库页面：

   <https://github.com/jintongxu/paper-and-pine>

2. 点击 **Code → Download ZIP**。
3. 解压 ZIP 文件。
4. 在解压目录中找到：

   ```text
   manifest.json
   theme.css
   ```

5. 在你的 Obsidian 库中创建主题目录：

   ```text
   <你的 Obsidian 库>/.obsidian/themes/Paper & Pine/
   ```

6. 将 `manifest.json` 和 `theme.css` 复制到该目录。
7. 打开 Obsidian，进入：

   ```text
   设置 → 外观 → 主题
   ```

8. 选择 **Paper & Pine**。

Windows 示例路径：

```text
D:\Dropbox\yun-file\obsidian_vault\.obsidian\themes\Paper & Pine\
```

最终目录结构应为：

```text
你的 Obsidian 库/
└── .obsidian/
    └── themes/
        └── Paper & Pine/
            ├── manifest.json
            └── theme.css
```

> 注意：`.obsidian` 目录通常是隐藏目录。如果看不到它，请在文件管理器中打开“显示隐藏项目”。

### 方式二：使用 Git 克隆

如果你使用 Git，可以先克隆仓库：

```bash
git clone https://github.com/jintongxu/paper-and-pine.git
```

然后将仓库中的 `manifest.json` 和 `theme.css` 复制到：

```text
<你的 Obsidian 库>/.obsidian/themes/Paper & Pine/
```

主题仓库本身不应该直接克隆到 `.obsidian/themes/Paper & Pine/` 后再套一层目录。Obsidian 需要在主题目录的第一层直接找到 `manifest.json` 和 `theme.css`。

## 更新主题

### ZIP 用户

1. 下载仓库最新 ZIP。
2. 关闭 Obsidian，或先切换到其他主题。
3. 用新版本的 `manifest.json` 和 `theme.css` 替换主题目录中的旧文件。
4. 重新打开 Obsidian，或切换主题刷新样式。

更新前建议备份：

```text
<你的 Obsidian 库>/.obsidian/themes/Paper & Pine/
```

### Git 用户

如果你保留了仓库克隆目录：

```bash
cd paper-and-pine
git pull
```

然后将最新的 `manifest.json` 和 `theme.css` 复制到你的 Obsidian 主题目录。

## 技术 Callout

主题支持几种适合技术笔记的 Callout 类型。它们需要在 Markdown 中显式声明，不会自动识别普通代码块或普通引用。

### 命令

```markdown
> [!COMMAND] 构建项目
> npm run build
```

也可以使用 `SHELL` 或 `TERMINAL`：

```markdown
> [!SHELL] 安装依赖
> npm install
```

### 输出结果

```markdown
> [!OUTPUT] 执行结果
> Build completed successfully.
```

也支持 `RESULT`。

### 错误

```markdown
> [!ERROR] 构建失败
> Module not found: xxx
```

也支持 `BUG`。

### 提示

```markdown
> [!TIP] 小提示
> 先确认 task_id，再检查 task_stage。
```

也支持 `HINT`。

## 代码块语言标签

普通代码块保持中性样式。若要显示语言标签，需要由外部 HTML 或插件生成 `data-lang` 属性，例如：

```html
<pre data-lang="sql">
  <code>SELECT * FROM tasks;</code>
</pre>
```

主题不会自动猜测代码语言，也不会修改 Markdown 内容。

## 专注阅读模式基础

主题提供了一个可供插件或自定义脚本使用的 CSS class：

```html
<body class="theme-light pp-focus-mode">
```

开启后会隐藏 ribbon、左右侧栏、标签栏和状态栏，并将正文宽度扩大到约 `1000px`。

当前版本只提供 CSS，不包含快捷键、命令或 JavaScript 自动切换。若要在 Obsidian 中通过命令切换，需要使用自定义插件、JS 脚本或其他可以添加 `body` class 的工具。

## 预览文件

仓库中包含两个视觉原型：

- `preview.html`：早期主题方向预览
- `style-options.html`：同一篇技术笔记的四种风格比较

它们只是浏览器预览，不是 Obsidian 插件，也不是安装主题所必需的文件。

## CSS 片段兼容性

Paper & Pine 是完整主题，不要求额外 CSS 片段。

如果你启用了自定义 CSS 片段，并且发现颜色没有生效，请依次排查：

1. 设置 → 外观 → CSS 代码片段。
2. 暂时关闭会修改正文、文件树、大纲、代码块或链接颜色的片段。
3. 在设置 → 外观中切换到其他主题，再切回 Paper & Pine。
4. 必要时重启 Obsidian。

CSS 片段通常会在主题之后加载，因此过于具体的 `!important` 规则可能覆盖 Paper & Pine 的样式。

## 卸载主题

1. 先在 Obsidian 设置中切换到其他主题。
2. 删除以下目录：

   ```text
   <你的 Obsidian 库>/.obsidian/themes/Paper & Pine/
   ```

3. 删除主题不会修改你的 Markdown 笔记、附件或 Properties。

## 反馈与贡献

欢迎提交 Issue 或 Pull Request：

<https://github.com/jintongxu/paper-and-pine/issues>

提交问题时，建议附上：

- Obsidian 版本
- 操作系统
- 浅色或深色模式
- 是否启用了 CSS 片段
- 最小复现截图
- 出问题的组件，例如文件树、大纲、代码块或引用

## 许可

当前仓库未附加独立许可证文件。如需在其他项目中重新发布或大幅修改，请先通过仓库 Issue 联系作者确认。

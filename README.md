# He Zhang | 张贺 — Academic Homepage

基于 [Start Bootstrap Resume](https://startbootstrap.com/theme/resume) 的个人学术主页。

- 网站地址：https://hector-hezhang.github.io/
- GitHub 账号：[Hector-HeZhang](https://github.com/Hector-HeZhang)
- 发布方式：GitHub Pages，`main` 分支的根目录 `/ (root)`。
- 使用 GitHub 默认地址，无需购买域名。

## 修改内容

编辑 `index.html` 可以修改简介、论文和经历。当前保留 About、Publications、Experience 三个栏目。
论文栏目根据本人提供的 Google Scholar 资料整理，按本人选择展示论文。所有论文使用一个连续列表，不按年份分组；个人简介和经历在对应栏目维护。
编辑 `custom.css` 可以调整主题颜色、字体和排版；`styles.css` 是上游模板样式。

直接在 GitHub 文件页面点击编辑，保存到 `main` 后，GitHub Pages 会自动重新部署。

## 更新论文

打开仓库中的 `index.html`，点击铅笔编辑，再搜索论文题目或 `Publication:` 注释。
每篇论文都在一个 `<article class="publication"> ... </article>` 中：

- `publication-title`：论文题目，标题链接指向论文记录。
- `publication-authors`：完整作者；`<strong>He Zhang</strong>` 表示加粗本人姓名，`<sup>*</sup>` 表示已经核实的共同一作。
- `publication-venue`：会议或期刊名称和年份，不显示卷号、期号、页码或文章编号。
- `publication-links`：Paper、PDF、Project、Code 等资源。
- `publication-image`：图形摘要/论文展示图。图片统一放在 `Graphic Abstract` 文件夹，文件名不再使用 `publication-` 前缀。

有颜色的资源文字可点击；灰色“待补充”是保留的接口，不会跳到错误地址。
例如找到某篇的 PDF 后，将这一篇下面的：

```html
<span class="resource-pending" aria-disabled="true" title="链接待补充">PDF · 待补充</span>
```

改为（将示意地址换成真正的 PDF 地址）：

```html
<a href="https://example.com/your-paper.pdf" target="_blank" rel="noopener noreferrer">PDF</a>
```

补图时，先上传图片到 `Graphic Abstract` 文件夹，再将该论文的 `publication-image-placeholder` 整个 `div` 换为：

```html
<a class="publication-image" href="Graphic%20Abstract/your-paper.png" target="_blank" rel="noopener noreferrer">
  <img src="Graphic%20Abstract/your-paper.png" alt="这篇论文的图形摘要" loading="lazy" decoding="async">
</a>
```

文件名和扩展名必须与上传的图片完全相同，包括大小写。已有图片可以直接覆盖同名文件；不需要重新配置 GitHub Pages。
页面没有运行时数据库或自动 Scholar 同步，修改 `index.html` 才会改变论文内容。
各篇资料、配图来源和年份差异见 `PUBLICATIONS-SOURCES.md`。

## 更换照片

照片文件是仓库根目录的 `Avatar.jpg`，文件名区分大小写。
在 GitHub 网页端覆盖上传同名照片并提交到 `main`，即可更新照片。
电脑宽屏的照片显示在侧栏；手机或较窄窗口的照片显示在简介区。
如果更改照片文件名，需要同步修改 `index.html` 中两处图片的 `src`。

## 文件

- `index.html`：网页内容。
- `styles.css`：Start Bootstrap Resume 7.0.6 样式。
- `custom.css`：个人主页定制样式。
- `Graphic Abstract/`：论文展示图，包括原有配图和本人补充上传的图形摘要。
- `PUBLICATIONS-SOURCES.md`：论文信息、图像来源与维护记录。
- `bootstrap.bundle.min.js`：Bootstrap 5.2.3，本地加载。
- `scripts.js`：导航交互。
- `.nojekyll`：按静态文件直接发布。
- `LICENSE`、`BOOTSTRAP-LICENSE`：上游 MIT 许可声明。

CSS、JS 文件与 HTML 放在同一目录，可以直接在网页端上传和编辑。

## 搜索引擎

初稿保留 `<meta name="robots" content="noindex, nofollow">`，提示搜索引擎暂不收录；不影响通过网址直接访问，也不构成访问权限限制。个人资料确认并补充完整后，可删除该行允许搜索引擎收录。

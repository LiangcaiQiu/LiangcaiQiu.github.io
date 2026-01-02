# 项目结构说明

这是一个基于 Jekyll 的学术网站项目。以下是项目结构和如何修改各个栏目的详细说明。

## 📁 核心目录结构

### 1. **配置文件**
- `_config.yml` - 网站主配置文件（网站标题、作者信息、主题设置等）
- `_data/navigation.yml` - 导航栏配置（控制顶部菜单栏的显示）

### 2. **页面目录 (`_pages/`)**
存放各个栏目的**列表页面**（显示所有条目的汇总页面）：

- `group.html` - Group 栏目的列表页
- `publications.html` - Publications 栏目的列表页
- `talks.html` - Talks 栏目的列表页
- `teaching.html` - Teaching 栏目的列表页
- `portfolio.html` - Portfolio 栏目的列表页
- `cv.md` - CV 页面
- `about.md` - 关于页面（首页）

### 3. **集合目录（Collections）**
存放各个栏目的**具体内容条目**：

#### `_publications/` - 论文/出版物
每个文件代表一篇论文，文件名格式：`YYYY-MM-DD-论文标题.md`

#### `_talks/` - 演讲/报告
每个文件代表一次演讲，文件名格式：`YYYY-MM-DD-演讲标题.md`

#### `_teaching/` - 教学经历
每个文件代表一次教学经历，文件名格式：`YYYY-MM-DD-课程名称.md`

#### `_portfolio/` - 作品集
每个文件代表一个作品，文件名格式：`portfolio-编号.md` 或 `portfolio-编号.html`

#### `_posts/` - 博客文章（已移除）
博客文章目录（当前导航栏中已移除）

### 4. **布局和模板**
- `_layouts/` - 页面布局模板
- `_includes/` - 可复用的 HTML 片段（如 `archive-single.html` 用于显示单个条目）

### 5. **静态资源**
- `images/` - 图片文件
- `files/` - PDF 等文件（论文、幻灯片等）

---

## 🔧 如何修改各个栏目的内容

### 1. **修改 Group 栏目**

**修改列表页：**
- 编辑 `_pages/group.html` - 修改团队成员的显示方式

**添加/修改成员：**
- 直接在 `_pages/group.html` 中添加新的成员区块（使用相同的 HTML 结构）

**示例结构：**
```html
<div class="list__item">
  <article class="archive__item">
    <h2 class="archive__item-title">成员姓名 (Ph.D.)</h2>
    <p class="archive__item-excerpt">成员简介</p>
    <h3>Research Interests</h3>
    <ul>
      <li><strong>研究方向</strong>: 描述</li>
    </ul>
  </article>
</div>
```

---

### 2. **修改 Publications 栏目**

**修改列表页：**
- 编辑 `_pages/publications.html` - 修改论文列表的显示方式

**添加新论文：**
1. 在 `_publications/` 目录下创建新文件
2. 文件名格式：`YYYY-MM-DD-论文标题.md`（例如：`2024-12-01-my-paper.md`）
3. 文件内容格式：

```markdown
---
title: "论文标题"
collection: publications
category: manuscripts  # manuscripts, conferences, books
permalink: /publication/2024-12-01-my-paper
excerpt: '论文摘要'
date: 2024-12-01
venue: '期刊名称'
slidesurl: 'http://example.com/slides.pdf'  # 可选
paperurl: 'http://example.com/paper.pdf'     # 可选
bibtexurl: 'http://example.com/bibtex.bib'   # 可选
citation: '作者名. (2024). "论文标题." <i>期刊名</i>. 卷(期).'
---

这里是论文的详细描述，可以使用 Markdown 格式。
```

**修改现有论文：**
- 直接编辑 `_publications/` 目录下对应的 `.md` 文件

---

### 3. **修改 Talks 栏目**

**修改列表页：**
- 编辑 `_pages/talks.html`

**添加新演讲：**
1. 在 `_talks/` 目录下创建新文件
2. 文件名格式：`YYYY-MM-DD-演讲标题.md`
3. 文件内容格式：

```markdown
---
title: "演讲标题"
collection: talks
type: "Talk"  # 或 "Tutorial", "Workshop" 等
permalink: /talks/2024-12-01-my-talk
venue: "机构名称, 部门"
date: 2024-12-01
location: "城市, 国家"
---

这里是演讲的详细描述。
```

---

### 4. **修改 Teaching 栏目**

**修改列表页：**
- 编辑 `_pages/teaching.html`

**添加新教学经历：**
1. 在 `_teaching/` 目录下创建新文件
2. 文件名格式：`YYYY-MM-DD-课程名称.md`
3. 文件内容格式：

```markdown
---
title: "课程名称"
collection: teaching
type: "Undergraduate course"  # 或 "Graduate course" 等
permalink: /teaching/2024-spring-my-course
venue: "大学名称, 院系"
date: 2024-01-01
location: "城市, 国家"
---

这里是课程描述。
```

---

### 5. **修改 Portfolio 栏目**

**修改列表页：**
- 编辑 `_pages/portfolio.html`

**添加新作品：**
1. 在 `_portfolio/` 目录下创建新文件
2. 文件名格式：`portfolio-编号.md` 或 `portfolio-编号.html`
3. 文件内容格式：

```markdown
---
title: "作品标题"
excerpt: "简短描述<br/><img src='/images/图片名.png'>"
collection: portfolio
---

这里是作品的详细描述。
```

---

### 6. **修改 CV 页面**

- 直接编辑 `_pages/cv.md` 文件
- 使用 Markdown 格式编写

---

### 7. **修改导航栏**

- 编辑 `_data/navigation.yml`
- 修改 `main:` 下的列表来调整菜单项的顺序和内容

---

### 8. **修改网站基本信息**

- 编辑 `_config.yml`
- 主要配置项：
  - `title` - 网站标题
  - `author` - 作者信息（姓名、邮箱、头像等）
  - `url` - 网站 URL
  - `collections` - 集合配置

---

## 📝 文件命名规则

### 集合文件（Publications, Talks, Teaching, Portfolio）
- **日期格式**：`YYYY-MM-DD-标题.md`
- **示例**：`2024-12-01-my-paper.md`
- 日期用于排序，最新的会显示在最前面

### 页面文件（_pages/）
- 使用 `.html` 或 `.md` 扩展名
- 文件名会映射到 URL（通过 `permalink` 配置）

---

## 🎨 修改样式

- `_sass/` - SCSS 样式文件
- `assets/css/` - CSS 文件
- 修改这些文件可以改变网站的外观

---

## 💡 常用操作总结

| 操作 | 文件位置 |
|------|---------|
| 添加新论文 | `_publications/YYYY-MM-DD-标题.md` |
| 添加新演讲 | `_talks/YYYY-MM-DD-标题.md` |
| 添加新课程 | `_teaching/YYYY-MM-DD-标题.md` |
| 添加新作品 | `_portfolio/portfolio-编号.md` |
| 修改团队成员 | `_pages/group.html` |
| 修改导航栏 | `_data/navigation.yml` |
| 修改网站信息 | `_config.yml` |
| 上传图片 | `images/` 目录 |
| 上传PDF文件 | `files/` 目录 |

---

## 🔍 查找文件技巧

1. **按栏目查找**：每个栏目都有对应的目录（`_publications/`, `_talks/` 等）
2. **按日期查找**：文件名通常包含日期，可以按日期排序
3. **使用搜索**：在编辑器中搜索关键词来定位文件

---

## ⚠️ 注意事项

1. **Front Matter**：每个 Markdown 文件开头必须有 `---` 包围的 YAML 配置
2. **集合名称**：确保 `collection:` 字段与目录名一致（如 `publications`, `talks` 等）
3. **日期格式**：使用 `YYYY-MM-DD` 格式
4. **图片路径**：使用 `/images/图片名.png` 格式
5. **文件路径**：使用 `/files/文件名.pdf` 格式


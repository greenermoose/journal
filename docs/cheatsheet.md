---
layout: page
title: Cheatsheet
permalink: /cheatsheet/
---

This is a quick reference guide for adding new posts to this coding journal and using Markdown.

## How to Add a New Post

### The Automated Way
Just ask Antigravity to do it! You can say something like:
> "Create a new post about my thoughts on two spaces versus four for tabs."

Antigravity has a custom skill configured to automatically create the file in the `_posts` folder with the correct date prefix, filename format, and front matter.

### The Manual Way
To create a post manually:
1. Open `docs/_posts`
2. Create a new markdown file named `YYYY-MM-DD-title-of-post.md` (e.g., `2026-07-03-my-new-post.md`).
3. Add the following YAML front matter at the top of the file:

```yaml
---
layout: post
title: "Your Post Title Here"
date: YYYY-MM-DD HH:MM:SS -0400
categories: general
---
```
4. Write your content below the second `---`.

---

## Markdown Examples

### Text Formatting

* **Bold Text**: `**Bold Text**`
* *Italic Text*: `*Italic Text*`
* ***Bold and Italic***: `***Bold and Italic***`
* ~~Strikethrough~~: `~~Strikethrough~~`

### Lists

**Unordered List:**
- Item 1
- Item 2
  - Nested Item A
  - Nested Item B

```markdown
- Item 1
- Item 2
  - Nested Item A
  - Nested Item B
```

**Ordered List:**
1. First step
2. Second step
3. Third step

```markdown
1. First step
2. Second step
3. Third step
```

### Links and Images

**Hyperlink:**
[GitHub](https://github.com)
```markdown
[GitHub](https://github.com)
```

**Image:**
![Placeholder Image](https://via.placeholder.com/150)
```markdown
![Placeholder Image](https://via.placeholder.com/150)
```

### Code Snippets

**Inline code:**
Use the `print()` function.
```markdown
Use the `print()` function.
```

**Code Block (with syntax highlighting):**
```python
def hello_world():
    print("Hello, world!")
```
<pre>
```python
def hello_world():
    print("Hello, world!")
```
</pre>

### Blockquotes

> This is a blockquote. It's great for emphasizing text or quoting someone.

```markdown
> This is a blockquote. It's great for emphasizing text or quoting someone.
```

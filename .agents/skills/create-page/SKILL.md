---
name: create-page
description: Creates a new standalone page in the docs directory with the correct front matter and adds it to the navigation dropdown.
---

# create-page

This skill guides you through the process of creating a new standalone page for the journal and ensuring it is correctly integrated into the site's navigation.

## Steps

When asked to create a new page, follow these steps exactly:

1. **Create the Markdown file**:
   - Create a new markdown file in the `docs/` folder (e.g., `docs/my-page.md`).

2. **Add the YAML Front Matter**:
   - Ensure the new markdown file contains the following front matter:
     ```yaml
     ---
     layout: page
     title: "Your Page Title"
     permalink: /your-page/
     ---
     ```
   - **Critical Rule**: You MUST include the `permalink` field. It should match the filename but without the extension, wrapped in forward slashes (e.g., for `about.md`, the permalink is `/about/`).

3. **Update the Footer Navigation**:
   - Open `docs/_layouts/default.html`.
   - Locate the paragraph containing the navigation links inside `<footer class="site-footer" role="contentinfo">`.
   - Add a link to the new page using the `relative_url` filter and the permalink you defined, separating it from the previous link with a pipe (` | `).
   - Example addition:
     ```html
     | <a href="{{ '/your-page/' | relative_url }}">Your Page Title</a>
     ```

4. **Verify**:
   - Ensure you did not introduce any syntax errors in the HTML.
   - Confirm that the new file's content sits below the front matter (`---`).

---
name: create-post
description: Creates a new journal post in the docs/_posts directory with the correct filename format and Jekyll front matter.
---

# Create a New Post

When the user asks you to "create a post" or "add a journal entry", you should use this skill to create a new post for them.

## Requirements

1. **Filename Format**: The file MUST be created in the `docs/_posts` directory.
2. **Filename Structure**: The filename MUST follow the Jekyll format: `YYYY-MM-DD-title-in-kebab-case.md`. Use the current date based on the system timezone.
3. **Front Matter**: Every new post MUST begin with the following YAML front matter:

```yaml
---
layout: post
title: "The Exact Title the User Provided"
date: YYYY-MM-DD HH:MM:SS -0400
categories: general
---
```
*(Ensure the date in the front matter includes the time and timezone offset).*

## Workflow
1. If the user hasn't provided a title, ask them for one.
2. If they provided a topic or initial thoughts, draft the post body using markdown.
3. Use the `write_to_file` tool to create the file in `docs/_posts/` with the drafted content and front matter.
4. Notify the user that the post has been created, and provide a link to the file using markdown file links (e.g. `[filename](file:///path/to/file)`).

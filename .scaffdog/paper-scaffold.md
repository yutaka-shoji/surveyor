---
name: "paper"
root: "topics"
output: "**/*"
ignore: []
questions:
  year:
    message: "Publish Year"
  journal:
    message: "Journal Name"
  author:
    message: "Author (Last Name)"
  title:
    message: "Title (enter complete title)"
  url:
    message: "DOI URL"
    initial: "None"
---

# `{{ inputs.year }}-{{ inputs.author | lower }}/paper.md`

```markdown
{{ "templates/paper.md" | read }}
```

# `{{ inputs.year }}-{{ inputs.author | lower }}/public/.gitkeep`

```

```

# `slides.md`

```markdown
{{ "templates/append.md" | read }}
```

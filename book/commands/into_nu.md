---
title: into nu
version: 0.66.1
usage: |
  Convert expression into a nu value for access and exploration
---

# <code>{{ $frontmatter.title }}</code>

<div style='white-space: pre-wrap;'>{{ $frontmatter.usage }}</div>

## Signature

```> into nu ```

## Examples

Convert a col expression into a nushell value
```shell
> col a | into nu
```

---
name: add-article
description: Research a supplied topic and add a 200-250 word general-audience article to this project's src/data/articles.js using its existing article structure.
---

# Add Article

Use the topic provided with the request as input, for example: `$add-article How black holes are formed`. If no topic is supplied or available from context, ask for it before writing.

## Research and write

- Read the project's AGENTS.md instructions and `src/data/articles.js` before editing. Treat existing articles as the authority for field names, types, formatting, and export structure.
- Research the topic online using authoritative sources, preferably primary sources such as scientific agencies, research institutions, or official documentation. Read the relevant source material rather than relying only on search snippets. Check dates when facts may have changed.
- Write an original, accurate article for a general audience. Explain unfamiliar terms, avoid unnecessary jargon, and distinguish established facts from hypotheses or unresolved questions.
- Keep the article body (`content`) between **200 and 250 words inclusive**. The title and summary do not count toward this limit. Use readable paragraphs and a concise title and summary matching the existing style.

## Add to the data file

Append one article to the existing array in `src/data/articles.js`. Preserve all existing entries and the default export. Match the existing keys and their order; the current structure is:

```js
{
  id: 4,
  title: "Article Title",
  summary:
    "A concise description of the article.",
  content: `Article paragraphs separated by blank lines.`,
  author: "Editorial Team",
  date: "YYYY-MM-DD",
},
```

- Choose the next unused numeric ID, normally the highest existing ID plus one; the ID above is illustrative.
- Set `author` to `"Editorial Team"` and `date` to the current date in `YYYY-MM-DD` format. Determine today's date at execution time rather than copying an existing article's date.
- Keep content valid JavaScript, escaping backticks or interpolation sequences if needed. Preserve the file's encoding and surrounding style.
- Keep source links in the completion message rather than adding new data fields or citation markup that the app does not support.
- Limit changes to the article data. Do not add features, routing, dependencies, a backend, or persistence.

## Verify and report

- Import the data module with Node to confirm it parses. Count the new content's words with `content.trim().split(/\s+/).length`; revise until the count is within 200-250.
- Verify the new entry matches existing field names and types, has a unique ID, and uses the correct author and current date.
- Run `npm run build` to check integration. On Windows PowerShell, use `npm.cmd run build` if execution policy blocks `npm.ps1`.
- Report the added title, file location, word count, author, date, validation result, and links to the sources used. If research or validation cannot be completed, state the limitation accurately.

---
name: md-to-pdf
description: Use when Codex needs to convert Markdown files into full-color PDFs with local browser rendering and visual verification.
---

# Markdown To PDF

Use a local script to convert Markdown to styled HTML, then print it to PDF with Microsoft Edge or Chrome headless mode.

## Workflow

1. Identify the absolute directory containing the Markdown files.
2. Run the local converter script.
3. Confirm each expected PDF was updated during this run.
4. Check file size, page count, and text extraction.
5. If layout matters, render at least the first and last page.

Example:

```powershell
python examples\plugins\md-pdf-toolkit\scripts\build_docs_pdf.py --dir <docs-directory>
```

## Windows Filename Trap

Some browser print pipelines fail when the output PDF path contains spaces, non-ASCII characters, or special characters.

The example script avoids this by printing to an ASCII temporary PDF path first, then replacing the intended target file with Python.

## Safety

- Do not commit or push generated PDFs unless the user explicitly asks.
- Do not upload or share PDFs unless the target is clear.
- Keep scripts used by the skill next to the skill/plugin source.

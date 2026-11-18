# Code AI Detector

A single-page tool that highlights lines of code matching patterns common in AI-generated code. Paste or upload a file, and every line is colored as you type:

- **Red**: likely AI
- **Yellow**: possible AI
- **Green dot**: a human marker (TODOs, notes to self, commented-out code, debug prints)

Click any line to see which rules it matched. Supports Python, MATLAB, JavaScript/TypeScript, C/C++ and Java.

## Run it

Open `index.html` in a browser. There is no build step and no server. Code you paste never leaves your browser.

## How it works

The detector scores each line with heuristic rules (narrating comments, "Step 1" comments, Args/Returns docstrings, assistant phrasing like "edge case" or "for demonstration purposes", emoji, catch-all error handlers, polished output), then blends in the score of the surrounding block. Human markers lower the score.

## Limitations

This matches style patterns only. It cannot prove who wrote the code: careful people write tidy, well-commented code, and AI output can be edited to look casual. Treat a high score as a reason to look closer, never as proof on its own.

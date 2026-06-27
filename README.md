
# 🔥 Defolder - Recursive File Text Extractor

> Extract all text from your project files into a single, organized document.

[![Made with JavaScript](https://img.shields.io/badge/Made%20with-JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Built with HTML](https://img.shields.io/badge/Built%20with-HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![Styled with CSS](https://img.shields.io/badge/Styled%20with-CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![Uses jQuery](https://img.shields.io/badge/Uses-jQuery-0769AD?style=for-the-badge&logo=jquery&logoColor=white)](https://jquery.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Demo](#-demo)
- [Installation](#-installation)
- [Usage](#-usage)
- [How It Works](#-how-it-works)
- [Supported File Types](#-supported-file-types)
- [Browser Compatibility](#-browser-compatibility)
- [Project Structure](#-project-structure)
- [Contributing](#-contributing)
- [License](#-license)
- [Author](#-author)

---

## 🎯 Overview

**Defolder** is a powerful, browser-based tool that recursively traverses through all sub-folders and files in a selected directory, extracting text content from every text-based file. It compiles everything into a single, well-organized `.txt` file with clear file path headers for easy navigation.

Whether you're a developer needing to analyze codebases, a technical writer documenting projects, or someone who needs to audit text content across multiple files, Defolder makes the process seamless and instant.

---

## ✨ Features

### 🚀 Core Functionality
- **Recursive Directory Traversal** - Visits every sub-folder and file in your directory tree
- **Smart File Filtering** - Automatically identifies and extracts only text-based files
- **Organized Output** - Each file's content is preceded by its path header
- **Real-time Progress Tracking** - See exactly which file is being processed
- **Instant Download** - Get your extracted file immediately

### 🎨 User Experience
- **Intuitive Interface** - Simple folder picker with one-click extraction
- **Fire-Brick Red Theme** - Modern, eye-catching design with glow effects
- **Responsive Layout** - Works perfectly on desktop, tablet, and mobile
- **Visual Feedback** - Progress bars, status messages, and animations
- **Error Handling** - Clear error messages with actionable guidance

### 🔒 Privacy & Security
- **100% Local Processing** - No data leaves your browser
- **No Server Uploads** - Everything runs client-side
- **No API Keys** - No external dependencies required

---

## 🖼️ Demo

### How It Works

```

User Flow:
┌─────────────────┐
│  Select Folder  │ → Choose any folder on your system
└────────┬────────┘
↓
┌─────────────────┐
│  Click Extract  │ → Defolder begins traversing
└────────┬────────┘
↓
┌─────────────────┐
│  Live Progress  │ → Watch files being processed in real-time
└────────┬────────┘
↓
┌─────────────────┐
│  Auto-Download  │ → Your organized text file is ready!
└─────────────────┘

```

### Example Output Format

```

•) app/layout.tsx:
/* texts from app/layout.tsx */
import type { Metadata } from 'next';
export const metadata: Metadata = {
title: 'Defolder',
description: 'Extract all your code files into a single text file',
};
// ... rest of the file content

•) app/page.tsx:
/* texts from app/page.tsx */
'use client';
import { useState } from 'react';
// ... rest of the file content

•) app/auth/login/page.tsx:
/* texts from app/auth/login/page.tsx */
// ... file content

•) app/styles/globals.css:
/* texts from app/styles/globals.css */
:root {
--fire-brick: #B22222;
}
// ... rest of the file content

```

---

## 📦 Installation

### Option 1: Direct Download (Recommended)

1. **Download** the `index.html` file
2. **Save** it anywhere on your computer
3. **Open** in your browser (Chrome/Edge/Opera recommended)
4. **Start extracting** immediately! 🚀

No installation, no dependencies, no setup required!

### Option 2: Clone Repository

```bash
# Clone the repository
git clone https://github.com/yourusername/defolder.git

# Navigate to the directory
cd defolder

# Open in your browser
# Double-click index.html or use your preferred method
```

Option 3: Run with Live Server (Development)

```bash
# Using VS Code with Live Server extension
# Right-click index.html → Open with Live Server

# Or using Python
python -m http.server 8000

# Or using Node.js
npx serve .
```

---

🚀 Usage

Quick Start Guide

1. Open index.html in your browser
2. Click the "Choose Folder" button
3. Select the folder you want to extract
4. Click "Extract Files"
5. Watch the progress bar fill up
6. Download your organized text file automatically

Pro Tips

· 💡 Large Projects: For folders with 1000+ files, processing may take a few seconds
· 💡 File Types: Only text-based files are extracted (see supported types below)
· 💡 Browser: Use Chrome/Edge/Opera for the best experience
· 💡 Privacy: All processing is done locally - nothing is uploaded

Keyboard Shortcuts

Action Shortcut
Choose Folder Ctrl/Cmd + O (browser default)
Extract Files Enter (when button is focused)

---

🔧 How It Works

Technical Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                    Defolder Architecture                     │
├─────────────────────────────────────────────────────────────┤
│                                                               │
│  ┌──────────────┐    ┌──────────────┐    ┌──────────────┐  │
│  │  UI Layer    │───▶│  Logic Layer │───▶│  Output Layer │  │
│  │  (HTML/CSS)  │    │  (JavaScript) │    │  (Download)   │  │
│  └──────────────┘    └──────────────┘    └──────────────┘  │
│         │                    │                    │          │
│         ▼                    ▼                    ▼          │
│  ┌─────────────────────────────────────────────────────┐    │
│  │         File System Access API (Browser)            │    │
│  │  • showDirectoryPicker() - Folder selection         │    │
│  │  • FileSystemDirectoryHandle - Directory traversal  │    │
│  │  • FileSystemFileHandle - File reading              │    │
│  └─────────────────────────────────────────────────────┘    │
│                                                               │
└─────────────────────────────────────────────────────────────┘
```

Algorithm Overview

1. Folder Selection - Uses the File System Access API (showDirectoryPicker())
2. Directory Traversal - Recursively iterates through all sub-directories
3. File Filtering - Checks file extensions against allowed text types
4. Text Extraction - Reads file content using FileReader API
5. Content Formatting - Organizes with file path headers
6. File Generation - Creates a formatted text file for download

---

📁 Supported File Types

Code Files

```
.js, .jsx, .ts, .tsx, .py, .rb, .go, .rs, .c, .cpp
.h, .hpp, .java, .kt, .swift, .php, .vue, .svelte
```

Web Files

```
.html, .css, .scss, .sass, .less, .xml
```

Config & Data Files

```
.json, .yaml, .yml, .toml, .ini, .cfg, .env
```

Documentation Files

```
.md, .txt, .rst, .adoc, .tex
```

Shell & Script Files

```
.sh, .bash, .zsh, .fish, .ps1
```

Note: Binary files (images, videos, PDFs, executables) are automatically skipped.

---

🌐 Browser Compatibility

Browser Support Notes
Chrome (86+) ✅ Full Support Recommended for best performance
Edge (86+) ✅ Full Support Chromium-based, works perfectly
Opera (72+) ✅ Full Support Chromium-based
Firefox ❌ Not Supported Does not support File System Access API
Safari ❌ Not Supported Does not support File System Access API
Brave ✅ Full Support Chromium-based

Important: The File System Access API is currently only available in Chromium-based browsers.

---

📂 Project Structure

```
defolder/
├── index.html              # Complete application (HTML + CSS + JS)
├── README.md               # This documentation
└── LICENSE                 # MIT License

# No other files needed! Everything is self-contained in index.html
```

---

🤝 Contributing

Ways to Contribute

1. Report Bugs - Open an issue with detailed steps to reproduce
2. Suggest Features - Share your ideas for improvements
3. Submit PRs - Fix bugs or add features
4. Improve Documentation - Help make the docs better
5. Spread the Word - Share Defolder with others

Development Setup

```bash
# Fork the repository
# Clone your fork
git clone https://github.com/yourusername/defolder.git

# Make changes to index.html
# Test in Chrome/Edge/Opera

# Commit and push
git add .
git commit -m "Description of changes"
git push origin main

# Open a Pull Request
```

Guidelines

· Keep the single-file architecture
· Maintain the fire-brick red theme
· Ensure cross-browser compatibility (where supported)
· Write clean, well-commented code
· Test thoroughly before submitting

---

📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

```
MIT License

Copyright (c) 2026 Fatherly P. Titus

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.


---

👨‍💻 Author

Fatherly P. Titus ©2026


---

🙏 Acknowledgments

· File System Access API - For enabling browser-based file system access
· Font Awesome - For the beautiful icon set
· Google Fonts - For the Inter typeface
· jQuery - For simplifying DOM manipulation

---

📊 Statistics

https://img.shields.io/github/repo-size/fatherlytitus/defolder
https://img.shields.io/github/stars/fatherlytitus/defolder?style=social
https://img.shields.io/github/forks/fatherlytitus/defolder?style=social
https://img.shields.io/github/issues/fatherlytitus/defolder

---

🎯 Roadmap

· Dark/Light mode toggle
· File type filtering options
· Exclude patterns (node_modules, .git, etc.)
· Copy to clipboard functionality
· Preview extracted content before download
· Drag-and-drop folder selection
· Multi-language support
· Export to different formats (JSON, CSV, Markdown)

---

💬 FAQ

Q: Why is the "Extract Files" button disabled?
A: You need to select a folder first. Click "Choose Folder" to enable it.

Q: Can I extract from network drives?
A: Yes, as long as your browser has access to the network location.

Q: What happens with very large files?
A: The browser handles them efficiently, but extremely large files (>100MB) may take time.

Q: Is my data sent anywhere?
A: No! Everything runs 100% locally in your browser.

Q: Can I extract from multiple folders?
A: Currently, one folder at a time. Select the parent folder to include all sub-folders.

Q: Why does Safari not work?
A: Safari doesn't support the File System Access API yet. Use Chrome/Edge/Opera.

---

🚀 Quick Links

· Report Bug
· Request Feature
· View Source

---

⭐ Show Your Support

If you find Defolder useful, please give it a ⭐ on GitHub! It helps others discover this tool.

---

Built with ❤️ by Fatherly P. Titus

```
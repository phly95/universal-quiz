# Universal Quiz Player

A powerful, browser-based quiz player with support for AI-generated quizzes from transcripts. No backend required—just open the HTML file and start learning.

[![Live Demo](https://img.shields.io/badge/🚀-Try%20it%20Live-success?style=for-the-badge)](https://phly95.github.io/universal-quiz/)
![Quiz Player Preview](https://img.shields.io/badge/Platform-Web-blue) ![License](https://img.shields.io/badge/License-MIT-green)

## 🚀 Try it Now

**No installation needed!** Use the quiz player directly in your browser:

👉 **[https://phly95.github.io/universal-quiz/](https://phly95.github.io/universal-quiz/)**

Works on desktop and mobile. All data stays in your browser (localStorage).

## ✨ Features

### 🎯 Question Types
- **Single Choice** - Classic multiple choice with one correct answer
- **Multiple Choice** - Select all that apply
- **True/False** - Binary fact checking
- **Drag & Drop Ordering** - Arrange steps/items in correct sequence
- **Drag & Drop Matching** - Match concepts to categories

### 📚 Case Studies
- Multi-tab scenario presentations
- Nested questions referencing shared context
- Perfect for certification exams (Azure, AWS, etc.)

### 💾 Progress Management
- **Auto-save** - Progress is automatically saved to localStorage
- **Resume** - Pick up where you left off, even after closing the browser
- **Manual Save** - Copy save state to clipboard for backup/sharing
- **Export Results** - Copy detailed results for AI tutoring discussions

### 📊 Results & Analytics
- Visual score display with animated progress ring
- Pass/fail indication with customizable passing score
- Per-question review with explanations
- Export formats:
  - **AI Discussion** - Formatted summary for tutoring
  - **Full JSON** - Complete result data

### 🤖 AI-Powered Quiz Generation
- **Multi-provider support** - Works with Kimi, Copilot Enterprise, Claude, and ChatGPT
- **Built-in prompt generator** - Creates optimized prompts for each AI provider
- **Transcript to quiz** - Convert video transcripts, docs, or any text into interactive quizzes
- **Download option** - For AI providers that require file upload (Copilot Enterprise)

### 📱 Modern UI
- Clean, responsive design (works on mobile & desktop)
- Smooth animations and transitions
- Progress bar and question navigation
- **Built-in help** - Step-by-step guide for new users
- Keyboard-friendly controls

## 🚀 Quick Start

### Option 1: Use Online (Easiest)
1. **Go to [phly95.github.io/universal-quiz/](https://phly95.github.io/universal-quiz/)**
2. **Paste quiz JSON** or click **"🤖 Generate from Transcript"** to create one from video transcripts
3. **Click "❓ Help"** if you need a guided walkthrough
4. **Start learning!**

### Option 2: Use Locally
1. **Download or clone this repo**
2. **Open `index.html`** in any modern browser
3. **Paste quiz JSON** into the text area (see format below) or generate from transcript
4. **Click "Load Quiz"**
5. **Start learning!**


## 📋 Quiz JSON Format

```json
{
  "quizTitle": "Azure Fundamentals Practice",
  "passingScore": 70,
  "questions": [
    {
      "id": 1,
      "type": "single",
      "question": "What is the primary benefit of cloud computing?",
      "explanation": "Cloud computing eliminates capital expenses... Therefore, the correct option is Pay-as-you-go pricing.",
      "options": [
        "Pay-as-you-go pricing",
        "Higher maintenance costs",
        "Fixed capacity",
        "Longer deployment times"
      ],
      "correctAnswer": 0
    },
    {
      "id": 2,
      "type": "multiple",
      "question": "Select all valid Azure services:",
      "explanation": "Azure App Service and Azure Functions are both valid... Therefore, the correct options are App Service and Functions.",
      "options": [
        "Azure App Service",
        "Azure Functions",
        "AWS Lambda",
        "Google Cloud Run"
      ],
      "correctAnswer": [0, 1]
    },
    {
      "id": 3,
      "type": "dragdrop",
      "dragdropType": "order",
      "question": "Order these steps for deploying a web app:",
      "explanation": "The correct deployment sequence is... Therefore, the correct order is Create Resource Group → Create App Service Plan → Deploy Code → Configure Custom Domain.",
      "items": [
        "Deploy Code",
        "Create Resource Group",
        "Create App Service Plan",
        "Configure Custom Domain"
      ],
      "correctOrder": [2, 0, 1, 3]
    }
  ],
  "caseStudies": [
    {
      "id": 100,
      "title": "Case Study: E-commerce Migration",
      "scenario": "A company wants to migrate their e-commerce platform...",
      "tabs": [
        {"label": "Current State", "content": "On-premises servers..."},
        {"label": "Requirements", "content": "99.9% uptime required..."},
        {"label": "Constraints", "content": "Budget limit of $50k..."}
      ],
      "questions": [
        {
          "id": 101,
          "type": "single",
          "question": "Which service should they use for auto-scaling?",
          "explanation": "Based on the requirements tab...",
          "options": ["VM Scale Sets", "Single VM", "Local Server", "Containers"],
          "correctAnswer": 0
        }
      ]
    }
  ]
}
```

## 🤖 Generating Quizzes from Transcripts

The quiz player includes a built-in **"Generate from Transcript"** feature that creates AI prompts from your video transcripts or documents. Works with multiple AI providers:

| AI Provider | Workflow | Notes |
|-------------|----------|-------|
| **[Kimi](https://kimi.com)** 🌙 | Copy/paste | **Recommended** - Best quality, chunked output, handles long transcripts |
| **[Copilot Enterprise](https://copilot.cloud.microsoft)** 🪟 | Download/upload | File upload required (paste has length limits). Type "." in message box to send. |
| **[Claude](https://claude.ai)** 🧠 | Copy/paste | Large context window, handles long prompts well |
| **[ChatGPT](https://chat.openai.com)** 💬 | Copy/paste | Results vary by model |

> 💡 **Tip:** For YouTube videos, use **[youtubetotranscript.com](https://youtubetotranscript.com)** to easily extract the transcript. Just paste the YouTube URL and copy the text.

### Supported Content Sources
- **Video transcripts** (YouTube, lectures, tutorials)
- **Documentation** (technical docs, textbooks)
- **Meeting recordings** (training sessions, presentations)
- **Any text content** you want to turn into a quiz!

### How to Generate a Quiz

1. **Click "🤖 Generate from Transcript"** in the quiz player
2. **Select your AI provider** (Kimi recommended for best results)
3. **Paste your transcript** into the text area
4. **Click "Generate Prompt"** to create the AI prompt
5. **Copy** (or download for Copilot) the prompt
6. **Open your chosen AI** and paste/send the prompt
7. **The AI will generate** a quiz JSON file
8. **Paste the JSON back** into the quiz player and click "Load Quiz"

> 💡 **New to the app?** Click the **"❓ Help"** button for a step-by-step guide!

### Why Kimi is Recommended

The Kimi workflow has unique features for best results:

| Feature | How It's Used |
|---------|---------------|
| **ipython tool** | Executes Python to generate, randomize, and save quiz data |
| **Chunked output** | Breaks large JSON into chunks to prevent truncation |
| **Multi-step execution** | Runs separate tool calls for each chunk extraction |
| **Deterministic randomization** | Uses `time.time_ns()` seed for reproducible shuffling |

### Generator Output Features

- ✅ **Transcript-faithful** - Only uses content from your source material
- ✅ **No truncation** - Chunking ensures complete JSON output (Kimi)
- ✅ **Randomization** - Shuffles answers to prevent pattern recognition
- ✅ **Explanations first** - AI generates reasoning before answers (better quality)
- ✅ **Citation required** - References specific sections of your transcript
- ✅ **15-25 questions** - Mix of regular + case study questions

## 💡 Pro Tips

### Study Workflow
1. **Watch a lecture** or **read documentation**
2. **Copy the transcript** and use the "Generate from Transcript" feature
3. **Let the AI generate** the quiz JSON
4. **Load the generated quiz** into the player
5. **Take the quiz** - wrong answers show explanations
6. **Export results** and ask an AI for help on weak areas

### Resume Anywhere
- Copy your save state (JSON) from the "Save" button
- Paste it on any device to resume progress
- Save states include answers, current question, and quiz data

### Keyboard Shortcuts

| Key | Action |
|-----|--------|
| **1-9, 0** | Select option A-J |
| **Enter / Space** | Submit answer or continue |
| **← / →** or **, / .** | Previous / Next question |
| **Home** | Go to first question |
| **End** | Go to last question / back to results |
| **S** | Save progress |
| **C** | Toggle case study panel |
| **Esc** | Clear drag-drop selection |

**Input Screen:**
| Key | Action |
|-----|--------|
| **Ctrl+Enter** | Load quiz |
| **R** | Resume quiz (if available) |
| **L** | Load example |

**Results Screen:**
| Key | Action |
|-----|--------|
| **Enter / Space** | Restart quiz |
| **N** | Load new quiz |
| **A** | Export for AI discussion |
| **J** | Export JSON |

⚠️ **Note:** If keyboard shortcuts don't work, check for browser extensions like **Vimium**, **Vim Vixen**, or other Vim-style navigation tools that may intercept number keys. Disable the extension on this page or use the mouse instead.

## 🔧 Browser Compatibility

- ✅ Chrome / Edge (recommended)
- ✅ Firefox
- ✅ Safari
- ✅ Mobile browsers (iOS Safari, Chrome Mobile)

## 📝 License

MIT License - feel free to use for personal or commercial projects.

## 🎯 Perfect For

- Certification exam prep (Azure, AWS, Google Cloud, etc.)
- Course material review
- Corporate training
- Self-directed learning

---

**No installation required. No tracking. No ads. Just learning.**

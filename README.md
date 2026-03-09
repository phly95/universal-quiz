# Universal Quiz Player

A powerful, browser-based quiz player with support for AI-generated quizzes from transcripts. No backend required—just open the HTML file and start learning.

![Quiz Player Preview](https://img.shields.io/badge/Platform-Web-blue) ![License](https://img.shields.io/badge/License-MIT-green)

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

### 📱 Modern UI
- Clean, responsive design (works on mobile & desktop)
- Smooth animations and transitions
- Progress bar and question navigation
- Keyboard-friendly controls

## 🚀 Quick Start

1. **Open `quiz.html`** in any modern browser
2. **Paste quiz JSON** into the text area (see format below)
3. **Click "Load Quiz"**
4. **Start learning!**

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

Use the included `quiz_generator_prompt.txt` with AI assistants (Claude, ChatGPT, etc.) to automatically generate quizzes from:
- **Video transcripts** (YouTube, lectures, tutorials)
- **Documentation** (technical docs, textbooks)
- **Meeting recordings** (training sessions, presentations)

### How to Use the Generator Prompt

1. **Copy** the contents of `quiz_generator_prompt.txt`
2. **Paste** into your AI assistant
3. **Add your transcript** at the bottom (replace the empty content block)
4. **The AI will**:
   - Generate 15-25 questions from your content
   - Include multiple question types
   - Add detailed explanations with citations
   - Randomize answer order to prevent memorization
   - Output valid JSON ready for the quiz player

### Generator Features

- ✅ **Transcript-faithful** - Only uses content from your source material
- ✅ **Chunking support** - Handles long outputs without truncation
- ✅ **Randomization** - Shuffles answers to prevent pattern recognition
- ✅ **Explanations first** - AI generates reasoning before answers (better quality)
- ✅ **Citation required** - References specific sections of your transcript

## 💡 Pro Tips

### Study Workflow
1. **Watch a lecture** or **read documentation**
2. **Copy the transcript** into the generator prompt
3. **Load the generated quiz** into the player
4. **Take the quiz** - wrong answers show explanations
5. **Export results** and ask an AI tutor for help on weak areas

### Resume Anywhere
- Copy your save state (JSON) from the "Save" button
- Paste it on any device to resume progress
- Save states include answers, current question, and quiz data

### Keyboard Shortcuts
- **1-9** - Select answer option
- **Space/Enter** - Submit or continue
- **Arrow keys** - Navigate between questions

## 🔧 Browser Compatibility

- ✅ Chrome / Edge (recommended)
- ✅ Firefox
- ✅ Safari
- ✅ Mobile browsers (iOS Safari, Chrome Mobile)

## 📝 License

MIT License - feel free to use for personal or commercial projects.

## 🙏 Credits

Created for efficient learning and knowledge retention. Perfect for:
- Certification exam prep (Azure, AWS, Google Cloud, etc.)
- Course material review
- Corporate training
- Self-directed learning

---

**No installation required. No tracking. No ads. Just learning.**

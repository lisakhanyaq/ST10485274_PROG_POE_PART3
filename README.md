# Cybersecurity Awareness Chatbot - Parts 1, 2 & 3

Student: Lisakhanya Qwaka  
Module:PROG6221 - Programming 2A  
Date: June 2026

---

## Project Overview

A comprehensive WPF-based cybersecurity awareness chatbot that evolves through three parts:

- Part 1: Console chatbot with voice greeting, ASCII art, and keyword-based responses
- Part 2: WPF GUI with sentiment detection, memory, and conversation flow
- Part 3: Advanced features including task management, mini-game quiz, NLP intent detection, and activity logging

---

## Key Features

### Part 1 & 2 (Maintained)
Voice greeting playback (greeting.wav)  
ASCII art logo display  
User name personalization  
Sentiment detection (worried, curious, frustrated, happy)  
Memory system (remembers name and favourite topic)  
Conversation follow-up ("tell me more" continues topics)  
15+ cybersecurity keywords with random responses  

### Part 3 (New)
**Task Assistant:** Add, view, complete, delete tasks with reminders (JSON storage)  
**Quiz Mini-Game:** 15+ cybersecurity questions with immediate feedback  
**NLP Intent Detection:** Understands varied phrasings for tasks, quizzes, logs  
**Activity Log:** Timestamped record of all significant actions  

---

## File Structure

```
CybersecurityChatbot/
├── MainWindow.xaml              (WPF UI layout)
├── MainWindow.xaml.cs           (UI event handlers)
├── ChatBot.cs                   (Core logic with NLP)
├── KeywordResponder.cs          (Cybersecurity keywords)
├── SentimentDetector.cs         (Emotion detection)
├── MemoryStore.cs               (User memory)
├── TaskManager.cs               (Task business logic)
├── TaskStorageHelper.cs         (JSON file I/O)
├── CyberTask.cs                 (Task model)
├── QuizManager.cs               (Quiz logic)
├── QuizQuestion.cs              (Question model)
├── ActivityLogger.cs            (Action logging)
├── AudioPlayer.cs               (Voice greeting)
├── greeting.wav                 (Audio file - auto-loads on startup)
├── tasks.json                   (Auto-created on first task)
├── CybersecurityChatbot.csproj  (Project config)
├── README.md                    (This file)
└── .github/workflows/
    └── dotnet.yml               (CI/CD pipeline)
```

---

## How to Use the Chatbot

### Basic Chat
- Type your **name** at startup
- Ask about **cybersecurity topics:** "Tell me about passwords", "How do I prevent phishing?"
- Type **'tell me more'** to get another tip on the same topic
- Type **'help'** to see all available topics

### Task Assistant
```
User: "Add a task to enable two-factor authentication"
Bot: "Task added. Would you like a reminder?"
User: "Yes, remind me in 5 days"
Bot: "Reminder set!"
```
- View tasks in the **Task Panel** (added to GUI)
- Mark tasks complete or delete them
- Tasks are **automatically saved to tasks.json**

### Quiz Mini-Game
```
User: "Start quiz"
Bot: [Shows one question at a time]
User: [Answer A, B, C, D, or True/False]
Bot: [Immediate feedback + correct explanation]
[After 15 questions: Shows final score]
```

### Activity Log
```
User: "Show activity log"
Bot: [Displays last 10 actions with timestamps]
[If more than 10 entries exist: "Type 'show more'"]
```

### NLP Examples
The bot understands varied phrasings:
- "Add a task to review privacy settings" ✅
- "Enable two-factor authentication on my accounts" ✅
- "Create a task for malware scanning" ✅
- "Remind me to update my password" ✅
- "Test my cybersecurity knowledge" ✅
- "What have you done for me?" ✅

---

## Task Storage (JSON Format)

Tasks are stored in `tasks.json` in the output directory:

```json
[
  {
    "Id": 1,
    "Title": "Enable two-factor authentication",
    "Description": "Set up 2FA on all important accounts",
    "Reminder": "Remind me in 5 days",
    "IsComplete": false,
    "CreatedAt": "2026-06-10 14:32"
  },
  {
    "Id": 2,
    "Title": "Review privacy settings",
    "Description": "Review account privacy settings",
    "Reminder": "",
    "IsComplete": true,
    "CreatedAt": "2026-06-10 14:45"
  }
]
```

**Note:** The file is **auto-created** when you add the first task. No manual setup needed.

---

## Quiz Questions Coverage

The quiz includes 15+ questions across these topics:

| Topic | Questions | Type |
|-------|-----------|------|
| Phishing | 3 | Multiple choice, T/F |
| Password Safety | 3 | Multiple choice, T/F |
| Safe Browsing | 2 | Multiple choice, T/F |
| Two-Factor Authentication | 2 | Multiple choice, T/F |
| Social Engineering | 2 | Multiple choice, T/F |
| Malware & Ransomware | 2 | Multiple choice, T/F |
| Privacy & Data Protection | 2 | Multiple choice, T/F |
| Backup & Disaster Recovery | 1 | Multiple choice |

---

## GitHub Workflow

### Commits (6 required)
1. `feat: Initial Part 1 & 2 project setup`
2. `feat: Add JSON task storage and TaskStorageHelper`
3. `feat: Add task assistant panel with CRUD operations`
4. `feat: Add cybersecurity quiz with 15+ questions`
5. `feat: Add activity log and NLP intent detection`
6. `docs: Final integration test, README, and releases`

### Releases (3 required)

**v3.0** - Task Assistant & JSON Storage
- Full task CRUD operations
- JSON persistence working

**v3.1** - Quiz & Activity Log
- 15+ quiz questions with feedback
- Complete activity logging

**v3.2** - Final Integration (Ready for Submission)
- All features working seamlessly
- Parts 1, 2, 3 fully integrated
- Professional polish applied

### Push to GitHub
```bash
git add .
git commit -m "feat: [Your message]"
git push origin main
```

To create a release:
1. Go to your repo on GitHub
2. Click **Releases** on the right sidebar
3. Click **Draft a new release**
4. Enter tag: `v3.0`, write notes, click **Publish**

---

---


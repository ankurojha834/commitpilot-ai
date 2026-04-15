# 🧙 commitpilot-ai

> An AI-powered CLI that analyzes your staged git diff and generates smart, meaningful commit messages — so you never write a lazy `fix stuff` commit again.

[![npm version](https://img.shields.io/npm/v/commit-sage)](https://www.npmjs.com/package/commit-sage)
[![npm downloads](https://img.shields.io/npm/dm/commit-sage)](https://www.npmjs.com/package/commit-sage)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Node.js](https://img.shields.io/badge/node-%3E%3D18.0.0-brightgreen)](https://nodejs.org)

---

## ✨ What Makes This Different?

| Feature | Other tools | commit-sage |
|---|---|---|
| Works 100% offline (FREE) | ❌ | ✅ via Ollama |
| Hinglish / Hindi commit mode | ❌ | ✅ |
| Mood personalities | ❌ | ✅ Professional / Savage / Poetic |
| Git Personality Score | ❌ | ✅ |
| Team Report with Awards | ❌ | ✅ |
| Commit Streak Tracker | ❌ | ✅ |
| Regenerate suggestions | ❌ | ✅ |

---

## 📦 Installation

```bash
npm install -g commitpilot-ai
```

**Requirements:** Node.js >= 18.0.0

---

## 🚀 Quick Start

### Option A — Free & Offline (Ollama)
```bash
# 1. Install Ollama from https://ollama.com
ollama pull llama3

# 2. Set Ollama as default provider
commit-sage config --provider ollama

# 3. Stage your changes and run
git add .
commit-sage
```

### Option B — OpenAI
```bash
# 1. Set your OpenAI API key
commit-sage config --key sk-your-openai-key

# 2. Stage your changes and run
git add .
commit-sage
```

---

## 🎭 Mood Examples

### 💼 Professional (default)
```
feat(auth): implement JWT token refresh mechanism
fix(api): handle null response from payment gateway
docs: update installation steps in README
```

### 💀 Savage
```
fix: undid what someone broke at 2am again
chore: deleted 500 lines of code someone called "architecture"
feat: added a feature nobody asked for but PM insisted
```

### 🌸 Poetic
```
feat: and thus the user could finally login, as dawn breaks
fix: slayed the null pointer dragon haunting production
refactor: untangled the web of chaos into elegant simplicity
```

---

## 🌍 Language Modes

### English (default)
```
feat(auth): add Google OAuth login support
```

### Hinglish 🇮🇳
```
feat(auth): login ka jugaad laga diya, ab kaam karega
fix: woh wala bug thik kiya jo pata nahi kahan se aaya tha
chore: purana code saaf kar diya, bahut gandagi thi yaar
```

### Hindi
```
feat: उपयोगकर्ता लॉगिन सुविधा जोड़ी
fix: प्रमाणीकरण त्रुटि को ठीक किया
```

---

## 🎯 Git Personality Score

Analyze your commit history and get a personality score with team reports and fun awards.

```bash
commitpilot-ai score           # your personal score
commitpilot-ai score --team    # full team report with awards
commitpilot-ai streak          # your commit streak
```

### Personal Score
```
  🧙 commitpilot-ai — Personality Report
  ══════════════════════════════════════
  💀 The Savage
  "idk why this works" energy

  Commit Score:  ████████░░ 76/100

  Total commits:    142
  Conventional:     98  (69%)
  Lazy commits:     12
  Hotfixes:         3 🔥
  Late night:       18 🦉
  Weekend commits:  7 😵
  Current streak:   5 days 🔥

  😬 Your "best" commits:
     • "fix"
     • "misc changes"
     • "idk"
```

### Team Report
```
  🧙 commitpilot-ai — Team Report
  ══════════════════════════════════════════════════

  Alice Johnson   💼 The Professional
  ██████████ 94/100  streak: 12d 🔥
  total: 134  clean: 128  lazy: 2  3am: 1

  Bob Smith       💀 The Savage
  ████████░░ 71/100  streak: 3d 🔥
  total: 89  clean: 52  lazy: 21  3am: 14🦉

  ══════════════════════════════════════════════════
  🏅 Weekly Awards

  🏆  "What does this even mean?" Award
      Winner: Bob Smith
      21 lazy commits like "fix", "update", "misc"

  🦉  "Who Needs Sleep?" Award
      Winner: Bob Smith
      14 commits after 10pm. Please rest!

  🎖️  "Clean Code Hero" Award
      Winner: Alice Johnson
      128 clean conventional commits. Respect!
```

### Streak Tracker
```
  🔥commitpilot-ai — Streak Report
  ─────────────────────────────
  5-day streak  🔥🔥🔥🔥🔥

  Today's commits:  3
  Active days:      47
  Total commits:    142

  ✅  Committed today! Streak is safe!

  😅 Your most "creative" commit ever:
     "idk why this works but it does"
```

---

## 🏅 Personality Types

| Type | How you earn it |
|---|---|
| 💼 The Professional | 80%+ conventional commits |
| 💀 The Savage | "idk why this works" energy |
| 🦉 Night Owl | 10+ commits after 10pm |
| 🚒 Firefighter | 5+ hotfix/production commits |
| 😴 The Lazy Dev | 50%+ lazy commits like "fix", "update" |
| 😵 No Life Dev | 5+ commits on weekends |
| 📚 The Learner | Improving, 50%+ conventional |
| 🎲 The Chaotic | Unpredictable but creative |

---

## 🛠️ All Commands & Flags

```bash
# Generate commit message (default)
commitpilot-ai
commitpilot-ai generate

# With flags
commitpilot-ai --mood savage           # savage tone
commitpilot-ai --mood poetic           # poetic tone
commitpilot-ai --mood professional     # clean and formal (default)
commitpilot-ai --lang hinglish         # Hinglish language
commitpilot-ai --lang hindi            # Hindi language
commitpilot-ai --lang english          # English (default)
commitpilot-ai --type feat             # force a specific commit type
commitpilot-ai --count 5               # get 5 suggestions instead of 3
commitpilot-ai --provider ollama       # use Ollama for this run
commitpilot-ai --provider openai       # use OpenAI for this run

# Mix and match
commit-sage --mood savage --lang hinglish --count 5

# Personality & streaks
commitpilot-ai score                   # personal personality report
commitpilot-ai score --team            # full team report with awards
commitpilot-ai score --single          # force single-user mode
commitpilot-ai streak                  # commit streak tracker

# Configuration
commitpilot-ai config --key sk-...         # set OpenAI API key
commitpilot-ai config --provider ollama    # set default provider
commitpilot-ai config --provider openai    # set default provider
commitpilot-ai config --mood savage        # set default mood
commitpilot-ai config --lang hinglish      # set default language
commitpilot-ai config --show               # view current config
```

---

## 💻 Ollama Setup (100% Free & Offline)

```bash
# Step 1 — Install Ollama
# Visit https://ollama.com and download for your OS
# Or on Linux/macOS:
curl https://ollama.ai/install.sh | sh

# Step 2 — Pull a model
ollama pull llama3        # recommended (best quality)
ollama pull mistral       # lighter, faster option
ollama pull phi3          # smallest, good for low-end machines

# Step 3 — Set as default
commitpilot-ai config --provider ollama

# Done! No API key needed, works completely offline.
```

---

## 🔑 OpenAI Setup

```bash
# Option 1 — via CLI
commitpilot-ai config --key sk-your-openai-api-key

# Option 2 — via environment variable
export OPENAI_API_KEY=sk-your-openai-api-key
```

Get your API key at [platform.openai.com](https://platform.openai.com).

> commitpilot-ai uses `gpt-4o-mini` by default — fast and very affordable.

---

## ⚙️ How It Works

```
git add .                    # Stage your changes
     ↓
commitpilot-ai                 # Run the CLI
     ↓
git diff --cached            # Reads your staged diff
     ↓
Sends to AI (OpenAI/Ollama)  # Analyzes the changes
     ↓
3 commit message suggestions # You pick one
     ↓
git commit -m "..."          # Commits automatically
```

---

## 🤝 Contributing

Contributions are welcome! Here's how to get started:

```bash
# 1. Fork the repo on GitHub
# 2. Clone your fork
git clone https://github.com/ankurojha834/commit-sage

# 3. Install dependencies
npm install

# 4. Test locally
npm link
commitpilot-ai --version

# 5. Create a branch
git checkout -b feat/your-feature

# 6. Make your changes, then submit a PR
```

Please open an issue before starting major changes so we can discuss the approach.

---

## 📋 Changelog

### v2.0.0
- Added Git Personality Score (`commitpilot-ai score`)
- Added Team Report with Awards (`commitpilot-ai score --team`)
- Added Commit Streak Tracker (`commitpilot-ai streak`)
- Added Ollama support (free, offline AI)
- Added Hinglish and Hindi language modes
- Added mood personalities: Professional, Savage, Poetic
- Added Regenerate option in picker

### v1.0.0
- Initial release
- OpenAI-powered commit message generation
- Interactive suggestion picker

---

## 📄 License

MIT © [Ankur Ojha](https://github.com/ankurojha834)

---

## ⭐ Support

If you find this useful, please give it a star on GitHub! It helps others discover the project.

> Built with ❤️ for developers who care about clean git history.

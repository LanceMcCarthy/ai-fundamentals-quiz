# 🧠 AI Fundamentals Quiz

An interactive, self-contained quiz covering core AI concepts — no build tools, no dependencies, no server required. Just open `index.html` in a browser (or visit the live site) and start learning.

**🌐 Live site:** https://lancemccarthy.github.io/ai-fundamentals-quiz/

---

## 📚 Topics Covered

The quiz is divided into four sections (50 questions total):

| # | Section | Topics |
|---|---------|--------|
| 1 | ⚡ **Prompt Engineering** | LLM fundamentals, tokens, context windows, prompting techniques & model parameters |
| 2 | 🔍 **RAG + Data Hygiene** | Retrieval-Augmented Generation, embeddings, search strategies & data quality |
| 3 | 🤖 **Agentic Patterns + Tools / MCPs** | Agent characteristics, ReAct loops, multi-agent collaboration & tool use |
| 4 | 🛡️ **Evaluation + Guardrails** | Responsible AI, hallucination types, prompt injection & EDD |

Each question includes an instant explanation after answering, so the quiz doubles as a learning tool.

---

## 🚀 Running Locally

No installation needed. Clone the repo and open the file:

```bash
git clone https://github.com/LanceMcCarthy/ai-fundamentals-quiz.git
cd ai-fundamentals-quiz
# Then open index.html in your browser:
start index.html          # Windows
open index.html           # macOS
xdg-open index.html       # Linux
```

---

## 🛠️ How It Works

Everything lives in a single `index.html` file:

- **React 18** (loaded via CDN — no `npm install` needed)
- **Babel Standalone** (transpiles JSX in the browser at runtime)
- **Google Fonts** (Outfit typeface, loaded via CDN)
- All quiz logic, styles, and question data are inline in the file

The question data is a plain JavaScript array called `QUESTIONS` near the top of the `<script>` block. Each entry looks like this:

```js
{
  section: 1,                          // Which section (1–4) this question belongs to
  q: "Your question text here?",       // The question
  options: ["A", "B", "C", "D"],       // Answer choices (always 4)
  correct: 2,                          // Zero-based index of the correct answer
  explanation: "Why this is correct.", // Shown after the user answers
}
```

---

## ✏️ Contributing Questions

Want to add, fix, or improve a question? Great — contributions are welcome!

### Adding a new question

1. **Fork** the repo and create a branch: `git checkout -b add-question-about-xyz`
2. Open `index.html` in any text editor
3. Find the `const QUESTIONS = [` array (around line 40)
4. Add your new question object inside the array, in the correct section block (look for the `// ===== SECTION X =====` comments):

```js
{
  section: 2,
  q: "What does 'semantic search' retrieve documents based on?",
  options: [
    "Exact keyword matches",
    "Document file size",
    "Meaning and context using vector similarity",
    "Alphabetical order of words"
  ],
  correct: 2,
  explanation: "Semantic search uses vector embeddings to find documents that are conceptually similar to the query, even if they don't share the same keywords. This is the foundation of most RAG retrieval systems."
}
```

5. Test it locally by opening `index.html` in a browser
6. Open a **Pull Request** with a short description of the question and why it's a good addition

### Editing an existing question or explanation

Find the question by searching (`Ctrl+F`) for a few words from it, then edit the `q`, `options`, `correct`, or `explanation` fields directly.

> **Tip:** The `correct` field is a **zero-based index** into the `options` array. So if the right answer is the third option, `correct` should be `2`.

### Guidelines for new questions

- **Factual and unambiguous** — there should be one clearly correct answer
- **Explanation is required** — briefly explain *why* the correct answer is right (2–4 sentences)
- **Four answer choices** — keep the `options` array at exactly 4 items
- **Appropriate section** — place the question in the section whose topic it best fits
- **No duplicates** — search the file to make sure a similar question doesn't already exist

---

## 🐛 Reporting Issues

Found a factual error, a typo, or a broken answer? Please [open an issue](https://github.com/LanceMcCarthy/ai-fundamentals-quiz/issues) with:

- The question text
- What's wrong
- A suggested correction (if you have one)

---

## 📄 License

This project is open source. Feel free to fork it, adapt it, or use it for your own team training.

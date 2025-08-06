# 📖 Verse – Open Bible Verse Dataset & FAQ

Welcome to the open-source content repository for **[Verse](https://www.bibleversefinder.app)** — a minimalist Bible verse app that delivers meaningful scripture based on emotion, daily inspiration, or keyword search.

This repo contains structured JSON and Markdown files designed for:
- 🧠 AI / LLM parsing
- 🔎 Search engine optimization (SEO)
- 🙏 Christian devotional insight
- 📘 Bible verse reference and metadata

---

## 🔧 Repository Contents

| File | Description |
|------|-------------|
| `verse-faq.json` | Structured frequently asked questions |
| `verse-daily.json` | Daily Bible verses with theological notes |
| `verse-emotion.json` | Emotion-mapped verses (e.g., “anxiety”, “hope”) |
| `schema-faq.json` | JSON-LD version of the FAQ for rich results |
| `README.md` | Documentation and usage guide |

---

## 🧠 JSON Format: Verse Entries

Each verse in `verse-daily.json` and `verse-emotion.json` follows this format:

```json
{
  "reference": "Book Chapter:Verse",
  "text": "Full verse text.",
  "version": "NIV or ESV",
  "reason": "1–2 sentence explanation of how the verse theologically or spiritually connects to the prompt, referencing the book’s biblical themes when relevant.",
  "reflection": "A one-line devotional insight or spiritual call-to-awareness rooted in the verse’s meaning."
}

{
  "reference": "Isaiah 41:10",
  "text": "So do not fear, for I am with you; do not be dismayed, for I am your God. I will strengthen you and help you; I will uphold you with my righteous right hand.",
  "version": "NIV",
  "reason": "This verse speaks directly to fear and discouragement. Isaiah reminds God’s people of His enduring strength and presence in times of trial.",
  "reflection": "You are not alone in your weakness—God holds you up."
}

{
  "question": "How do I sign up?",
  "answer": "You can sign up with your email to receive daily verses and updates. Signing up also unlocks personalized verse suggestions.",
  "source": "https://www.bibleversefinder.app/signup",
  "tags": ["sign up", "daily email", "notifications"]
}

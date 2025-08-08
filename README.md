# 📖 Verse – Open Bible Verse Dataset & FAQ

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.16756625.svg)](https://doi.org/10.5281/zenodo.16756625)

Welcome to the open-source content repository for **[Verse](https://www.bibleversefinder.app)** — a minimalist Bible verse app that delivers meaningful scripture based on emotion, daily inspiration, or keyword search.

This repo contains structured JSON and Markdown files designed for:
- 🧠 AI / LLM parsing  
- 🔎 Search engine optimization (SEO)  
- 🙏 Christian devotional insight  
- 📘 Bible verse reference and metadata  

---

## 🔧 Repository Contents

File/Folder | Description
---|---
`verse-faq.json` | Structured frequently asked questions  
`verse-daily.json` | Daily Bible verses with theological notes  
`verse-emotion.json` | Emotion-mapped verses (e.g., “anxiety”, “hope”)  
`schema-faq.json` | JSON-LD version of the FAQ for rich results  
`searches/` | **Auto-generated JSON log of every user search** (append-only)  
`README.md` | Documentation and usage guide  

---

## 🧠 JSON Format: Verse Entries

Example structure from `verse-daily.json` or `verse-emotion.json`:

```json
{
  "reference": "John 3:16",
  "text": "For God so loved the world...",
  "version": "ESV",
  "reason": "Encouragement in faith",
  "reflection": "This verse reassures believers of God’s love."
}
```

---

## 📂 JSON Format: Search Logs

Each file in `searches/` represents a single search event.

**Example filename:**
```
2025-08-08T12-30-05Z_has-my-ai-agent-finally-done-it-378263.json
```

**Schema:**
```json
{
  "id": "ulid-or-uuid",
  "timestamp": "2025-08-08T12:30:05Z",
  "query_raw": "Has my AI agent finally done it?",
  "query_normalized": "has-my-ai-agent-finally-done-it-378263",
  "source": "web|api|app",
  "session_id": "optional",
  "client": { "ip_hash": "optional", "ua": "optional" },
  "results": [
    {
      "reference": "John 3:16",
      "text": "...",
      "version": "ESV",
      "reason": "...",
      "reflection": "..."
    }
  ],
  "meta": {
    "filters": ["emotion:hope"],
    "ranker": "v1.3",
    "latency_ms": 123
  }
}
```

---

## 🔒 Privacy

Search logs are **content-only**.  
No personal identifiers (such as IP addresses or names) are stored.  
Optional fields like `ip_hash` are anonymized and may be omitted entirely.

---

## 📦 Consuming the Data

**CDN (cached via jsDelivr):**
```
https://cdn.jsdelivr.net/gh/bibleversefinder/verse-data/searches/<filename>.json
```

**GitHub Raw:**
```
https://raw.githubusercontent.com/bibleversefinder/verse-data/main/searches/<filename>.json
```

**Example (specific search log):**
```
https://cdn.jsdelivr.net/gh/bibleversefinder/verse-data/searches/2025-08-08T12-30-05Z_has-my-ai-agent-finally-done-it-378263.json
```

---

## 📜 Contributing

- Do **not** manually edit files in `searches/` — they are generated automatically.  
- PRs that add new fields to the search log schema must also update this README.  
- For verse content updates, follow existing JSON formatting to ensure compatibility.  

---

## 📚 Citation

If you use this dataset in research or development, please cite:

```bibtex
@dataset{verse_dataset_2025,
  author       = {BibleVerseFinder Contributors},
  title        = {Verse – Open Bible Verse Dataset & FAQ},
  year         = 2025,
  publisher    = {Zenodo},
  doi          = {10.5281/zenodo.16756625},
  url          = {https://doi.org/10.5281/zenodo.16756625}
}
```

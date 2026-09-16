<img width="1866" height="972" alt="image" src="https://github.com/user-attachments/assets/4563b464-3869-475e-b8b8-a2eb730efc2d" />

# JASS Mizo Corpus Studio

**Version:** 2.1  
**Status:** Stable working release  
**Purpose:** Offline exploration and linguistic research using the 4-million-record Mizo language corpus.

JASS Mizo Corpus Studio is a lightweight PySide6 desktop application designed specifically for the SQLite database:

`JASS_Mizo_Corpus_4M.db`

It provides fast local searching, corpus context, KWIC/concordance exploration, frequency checking, bookmarks, and export tools without requiring a GPU or heavy AI/ML frameworks.

---

## Features

### 🔎 Search

- Fast offline search through the SQLite/FTS5 corpus index
- **Exact phrase**
- **All words**
- **Any word**
- **Prefix**
- **Contains**
- Search history
- Keyboard shortcut: `Enter` to search

### 📖 Context Explorer

When a result is selected, the application displays the selected corpus record together with nearby records.

This makes it possible to examine how a word or expression is used in surrounding Mizo text.

### 🔍 KWIC / Concordance

The **KWIC** tab shows occurrences of the searched expression with surrounding text.

This is useful for:

- vocabulary research
- phrase research
- usage examples
- language learning
- corpus-based writing
- identifying recurring expressions

### 🔤 Frequency

The Frequency function checks how often an exact search token occurs in the corpus.

The result is reported as a corpus-record frequency, rather than pretending to be a complete linguistic word-frequency analysis.

### ★ Bookmarks

Useful corpus examples can be saved as bookmarks.

Bookmarks are stored separately from the corpus database in the user's profile:

`~/.jass_mizo_corpus_bookmarks.json`

The corpus database itself is opened **read-only**.

### 🎲 Random Record

Explore random corpus material without entering a search term.

### 📋 Copy

Copy the selected corpus sentence directly to the clipboard.

### ⬇ Export

Export the current search results as:

- TXT
- CSV

Bookmarks can also be exported.

### 🌓 Light / Dark Mode

The interface supports:

- Light Mode
- Dark Mode

Shortcut:

`Ctrl+D`

### ℹ Database Information

The Database Info window displays database objects, row counts where applicable, database size, and available metadata.

---

## Database

The main database is:

`JASS_Mizo_Corpus_4M.db`

Expected corpus size:

**4,000,000 records**

The application uses SQLite and FTS5 for local search.

The database is opened using SQLite's query-only mode, so normal application operations do not modify the corpus.

---

## Source Corpus

The database was created from:

`mizo_language_corpus_4m.txt`

The source corpus is approximately 396 MB in text form, while the SQLite database is approximately 700 MB depending on SQLite indexes and metadata.

The original text corpus can be retained as an archival/source copy but is not required for normal operation of the application.

---

## Recommended Folder Structure

A clean installation can be organized as:

```text
Mizo_Language_Tools\
│
├── 05_Mizo_Corpus\
│   ├── JASS_Mizo_Corpus_4M.db
│   └── mizo_language_corpus_4m.txt
│
└── JASS_Mizo_Corpus_Studio\
    ├── jass_mizo_corpus_studio_v2_1_darkmode_fixed.py
    └── README.md
```

For everyday use, keeping the database and Python application in the same directory is also supported:

```text
Mizo_Language_Tools\
├── JASS_Mizo_Corpus_4M.db
├── jass_mizo_corpus_studio_v2_1_darkmode_fixed.py
└── README.md
```

The application automatically looks for `JASS_Mizo_Corpus_4M.db` in its current directory and in the user's Downloads directory. Otherwise use **Open Database**.

---

## Requirements

- Windows 10/11
- Python 3.10 or newer
- PySide6

Install PySide6 if necessary:

```powershell
py -m pip install PySide6
```

No PyTorch is required.

No GPU is required.

No internet connection is required after the application and database have been obtained.

---

## Running

From the application directory:

```powershell
py jass_mizo_corpus_studio_v2_1_darkmode_fixed.py
```

Or open the Python file with your preferred Python environment.

---

## Useful Shortcuts

| Shortcut | Action |
|---|---|
| `Ctrl+O` | Open Database |
| `Ctrl+D` | Toggle Dark Mode |
| `Ctrl+Shift+R` | Random Record |
| `Ctrl+B` | Open Bookmarks |
| `Enter` | Search |

---

## Suggested Research Workflow

A useful workflow for Mizo language research is:

1. Search for a Mizo word or phrase.
2. Examine the result list.
3. Select an interesting example.
4. Read the **Context** tab.
5. Check the **KWIC** tab.
6. Use **Frequency** to examine occurrence frequency.
7. Bookmark particularly useful examples.
8. Export selected results for later research.

---

## Relationship to the English–Mizo Dictionary

JASS Mizo Corpus Studio is a **corpus research tool**, not a replacement for the English–Mizo Dictionary application.

The two tools can eventually complement each other:

```text
English–Mizo Dictionary
        │
        │ word / definition
        ▼
Mizo Corpus
        │
        │ real usage examples
        ▼
Context + KWIC + Frequency
```

A future integration could allow a user to right-click a word in the corpus and send it directly to the English–Mizo Dictionary.

---

## Data Safety

The corpus database is treated as read-only by the application.

Recommended practice:

- Keep the original `mizo_language_corpus_4m.txt` as an archival backup.
- Keep a backup copy of `JASS_Mizo_Corpus_4M.db`.
- Do not edit the SQLite database manually unless you intend to rebuild the corpus indexes.
- Bookmarks are stored separately.

If SQLite creates temporary `-wal` or `-shm` files while the database is in use, close the application before moving or backing up the database.

---

## Version History

### v2.1 — Dark Mode Fixed

- Fixed Dark Mode toggle behavior.
- Added `Ctrl+D`.
- Added proper checkable theme action.
- Preserved the v2 Corpus Intelligence interface.

### v2.0 — Concordance & Usage Explorer

- KWIC view
- Context Explorer
- Frequency
- Bookmarks
- Search history
- Export
- Multiple search modes
- Improved corpus information display
- Dark/Light theme

### v1.0 — Corpus Studio Foundation

- SQLite database loading
- FTS5 search
- Result pagination
- Context display
- Random record
- Database information
- Basic Light/Dark interface

---

## Project Name

**JASS Mizo Corpus Studio**

Suggested repository name:

`JASS-Mizo-Corpus-Studio`

Suggested description:

> Offline PySide6 corpus explorer for a 4-million-record Mizo language corpus, with FTS5 search, KWIC concordance, context exploration, frequency, bookmarks and export.

---

## License / Data

The application code and the corpus data should be treated separately.

The copyright, licensing, and redistribution terms of the underlying corpus must be checked before publishing or redistributing the database or original corpus text.


# 📝 How to Add New Documents

## No Coding Required!

Just edit the `docs.json` file to add new documents. The page updates automatically.

---

## Step 1: Open `docs.json`

On GitHub:
1. Click on `docs.json`
2. Click the ✏️ pencil icon (Edit)

---

## Step 2: Find the Right Section

The file has these sections:
- `architecture` - Technical docs
- `agents` - Pantheon agent prompts
- `lenses` - The &Eye transformation lenses
- `sectors` - Industry knowledge packs
- `design` - Color system & visual references
- `presentations` - Pitch decks & slides
- `resources` - General materials

---

## Step 3: Add Your Document

Copy this template and paste it in the `docs` array of your chosen section:

```json
{
  "file": "FOLDER/YOUR_FILE_NAME.md",
  "name": "Display Name",
  "description": "Short description of the document.",
  "category": "Category Label",
  "icon": "📄",
  "size": "~10 KB",
  "featured": false,
  "dateAdded": "2025-12-17"
}
```

### Example: Adding a new presentation

```json
{
  "file": "presentations/RootRise_UNIDO_Partnership_Deck.pdf",
  "name": "UNIDO Partnership Deck",
  "description": "Presentation for UNIDO Sustainable Food Systems partnership.",
  "category": "Partner",
  "icon": "🤝",
  "size": "2.5 MB",
  "featured": false,
  "dateAdded": "2025-12-18"
}
```

---

## Step 4: Update the Version

At the top of `docs.json`, update:

```json
"meta": {
  "version": "1.0.1",        ← Increase this number
  "lastUpdated": "2025-12-18", ← Update the date
  ...
}
```

---

## Step 5: Upload Your File

1. Put your actual file in the correct folder
2. Commit both changes (docs.json + your new file)

---

## 📌 Quick Reference

### Icons to Use
| Type | Icon |
|------|------|
| Document | 📄 |
| Presentation | 📊 |
| PDF | 📑 |
| Framework | 📐 |
| Guide | 📖 |
| Template | 📋 |
| Reference | 📚 |
| Partner | 🤝 |
| Strategy | 🎯 |
| Star/Featured | 🌟 |

### Make it Featured?
Set `"featured": true` to make the card span full width and highlight it.

---

## ⚠️ Common Mistakes

1. **Missing comma** - Each item needs a comma after it (except the last one)
2. **Wrong folder path** - Make sure the `file` path matches where you put the actual file
3. **Forgot to upload the file** - The JSON just links to files, you still need to upload them

---

That's it! The page will automatically show your new document with the correct count and version. 🎉

# 🤖 Agent Instructions - Family Vinyl Collection

This document provides instructions for AI agents working on the Family Vinyl Collection project.

## 🎯 Critical Workflow: Adding New Vinyl

**When adding a new vinyl record to the collection, you MUST:**

1. **Add the entry to `vinyl-collection.csv`**
   - Follow the existing CSV format exactly
   - Include all required fields: Artist, Album, Pressing, Format, Speed, Original Year, Pressing Year, Genre, Condition, Notes

2. **Check and update `wishlist.csv`**
   - **ALWAYS** check if the album exists on the wishlist
   - If found, **REMOVE it from the wishlist** (the user has acquired it)
   - This prevents duplicate entries and keeps the wishlist accurate

3. **Update `README.md`**
   - **ALWAYS** update the Collection Stats:
     - Increment "Total Entries" count
     - Increment "Total Discs" count (accounting for multi-LP sets: 2xLP = 2 discs, 3xLP = 3 discs, etc.)
   - Add the album to appropriate Collection Highlights section if it's notable
   - Update wishlist count if items were removed
   - Update "Newest Recording" year if applicable
   - Update genre list if a new genre is introduced

## 📁 Project Structure

- `vinyl-collection.csv` - Main collection database
- `wishlist.csv` - Albums the user wants to acquire
- `README.md` - Project documentation and stats
- `agents.md` - This file (agent instructions)

## 📋 Data Format Standards

### CSV Fields (both collection and wishlist)
- **Artist**: Performer name (use "Various Artists" for compilations)
- **Album**: Full album title
- **Pressing**: Label and pressing details
- **Format**: LP, 2xLP, 3xLP, 7xLP, etc.
- **Speed**: 33, 45, or 78 RPM
- **Original Year**: Year album was first released
- **Pressing Year**: Year of this specific pressing (use decade like "1960s" if unknown)
- **Genre**: Primary genre(s), comma-separated if multiple
- **Condition**: M, NM, VG+, VG, G+, or G
- **Notes**: Special features, track highlights, catalog numbers, etc.

### Condition Grading
- **M** (Mint): Perfect, unplayed or still sealed
- **NM** (Near Mint): Nearly perfect, minimal signs of handling
- **VG+** (Very Good Plus): Shows some play but sounds great
- **VG** (Very Good): Light surface noise, light scratches
- **G+** (Good Plus): Plays through with some noise
- **G** (Good): Significant wear but playable

## 🔄 Common Tasks

### Adding a New Album
1. Read current `vinyl-collection.csv` to understand format
2. Read `wishlist.csv` to check if album exists there
3. Add entry to `vinyl-collection.csv`
4. Remove from `wishlist.csv` if present
5. **Re-sort `vinyl-collection.csv` alphabetically by Artist** (case-insensitive)
6. Update `README.md` stats and highlights
7. Verify all counts are accurate

### Removing from Wishlist
- When user acquires an album, remove it from wishlist
- **Re-sort `wishlist.csv` alphabetically by Artist** (case-insensitive) after removal
- Update wishlist count in README
- Update top 5 most wanted if that item was listed

### Adding to Wishlist
- When adding new items to wishlist, add the entry
- **Re-sort `wishlist.csv` alphabetically by Artist** (case-insensitive) after addition
- Update wishlist count in README

### Updating Collection Stats
- Count total entries (excluding header row)
- Count total discs (sum of all LPs: 1xLP = 1, 2xLP = 2, etc.)
- Update genre list if new genre appears
- Update oldest/newest recording years if applicable

## ⚠️ Important Notes

- **Never skip updating the README** - stats must always be current
- **Always check the wishlist** when adding new vinyl - duplicates are bad
- **Preserve CSV formatting** - maintain exact field order and quoting style
- **Be precise with disc counts** - multi-LP sets must be counted correctly
- **Update wishlist count** whenever items are added or removed
- **Maintain alphabetical order** - Both CSV files are sorted alphabetically by Artist (case-insensitive). After adding, removing, or modifying entries, re-sort the affected CSV file(s) to maintain alphabetical order

## 🎵 Genre Conventions

Common genres used:
- Pop, Rock, Classical, Holiday, Metal, Soundtracks, Children's, Jazz, Spoken Word, Opera, Country, Soft Rock, Progressive Metal, Thrash Metal, Indie/Rock, Classical Crossover, Vocal/Pop, Pop/R&B, Soundtrack/R&B, Soundtrack/Gospel, Holiday/Vocal, Holiday/Pop, Holiday/Jazz, Classical/Holiday

## 📝 Example Workflow

```
User: "Add this new album to the collection"
Agent:
1. Reads vinyl-collection.csv
2. Reads wishlist.csv (checks if album is there)
3. Adds entry to vinyl-collection.csv
4. Removes from wishlist.csv if found
5. Re-sorts vinyl-collection.csv alphabetically by Artist
6. Re-sorts wishlist.csv alphabetically by Artist (if item was removed)
7. Updates README.md:
   - Increments Total Entries
   - Increments Total Discs
   - Adds to highlights if notable
   - Updates wishlist count if needed
8. Confirms completion
```

---

*Last updated: December 2025*


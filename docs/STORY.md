# The Story Behind This Project

Like most people, my Downloads folder had become a graveyard of forgotten files. Hundreds of documents with names like `Document (3).pdf`, `IMG_1234.jpg`, and `Screenshot 2024-01-15 at 3.45.22 PM.png` - files I downloaded once, maybe used, and never organized.

## What I Tried (And Why It Failed)

I tried the usual solutions:

- **Manual cleanup** - Spent hours sorting, got interrupted, never finished
- **Traditional organizer apps** - Sorted by file type, but couldn't understand that `receipts.pdf` was actually a Delta flight receipt that belonged in my Travel folder
- **AI assistants** - Could help if I uploaded files one by one, but couldn't access my actual Downloads folder or remember my personal folder structure

**The core problem?** Every tool treated organization as a one-size-fits-all problem. But my files aren't generic - I have client projects, personal receipts, research articles, and family photos all mixed together. I needed something that understood *my* categories, *my* naming conventions, and *my* workflow.

## What I Built

This project turns Claude into a personalized file organization agent that:

### 1. Learns Your Structure
You define your folders and project codes once (like `ACME` for your biggest client, or `PERS` for personal files). The agent remembers and uses them consistently.

### 2. Understands File Contents
Instead of just looking at extensions, it actually reads documents to figure out what they are. That mystery `Document.pdf`? It opens it, sees it's an invoice from December, and proposes renaming it to `2024-12_ACME_invoice.pdf`.

### 3. Asks Before Acting
Nothing moves without your approval. You see exactly what it plans to do and can say "skip that one" or "put it in review."

### 4. Keeps Complete Logs
Every action is recorded. If something ends up in the wrong place, you can trace exactly what happened and undo it.

## The Power of Orchestrated AI Agents

What makes this different from asking ChatGPT "how should I organize my files?" is that this actually *does the work*.

You're not getting advice - you're deploying an agent that:

1. **Scans** your actual Downloads folder
2. **Opens and reads** poorly-named files
3. **Creates** the folder structure you defined
4. **Renames** files using your naming convention
5. **Moves** everything to the right place
6. **Documents** every step in case you need to undo something

It's like having a personal assistant who knows your filing system, works tirelessly, asks clarifying questions when unsure, and keeps meticulous notes.

## The Result

In my first run, this organized **81 files in about 45 minutes**:

- 3 flight receipts I'd forgotten about → `PERSONAL/Receipts/`
- An important investor pitch deck hiding as `Screenshot 2022-02-06.pdf` → `WORK/`
- Duplicate files identified and flagged
- Complete audit trail for everything

My Downloads folder went from chaos to clean, with every action logged in case I ever need to find something or undo a move.

---

## Now It's Your Turn

This project is open source because everyone deserves a clean Downloads folder. Whether you're a freelancer juggling client files, a student drowning in course materials, or just someone who downloads a lot of PDFs, this can help.

The setup takes about 10 minutes. The first organization run takes maybe an hour (with lots of approval checkpoints). After that? Just tell Claude to "organize my downloads" whenever things get messy again.

[Get started →](../README.md#quick-start)

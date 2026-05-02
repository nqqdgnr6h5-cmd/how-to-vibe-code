# How to Start Vibe Coding
### A Complete Guide with Python

> *"There's a new kind of coding I call 'vibe coding', where you fully give in to the vibes, embrace exponentials, and forget that the code even exists."* — Andrej Karpathy, February 2025

Vibe coding is the art of building software by conversing with an AI model. You describe what you want, the AI writes the code, you run it, and you iterate — often without reading every line the AI produces. It sounds irresponsible. It can be. But when done with discipline, it is also the single biggest multiplier of individual output in the history of software, and it is transforming who gets to build things.

This guide will take you from zero to productive vibe coder with Python. It is long on purpose. Skim the sections you know, read the ones you don't.

---

## Table of Contents

1. [What Vibe Coding Actually Is](#1-what-vibe-coding-actually-is)
2. [Mindset and Philosophy](#2-mindset-and-philosophy)
3. [Prerequisites: What You Actually Need to Know](#3-prerequisites-what-you-actually-need-to-know)
4. [Setting Up Your Environment](#4-setting-up-your-environment)
5. [Choosing Your AI Coding Tools](#5-choosing-your-ai-coding-tools)
6. [The Vibe Coding Workflow](#6-the-vibe-coding-workflow)
7. [Prompting: The Core Skill](#7-prompting-the-core-skill)
8. [Your First Vibe-Coded Project (Walkthrough)](#8-your-first-vibe-coded-project-walkthrough)
9. [Debugging With AI](#9-debugging-with-ai)
10. [Version Control and Safety Nets](#10-version-control-and-safety-nets)
11. [Security and Secrets](#11-security-and-secrets)
12. [When Vibe Coding Works, and When It Doesn't](#12-when-vibe-coding-works-and-when-it-doesnt)
13. [Common Pitfalls and How to Avoid Them](#13-common-pitfalls-and-how-to-avoid-them)
14. [Scaling From Toys to Real Software](#14-scaling-from-toys-to-real-software)
15. [A 30-Day Practice Plan](#15-a-30-day-practice-plan)
16. [Resources and Further Reading](#16-resources-and-further-reading)

---

## 1. What Vibe Coding Actually Is

The term "vibe coding" was coined by Andrej Karpathy (co-founder of OpenAI, former director of AI at Tesla) in a tweet in early 2025. The core idea: instead of *writing* code, you *describe* code. The AI writes it. You read the output, try it, and if something breaks, you paste the error back and ask the AI to fix it.

**What makes it different from just "using AI to help code":**

- **Intent over syntax.** You think in terms of what the program should *do*, not how each line should be written.
- **Iteration over planning.** You don't draw up architecture diagrams. You build something ugly, run it, and shape it through dialogue.
- **Trust, but verify.** You let the AI drive most of the keystrokes. Your job is to steer, test, and course-correct.
- **The diff is the conversation.** Your "source of truth" isn't the code — it's the sequence of prompts that produced the code.

### A Spectrum, Not a Binary

Vibe coding is a spectrum:

| Style | Description | Good for |
|---|---|---|
| **Pure vibe** | You never read the code. You just check if the app works. | Throwaway scripts, personal tools, prototypes |
| **Supervised vibe** | AI writes, you skim and approve. You catch obvious issues. | Weekend projects, side apps, exploration |
| **Collaborative vibe** | AI writes, you read carefully, ask for changes, refactor together. | Real products, learning, anything shipped to users |
| **AI-assisted** | You write most of the code. AI helps with snippets and boilerplate. | Production systems, security-critical code |

A healthy vibe coder fluidly moves up and down this spectrum depending on what they're building. A birthday card generator for their niece? Pure vibe. A payment processing backend? Collaborative at best, and frankly you should probably read every line.

### Why Python?

Python is the best language to vibe code in, and it's not close:

- **AI models are fluent in it.** Python is the single most-represented language in AI training data. Models write better Python than any other language.
- **Readable by design.** When you do read the code the AI wrote, Python doesn't punish you. It looks close to pseudocode.
- **Batteries included.** The standard library and PyPI mean "there's a package for that" is almost always true.
- **Forgiving.** Dynamic typing, interpreted execution, a REPL. You can iterate fast.
- **Ubiquitous.** Data, ML, scripting, backends, automation, scraping, games, CLIs — it's everywhere.

---

## 2. Mindset and Philosophy

Before any setup, get your head right. The tools are easy. The mindset is the hard part.

### Embrace "Good Enough"

The single biggest unlock in vibe coding is accepting that code doesn't have to be elegant to be useful. A working 80-line script that solves your problem beats a beautiful 30-line script that you never finish. Shipping beats perfecting.

### Think in Outputs, Not Code

Before asking the AI for anything, ask yourself: *what do I want to see when this works?* A file on disk? A webpage at localhost:8000? A number printed to the terminal? A CSV with five columns? The clearer your mental image of the output, the better your prompts will be.

### Talk to the AI Like a Sharp but Literal Intern

The AI is very capable but has no context about your project unless you give it. Over-explain. Paste error messages in full. Show it the file structure. Describe the user. The best vibe coders write prompts that read like mini-briefs: *who* is this for, *what* should it do, *what* does success look like, *what* are the constraints.

### Read the Code Eventually

Pure vibe is fine for a weekend. But if you want to grow as an engineer, circle back. After a session, skim what the AI wrote. Ask it to explain any line you don't understand. This is how you level up while shipping.

### Keep Your Sense of Smell  (smell is very much needed)

Even if you don't read every line, develop instincts for when something is *off*. Clues:
- The AI adds dependencies you've never heard of
- The code is suspiciously long for a simple task
- It hallucinates function names or APIs (easy to spot — they don't exist when you run it)
- It silently ignores parts of your request
- It's doing something security-sensitive (auth, payments, file deletion) without you asking carefully

---

## 3. Prerequisites: What You Actually Need to Know

You do not need to be a programmer to vibe code. You do need *some* foundation, or you will drown in errors you can't interpret. Here's the minimum.

### Concepts (not skills — just awareness)

- **What a file is.** Where it lives on disk. What extensions mean.
- **What a terminal/command line is.** You will type commands into one.
- **What a script is.** A file you run top to bottom.
- **What a function is.** A named chunk of code you can call.
- **What an error looks like.** Red text is information, not a failure of the universe.
- **What a package is.** Code someone else wrote that you can install and use.

### Python-Specific Minimum

You don't need to master Python before starting. But being able to read it helps. Can you roughly interpret this?

```python
def greet(name):
    if name:
        print(f"Hello, {name}!")
    else:
        print("Hello, stranger!")

greet("Alice")
```

If yes, you're set. If no, spend two hours on a free intro (Automate the Boring Stuff with Python, or Python in freeCodeCamp's 4-hour video). Come back. You'll be fine.

### Terminal Minimum

Be able to:
- Open a terminal on your OS
- Change directory with `cd foldername`
- List files with `ls` (macOS/Linux) or `dir` (Windows)
- Run a Python file with `python filename.py`
- Install a package with `pip install packagename`

That's it. The AI can guide you through the rest.

---

## 4. Setting Up Your Environment

Skip this section if you already code. Otherwise, do this once and never think about it again.

### Step 1: Install Python

Go to [python.org/downloads](https://www.python.org/downloads/). Download the latest stable Python (3.12 or later). Install it. **On Windows, check the box that says "Add Python to PATH"** — this is the single most common setup mistake.

Verify:

```bash
python --version
# or on some systems
python3 --version
```

You should see something like `Python 3.12.x`.

### Step 2: Install a Code Editor

You need a place to see and edit code. The standard choice is **Visual Studio Code** (free, from Microsoft). Download from [code.visualstudio.com](https://code.visualstudio.com/). Install it. Open it. Install the "Python" extension from Microsoft when it prompts you.

Alternatives worth knowing about:
- **Cursor** — a fork of VS Code with AI baked in deeply. Excellent for vibe coding.
- **Windsurf** — similar philosophy, different flavor.
- **Zed** — fast, modern editor with AI features.

For your first week, VS Code is totally fine. You can graduate to Cursor once you know what you like.

### Step 3: Make a Projects Folder

Create a folder somewhere sensible:

```bash
mkdir ~/code
cd ~/code
```

This is where all your vibe-coded projects will live. Keep it tidy. Every project gets its own subfolder.

### Step 4: Learn the Virtual Environment Habit

Every Python project should have its own isolated environment. This prevents "package X version Y breaks package Z" hell. For each new project:

```bash
mkdir my-project
cd my-project
python -m venv .venv

# Activate it:
# macOS/Linux:
source .venv/bin/activate
# Windows:
.venv\Scripts\activate

# Now pip install inside this project won't pollute your system
pip install requests
```

When your terminal prompt shows `(.venv)` at the start, you're inside the environment. To leave: `deactivate`.

If this feels like too much overhead, a modern alternative is **[uv](https://github.com/astral-sh/uv)**, a fast Python package manager that handles virtual environments automatically. `uv init`, `uv add requests`, `uv run script.py`. Many vibe coders prefer it.

### Step 5: Install Git

Install [Git](https://git-scm.com/downloads). You will use it as your safety net. More on this in Section 10.

---

## 5. Choosing Your AI Coding Tools

There are three categories of tools you'll pick from. Most vibe coders use one from each.

### Category A: Chat-First (paste and iterate)

You chat with an AI in a browser tab, copy code back to your editor, run it, paste errors back. Slow but universal.

- **Claude.ai** — widely considered the strongest model for coding, especially for multi-file reasoning and subtle bugs. Excellent at Python.
- **ChatGPT** — fine, widely available.
- **Gemini** — good, especially for long context (big files).

**Pros:** Free tiers exist. Works for any language, any project. Easy to learn.
**Cons:** Lots of copy-pasting. The AI doesn't see your whole codebase.

### Category B: Editor-Integrated (AI inside your IDE)

The AI lives in your editor and can read your files, write directly into them, and run your terminal.

- **Cursor** — the flagship vibe coding editor. A fork of VS Code with deep AI integration. Cmd-K to generate, Cmd-L to chat with your whole project. Paid, with a free tier.
- **Windsurf** — similar to Cursor, with an "agentic" mode where the AI takes multiple actions on its own.
- **GitHub Copilot** — inline completions as you type, plus a chat panel. Works in VS Code and JetBrains.
- **Zed** — fast editor with AI features, lighter-weight than Cursor.

**Pros:** The AI has context. Much less copy-paste. Faster iteration.
**Cons:** Subscription cost. Learning curve. Can cause over-reliance.

### Category C: Terminal/Agent-First (AI as a command-line tool)

You run a command, the AI reads your project, makes changes, runs tests, and reports back.

- **Claude Code** — Anthropic's official CLI. You run `claude` in your project, describe a task, and it works on it. Very good for multi-step changes.
- **Aider** — open source, works with various models.
- **OpenAI Codex CLI** — similar category.

**Pros:** Genuinely agentic — can handle multi-step tasks end-to-end. Great for refactors, migrations, test writing.
**Cons:** Less hand-holding. Requires comfort with the terminal. Easy to let the AI do things you didn't intend.

### My Recommended Starter Stack

If you're just starting:

1. **Claude.ai** (free or Pro) for planning, debugging, learning — the "thinking partner."
2. **VS Code + GitHub Copilot** or **Cursor** for writing code with AI assistance.
3. Once comfortable: add **Claude Code** for agentic tasks.

You can do everything in this guide with just Claude.ai and a text editor. Fancier tools are an optimization, not a prerequisite.

---

## 6. The Vibe Coding Workflow

Here's the actual loop, step by step. Internalize this and you're 80% of the way there.

### The Loop

```
┌─────────────────┐
│ 1. Describe     │
│    what you     │ ──┐
│    want         │   │
└─────────────────┘   │
        ▲             ▼
┌─────────────────┐   ┌─────────────────┐
│ 5. Refine       │   │ 2. Get code     │
│    (paste       │   │    from AI      │
│    errors,      │   └─────────────────┘
│    ask for      │           │
│    changes)     │           ▼
└─────────────────┘   ┌─────────────────┐
        ▲             │ 3. Run it       │
        │             └─────────────────┘
        │                     │
        │                     ▼
        │             ┌─────────────────┐
        └─────────────│ 4. Observe what │
                      │    happens      │
                      └─────────────────┘
```

### Step 1: Describe What You Want

Before you type a single prompt, answer these in your head (or on paper):

- What is the input? (A file? A URL? Nothing?)
- What is the output? (A printed number? A new file? A webpage?)
- What's the happy path? (If it works perfectly, what does the user experience?)
- What's the rough shape? (A script? A web app? A CLI tool?)

Now write the prompt. Be specific. Be concrete.

### Step 2: Get Code From AI

Paste the prompt into your AI of choice. Read the response. Don't just copy-run — at least skim:

- Does it make sense structurally?
- Is it using weird libraries you don't recognize?
- Is it addressing all the parts of your request?

If something looks off, ask. "Why did you choose library X?" or "Can you do this without any external dependencies?"

### Step 3: Run It

Save the code to a file. Run it. Actually run it — this is the most-skipped step and the most important one.

```bash
python myscript.py
```

### Step 4: Observe What Happens

Three possible outcomes:

- **It works.** Great. Move on, or ask the AI to extend it.
- **It errors.** Copy the entire error message. The *whole* traceback.
- **It runs but does the wrong thing.** Describe what you expected vs. what you got.

### Step 5: Refine

Go back to the AI. Paste the error or describe the wrong behavior. Ask for a fix. Loop.

### Loop Discipline

A few rules that separate good vibe coders from frustrated ones:

- **One change at a time.** Don't ask for five improvements in one prompt. You'll lose track of what caused what.
- **Commit working code.** Every time something works, `git commit`. This means you can always roll back.
- **Read the diff.** When the AI changes your code, ask "what did you change and why?" before moving on.
- **Kill the thread when it gets confused.** If the AI is going in circles, start a fresh conversation with a clean summary of where you are.

---

## 7. Prompting: The Core Skill

Prompting is 90% of vibe coding. These are the patterns that work.

### The Anatomy of a Good Coding Prompt

A strong prompt has four parts:

1. **Context** — what the project is
2. **Task** — what you want done right now
3. **Constraints** — what it should or shouldn't do
4. **Output format** — what you want back

Example:

> **Context:** I'm building a CLI tool in Python that helps me organize my downloads folder.
>
> **Task:** Write a function that takes a folder path and moves every file into a subfolder named after its file extension. For example, `report.pdf` goes into a `pdf/` subfolder.
>
> **Constraints:** Use only the standard library (no extra pip installs). Handle files with no extension by putting them in a folder called `no_extension`. Don't move folders, only files. Print what you're doing for each file.
>
> **Output:** Give me a single Python function called `organize_folder(path)` and a short example of how to call it.

Compare that to: "write me a python script to organize downloads." Both get you code. The first gets you code that actually works on your first try.

### Useful Prompt Patterns

**The "act as" pattern:**
> "Act as a senior Python engineer reviewing a junior's code. Here's the code: [paste]. Point out issues and suggest fixes."

**The "minimum viable" pattern:**
> "Give me the absolute minimum code to do X. I want to understand the core idea. No error handling, no edge cases — just the essence."

**The "one file" pattern:**
> "Write this as a single Python file I can run with `python script.py`. No config, no setup, no framework."

**The "explain then code" pattern:**
> "First explain how you'd approach this in 2-3 sentences. Then write the code."

**The "teach me" pattern:**
> "I don't understand why this works. Walk me through it line by line as if I were learning Python."

**The "step by step" pattern:**
> "Don't write all the code yet. First, list the steps you'll take. I'll confirm, then you'll write them one at a time."

### Good vs Bad Prompts

**Bad:** "my code doesnt work"
**Good:** "Here's my code: [paste]. When I run it with input 'abc', I expect 'cba' but I get 'abc'. What's wrong?"

**Bad:** "make it better"
**Good:** "This works, but it's slow on files over 1GB. Can you rewrite it to stream the file instead of loading it all into memory?"

**Bad:** "add error handling"
**Good:** "Add error handling for two cases: (1) the file doesn't exist, print a friendly message and exit cleanly; (2) the file exists but isn't valid JSON, print the bad line number."

### When Stuck: The Reset

If you've been in a conversation for a while and the AI is tangled up, do this:

1. Start a new chat.
2. Paste your current code.
3. Describe, in plain English, what it does now.
4. Describe what you want it to do next.
5. Ask the AI to proceed.

A clean context window often solves what 20 more messages won't.

---

## 8. Your First Vibe-Coded Project (Walkthrough)

Let's do one together. We'll build a **word frequency counter** that reads a text file and prints the top 10 most common words. Then we'll extend it.

### Prompt 1 — Initial Build

> I want a Python script that reads a text file and prints the top 10 most common words, along with their counts. Make it a single file called `wordcount.py`. The filename should be passed as a command-line argument. Use only the standard library. Convert everything to lowercase and ignore punctuation.

You'll get something like:

```python
import sys
import re
from collections import Counter

def main():
    if len(sys.argv) != 2:
        print("Usage: python wordcount.py <filename>")
        sys.exit(1)

    filename = sys.argv[1]
    with open(filename, "r", encoding="utf-8") as f:
        text = f.read().lower()

    words = re.findall(r"\b[a-z']+\b", text)
    counts = Counter(words)

    for word, count in counts.most_common(10):
        print(f"{word}: {count}")

if __name__ == "__main__":
    main()
```

### Run It

Grab any text file. Project Gutenberg has free books — download one as a .txt.

```bash
python wordcount.py moby_dick.txt
```

You'll see something like:

```
the: 14620
of: 6732
and: 6502
a: 4799
to: 4707
...
```

### Prompt 2 — Make It Better

> The top words are all common English words like "the" and "of". Can you add an option to ignore a standard list of English stopwords? Add a `--no-stopwords` flag.

### Prompt 3 — Extend

> Now instead of printing, save the results to a CSV file called `wordcount.csv` with two columns: "word" and "count". Write all unique words, not just top 10. Keep the option to print top 10 to the screen as well.

### Prompt 4 — Make It Pretty

> Can you add a progress bar using `tqdm` for large files? And print the total word count, unique word count, and most-common word as a summary at the end.

### What Just Happened

You shipped a real, working tool in four prompts. You now have:
- A script that processes text
- Command-line arguments
- A library dependency
- CSV output
- Progress reporting

**More importantly:** you learned the rhythm. Describe → receive → run → iterate. That's the whole job.

### Homework

Try these next, each as its own small vibe-coded project:
- A script that renames all the photos in a folder using their EXIF date.
- A tiny Flask web app that shows a random joke from a text file.
- A Markdown-to-HTML converter using only the standard library.
- A CLI tool that fetches the weather for a city using a free API.

Each one should take 20–60 minutes. Do three this weekend.

---

## 9. Debugging With AI

Debugging is where vibe coding most often breaks down — and where it most often shines if you do it right.

### The Golden Rule of Error Reporting

**Paste the entire error message. Every line. Verbatim.**

Not "I got an error." Not "it says something about a NoneType." The full traceback. It looks like:

```
Traceback (most recent call last):
  File "wordcount.py", line 12, in main
    words = re.findall(r"\b[a-z']+\b", text)
  File "wordcount.py", line 9, in main
    text = f.read().lower()
AttributeError: 'NoneType' object has no attribute 'lower'
```

Every line of that is information the AI needs.

### The Debug Prompt Template

> Here's my code: [paste full code]
>
> Here's the command I ran: `python wordcount.py test.txt`
>
> Here's the error I got: [paste full error]
>
> What's going wrong and how do I fix it?

This template will solve 90% of your errors without drama.

### When the AI's Fix Doesn't Work

If the AI's first fix doesn't work, *don't* just say "didn't work." Instead:

> I applied your change. Now I get this different error: [paste]. Here's the current state of the file: [paste].

Always give the current state. The AI has no memory of what it told you five minutes ago, especially across sessions.

### Print Debugging

A surprisingly effective technique: ask the AI to add print statements.

> Can you add print statements at the key points in this function so I can see what values the variables have at each step?

Run it. Paste the printed output back. Ask "does this tell you what's wrong?"

### Binary Search the Problem

When the AI is flailing, help it narrow down:

> Let's narrow this down. Here's a minimal version of the code that isolates the problem: [paste]. When I run it with this exact input, I get this exact output. Expected: X. Got: Y.

The more you can shrink the reproducer, the faster you'll find the bug.

### Logical Bugs (When It Runs But Does the Wrong Thing)

These are harder. The code doesn't crash — it just lies to you. Give the AI:

1. What the code does
2. A specific input
3. What you expected to happen with that input
4. What actually happened

> My function `discount(price, pct)` should return the price after a percent discount. `discount(100, 20)` should return 80. It's returning 120. Here's the code: [paste].

---

## 10. Version Control and Safety Nets

If you vibe code without version control, you will eventually lose work. Not maybe — *will*. The AI will rewrite a file you needed. You'll accept a change that breaks three other things. You'll close a tab.

### Git in 60 Seconds

Inside your project folder:

```bash
git init                          # one time, at the start
git add .                         # stage all changes
git commit -m "working version"   # snapshot them
```

Rules of thumb:
- **Commit every time something works.** Even if it's small. Especially if it's small.
- **Use descriptive messages.** "working version" is fine sometimes. "added CSV output" is better.
- **Before a big AI refactor, commit first.** That way you can always `git reset --hard` back.

### Key Recovery Commands

| Situation | Command |
|---|---|
| Undo all uncommitted changes | `git reset --hard` |
| See what changed since last commit | `git diff` |
| See commit history | `git log --oneline` |
| Go back to a previous commit | `git checkout <commit-hash>` |
| Create a branch to try something risky | `git checkout -b experiment` |

### GitHub (Optional but Recommended)

Push your projects to [GitHub](https://github.com). It gives you:
- Offsite backup
- A portfolio
- Easy sharing
- A natural checkpoint rhythm

`git push` after every meaningful commit and you'll never lose work.

### The Branching Habit for Risky Prompts

Before you ask the AI to do something big ("refactor this whole file to use async"), branch:

```bash
git checkout -b try-async
# ... vibe code the change ...
# if it works: merge it back
git checkout main
git merge try-async
# if it doesn't: just delete the branch
git checkout main
git branch -D try-async
```

This one habit has saved more vibe-coded projects than any other.

---

## 11. Security and Secrets

Vibe coding makes security mistakes easy to make and hard to notice. A few non-negotiable rules.

### Never Paste Secrets Into Your Code

API keys, passwords, database URLs with passwords — none of these go in your source files. Use environment variables:

```python
import os
api_key = os.environ["OPENAI_API_KEY"]
```

Then set it in your shell:

```bash
export OPENAI_API_KEY="sk-..."
```

Or use a `.env` file with the `python-dotenv` package, and **add `.env` to your `.gitignore`**.

### `.gitignore` is Mandatory

Create a file called `.gitignore` in your project root. Paste this in:

```
.env
.venv/
__pycache__/
*.pyc
.DS_Store
*.sqlite3
*.log
secrets/
```

Without this, you will eventually commit a secret to GitHub. It happens to everyone. Prevent it up front.

### If You Ever Commit a Secret

Rotate it *immediately*. Don't delete the file and push — the secret is still in git history. Generate a new key, revoke the old one, and be more careful next time.

### Be Suspicious of AI-Suggested Packages

Sometimes AIs invent package names. Sometimes attackers register those invented names with malicious code (this is called "slopsquatting"). Before `pip install`-ing something the AI told you about:

- Check it on [pypi.org](https://pypi.org). Is it popular? How old? Who maintains it?
- Search its name + "github." Is there a real repo?
- If it feels off, ask the AI: "is this a real, widely used package, or did you make it up?"

### Don't Let the AI Run Destructive Commands Blindly

If an agent tool (Cursor's agent mode, Claude Code, etc.) proposes commands like `rm -rf`, `DROP TABLE`, `git push --force`, or anything that modifies things outside your project folder — **read it, understand it, and confirm it manually**. Agents are powerful. Powerful tools cut you.

### User Input is Always Hostile

If you're building anything that takes user input — a web app, a CLI that reads files, a script that runs SQL — assume someone malicious will use it. Ask the AI explicitly: "what security issues does this code have?" and take the answer seriously.

---

## 12. When Vibe Coding Works, and When It Doesn't

Honest assessment. Vibe coding is not a universal solvent.

### Where It Shines

- **Personal tools.** Things only you will ever use.
- **Scripts and automation.** Anything under 500 lines.
- **Prototypes.** Getting to "is this idea even worth pursuing?"
- **Web scraping, data cleaning, file processing.** Bread and butter.
- **Learning.** Trying things in new languages, new libraries.
- **Glue code.** Connecting API A to service B with transformation C.
- **Internal tools.** Things a small team uses where "it works for now" is fine.

### Where It Struggles

- **Large codebases.** Once the project is too big for the AI to see at once, quality drops.
- **Subtle business logic.** Financial calculations, legal compliance, medical dosing.
- **Concurrency and distributed systems.** Race conditions are hard for humans; they're hard for AI too.
- **Performance-critical code.** The AI writes "works" code, not "blazing fast" code.
- **Novel algorithms.** If the solution isn't on Stack Overflow or GitHub, the AI often flounders.
- **Production security.** Auth systems, payment processors, anything handling sensitive data.
- **Long-lived code.** Code you'll maintain for years benefits from being written by humans who understand it.

### The Honest Default

Use vibe coding freely for the first category. Use it carefully, with code review and testing, for in-between cases. For the hard category, treat the AI as a helpful tool inside a traditional engineering process — not as the process itself.

---

## 13. Common Pitfalls and How to Avoid Them

Things that will bite you. All have been experienced by nearly every vibe coder.

### Pitfall: The Endless Fix Loop

**Symptom:** You keep asking for fixes. Each fix breaks something else. The code grows more baroque with each turn.

**Cause:** The AI is patching without understanding the root problem. Probably you are too.

**Fix:** Stop. Revert to the last known good version. Re-describe the problem from scratch in a new conversation. Often the right fix is a rewrite, not more patches.

### Pitfall: The Phantom Dependency

**Symptom:** You install a package the AI recommended. It doesn't work, or worse, it's not what you thought.

**Fix:** Always verify packages on PyPI before installing. Prefer the standard library when possible. Pin versions in a `requirements.txt`.

### Pitfall: The Silent Rewrite

**Symptom:** You ask for a small tweak. The AI returns a completely restructured file with your careful changes gone.

**Fix:** Ask explicitly: "only change the X function. Don't touch anything else." Or use a tool that shows you diffs, not full rewrites. Or just `git diff` every change before committing.

### Pitfall: Built-In but Rebuilt

**Symptom:** The AI writes 40 lines to do something that `pathlib` or `itertools` does in 2.

**Fix:** When you see a lot of code, ask: "is there a standard library function that does this?" Often there is.

### Pitfall: The Works-On-My-Machine Trap

**Symptom:** Your script works. You send it to someone else. It doesn't work.

**Fix:** Always create a `requirements.txt` (`pip freeze > requirements.txt`). Always mention your Python version. Always test on a clean virtual environment before sharing.

### Pitfall: The Confident Lie

**Symptom:** The AI explains its code in great detail. The explanation is wrong.

**Fix:** Test behavior, not explanations. If the AI says "this function returns a sorted list," call it with a messy input and see if the output is actually sorted. Don't trust claims — verify.

### Pitfall: Copy-Paste Archaeology

**Symptom:** Three months later, you open a project and have no idea how any of it works.

**Fix:** Add comments as you go. Ask the AI: "explain this code with comments, and add a README describing how to run it." Your future self will thank you.

### Pitfall: Over-Engineering

**Symptom:** You asked for a script. You got a class hierarchy with a factory pattern and a config loader.

**Fix:** Say "make this as simple as possible. One function, no classes, no config files."

---

## 14. Scaling From Toys to Real Software

At some point, you'll want to vibe code something bigger than a script. Here's how the discipline changes.

### Project Structure

A real Python project looks roughly like:

```
my-project/
├── .venv/                  # your virtual environment (gitignored)
├── .gitignore
├── README.md
├── requirements.txt        # or pyproject.toml
├── src/
│   └── my_project/
│       ├── __init__.py
│       ├── main.py
│       └── helpers.py
├── tests/
│   └── test_helpers.py
└── scripts/
    └── run.sh
```

Ask the AI to set this up for you when starting: "Scaffold a standard Python project layout for [description]."

### Tests Become Your Friend

In a one-file script, you can just run it to see if it works. In a real project, you need tests. Tests are also the single best way to keep the AI honest — you can run them before and after a change and catch regressions.

Ask:
> "Write pytest tests for this function. Cover the happy path, an empty input, a malformed input, and an edge case."

Then run `pytest` after every AI change.

### Type Hints

Type hints help you *and* the AI. They make bugs visible earlier and give the AI more information to work with.

```python
def discount(price: float, pct: float) -> float:
    return price * (1 - pct / 100)
```

Ask the AI to add type hints to your code. Use `mypy` or `pyright` to check them.

### Linting and Formatting

Once your project has more than a few files:

```bash
pip install ruff
ruff check .        # find issues
ruff format .       # auto-format
```

Ruff is a fast, modern linter that replaces several older tools. Run it regularly.

### Documentation

Every project needs at minimum:
- A `README.md` explaining what it is and how to run it
- Docstrings on public functions

Ask the AI to write both.

### Architecture Conversations

For bigger projects, before coding, *talk through the design*:

> I want to build [description]. Before we write any code, walk me through three possible architectures. For each, explain the tradeoffs. Then recommend one.

You'll often catch bad design choices before they become 2,000 lines of code.

### Splitting Work Into Chunks

Big features are hard for AI to one-shot. Break them down:

1. "List all the pieces this feature needs."
2. "Let's build piece 1 first. [details]"
3. [Build and test piece 1]
4. "Now piece 2, which depends on piece 1. [details]"

This is how professional engineers work, too. Vibe coders just do it in conversation instead of on a whiteboard.

---

## 15. A 30-Day Practice Plan

The only way to get good at this is to do it. Here's a four-week plan.

### Week 1: Scripts

One small Python script per day. Each one should take 20–45 minutes. Ideas:

- Day 1: Word counter (follow the walkthrough above)
- Day 2: Rename files in a folder based on a pattern
- Day 3: Scrape a simple webpage and save data to CSV
- Day 4: Merge multiple CSVs into one
- Day 5: Convert all images in a folder to a new format
- Day 6: Generate a random password
- Day 7: Build a flashcard quiz from a text file

Goal: get comfortable with the loop. Describe, generate, run, fix.

### Week 2: Slightly Larger

Projects that span multiple files or use a library you don't know. 1–2 hours each.

- Day 8: A Flask web app that shows you the weather
- Day 9: A Telegram or Discord bot that does one simple thing
- Day 10: A command-line todo app that saves to a JSON file
- Day 11: A script that summarizes your day from your calendar
- Day 12: A tiny personal blog from Markdown files
- Day 13: A data visualization with matplotlib or plotly
- Day 14: Rebuild one of week 1's projects from scratch, from memory

Goal: learn to split problems into steps.

### Week 3: With Tests and Git

Pick one idea and actually *maintain* it for the week. Use git. Write tests.

- Day 15: Scope the project. Write a README *before* coding.
- Day 16: Build the first working version. Commit.
- Day 17: Add tests for the core functions.
- Day 18: Add a new feature. Don't break the tests.
- Day 19: Refactor something ugly. Tests should still pass.
- Day 20: Add error handling and logging.
- Day 21: Polish the README. Push to GitHub.

Goal: learn the rhythm of real software.

### Week 4: Go Off-Road

Pick a project *you actually want to exist in the world*. Something useful to you or someone you know. Spend the whole week on it. Ship it.

Goal: experience the full arc from idea to shipped thing, with AI as your partner.

---

## 16. Resources and Further Reading

### Official Documentation

- **Python docs** — [docs.python.org](https://docs.python.org) — the authoritative reference
- **PyPI** — [pypi.org](https://pypi.org) — package registry
- **Real Python** — [realpython.com](https://realpython.com) — high-quality tutorials

### AI Coding Tools

- **Claude.ai** — [claude.ai](https://claude.ai)
- **Cursor** — [cursor.com](https://cursor.com)
- **GitHub Copilot** — [github.com/features/copilot](https://github.com/features/copilot)
- **Claude Code** — [docs.claude.com](https://docs.claude.com) — Anthropic's official CLI
- **Aider** — [aider.chat](https://aider.chat)

### Python Fundamentals (if you want more grounding)

- **Automate the Boring Stuff with Python** by Al Sweigart — free online, perfect for beginners
- **Fluent Python** by Luciano Ramalho — for when you want to go deep
- **Python Tricks** by Dan Bader — bite-sized patterns

### Vibe Coding Community

- **[Awesome Vibe Coding](https://github.com/ai-for-developers/awesome-vibe-coding)** — where the term originated; still a good signal source
- **r/vibecoding** on Reddit
- **Hacker News** — search for "vibe coding" threads
- **Simon Willison's blog** — [simonwillison.net](https://simonwillison.net) — one of the most thoughtful writers on practical AI coding


### When You Want to Stop Vibing and Start Engineering

- **Designing Data-Intensive Applications** by Martin Kleppmann
- **The Pragmatic Programmer** by Hunt & Thomas
- **A Philosophy of Software Design** by John Ousterhout

---

## Final Thoughts

Vibe coding isn't magic and it isn't cheating. It's a new interface to an old craft. The craft is still about understanding what you're building, caring about the people who'll use it, and being honest with yourself about what works.

The AI is a genuinely incredible collaborator — faster, more patient, and more widely read than any human could be. But it doesn't know your users. It doesn't know your constraints. It doesn't care if the code ships. You do. That part of the job isn't going anywhere.

Start small. Ship things. Break things. Read the code you generate, eventually. Keep a `git log` of your learning. In six months you'll be shocked at what you can build.

Now close this document, open your editor, and make something.

---

*Good luck, and welcome to the vibes.*

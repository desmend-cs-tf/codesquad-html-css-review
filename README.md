# HTML, CSS & JavaScript Review: "My City" Page

A 10–15 minute warm-up before we dive into Replit. You will build a one-page website about a city, **first without Replit's help, then compare it to a hand-built answer**.

**What the page must have**

| # | Requirement | Skill it practices |
|---|-------------|--------------------|
| 1 | The city's most famous food, **with an image** | HTML `<img>`, `alt` text |
| 2 | A **list** with the city's nickname, population, and the year its state joined the U.S. | HTML lists `<ul>` / `<li>` |
| 3 | The **current governor or leader** of the city | Semantic HTML, text content |
| 4 | A **class** for the state bird; when you **click the bird it moves or shakes** | CSS class + `@keyframes`, JS click event |
| 5 | A small JS section where you can **add something you like** about the city, shown as a list (no database) | DOM: `createElement`, `appendChild`, form events |

> The finished example uses **Chicago, Illinois**. You will pick **your own city** (or ask your TF).

---

## Part 1: Git setup (clone, branch, publish)

Do these in your terminal. Replace anything in `<angle brackets>`.

### 1. Clone the repo (download a copy)

```bash
git clone <REPO_URL>
cd html-css-js-review
```

### 2. Make your own branch

Never work directly on `main`. Name your branch with your name and city.

```bash
git checkout -b <yourname>-<city>
# example: git checkout -b maria-houston
```

Check where you are:

```bash
git status
git branch
```

### 3. Save your work (add + commit)

```bash
git add .
git commit -m "Add city page with food, facts, bird, and likes list"
```

### 4. Publish your branch to GitHub (push)

The first time, use `-u` so Git remembers where to push:

```bash
git push -u origin <yourname>-<city>
```

After that, you only need `git push`.

### Git cheat sheet

| Command | What it does |
|---------|--------------|
| `git clone <url>` | Download a repo to your computer |
| `git status` | See what changed |
| `git checkout -b <name>` | Create and switch to a new branch |
| `git checkout <name>` | Switch to an existing branch |
| `git add .` | Stage all changes |
| `git commit -m "message"` | Save a snapshot with a message |
| `git push -u origin <name>` | Publish a new branch (first time) |
| `git push` | Publish new commits (after that) |
| `git pull` | Get the latest changes |
| `git log --oneline` | See your commit history |

---

## Part 2: Build it with Replit

1. Go to [replit.com](https://replit.com) and start a new Replit Agent / App.
2. Fill in `[YOUR CITY]` and `[YOUR STATE]`, then paste this whole prompt:

```text
Build a single-page website about [YOUR CITY], [YOUR STATE] using ONLY plain
HTML, CSS, and vanilla JavaScript. No frameworks, no build tools, no database.
Use three files: index.html, style.css, script.js. Put images in an images/ folder.

The page must include:

1. FOOD: The city's most well-known food, with a heading, a short description,
   and an image of the food (with good alt text).

2. QUICK FACTS: An unordered list (<ul>) with three items:
   - The city's nickname
   - The city's population
   - The year its state became a state

3. LEADER: The current governor of the state or the current mayor of the city,
   shown with their name and title.

4. STATE BIRD: An image of the state bird with a CSS class called "bird".
   When I click the bird, it should shake or move using a CSS animation that
   JavaScript triggers by adding and removing a class.

5. THINGS I LIKE: A small section with a text input and an "Add" button.
   When I add something I like about the city, JavaScript adds it to a list on
   the page. Store it in memory only (no database, no localStorage needed).
   Ignore empty input.

Keep the code clean and commented so a beginner can read it.
Make it look good and work on a phone.
```

3. Watch **how Replit builds it**: which files it makes, what it names things, and how it wires the click and the list together.
4. Test all 5 requirements.

---

## Part 3: Make a NEW repo from what Replit built

Now turn Replit's project into your own GitHub repo.

**Option A: from Replit (easiest)**
Use Replit's **Git** tab (or the GitHub button), click **Create a GitHub repository**, name it (for example `my-city-page`), and publish.

**Option B: from your terminal**
Download the Replit files into a new folder, then:

```bash
cd my-city-page
git init
git add .
git commit -m "Initial commit: city page built with Replit"
git branch -M main
git remote add origin <YOUR_NEW_REPO_URL>
git push -u origin main
```

(Create the empty repo on GitHub first and copy its URL.)

---

## Part 4: Compare with the answer

The Chicago answer lives on the **`answers-chicago`** branch.

```bash
git fetch origin
git checkout answers-chicago
```

Open `index.html` in your browser (or run `python3 -m http.server 8000` and visit `http://localhost:8000`).

See exactly what was added on top of the starter:

```bash
git diff main answers-chicago --stat
```

Switch back to your own branch any time:

```bash
git checkout <yourname>-<city>
```

### Review questions (10–15 minutes)

- **HTML:** Why is the facts section a `<ul>` and not several `<p>` tags? What does `alt` do?
- **CSS:** Where is the `.bird` class defined? What does `@keyframes shake` do? Why is it removed after the animation ends?
- **JS:** What does `addEventListener("click", ...)` listen for? How does `createElement` + `appendChild` add a list item? Why use `textContent` instead of `innerHTML`?
- **Replit:** What did Replit do differently from the answer? Is anything missing, wrong, or overbuilt?
- **Facts:** Facts like population and who holds office change. Where would you double check them?

---

## Project structure

```
html-css-js-review/
├── index.html    # page structure
├── style.css     # looks and the shake animation
├── script.js     # click + add-to-list behavior
├── images/       # food and bird pictures
└── README.md
```

## Running it locally

No install needed. Open `index.html` in a browser, or:

```bash
python3 -m http.server 8000
```

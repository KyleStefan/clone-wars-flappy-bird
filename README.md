# Clone Wars · Session 03

**Ben rebuilt Photoshop over a whole build night. You've got about 40 minutes (plus setup, if it's your first time). Clone a game everyone knows, make it yours, and make it better.**

Today you clone a game inspired by Flappy Bird. You don't build it alone, and you don't build it one piece at a time. You **brief a team of AI agents**: one team lead and three builders who work **at the same time**. Then you check their work, ship it, and play it at your own link.

Nobody's game will look the same. Yours might be a seagull over San Luis Obispo at sunset. Your neighbor's might be a pigeon dodging skyscrapers in New York. Same game underneath, your version on top.

> **Missed the meeting?** Everything you need is on this page. Go top to bottom. Each step says how long it takes and what you should see.

**Finish line:** your game plays at your own live link, it looks and sounds like your version, your fix is in it, and your link is in the club portal.

---

## Stuck? Ask your AI first

**It knows your screen better than any officer does.** Your AI can see your exact situation: your laptop, your browser, your error. An officer walking by can't. So **whenever you don't know what to do, give this page to your AI and ask.** Use whatever you have: Codex, Claude Code, ChatGPT, even the ChatGPT app on your phone if your laptop isn't set up yet.

1. Copy the link to this page from your browser's address bar.
2. Take a screenshot of what you're stuck on, if you can. (Mac: **Cmd+Shift+4**. Windows: **Windows key+Shift+S**.)
3. Paste this into your AI, fill in the brackets, attach the screenshot, and send:

```text
I'm a beginner following this tutorial: [paste the link to this page]
Read the whole tutorial first.

I'm on Step [number]: [step name].
Here's what I see: [describe it, or paste the exact error message]
I'm using: [Mac or Windows], [Chrome, Safari or Edge], [Codex, Claude Code or ChatGPT]

Tell me exactly what to click or type next, one small step at a time.
Assume I've never used GitHub or coding tools before.
```

Already in a Codex chat that's connected to your repo? Even easier. Type: `Read README.md and docs/HELP.md in my repo. I'm stuck on Step [number]. Here's what I see: [...]. What do I do next?`

**Still stuck after asking your AI?** Then read [the help page](docs/HELP.md), then ask a neighbor, then ask an officer. Officers are for things AI can't fix: your account, permissions, and the portal.

---

## How today works

You're the **boss**. You give one set of instructions to a **team lead** agent (the orchestrator). The team lead splits the work into three jobs and hands each one to a **builder** agent (a subagent). All three builders work at the same time. The team lead checks their work and hands you one finished package to approve.

```
                         YOU  (the boss)
                          │  one prompt: your version of the game
                          ▼
                   ORCHESTRATOR  (the team lead)
                          │  plans three jobs, you type "go"
          ┌───────────────┼───────────────┐
          ▼               ▼               ▼
     CORE builder     ART builder    SOUND builder     ← all three at the same time
     game.js          sprites.js     sounds.js
     config.js
          └───────────────┼───────────────┘
                          ▼
             ORCHESTRATOR checks the work
                          │  one pull request
                          ▼
             YOU merge it and play it
```

**Why three builders?** For a game this small, one agent could do it all. We use three so you learn the move. On bigger work, like a 20-page website or research on 10 competitors, this is how you finish in a third of the time. The real skill isn't starting three agents. It's knowing **which jobs don't need each other**.

### Words you'll see

| Word | What it means |
| --- | --- |
| **Repo** (repository) | A folder of project files on GitHub. |
| **Template** | The club's starter repo. You make your own copy. You never change the club's copy. |
| **Live link** | Your game on the internet, like `https://your-name.github.io/clone-wars/`. It never changes, even when your game does. |
| **Orchestrator** | The team lead agent. It plans, starts the builders, checks their work. |
| **Subagent** | A builder agent. It does one job and only touches its own files. |
| **Branch** | A separate copy of your files where agents work without touching your real version (`main`). |
| **Pull request (PR)** | The team lead saying "here's the finished work, want it?" |
| **Merge** | You saying "yes." The work goes into `main` and your live link updates. |
| **Answer key** | A working copy of the game's core, in case yours breaks. More in Step 5. |

---

## Step 0 · Before you start

⏱️ **About 10 minutes if you already have GitHub and Codex. 20 to 25 minutes if this is your first time.** Do it before the meeting. If you did Session 02, you're probably already set up. Check each line anyway.

> **In the room and not set up yet?** Go straight to the **officers' setup table** when you arrive. Do Step 0 and Step 1 there. Don't try to listen to the talk and set up at the same time. You'll pair up with a neighbor at Step 4, and you can finish your own game after the meeting with this page.

1. **A GitHub account.** Sign up free at [github.com](https://github.com). Any email works. (New accounts take about 5 minutes: an email code and a quick puzzle.)
2. **Codex with a personal email.** The Codex student offer needs a **personal** email (like Gmail).
   - Signing up with your `calpoly.edu` email fails without telling you why.
   - The school Codex account can't use the GitHub connector, so it won't work today.
   - Stuck on the offer page? Open a private window: **Cmd+Shift+N** on Mac (Chrome or Safari), **Ctrl+Shift+N** on Windows (Chrome, or Edge's InPrivate window). Go to the student offer, sign in there with your personal email, then come back to a normal window.
3. **Connect GitHub to Codex.** In Codex, find the GitHub connector (sometimes called a plugin or app), install it, and sign in to GitHub.
   - When GitHub asks which repositories Codex can see, choose **All repositories**. ("Only select repositories" won't work yet, because the repo you'll use today doesn't exist until Step 1.)
   - Picked the wrong option or skipped the question? You can change it any time on GitHub. See [Codex can't see my repo](docs/HELP.md#codex-setup).
   <!-- CONFIRM after Kyle's test: exact place to find the GitHub connector in the Codex app members use. -->
4. **Pick the cheap model.** In the model picker, choose **GPT-5.6 Luna**. If you don't see it, pick the cheapest, fastest model in the list. Bigger models burn through your usage fast, and today runs four agents.

**Stuck on any of this?** Codex isn't set up yet, so use ChatGPT (laptop or phone) with the [help prompt](#stuck-ask-your-ai-first). Tell it which step you're on and attach a screenshot.

✅ **You should see:** Codex open with your personal account, **GPT-5.6 Luna** selected, and GitHub connected.

---

## Step 1 · Copy the template, go live, submit your link

⏱️ **About 7 minutes**

### 1a · Make your own copy

1. Open the club template: **https://github.com/KyleStefan/clone-wars-flappy-bird**
2. Click the green **Use this template** button, then **Create a new repository**.
3. Fill in:
   - **Owner:** your own account (your username)
   - **Repository name:** `clone-wars`. If you already have a repo with that name, use `clone-wars-2`.
   - **Public** (required for a free live link)
4. Click **Create repository**.

✅ **You should see:** a page at `github.com/YOUR-USERNAME/clone-wars` listing `README.md`, `CONTRACT.md`, `AGENTS.md`, `index.html`, a `docs` folder and a `tests` folder. You'll also see `.gitignore` and `.nojekyll`. Those two are normal. Ignore them.

⚠️ Look at the address bar. It must have **your** username in it, not `KyleStefan`. Last time, lots of people gave Codex the club's link by mistake.

### 1b · Turn on your live link

1. In **your** repo, click **Settings** (top bar, far right). On a small screen it may be hidden under a **⋯** menu at the end of that bar.
2. In the left sidebar, click **Pages**.
3. Under **Build and deployment → Source**, choose **Deploy from a branch**.
4. Under **Branch**, choose **main** and **/(root)**. Click **Save**.
5. Wait about a minute. Refresh the page. A box appears at the top: **"Your site is live at …"**. Click **Visit site**.

✅ **You should see:** a dark page that says **"Your starter is live."** with your live link and a **Copy link** button.

Seeing a **404** page? That's normal for the first minute or two. Wait, then refresh. Still 404 after 5 minutes? See [Pages shows 404](docs/HELP.md#pages-shows-404).

### 1c · Save both links

Open a note (Notes, Google Docs, anything) and paste both links into it. You'll need them again.

| Link | How to get it | What it's for |
| --- | --- | --- |
| **Repo link** | On GitHub, click your repo name (`clone-wars`) at the top of the page, then copy the address bar. It must look exactly like `https://github.com/YOUR-USERNAME/clone-wars`, with **nothing after `clone-wars`**. If you copy it while you're on the Settings page, it ends in `/settings/pages`, which is wrong. | **Give this one to Codex.** |
| **Live link** | Copy it from the **Copy link** button on your starter page. It looks like `https://YOUR-USERNAME.github.io/clone-wars/` | **Submit this one to the portal.** Share it with friends. |

### 1d · Submit your live link to the portal now

Your live link stays the same forever, so you submit it now, before you build. When you merge later, the same link shows your finished game.

1. Open **[calpolyvibecoding.com/portal](https://calpolyvibecoding.com/portal)** and log in (or sign up).
2. Open **Builds**.
3. Under **Post this week's build**, paste your **live link** into **Link**. The `github.io` one, not the repo link.
4. In **What is it?**, write: `Clone Wars (Session 03). Building now.`
5. Click **Post it**.

✅ **You should see:** your entry in the Builds list.

> ### 🛑 STOP 1 · Live and submitted
>
> Your starter page opens at your own `github.io` link, and that link is in the portal. Don't go on until both are true.

---

## Step 2 · Make it yours

⏱️ **About 3 minutes**

Fill in your version. The team lead passes each line to the builder who needs it.

| Line | What to write | Who uses it |
| --- | --- | --- |
| **Title** | A name for your game, 30 characters max | Core builder |
| **Set in** | A place or a vibe. This becomes the background, obstacles and sounds. | Art and Sound builders |
| **I play as** | Your character | Art and Sound builders |
| **Better because** | Your fix. Pick one below, or write your own. | Core builder |

### Need ideas?

| Title | Set in | I play as |
| --- | --- | --- |
| Galaxy Flap | a desert planet with two suns, a space-station trench with laser gates as obstacles | a small starfighter |
| SLO Flap | San Luis Obispo at sunset, Bishop Peak in the back, palm trees as obstacles | a seagull |
| Big Apple Dash | New York City at night, skyscrapers as obstacles | a pigeon |
| Orbit | outer space, asteroids as obstacles | a tiny rocket |
| Farm Run | a Cal Poly farm field, hay bale stacks as obstacles | a chicken |
| Pismo Glide | Pismo Beach on a sunny day, pier posts as obstacles | a pelican |

Want to pick what the obstacles look like? Put it in your **Set in** line, like the examples. If you don't, the Art builder picks something that fits.

Keep it simple: bold shapes and silhouettes draw well. Tiny details (a specific logo, a real person, your apartment's exact couch) don't.

**Inspired by a movie or show? Go for the vibe, not the brand.** "A desert planet with two suns" and "a small starfighter" are great. Named characters, famous ships, logos and theme songs aren't allowed. No real people either.

### Pick your fix ("Better because")

The original game is famous for being brutally hard. Pick one way to make yours better:

| Write this | What it does |
| --- | --- |
| **Easy mode** | Easy and Normal buttons on the start screen. Easy has bigger gaps and slower obstacles. |
| **Gentle start** | The first three obstacles have bigger gaps and move slower, so you don't die in two seconds. |
| **Checkpoints** | Every 10 points is a checkpoint. After a crash, you start again from your last checkpoint, not from zero. |
| **Your own idea** | Describe it in one sentence. The Core builder will try it. Custom fixes are riskier and aren't in the answer key. |

✅ **You should see:** your four lines written down, ready to paste in Step 3.

---

## Step 3 · Brief your team

⏱️ **About 4 minutes, including waiting for the plan**

### The one idea behind today (30-second read)

Three builders can work at the same time only if they **agree on names before they start**. The game will call `drawBird` to draw your character. The Art builder writes a `drawBird` that draws a seagull. The Core builder writes a game that calls `drawBird`. They never talk to each other. The shared names in `CONTRACT.md` are why their parts fit.

**What can't be split:** the crash check. Every moment, the game asks "is the bird touching a pipe?" That needs the bird **and** the pipes at the same time, so it stays with one builder (Core).

**Rule of thumb:** if two parts need each other every single moment, keep them together. If one only needs the other's name, split them.

### Brief them

1. In Codex, start a **new** chat with GitHub available. <!-- CONFIRM after Kyle's test: exact button to start a chat on your repo. -->
2. Make sure **GPT-5.6 Luna** is selected.
3. Click the **copy icon** (two squares) at the top right of the gray prompt box below.
4. Paste it into your **note** from Step 1c, not straight into Codex. (In Codex, pressing Enter sends the message before you're done.)
5. In your note, replace everything in **[square brackets]** with your **repo link** (the `github.com` one from your note, ending in `/clone-wars`) and your four lines from Step 2. Delete the brackets and the words inside them.
6. Copy the finished prompt from your note, paste it into Codex, and send it.

```text
You are the orchestrator for my Clone Wars build. You lead a team of
three subagents.

My repo: [paste your REPO link, the github.com one]

My version:
- Title: [your title]
- Set in: [a place or vibe]
- I play as: [your character]
- Better because: [easy mode, gentle start, checkpoints, or your own idea]

Part 1. Plan, then stop.
Read AGENTS.md and CONTRACT.md in my repo. Change nothing yet.
Follow AGENTS.md Part A, Step 1: tell me the plan in plain words,
then stop and wait until I type go.

Part 2. When I type go.
Follow AGENTS.md Part A, Steps 2 to 4: make the branch
clone-wars-build, start all three subagents at the same time on
gpt-5.6-luna, check their work, and open one pull request.
Do not merge.
```

The team lead replies with a plan. **Before you type go, check three things:**

- [ ] **Three jobs:** Core (`game.js`, `config.js`), Art (`sprites.js`), Sound (`sounds.js`).
- [ ] **Your version is in it:** your title, your place, your character, your fix.
- [ ] **It names the part that can't be split:** the crash check stays with Core.

Something's off? Tell it what to change in plain words. Otherwise type:

```text
go
```

✅ **You should see:** a plan with three jobs and your version in it. After you type **go**, a message saying it's starting the three jobs. The exact words vary, and that's fine.

---

## Step 4 · Watch your team build

⏱️ **About 5 to 10 minutes.** The agents do the work. You watch and learn.

While the builders work:

- **Look for three subagents running at the same time.** Depending on your Codex app, they show up as separate threads, a list of agents, or updates in the main chat. <!-- CONFIRM after Kyle's test: exactly where subagent threads appear. -->
- **Notice what each one is doing.** Core is writing the rules of the game. Art is drawing your world. Sound is making your beeps. None of them is waiting for the others.
- **Test yourself while you wait.** Without scrolling up: why can the Art builder work at the same time as the Core builder? And what's the one part that couldn't be split, and why? You'll write your answer in Step 6. (Stuck? Reread [the one idea](#the-one-idea-behind-today-30-second-read).)

> **Codex says you hit your usage limit?** Stop here. Nothing is lost: your live link is already in the portal. Watch a neighbor's build, then finish yours after the meeting. See [I ran out of usage](docs/HELP.md#i-ran-out-of-usage).
>
> **Came from the setup table and your team isn't running yet?** Sit with a neighbor whose build is running. Ask them to show you their plan, their subagents and their pull request. Start your own after the meeting with this page.

When the team lead finishes, it gives you a **pull request link**.

- No link? Look for a **Create PR** button in the chat, or a yellow **Compare & pull request** banner on your GitHub repo page.
- It says subagents weren't available and it did the jobs one at a time? That's fine. Same game, it just took longer.

✅ **You should see:** a message from the team lead with a pull request link and a summary of who built what.

---

## Step 5 · Check the work, merge, play

⏱️ **About 8 minutes**

### 5a · Check the pull request

1. Open the pull request link (or go to your repo and click **Pull requests**, then **Clone Wars: [your title]**).
2. Read the description: who built what, and the part that couldn't be split.
3. Click the **Files changed** tab. This first pull request should show **4 files**: `config.js`, `game.js`, `sounds.js`, `sprites.js`.
   - More than those four, or other names? Don't merge. Tell your team lead: "Put back every file except the four build files."
   - Later pull requests (a fix or the answer key) change **fewer** files, usually just one. That's normal.
   - You don't need to understand the code. You're checking that the right files changed, and nothing else.
4. **Check that your team really worked at the same time.** In the description's **Who built what** table, look at the **Started** times. All three within a minute or so of each other means three subagents ran in parallel. If it says **one after another**, subagents weren't available in your Codex app. You get the same game, just slower.

### 5b · Merge

1. Go back to the **Conversation** tab.
2. Click **Merge pull request**, then **Confirm merge**.

✅ **You should see:** a purple **Merged** badge.

### 5c · Wait for your live link to update

1. Click the **Actions** tab in your repo.
2. Wait for the newest run to show a **green check** (about 1 to 2 minutes). A yellow dot means it's still running.
3. Open your **live link** and do a **hard refresh**: **Cmd+Shift+R** on Mac, **Ctrl+Shift+R** on Windows. A normal refresh can keep showing the old starter page for a few minutes.

### 5d · Play it. Don't trust "done."

The agent said it's done. That doesn't mean it works. Check each one:

- [ ] Your title shows on the start screen.
- [ ] Space, click or tap starts the game and flaps.
- [ ] Obstacles come at you, and you score by passing them.
- [ ] Hitting an obstacle or the ground ends the game and shows your score.
- [ ] You can play again.
- [ ] It looks like **your** place and **your** character. You can clearly see the character and obstacles.
- [ ] You hear sounds. **M** turns them off and on.
- [ ] Your fix is there:
  - **Easy mode:** **Easy** and **Normal** buttons on the start screen. Easy has bigger gaps.
  - **Gentle start:** the first three gaps are clearly bigger than the ones after.
  - **Checkpoints:** reach 10 points, crash, and Game over says "Next game starts at checkpoint 10." Can't reach 10 in a couple of tries? Skip this box.
  - **Your own idea:** check whatever you asked for.

✅ **You should see:** your game, playing, at your own link.

### Something's broken?

Work down this list. **Don't spend more than one fix try.** That's what the answer key is for.

**1. A small yellow label at the bottom says `placeholder: ... missing`.**
A name doesn't match `CONTRACT.md`, so that part isn't plugging in. Go to 2.

**2. One fix try.** In the same chat, type `fix it:` and describe what you saw:

```text
fix it: [describe what's wrong, like "the game never starts when I press
Space" or "the pipes are the same color as the sky so I can't see them"]
```

The team lead makes a new pull request. Open it and check **Files changed**: a fix usually changes just 1 or 2 files, and that's fine. Merge it (same as 5b), wait for Actions, hard refresh, and play again.

**3. Still broken? Use the answer key.** The club has a working copy of `game.js`, the core of the game. It follows the same plan as yours, so your art, sound, title and fix (from the list) still plug in. In the same chat, type:

```text
use the answer key
```

Open the new pull request. **Files changed** should show `game.js`, and maybe `config.js`. Nothing else. Merge it, wait for Actions, hard refresh, and play.

> Using the answer key isn't cheating. Real engineers use a working reference all the time. The skill was **noticing** it was broken and **deciding** what to do.

Can't get the agent to swap it? See [Use the answer key by hand](docs/HELP.md#use-the-answer-key-by-hand).

> ### 🛑 STOP 2 · Live and playable
>
> Your game plays at your own live link, and it looks like your version.

---

## Step 6 · Update your portal entry

⏱️ **About 3 minutes**

1. Open **[calpolyvibecoding.com/portal](https://calpolyvibecoding.com/portal)** and go to **Builds**.
2. Find your Clone Wars entry and edit it. <!-- CONFIRM: exact name of the edit button in the portal. -->
3. Replace **What is it?** with one line in this shape:

```text
[Your title]: a Flappy Bird-style clone set in [place]. My fix: [fix]. The part that couldn't be split was [your answer, in your own words].
```

   For example:

   > SLO Flap: a Flappy Bird-style clone set in San Luis Obispo at sunset. My fix: easy mode. The part that couldn't be split was the crash check, because it has to know where the bird and the pipes are at the same moment.

4. Save.

✅ **You should see:** your entry with the new description, still pointing at your live link.

> ### 🛑 STOP 3 · Shipped
>
> Your game is live, it's yours, and the portal has your link and your one-line explanation.

---

## What you practiced

| Track | What you did today |
| --- | --- |
| **Orchestration** | You directed a team lead and three builders working at the same time, and approved one combined result. |
| **Context** | One written plan (`CONTRACT.md`) let agents that never talked to each other build parts that fit. |
| **Judgment** | You checked the plan before "go", checked which files changed, played the game instead of trusting "done", and decided whether to fix or use the answer key. |
| **Evidence** | A live link anyone can play, and one line explaining what couldn't be split. |
| **Capability** | Agents that read your repo, write files, and open pull requests for you. |

**The Loop:** spec → build → test → deploy → iterate.

The finished game is plain HTML and JavaScript. No AI runs when someone plays it. AI helped you **build** it.

---

## Keep going (after the meeting)

- **Try a custom fix.** Start a new chat, point it at your repo, and describe a new feature. Ask it to follow `CONTRACT.md` and open a pull request.
- **Push your art further.** Ask for more detail in `sprites.js`: a moving skyline, day turning into night.

## Build your own clone (after you finish)

Want to clone something other than Flappy Bird? Use the same method on your own.

**Before you start:**
- **This isn't supported during the meeting.** There's no answer key, and officers can't help with it. Finish your Flappy Bird first.
- **Keep it to one screen and one thing to do.** A Wordle board, a Snake game, one Duolingo lesson. Not "all of Spotify."
- Same rules as today: plain HTML and JavaScript, no web addresses, no API keys, no brands.

**1. Make a new repo.** On GitHub, click **+** (top right) → **New repository**. Name it (like `my-clone`), choose **Public**, check **Add a README file**, and click **Create repository**.

**2. Brief a new team.** Start a new Codex chat on **GPT-5.6 Luna**. Fill in the brackets in your note first, then paste:

```text
You are the orchestrator for a new clone. You lead three subagents.
My repo: [paste the new repo link]

I want to clone: [one screen of an app or game, like "a Wordle board"]
My version: [how you want it to look and feel]
Better because: [one fix]

Part 1. Plan, then stop.
Split this into exactly three jobs that can run at the same time.
Give each job its own files. Draft a CONTRACT.md: the exact names the
three parts share, and the one part that can't be split, and why.
Show me the plan and wait until I type go.

Part 2. When I type go.
On a branch named clone-build, save CONTRACT.md and an index.html
that loads every file. Start all three subagents at the same time on
gpt-5.6-luna, one per job. Each reads CONTRACT.md and touches only its
own files. Plain HTML, CSS and JavaScript only: no frameworks, no web
addresses, no API keys, no logos or brands. Check that the parts fit,
then open one pull request with who built what and when each started
and finished. Do not merge.
```

**3. Check the plan before you type go.** It's the same skill as today:
- [ ] Three jobs, and each one has **different files**.
- [ ] The names they share are written down.
- [ ] It names the part that can't be split.
- [ ] **The real test:** does any job need another job's *code* to exist first, not just its *names*? If yes, those jobs aren't really parallel. Tell it: "Job [X] depends on job [Y]. Re-split so the three jobs only share names."

**4. Merge, go live, play.** Check **Files changed** and merge. Then turn on Pages (**Settings → Pages → Deploy from a branch → main → /(root) → Save**), wait for the green check in **Actions**, and open your live link.

Need help? [docs/HELP.md](docs/HELP.md)

# AGENTS.md · Rules for every agent in this repo

This repo is a Clone Wars build for Cal Poly Vibe Coding Club. A beginner (the **member**) directs a team: one **orchestrator** agent leads three **subagents** that build three parts of a game at the same time.

- If the member pasted the orchestrator prompt to you, you are the **orchestrator**. Read Part A.
- If the orchestrator started you with a job, you are a **subagent**. Read Part B.
- Everyone follows Part C.

The member is new to all of this. Talk in plain words. Short sentences. No jargon without a one-line explanation.

---

## Part A · The orchestrator

You lead. You plan, start the subagents, check their work and open one pull request. **You do not write `game.js`, `config.js`, `sprites.js` or `sounds.js` yourself** (the only exception is fallback 1 below).

### Step 1 · Plan, then stop

1. Read `CONTRACT.md` and this file. Change nothing.
2. Check the member's **My version** block. If Title, Set in, I play as or Better because is blank or still has square brackets like `[a place or vibe]`, stop and ask the member to fill it in. Don't guess.
3. Reply with the plan in this exact shape, filled in with their version:

   > **Here's the plan for [Title].**
   >
   > **Three jobs that can run at the same time:**
   > 1. **Core** builds `game.js` and `config.js`: the game rules, the title "[Title]" and your fix: [Better because].
   > 2. **Art** builds `sprites.js`: [Set in] as the background, and you play as [I play as].
   > 3. **Sound** builds `sounds.js`: flap, score and crash sounds that fit [Set in].
   >
   > **Why they don't collide:** each job makes different files. They only share names from `CONTRACT.md`, like `drawBird` and `flap`.
   >
   > **The part that can't be split:** the crash check. It needs the bird and the pipes at the same moment, so the whole game loop stays with Core.
   >
   > Type **go** to start all three at once.

4. **Stop.** Do nothing else until the member types `go`.

### Step 2 · When the member types `go`

1. Create a branch named `clone-wars-build` from `main`.
2. **Start all three subagents at the same time.** Do not wait for one to finish before starting the next. Use the model `gpt-5.6-luna` for every subagent. If that model isn't available, use the cheapest, fastest model you can.
3. Give each subagent exactly this, and nothing else:
   - "You are the [Core / Art / Sound] subagent. Read `AGENTS.md` Part B and Part C, and `CONTRACT.md`, in [repo], on branch `clone-wars-build`."
   - Its job section from Part B below, copied word for word.
   - The My version lines it uses (see the table in Part B).
4. Tell the member: "Three subagents are working at the same time now. This takes a few minutes." If your app shows subagent threads, tell the member where to see them.
5. Don't write any of their files while they work.

### Step 3 · Check the work

When all three subagents are done:

1. Confirm the branch changed **only** `game.js`, `config.js`, `sprites.js` and `sounds.js`. If any other file changed, put it back the way it is on `main`.
2. Compare each file against its section of `CONTRACT.md`. Look hardest at the names: `GAME_CONFIG`, `SPRITES`, `SOUNDS`, `drawBackground`, `drawGround`, `drawBird`, `drawPipe`, `flap`, `score`, `crash`. One wrong letter and that part won't plug in.
3. If you can run commands, run `node tests/check.cjs` and keep the result for the pull request.
4. If one subagent failed, or its file breaks a rule, start **one fresh subagent** for that job only, with the same instructions plus one sentence saying what was wrong. Do this **once**. Don't fix its code yourself. If it fails again, say so in the pull request.

### Step 4 · Open one pull request

1. Open a pull request from `clone-wars-build` to `main`. Title: `Clone Wars: [Title]`
2. Use this description:

   ```
   ## My version
   Title: ...  |  Set in: ...  |  I play as: ...  |  Better because: ...

   ## Who built what
   How they ran: [at the same time, as subagents] OR [one after another, because subagents weren't available]
   | Subagent | Files | Started | Finished | What it made |
   | Core  | game.js, config.js | 12:36:05 | 12:39:40 | ... |
   | Art   | sprites.js | 12:36:06 | 12:38:10 | ... |
   | Sound | sounds.js | 12:36:06 | 12:37:30 | ... |
   (Use the real clock times each subagent actually started and finished. Never make them up. If you can't see exact times, write "not shown".)

   ## The part that couldn't be split
   The crash check, because it needs the bird and the pipes at the same moment.

   ## Checks
   (result of node tests/check.cjs, or "not run")

   ## Not tested
   (anything you couldn't check. Say plainly: the member still has to play it.)
   ```

3. **Do not merge.** The member merges.
4. Tell the member: the pull request link, "It should show 4 files changed," and "Next: follow Step 5 in README.md."

### Fallbacks

1. **You can't start subagents here.** Do the three jobs yourself, **one after another**: Core, then Art, then Sound, following each job section exactly. Tell the member: "Subagents aren't available here, so I did the three jobs one at a time. Same result, just slower."
2. **Subagents can't save to the branch at the same time** (errors about the branch being changed or out of date). Have each subagent send you its finished file instead, then you save all four files to `clone-wars-build` yourself.
3. **You can't create a pull request.** Tell the member the branch name and that there's a **Create PR** button in the chat, or a **Compare & pull request** button on their GitHub repo page.

### When the member is stuck and asks for help

Members are told to ask you first, before an officer. You can see their situation better than anyone in the room.

1. Read `README.md` and `docs/HELP.md` if you haven't.
2. Find the step they're on. If they didn't say, ask one short question.
3. Answer with **one small action at a time**: exactly what to click or type, using the button names from the README. Wait for them to say it worked before giving the next action.
4. If `docs/HELP.md` covers their problem, follow it, and tell them which section it came from.
5. Don't change any files while helping unless they ask you to.
6. If it needs an account, permission or portal fix you can't do, say: "This one needs an officer."

### When the member's build stopped because they ran out of usage

1. Look for work that already exists: a `clone-wars-build` branch, an open pull request, or files in the chat.
2. Keep every finished build file that follows `CONTRACT.md`. Start fresh subagents only for the missing ones (Part A, Step 2), then do Steps 3 and 4.
3. If nothing was saved, start again from Part A, Step 1.

### When the member types "fix it"

The member played the game and something is wrong. They'll describe it.

1. Work on a new branch named `clone-wars-fix` from `main`.
2. Decide which file the problem is in: how it plays is `game.js`, the numbers are `config.js`, how it looks is `sprites.js`, how it sounds is `sounds.js`.
3. Fix only that. Keep every `CONTRACT.md` name the same.
4. Open a pull request titled `Fix: [what was wrong]`. Don't merge. Tell the member to merge it and play again.
5. This is the member's **one** fix try. If it's still broken, tell them to use the answer key.

### When the member types "use the answer key"

1. Work on a new branch named `answer-key` from `main`.
2. Read `game.js` from the public repo **https://github.com/KyleStefan/clone-wars-answer-key** (branch `main`).
3. Replace the member's `game.js` with it, **unchanged, every line.**
4. Look at `fix` in the member's `config.js`. If it's `'easy-mode'`, `'gentle-start'`, `'checkpoints'` or `'none'`, leave it. If it's `'custom'`, change it to `'none'` and tell the member: "The answer key doesn't include your custom fix, so it's turned off. Your title, art and sound are still yours."
5. Don't touch `sprites.js` or `sounds.js`.
6. Open a pull request titled `Use the answer key`. Don't merge. Tell the member to merge it and play again.

If you can't read the other repo, tell the member to follow **Use the answer key by hand** in `docs/HELP.md`.

---

## Part B · The subagents

| Subagent | Your files (create or change only these) | My version lines you use |
| --- | --- | --- |
| **Core** | `game.js`, `config.js` | Title, Better because |
| **Art** | `sprites.js` | Set in, I play as |
| **Sound** | `sounds.js` | Set in, I play as |

Work on the branch `clone-wars-build`. The other two subagents are working at the same time. You will not see their files, and they may not exist yet. **That is normal. Never create another subagent's files.** Trust `CONTRACT.md`.

### Core subagent job

1. Read `CONTRACT.md` sections 1, 4 and 5 all the way through.
2. Create `config.js`: set `window.GAME_CONFIG` with every name in the Settings table. `title` is the member's Title. `fix` comes from Better because, using the table in section 1. Keep the Normal values unless the member's fix says otherwise.
3. Create `game.js`: build the game so it checks **every box** in section 4. **Where a box shows code, copy that code exactly.** Build the fix from section 5 that matches `fix`.
4. Before you finish, reread section 4 one box at a time. Fix any box you missed.
5. Commit both files to `clone-wars-build`. Report back: the files, the fix you built, and anything you're unsure about.

### Art subagent job

1. Read `CONTRACT.md` section 2 all the way through.
2. Create `sprites.js`: set `window.SPRITES` with the four drawing functions, exact names and inputs.
   - `drawBackground` and `drawGround`: the member's **Set in**. Simple, bold shapes and silhouettes, not tiny details.
   - `drawBird`: the member's **I play as**, fitting in the `size` box.
   - `drawPipe`: obstacles that fit **Set in** (skyscrapers, palm trees, asteroids). They must fill exactly the pipe rectangles.
3. Check readability: the character and obstacles need dark outlines and colors that stand out from the sky.
4. Commit `sprites.js` to `clone-wars-build`. Report back: what the scene, character and obstacles look like.

### Sound subagent job

1. Read `CONTRACT.md` section 3 all the way through.
2. Create `sounds.js`: set `window.SOUNDS` with `flap`, `score` and `crash`, using the exact `getAudio` helper. Make each sound fit the member's **Set in** and **I play as**.
3. Keep every sound under 0.5 seconds and quiet (gain 0.2 or less).
4. Commit `sounds.js` to `clone-wars-build`. Report back: what each sound is like.

---

## Part C · Rules for everyone

- **Stay in your files.** Never edit `index.html`, `README.md`, `CONTRACT.md`, `AGENTS.md`, `docs/`, `tests/`, `.nojekyll`, or another agent's files.
- **Use the `CONTRACT.md` names exactly:** same spelling, same capital letters, same inputs in the same order.
- **Plain files only.** Classic scripts that set `window` globals. No `import`, `export`, modules, frameworks, packages or build steps.
- **Nothing from the internet.** No `fetch`, no web addresses, no API keys, no image files, no audio files, no web fonts.
- **No `innerHTML`.** Use `textContent`.
- **No brands or real people.** Don't use the words "Flappy Bird", logos, or real people's names or faces. If "Set in" or "I play as" names a movie, show or game, match the vibe with original designs: no named characters, famous ships, logos or theme songs.
- **Never merge.** The member merges.
- **Never read or copy the answer key** unless the member typed "use the answer key".
- **If something is unclear, stop and ask.** Don't guess.

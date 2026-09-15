# Help · Clone Wars

Something not working? Find your problem below. Button names move around as apps update, so if a label doesn't match exactly, look for the closest one.

**Before anything else, ask your AI.** It can see your exact screen and error. An officer can't. Give it the tutorial and this page, and ask. Use Codex, Claude Code, or ChatGPT (even on your phone if your laptop isn't set up):

```text
I'm a beginner following this tutorial: [paste the link to your repo's README page]
and its help page: [paste the link to this page]
Read both first.

I'm on Step [number]. Here's what I see: [describe it, or paste the exact error]
I'm using: [Mac or Windows], [Chrome, Safari or Edge], [Codex, Claude Code or ChatGPT]

Tell me exactly what to click or type next, one small step at a time.
Assume I've never used GitHub or coding tools before.
```

Attach a screenshot if you can (Mac: **Cmd+Shift+4**. Windows: **Windows key+Shift+S**).

**Jump to:**
[Codex setup](#codex-setup) ·
[Wrong repo](#codex-is-working-in-the-wrong-repo) ·
[Pages shows 404](#pages-shows-404) ·
[Portal](#portal-problems) ·
[Plan didn't stop](#the-team-lead-didnt-stop-to-show-me-the-plan) ·
[No subagents](#it-says-subagents-arent-available) ·
[Out of usage](#i-ran-out-of-usage) ·
[No pull request](#i-dont-have-a-pull-request) ·
[Wrong files changed](#the-pull-request-changed-more-than-4-files) ·
[Placeholder label](#a-yellow-label-says-placeholder--missing) ·
[Blank or unplayable](#blank-screen-or-the-game-wont-start) ·
[Can't see things](#i-cant-see-my-character-or-the-obstacles) ·
[No sound](#no-sound) ·
[Answer key by hand](#use-the-answer-key-by-hand) ·
[Undo a merge](#undo-a-merge-with-revert)

---

## Codex setup

These four ate the most time last session.

**The student offer won't work with my school email.**
Sign up with a **personal** email (like Gmail). The `calpoly.edu` sign-up fails without telling you why. If the offer page keeps bouncing you, open a private window (**Cmd+Shift+N** on Mac in Chrome or Safari; **Ctrl+Shift+N** on Windows in Chrome, or Edge's InPrivate window), go to the offer page, sign in there with your personal email, then go back to a normal window.

**I'm signed into the school Codex account.**
Sign out and sign in with your personal account. The school account can't use the GitHub connector.

**Codex says it can't see my repo.**
The GitHub connector needs permission to see your repositories.
1. On GitHub, click your profile picture → **Settings** → **Applications** (left sidebar) → **Installed GitHub Apps**.
2. Find the ChatGPT / Codex app and click **Configure**.
3. Under **Repository access**, choose **All repositories**, or add your `clone-wars` repo. Save.
4. Start a **new** chat in Codex and try again.

This works any time, including if you skipped the question or picked "Only select repositories" when you installed it. The app isn't in that list at all? The connector was never installed. Install it from Codex first.

**I can't find GPT-5.6 Luna.**
Pick the cheapest, fastest model in the list. Avoid the biggest one; it uses your allowance several times faster.

---

## Codex is working in the wrong repo

The link you gave it must have **your** username: `https://github.com/YOUR-USERNAME/clone-wars`. If it has `KyleStefan`, that's the club's template, which you can't change. Start a new chat and paste your own repo link.

---

## Pages shows 404

A 404 is normal for the first 1 to 2 minutes after turning Pages on or merging.

1. In your repo, click **Actions**. Wait for the newest run to show a green check.
2. Open **Settings → Pages**. It should say **Deploy from a branch**, **main**, **/(root)**.
3. Use the exact link shown at the top of **Settings → Pages**. It ends with your repo name and a `/`.
4. Your repo must be **Public**. (Settings → General → scroll to the bottom → Danger Zone → Change visibility.)
5. `index.html` must be at the top level of your repo, not inside a folder.

---

## Portal problems

- **I pasted the wrong link.** The portal needs the `github.io` live link, not the `github.com` repo link. Edit your entry and fix it.
- **I can't log in or the post fails.** Ask an officer. Keep building in the meantime.
- **I already posted. Do I post again after I merge?** No. Your live link doesn't change, so your entry already points at your finished game. Just edit the description in Step 6.

---

## The team lead didn't stop to show me the plan

It should stop and wait for **go**. If it started building right away, let it finish, then check the pull request carefully in Step 5. Next time, make sure you pasted the whole prompt, including "Part 1. Plan, then stop."

---

## It says subagents aren't available

Some versions of Codex can't start subagents. The team lead does the three jobs one after another instead. You get the same game, it just takes longer. The lesson still holds: the three jobs **could** have run at the same time because they only share names.

If it didn't fall back on its own, type:

```text
Subagents aren't available. Do the Core, Art and Sound jobs yourself,
one after another, following AGENTS.md. Then open one pull request.
```

---

## I ran out of usage

Codex says you hit your limit, and it won't answer anymore. **You're done building for today, and nothing is lost.**

- **Your link already counts.** You submitted your live link in Step 1, so it's in the portal.
- **Keep learning now.** Sit with a neighbor whose build is running. Ask them to show you their plan, their subagents, their pull request and their game.
- **Finish later.** After the meeting, finish at home with the README and this page. There are two limits: a short one that resets within a few hours, and a weekly one that can take days. Codex tells you when you can use it again.
- **When your limit resets,** open the same chat (or a new one with your repo link) and type:

  ```text
  Read AGENTS.md in my repo. My Clone Wars build stopped because I ran out
  of usage. Check what's already finished, on any branch or pull request.
  Finish only what's missing, then open one pull request. Don't merge.
  ```

  If nothing was saved, it starts over from Step 3. That's fine.
- **Next time:** make sure **GPT-5.6 Luna** (or the cheapest model) is selected before you start. Bigger models use your limit several times faster.

---

## I don't have a pull request

- Look for a **Create PR** button in the Codex chat.
- Or open your repo on GitHub. A yellow banner may say **clone-wars-build had recent pushes** with a **Compare & pull request** button. Click it, then **Create pull request**.
- Or click **Pull requests → New pull request**, set **compare** to `clone-wars-build`, and click **Create pull request**.

---

## The pull request changed more than 4 files

Don't merge. Type in the chat:

```text
The pull request changed files other than game.js, config.js, sprites.js
and sounds.js. Put every other file back exactly as it is on main.
```

Check **Files changed** again before merging.

---

## A yellow label says `placeholder: ... missing`

The label names the parts that didn't plug in.

| Label says | What it means | What to type |
| --- | --- | --- |
| `settings` | `config.js` is missing or doesn't set `window.GAME_CONFIG` | `fix it: config.js isn't setting window.GAME_CONFIG. Check it against CONTRACT.md section 1.` |
| `art`, or names like `drawBird` | `sprites.js` is missing or a function name is misspelled | `fix it: the label says [paste the label]. Fix sprites.js so the names match CONTRACT.md section 2 exactly.` |
| `sound`, or names like `flap` | `sounds.js` is missing or a function name is misspelled | `fix it: the label says [paste the label]. Fix sounds.js so the names match CONTRACT.md section 3 exactly.` |
| a setting name like `pipeGap` | `config.js` is missing that setting | `fix it: config.js is missing [name]. Add it using CONTRACT.md section 1.` |

---

## Blank screen, or the game won't start

That's the Core builder's file, `game.js`, the part most likely to break.

1. **One fix try.** Type `fix it:` and describe exactly what you see. For example: "fix it: the start screen shows but pressing Space does nothing."
2. **Still broken?** Type `use the answer key`. Merge the new pull request and play again.

Still showing "Your starter is live." after merging? First do a **hard refresh** (**Cmd+Shift+R** on Mac, **Ctrl+Shift+R** on Windows). A normal refresh can show the old page for a few minutes. Still the starter? Then `game.js` didn't load. Check that the pull request included `game.js` and that Actions shows a green check.

---

## I can't see my character or the obstacles

The art is too close to the background color. Type:

```text
fix it: I can't see the [character / obstacles] against the background.
Make them stand out with brighter colors and a dark outline, following
CONTRACT.md section 2.
```

This is one of the most common art bugs. Nice catch.

---

## No sound

- Press **M** once. Sound may be off.
- Click or press Space first. Browsers don't allow sound until you interact with the page.
- Check your computer's volume, and that the browser tab isn't muted.
- Still nothing? `fix it: I hear no sound. Check sounds.js against CONTRACT.md section 3.`

---

## Use the answer key by hand

If the agent can't swap it for you:

1. Open the answer key: **https://github.com/KyleStefan/clone-wars-answer-key/blob/main/game.js**
2. Click the **Copy raw file** button (two overlapping squares, top right of the file).
3. In **your** repo, click `game.js`, then the **pencil icon** (Edit this file).
4. Select everything in the editor (Cmd+A on Mac, Ctrl+A on Windows) and paste.
5. Click **Commit changes** → leave **Commit directly to the main branch** selected → **Commit changes**.
6. If you wrote your own custom fix: open `config.js`, click the pencil, change `fix: 'custom'` to `fix: 'none'`, and commit.
7. Wait for **Actions** to show a green check, then play.

---

## Undo a merge with Revert

Merged something that made it worse?

1. Click **Pull requests → Closed**, and open the pull request you merged.
2. Near the bottom, click **Revert**. This makes a new pull request that undoes it.
3. Click **Merge pull request → Confirm merge**.
4. Wait for Actions, then refresh your live link.

---

## Ask an officer when

- the portal won't accept your post;
- your repo is owned by the wrong account or organization;
- GitHub asks for permissions you don't understand;
- the answer key is merged and the game still doesn't work.

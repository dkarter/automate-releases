theme: Scherzkeks-improved

# Automate Everything

![](./all-the-things.png)

---

# Our tooling should serve us

- Reduce time to market
- Reduce development time
- Minimize toil
- Focus on the important stuff
- Make it easy to know what changed and why
- Reduce human error

^ the important stuff is business logic, developing the product etc

---

# What can we do

- Automate release branches
- Automate versioning
- Automate changelog updates
- Automate GitHub releases

---

![](./automate.gif)

---

# Release Please

- Project by Google
- Integrates with Github Actions (minimal config)
- Supports Elixir and JavaScript

---

# Demo Time

---

![inline](./release-demo.mp4)

---

# How can we get there

---

# 🧐

^ some people might be curious

---

# 😁

^  and perhaps excited about change

---

# 😟

^
but others not so much
Change is hard, I get it.
It will take some time to get used to, and will take some buy in from the team

---

# 😌

^ 
but once you get used to it, it will be hard doing it any other way
it totally pays for itself in the long-run
so please hear me out on this
the goal is to improve DX at the end of the day


---

# Conventional Commits

> The Conventional Commits specification is a lightweight convention on top of commit messages. It provides an easy set of rules for creating an explicit commit history; **which makes it easier to write automated tools on top of.**

---

> This convention dovetails with **SemVer**, by describing the **features**, **fixes**, and **breaking changes** made in commit messages.

---

# Commit Message Structure

[.code-highlight: none]
[.code-highlight: 1]
```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

---

# Examples

```
feat: adds v4 UUID to crypto

This adds support for v4 UUIDs to the library.

fix(utils): unicode no longer throws exception
  PiperOrigin-RevId: 345559154
  BREAKING-CHANGE: encode method no longer throws.
  Source-Link: googleapis/googleapis@5e0dcb2

feat(utils): update encode to support unicode
  PiperOrigin-RevId: 345559182
  Source-Link: googleapis/googleapis@e5eef86
```

---

# Commit Types

There are multiple commit types, but here are the main ones:

[.build-lists: true]
- **fix:** patches a bug -> SemVer **`PATCH`**
- **feat:** introduces a new feature -> SemVer **`MINOR`**
- **feat!:** / **fix!:** breaking change -> SemVer **`MAJOR`**

---

# Other Types

```
build:, chore:, ci:, docs:, style:, refactor:, perf:, test:
```

Don't affect versioning... (unless you add a `!`, e.g. `refactor!:`)

---

# But my commits contain all kinds of stuff

---

# Mindset shift

[.text: alignment(left)]
Git is your friend. Especially when it comes to tracking down a change that introduced a bug.

You want to know:
- What changed
- Why it changed
- What are the implications to users

---

# Small, Atomic Commits

Commits only change one small thing and are easy to revert.

---

# It gets easier with time

The more you do it the easier it becomes and there are tools out there that help make this very easy

---

# How

[.text: alignment(left)]
❌ Instead of

```bash
git add --all
```

✅ Use `--patch`

```bash
git add -p
```

^ (or stage individual changes in VSCode if that's what you prefer)

---

![center inline autoplay](./gap-demo.mp4)

^
same tools available in VSCode

---

# Husky + Commitlint

Will help integrate conventional commits into our workflow by letting you know after committing if the commit doesn't match the spec.

---

# Resources (links)

- [Conventional Commits Spec](https://www.conventionalcommits.org/en/v1.0.0/)
- [Husky + Commitlint setup](https://nodecodestack.com/how-to-set-husky-with-commitlint-in-monorepo/)
- [Release Please release automation](https://github.com/googleapis/release-please)
- [Release Please GH Action](https://github.com/google-github-actions/release-please-action)
- [git add --patch docs](https://git-scm.com/docs/git-add#Documentation/git-add.txt---patch)
- [conventional commits plugin for VSCode](https://www.tderflinger.com/en/conventional-commits-vscode)

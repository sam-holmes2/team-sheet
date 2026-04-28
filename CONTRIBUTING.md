# Contributing to team-sheet

Thanks for taking an interest. This is a solo side project and contributions are welcome, but please read this first so we don't waste each other's time.

---

## A note on maintainership
This is my first time maintaining an open source project and I'm learning as I go. I don't have all the answers on process, conventions, or where this is headed. I'd rather be upfront about that than pretend otherwise.

If something feels off about how the project is run, a contribution wasn't handled well, or you have suggestions on how to improve things from a maintainer perspective, I genuinely want to hear it. Open an issue, start a discussion, or flag it directly.

I'll make mistakes, I'll try to fix them and hopefully we can all continue levelling up :)


## What kind of contributions are welcome

- **Bug fixes** - especially anything that breaks data import/export, localStorage, or the AI journalling workflow
- **Accessibility improvements**
- **Browser compatibility fixes**
- **Documentation corrections**
- **New features discussed in an issue first** - see below

## What to check before opening a PR

- The whole app is a single HTML file with no build step. Keep it that way.
- Test in at least Chrome and Firefox, including Firefox's local-file isolation behaviour.
- No new dependencies. No npm. No bundlers.
- Keep `instructions.md` in sync with any data model changes - the AI session workflow depends on it being accurate.


## For new features

Open an issue before writing code. New features need to stay coherent with the overall design - local-first, privacy-respecting, no backend, IFS-informed. If the idea doesn't fit that, a PR is unlikely to be merged no matter how well it's built.

## Opening an issue

Use [GitHub Issues](https://github.com/sam-holmes2/team-sheet/issues). For bugs, include:
- Browser and OS
- What you did, what you expected, what actually happened
- Any console errors

For feature requests, explain the problem you're trying to solve, not just the solution you have in mind.

## Code style

Match the existing style - vanilla JS, no classes for logic, terse variable names, CSS variables for theming. If you're unsure, just be consistent with whatever is around the code you're touching.

## Licence

By submitting a PR you agree that your contribution will be licensed under the same licence as the project (MIT).

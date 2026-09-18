# Contributing

This is the Contextator organisation's default guide. A repository that ships its own `CONTRIBUTING.md`
replaces it, and that one is the one to follow — it knows how to run its own code.

Read [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md) too, and note that a security problem does not go in an
issue: [`SECURITY.md`](SECURITY.md) says where it goes instead.

## Before you write code

**Open an issue first for anything bigger than a fix.** A pull request that changes observable behaviour
without an issue behind it usually ends in a discussion that would have been cheaper before the work.
A typo, a broken link, a wrong error message: just send it.

Say what problem you are solving and how you plan to solve it. Agreement on the second half is what saves
the time.

## The shape of a good pull request

- **One change per pull request.** A refactor bundled with a fix is two reviews pretending to be one.
- **The repository's own checks pass.** Every repository documents them in its README or `CONTRIBUTING.md`;
  running them before you push is most of staying green.
- **Tests come with behaviour.** A fix carries the test that fails without it.
- **Documentation comes with the change.** If the README, the wiki or the `.env.example` says something
  that your change makes untrue, it is part of your change to correct it.
- **The description says what and why.** The diff already says how.

Commits are written in the imperative — *"Add the retry"*, not *"Added"* or *"Adding"* — and the body
explains the reasoning that is not visible in the code.

## Licensing of what you send

The software in this organisation is free software under the **AGPL-3.0-or-later**, and a commercial
licence is offered alongside it. For both to stay possible, an outside contribution needs a **licence
grant** from its author before it can be merged; a repository that requires one documents it in its own
`CONTRIBUTING.md` or `CLA.md` and the check will tell you on your first pull request.

By contributing you confirm the work is yours to give and that you agree to it being released under that
repository's licence.

## Review

There is one maintainer. Review is usually a few days, sometimes longer, and a quiet pull request has not
been rejected — a ping on the thread is welcome after a week.

A change that is not merged is not a wasted one: the reason is written on the pull request, and it is
almost always about scope or timing rather than the work.

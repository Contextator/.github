# Security policy

This is the Contextator organisation's default policy. A repository that ships its own `SECURITY.md`
replaces it, and that one is the one to follow.

## Reporting a vulnerability

**Please do not open a public issue for a security problem.** An issue is readable by everybody the moment
it is filed, including by whoever would use it.

The intended route is GitHub's **private vulnerability reporting** on the affected repository: the
**Security** tab → *Report a vulnerability*. It opens a private thread between you and the maintainer, it
is free, and it needs no e-mail address from either side.

> **It is not switched on yet.** As of 2026-09-18 private vulnerability reporting is disabled on this
> organisation's repositories and only their owner can enable it (Settings → Security → Private
> vulnerability reporting). Until the Security tab offers *Report a vulnerability*, **contact the owner
> privately instead** — through [tunedness.com](https://tunedness.com), or any private channel you already
> have with them.
>
> <!-- OWNER: once private vulnerability reporting is enabled, delete this block. If you would rather
>      publish a security contact address, put it here instead — no address is published anywhere in
>      this organisation today, so none was invented for this file. -->

Whichever route you use, the useful report says: what an attacker can do, the smallest sequence of steps
that shows it, the version or commit you tested, and how the instance was deployed. A patch is welcome and
never required.

There is **no bug bounty**. You will get an acknowledgement, a fix or an explanation of why the behaviour
is intended, and credit in the release notes if you want it.

## What to expect

| | |
|---|---|
| First reply | Within a few days. There is one maintainer, not a rota. |
| While it is open | You hear what was reproduced, what the fix looks like, and when it lands. |
| Disclosure | After the fix is available, at a moment you agree with. An advisory is published on the affected repository. |

## Supported versions

Nothing in this organisation has reached a tagged release yet. The supported version is whatever is on the
default branch of the affected repository, and upgrading means pulling and rebuilding.

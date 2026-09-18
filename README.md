# `.github`

This repository is the [Contextator organisation](https://github.com/Contextator)'s profile and its
default community health files. There is no product code here — Contextator itself lives in
[Contextator/Contextator](https://github.com/Contextator/Contextator).

## What is in it

| Path | What GitHub does with it |
|------|--------------------------|
| [`profile/README.md`](profile/README.md) | Rendered on the organisation page at [github.com/Contextator](https://github.com/Contextator). |
| [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md) | The organisation's code of conduct, used by every repository that does not carry its own. |
| [`CONTRIBUTING.md`](CONTRIBUTING.md) | Shown when somebody opens an issue or a pull request, unless the repository has its own. |
| [`SECURITY.md`](SECURITY.md) | Rendered as the security policy of every repository without one. |
| [`SUPPORT.md`](SUPPORT.md) | Linked from the issue chooser as the place to ask a question. |
| [`.github/ISSUE_TEMPLATE/`](.github/ISSUE_TEMPLATE) | Default issue templates and the chooser's contact links. |
| [`.github/PULL_REQUEST_TEMPLATE.md`](.github/PULL_REQUEST_TEMPLATE.md) | The default pull request description. |

**A repository's own file always wins.** Nothing here overrides what a repository ships; these are the
fallbacks for the ones that ship nothing.

## Editing the profile

`profile/README.md` is plain Markdown rendered by GitHub with the same restrictions as any README: no
scripts, no styles, and a small allowlist of HTML. A change is live on the organisation page as soon as it
is on `main`, so read it once more before pushing — that page is the first thing most people see.

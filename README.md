# .github

The organization's shared GitHub metadata.

> ⚠️ **This repository must be named exactly `.github` on GitHub.** The local
> folder is called `eventa-.github` only so it is visible next to its siblings
> instead of hidden by the leading dot. Push it as `.github`:
>
> ```bash
> git remote add origin git@github.com:<org>/.github.git
> ```

## What is in here

| Path | Effect |
| --- | --- |
| `profile/README.md` | Renders on the organization's landing page at `github.com/<org>` |
| `repo-metadata.md` | The About text and topics for each repo — reference copy, see below |

## Why `repo-metadata.md` exists

A repository's **About** blurb and **topics** live in GitHub's settings, not in
any file, so they are invisible to code review and easy to let drift. Keeping the
intended text here means there is one place to check what each repo is supposed
to say, and one diff to review when it changes.

Applying it is manual (GitHub UI → the ⚙️ beside **About**), or scripted:

```bash
gh repo edit <org>/eventa-api \
  --description "…" \
  --add-topic nestjs --add-topic drizzle-orm
```

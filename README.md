# schmitech-fr.github.io

The public site at <https://schmitech-fr.github.io/>. It exists mainly to serve
the privacy policies that Google Play requires: a policy URL must be publicly
reachable and stay reachable for as long as the app is listed, and the app
repositories are private, so they cannot serve it themselves.

GitHub Pages publishes the default branch root automatically for a
`<owner>.github.io` repository — there is no workflow and no build step. A push
is live within a minute.

```
index.html                      https://schmitech-fr.github.io/
budget/privacy/index.html       https://schmitech-fr.github.io/budget/privacy/
mon-garage/privacy/index.html   https://schmitech-fr.github.io/mon-garage/privacy/
```

## Every page is in French and English

One page holds both languages, as two `<section>`s, and a switch shows one at a
time. It is plain CSS — `#en:target` plus `body:has(#en:target)` — so there is
no script and no second URL to keep in step. Where `:has()` is missing the
English section simply appears below the French one, which is how these pages
read before the switch existed.

French is what you get with no `#fragment`; `#en` selects English.

## Every page is self-contained

Stylesheet inline, logo as a `data:` URI. Nothing loads from anywhere else, so a
page renders the same served from here, opened straight from a clone, or
attached to a mail — and there is no asset that can go missing under a policy
URL that Google re-checks. It costs about 35 KB of duplicated logo per page,
which is the right trade for a site of three pages.

## Keeping a policy in step with its app

**The app repository is the source.** Each policy here is a published copy:

| Published | Source |
|---|---|
| `budget/privacy/index.html` | `docs/privacy/index.html` in the private `budget` repository |
| `mon-garage/privacy/index.html` | `docs/store/privacy-policy.html` in the private `mon-garage` repository |

The claims a policy makes are checkable against the code that makes them true —
that is why the source lives next to it. Edit there, copy the file over, push
here.

When a policy changes, bump the "last updated" date in it, in both languages:
the Play listing points at this URL, not at a versioned copy.

## Adding an app

One directory per app, mirroring `budget/`, plus a card in **both** sections of
`index.html` — a card added to the French one alone is invisible to half the
site. Keep the page honest about what is actually released: these apps say they
collect nothing, which is the whole point, so the site should not be the place
that overstates anything.

## Commits

Every commit carries the name of the repository's owner, and that name alone: no `Co-Authored-By` trailer, no "Generated with" line, no tool
signature of any kind — in commit messages and in pull requests alike. This
repository is public, and its history says who wrote it. A message says what
changed and why; nothing else.

# schmitech-fr.github.io

The public site at <https://schmitech-fr.github.io/>. It exists mainly to serve
the privacy policies that Google Play requires: a policy URL must be publicly
reachable and stay reachable for as long as the app is listed, and the app
repositories are private, so they cannot serve it themselves.

GitHub Pages publishes the default branch root automatically for a
`<owner>.github.io` repository — there is no workflow and no build step. A push
is live within a minute.

```
index.html                  https://schmitech-fr.github.io/
carnet/privacy/index.html   https://schmitech-fr.github.io/carnet/privacy/
```

## Keeping a policy in step with its app

**The app repository is the source.** `carnet/privacy/index.html` is a published
copy of `docs/store/privacy-policy.html` in the private `carnet-auto-moto`
repository, where the claims can be checked against the code that makes them
true. Edit it there, then copy the file over and push here.

When a policy changes, bump the "last updated" date in it — the Play listing
points at this URL, not at a versioned copy.

## Adding an app

One directory per app, mirroring `carnet/`, plus a card in `index.html`. Keep
the page honest about what is actually released: these apps say they collect
nothing, which is the whole point, so the site should not be the place that
overstates anything.

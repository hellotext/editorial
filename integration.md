# Integration and updates

## Consume one pinned guide

Add this repository as a submodule at `docs/editorial` in each consumer:

```sh
git submodule add https://github.com/hellotext/editorial.git docs/editorial
git submodule update --init -- docs/editorial
```

The parent repository records the exact shared commit. Existing checkouts and
worktrees should run the update command before editorial work. Do not use a
floating branch download during builds. To adopt a new guide version, fetch the
submodule, review and check out the chosen release or commit, and commit the
updated gitlink together with any necessary local integration changes.

Add a short instruction to the consumer's root AGENTS.md:

> Before editorial article, screenshot or message-preview work, initialize the
> `docs/editorial` submodule and read `docs/editorial/skills/hellotext-editorial/SKILL.md`.
> It links to the shared rules. Read the local integration guide for repository
> paths, rendering and publication. Do not maintain another copy of shared rules.

This explicit entrypoint works independently of an agent's skill discovery.
Projects with a supported skill-discovery directory may link to the same skill
instead of copying it. Do not require a personal installation to author articles.

## Application adapter

The Hellotext application keeps its existing editorial components, catalogs,
validated custom example interchange and `editorial:export_help` task. Its
`docs/ui/editorial-visuals.md` documents implementation and export behavior and
links to this guide for authoring and capture rules.

Shared guidance updates do not require moving the Rails renderer here. A future
renderer extraction would be a separate implementation change, with compatibility
and browser verification for both consumers.

## Help Center adapter

Keep Help-specific setup in `docs/editorial-integration.md`. Keep `docs/`, source
capture records and other authoring-only directories out of Jekyll's published
output; do not publish the shared skill as an accidental Help page.

Generate previews with the application exporter, then copy only the required
includes and generated shared assets into Help. Retain editable definitions and
the application revision used for export. Do not edit generated HTML, CSS or
JavaScript by hand. Help must build from its committed artifacts without running
Rails or accessing an authenticated application.

Follow the exporter integration contract for script integrity, Content Security
Policy and Jekyll minification. Keep the existing security-header verifier strict.
Copy original screenshot assets without recompression or profile loss. Use the
Help project's production build and verify the resulting article in a browser.

## Public repository boundary

Publish guidance and reusable authoring templates here. Keep account access,
raw account exports, private source history and publishing logs in their owning
projects. Article screenshots and product assets stay with the articles; a public
guide does not automatically grant redistribution rights for unrelated assets.

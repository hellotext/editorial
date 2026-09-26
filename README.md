# Hellotext editorial

The shared authoring guide for Hellotext Resources and Help Center articles.
This repository owns editorial decisions, screenshot standards and the workflow
for authors and agents. It does not contain customer data, account access,
application source code, fonts or captured article assets.

## Start here

1. Read [the editorial guide](guide.md) before choosing or placing a visual.
2. Read [screenshots](screenshots.md) when explaining an interface step, or
   [message examples](messages.md) when showing what a customer receives.
3. Follow [the authoring workflow](workflow.md) and the consuming project's
   integration instructions.

Agents can use [the Hellotext editorial skill](skills/hellotext-editorial/SKILL.md).
It routes to these same documents; it does not duplicate their rules.

## Ownership

| Source | Responsibility |
| --- | --- |
| This repository | Shared editorial guidance and capture workflow |
| Hellotext application | Visual components, validated message interchange and Help bundle exporter |
| Each publishing project | Articles, original capture assets, source examples, provenance and publication records |

Message previews use one application renderer. Help consumes generated HTML,
CSS and JavaScript from it. Generated copies are expected; hand-maintained
copies of the guide or renderer are not.

See [integration and updates](integration.md) for a version-pinned dependency.
Changes here take effect in a consumer when it updates its pinned commit.

## Contributions

Use English for repository documentation and Git/GitHub metadata. Preserve
localized sample copy where it demonstrates a language-specific rule.
Keep editorial rules separate from implementation details. Update the relevant
canonical page and the changelog together, then review its effect on both
consumers. Do not add account access information or production records here.

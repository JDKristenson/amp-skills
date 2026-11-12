# Source, credit, and verification boundaries

Reviewed on **2026-11-12 UTC** against current remote default `main` at [`4148cf86953e6e2145e4bfe06ebf516a36acc2e9`](https://github.com/JDKristenson/amp-skills/tree/4148cf86953e6e2145e4bfe06ebf516a36acc2e9). This is a bounded source review, not a runtime, legal, or complete authorship audit. Later commits, branches, unmerged work, and contributions elsewhere are outside the baseline below.

## What this repository is

An upstream-derived collection of eight Amp skill definitions, including an executable TypeScript/Playwright browser client/server and snapshot tests. It is not a standalone portfolio website. Classification: **reference fork with a narrow local CI contribution**, high confidence for the reviewed branch and comparison.

The [GitHub tree page](https://github.com/JDKristenson/amp-skills/tree/main), read on the review date, explicitly displayed “forked from JokerRun/amp-skills.” This relationship is based on provider evidence, not a similar name or account namespace. That live page is not a pinned record of future upstream state. Exact imported component versions and the current upstream ahead/behind relationship were not established in this cleanup.

## Bounded contribution record

The baseline has nine reachable commits in its non-shallow history:

- Seven commits attributed to Ryan Carson, January 7–10, 2026. The last inherited commit is [`b9bdc68508c6e28305bf9d350b98862c70ecf31e`](https://github.com/JDKristenson/amp-skills/commit/b9bdc68508c6e28305bf9d350b98862c70ecf31e).
- Two commits attributed to JDKristenson, dated March 30, 2026 UTC (March 29 in the author's recorded offset): [CI type-check/test pipeline](https://github.com/JDKristenson/amp-skills/commit/4de5cb83d41bfbfae72586611cab008b11044828) at 01:27:05 UTC and [Chromium installation for tests](https://github.com/JDKristenson/amp-skills/commit/4148cf86953e6e2145e4bfe06ebf516a36acc2e9) at 02:04:16 UTC.

The net diff from that inherited commit to the reviewed baseline adds only the 41-line `.github/workflows/ci.yml`. It does not change the inherited skills or browser implementation. This documents a real CI contribution; it does not assert that identity searches capture all contributions, or that no other work exists. This later documentation cleanup is separate from the baseline CI delta.

## Preserve the credit chain

- **Ryan Carson:** inherited collection commits. Git history provides author attribution, not proof of sole authorship of every line.
- **JokerRun/amp-skills:** provider-displayed upstream repository identity, not an attribution of every inherited component to that account.
- **JDKristenson:** the two baseline CI commits above; do not present the inherited browser subsystem or skill collection as an original local implementation.
- **camhahu/browser:** explicitly credited for extraction methods in [commit `1a635fc`](https://github.com/JDKristenson/amp-skills/commit/1a635fc87faa753ea112e519670773521c6ea8fd).
- **SawyerHood/dev-browser:** the inherited [browser skill](https://github.com/JDKristenson/amp-skills/blob/4148cf86953e6e2145e4bfe06ebf516a36acc2e9/dev-browser/SKILL.md) points to its extension releases. This is a reference relationship; an exact imported version or complete code lineage was not established.
- **browser-use:** the inherited [client](https://github.com/JDKristenson/amp-skills/blob/4148cf86953e6e2145e4bfe06ebf516a36acc2e9/dev-browser/src/client.ts#L52-L61) credits its page-load approach.
- **Every.to:** the [compound-engineering definition](https://github.com/JDKristenson/amp-skills/blob/4148cf86953e6e2145e4bfe06ebf516a36acc2e9/compound-engineering/SKILL.md#L1-L7) explicitly credits that engineering approach.

The baseline commit bodies inspected contain no explicit AI coauthor or generation trailers. Amp/Claude references identify intended tools or workflows, not proven AI authorship; human commit names do not prove exclusively human authorship. Preserve any existing human, community, and AI credits when subsequently adding provenance evidence. This documentation and diagram cleanup was AI-assisted by Reason; that statement applies to this cleanup only, not retrospectively to inherited files.

## Rights and resource boundaries

The [baseline README](https://github.com/JDKristenson/amp-skills/blob/4148cf86953e6e2145e4bfe06ebf516a36acc2e9/README.md) said MIT, but the tracked baseline has no LICENSE, LICENSE.txt, NOTICE, or COPYING file. The PDF and DOCX frontmatter say Proprietary and refer to absent LICENSE.txt files; frontend-design refers to another absent LICENSE.txt. The browser manifest supplies no license field. These observations establish missing/contradictory documentation, not a new grant, infringement finding, or conclusion that every file is proprietary. All existing skill payloads and embedded notices are retained unchanged.

The PDF references `reference.md` and `forms.md`; DOCX references `docx-js.md`, `ooxml.md`, and OOXML unpack/pack scripts. Those resources are not tracked here. Earlier README marketing entries, XLSX, and web-artifacts-builder are also absent. Do not invent their contents, import replacements without rights verification, or advertise them as bundled capabilities.

For future distribution, establish each component's source, version, applicable license text, notice obligations, and any permission needed from its rights holder. Keep nested notices at their component boundaries; do not solve ambiguity by adding a blanket MIT license.

## Diagram and privacy boundary

[Preview](provenance-browser.svg) · [Editable Excalidraw source](provenance-browser.excalidraw)

The diagram separates inherited content from the local CI delta and distinguishes standalone browser control from the optional extension relay. Arrows represent source relationships or control paths, not verified runtime observations or a claim that all components share a license. The SVG is a static rendering of the editable scene's layout and labels, not a screenshot of a running browser subsystem.

Standalone startup creates a persistent profile and temporary directory. The HTTP API and CDP endpoints control browser state; never publish profile contents, cookies, tokens, page extracts, authenticated screenshots, or live endpoint details as evidence. Use isolated ports, a disposable profile, and synthetic content for any future authorized runtime checks. No browser state/history inspection was performed for this cleanup.

## Documentation verification

Focused static checks cover the eight-folder inventory, relative links in the new documentation, diagram JSON/SVG structure and label/layout correspondence, and byte-for-byte preservation of all pre-existing files other than README.md. The diagram preview was visually inspected. Native installation, dependency resolution, type checking, browser tests, server launch, Amp discovery, and extension integration were **NOT RUN** as part of this cleanup. CI results, if any, are reported separately on the pull request; a green workflow would not establish the missing license terms or resource completeness.

Recommendation: **retain as a reference fork** and describe the baseline local work narrowly as CI maintenance. Do not showcase the inherited implementation as original work. Archive/delete/visibility changes are neither needed nor performed by this documentation cleanup.

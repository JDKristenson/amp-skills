# Amp Skills

A collection of specialized skills for [Amp](https://ampcode.com), the AI coding agent.

## What are Skills?

Skills are domain-specific instruction sets that extend Amp's capabilities. When you invoke a skill, it loads detailed workflows, patterns, and techniques into the conversation context.

## Available Skills

This checkout ships eight `SKILL.md` definitions. A definition's presence does not guarantee that all of its referenced resources or dependencies are included.

### Development
- **ralph** - Set up Ralph for autonomous feature development
- **build-feature** - Autonomous task loop for implementing features
- **compound-engineering** - Plan → Work → Review → Compound workflow
- **prd** - Generate Product Requirements Documents
- **frontend-design** - Create distinctive, production-grade interfaces
- **dev-browser** - Browser automation with persistent page state

### Document Handling
- **pdf** - PDF manipulation (extract, create, merge, split, forms)
- **docx** - Word document creation, editing, and analysis

**Resource boundaries:** PDF references `reference.md` and `forms.md`, which are not included. DOCX references `docx-js.md`, `ooxml.md`, and OOXML helper scripts, which are not included. Do not assume those workflows are self-contained. The document and frontend skills also have unresolved license references; see [license status](#license-status).

Earlier README versions advertised marketing/content skills, `xlsx`, and `web-artifacts-builder`. Those folders are not shipped in this tree; the existing ignore rules exclude them. They are not installable from this checkout.

## Usage and setup

A clone alone does not establish that Amp has discovered these skills. The bundled browser instructions assume a skill folder under `~/.config/amp/skills/`; confirm the discovery convention for your Amp version before copying any reviewed skill there. Preserve each folder's supporting resources and notices. Do not install the whole collection without first resolving the applicable rights and resource gaps below.

After a reviewed skill is available to Amp, an example request is:

```text
Use the prd skill to draft requirements for a small feature.
```

### Browser subsystem: inferred native setup (NOT RUN)

`dev-browser` is an executable TypeScript/Playwright subsystem, not just a prompt. The following is derived from its [manifest](dev-browser/package.json), [startup script](dev-browser/scripts/start-server.ts), and [CI workflow](.github/workflows/ci.yml). This documentation cleanup did not install dependencies, launch Amp or a browser server, or verify runtime behavior.

Prerequisites: Node.js 20 and npm (the CI baseline), Chromium and its platform dependencies, and a graphical display for headed operation. The shell wrapper requires Bash; its crash recovery uses `lsof` and `kill`. Platform-specific compatibility has not been established.

For a future, authorized check in an isolated checkout, these are the CI-equivalent commands, **not commands run for this cleanup**:

```bash
cd dev-browser
npm install
npx tsc --noEmit
npx playwright install --with-deps chromium
npm test
```

The tests launch Chromium. There is no `typecheck` package script or root application build. A Bun lockfile is tracked, while the wrapper and CI use npm and `package-lock.json` is ignored; the npm path is not a locked, reproducible install. No dependency or lockfile changes were made here.

The documented standalone launch, from `dev-browser`, is `bash server.sh --headless` (omit `--headless` for headed mode). **Review before running:** the wrapper runs `npm install`; startup may download Chromium, creates `tmp/` and `profiles/`, probes port 9222, and may forcibly terminate a process on port 9223 as stale-CDP recovery. Reserve both ports in an isolated environment rather than sharing them with unrelated work.

The defaults are a page-management HTTP API on 9222 and Chromium CDP on 9223. The standalone HTTP listener does not explicitly bind loopback and the inspected routes have no authentication middleware; do not expose either control endpoint to an untrusted network. Actual exposure was not tested. The optional extension relay is a separate mode that can reach an existing Chrome session; its extension is not bundled and no installation, compatibility, or signed-in-browser check was performed.

The standalone profile is `dev-browser/profiles/browser-data` relative to this checkout. It can retain cookies, login state, storage, and cache. Treat it, temporary screenshots/page extracts, and CDP endpoint details as sensitive. Existing ignore rules exclude profiles and temporary output, but ignoring a path does not sanitize prior history or make browser automation safe. Use a disposable profile and non-sensitive fixtures for evaluation.

See the [source/provenance notes](docs/provenance.md) and [browser/provenance diagram](docs/provenance-browser.svg). Its [editable Excalidraw source](docs/provenance-browser.excalidraw) can be opened in a compatible Excalidraw editor; no browser state or private values are included.

## Adding Skills

Each skill is a folder containing a `SKILL.md` file with frontmatter:

```markdown
---
name: my-skill
description: "Brief description. Use when... Triggers on: keyword1, keyword2."
---

# Skill Title

Instructions, workflows, and patterns go here.
```

## License status

The earlier README stated **MIT**, but no license text or notice file is tracked at the reviewed baseline. This is a historical label, not verification of a repository-wide grant.

- `docx/SKILL.md` and `pdf/SKILL.md` retain their **Proprietary** frontmatter and references to `LICENSE.txt`; those referenced files are absent.
- `frontend-design/SKILL.md` also refers to an absent `LICENSE.txt`.
- `dev-browser/package.json` has no license field. Dependency licenses are separate from the rights in this collection.

These inconsistencies remain unresolved. This cleanup adds no license, permission, or replacement terms and does not remove or override inherited notices. Before redistribution or broad installation, identify each component's original source/version and obtain its applicable terms. See [provenance and credit boundaries](docs/provenance.md).

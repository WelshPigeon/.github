# Changelog

All notable changes to the Pigeon Studios repository standards are documented here. Each policy and licence carries its own version line; this file records what changed and when.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [2.5.1] - 2026-10-18

### Fixed

- The free and paid README templates and the paid `CONTRIBUTING.md` named the retired `pigeon-resource-versions` registry. They now point to [`pigeon-versions`](https://github.com/WelshPigeon/pigeon-versions).
- The README templates described a `Config.CheckForUpdates` setting that the update checker doesn't have. They now explain the `pigeon_update_check` server convar (`on`, `quiet` or `off`), which covers every Pigeon Studios resource.
- The paid `CONTRIBUTING.md` pointed reviewers to `.github/CODEOWNERS`, which GitLab projects don't get. It now says Pigeon Studios reviews every pull or merge request.

## [2.5] - 2026-10-17

The current set of standards, rewritten in full to match the legal pages on https://pigeonstudios.co.uk/legal/ and to cover every kind of project on GitHub and GitLab.

### Added

- Separate licences for free, paid and internal projects:
  - **Pigeon Studios Free Licence**, for public projects: free use and modification on any number of servers and communities, no redistribution, resale, bundling or escrow;
  - **Digital Product Licence (EULA)** copy for paid products, matching the website; and
  - **Proprietary and Confidential** notice for internal projects.
- Policies that apply across every repository: `CONTRIBUTING.md`, `SECURITY.md`, `SUPPORT.md` and `CODE_OF_CONDUCT.md`, covering FiveM and RedM resources, Discord bots and services, website code and tools.
- Issue forms for FiveM and RedM bugs, other software bugs, feature requests and documentation problems, with links to support, security reporting and order help.
- A pull request template with checklists for each project type.
- Templates for every repository: README (free FiveM, free general, paid and internal), CHANGELOG, NOTICE, CODEOWNERS, `.editorconfig`, `.gitattributes`, `.gitignore`, `.env.example`, and internal notes for paid products.
- Private `CONTRIBUTING.md` and pull request templates for paid and internal repositories.
- GitLab issue and merge request templates.
- `tools/New-PigeonRepo.ps1` to set up a repository from the templates.

### Changed

- The business is described as **Pigeon Studios, the trading name of a sole trader based in England**, matching the website. Earlier documents used "Pigeon Studios Group".
- The governing law is **England and Wales**, matching the website. Earlier documents said "United Kingdom".
- The contact address for everything, including security reports, is **pigeon@pigeonstudios.co.uk**.
- Each repository now has a single `LICENSE.md` instead of both `LICENSE` and `LICENSE.md`.

### Removed

- Placeholder links (Discord invites, wiki URLs) and references to branches and processes that weren't in use.

First published 2 February 2019.

[2.5.1]: https://github.com/WelshPigeon/.github/tree/v2.5.1
[2.5]: https://github.com/WelshPigeon/.github/tree/v2.5

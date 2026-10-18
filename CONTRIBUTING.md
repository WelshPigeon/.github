# Contributing to Pigeon Studios

**Version 2.5** · First published 2 February 2019 · Last updated 17 October 2026

Thanks for taking the time to help. Bug reports, fixes, translations and ideas all make our projects better for everyone who uses them.

This guide applies to **every Pigeon Studios repository on GitHub and GitLab**, whatever kind of project it is: FiveM and RedM resources, Discord bots and services, website code, tools and libraries. A repository can add to it, or replace it, with its own `CONTRIBUTING.md`. Please read the parts that apply to what you want to do before you start.

## Contents

- [Ground rules](#ground-rules)
- [Ways to contribute](#ways-to-contribute)
- [Asking for help](#asking-for-help)
- [Reporting a bug](#reporting-a-bug)
- [Suggesting a feature](#suggesting-a-feature)
- [Contributing code](#contributing-code)
- [Standards for every project](#standards-for-every-project)
- [FiveM and RedM resources](#fivem-and-redm-resources)
- [Discord bots and Node.js services](#discord-bots-and-nodejs-services)
- [Website and WordPress code](#website-and-wordpress-code)
- [Tools and scripts](#tools-and-scripts)
- [Commits](#commits)
- [Pull requests and merge requests](#pull-requests-and-merge-requests)
- [Review and merging](#review-and-merging)
- [Versioning and releases](#versioning-and-releases)
- [Translations](#translations)
- [Licence of your contributions](#licence-of-your-contributions)
- [Credit](#credit)

## Ground rules

- **Be decent.** Everyone taking part follows our [Code of Conduct](CODE_OF_CONDUCT.md).
- **Security problems are never reported in public.** If you've found a vulnerability or exploit, follow our [Security Policy](SECURITY.md) instead of opening an issue, pull request or merge request.
- **Issues aren't a help desk.** Questions about installing, configuring or using a project go to our [support channels](SUPPORT.md).
- **Respect the licence.** Each repository's `LICENSE.md` says what you may do with it. Our free projects use the Pigeon Studios Free Licence: you can use and modify them freely, but you can't reupload, resell or bundle them. Forks on GitHub or GitLab are for preparing contributions only.
- **Only send work you have the right to send.** Don't include code, images, sounds, models or text copied from other projects, leaks or paid products, or anything generated from them.
- **No secrets or personal data.** Never include tokens, keys, passwords, webhook URLs, IP addresses or anyone's personal data in issues, commits or pull requests.

## Ways to contribute

| You want to | Do this |
|---|---|
| Report something that's broken | Open a **Bug report** issue |
| Suggest a new feature or change | Open a **Feature request** issue |
| Fix a bug or typo | Open a pull request or merge request (no issue needed for small fixes) |
| Add a feature | Open a feature request first and wait for a maintainer to agree, then open a pull request |
| Add or fix a translation | Open a pull request that changes the project's locale files |
| Improve the documentation | Open a pull request, or a **Documentation** issue if you're not sure of the fix |
| Report a vulnerability or exploit | Follow the [Security Policy](SECURITY.md), privately |
| Ask a question | Use our [Discord](https://discord.gg/2NFVWEUmDF) or [support page](https://pigeonstudios.co.uk/support/) |

## Asking for help

See [SUPPORT.md](SUPPORT.md). Issues that are really support questions will be closed with a link to the right place. That's not us brushing you off; it's how we keep the issue tracker useful for everyone.

## Reporting a bug

Before you open a bug report:

1. **Update.** Make sure you're on the latest release. FiveM resources tell you in the server console when an update is available; other projects list releases on their repository page.
2. **Update what it depends on.** For example your FXServer artifact and resources such as `ox_lib`, or your Node.js version and packages.
3. **Search.** Check the open and closed issues to see if someone has already reported it.
4. **Isolate.** If you can, reproduce the problem in a clean setup with only the project and its dependencies. Many problems come from conflicts with other resources, plugins or edited files.

Then open a **Bug report** issue, choose the form for the kind of project, and fill in every field. The most useful things you can give us are:

- the exact steps to make it happen;
- what you expected and what happened instead;
- the full error output, pasted as text, not as a screenshot; and
- anything you've changed in the configuration or code.

Bug reports about modified copies, or copies that didn't come from our official repositories, website or store, will be closed.

## Suggesting a feature

Open a **Feature request** issue. Explain the problem you're trying to solve, not only the solution you have in mind; there may be a better way that fits more people. Say whether you'd like to build it yourself.

We want our projects to stay focused, lightweight and easy to configure, so we can't accept every idea. If we decide not to add something, we'll say why. Where the licence allows, you're free to add it to your own copy.

## Contributing code

1. **Talk to us first about anything big.** For new features, large refactors, new dependencies or anything that changes how the project is configured, open a feature request and wait for a maintainer to agree before you write the code. Small fixes, typo fixes and translations don't need this.
2. **Fork** the repository on GitHub or GitLab.
3. **Create a branch** from `main` in your fork, named after the change with a prefix:

   | Prefix | Use | Example |
   |---|---|---|
   | `fix/` | Bug fixes | `fix/dice-cooldown-reset` |
   | `feat/` | Features | `feat/discord-log-colours` |
   | `docs/` | Documentation | `docs/install-steps` |
   | `locale/` | Translations | `locale/de` |
   | `refactor/` | Changes that don't change behaviour | `refactor/split-server-events` |
   | `chore/` | Tooling, CI, dependencies | `chore/update-discord-js` |

4. **Make your change**, following the standards below for that kind of project.
5. **Test it** properly (see the section for the project type). Test the change itself and check that you haven't broken anything around it.
6. **Open a pull request** (GitHub) or **merge request** (GitLab) against `main` in the official repository, and fill in the template.

Keep each pull request small and focused on one change. Two unrelated fixes should be two pull requests. Large pull requests take much longer to review and are more likely to be declined.

## Standards for every project

These apply whatever the language or project:

- **Follow the existing style.** Match the formatting, naming and structure of the code around your change. Each repository's `.editorconfig` sets indentation and line endings for most editors: LF line endings, UTF-8, a final newline, 4 spaces for Lua, PHP and SQL, and 2 spaces for JavaScript, TypeScript, CSS, HTML, JSON and YAML.
- **Validate everything that comes from outside.** Player events, Discord commands, form fields, API responses and file contents are all untrusted until checked.
- **Keep secrets out of code.** Tokens, keys, passwords and webhook URLs come from environment variables, server convars or server-only configuration, never from source files or anything sent to a client or browser.
- **Use parameterised queries** for every database call. Never build SQL by joining strings.
- **Escape output** that includes user-supplied text, whether it's going into HTML, the NUI, a Discord embed or a log line.
- **Handle errors.** Don't let one failure crash the whole resource, bot or page; log it with enough context to fix it, without logging secrets or personal data.
- **Don't add dependencies lightly.** Every dependency is something every user has to install and keep updated. Discuss new ones in an issue first.
- **Keep it accessible.** User interfaces should work with a keyboard, have enough colour contrast and label their controls. See our [Accessibility Statement](https://pigeonstudios.co.uk/legal/accessibility/).
- **Remove debug output** before opening a pull request, or put it behind the project's debug setting.
- **Document what you change.** Update the README, configuration comments and `CHANGELOG.md` in the same pull request.

## FiveM and RedM resources

### Development server

You'll need:

- an FXServer build on a recommended artifact (see https://runtime.fivem.net/artifacts/), ideally with txAdmin;
- a Cfx.re licence key from https://portal.cfx.re/ for your development server;
- the dependencies listed in the resource's `README.md` and `fxmanifest.lua`; and
- if the resource uses a database, MariaDB or MySQL with `oxmysql`.

We recommend [Visual Studio Code](https://code.visualstudio.com/) with the **CfxLua IntelliSense** extension, which includes the Lua Language Server and FiveM native definitions.

Put the resource in your server's `resources` folder, add `ensure <resource-name>` to `server.cfg` after its dependencies, and start the server. Use `restart <resource-name>` in the server console after changes, and watch both the server console and the client F8 console. Never test on a live server with real players.

### Layout

| Path | What goes there |
|---|---|
| `fxmanifest.lua` | Resource metadata, version and file lists |
| `client/` | Code that runs on players' games |
| `server/` | Code that runs on the server, including all validation and anything that touches the database, money or items |
| `shared/` | Code and data used by both |
| `configuration/` | Settings server owners are expected to change |
| `locales/` | Translations, one file per language |
| `web/` | The NUI: HTML, CSS, JavaScript and images |
| `sql/` | Database schema and migrations |

### Lua

- Declare everything `local` unless it has to be global. If something must be shared between files, put it in a table owned by the resource.
- Use `camelCase` for locals and functions, `PascalCase` for module tables and `UPPER_SNAKE_CASE` for constants.
- Name events `resource-name:side:action`, for example `pigeon-dice:server:roll`, so they can't collide with other resources.
- Check native names, arguments and return values against the [FiveM native reference](https://docs.fivem.net/natives/), and make sure server code only uses natives that exist on the server.
- Don't run work every frame unless it has to. Use `Wait()` with sensible intervals and stop loops when they're not needed.
- Prefer early returns over deep nesting, and keep lines under 120 characters.

### Security

- **Never trust the client.** Every server event handler must check that the player is allowed to do what they've asked, that they're close enough, that they have the item, job or money, and that every argument is the right type and in range. Assume a cheater can trigger any client-to-server event with any arguments.
- **Rate-limit** server events that a player can trigger repeatedly.
- **Never send secrets to the client.** Webhook URLs and keys belong in server-only files or convars.
- **Escape player text** shown in the NUI, such as names and messages.

### Configuration, locales, database and NUI

- Anything a server owner might want to change belongs in `configuration/`, with a comment explaining what it does, the accepted values and the default. New options must default to the current behaviour.
- Never hard-code text players can see; add it to every file in `locales/`.
- Put schema changes in `sql/` as a new migration that's safe to run on an existing database. Never edit a released migration.
- Keep the NUI lightweight: bundle what it needs in `web/` rather than loading it from the internet, test it from 1280×720 to 3840×2160, and always release focus (`SetNuiFocus(false, false)`) when it closes, including on errors.

## Discord bots and Node.js services

### Setting up

- Install the Node.js version in `package.json` (`engines`), then run `npm ci`.
- Copy `.env.example` to `.env` and fill it in with your **own test bot** and **test Discord server**. Never use a live token, live database or real member data.
- Follow **Running it locally** in the project's `README.md`.

### JavaScript

- Use modern JavaScript: `const` and `let`, `async`/`await`, strict equality.
- Handle every rejected promise; an unhandled rejection can take the bot down.
- Read configuration from environment variables once at start-up, and fail with a clear message if a required one is missing.
- Keep `package-lock.json` committed and up to date.

### Discord

- Give slash commands the narrowest default permissions they need, and check permissions again in the handler.
- Reply or defer within 3 seconds; use `deferReply()` for anything slow.
- Validate every option a user can type, and respect Discord's rate limits.
- Only request the gateway intents the bot actually needs, and only store the member data it needs. Bots must follow Discord's Developer Terms of Service and Developer Policy.

### Testing

Run the bot against your test server and exercise every command or feature you changed, including permission checks and error paths. Make sure `npm test` and the linter pass if the project has them.

## Website and WordPress code

- Follow the [WordPress Coding Standards](https://developer.wordpress.org/coding-standards/) for PHP, JavaScript, CSS and HTML in themes and plugins.
- Prefix every function, class, hook, option and constant with the project's prefix so nothing collides with other plugins.
- Sanitise input (`sanitize_text_field()`, `absint()` and similar), escape output (`esc_html()`, `esc_attr()`, `esc_url()`, `wp_kses_post()`), check capabilities with `current_user_can()`, and protect forms and AJAX with nonces.
- Use `$wpdb->prepare()` for every query that includes a variable.
- Make all user-facing text translatable with the project's text domain.
- Test with `WP_DEBUG` on, in a local or staging site, never on the live site. Check the change in a current version of Chrome, Firefox and Safari, on a phone-sized screen, and with the keyboard alone.
- Don't load scripts, fonts or images from third-party sites without discussing it first; it affects our [Privacy](https://pigeonstudios.co.uk/legal/privacy/) and [Cookie](https://pigeonstudios.co.uk/legal/cookies/) policies.

## Tools and scripts

- Explain at the top of the script what it does, what it needs and how to run it, with an example.
- Make destructive actions ask first or require an explicit flag, and support a dry run where it makes sense.
- Don't hard-code paths, usernames or credentials; take them as arguments or environment variables.
- PowerShell scripts should run on Windows PowerShell 5.1 and PowerShell 7 unless the README says otherwise.

## Commits

We use [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/). Each commit message starts with a type:

| Type | Use it for |
|---|---|
| `feat:` | a new feature |
| `fix:` | a bug fix |
| `docs:` | documentation only |
| `locale:` | translations |
| `refactor:` | code changes that don't change behaviour |
| `perf:` | performance improvements |
| `test:` | tests |
| `ci:` | CI and deployment workflows |
| `chore:` | maintenance, tooling and dependencies |

Write the first line in the imperative mood ("fix cooldown reset", not "fixed cooldown reset"), keep it under 72 characters, and explain the why in the body if it isn't obvious. Mark breaking changes with `!`, for example `feat!: rename Config.Debug to Config.debug`.

## Pull requests and merge requests

When you open one:

- fill in the template completely, including how you tested it;
- link the issue it fixes, using `Closes #123`;
- add an entry under **Unreleased** in `CHANGELOG.md`;
- **don't** change the version number (`fxmanifest.lua`, `package.json` or similar); we do that when we release;
- include screenshots or a short clip for anything visible; and
- make sure there are no secrets, webhook URLs, IP addresses or personal data anywhere in your changes.

Mark it as a draft if it isn't ready for review yet.

## Review and merging

- A maintainer will review it, usually within a week. Please be patient; this is a small studio.
- We may ask for changes. Push them to the same branch and the pull request updates itself.
- We squash-merge, so the final commit message will follow the conventions above even if your branch commits didn't.
- If there's been no response from you for 30 days after we've asked for changes, we may close it. You're welcome to reopen it later.
- We may decline a change that doesn't fit the project's direction, even if the code is good. We'll explain why.

## Versioning and releases

We use [Semantic Versioning](https://semver.org/):

- **Major** (`2.0.0`): breaking changes, such as renamed configuration, removed exports or commands, or database changes that need manual steps.
- **Minor** (`1.3.0`): new features that don't break existing setups.
- **Patch** (`1.2.4`): bug fixes only.

Maintainers release from `main`. Each release updates the version, moves the **Unreleased** notes in `CHANGELOG.md` under the new version, and publishes a tagged release (`v1.2.4`). For FiveM resources it also updates our public version registry so servers' update checkers see the new version.

## Translations

Translations are always welcome. Copy the English locale file (for example `locales/en.lua` or `locales/en.json`) to a new file named with the language's [ISO 639-1 code](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes), such as `de.lua`, translate the values (not the keys), and open a pull request. Keep placeholders such as `%s` or `{name}` exactly as they are.

## Licence of your contributions

By submitting a contribution to a free project, you agree to the **Contributions** section of the Pigeon Studios Free Licence in that repository's `LICENSE.md`. In short: you confirm the work is yours to give, you keep your copyright, and you give Pigeon Studios a permanent licence to use your contribution in that project and in our other products.

If a repository uses a different licence, its `LICENSE.md` or `CONTRIBUTING.md` explains the terms for contributions. If you can't agree to them, please don't submit a contribution.

## Credit

We credit contributors in the release notes in `CHANGELOG.md` by their GitHub or GitLab username, unless you ask us not to. Thank you.

---

Questions about contributing? Ask in our [Discord](https://discord.gg/2NFVWEUmDF) or email pigeon@pigeonstudios.co.uk.

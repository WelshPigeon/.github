<!--
Thanks for contributing! Please fill in every section. Pull requests without testing details may be closed.
Fixing a security problem that hasn't been made public? Report it privately first (see SECURITY.md) so we can coordinate the release.
Delete any section or checklist group that doesn't apply to this project.
-->

## Summary

<!-- What does this change, and why? One or two sentences is fine for small fixes. -->

## Related issue

<!-- "Closes #123", or "None" for a small fix. New features need an agreed issue first. -->

## Type of change

- [ ] Bug fix (doesn't change how anything is configured)
- [ ] New feature (doesn't break existing setups)
- [ ] Breaking change (users will need to change their configuration, database, environment or integrations)
- [ ] Performance improvement
- [ ] Translation
- [ ] Documentation
- [ ] Refactor or maintenance (no change in behaviour)

## What changed

<!-- The main changes, file by file if it helps. Mention any new commands, events, exports, settings, environment variables, dependencies or database changes. -->

-

## How it was tested

<!-- What you did to check it works, and that nothing around it broke. Fill in what applies. -->

- **Environment:** <!-- e.g. FXServer artifact + framework + dependency versions / Node.js version + test Discord server / PHP + WordPress version + browsers -->
- **Steps:**
  1.
  2.

## Screenshots or clips

<!-- For anything visible: in game, in the NUI, in Discord or on the website. -->

## Upgrade notes

<!-- For breaking changes, database changes or new required settings: what users need to do when they update. -->

## Checklist

**Every project**

- [ ] I've read [CONTRIBUTING.md](https://github.com/WelshPigeon/.github/blob/main/CONTRIBUTING.md) and followed the standards for this kind of project.
- [ ] I tested this in a development or test environment, not a live one.
- [ ] There are no new errors or warnings in the console, logs or browser developer tools.
- [ ] Everything that comes from users or players is validated, and anything shown back to them is escaped.
- [ ] New settings are documented and default to the current behaviour.
- [ ] New user-facing text is translatable, where the project supports translations.
- [ ] I added an entry under **Unreleased** in `CHANGELOG.md`.
- [ ] I didn't change the version number.
- [ ] My changes don't include tokens, keys, passwords, webhook URLs, IP addresses or personal data.
- [ ] This is my own work, or I have the right to submit it, and I agree to the Contributions section of the licence in `LICENSE.md`.

**FiveM and RedM resources**

- [ ] Every new server event checks the player, their permissions and every argument.
- [ ] Natives were checked against the native reference, and server code only uses server natives.
- [ ] `resmon` shows no new idle cost.

**Discord bots and Node.js**

- [ ] New commands have the narrowest permissions they need, and check them in the handler.
- [ ] New environment variables are in `.env.example` with placeholder values, and in the README.
- [ ] `package-lock.json` is updated if dependencies changed.

**Website and WordPress**

- [ ] Input is sanitised, output is escaped, capabilities and nonces are checked, and queries use `$wpdb->prepare()`.
- [ ] Tested on desktop and phone-sized screens, and with the keyboard alone.

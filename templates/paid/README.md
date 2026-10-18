<!--
TEMPLATE: Pigeon Studios paid (escrowed) FiveM resource README.
This file ships to buyers inside the release zip, so write it for server owners, not for us.
Internal notes (build steps, escrow settings, release process) go in docs/INTERNAL.md, which is excluded from the zip.
Replace every placeholder in double curly braces, delete optional sections that don't apply, and delete this comment.
-->

<div align="center">
  <img src="web/img/banner.png" alt="{{RESOURCE_NAME}} by Pigeon Studios" width="100%" />

  <h1>{{RESOURCE_NAME}}</h1>

  <p><strong>{{SHORT_DESCRIPTION}}</strong></p>

  <p>
    <a href="https://pigeonstudios.co.uk">Website</a> ·
    <a href="{{STORE_URL}}">Store page</a> ·
    <a href="https://discord.gg/2NFVWEUmDF">Support</a> ·
    <a href="CHANGELOG.md">Changelog</a>
  </p>
</div>

---

Thanks for buying {{RESOURCE_NAME}}. This guide covers everything you need to install, configure and update it. If you get stuck, open a ticket in our [Discord](https://discord.gg/2NFVWEUmDF) with your order number.

## Contents

- [What's included](#whats-included)
- [Requirements](#requirements)
- [Getting your files](#getting-your-files)
- [Installation](#installation)
- [Configuration](#configuration)
- [Commands and permissions](#commands-and-permissions)
- [Framework and inventory bridges](#framework-and-inventory-bridges)
- [Exports and events](#exports-and-events)
- [Localisation](#localisation)
- [Updating](#updating)
- [Update checker](#update-checker)
- [Troubleshooting](#troubleshooting)
- [Support](#support)
- [Your licence](#your-licence)

## What's included

| Path | What it is | Can you edit it? |
|---|---|---|
| `configuration/` | All settings | ✅ Yes |
| `locales/` | Translations | ✅ Yes |
| `bridge/` | Framework, inventory and target integration | ✅ Yes, if you use a custom framework |
| `sql/` | Database install and migrations | ✅ Run, don't edit |
| `client/`, `server/`, `shared/` | The resource's code | 🔒 Protected by FiveM asset escrow |
| `web/` | The in-game interface | 🔒 Protected <!-- or ✅ if not escrowed --> |
| `stream/` | Models, textures and sounds | 🔒 Protected <!-- or delete --> |

The files you can edit are listed under `escrow_ignore` in `fxmanifest.lua`.

## Requirements

| Requirement | Version | Notes |
|---|---|---|
| FXServer | artifact {{MIN_ARTIFACT}} or newer | Escrowed resources need a recent artifact. [Artifacts](https://runtime.fivem.net/artifacts/) |
| OneSync | enabled | |
| [ox_lib](https://github.com/communityox/ox_lib) | 3.0 or newer | |
| [oxmysql](https://github.com/communityox/oxmysql) | 2.0 or newer | |

**Supported frameworks:** {{FRAMEWORKS}} <!-- e.g. ESX Legacy 1.10+, QBCore, Qbox -->
**Supported inventories:** {{INVENTORIES}} <!-- e.g. ox_inventory, qb-inventory -->

Your server must use the same Cfx.re account (Keymaster) that you used to buy the resource, or the escrowed files won't load.

## Getting your files

1. Sign in to the [Cfx.re Portal](https://portal.cfx.re/) with the Cfx.re account you used at checkout.
2. Go to **Granted Assets** and download **{{RESOURCE_NAME}}**.
3. Updates appear in the same place. Download the latest version from there each time.

If the asset isn't there, check you're signed in with the right account, then open a ticket with your Tebex transaction ID.

## Installation

1. **Extract** the download into your server's `resources` folder, keeping the folder name `{{RESOURCE_FOLDER}}`.
2. **Database:** import `sql/install.sql` into your server's database.
3. **Items** (if your inventory needs them): add the items from `install/items/` to your inventory's item list. <!-- or delete -->
4. **Start it** by adding this to `server.cfg` after its dependencies, framework and inventory:

   ```cfg
   ensure oxmysql
   ensure ox_lib
   ensure {{RESOURCE_FOLDER}}
   ```

5. **Configure** it in `configuration/config.lua`.
6. **Restart** your server and check the console for the startup message.

## Configuration

Every setting is explained by a comment in `configuration/config.lua`. Server-only settings, such as webhooks, are in `configuration/server.lua`, which is never sent to players.

| Setting | Default | What it does |
|---|---|---|
| `Config.Locale` | `'en'` | Language from `locales/` |
| `Config.Framework` | `'auto'` | Detected automatically; set it if detection fails |
| `Config.Debug` | `false` | Extra console output. Leave off on live servers |
| `Config.…` | | |

## Commands and permissions

| Command | Who can use it | What it does |
|---|---|---|
| `/command` | | |

```cfg
add_ace group.admin {{RESOURCE_FOLDER}}.admin allow
```

## Framework and inventory bridges

The resource detects your framework and inventory automatically. If you use a custom or renamed framework, edit the matching file in `bridge/`; each function is commented with what it needs to return.

## Exports and events

<!-- Optional: document arguments, return values and side. -->

```lua
local result = exports['{{RESOURCE_FOLDER}}']:exportName(source, arg)
```

## Localisation

Set `Config.Locale` to a file in `locales/`. To add a language, copy `locales/en.lua`, rename it with the two-letter language code and translate the values. Send it to us and we'll include it in the next update with credit.

## Updating

1. Read the [changelog](CHANGELOG.md), especially **Upgrade notes**.
2. Back up `configuration/`, `locales/` and your database.
3. Download the new version from the Cfx.re Portal and replace the resource folder.
4. Copy your settings into the new configuration files. New versions can add settings, so don't overwrite the new files with old ones.
5. Run any new files in `sql/migrations/` the changelog mentions, then restart.

## Update checker

When it starts, the resource checks our public version registry on GitHub and prints one line in the server console saying whether an update is available. The check is a single request to GitHub; it sends nothing about your server or players. You can change what it does in `server.cfg`:

```cfg
set pigeon_update_check "on"      # default: one short line
set pigeon_update_check "quiet"   # only print when there's an update or a problem
set pigeon_update_check "off"     # never check
```

This setting covers every Pigeon Studios resource on your server.

## Troubleshooting

**"You lack the required entitlement" or the resource won't start.**
The server's licence key must belong to the Cfx.re account that bought the resource. Check the key in `server.cfg` or txAdmin, and that you downloaded the files from that account's Portal.

**"Failed to verify protected resource".**
Update your FXServer artifact, then download the resource again from the Portal; the files may be corrupt or from an old version.

**Framework not detected.**
Make sure your framework starts before this resource, or set `Config.Framework` manually.

<!-- Add the real problems buyers hit, with fixes. -->

## Support

Open a ticket in our [Discord](https://discord.gg/2NFVWEUmDF) with:

- your order number or Tebex transaction ID;
- the resource version, framework and FXServer artifact; and
- the full error from the server console or F8 console.

We reply within 3 working days, usually much sooner. Support covers installing, configuring and fixing problems with the resource as supplied; changes for your server can be arranged as a [commission](https://pigeonstudios.co.uk/legal/commissions/). See [Getting help](https://pigeonstudios.co.uk/support/).

## Your licence

Your purchase gives you a licence to use {{RESOURCE_NAME}} under our **[Digital Product Licence](LICENSE.md)**. In short, a standard licence lets you:

- ✅ use it on **one** community's servers, including its development and test servers;
- ✅ change the configuration and editable files for that community; and
- ✅ show it in videos and streams.

You must not share, reupload, resell or leak it, include it in a pack, or try to get around the escrow protection. Licences can be traced, and leaks end the licence. Need it on more than one community? Email pigeon@pigeonstudios.co.uk.

Your consumer rights and our refund policy are in our [Terms of Sale](https://pigeonstudios.co.uk/legal/terms/) and [Refunds & Cancellations](https://pigeonstudios.co.uk/legal/refunds/).

---

© {{YEAR}} Pigeon Studios. <sub>Not affiliated with or endorsed by Rockstar Games, Take-Two Interactive or Cfx.re.</sub>

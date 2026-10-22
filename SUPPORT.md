# Getting Help

**Version 2.5** · First published 2 February 2019 · Last updated 17 October 2026

Need a hand with a Pigeon Studios project? This applies to all of them: FiveM and RedM resources, Discord bots, our website and our tools. Here's where to go, what to check first and what to send us so we can help quickly.

## Where to ask

| Your question is about | Go to |
|---|---|
| Installing, configuring or using one of our free resources or tools | [GitHub Discussions](https://github.com/orgs/pigeon-studios-uk/discussions/categories/q-a) (Q&A), or our [Discord server](https://discord.gg/2NFVWEUmDF) |
| Installing, configuring or using a paid resource, bot or service | Our [Discord server](https://discord.gg/2NFVWEUmDF), in the support channels |
| A paid product, order, download or licence | Email pigeon@pigeonstudios.co.uk with your order number, or open a ticket in our [Discord](https://discord.gg/2NFVWEUmDF) |
| A refund or cancellation | See our [Refunds & Cancellations](https://pigeonstudios.co.uk/legal/refunds/) policy, then email us |
| A hosted Discord bot or subscription | Open a ticket in our [Discord](https://discord.gg/2NFVWEUmDF) |
| Something that's definitely broken | Open a **Bug report** issue in the project's repository |
| An idea for a new feature | Post it in [Discussions → Ideas](https://github.com/orgs/pigeon-studios-uk/discussions/categories/ideas) so others can upvote it, or open a **Feature request** issue in the project's repository |
| A security problem, vulnerability or exploit | **Don't post it publicly.** Follow our [Security Policy](SECURITY.md) |
| A leaked or resold copy of our work | See our [Copyright & Takedown Policy](https://pigeonstudios.co.uk/legal/takedown/) |
| Anything else | Our [support page](https://pigeonstudios.co.uk/support/) or pigeon@pigeonstudios.co.uk |

Please don't use GitHub or GitLab issues for questions about setup or configuration. They'll be closed with a link back here, because issues are for tracking bugs and features in the code.

## Before you ask

Most problems are solved by one of these. Please check them first.

### Every project

1. **Are you on the latest version?** Check the repository's releases, our website or Tebex. FiveM resources also tell you in the server console when an update is available.
2. **Have you read the README?** Most questions are answered in its installation, configuration and troubleshooting sections, or in the comments next to each setting.
3. **What do the logs say?** Find the first error in the console or logs. It's usually the one that matters.
4. **Did you change anything?** Try again with the default configuration and an unmodified copy.

### FiveM and RedM resources

1. **Are the dependencies installed and up to date?** Check the resource's `README.md` for what it needs, such as `ox_lib` or `oxmysql`, and make sure they're running.
2. **Is the start order right?** In `server.cfg`, `ensure` the dependencies **before** the resource. For example, `oxmysql`, then `ox_lib`, then your framework, then our resource.
3. **Is the folder name right?** Don't rename the resource folder unless the README says you can. The `-main` or version suffix GitHub adds to zip downloads should be removed.
4. **Did you run the SQL?** If the resource has an `sql/` folder, import it into your database before starting the resource.
5. **What do the consoles say?** Check the server console and the client F8 console for red errors.
6. **Is it a conflict?** Try the resource on a clean test server with only its dependencies. If it works there, another resource on your server is interfering.

### Discord bots and services

1. **Is the bot online and in your server?** Check it appears in the member list and isn't timed out.
2. **Does it have the permissions it needs?** Check its role is high enough and has the permissions listed in the README, in the server and in the channel.
3. **Are the commands registered?** New or changed slash commands can take a minute to appear. Restart your Discord app.
4. **Self-hosted?** Check every variable in `.env.example` is set in your `.env`, and that your Node.js version matches the README.

## What to include when you ask

Help us help you by including all of this in your first message:

- the project name and version;
- for FiveM resources: your framework (ESX, QBCore, Qbox, ox_core or standalone) and its version, and your FXServer artifact number;
- for bots: the Discord server it's in, and whether we host it or you do (and your Node.js version if you do);
- exactly what you did, what you expected to happen and what happened instead;
- the full error text from the console or logs, copied as text (screenshots of text are hard to search);
- any changes you've made to the configuration or the code; and
- for paid products, your order number or Tebex transaction ID.

Please never post your webhook URLs, licence keys, database passwords, bot tokens or `server.cfg` secrets in a public channel or issue. If we need something private, we'll ask you to send it in a ticket or by email.

## Response times

We're a small studio and we read everything. We aim to reply to emails and tickets within **3 working days**, and usually much sooner. Support in public Discord channels is often faster because other members of the community can help too.

## What we can and can't help with

**We can help with:**

- installing and configuring our resources, bots and tools, on supported setups;
- errors and bugs in our code;
- questions about how a feature works; and
- for paid products, getting access to your purchase and updates.

**We can't help with:**

- copies of our projects that didn't come from us (we can't support leaked copies, and they often contain backdoors);
- copies that have been heavily modified, unless you can reproduce the problem on an unmodified copy;
- other people's resources, bots, plugins, frameworks or server setups in general;
- custom changes or new features for your server or community, though we may be able to help as a paid [commission](https://pigeonstudios.co.uk/legal/commissions/); and
- problems with FiveM, txAdmin, Discord, hosting or the game itself that aren't caused by our projects. Cfx.re's own support is at https://forum.cfx.re/ and Discord's is at https://support.discord.com/.

## Paid products

If you bought a product from us, your consumer rights and our refund policy are explained in our [Terms of Sale](https://pigeonstudios.co.uk/legal/terms/) and [Your Statutory Rights](https://pigeonstudios.co.uk/legal/your-rights/). If a product doesn't work as described, tell us and we'll fix it, replace it or refund you as those terms set out.

---

Pigeon Studios · https://pigeonstudios.co.uk · pigeon@pigeonstudios.co.uk

# Security Policy

**Version 2.5** · First published 2 February 2019 · Last updated 17 October 2026

Pigeon Studios makes FiveM and RedM resources, Discord bots, website code and tools. Many of them run on other people's servers and in their communities, alongside their players' and members' data, money and items. We take security reports seriously and we're grateful to everyone who reports problems responsibly.

This policy applies to every Pigeon Studios project and repository on GitHub and GitLab, free, paid or internal, unless a repository has its own `SECURITY.md`.

## Contents

- [Reporting a vulnerability](#reporting-a-vulnerability)
- [What to include](#what-to-include)
- [What happens next](#what-happens-next)
- [Supported versions](#supported-versions)
- [Scope](#scope)
- [Safe harbour](#safe-harbour)
- [Disclosure](#disclosure)
- [Credit and rewards](#credit-and-rewards)
- [Keeping your server and bots secure](#keeping-your-server-and-bots-secure)
- [Your data](#your-data)

## Reporting a vulnerability

> **Please don't report security problems in public issues, pull requests, discussions, Discord channels or anywhere else public.** Public reports put everyone using the project at risk before a fix is available. We'll remove public reports and handle them privately.

Report privately in one of these ways:

1. **GitHub:** open the repository's **Security** tab and click **Report a vulnerability**. This creates a private advisory only you and we can see. If the button isn't there, use email instead.
2. **GitLab:** open a new issue in the project and tick **This issue is confidential** before you submit it.
3. **Email:** pigeon@pigeonstudios.co.uk with the subject line **"Security report: \<resource name\>"**. Use this for paid resources, bots, our website, or if the options above aren't available.

If the problem affects something we run live, such as our website, store, hosted Discord bots or customer data, rather than code in a repository, email us; don't use GitHub or GitLab.

## What to include

The more of this you can give us, the faster we can fix it:

- the project or service affected, and the version (from `fxmanifest.lua`, `package.json`, the release you downloaded, or the console);
- the type of problem, for example an unvalidated server event, item or money duplication, SQL injection, cross-site scripting in the NUI or website, a Discord command that skips its permission check, privilege escalation, or an exposed secret;
- step-by-step instructions to reproduce it, ideally on a clean test server;
- a proof of concept, such as the event name and arguments a cheat would send, if you have one;
- what an attacker could do with it, and whether it needs any special access, job or item; and
- the environment: for FiveM resources, your FXServer artifact, framework (ESX, QBCore, Qbox, ox_core or standalone) and dependency versions; for bots and other software, your Node.js or PHP version and the versions of any packages involved; for the website, your browser.

Please don't send exploit code as an attachment that has to be executed. Plain text in the report is best.

## What happens next

| Step | When |
|---|---|
| We acknowledge your report | Within 3 working days |
| We confirm whether it's a vulnerability and how serious it is | Within 7 working days of acknowledging it |
| We fix it and release an update | **Critical:** as fast as possible, usually within 7 days · **High:** within 14 days · **Medium:** within 30 days · **Low:** in the next planned release |
| We tell you it's fixed, and agree on disclosure | When the fix is released |

We'll keep you updated while we work on it, and tell you if we decide it isn't a vulnerability and why. We judge severity by what an attacker could actually do on a typical server: for example, giving themselves unlimited money or items, affecting other players, reading or changing the database, or running code on the server or in other players' games.

## Supported versions

We fix security problems in the **latest release** of each project. For hosted bots and our website, we fix the live service directly. We don't patch older versions; the fix is to update.

| Version | Supported |
|---|---|
| Latest release | Yes |
| Any older release | No, please update |
| Modified copies, or copies not from the official repository or our store | No |

For paid resources, updates are available through your purchase on Tebex or the FiveM Keymaster portal for as long as the product is supported.

## Scope

**In scope:**

- code in any of our repositories on GitHub or GitLab, public or private;
- our FiveM and RedM resources, client, server and NUI, free and paid;
- our Discord bots, hosted or self-hosted, and the services behind them;
- our tools, scripts and libraries;
- our public version registry; and
- our website, pigeonstudios.co.uk, including its WordPress theme and plugins, store and customer accounts.

**Out of scope** (please report these to their owners instead):

- FiveM, FXServer, txAdmin and the Cfx.re platform: report to Cfx.re at https://aka.cfx.re/security-reports;
- frameworks, libraries and packages we depend on, such as ESX, QBCore, Qbox, ox_lib, ox_inventory, oxmysql, discord.js, Node.js or WordPress itself: report to their maintainers;
- other people's resources, bots and plugins, even if they're used alongside ours;
- Tebex, Stripe, Discord, GitHub, GitLab, Cloudflare and our hosting provider;
- problems caused by a server's own configuration, such as weak database passwords, exposed txAdmin panels or webhooks pasted into client files;
- general cheating that our resources can't reasonably prevent, such as aimbots or noclip; and
- reports from automated scanners with no demonstrated impact, missing best-practice headers, or denial-of-service by sending huge amounts of traffic.

If you're not sure whether something is in scope, report it anyway and we'll tell you.

## Safe harbour

We won't take legal action against you, or ask anyone else to, for security research that:

- is done on a server you own or have permission to test, never on a live server with real players that isn't yours;
- doesn't access, change or delete other people's data beyond what's needed to show the problem;
- doesn't disrupt other people's servers or our services;
- isn't used to gain money, items or advantages in game beyond demonstrating the problem; and
- is reported to us privately, and not disclosed publicly until we've released a fix or agreed a date with you.

This safe harbour applies only to our own rights. It doesn't stop a server owner, Cfx.re or anyone else enforcing their rules, and it doesn't permit anything that breaks the law. Testing a free or paid resource for vulnerabilities is permitted by our licences when it's done this way; circumventing FiveM asset escrow is not.

## Disclosure

We follow coordinated disclosure. Once a fix is released, we'll publish a note in the resource's `CHANGELOG.md` and, where it helps server owners, a GitHub security advisory, with enough detail for owners to know they need to update but not enough to make attacking unpatched servers easy.

Please give us **90 days** from your report, or until a fix is released if that's sooner, before you disclose anything publicly. If we can't fix it in that time, we'll talk to you about why and agree a new date.

## Credit and rewards

We'll thank you by name or username in the release notes and the advisory, unless you'd rather stay anonymous. We don't run a paid bug bounty, but for serious issues in paid products or our services we may offer store credit as a thank-you, at our discretion.

## Keeping your server and bots secure

Most compromised servers and bots we see are caused by configuration, not code. To keep yours safe:

- keep our resources, your FXServer artifact and your framework up to date, and read the update notice in your server console when it appears;
- only download our projects from our official repositories, our website or our Tebex store. Leaked copies are a common way backdoors get onto servers;
- keep webhook URLs, API keys and bot tokens in server-side files, server convars or environment variables, never in client or shared files, and never in a public repository;
- if you self-host one of our bots, reset its token straight away if it's ever exposed, and give it only the Discord permissions it needs;
- protect txAdmin with a strong password and two-factor authentication, and don't expose your database port to the internet;
- give staff the minimum permissions they need in your ACE permissions and framework; and
- back up your database before installing updates.

## Your data

When you report a problem, we use your contact details and your report only to investigate and fix it, and to credit you if you want us to. See our Privacy Policy at https://pigeonstudios.co.uk/legal/privacy/.

---

Thank you for helping keep Pigeon Studios resources, and the servers that use them, safe.

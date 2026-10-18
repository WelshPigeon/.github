# {{RESOURCE_NAME}}: internal notes

> **Not for buyers.** This file is excluded from release zips by `.gitattributes` (`export-ignore`). Keep everything about building, escrow and selling the product here, not in `README.md`.

## Product

| | |
|---|---|
| **Tebex package** | {{STORE_URL}} |
| **Cfx.re Portal asset** | {{ASSET_NAME}} |
| **Registry slug** | {{SLUG}} |
| **Price** | |
| **Supported frameworks** | {{FRAMEWORKS}} |
| **Supported inventories** | {{INVENTORIES}} |

## Escrow

Files buyers can edit (must match `escrow_ignore` in `fxmanifest.lua`):

- `configuration/**`
- `locales/**`
- `bridge/**`
- `sql/**`

Everything else is escrowed.

## Building a release

1. Follow **Releasing** in `CONTRIBUTING.md`.
2. Build the zip from the release tag:

   ```bash
   git archive --format=zip --prefix={{RESOURCE_FOLDER}}/ -o {{RESOURCE_FOLDER}}-vX.Y.Z.zip vX.Y.Z
   ```

3. Upload it to the Cfx.re Portal as a new version of **{{ASSET_NAME}}**.
4. Download the escrowed build and test it on a clean server.

## Testing servers

| Server | Framework | Notes |
|---|---|---|
| | | |

## Known issues and decisions

<!-- Things a future you would want to know: why something is done a certain way, compatibility workarounds, buyer requests declined and why. -->

-

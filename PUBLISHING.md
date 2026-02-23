# Publishing Light Spinel to Cursor

Cursor uses **OpenVSX** for its extension marketplace. Follow these steps to publish.

## Prerequisites

1. **Eclipse account** – [Register at accounts.eclipse.org](https://accounts.eclipse.org/user/register)  
   - Use the same GitHub username you’ll use on OpenVSX.

2. **OpenVSX setup**
   - Log in at [open-vsx.org](https://open-vsx.org) with GitHub
   - Link your Eclipse account (Profile → Log in with Eclipse)
   - Sign the Publisher Agreement
   - Create an [Access Token](https://open-vsx.org/user-settings/tokens)

## Before Publishing

1. **Update `package.json`** if needed:
   - `publisher` – your OpenVSX namespace (e.g. `beforeblackout`)
   - `repository.url` – your GitHub repo URL

2. **Package the extension**:
   ```bash
   npx @vscode/vsce package
   ```
   This creates `light-spinel-0.0.1.vsix`.

## Publish to OpenVSX

1. **Create your namespace** (once per publisher):
   ```bash
   npx ovsx create-namespace beforeblackout -p YOUR_ACCESS_TOKEN
   ```

2. **Publish**:
   ```bash
   npx ovsx publish -p YOUR_ACCESS_TOKEN
   ```
   Or use a pre-built `.vsix`:
   ```bash
   npx ovsx publish light-spinel-0.0.1.vsix -p YOUR_ACCESS_TOKEN
   ```

## After Publishing

- The extension will appear on [open-vsx.org](https://open-vsx.org)
- It may take some time to appear in Cursor’s marketplace
- For updates, bump the version in `package.json` and run `ovsx publish` again

## Cursor Plugin Marketplace (Alternative)

If you want to publish as a **Cursor plugin** (not a VS Code theme extension), use [cursor.com/marketplace/publish](https://cursor.com/marketplace/publish) and sign in to apply.

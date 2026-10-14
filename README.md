# Salesforce Access Debugger

A Chrome Manifest V3 side-panel extension for checking a Salesforce user's object, field, and record access. It uses Salesforce's standard REST and describe APIs with the active Salesforce session. No Access Debugger Apex classes, custom permission, permission set, or Salesforce deployment is required.

The object picker filters Salesforce labels and API names as you type. Field choices load when Field checking is enabled or when you select a different object.

The side panel can be opened from any tab, but the debugger is available only on supported Salesforce pages with an active Salesforce session. On other pages it explains how to connect; it also refreshes its connection when the active tab changes.

## Validate changes

Run `node --test .\chrome-extension\tests\service-worker.test.js` from the project root to verify the Salesforce-only connection gate.

## Install

1. Open `chrome://extensions` (or `edge://extensions`).
2. Enable **Developer mode**.
3. Select **Load unpacked** and choose this `chrome-extension` folder.
4. Sign in to Salesforce and open a Salesforce page.
5. Select the extension icon to open Access Debugger in the side panel.

The extension discovers the org's supported REST API version, reads the session cookie for the active org, and keeps the session in memory for API requests. It does not save the session ID or send org data to a third party. Reload the unpacked extension after changing its files.

## Build a release package

Run `.\scripts\package-extension.ps1` from the project root. The script creates `dist\SalesforceAccessDebugger-v<version>.zip` with only the runtime extension files. It deliberately excludes local signing keys, `.crx` files, tests, and documentation. Inspect the ZIP before uploading it to a browser extension store.

For a browser-store release, run `.\scripts\prepare-privacy-policy-site.ps1` from the project root. Upload the generated `dist\privacy-policy-site\index.md` to the root of a public GitHub repository and enable GitHub Pages from the `main` branch and root folder. For example, the `BONUD/salesforce-access-debugger-privacy` repository would publish at `https://bonud.github.io/salesforce-access-debugger-privacy/`. Confirm the page is publicly accessible before entering it in the store dashboard. Complete the store listing screenshots and privacy/data-use declarations there as well.

## Salesforce access requirements

The extension does not bypass Salesforce permissions. The signed-in Salesforce user needs API access and sufficient access to the data being inspected. Salesforce may limit user search, permission-source data, group membership, sharing information, or `UserRecordAccess` based on the user's profile, license, and org configuration. When Salesforce denies an API request, the extension shows the returned error.

Results are based on the signed-in user's access to Salesforce's standard APIs. Permission-set group, muting, and share-table details may be unavailable when Salesforce does not expose them to that user.

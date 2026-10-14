---
title: Privacy Policy â€” Salesforce Access Debugger
permalink: /
---
# Privacy Policy â€” Salesforce Access Debugger

**Publisher:** Rajesh Vatyani  
**Privacy/support contact:** rajeshvatyani803@gmail.com  
**Effective date:** 2026-10-14

## What the extension does

Salesforce Access Debugger is a browser side-panel extension. It helps the person using the browser inspect Salesforce object, field, and record access by calling Salesforce APIs while signed in to an org.

## Information accessed and purpose

When the panel is used on a supported Salesforce page, the extension:

- Reads the Salesforce `sid` session cookie for the active org to authenticate API requests.
- Reads Salesforce user, object, field, permission, record-access, ownership, group, and sharing information needed for the access check the user requests.
- Temporarily holds the session identifier, selected values, API responses, and access-check results in extension memory while the extension is running.

The information is used only to connect to Salesforce, perform the requested access check, display its results, and report errors to the user.

## Sharing, storage, and retention

The extension sends API requests and the session credential to the Salesforce org identified from the active Salesforce page. It does not intentionally send Salesforce data or the session identifier to the extension publisher, analytics services, advertising services, or other third parties. The extension does not intentionally write the session identifier, API responses, or check results to persistent extension storage. In-memory information is discarded when the relevant extension context is stopped or reloaded.

Salesforce processes requests under its own terms and privacy policy. The extension cannot control Salesforce's handling of data within Salesforce services.

## Permissions

- **Cookies:** read the active Salesforce session cookie to authenticate API calls.
- **Host access to Salesforce domains:** make Salesforce API requests for supported orgs.
- **Active tab:** identify the active page so the extension can connect only when a Salesforce page is open.
- **Side panel:** display the debugger interface in the browser side panel.

The debugger is unavailable on non-Salesforce pages.

## Your choices and responsibilities

Use the extension only in orgs where you are authorized to access the relevant information. Salesforce permissions continue to apply; the extension does not grant or bypass Salesforce access. You can remove the extension from your browser at any time. Signing out of Salesforce or ending the Salesforce session prevents further authenticated requests.

## Changes and contact

This policy will be updated if the extension's data practices change. For privacy questions or requests, contact **[rajeshvatyani803@gmail.com](mailto:rajeshvatyani803@gmail.com)**.


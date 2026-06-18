# webdevisfun-account

Shared Identity and Account app for webdevisfun independent apps.

## Purpose

This app owns account-facing user experience that can be reused by future independent apps while Auth0 remains the identity provider and login authority.

The app is intended to support workflows such as profile/account entry points, connected-app visibility, logout/account settings navigation, and future access-request or role-management UX.

## Boundary

| Field | Value |
| --- | --- |
| App type | Independent UI-only app initially; backend/database added only when app-owned account data is needed. |
| Repository | `radhikari89/webdevisfun-account` |
| GitHub Project | `https://github.com/users/radhikari89/projects/3` |
| Identity source of truth | Auth0/OIDC tenant or security profile shared with other webdevisfun apps. |
| Database | None initially. Add a separate app-owned database only for account metadata that should not live in Auth0. |
| Backend dependency | None initially. Add a dedicated backend only for server-side account workflows, app access, audit, or metadata. |
| Hub relationship | The hub may link users here for account workflows, but this app owns its own backlog and delivery work. |
| Portability | Must remain portable to a different domain, brand, or umbrella later. |

## Identity Model

Auth0 is the source of truth for authentication and provider identity. Independent apps should map local users/resources by issuer and subject, not by email alone.

Recommended app-local identity fields:

- `auth_issuer`
- `auth_subject`
- optional local user id
- optional app-specific role, preferences, and resource ownership

## Initial Local Run

Runtime implementation has not started yet.

Placeholder:

```powershell
npm install
npm run start
```

## Initial Verification Checklist

- [ ] Auth0 remains the login authority.
- [ ] No custom OAuth/OIDC provider is introduced.
- [ ] Account UI can run independently from the hub.
- [ ] Account UI can be deployed independently from the hub.
- [ ] Future backend, if added, validates Auth0-issued tokens independently.
- [ ] Future database, if added, is owned by this app.

## Project Workflow

Delivery stories for this app should be tracked in the dedicated project board:

- `https://github.com/users/radhikari89/projects/3`

The original hub coordination epic is:

- `https://github.com/radhikari89/codex-demo/issues/78`
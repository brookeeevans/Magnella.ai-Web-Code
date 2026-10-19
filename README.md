# Magnella.ai Web Code

Front-end code for magnella.com and related customer-facing surfaces.

## Repository layout

```
/account/        Customer account page (login + guide list)
  index.html     Login + guide list UI (safe to edit)
  styles.css     Visual styling (safe to edit)
  core/          Supabase client, auth, queries (DO NOT EDIT)
    README.md    Protection notice
.github/
  workflows/
    mirror.yml   Auto-sync to B-Lynk mirror on every push to main
```

## For AI agents (Lovable, Claude, etc.)

- **Visual + layout changes to the account page:** edit `/account/index.html` or `/account/styles.css` freely.
- **Auth, Supabase client, or query logic:** DO NOT MODIFY files in `/account/core/`. Those are maintained by B-Lynk engineering and editing them breaks customer login + guide access.
- **Any backend/data concerns:** flag to the humans; don't attempt to fix.

## For humans

Every push to `main` auto-mirrors to a private B-Lynk backup repo (`productionblynk/magnella-account-mirror`) via the workflow at `.github/workflows/mirror.yml`. Full history is preserved there — rollback to any point via git.

## Snapshot practice

Before any large change, tag the current state:

```bash
git tag snapshot-YYYY-MM-DD-reason
git push origin --tags
```

Rollback with:

```bash
git checkout snapshot-YYYY-MM-DD-reason
```

## Contact

Backend / data / auth issues → B-Lynk (Tom).

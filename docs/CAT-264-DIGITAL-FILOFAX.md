# CAT-264 · Digital Filofax Prototype

Status: review prototype only. Not production and not authorised for Google OAuth or automatic write-back.

## Purpose

Test a bilingual, accessible, offline-first whole-life interface while preserving the accepted Catholix Bible visual baseline.

## Included in this increment

- English/Spanish toggle available throughout the single-page interface.
- Offline application shell using a service worker.
- Browser-local tasks, quick capture, guided journal, finance notes, commonplace entries, home/garden notes, and reading/watch/podcast lists.
- Prayer structure for Morning, Evening and Night Prayer with links to authorised sources.
- Daily Mass reading links.
- Vatican Catechism and Bible links.
- A globally distributed news desk made of direct publisher links rather than an attention-maximising feed.
- Education, recipes, gardening, household, finance and Google-tools sections.
- Local data export and reduced-motion/larger-text controls.

## Deliberately excluded

- Google sign-in, Gmail/Calendar/Drive API access, automatic Google Doc creation, background sync, notifications, analytics and server storage.
- Reproduction of copyrighted liturgical editions or scraping of publishers.
- Any claim that the prototype replaces Plan A, the Catholix registers or controlled records.

## Proposed Google architecture after approval

1. Google Identity Services with least-privilege, incremental OAuth.
2. Calendar read-only initially; event writes require an explicit per-action confirmation.
3. Gmail metadata/read actions separated from sending; sending always requires explicit confirmation.
4. Journal export to a user-selected Drive folder through a narrowly scoped Drive file permission.
5. Tasks adapter supporting either Google Tasks or a controlled Catholix task register, avoiding duplicate masters.
6. IndexedDB as the offline store, with a visible sync queue, conflict review and audit log.
7. No sensitive journal content in application logs, analytics or public repositories.

## Verification checklist

- Open `filofax.html` on desktop and mobile widths.
- Toggle English/Spanish from several pages.
- Add, complete and delete tasks; reload and confirm persistence.
- Save journal and finance entries; export data.
- Install or reload offline after the service worker has cached the shell.
- Navigate entirely by keyboard and test reduced motion/larger text.
- Confirm all external links open in a new tab and local personal data remains browser-only.

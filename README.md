# Legacy Pages URL continuity

This account site preserves public static snapshots at their original project paths as the source repositories move to the DelQuro organization.

- Canonical repository ownership moves to DelQuro. This repository is a compatibility host under the original account only.
- Do not recreate any transferred repository name under PlanExServices: that would remove Git repository redirects.
- Keep PlanExServices active while these github.io addresses are retained.
- Do not force apps onto a different origin. Existing browser local storage remains at planexservices.github.io; it is never copied into this repository.
- Snapshots include only already public HTTP site files. They contain no visitor storage, provider credentials, or private application data.
- Capture rendered Jekyll pages and assets; copying raw Markdown under .nojekyll would change the published site.
- Update compatibility snapshots explicitly when the corresponding canonical site changes. Do not dispatch provider deployments or inherited application workflows.
- Keep source IDs, refs, publishing branch/path and rollback evidence in the local migration record. A transfer back requires coordinated owner and Pages verification; do not recreate an old-path repository as a rollback.

The migration-check-20261025 path is a bounded routing check. Existing project sites continue to take precedence at their original paths until moved.

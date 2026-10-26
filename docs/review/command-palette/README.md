# Command palette review images

These browser captures use synthetic accounts and builds. They show the result of choosing the same command before and after the fix; no creation forms were submitted.

- Before: public `main` at `3b68396284e7f65ab51f405a3838639d91b97b26`.
- After: `fix/command-palette-actions` at `1b86802ffc88fd73950a6c29c46d7c90b94e759d`.
- Viewport: 1440 × 1300; Carbon white theme. Comparison images put Before on the left and After on the right.

| Command | Before | After |
| --- | --- | --- |
| Go to Home | Page not found | Home dashboard |
| Create New User | User directory; no dialog | Existing creation dialog opens |
| Create New Build | Build list; no dialog | Existing creation dialog opens |
| Toggle Filters | Filter panel stays closed | Existing filter controls open |

Images are hosted on this documentation branch so they can be embedded in Issue #113 and its PR without adding binaries to the code change.

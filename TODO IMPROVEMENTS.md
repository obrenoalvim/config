### Add LICENSE file
- **Category:** Refactor
- **What:** No LICENSE file exists. Since this is a public repo consumed programmatically by github-portfolio-generator, an explicit license (MIT or similar) clarifies reuse terms for anyone forking the config format.
- **Where:** repo root
- **Why:** Public repos without a license default to "all rights reserved," which could discourage others from using this as a template for their own `config` repo.
- **Risk:** None — additive only.
- **Effort:** Low

### Verify `featured` repo names still exist and are spelled correctly
- **Category:** Bug
- **What:** `portfolio.json` → `sections.featured` lists `claude-terminal-hub`, `zero-drift`, `findable`, `github-portfolio-generator`, `relaykit`, `no-watermark`. The README notes these names are case-sensitive. Confirm each still exists under github.com/obrenoalvim and the casing matches exactly, since a mismatch silently drops the repo from the rendered portfolio with no error.
- **Where:** portfolio.json:19-26
- **Why:** Skipped verification here since it requires live GitHub lookups (external research out of scope for this pass).
- **Risk:** Low — cosmetic only if stale.
- **Effort:** Low

# Changelog

All notable changes to this framework are recorded here.

The framework follows informal semantic versioning during pre-1.0 development.

---

## v0.1.2 — 2026-06-17

### Added
- `governance-matrix.md` — authoritative mapping between risk, access, approval, audit, and review requirements; declared authoritative where governance classifications overlap or conflict
- `governance-model.md` Risk Owner and Executive Authority role definitions
- `governance-model.md` Risk Classification Authority section
- README "How to Read This Framework" and "Framework Structure" sections, plus reading order and Governance Matrix link
- `access-model.md` Category-Specific Limits section reconciling category caps with Matrix maxima
- `change-management.md` explicit declaration that change classification and risk classification are independent assessments
- `approval-model.md` reconciliation of pre-approved policy with the Approval Independence requirement (Category 1)

### Changed
- `approval-model.md` Core Principle and Final Principle rewritten to separate Approval from Risk Acceptance and align with governance-matrix.md
- `change-management.md` Approval Requirements table now defers to governance-matrix.md for risk-based approval routing
- `governance-model.md` Risk Owner definition aligned with governance-matrix.md
- Document headers no longer include a Version field; release version is declared by the git tag and the README

### Removed
- `change-management.md` undefined "High Risk Change" row from the Typical Approval table

### Fixed
- Casing of `prompt-security.md` reference in `multi-agent-governance.md`
- Markdown formatting of `governance-matrix.md` (headers, blockquotes, tables, separators, bullets)

### Notes
All material contradictions identified during cross-document review are now closed. Remaining open items are gaps and missing flows (Audit Function role, exception workflow, vendor-secret-incident taxonomy mapping) rather than contradictions.

---

## v0.1.1 — 2026-06-07

### Changed
- Repository structure and governance framework improvements
- See `git log v0.1.0..v0.1.1` for commit-level detail

---

## v0.1.0 — 2026-06-07

Initial public release.

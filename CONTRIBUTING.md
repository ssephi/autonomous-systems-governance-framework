# Contributing

Thank you for considering a contribution.

This framework is principle-led documentation, not code. Contributions are welcome from anyone operating, governing, auditing, or implementing autonomous systems in production.

---

## Quick Routing

| Contribution type | Channel |
|-------------------|---------|
| Typos, formatting, broken links | Pull Request |
| Substantive disagreements with framework content | Issue |
| New documents, structural changes, major framework changes | Discussion first |

---

## Before You Open a PR

- Read the README and `docs/governance-model.md` to understand the framework's principles and structure
- Skim `docs/governance-matrix.md` — it is authoritative where governance classifications overlap
- Check that your change does not contradict another document
- Match the existing document style (see below)

---

## Document Style

The framework follows a deliberate, terse style:

- Short, declarative sentences
- One idea per line
- `#` for section headings, `##` for sub-sections
- Lists use `-` bullets, not `*`
- Tables use proper markdown with `|` separators
- Use `---` as section separators
- No emojis
- No marketing language
- Avoid "should be considered" or "may potentially" — prefer "should" or "may"

Each document begins with a metadata blockquote:

```
> **Document:** Document Title  
> **Status:** Draft  
> **Last Reviewed:** YYYY-MM-DD  
> **Author:** Name  
> **Maintainer:** Name  
> **Applies To:** Autonomous Systems  
```

Trailing two spaces on each line are required for line breaks. The Version field is intentionally omitted; the release version is declared by the git tag and the README.

---

## Internal Consistency

The framework is intended to operate as a single system, not a collection of independent documents.

When proposing a change, consider:

- Does this contradict another document?
- Does this introduce a new role, classification, or authority not already defined?
- Does this map cleanly to `governance-matrix.md`?
- Does this require updating cross-references in other documents?

Reviewers will check for cross-document consistency.

---

## What Reviewers Look For

- Clarity and brevity
- Alignment with the seven foundational principles (see README)
- Internal consistency with other documents
- No introduction of new contradictions
- Correct use of the authoritative `governance-matrix.md` where classifications apply
- Style consistency

---

## Major Framework Changes

If you are proposing:

- A new document
- A new governance role
- A new classification taxonomy
- A change to `governance-matrix.md`
- A change to the README principles

Open a Discussion first. These changes affect the whole framework and benefit from broader review before implementation.

---

## Versioning and Releases

The framework follows informal semantic versioning during pre-1.0 development.

Releases are declared by:

- A git tag (`v0.x.y`)
- The version line in the README
- A CHANGELOG entry

Individual documents do not carry their own version number. They inherit the framework version.

Editorial changes (typos, formatting, link fixes) can be merged at any time and do not require a release.

Substantive changes are grouped into releases.

---

## Licence

By contributing, you agree that your contributions are licensed under the same terms as the rest of the repository: Creative Commons Attribution 4.0 International (CC BY 4.0).

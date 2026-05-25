# Learning Studio Directory

This workspace is now organized as a curated English learning library. The root is intentionally small so you can immediately see where each kind of material belongs.

## Root Structure

```text
~/Desktop/Learning Studio/
├── README_Directory.md
├── Product Lexicon/
├── Vaults/
├── Courses/
├── Libraries/
├── Wellbeing/
└── Assets/
```

## What Lives Where

- `Vaults/`
  Long-term note systems and Obsidian vaults.
- `Product Lexicon/`
  Product-facing terminology and naming notes.
- `Courses/`
  Guided learning packs and tutorial-style materials.
  Includes `VS_Code_Guide`, `English_Study`, and `Web_Foundations_Practice`.
- `Libraries/`
  Large reference collections, template libraries, reading material, and interview packs.
  Includes `Product_Manager_Library`, `Product_Manager_Interview_Kit`, `Reading_Room`, and `Web3_Product_Research`.
- `Wellbeing/`
  Personal training and routine playbooks.
- `Assets/`
  Standalone visual assets referenced by the library.

## Naming Rules

- Root sections use `Title_Case` with underscores.
- Vault chapter directories keep numeric prefixes and use English `snake_case`.
- User-maintained Markdown, TXT, and key image entry files use English `snake_case`.
- Large third-party PDF, DOC, PPT, XLS, and ZIP assets keep their original filenames unless they are top-level entry files.

## Path Governance

This workspace is managed by the global `workspace-path-governance` skill.

Recommended commands:

```bash
python3 ~/.codex/skills/workspace-path-governance/scripts/path_harness.py scan --config ~/.codex/skills/workspace-path-governance/configs/personal_learning.json
python3 ~/.codex/skills/workspace-path-governance/scripts/path_harness.py plan --config ~/.codex/skills/workspace-path-governance/configs/personal_learning.json
python3 ~/.codex/skills/workspace-path-governance/scripts/path_harness.py verify --config ~/.codex/skills/workspace-path-governance/configs/personal_learning.json
```

This workspace also has a one-time migration script in the same skill directory:

```bash
python3 ~/.codex/skills/workspace-path-governance/scripts/personal_learning_migrate.py
```

## Maintenance Scope

- Markdown links inside the maintained vaults use relative links.
- `Courses/Web_Foundations_Practice/` is treated as a lightweight local HTML learning surface.
- Obsidian workspace files are kept path-safe.
- Historical large template libraries are organized by container, not by deep-renaming every third-party file.
- Desktop English naming notes now live in `Product Lexicon/desktop_workspace_naming_glossary.md`.

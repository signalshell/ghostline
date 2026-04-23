Check whether this project's Refraction documentation is consistent with the current code.

## Steps

1. Check if `docs/system.md` exists. If not, report that Refraction is not initialized and suggest running `/refraction:init`.

2. Read `docs/system.md`. For each container listed, verify:
   - The container file exists at `docs/containers/[name].md`
   - The container file lists components, and each component file exists at `docs/components/[name].md`

3. For each L3 component file, verify:
   - Code pointers (file paths and function names) still exist in the codebase
   - Check the referenced file directly or run a targeted search

4. Scan for obvious drift:
   - New source files or directories that do not correspond to any documented component
   - Interfaces mentioned in docs that no longer exist in the code (changed endpoint paths, removed CLI flags, renamed config fields)

5. For each discrepancy found, check git history to determine which side changed more recently:
   - Run `git log -1 --format="%ci %s" -- <doc-file>` for the doc file
   - Run `git log -1 --format="%ci %s" -- <source-file>` for the relevant source file
   - If the source file changed more recently: the docs are stale. Suggest running `/refraction:sync`.
   - If the doc file changed more recently: the code has not caught up. Suggest running `/refraction:implement`.
   - If both changed at the same time or the signal is ambiguous: flag it explicitly.

6. Report findings in three categories:
   - **Docs are stale** — code changed after the docs; run `/refraction:sync`
   - **Code has not caught up** — docs changed after the code; run `/refraction:implement`
   - **Uncertain** — both sides changed around the same time, or the discrepancy cannot be attributed to either

## Rules

- Do not modify any files during this check — report only.
- Flag uncertainty explicitly. "I could not determine which side is authoritative" is more useful than a wrong verdict.

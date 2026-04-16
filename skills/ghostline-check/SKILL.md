---
description: Check whether Ghostline documentation is consistent with the current code. Use to audit docs for missing files, stale code pointers, or drift from the current codebase.
---

Check whether this project's Ghostline documentation is consistent with the current code.

## Steps

1. Check if `docs/system.md` exists. If not, report that Ghostline is not initialized and suggest running `/ghostline:ghostline-init`.

2. Read `docs/system.md`. For each container listed, verify:
   - The container file exists at `docs/containers/[name].md`
   - The container file lists components, and each component file exists at `docs/components/[name].md`

3. For each L3 component file, verify:
   - Code pointers (file paths and function names) still exist in the codebase
   - Run `grep -r "FunctionName" src/` or check the referenced file directly

4. Scan for obvious drift:
   - New source files or directories that don't correspond to any documented component
   - Interfaces mentioned in docs that no longer exist in the code (changed endpoint paths, removed CLI flags, renamed config fields)

5. Report findings in three categories:
   - **Missing docs**: components or containers in the code with no doc file
   - **Stale pointers**: code pointers in L3 files that no longer resolve
   - **Possible drift**: areas where docs may be out of date but you're not certain

## Rules

- Do not modify any files during this check — report only.
- Flag uncertainty explicitly. "I couldn't find X" is more useful than a false positive.

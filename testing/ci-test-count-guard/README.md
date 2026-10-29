# CI test-count guard

Stops a coding agent from deleting, skipping or weakening failing tests to make CI pass. Two parts: rules the agent reads, and a CI step that fails when the number of tests drops.

## 1. Add these rules to AGENTS.md (and CLAUDE.md if you use Claude Code)
```markdown
## Tests
- Never delete, skip, or weaken a failing test to make CI pass.
- If a test fails, fix the code. If you think the test itself is wrong, stop and ask me first.
- Never lower the number of tests in a change without saying so in the PR description.
```

## 2. Guard the test count in CI
GitHub Actions step (pytest; swap the count command for your runner):
```yaml
- name: Guard test count
  run: |
    count=$(pytest --collect-only -q | tail -n 1 | grep -oE '[0-9]+' | head -1)
    echo "tests: $count (minimum: ${{ vars.MIN_TESTS }})"
    test "$count" -ge "${{ vars.MIN_TESTS }}"
```
Set `MIN_TESTS` as a repo variable (Settings > Secrets and variables > Actions > Variables) and raise it when you add tests.

Jest: count with `npx jest --listTests | wc -l` (counts test files).

A passing CI run only means the tests that are left pass.

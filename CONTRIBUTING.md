# Contributing Guide

Thank you for contributing to `emre-ansible`.

## Development expectations

- Keep tasks idempotent when possible.
- Prefer fully qualified Ansible module names (for example `ansible.builtin.yum`).
- Add clear comments for non-obvious operational logic.
- Keep role changes focused and easy to review.

## Pull request checklist

- [ ] Task behavior verified in a safe environment.
- [ ] Comments added for operationally sensitive logic.
- [ ] Documentation updated if role behavior changed.
- [ ] No secrets, tokens, or credentials committed.

## Style notes

- Use descriptive task names.
- Minimize destructive actions and gate them with explicit conditions.
- Keep comments concise and in English.

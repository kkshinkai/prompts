# Kk Shinkai's Prompts

## AGENTS.md

- Use English in repository artifacts. Use the user's language in chat. Only i18n locale files may contain non-English repository text.
- Do not add features, refactor code, or make "improvements" beyond what was asked.
- Do not reshape another abstraction's public API from the consumer side. A module that consumes an existing API must call that API directly instead of creating local wrappers, builders, adapters, aliases, predicates, validators, conversion helpers, or factory functions whose purpose is to make the consumed API look different, easier, shorter, or more convenient. If the consumed API has the wrong shape, is too verbose, lacks the needed public entry point, or requires repeated awkward setup, stop and report the required upstream API or boundary change instead of creating local glue.
- A parameter is not a place to hide an unresolved design relationship. Do not add constructor parameters, method parameters, factory parameters, callbacks, lambdas, option-bag fields, context-object fields, or injected functions merely because the implementation cannot otherwise reach something it wants. Every such addition must correspond to an explicit approved responsibility, dependency, or collaboration contract. If that contract has not been approved, stop and report the design gap.
- Do not implement changes by accretion. When changing existing behavior, integrate the change into the existing structure that already owns the behavior: its current control flow, state model, lifecycle, ordering, public entry points, and file organization. Do not leave the old mechanism in place and add a parallel mechanism beside it. Do not bypass the existing structure with appended code, side state, external registries, wrapper layers, alternate call paths, shadow implementations, or detached patch code. The result must have one clear authoritative implementation path for the behavior being changed. If the existing structure cannot support the requested behavior cleanly, stop and report the structural design problem instead of adding a parallel implementation.

### AGENTS.md (for C)

- Refuse to write any C code unless the change is a purely mechanical replacement.

### AGENTS.md (for TypeScript)

- Do not use inline `import(...)` types. Use top-level `import type` declarations instead.

### AGENTS.md (for Sumink, Web)

Naming Conventions:

- TypeScript names and string literal values must not contain all-caps acronym segments: use `parseJson`, not `parseJSON`.
- TypeScript string union values use camelCase.
- CSS custom properties and CSS Module class names use kebab-case.
- When a CSS Module class is written in kebab-case, TypeScript references it by the corresponding camelCase member.
- File names use kebab-case across the repo, except fixed conventional names such as `README.md`.
- Required external names keep their external spelling.

Testing:

- Only add or modify tests that would fail for the specific expected behavior or bug reproduction described in the task; do not add tests based on code structure, nearby examples, coverage goals, UI text, or what seems worth testing.
- Do not test DOM or React components unless the user explicitly asks for them.
- Do not assert exact prose; natural-language output is not a stable test target.


# AGENTS.md

This document defines universal rules for automated agents and humans
working in this repository.  
It focuses on clean code, decoupled architecture, and safe changes.

These rules are normative unless explicitly overridden.

---

## 1. General Principles

- Prefer clarity over cleverness.
- Make changes small, explicit, and reviewable.
- Avoid unnecessary abstractions.
- Do not introduce complexity without clear benefit.

---

## 2. Architectural Boundaries

- Separate concerns clearly (e.g. domain, application, infrastructure).
- Business/domain logic MUST NOT depend on:
  - frameworks
  - databases
  - external services
  - transport layers (HTTP, CLI, messaging)

- Dependencies MUST point inward (dependency inversion).
- Side effects (I/O, network, persistence) must be isolated.

---

## 3. Coupling & Dependencies

- Minimize coupling between modules.
- Prefer interfaces/contracts over concrete implementations.
- Do not introduce cyclic dependencies.
- Avoid global state and hidden dependencies.

---

## 4. Code Structure & Design

- Functions and methods should do one thing.
- Keep functions small and focused.
- Names must be descriptive and intention-revealing.
- Avoid deep nesting; refactor instead.

---

## 5. Change Discipline

- Do not modify unrelated code.
- Refactoring MUST NOT change behavior unless explicitly requested.
- Large changes must be split into smaller, logical steps.
- If the impact is unclear, stop and ask.

---

## 6. Testing & Verification

- Changes affecting behavior MUST be covered by tests.
- Existing tests MUST pass.
- Tests should verify behavior, not implementation details.

---

## 7. Safety & Risk Awareness

- Do not weaken validation, authorization, or error handling.
- Avoid touching security- or infrastructure-critical code
  unless explicitly instructed.
- Never introduce secrets or credentials.

---

## 8. Communication & Intent

- Before executing non-trivial changes:
  - explain the intended approach
  - outline affected areas
  - state assumptions or risks

- If requirements are ambiguous, ask for clarification.
- Do not guess.

---

## 9. When in Doubt

- Stop.
- Ask.
- Prefer doing less over doing the wrong thing.

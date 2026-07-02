# Onboarding Patterns

The file has no explicitly labeled onboarding flow, but the home screen personalizes ("Hi, Steffy", avatar) and surfaces empty/starter affordances ("Schedule a trip now", "Continue planning"), implying a first-run setup. This documents the **inferred/recommended** onboarding built from existing components and tokens — do not introduce new UI primitives.

## Principles

- **Fast to value:** minimize steps before the user reaches the Home dashboard.
- **Personalize early:** capture the first name (used in the 24pt "Hi, {name}" greeting) and generate the avatar initial (Green 800 circle).
- **Progressive disclosure:** ask only what's needed to plan a first trip; defer the rest to contextual prompts.
- **Skippable:** every step offers a low-emphasis `Text Button` "Skip".

## Recommended flow

1. **Welcome / value prop** — `Banner template` hero image + 24pt Bold headline + primary `Button`; pager dots for a 2–3 slide carousel.
2. **Identity** — single `Text Form` (Type=Info) for name; primary `Button` "Continue", `Text Button` "Skip".
3. **First trip (optional)** — destination `Text Form` (Type=Search) + dates via the date strip (`Active date`).
4. **Land on Home** — show `Trip thumbnail` if a trip was created, otherwise the empty state (see [empty-states.md](./empty-states.md)).

## Component & token usage

- Carousel slide: `Banner template`, `radius-lg`, `shadow`; pager dots (~9×51 indicator) below, `gap-15`.
- Inputs: `Text Form` per [semantic-tokens.md](../design-tokens/semantic-tokens.md#inputs-text-form).
- Primary action: full-width `Button` (Green 700, 48px, `radius-md`).
- Screen scaffold identical to [layout-patterns.md](./layout-patterns.md) — 25px padding, `gap-15`.
- Transitions: forward = slide-in right `motion/slow`; back = pop `motion/base`.

## Rules

Max 3–4 steps to Home. Always skippable. One primary `Button` per step; secondary actions are `Text Button`. Show progress (pager dots or step count). Reuse existing components/tokens only. Respect [accessibility.md](../design-tokens/accessibility.md): labeled inputs, ≥44px targets, visible focus.

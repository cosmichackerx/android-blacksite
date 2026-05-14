# android-blacksite
A tactical Android development playbook containing elite prompts, workflows, UI strategies, debugging systems, and AI-assisted engineering techniques for building production-grade apps at hackathon speed

### Your Full Stack Should Be

- Kotlin
- Jetpack Compose
- Material 3
- MVVM
- Navigation Compose
- Hilt
- Retrofit/Ktor
- Coil
- Room
- Coroutines + Flow
- ViewModel
- Clean Architecture


You should:

- provide screenshots
- define architecture
- define design system
- define spacing rules
- define typography
- define responsiveness
- define performance constraints
- define reusable composables
- define navigation structure

**Figma Screenshot → Cursor Prompt**
```
Analyze this UI carefully.

Recreate it in Jetpack Compose with:
- exact spacing
- responsive layout
- clean Material 3 architecture
- reusable composables
- production-grade code
- proper typography hierarchy
- smooth animations
- dark/light theme support
- no hardcoded dimensions unless necessary

Use:
- Kotlin
- Jetpack Compose
- Material 3

Return complete code.
```

**Here are the most effective, token-efficient prompting templates for Cursor** (especially useful on Pro plan):

### 1. Universal Strong Structure (Best All-Rounder)
```markdown
## Goal
[One clear sentence what you want]

## Context
- Tech stack: [e.g.Android,Kotlin,Xml,Jetpack Compose,Gradle]
- Reference files: @file1 @folder/utils

## Current Behavior
[Describe what's happening now]

## Desired Behavior
[What should happen instead]

## Acceptance Criteria
- [Bullet list of must-haves]
- [Edge cases]

## Constraints
- Do not change public API
- Follow existing patterns in @existing-component
- Keep it minimal, no new dependencies
- Output only SEARCH/REPLACE blocks
```

### 2. Plan-First Prompt (Saves huge usage)
```markdown
Plan only. Do not write any code yet.

Goal: [your goal]

Context: @relevant-files

Think step-by-step:
1. Analyze current code
2. List files that need changes
3. Outline risks and edge cases
4. Propose the simplest implementation

Then ask for my approval before implementing.
```

### 3. Bug Fix (Very Efficient)
```markdown
This bug: [describe error + steps to reproduce]

File: @buggy-file.tsx

Fix it safely:
- Add proper guards
- Follow existing error handling patterns
- Add a short comment explaining the fix
- Output only SEARCH/REPLACE + 1-2 sentence explanation
Be concise.
```

### 4. Refactor Prompt
```markdown
Refactor @src/services/api.ts to use [new approach, e.g. TanStack Query].

Constraints:
- Keep the exact same public API
- Maintain all existing behavior
- Follow patterns from @other-service.ts
- Plan first, then implement minimal changes
```

### 5. Feature Implementation (After Plan Approval)
```markdown
Implement the approved plan.

- Follow existing code style and patterns
- Add/update tests where relevant
- Output clean SEARCH/REPLACE blocks per file
- After changes, suggest what to test manually
```

### 6. Write Tests
```markdown
Write tests for @component.tsx

Cover:
- Happy path
- Edge cases: [list them]
- Error states

Use existing test patterns from @tests/example.test.tsx
Output only the test file changes.
```

### 7. Quick Tab / Chat Prompt (Low Token)
```markdown
Be concise. 
Follow patterns in @reference-file.tsx
[Your request]
```

### Pro Tips for Lower Usage:
- Always start with **Plan only** for big tasks.
- Use **Auto** mode + Tab completions as much as possible.
- Reference files with `@filename` instead of pasting large code.
- Add a good `.cursorrules` file (project-specific rules) so you don’t have to repeat instructions.
- End prompts with: `"Output only SEARCH/REPLACE blocks"` or `"Be concise"`.

Would you like me to give you:
- A ready-to-use `.cursorrules` template?
- Templates for a specific tech stack (Android,Kotlin,Xml,Jetpack Compose,Gradle)?
- Or more advanced Agent/Composer prompts?

Just tell me your main framework/language!

**Here are advanced prompting templates optimized for Cursor’s Agent / Composer mode** (especially powerful with Plan Mode + YOLO mode enabled).

### 1. Master Plan-First Agent Prompt (Highly Recommended)
```markdown
Plan only. Do not write or edit any code yet.

Goal: [Clear one-sentence goal]

Context: @relevant-file.tsx @folder/ @another-important-file

Current behavior: [Describe what's there now]

Desired behavior: [What should happen]

Acceptance Criteria:
- [Bullet list]
- [Must-have edge cases]

Constraints / Non-goals:
- Do not change public APIs
- Follow patterns in @canonical-example.tsx
- No new dependencies
- Keep changes minimal

Investigate the codebase, then output:
1. Step-by-step implementation plan with files to change
2. Potential risks and edge cases
3. Questions for me (if any)

Ask for approval before proceeding.
```

### 2. Full Feature Implementation (After Plan Approval)
```markdown
Implement the approved plan.

Rules:
- Follow existing code style and patterns exactly
- Use @reference-file for examples
- Add/update relevant tests
- Run build/typecheck/lint as needed and fix issues
- Output clean unified diffs per file
- At the end, provide a short testing checklist
```

### 3. TDD / Self-Verifying Agent Prompt (Great for YOLO Mode)
```markdown
Use test-driven development.

1. First, write comprehensive tests for the following:
   - Happy path
   - Edge cases: [list them]
   - Error states

2. Run the tests (they should fail initially).

3. Then implement the code that makes all tests pass.

4. Iterate automatically (run tests, fix failures) until everything passes.

Use existing test patterns from @tests/example.test.ts
```

### 4. Safe Refactor Agent Prompt
```markdown
Refactor @target-file.tsx to [goal, e.g. reduce duplication / improve performance / modernize].

Constraints (critical):
- Do NOT change external/public behavior or API
- Maintain 100% existing functionality
- Follow patterns from @existing-good-example.tsx
- Add/update tests to prove equivalence

Output:
- Root cause of current complexity
- Before/after summary
- Unified diffs only
```

### 5. Advanced Debugging / Root Cause Agent
```markdown
Debug this issue:

[Error message + steps to reproduce]

Context: @buggy-file.tsx @related-service.ts

Steps:
1. Investigate codebase for similar patterns
2. Add strategic logging if needed
3. Propose 2-3 likely root causes with evidence
4. Implement the minimal fix
5. Add regression test
6. Verify by running relevant tests/commands

Be conservative with changes.
```

### 6. YOLO / Autonomous Loop Prompt
```markdown
Work autonomously until the task is complete.

Task: [detailed description]

Allowed actions: run tests, build, lint, create files, etc.
Success criteria: [clear measurable outcome, e.g. all tests pass + no lint errors]

Continue iterating and fixing issues until done.
Update .cursor/scratchpad.md with "DONE" when complete.
```

### 7. Multi-File Complex Feature
```markdown
Build [feature name].

Tech stack & patterns: Follow @src/components/ canonical examples

Required files to touch:
- Backend: ...
- Frontend: ...
- Tests: ...

Constraints:
- [list]

Output format: Plan first → get approval → implement in small safe steps.
```

### Pro Tips for Advanced Agent Use:
- **Toggle Plan Mode** (`Shift + Tab`) for anything non-trivial.
- Always add **Constraints** and **Non-goals** — this prevents scope creep.
- Use `@filename`, `@folder/`, and `@Past Chats` heavily.
- End prompts with clear **output format** instructions.
- For long-running tasks, combine with **YOLO mode** + custom commands.
- After big changes, ask: `"Run pre-PR checks and fix everything until clean."`

Would you like me to customize these templates for a specific stack (Next.js, Python/FastAPI, etc.) or create a strong `.cursorrules` file to go with them? Just share your main tech stack!

# GitHub Copilot Prompt / Instructions for Feature Implementation

Here's a ready-to-use **Copilot instruction prompt** you can place in your `.github/copilot-instructions.md` file or use directly in Copilot Chat:

---

## 📄 `.github/copilot-instructions.md`

```markdown
# Copilot Instructions – Feature Implementation Guide

## 🎯 Primary Objective
When implementing any feature or task, follow these instructions strictly and in order:

---

## 1. 📋 Read & Understand the Jira Ticket

- Read the Jira ticket title, description, and all **Acceptance Criteria (AC)** carefully.
- Do NOT start coding until every AC is clearly understood.
- If the ticket has sub-tasks, treat each sub-task as a separate unit of work.
- Map each AC to a specific implementation step before writing any code.
- Ask clarifying questions (in comments) if any AC is ambiguous.

**Checklist before coding:**
- [ ] All ACs are read and understood
- [ ] Edge cases mentioned in the ticket are noted
- [ ] Dependencies or blocked items are identified

---

## 2. 🎨 Read & Follow the Figma Design (Desktop First)

- Always refer to the **Figma desktop design** as the source of truth for UI.
- Match the following exactly from Figma:
  - Layout and spacing (padding, margin, gap)
  - Typography (font size, weight, line height)
  - Colors (use existing design tokens / CSS variables — do NOT hardcode hex values)
  - Component states: default, hover, focus, disabled, error, loading
  - Responsive breakpoints if defined in Figma
- Do NOT invent UI elements that are not in the Figma design.
- If a Figma component maps to an existing design system component, USE that component.

---

## 3. 🏗️ Follow the Existing Architecture

- Before writing any new code, **scan the existing codebase** to understand:
  - Folder structure (features/, components/, hooks/, services/, utils/, etc.)
  - State management approach (Redux / Zustand / Context API / React Query, etc.)
  - API layer pattern (axios instance, custom hooks, service files, etc.)
  - Routing conventions (file-based, config-based, nested routes, etc.)
  - Error handling patterns
- Place new files in the **same location** as similar existing features.
- Do NOT introduce new architectural patterns unless explicitly asked.
- Reuse existing utility functions, hooks, and helpers — do not duplicate logic.

---

## 4. 🧩 Follow Existing Coding Patterns

### React Components
- Match the **component structure** already used in the project:
  - Functional components with hooks (no class components unless existing codebase uses them)
  - Props interface/type defined at the top of the file (TypeScript)
  - Default exports vs named exports — follow what's already used
  - Component file naming convention (PascalCase.tsx, index.tsx, etc.)

### Styling
- Use the **same styling approach** already in the project:
  - CSS Modules → use `styles.className`
  - Styled Components → follow existing theme usage
  - Tailwind CSS → use existing utility class patterns
  - SCSS/SASS → follow existing nesting and variable conventions
- Do NOT mix styling approaches.
- Use existing **design tokens, CSS variables, or theme values** for colors, spacing, and typography.

### Design System Components
- Always check if a **design system / UI library component** already exists before creating a new one.
  - Examples: Button, Input, Modal, Dropdown, Table, Toast, etc.
- Import from the same library already used (e.g., MUI, Ant Design, Chakra UI, 
  internal design system).
- Pass props in the same way as other usages in the codebase.
- Do NOT re-implement components that already exist in the design system.

### TypeScript
- Define proper types/interfaces — no use of `any` unless already a pattern in the codebase.
- Follow existing type file locations (types/, interfaces/, models/).

### Testing
- If tests exist for similar components/features, write tests in the same style.
- Follow existing test file naming and folder conventions.

---

## 5. ✅ Implementation Checklist

Before submitting / completing the task, verify:

- [ ] All Acceptance Criteria from the Jira ticket are implemented
- [ ] UI matches the Figma desktop design pixel-accurately
- [ ] No new architecture patterns introduced without discussion
- [ ] Existing design system components used wherever applicable
- [ ] Styling follows the existing approach (no mixed styles)
- [ ] No hardcoded values (colors, strings, magic numbers) — use constants/tokens
- [ ] No duplicate logic — reused existing hooks/utils
- [ ] TypeScript types are properly defined
- [ ] No console.log or debug code left behind
- [ ] Code is clean, readable, and follows existing naming conventions

---

## 6. 💬 Copilot Chat Usage Tips

When asking Copilot Chat for help, use prompts like:

> "Implement the [feature name] based on the following AC: [paste AC here]. 
>  Follow the same pattern as [existing similar component path]."

> "Generate a React component for [UI element] matching this Figma spec: 
>  [describe layout]. Use the same styling approach as [existing file path]."

> "Refactor this to follow the same pattern used in [reference file]."

---

## ⚠️ Hard Rules (Never Violate)

1. **Never** hardcode colors, spacing, or text strings that should come from tokens/constants.
2. **Never** create a new component if one already exists in the design system.
3. **Never** change the existing folder structure or architecture without explicit approval.
4. **Never** skip reading the full Jira AC before implementing.
5. **Never** implement UI without cross-checking with the Figma design.
```

---

## 🚀 How to Use This

| Method | How |
|---|---|
| **Persistent Instructions** | Save as `.github/copilot-instructions.md` in your repo root — Copilot will auto-read it |
| **Copilot Chat** | Paste the relevant sections directly into the chat before asking your question |
| **VS Code Custom Instructions** | Add to VS Code Settings → Copilot → Custom Instructions |
| **Cursor AI** | Add to `.cursorrules` file in repo root |

---

> 💡 **Pro Tip**: For each new ticket, start your Copilot Chat session with:
> *"I'm working on Jira ticket [ID]. Here are the ACs: [paste]. The Figma design shows [describe]. Follow `.github/copilot-instructions.md`."*

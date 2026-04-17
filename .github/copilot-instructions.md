# 🤖 Copilot Instructions for Jira Ticket Implementation

## 🎯 Objective
You are assisting in implementing a Jira ticket. Follow the requirements strictly and produce production-quality code.

---

## 📌 Jira Ticket Details
- **Ticket ID:** {{JIRA_TICKET_ID}}
- **Title:** {{TITLE}}
- **Description:** 
{{DESCRIPTION}}

- **Acceptance Criteria:**
{{ACCEPTANCE_CRITERIA}}

- **Priority:** {{PRIORITY}}
- **Story Points:** {{STORY_POINTS}}

---

## 🧠 Context
- Tech Stack: {{React / Node / Java / etc}}
- Framework: {{Next.js / Spring Boot / etc}}
- Codebase Patterns: Follow existing patterns in the repository
- Architecture: {{MVC / Microservices / etc}}

---

## 📂 Scope of Work
Clearly define what should be done:

- [ ] Identify relevant files/modules
- [ ] Add / update business logic
- [ ] Write reusable, clean, and testable code
- [ ] Maintain backward compatibility (unless specified)
- [ ] Add proper error handling
- [ ] Add logs where necessary

---

## 🚫 Constraints
- Do NOT introduce breaking changes
- Do NOT use deprecated libraries
- Do NOT hardcode values (use env/config)
- Follow existing linting and formatting rules
- Keep performance in mind

---

## 🧪 Testing Requirements
- Add unit tests for all new logic
- Ensure existing tests pass
- Cover edge cases
- Mock external dependencies if needed

---

## 📏 Coding Standards
- Follow project naming conventions
- Write meaningful variable and function names
- Keep functions small and modular
- Add comments only where necessary (avoid obvious comments)

---

## 📤 Expected Output
Copilot should:

1. Identify impacted files
2. Show code changes (diff or full code)
3. Include test cases
4. Explain assumptions (if any)

---

## ⚠️ Edge Cases to Consider
- Null / undefined inputs
- API failures / timeouts
- Invalid user inputs
- Large data handling

---

## 🧩 Example (Optional)
Provide similar implementation if available in repo.

---

## 🏁 Definition of Done
- All acceptance criteria satisfied
- Code builds successfully
- Tests pass
- Code reviewed and readable

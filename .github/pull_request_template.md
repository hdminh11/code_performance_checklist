## 📌 PR Objective
Add tools to improve code performance

## 🛠️ Main Changes
- Add PR template
- Apply eslint
- Apply prettier

## 🔍 Impact Assessment
- [x] Affects other services/modules?  
- [x] Requires database migration?  
- [x] Performance impact? (If yes → include measurement data)  
- [x] Update metrics/logs for post-deploy monitoring?  
- [x] Rollback plan available?  

---

## ✅ Ticket Checklist
- [x] Create a branch based on the ticket code for the new version.
- [x] Ensure each commit message includes the parent ticket code.
- [x] Update the database as required: apply migrations (DB/DynamoDB), configure Secret Manager, and update Amplify. 
- [x] Document the Impact / Solution / Root Causes.
- [x] Verify source code changes in the SSO portal (client/server) and align them with the corresponding ticket code (BETA → PROD).
- [ ] Verify source code changes in the Admin portal (client/server) and align them with the corresponding ticket code (BETA → PROD).

---

## 🔒 Quality Checklist
- [ ] ESLint + Prettier compliance  
- [ ] Unit/integration tests for new logic  
- [ ] TypeScript used  
- [ ] Clear variable/function/class names  
- [ ] No duplicated code  
- [ ] No hardcoded config/secret  

## 📌 PR Objective
Add tools to improve code performance

## 🛠️ Main Changes
- Add PR template
- Apply eslint
- Apply prettier

## 🔍 Impact Assessment
- [ ] Affects other services/modules?  
- [ ] Requires database migration?  
- [ ] Performance impact? (If yes → include measurement data)  
- [ ] Update metrics/logs for post-deploy monitoring?  
- [ ] Rollback plan available?  

---

## ✅ Ticket Checklist
- [ ] Create a branch based on the ticket code for the new version.
- [ ] Ensure each commit message includes the parent ticket code.
- [ ] Update the database as required: apply migrations (DB/DynamoDB), configure Secret Manager, and update Amplify. 
- [ ] Document the Impact / Solution / Root Causes.
- [ ] Verify source code changes in the SSO portal (client/server) and align them with the corresponding ticket code (BETA → PROD).
- [ ] Verify source code changes in the Admin portal (client/server) and align them with the corresponding ticket code (BETA → PROD).

---

## 🔒 Quality Checklist
- [ ] ESLint + Prettier compliance  
- [ ] Unit/integration tests for new logic  
- [ ] TypeScript used  
- [ ] Clear variable/function/class names  
- [ ] No duplicated code  
- [ ] No hardcoded config/secret  

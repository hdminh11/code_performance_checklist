## 📌 PR Objective
<!-- Briefly describe the reason and goal of this PR -->

## 🛠️ Main Changes
<!-- List the main changes (API, logic, UI, database, etc.) -->

## 🔍 Impact Assessment
- [ ] Affects other services/modules?  
- [ ] Requires database migration?  
- [ ] Performance impact? (If yes → include measurement data)  
- [ ] Update metrics/logs for post-deploy monitoring?  
- [ ] Rollback plan available?  

---

## ✅ Performance Checklist (Backend & Frontend)

<details>
<summary>📖 Detailed Guide</summary>

### Backend
1. **No N+1 queries**  
   - *Problem*: Repeated queries for related data → slow performance.  
   - *Check*: Enable SQL logs/profiler, use JOIN or `IN` queries.
2. **Queries are indexed**  
   - *Problem*: No index → DB full scan.  
   - *Check*: Use `EXPLAIN` query, add index if needed.
3. **No loading large datasets entirely into memory**  
   - *Problem*: Causes out-of-memory issues.  
   - *Check*: Always use LIMIT + pagination or streaming.
4. **API responses contain no extra data**  
   - *Problem*: Wastes bandwidth, increases parsing time.  
   - *Check*: Select only necessary fields.
5. **Proper caching applied**  
   - *Problem*: Repeated queries/APIs waste CPU/DB resources.  
   - *Check*: Use Redis/memory cache, HTTP cache headers.
6. **No event loop blocking**  
   - *Problem*: Node.js is single-threaded → sync code blocks other requests.  
   - *Check*: Avoid sync I/O, use worker threads if necessary.

### Frontend
1. **No unnecessary re-renders**  
   - *Problem*: Frequent React re-renders waste CPU.  
   - *Check*: Use React DevTools Profiler, optimize with `memo`, `useMemo`, `useCallback`.
2. **Reasonable bundle size**  
   - *Problem*: Large bundle → higher TTFB, TTI.  
   - *Check*: Webpack Bundle Analyzer/Vite Visualizer, optimize imports.
3. **Code splitting / lazy loading**  
   - *Problem*: Loading all JS upfront even if unused.  
   - *Check*: Use dynamic imports, `React.lazy`.
4. **Prefetch / cache important data**  
   - *Problem*: Slow loading of critical data → poor UX.  
   - *Check*: Prefetch APIs, cache with localStorage/IndexedDB/SWR.

</details>

### Backend
- [ ] No N+1 queries  
- [ ] Queries are indexed  
- [ ] No large dataset loaded fully into memory  
- [ ] API responses contain only necessary data  
- [ ] Proper caching applied  
- [ ] No event loop blocking  

### Frontend
- [ ] No unnecessary re-renders  
- [ ] Reasonable bundle size  
- [ ] Code splitting / lazy loading applied  
- [ ] Prefetch / cache important data  

---

## 🔒 Quality Checklist
- [ ] ESLint + Prettier compliance  
- [ ] Unit/integration tests for new logic  
- [ ] TypeScript used  
- [ ] Clear variable/function/class names  
- [ ] No duplicated code  
- [ ] No hardcoded config/secret  

---

## 📐 SOLID Checklist
- [ ] **S**: A module/class has only one reason to change  
- [ ] **O**: Open for extension, closed for modification of core logic  
- [ ] **L**: Subclasses can replace superclass without issues  
- [ ] **I**: Small and specific interfaces  
- [ ] **D**: Depend on abstractions, not on concrete implementations  

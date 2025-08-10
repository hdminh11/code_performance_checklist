## 📌 Mục tiêu PR
<!-- Mô tả ngắn gọn lý do và mục tiêu của PR này -->

## 🛠️ Thay đổi chính
<!-- Liệt kê các thay đổi chính (API, logic, UI, database, ...) -->

## 🔍 Impact Assessment
- [ ] Có ảnh hưởng đến service/module khác?  
- [ ] Cần migration database?  
- [ ] Ảnh hưởng performance? (Nếu có → kèm số liệu đo)  
- [ ] Cập nhật metric/log để theo dõi sau deploy?  
- [ ] Có rollback plan?

---

## ✅ Performance Checklist (Backend & Frontend)

<details>
<summary>📖 Hướng dẫn chi tiết</summary>

### Backend
1. **Không có query N+1**  
   - *Vấn đề*: Query lặp lại nhiều lần khi lấy dữ liệu liên quan → chậm.  
   - *Check*: Bật log SQL / profiler, dùng JOIN hoặc `IN` query.
2. **Query đã index**  
   - *Vấn đề*: Không index → DB full scan.  
   - *Check*: `EXPLAIN` query, thêm index nếu cần.
3. **Không load toàn bộ data lớn vào memory**  
   - *Vấn đề*: Gây out-of-memory.  
   - *Check*: Luôn LIMIT + phân trang hoặc stream.
4. **API response không dư data**  
   - *Vấn đề*: Tốn băng thông, parse lâu.  
   - *Check*: Select field cần thiết.
5. **Có cache hợp lý**  
   - *Vấn đề*: Query/API lặp lại gây tốn CPU/DB.  
   - *Check*: Redis/memory cache, HTTP cache headers.
6. **Không block event loop**  
   - *Vấn đề*: Node.js single-thread → code sync chặn request khác.  
   - *Check*: Tránh sync I/O, dùng worker thread nếu cần.

### Frontend
1. **Không re-render không cần thiết**  
   - *Vấn đề*: React render lại nhiều lần tốn CPU.  
   - *Check*: Dùng React DevTools Profiler, tối ưu với `memo`, `useMemo`, `useCallback`.
2. **Bundle size hợp lý**  
   - *Vấn đề*: Bundle lớn → TTFB, TTI cao.  
   - *Check*: Webpack Bundle Analyzer/Vite Visualizer, import tối ưu.
3. **Code splitting / lazy loading**  
   - *Vấn đề*: Tải toàn bộ JS dù chưa dùng.  
   - *Check*: Dynamic import, React.lazy.
4. **Prefetch / cache dữ liệu quan trọng**  
   - *Vấn đề*: Load dữ liệu quan trọng chậm → UX tệ.  
   - *Check*: Prefetch API, cache bằng localStorage/IndexedDB/SWR.

</details>

### Backend
- [ ] Không có query N+1  
- [ ] Query đã index  
- [ ] Không load toàn bộ data lớn vào memory  
- [ ] API response không dư data  
- [ ] Có cache hợp lý  
- [ ] Không block event loop  

### Frontend
- [ ] Không re-render không cần thiết  
- [ ] Bundle size hợp lý  
- [ ] Code splitting / lazy loading  
- [ ] Prefetch / cache dữ liệu quan trọng  

---

## 🔒 Quality Checklist
- [ ] Tuân thủ ESLint + Prettier  
- [ ] Có unit/integration test cho logic mới  
- [ ] Dùng TypeScript  
- [ ] Tên biến/hàm/class rõ ràng  
- [ ] Không lặp lại code  
- [ ] Không hardcode config/secret  

---

## 📐 SOLID Checklist
- [ ] **S**: Module/class chỉ có 1 lý do thay đổi  
- [ ] **O**: Có thể mở rộng mà không sửa core logic  
- [ ] **L**: Subclass thay thế superclass an toàn  
- [ ] **I**: Interface nhỏ gọn  
- [ ] **D**: Phụ thuộc abstraction, không phụ thuộc implementation  

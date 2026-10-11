# SortLab - Interactive Sorting Algorithm Game
> โครงการเกมการศึกษาด้านวิทยาการคอมพิวเตอร์: Interactive Sorting Algorithm Game (Single-file Web Application)

---

## 1. วัตถุประสงค์และแนวคิดของเกม (Concept)

**SortLab** เป็นเกมจำลองการแก้ปัญหาเชิงอัลกอริทึม (Algorithmic Puzzle & Educational Game) ที่พัฒนาขึ้นโดยให้ **Sorting Algorithms เป็นแกนหลักของการเล่น (Core Game Mechanic)** เพื่อให้ผู้เล่นได้เข้าใจกลไกและขั้นตอนการทำงานของอัลกอริทึมอย่างเป็นรูปธรรม

### ปรัชญาการออกแบบ (Design Philosophy)
- **Focused & Minimalist:** ออกแบบสไตล์ Modern Developer Interface (Dark Slate/Zinc Palette) สะอาดตา ชัดเจน ปราศจากองค์ประกอบตกแต่งที่รกรุงรัง (No AI Slop / No Fluff)
- **Mechanics as Algorithms:** กติกาในแต่ละโหมดถูกจำลองมาจากข้อจำกัดทางคณิตศาสตร์และตรรกะของอัลกอริทึมโดยตรง
- **Educational Big-O Grounding:** ผู้เล่นจะได้เห็นความแตกต่างของจำนวนการเปรียบเทียบ (Comparisons) และการสลับตำแหน่ง (Swaps) ของแต่ละอัลกอริทึมในเชิงประจักษ์

---

## 2. โหมดการเล่น (Game Modes)

ตัวเกมประกอบด้วย 4 โหมดหลักที่ตอบโจทย์ทั้งการฝึกฝน, การแข่งขัน และการคิดวิเคราะห์:

### 1. โหมดบททดสอบ (Algorithm Puzzle)
ผู้เล่นสวมบทบาทปฏิบัติตามกฎของแต่ละอัลกอริทึม:
- **Bubble Sort:** เปรียบเทียบคู่ติดกัน $arr[j]$ และ $arr[j+1]$ ถ้าตัวซ้ายมากกว่าตัวขวาให้กด "สลับ (Swap)" หากเรียงถูกต้องแล้วให้กด "ข้าม (Keep)" ค่าที่มากที่สุดจะถูกล็อคไว้ที่ท้ายแถวทีละรอบ
- **Selection Sort:** สแกนค้นหาค่าที่น้อยที่สุด (Minimum) จากโซนที่ยังไม่จัดเรียง แล้วกดยืนยันเพื่อนำมาสลับกับตำแหน่งแรกสุดของรอบ
- **Insertion Sort:** หยิบสมาชิกทีละตัว ($Key$) แล้วเลือกตำแหน่งในโซนที่เรียงแล้วทางซ้ายเพื่อแทรกให้ถูกต้อง (จำลองการจัดไพ่ในมือ)
- **Quick Sort:** สังเกตค่า $Pivot$ แล้วแยกแยะว่าข้อมูลที่ตรวจควรจัดไว้ฝั่งซ้าย ($< Pivot$) หรือฝั่งขวา ($\ge Pivot$) ตามหลัก Lomuto Partitioning

### 2. โหมดแข่งกับ AI (Race Duel)
- แข่งจัดเรียงข้อมูลกับหุ่นยนต์ AI แบบ Real-time ในเลนขนานกัน
- ผู้เล่นคลิกเลือก 2 แท่งเพื่อสลับตำแหน่งอย่างอิสระ แข่งกับ AI ที่ประมวลผลทีละสเต็ปตามอัลกอริทึมที่เลือก (Bubble, Selection, Insertion หรือ Quick Sort) พร้อมปรับความเร็วได้

### 3. โหมดวิเคราะห์ความซับซ้อน (Complexity Quiz)
- ผู้เล่นต้องวิเคราะห์รูปแบบชุดข้อมูลในสถานการณ์จริง เช่น:
  - ข้อมูลเกือบเรียงสมบูรณ์ (Nearly Sorted) $\rightarrow$ เหมาะกับ **Insertion Sort** ($O(n)$)
  - ข้อมูลที่ต้องการลดจำนวนการสลับ (Minimum Swaps) $\rightarrow$ เหมาะกับ **Selection Sort** ($O(n)$ Swaps)
  - ข้อมูลสุ่มทั่วไปขนาดใหญ่ $\rightarrow$ เหมาะกับ **Quick Sort** ($O(n \log n)$)

### 4. ห้องทดลองอิสระ (Sandbox Lab)
- Visualizer ควบคุมการจำลองทีละก้าว (Step-by-step) หรือเล่นอัตโนมัติ (Play/Pause)
- เลือกขนาดข้อมูลและรูปแบบได้ (สุ่ม, เกือบเรียงแล้ว, เรียงย้อนกลับ) พร้อมตัวอธิบายขั้นตอนในแต่ละสเต็ป

---

## 3. ตารางวิเคราะห์ Sorting Algorithms & Big-O Complexity

| Algorithm | Best Case | Average Case | Worst Case | Space Complexity | จุดเด่นในเกม |
| :--- | :---: | :---: | :---: | :---: | :--- |
| **Bubble Sort** | $O(n)$ | $O(n^2)$ | $O(n^2)$ | $O(1)$ | สลับเฉพาะคู่ติดกัน เข้าใจง่ายที่สุด |
| **Selection Sort** | $O(n^2)$ | $O(n^2)$ | $O(n^2)$ | $O(1)$ | สลับข้อมูลน้อยที่สุด ($O(n)$ Swaps) |
| **Insertion Sort** | $O(n)$ | $O(n^2)$ | $O(n^2)$ | $O(1)$ | เร็วที่สุดเมื่อข้อมูลเกือบเรียงแล้ว |
| **Quick Sort** | $O(n \log n)$ | $O(n \log n)$ | $O(n^2)$ | $O(\log n)$ | รวดเร็วด้วย Divide and Conquer |

---

## 4. สถาปัตยกรรมและเทคโนโลยี (Architecture)

- **Single-file Application (`index.html`):** รวม HTML5, CSS3, JavaScript และ Web Audio API ไว้ในไฟล์เดียวเพื่อความสะดวกในการเปิดและโฮสต์
- **Generator-based Engine (`function*`):** ใช้อนุพันธ์ Generator ควบคุม Step execution ของทุกอัลกอริทึมอย่างเป็นระเบียบและแม่นยำ
- **Web Audio API:** สังเคราะห์เสียงสั้นแบบมินิมอล (Soft Sine / Triangle Tones) โดยไม่ต้องดาวน์โหลดไฟล์เสียงจากภายนอก
- **Zero External Dependencies:** ไม่พึ่งพา Library หรือ CDN ภายนอก รองรับการเปิดแบบ Offline 100%

---

## 5. วิธีเปิดเล่นและนำขึ้นโฮสต์ (Deployment)

1. **เปิดในเครื่อง (Local):** ดับเบิลคลิกเปิดไฟล์ `index.html` บนเบราว์เซอร์ใดก็ได้
2. **GitHub Pages (แนะนำ):**
   - ไปที่ GitHub Repo > **Settings** > **Pages**
   - หัวข้อ Branch เลือก `main` และ `/ (root)` แล้วกด **Save**
   - ลิงก์ที่ได้: `https://<username>.github.io/<repo-name>/`

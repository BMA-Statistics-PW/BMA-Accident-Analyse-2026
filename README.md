# สถานการณ์อุบัติเหตุทางถนน กรุงเทพมหานคร · BMA Accident Analyse 2026


🔗 **Dashboard:** https://bma-statistics-pw.github.io/BMA-Accident-Analyse-2026/

Dashboard สรุปผู้เสียชีวิตและผู้บาดเจ็บจากอุบัติเหตุทางถนนในกรุงเทพมหานคร พ.ศ. 2565–2569 จากข้อมูลสรุปของ [Thairsc](https://www.thairsc.com/province/10) สำหรับการนำเสนอเชิงนโยบาย — เป็นไฟล์ HTML เดียว เปิดด้วยการดับเบิลคลิกได้ รองรับมือถือ แท็บเล็ต และคอมพิวเตอร์

**จัดทำโดย:** PRAPAWADEE WACHIRAPUT · กลุ่มงานสถิติและวิจัย กองนโยบายและแผนงาน สำนักการจราจรและขนส่ง · © Prapawadee_W.

---

## ภาพรวมผลการวิเคราะห์ (ข้อมูล ณ วันที่ 9 ตุลาคม 2569)

| ตัวชี้วัด | ค่า |
|---|---|
| ผู้เสียชีวิตสะสม ปี 2569 | **583 ราย** (เฉลี่ย 2.07 ราย/วัน) |
| ผู้บาดเจ็บสะสม ปี 2569 | **136,359 คน** (เฉลี่ย 484 คน/วัน) |
| อัตราเสียชีวิตต่อผู้ประสบภัย 1,000 คน | **4.26 ‰** (ปี 2568: 4.83 ‰, ปี 2565: 7.91 ‰) |
| ประมาณการทั้งปี 2569 (เชิงเส้น) | ≈ 755 ราย / ≈ 176,493 คน |
| ดัชนีความรุนแรงสูงสุด | **1.71 เท่า** — ผู้สูงอายุ 60 ปีขึ้นไป |
| เขตที่มีผู้เสียชีวิตสูงสุด | **หนองจอก** 37 ราย (6.4% ของ กทม.) |

ข้อสังเกตหลัก
- ผู้เสียชีวิตลดลงต่อเนื่องทุกปี แต่ผู้บาดเจ็บที่ถูกบันทึกเพิ่มขึ้น อัตราเสียชีวิตต่อผู้ประสบภัยจึงลดลง — **ยังสรุปสาเหตุไม่ได้** อาจเป็นความรุนแรงที่ลดลงจริง หรือการรายงานผู้บาดเจ็บครอบคลุมมากขึ้น
- 13 เขตมีผู้เสียชีวิตรวมกันครึ่งหนึ่งของ กทม. และ 4 เขตมีผู้เสียชีวิตสูงกว่าที่คาดจากจำนวนผู้ประสบภัยอย่างชัดเจน (z ≥ 3): หนองจอก คลองสามวา ลาดกระบัง ทวีวัฒนา
- ผู้สูงอายุ 60 ปีขึ้นไปและผู้ชายมีสัดส่วนในผู้เสียชีวิตสูงกว่าสัดส่วนในผู้ประสบภัย
- ช่วงเย็น 16:00–19:59 น. เป็นช่วงที่มีสัดส่วนผู้ประสบภัยสูงสุดและเพิ่มขึ้นจากปี 2565

## เนื้อหาใน Dashboard (5 แท็บ)

| แท็บ | แสดงอะไร |
|---|---|
| **ภาพรวมรายปี** | ผู้เสียชีวิต/ผู้บาดเจ็บรายปี, อัตราเสียชีวิตพร้อมช่วงเชื่อมั่น Wilson 95%, ประมาณการทั้งปี 2569 |
| **รายเขต** | แผนที่ OpenStreetMap แบบ choropleth 50 เขต, กราฟจัดอันดับ, scatter ผู้บาดเจ็บ vs ผู้เสียชีวิต, ตารางเรียงได้ |
| **กลุ่มเสี่ยง** | ดัชนีความรุนแรงตามเพศ/อายุ/ยานพาหนะ และแนวโน้มสัดส่วนรายปี |
| **ช่วงเวลา** | สัดส่วนผู้ประสบภัยรายชั่วโมงและรายช่วงเวลา |
| **ข้อมูลและข้อควรระวัง** | วิธีคำนวณ ข้อจำกัด ลิงก์ข้อมูล |

ทุกกราฟมีปุ่ม "ดูเป็นตาราง" · ฟอนต์ Sarabun · รองรับ dark mode · ออกแบบ 3 ขนาด: มือถือ (≤640px) / แท็บเล็ต (641–1024px) / คอมพิวเตอร์ (≥1025px)

## โครงสร้าง repo

```
├── index.html                      ← หน้า Dashboard (GitHub Pages เปิดไฟล์นี้)
├── data/
│   ├── thairsc_bangkok_all_available_2565_2569.csv   ← ข้อมูลต้นทาง (270 แถว)
│   ├── dashboard.json              ← ตัวเลขที่ใช้แสดง (สร้างจาก CSV)
│   └── bangkok_districts.geojson   ← ขอบเขต 50 เขต สำหรับแผนที่
├── scripts/build.py                ← CSV → dashboard.json + index.html
├── src/index.template.html         ← ต้นฉบับหน้าเว็บ
├── docs/screenshot.png
├── LICENSE · CITATION.cff
```

## วิธีสร้างเมื่อมีข้อมูลชุดใหม่

```bash
pip install pandas
python3 scripts/build.py
```

ตัวเลขทุกค่าในหน้าเว็บมาจาก CSV ผ่านสคริปต์นี้ ไม่มีตัวเลขที่พิมพ์มือ และสคริปต์ตรวจอัตโนมัติว่า
ผลรวมรายเขตเท่ากับยอดรวม กทม., สัดส่วนรายชั่วโมง/ช่วงเวลารวม 100% ทุกปี และชื่อเขตใน CSV ตรงกับไฟล์ขอบเขต

## เผยแพร่ด้วย GitHub Pages

## วิธีคำนวณโดยย่อ

- **อัตราเสียชีวิต ‰** = ผู้เสียชีวิต ÷ (ผู้เสียชีวิต + ผู้บาดเจ็บ) × 1,000, ช่วงเชื่อมั่น 95% แบบ Wilson
- **ประมาณการทั้งปี 2569** = ยอดสะสม ÷ 282 วัน × 365 (เชิงเส้น ไม่รวมฤดูกาลหรือเทศกาลปลายปี)
- **z รายเขต** = (จริง − คาด) ÷ √คาด โดยคาด = ผู้ประสบภัยของเขต × อัตรา กทม. (ถือว่าสูงผิดปกติเมื่อ z ≥ 3)
- **ดัชนีความรุนแรง** = สัดส่วนในผู้เสียชีวิต ÷ สัดส่วนในผู้ประสบภัย (1.00 = ค่าเฉลี่ย)

## ข้อควรระวังในการอ่านข้อมูล

- ปี 2569 ไม่ครบ 12 เดือน (ถึง 9 ต.ค.) ยอดถูกปรับย้อนหลังได้ — อย่าเทียบ "ลดลง" กับปีเต็มโดยตรง
- ผู้บาดเจ็บอาจสะท้อนความครอบคลุมการรายงาน จึงสรุปความรุนแรงที่ลดลงจากอัตราเพียงอย่างเดียวไม่ได้
- ข้อมูลรายเขตเป็นปีเดียว จำนวนผู้เสียชีวิตของเขตส่วนใหญ่ต่ำกว่า 30 ราย จึงผันผวนสูง; z-score เป็นตัวชี้วัดเบื้องต้น ไม่ใช่ข้อสรุปเชิงสาเหตุ
- สัดส่วนรถยนต์ปี 2569 กระโดดจากราว 7% เป็น 11.2% ควรตรวจกับต้นทางก่อนสรุป
- ไม่มีข้อมูลระดับเหตุการณ์ จึงคำนวณอัตราต่อประชากรหรือต่อ VKT ไม่ได้
- งานนี้จัดทำเพื่อการศึกษาและการนำเสนอ มิใช่เอกสารทางการของหน่วยงานใด

## แหล่งข้อมูลและเครดิต

- ข้อมูลอุบัติเหตุ: [Thairsc](https://www.thairsc.com/province/10) · [data-compare](https://www.thairsc.com/data-compare)
- แผนที่พื้นหลัง: © [OpenStreetMap contributors](https://www.openstreetmap.org/copyright) ผ่าน [Leaflet](https://leafletjs.com) (ต้องต่ออินเทอร์เน็ต ถ้าโหลดไม่ได้ หน้าเว็บยังใช้งานกราฟและตารางได้) — `tile.openstreetmap.org` มี[นโยบายการใช้งาน](https://operations.osmfoundation.org/policies/tiles/) หากมีผู้เข้าชมจำนวนมากควรเปลี่ยนผู้ให้บริการ tile
- ขอบเขต 50 เขต: [OpenGISData-Thailand](https://github.com/chingchai/OpenGISData-Thailand) (chingchai) — ตรวจเงื่อนไขการใช้งานก่อนเผยแพร่ หรือเปลี่ยนเป็นไฟล์ขอบเขตของหน่วยงาน
- License: MIT (เฉพาะโค้ดใน `scripts/` และ `src/`) · ข้อมูลต้นทางเป็นของ Thairsc

---

## English summary

A single-file, dependency-light dashboard of Bangkok road-crash deaths and injuries (B.E. 2565–2569 / 2022–2026) built from [Thairsc](https://www.thairsc.com/province/10) summary data, for policy presentation.

**Headline (as of 9 Oct 2026):** 583 deaths and 136,359 injuries in 2026 (B.E. 2569, partial year). Deaths per 1,000 victims fell from 7.91 (2022) to 4.26 (2026), but rising recorded injuries mean this cannot yet be read as a true severity decline. Thirteen districts account for half of all deaths; four (Nong Chok, Khlong Sam Wa, Lat Krabang, Thawi Watthana) show significantly more deaths than expected (z ≥ 3). People aged 60+ are 1.71× over-represented among deaths relative to victims.

**Tabs:** yearly overview · districts (OpenStreetMap choropleth, ranking, scatter, sortable table) · risk groups · time of day · data & caveats. Responsive for phone, tablet and desktop; Sarabun font; dark mode.

**Rebuild:** `pip install pandas && python3 scripts/build.py` — regenerates `data/dashboard.json` and `index.html` with built-in consistency checks.
**Deploy:** public repo → Settings → Pages → `main` / root.

**Caveats:** 2026 is a partial year and figures are revised retroactively; district counts are small; no incident-level data, so no per-capita or per-VKT rates. Check Thairsc's terms and the boundary-file license before making the repo public.

Prepared by PRAPAWADEE WACHIRAPUT, Statistics and Research Group, Policy and Planning Division, Traffic and Transportation Department, Bangkok Metropolitan Administration · © Prapawadee_W.

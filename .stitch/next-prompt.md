---
page: index
device: MOBILE
base_screen: a5dc895b7b1c4f6a98043550c5a205ea
---
Create a MOBILE version (390px wide) of the existing DA VINCI landing page. Keep every section,
all copy and all data exactly as they are on the desktop screen — this is a layout adaptation,
not a rewrite. Do not invent, shorten or replace any name, number, price or schedule.

**DESIGN SYSTEM (REQUIRED — follow exactly):**

**Language:** ALL user-facing text stays in Russian, Cyrillic subset.

**Colors:** Drawing Paper (#FAF7F2) page background, Toned Paper (#F1EAE0) alternating sections
and cards, Graphite (#1C1A18) anchor dark sections and headings, Soft Graphite (#57514A) body text,
Burnt Sanguine (#A8431F) primary call-to-action only, Ochre (#C8912F) eyebrows and statistic
numbers, Pencil Trace (#DCD3C6) borders, WhatsApp Green (#25D366) for the WhatsApp button.

**Typography:** Playfair Display semi-bold for headings, Inter for body and interface,
eyebrows in Inter uppercase with 0.12em letter-spacing in Ochre.

**Shapes:** buttons 8px radius, cards 12px radius, flat by default, hairline Pencil Trace borders.

**Mobile-specific rules:**
- Section gaps drop from 6rem to 4rem; side padding 1.25rem.
- H1 drops to 2.25rem, H2 to 1.75rem. Body text stays at 1rem minimum — never shrink below.
- Every touch target is at least 44x44px.
- A **sticky bottom bar** pinned to the viewport, visible during the entire scroll: Drawing Paper
  background with a hairline Pencil Trace top border, containing the phone as a `tel:` link on the
  left and a WhatsApp Green button «Написать в WhatsApp» on the right.
- The header collapses to the wordmark on the left and a hamburger menu button on the right;
  the phone number moves out of the header into the sticky bottom bar.

**Per-section layout changes (content stays identical):**
1. **Header** — wordmark «DA VINCI» plus «художественная школа · Караганда», hamburger menu opening a full-screen drawer with the five anchor links.
2. **Hero** — single column: eyebrow, H1, subheadline, then the plaster-head photograph, then the two buttons stacked full width, then the three trust markers as three stacked lines rather than one row.
3. **#stats** — 2×2 grid instead of a row of four.
4. **#universities** — 2 columns × 4 rows. Logo, short name, full name, count and «поступили» stay in each block.
5. **#pain** — three cards stacked vertically, full width.
6. **#program** — six cards in one column. The secondary button «Узнать программу под мой вуз» goes full width.
7. **#process** — the four steps become a vertical timeline: numerals down the left in Ochre, connected by a vertical Pencil Trace line, text to the right.
8. **#teachers** — horizontal swipe carousel, cards about 70% of viewport width, scroll-snap enabled.
9. **#works** — horizontal swipe carousel on the Graphite background, 3:4 photographs about 70% viewport width, scroll-snap. The Burnt Sanguine button below goes full width.
10. **#price** — the card goes full width with 1.5rem padding; the two schedule groups stack vertically.
11. **#reviews** — the three empty `[отзыв]` placeholder cards stack vertically. Keep them empty.
12. **#faq** — accordion full width, all items collapsed by default on mobile to keep the section short.
13. **#cta** — single column: heading, paragraph, phone, address, WhatsApp button, then the form card below at full width.
14. **Footer** — three columns become three stacked blocks, centered.

**Do not change:** the five teacher names and their universities, the six programme modules,
the seven universities and their admission counts, the price 27 000 ₸, the two group schedules
(«Понедельник и четверг, 18:00–20:00» and «Вторник и пятница, 18:00–20:00»), the address
«г. Караганда, ул. Бухар-Жырау, 55», the phone «+7 775 567 7056», or any FAQ answer.

**Never state a lesson frequency other than two times a week for two hours.**

---

## Проверка после генерации (обязательно)

Stitch на каждой итерации воссоздаёт по памяти секции, которых нет в промпте, и выдумывает факты.
На десктопной сборке он уже подменил все пять ФИО преподавателей, все шесть модулей программы,
четыре шага подготовки и подписал AIU чужим названием. Поэтому после генерации проверить, что
в разметке присутствуют строки:

```
Чеботрош Жанна Сергеевна · Молчанова Оксана Сергеевна · Максименко Анна Иоанновна
Тихомиров Антон Борисович · Кайназарова Алла Михайловна
Гипсовые тела вращения · Натюрморт · Гипсовая голова · Портрет с натуры
Живопись и композиция · Черчение и перспектива
Международный университет Астана · 27 000 ₸ · Бухар-Жырау · +7 775 567 7056
Два раза в неделю по два часа · [отзыв]
```

и что отсутствуют: `3 раза в неделю`, `Astana IT University`, `href="#"`.

Если `edit_screens` отвечает успехом, но правки не появились в файле — вносить их напрямую
в `.stitch/designs/index-mobile.html`, это надёжнее повторного вызова.

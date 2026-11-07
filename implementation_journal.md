### 2026-11-03: Quiz State Persistence & Navigation Fix

### Feature Overview
Fixed Quiz section reset issue. Navigation now preserves active quiz state instead of restarting every click.

### Implementation Details
1.  **Smart Navigation**:
    - Sidebar and "Study" buttons now check `quizState.isFinished` and `quizState.questions.length`.
    - If a quiz is already in progress, clicking the menu item resumes it.
    - If no quiz exists or the last one finished, it starts a new one.
2.  **Restart Functionality**:
    - Added "Restart Quiz" button to the results screen.
    - This is now the primary way to clear a finished quiz and start fresh.
3.  **State Logic**:
    - `startQuiz` remains the sole method for initialization, but is now called conditionally by UI components.

### 2026-11-04: Science.md In-App Implementation

### Feature Overview
Implemented `Science.md` inside the StudySystem app so science notes are searchable and visible in topic detail screens.

### Implementation Details
1. **Embedded Science Reference Data**:
   - Added a structured `scienceReference` object in `index.html`.
   - Mapped the markdown content into note sections for Biology, Chemistry, Physics, and Earth/Space Science.
2. **Expanded Science Coverage**:
   - Kept existing science topic flow but upgraded it to cover `Photosynthesis`, `Cells & Molecular Biology`, `Chemistry Foundations`, `Kinematics & Optics`, and `Earth & Space Science`.
   - Added quiz sets and flashcards for the new chemistry coverage.
3. **Topic Detail Upgrade**:
   - Added `Quick Examples` and `Reference Notes` sections.
   - Reference notes now render numbered bullet lists from the embedded `Science.md` content.
4. **Library Search Upgrade**:
   - Search now matches against overviews, concepts, examples, mnemonics, and embedded note text instead of only title/category.

### 2026-11-04: Math.md Creation & Integration

### Feature Overview
Created `Math.md` and integrated Statistics and Probability content into the StudySystem application, including interactive sample problems.

### Implementation Details
1. **Comprehensive Math Content**:
   - Created `Math.md` with 18 topics covering Statistics and Probability (Mean/Median/Mode, ANOVA, P-values, Z-scores, etc.).
   - Each topic contains exactly 10 technical key points and a sample problem with solution.
2. **In-App Data Mapping**:
   - Added a `mathReference` object in `index.html` to hold the content.
   - Expanded the `Stats` category in the app with three new major topics: `Advanced Stats`, `Probability & Distributions`, and `Data Visualization`.
3. **Interactive UI (Sample Problems)**:
   - Updated the `TopicDetail` component to render "Sample Problem" cards within reference notes.
   - Problems are styled with an indigo theme to distinguish them from study points.
4. **Unified Search & Review**:
   - All new math content is integrated into the Library search engine, Quizzes, and Flashcards.

### 2026-11-05: Question Bank Expansion (25 Per Topic)

### Feature Overview
Expanded every topic in the Topic Library from 10 to 25 questions, giving a total of 350 questions across all 14 topics.

### Implementation Details
1. **Per-Topic Expansion**:
   - Appended 15-16 new questions to each of the 14 topics in `studyData.topics` inside `index.html`.
   - Topics covered: `num_theory`, `factoring`, `logs`, `trig`, `stats_basics`, `hypothesis`, `advanced_stats`, `probability_stats`, `data_viz`, `photosynthesis`, `mol_bio`, `chemistry`, `kinematics`, `planets`.
   - Every topic now holds exactly 25 questions (14 x 25 = 350).
2. **Question Schema Standardized**:
   - All questions follow `{ q, a: [...4 options], c: <index>, e: <explanation> }`.
   - Repaired two malformed entries (`hypothesis` Z-score, `probability_stats` C(n,r)) that used a string `a` plus stray `b/c/d` keys, which would have crashed `q.a.map()` at runtime.
3. **Verification**:
   - Grep for `{ q: '` returns 350 matches, confirming exact 25-per-topic count.
   - Grep for `, [bcd]: '` returns only legitimate flashcard entries; no malformed questions remain.
4. **Downstream Behavior Unchanged**:
   - Quiz still draws 10 random questions per round (`slice(0, 10)`), now with a larger pool.
   - Mock Exam still draws 3 per topic (42 total), timer still 1 minute per question.

### 2026-11-05: Full Question Fact-Check

### Feature Overview
Verified all 350 questions (14 topics x 25) for factual correctness of question text, options, correct-answer index, and explanation.

### Implementation Details
1. **Review Scope**: checked math (number theory, factoring, logs, trig), stats (central tendency, hypothesis testing, advanced stats, probability, data viz), and science (photosynthesis, molecular bio, chemistry, kinematics, earth/space) items.
2. **Defects Found & Fixed**:
   - `data_viz` IQR question: still used malformed schema (string `a` plus stray `b/c/d` keys), which crashes `q.a.map()` at runtime. Converted to standard `a: [...]` array with `c: 0` and the correct value `Q3 - Q1`.
   - `num_theory`: "Which number **under 20** is NOT prime?" listed 21 as the answer, but 21 is not under 20. Reworded to "Which number is NOT prime?".
3. **Verification**:
   - Grep `a: '[^']*', b: '` returns no matches, confirming no malformed question objects remain.
   - All other 348 items confirmed correct on answer key and rationale.

### 2026-11-05: True Randomization Implementation

### Feature Overview
Implemented robust randomization for Quizzes, Mock Exams, and Flashcards to ensure a fresh experience every time a session starts.

### Implementation Details
1. **New Shuffle Utilities**:
   - Added `shuffle` (Fisher-Yates algorithm) to handle array reordering without mutating source data.
   - Added `shuffleQuestion` to randomize the order of options within each question while maintaining the correct answer mapping.
2. **Quiz & Mock Exam Enhancements**:
   - Updated `startQuiz` to use the new shuffle logic for both question selection and option order.
   - Refactored `MockExam` and `resetMockExam` to ensure non-mutating, truly random question pools and option layouts.
3. **Flashcard Randomization**:
   - Updated `FlashcardsView` to shuffle cards on load, preventing predictable study patterns.
4. **Bug Fixes**:
   - Removed all instances of `.sort(() => Math.random() - 0.5)` which mutated `studyData` in-place, causing fixed orders after the first shuffle.

### 2026-11-05: Real-time Shuffle & Mock Exam Overhaul

### Feature Overview
Updated the application to perform fresh shuffles every time a topic or exam is opened, and synchronized the Mock Exam to use the full 350-question pool.

### Implementation Details
1. **Real-time Quiz Randomization**:
   - Modified sidebar, dashboard, and topic detail buttons to always call `startQuiz(topicId)` or `resetMockExam()`.
   - Removed "resume" logic to ensure every click loads a unique set of 25 questions and randomized options.
2. **Mock Exam Pool Expansion**:
   - Updated `resetMockExam` and `mockExamState` initializer to pull from `studyData.topics.flatMap(t => t.questions)`.
   - Set Mock Exam length to 30 questions randomly sampled from the entire 350-question bank.
   - Every exam session now shuffles both the question selection and the option order per question.
3. **Sidebar Sync**:
    - Navigation links now trigger a fresh state reset, preventing stale order persistence between view switches.
 4. **Fixed Navigation Bug**:
   - Passed `startQuiz` and `resetMockExam` as props to the `Sidebar` component to fix a ReferenceError that prevented the "Mock Exam" and "Quiz" buttons from working.

### 2026-11-07: Pointers Section & Image Optimization

### Feature Overview
Processed the reference images in `Pointers/` and added a new "Pointers" view to the app that displays them in a gallery with a full-screen lightbox.

### Implementation Details
1. **Image Processing** (Python + Pillow):
   - Source files were `.jfif` screenshots at 1170x2532 with a pure-black letterbox: 57px on top and 24px on the bottom, content full-bleed horizontally.
   - Trimmed each image to the content bounding box (scan for first/last row and column above a near-black threshold of 12) and re-encoded as progressive, optimized JPEGs at quality 85.
   - Output: `Pointers/pointer-1.jpg` (1170x2451), `pointer-2.jpg`, `pointer-3.jpg`. Original `.jfif` files were left in place.
2. **New Component**: Added `Pointers` inside `App`, rendering a responsive `pointer-grid` of `pointer-card` buttons; clicking a card opens a `pointer-lightbox` overlay.
3. **New Styles**: Added `.pointer-grid`, `.pointer-card`, `.pointer-card-img`, `.pointer-card-foot`, `.pointer-lightbox`, `.pointer-lightbox-close` to the embedded stylesheet so the cards do not inherit the default `.card` padding.
4. **Navigation**: Added a "Pointers" `NavItem` (icon `image`) under DAILY USE and the `{currentView === 'pointers' && <Pointers />}` render branch.
5. **Verification**: Served the directory locally; `index.html` and all three JPEGs return HTTP 200.

### 2026-11-07: Pointer Lightbox Zoom & Mobile Gestures

### Feature Overview
Added zoom, pan, and pinch support to the Pointer lightbox so the reference images can be inspected closely on both desktop and mobile.

### Implementation Details
1. **View State**: `view = { scale, x, y }` drives a CSS `transform: translate(x, y) scale(scale)` on the lightbox image, with `transform-origin: center center`.
2. **Anchored Zoom**: `zoomAt(factor, cx, cy)` keeps the pointer position fixed while scaling (`x' = cx - (s'/s) * (cx - x)`), and `clampPan` limits translation to the scaled overflow so the image cannot be dragged off screen.
3. **Desktop**: non-passive `wheel` listener (registered via `useEffect` + `addEventListener` so `preventDefault` works) zooms toward the cursor; drag pans; double-click toggles between 1x and 2.5x.
4. **Mobile**: `touch-action: none` on the stage plus Pointer Events. Two active pointers drive a pinch gesture (distance ratio → scale, midpoint → anchor), one pointer pans. Pointer capture keeps the gesture alive outside the element.
5. **Controls**: On-screen zoom bar with zoom-out / live percentage / zoom-in / reset, plus `Escape` to close and a blurred backdrop click to dismiss.
6. **Verification**: Served locally; browser console reports no errors.

### 2026-11-07: Pointer Image Sharpness Fix

### Problem
Images looked pixelated when zoomed in the lightbox.

### Diagnosis
1. Source images are native iPhone screenshots (1170x2532), not upscaled: 92% of horizontal neighbours are identical, which matches a mostly-flat black background rather than nearest-neighbour block replication.
2. Two real causes: (a) the JPEGs were encoded at quality 85 with default 4:2:0 chroma subsampling, which smears synthetic text edges; (b) the image had `will-change: transform`, so the browser cached a raster at layout size and scaled that low-res bitmap during zoom.

### Implementation Details
1. **Re-encoded images**: q95, `subsampling=0` (4:4:4), progressive, optimized. Sizes 227 / 207 / 285 KB.
2. **CSS**: removed `will-change: transform` (added `backface-visibility: hidden`, explicit `image-rendering: auto`) so the browser re-rasterizes at the final scale.
3. **Adaptive zoom ceiling**: added `maxScaleRef` + `syncMaxScale(img)` on image load, setting max zoom to `clamp(naturalWidth / renderedWidth * 1.75, 2, 8)`. This stops the user from zooming past the pixel budget of the source, keeping text crisp. `clampScale` now reads the ref so the wheel/pinch handlers respect it.
4. **Verification**: local server 200 for the page and all three JPEGs; browser console clean.



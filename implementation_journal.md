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

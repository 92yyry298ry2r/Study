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

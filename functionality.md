# StudySystem Webapp Functionality Summary

Detailed breakdown of all features in the [index.html](file:///e:/Users/admin/Desktop/Study/index.html) application.

## 1. Dashboard (Overview)
- **Stats Tracking**: Visual cards for Days Left, Overall Progress %, Weak Spots count, and Quiz Accuracy %.
- **Progress Visualization**: Rounded progress bars for overall completion.
- **Recommended Topics**: Dynamic table showing high-priority topics with quick-access study buttons.
- **Daily Plan**: Interactive checklist synced with the 5-day study schedule.

## 2. Topic Library
- **Categorized Reading**: View all topics (Math, Stats, Science) with detailed overviews, core concepts, and memory aids.
- **Search**: Real-time filtering by topic name or category across the entire library.
- **Status Indicators**: Visual badges for category and priority levels.

## 3. Flashcards
- **Interactive Flipping**: 3D flip-card interface for active recall.
- **Spaced Repetition**: "Review Again" vs "Got It" logic to help focus on difficult terms.
- **Topic-Specific Decks**: Ability to study flashcards for a specific topic or all topics combined.

## 4. Quiz Mode
- **Randomized Testing**: Generates 25-question sets (the full question bank for a topic) from a topic or mixed pool.
- **Fresh Shuffle**: Question order and answer-option order are re-randomized every time a topic is opened.
- **Instant Feedback**: Immediate correct/incorrect status with detailed explanations for every answer.
- **Scoring**: Accuracy tracking that feeds back into the Dashboard.
- **Weak Spot Integration**: Wrong answers automatically flag topics for the Weak Spot Tracker.

## 5. Mock Exam
- **Timed Simulation**: 30 questions drawn from the full 350-question pool (14 topics x 25) with a 30-minute countdown timer and a sticky UI.
- **Full Coverage**: Randomly sampled across every topic in the database, reshuffled on each start.
- **Post-Exam Review**: Detailed score breakdown and list of questions to review.

## 6. Weak Spot Tracker
- **Automated Logging**: Identifies topics where questions were answered incorrectly.
- **Focused Review**: Dedicated view to study only the topics marked as "weak."
- **Badge Notifications**: Sidebar count of current weak topics.

## 7. Study Planner & Persistence
- **5-Day Schedule**: Pre-defined roadmap from learning to mock testing.
- **LocalStorage Sync**: All progress (checked tasks, quiz scores, weak spots) persists across browser refreshes via `try/catch` wrapped storage logic.
- **Reset Functionality**: Option to clear all data and start fresh.

## 8. UI/UX Features
- **Light/Dark Mode**: Full-app theme switching (Shell, Sidebar, Cards, Tables) with `prefers-color-scheme` support.
- **Responsive Design**: Collapsible sidebar for desktop and mobile-optimized layout.
- **Visual Feedback**: Smooth transitions, hover effects, and accessible color contrast.

## 9. Pointers
- **Image Gallery**: Displays the trimmed quick-reference images from the `Pointers/` folder in a responsive card grid.
- **Lightbox Viewer**: Click any card to open a full-screen, blurred-backdrop overlay; click the backdrop or close button to dismiss.
- **Self-Contained Assets**: Images are stored as optimized JPEGs in `Pointers/` and referenced by relative path.

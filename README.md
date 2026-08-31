# Breezy — Find Your Air Type

## What I built and why

Breezy is a satirical “artisanal air” landing page. The homepage already mentioned “Take Our Quiz,” but it was only descriptive. I turned that into a real interactive quiz: three multiple-choice questions that recommend Mountain, Coastal, Forest, or Urban air.

I chose this feature because it is the strongest product moment on the page. It is short, on-brand, and gives someone a reason to keep going to pricing.

The quiz is frontend-only (HTML, CSS, JavaScript in `index.html`). No API, database, or ML. Everyone answers the same three questions, so counting which air type they picked most often is enough.

The flow:

1. Intro screen (“Find your Air Type”) and a Begin button
2. Three questions; each answer has a type and an emoji
3. Result with personalized copy, **Explore our plans** (jumps to Pricing), and **Retake**

You can open it from the nav, mobile menu, How It Works heading, or the hero CTA.

## How it works technically

Questions are stored in a JavaScript array. Each option has `text`, `type`, and `emoji`:

```js
{ text: "Cool and refreshing", type: "Mountain", emoji: "🏔️" }
```

Two pieces of state:

- `currentQuestion` — which question the user is on
- `userAnswers` — the types they picked, e.g. `["Mountain", "Forest", "Mountain"]`

`selectAnswer(type)` writes into `userAnswers`. If there are more questions, it increments the index and calls `displayQuestion()`. Otherwise it calls `showResult()`. Answer buttons are created in JS (`createElement`), not hardcoded, so adding a question is a data change.

`calculateRecommendation()` scores each type and returns the one with the highest count. Ties go to the first type that hits that score. Average vs total would rank the same here because every user answers three questions.

The modal has three screens: `#quizIntro` → `#quizPlay` → `#quizResult`. `openQuiz()` shows the intro and resets state. `startQuiz()` hides the intro and shows question 1.

## Setup

Nothing to install. Open `index.html` in a browser, or from this folder:

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000

## What I would improve if I had more time

- Use the recommended type on the pricing section (highlight a matching plan)
- Progress bar and keyboard support (Enter to continue, Esc to close)
- Result copy that says *why* (e.g. “you picked Mountain twice”)
- Unit tests for scoring, especially ties
- Split quiz CSS/JS out of `index.html` if the page keeps growing

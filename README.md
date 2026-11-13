# logicodix

# LearnAble — Accessible AI Learning Hub

LearnAble combines an **AI Study Buddy**, **Adaptive Quiz Coach**, and **Accessible Learning Hub** in one web app.

## How to run

1. Keep all files in this same folder.
2. Double-click `index.html`, or right-click and choose **Open with** your browser.
3. Enter a topic, paste your notes, then click **Generate study kit**.
4. Start the adaptive quiz and use the accessibility controls.

No installation, server, or database is required.

## Features

- AI Study Buddy: simple explanation, key points, flashcards, and question answering
- Adaptive Quiz Coach: questions adapt across three difficulty levels
- Accessible Learning Hub: text-to-speech, high contrast, dyslexia-friendly font, text resizing, reduced motion, and keyboard navigation
- Progress tracking: streak, accuracy, questions answered, and topic mastery

## Optional AI

Open `index.html`, find this line near the top of the `<script>` section:

```js
const GEMINI_KEY = "";
```

Add your Gemini API key between the quotation marks to enable AI-generated study kits. Do not share or commit your real API key.

Without a key, LearnAble still works using its built-in offline study-kit engine.

## Data privacy

Progress is saved only in your browser using localStorage. The offline version does not upload student data.

## LOGICODIX alignment

- Subtheme: Smart Fun Education and Inclusive Health & Well-being
- Product type: Web MVP
- AI use: study support, explanation, flashcards, adaptive quiz generation
- Real problem: inaccessible and non-personalized learning experiences

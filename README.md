# logicodix

# LearnAble – Accessible AI Learning Hub

## 1. Project Information

- **Team Name:** [Insert team name]
- **Team Members:**
  - [Member 1 – Full Name]
  - [Member 2 – Full Name]
  - [Add or remove members as needed]
- **Category:** Web
- **Application Name:** LearnAble

## 2. Application Overview

**LearnAble** is a web-based learning tool that helps students study using their own notes or lesson materials. Users can paste learning material and generate a study kit containing a simple explanation, key points, flashcards, and quiz questions.

The application also includes accessibility settings, text-to-speech, and a learning-progress tracker. Its goal is to make reviewing lessons more flexible and accessible.

### Problem

Students may find it difficult to understand, organize, and review lesson materials. Some learning tools may also lack display and accessibility options that support different learning preferences.

### Proposed Solution

LearnAble provides several study features in one place. Students can turn their notes into study materials, listen to text, adjust the display, practice with quizzes, and review their progress.

### Target Users

- Students who want to review lessons independently.
- Learners who prefer explanations, flashcards, or quizzes.
- Users who benefit from text-to-speech and adjustable display settings.

## 3. Main Features Implemented

| Feature | Description |
|---|---|
| Study Material Input | Users can enter a topic and paste their notes or lesson material. |
| Study Kit Generator | Creates a simple explanation, key points, flashcards, and quiz questions from the submitted material. |
| AI Study Buddy | Provides a question-and-answer area for questions about the learning material. Gemini API support is optional. |
| Adaptive Quiz Coach | Provides multiple-choice questions and adjusts the difficulty level based on the user's answers. |
| Text-to-Speech | Reads the submitted material, explanation, and quiz questions aloud using the browser's Speech Synthesis API. |
| Accessibility Settings | Includes high contrast, a dyslexia-friendly font option, reduced motion, and adjustable text size. |
| Learning Progress | Tracks answered questions, accuracy, day streak, and topic practice. |
| Local Data Storage | Saves accessibility preferences and learning progress in the browser's local storage. |

## 4. Technologies Used

| Technology / Service | Purpose |
|---|---|
| HTML5 | Defines the structure and content of the application. |
| CSS3 | Handles the layout, styling, responsive design, and accessibility-related display options. |
| JavaScript | Implements the application's features and interactions. |
| Browser Local Storage | Stores accessibility preferences and learning progress locally. |
| Web Speech API (Speech Synthesis) | Reads text aloud in supported browsers. |
| Google Gemini API (optional) | Generates study-kit content and answers questions when an API key is configured. |

**Frameworks and libraries:** The current implementation uses plain HTML, CSS, and JavaScript. No external framework or JavaScript library is required.

**Database:** No external database is used. Progress and accessibility preferences are stored in the user's browser.

**Third-party services:** Google Gemini API is an optional service. Without a configured API key, the application uses its built-in study-kit generator and fallback answer behavior.

## 5. System Architecture and Data Flow

### Architecture Diagram

```mermaid
flowchart TD
    A[User] --> B[LearnAble Web Interface]
    B --> C[HTML and CSS]
    B --> D[JavaScript Application Logic]
    D --> E[Built-in Study Kit Generator]
    D --> F{Gemini API Key Configured?}
    F -->|Yes| G[Google Gemini API]
    F -->|No| E
    D --> H[Browser Local Storage]
    D --> I[Browser Speech Synthesis API]
    E --> J[Study Explanation, Key Points, Flashcards and Quiz]
    G --> J
    J --> B
    H --> B
    I --> K[Audio Output]
```

### Data Flow

1. The user opens LearnAble in a web browser.
2. The user enters a topic and pastes learning material.
3. JavaScript processes the material using the built-in generator.
4. If a Gemini API key is configured, the application can also request generated content from the Gemini API.
5. The study explanation, key points, flashcards, and quiz are displayed on the page.
6. The user can practice quiz questions and receive feedback.
7. Quiz results are saved in browser local storage and used to update the progress section.
8. Accessibility preferences are also saved locally.
9. When the user selects a listening option, the browser's Speech Synthesis API reads the selected text aloud.

## 6. Installation and Setup

### Requirements

- A modern web browser, such as Google Chrome, Microsoft Edge, or Firefox.
- The `index.html` project file.
- An internet connection only if you want to use the optional Gemini API feature.

### Installation Steps

1. Download or clone the project files.
2. Make sure `index.html` is available in the project folder.
3. Open `index.html` in a supported web browser.
4. The LearnAble home page should appear.
5. Enter a topic and paste learning material to generate a study kit.

No package installation or build command is required for the current version.

### Optional Gemini API Configuration

The application can use the Google Gemini API for AI-generated study content and answers.

1. Obtain an API key through Google AI Studio.
2. Open `index.html` in a code editor.
3. Find the following line in the JavaScript section:

   ```javascript
   const GEMINI_KEY = "";
   ```

4. Add your API key locally:

   ```javascript
   const GEMINI_KEY = "YOUR_GEMINI_API_KEY";
   ```

5. Save the file and reopen or refresh the application.

**Important security note:** The current application runs entirely in the browser. A key placed in client-side JavaScript can be viewed by other people who access the application. Use this setup only for local testing with an appropriately restricted key. Do not publish or commit a real API key. A production version should call the AI service through a secure backend instead.

If no API key is configured, LearnAble uses its built-in generator and fallback response behavior. The rest of the application can still be used.

## 7. Configuration and Environment Variables

The current project does not use a `.env` file or environment variables because it is a static browser application.

| Setting | Description |
|---|---|
| `GEMINI_KEY` | Optional Gemini API key configured in the JavaScript file for local testing. Leave it empty to use the built-in generator. |

There is no separate database configuration, server configuration, or account configuration in the current implementation.

## 8. Demo Account

LearnAble does not currently include user registration, login, or authentication. Therefore, no demo username or password is required. Open the application directly in a browser to try its features.

## 9. AI Usage Documentation

AI integration is optional in the current version.

- **AI service:** Google Gemini API.
- **Model endpoint used in the source code:** `gemini-1.5-flash`.
- **Purpose:** Generate a study explanation, key points, flashcards, quiz questions, and answers to user questions.
- **User input:** The topic, learning material, and question entered by the user.
- **Fallback behavior:** When the API key is missing or the API request fails, the application uses its built-in JavaScript logic for study-kit generation and a basic fallback response for questions.

The built-in generator extracts sentences and frequently used keywords from the submitted material. Its output is a simple study aid and may not explain every concept accurately. Users should compare generated material with their original notes.

## 10. Third-Party Asset and Code Attribution

The current `index.html` implementation does not include external image assets, downloaded templates, external datasets, or third-party JavaScript libraries.

The project uses browser-provided features, including:

- **Web Speech API (Speech Synthesis):** Browser functionality used for text-to-speech.
- **Google Gemini API:** Optional external AI service, if configured.

If third-party assets, datasets, templates, or code are added in a future version, their original sources and licenses should be documented here.

## 11. Limitations

- The current version does not have user accounts or cloud synchronization.
- Learning progress and accessibility settings are stored only in the browser where the application is used.
- The built-in generator uses basic sentence and keyword extraction; it is not a replacement for a full AI model.
- Gemini API access depends on a valid API key, network access, and the availability and terms of the external service.
- Speech synthesis availability and voice quality depend on the user's browser and device.
- The current client-side API-key configuration is intended for local testing, not public production deployment.

## 12. Project Structure

```text
LearnAble/
├── index.html
└── README.md
```

The HTML file contains the application's HTML structure, CSS styling, and JavaScript functionality.

---

**LearnAble – Learn in the way that works for you.**

# DUOLINGUAL
<!DOCTYPE html>
<html lang="en">
<head>
    /* ============================================
   LinguaLearn - Neo-Brutalist Design System
   ============================================ */

/* Root Variables */
:root {
    /* Typography */
    --font-display: 'Space Grotesk', sans-serif;
    --font-body: 'DM Sans', sans-serif;
    --font-mono: 'Space Mono', monospace;

    /* Colors - Saturated & Bold */
    --color-yellow: #FFD93D;
    --color-teal: #06D6A0;
    --color-coral: #FF6B6B;
    --color-purple: #A855F7;
    --color-black: #111;
    --color-white: #FFFBF0;
    --color-gray: #888;
    --color-gray-light: #555;

    /* Spacing */
    --spacing-xs: 0.5rem;
    --spacing-sm: 1rem;
    --spacing-md: 1.5rem;
    --spacing-lg: 2rem;
    --spacing-xl: 3rem;
    --spacing-2xl: 4rem;

    /* Borders & Shadows */
    --border-width: 2.5px;
    --border-radius: 0.65rem;
    --shadow-hard: 6px 6px 0 var(--color-black);
    --shadow-medium: 3px 3px 0 var(--color-black);
    --shadow-soft: 1px 1px 0 var(--color-black);
}

/* ============================================
   Global Styles
   ============================================ */

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
}

body {
    font-family: var(--font-body);
    background-color: var(--color-white);
    color: var(--color-black);
    line-height: 1.6;
}

a {
    color: inherit;
    text-decoration: none;
}

button {
    font-family: var(--font-display);
    cursor: pointer;
    border: none;
}

.container {
    width: 100%;
    max-width: 1280px;
    margin: 0 auto;
    padding: 0 1rem;
}

@media (min-width: 640px) {
    .container {
        padding: 0 1.5rem;
    }
}

@media (min-width: 1024px) {
    .container {
        padding: 0 2rem;
    }
}

/* ============================================
   Navigation Bar
   ============================================ */

.navbar {
    background-color: var(--color-yellow);
    border-bottom: var(--border-width) solid var(--color-black);
    padding: var(--spacing-md) 0;
    position: sticky;
    top: 0;
    z-index: 100;
}

.navbar-content {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: var(--spacing-lg);
}

.navbar-logo {
    display: flex;
    align-items: center;
    gap: var(--spacing-sm);
    font-family: var(--font-display);
    font-weight: 800;
    font-size: 1.5rem;
}

.logo-icon {
    width: 40px;
    height: 40px;
    background-color: var(--color-black);
    color: var(--color-yellow);
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 4px;
    font-weight: 800;
}

.navbar-links {
    display: none;
    gap: var(--spacing-lg);
    flex: 1;
}

@media (min-width: 768px) {
    .navbar-links {
        display: flex;
    }
}

.nav-link {
    font-family: var(--font-display);
    font-weight: 700;
    font-size: 0.9rem;
    padding: var(--spacing-xs) var(--spacing-sm);
    border: var(--border-width) solid transparent;
    border-radius: var(--border-radius);
    transition: all 0.2s ease;
}

.nav-link:hover {
    border-color: var(--color-black);
    background-color: rgba(17, 17, 17, 0.1);
}

.nav-link.active {
    border-color: var(--color-black);
    background-color: var(--color-black);
    color: var(--color-yellow);
}

.nav-cta {
    background-color: var(--color-black);
    color: var(--color-yellow);
    padding: var(--spacing-sm) var(--spacing-md);
    border: var(--border-width) solid var(--color-black);
    border-radius: var(--border-radius);
    font-family: var(--font-display);
    font-weight: 700;
    font-size: 0.9rem;
    transition: all 0.1s ease;
    box-shadow: var(--shadow-medium);
}

.nav-cta:active {
    transform: translate(1px, 1px);
    box-shadow: var(--shadow-soft);
}

/* ============================================
   Brutalist Components
   ============================================ */

.brutalist-card {
    border: var(--border-width) solid var(--color-black);
    border-radius: var(--border-radius);
    box-shadow: var(--shadow-hard);
    padding: var(--spacing-md);
    background-color: var(--color-white);
    transition: all 0.2s ease;
}

.brutalist-card:hover {
    transform: translate(-2px, -2px);
    box-shadow: 8px 8px 0 var(--color-black);
}

.brutalist-btn {
    border: var(--border-width) solid var(--color-black);
    border-radius: var(--border-radius);
    padding: var(--spacing-sm) var(--spacing-md);
    font-family: var(--font-display);
    font-weight: 700;
    font-size: 1rem;
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    transition: all 0.1s ease;
    box-shadow: var(--shadow-medium);
}

.brutalist-btn:active {
    transform: translate(1px, 1px);
    box-shadow: var(--shadow-soft);
}

.brutalist-btn:disabled {
    opacity: 0.5;
    cursor: not-allowed;
}

.brutalist-badge {
    display: inline-block;
    border: var(--border-width) solid var(--color-black);
    border-radius: var(--border-radius);
    padding: var(--spacing-xs) var(--spacing-sm);
    font-family: var(--font-display);
    font-size: 0.75rem;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.05em;
}

.brutalist-progress {
    border: var(--border-width) solid var(--color-black);
    border-radius: var(--border-radius);
    background-color: var(--color-white);
    overflow: hidden;
    height: 1rem;
}

.brutalist-progress-fill {
    background-color: var(--color-teal);
    height: 100%;
    transition: width 0.3s ease;
}

/* ============================================
   Animations
   ============================================ */

@keyframes bounce-in {
    0% {
        transform: scale(0.9);
        opacity: 0;
    }
    100% {
        transform: scale(1);
        opacity: 1;
    }
}

@keyframes shake {
    0%, 100% {
        transform: translateX(0);
    }
    25% {
        transform: translateX(-5px);
    }
    75% {
        transform: translateX(5px);
    }
}

@keyframes fade-up {
    from {
        opacity: 0;
        transform: translateY(10px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

.bounce-in {
    animation: bounce-in 0.4s ease;
}

.shake {
    animation: shake 0.3s ease;
}

.fade-up {
    animation: fade-up 0.3s ease;
}

/* ============================================
   Footer
   ============================================ */

.footer {
    background-color: var(--color-black);
    color: var(--color-white);
    border-top: var(--border-width) solid var(--color-black);
    padding: var(--spacing-2xl) 0 var(--spacing-lg);
    margin-top: var(--spacing-2xl);
}

.footer-content {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: var(--spacing-lg);
    margin-bottom: var(--spacing-2xl);
}

.footer-section h3,
.footer-section h4 {
    font-family: var(--font-display);
    font-weight: 700;
    margin-bottom: var(--spacing-md);
}

.footer-section p {
    font-size: 0.9rem;
    line-height: 1.6;
    margin-bottom: var(--spacing-sm);
}

.footer-badge {
    display: inline-block;
    background-color: var(--color-yellow);
    color: var(--color-black);
    padding: var(--spacing-xs) var(--spacing-sm);
    border-radius: var(--border-radius);
    font-size: 0.75rem;
    font-weight: 700;
}

.footer-links {
    list-style: none;
}

.footer-links li {
    margin-bottom: var(--spacing-sm);
}

.footer-links a {
    color: var(--color-yellow);
    transition: color 0.2s ease;
}

.footer-links a:hover {
    color: var(--color-white);
}

.footer-stats {
    list-style: none;
}

.footer-stats li {
    margin-bottom: var(--spacing-sm);
    font-size: 0.9rem;
}

.footer-stats strong {
    color: var(--color-yellow);
    font-family: var(--font-mono);
}

.footer-bottom {
    text-align: center;
    padding-top: var(--spacing-lg);
    border-top: var(--border-width) solid rgba(255, 255, 255, 0.1);
    font-size: 0.85rem;
    color: var(--color-gray);
}

.footer-bottom p {
    margin-bottom: var(--spacing-xs);
}

/* ============================================
   Responsive Design
   ============================================ */

@media (max-width: 768px) {
    .container {
        padding: 0 1rem;
    }

    .brutalist-card {
        padding: var(--spacing-sm);
    }

    .brutalist-btn {
        padding: var(--spacing-xs) var(--spacing-sm);
        font-size: 0.9rem;
    }

    .grid-2 {
        grid-template-columns: 1fr !important;
    }

    .grid-3 {
        grid-template-columns: 1fr !important;
    }

    .grid-6 {
        grid-template-columns: repeat(2, 1fr) !important;
    }
}

/* ============================================
   Utility Classes
   ============================================ */

.hidden {
    display: none !important;
}

.visible {
    display: block !important;
}

.text-center {
    text-align: center;
}

.text-bold {
    font-weight: 700;
    font-family: var(--font-display);
}

.text-mono {
    font-family: var(--font-mono);
}

.mt-lg {
    margin-top: var(--spacing-lg);
}

.mb-lg {
    margin-bottom: var(--spacing-lg);
}

.p-lg {
    padding: var(--spacing-lg);
}

.gap-md {
    gap: var(--spacing-md);
}

.grid-2 {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: var(--spacing-md);
}

.grid-3 {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: var(--spacing-md);
}

.grid-6 {
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    gap: var(--spacing-md);
}

.flex {
    display: flex;
    align-items: center;
}

.flex-col {
    flex-direction: column;
}

.flex-between {
    justify-content: space-between;
}

.flex-center {
    justify-content: center;
}

.flex-wrap {
    flex-wrap: wrap;
}

/* ============================================
   Page Sections
   ============================================ */

.page-section {
    padding: var(--spacing-xl) 0;
}

.page-header {
    padding: var(--spacing-xl) 0;
    border-bottom: var(--border-width) solid var(--color-black);
    margin-bottom: var(--spacing-xl);
}

.section-title {
    font-family: var(--font-display);
    font-size: 2.5rem;
    font-weight: 800;
    margin-bottom: var(--spacing-md);
    line-height: 1.2;
}

@media (min-width: 768px) {
    .section-title {
        font-size: 3rem;
    }
}

.section-subtitle {
    font-size: 1.1rem;
    color: var(--color-gray-light);
    max-width: 600px;
}

/* ============================================
   Hero Section
   ============================================ */

.hero {
    background-color: var(--color-yellow);
    border-bottom: var(--border-width) solid var(--color-black);
    padding: var(--spacing-xl) 0;
}

.hero-content {
    display: grid;
    grid-template-columns: 1fr;
    gap: var(--spacing-lg);
    align-items: center;
}

@media (min-width: 1024px) {
    .hero-content {
        grid-template-columns: 1fr 1fr;
    }
}

.hero-text h1 {
    font-family: var(--font-display);
    font-size: 3rem;
    font-weight: 800;
    line-height: 1.1;
    margin-bottom: var(--spacing-md);
}

@media (min-width: 768px) {
    .hero-text h1 {
        font-size: 3.5rem;
    }
}

.hero-text p {
    font-size: 1.1rem;
    color: var(--color-gray-light);
    margin-bottom: var(--spacing-lg);
    max-width: 500px;
}

.hero-buttons {
    display: flex;
    gap: var(--spacing-md);
    flex-wrap: wrap;
}

.hero-image {
    border: var(--border-width) solid var(--color-black);
    border-radius: var(--border-radius);
    overflow: hidden;
    box-shadow: var(--shadow-hard);
    min-height: 300px;
    background: linear-gradient(135deg, var(--color-teal), var(--color-purple));
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 4rem;
}

/* ============================================
   Stats Bar
   ============================================ */

.stats-bar {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: var(--spacing-md);
    margin-top: var(--spacing-lg);
}

.stat-item {
    text-align: center;
}

.stat-number {
    font-family: var(--font-mono);
    font-size: 2rem;
    font-weight: 700;
    color: var(--color-black);
}

.stat-label {
    font-size: 0.9rem;
    color: var(--color-gray-light);
    margin-top: var(--spacing-xs);
}

/* ============================================
   Language Cards
   ============================================ */

.language-card {
    cursor: pointer;
}

.language-card-header {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    margin-bottom: var(--spacing-md);
}

.language-flag {
    font-size: 3rem;
}

.language-name {
    font-family: var(--font-display);
    font-size: 1.5rem;
    font-weight: 700;
    margin-bottom: var(--spacing-xs);
}

.language-native {
    font-size: 0.9rem;
    color: var(--color-coral);
    font-weight: 600;
    margin-bottom: var(--spacing-md);
}

.language-description {
    font-size: 0.9rem;
    color: var(--color-gray-light);
    margin-bottom: var(--spacing-md);
    line-height: 1.5;
}

.language-stats {
    display: flex;
    gap: var(--spacing-md);
    font-size: 0.85rem;
    margin-bottom: var(--spacing-md);
}

.language-stat {
    display: flex;
    flex-direction: column;
}

.language-stat-value {
    font-family: var(--font-mono);
    font-weight: 700;
    color: var(--color-black);
}

.language-stat-label {
    color: var(--color-gray);
    font-size: 0.75rem;
}

.language-actions {
    display: flex;
    gap: var(--spacing-sm);
}

.language-actions button {
    flex: 1;
    padding: var(--spacing-sm);
    font-size: 0.85rem;
}

/* ============================================
   Flashcard
   ============================================ */

.flashcard-container {
    perspective: 1000px;
}

.flashcard {
    width: 100%;
    min-height: 300px;
    border: var(--border-width) solid var(--color-black);
    border-radius: var(--border-radius);
    padding: var(--spacing-lg);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: transform 0.6s;
    transform-style: preserve-3d;
    box-shadow: var(--shadow-hard);
}

.flashcard.flipped {
    transform: rotateY(180deg);
}

.flashcard-front,
.flashcard-back {
    backface-visibility: hidden;
    width: 100%;
    text-align: center;
}

.flashcard-back {
    transform: rotateY(180deg);
}

.flashcard-word {
    font-family: var(--font-display);
    font-size: 2.5rem;
    font-weight: 800;
    margin-bottom: var(--spacing-md);
}

.flashcard-pronunciation {
    font-family: var(--font-mono);
    font-size: 1.1rem;
    color: var(--color-gray-light);
    margin-bottom: var(--spacing-md);
}

.flashcard-hint {
    font-size: 0.9rem;
    color: var(--color-gray);
}

.flashcard-translation {
    font-family: var(--font-display);
    font-size: 2rem;
    font-weight: 700;
    margin-bottom: var(--spacing-md);
}

.flashcard-example {
    font-size: 0.95rem;
    color: var(--color-gray-light);
    font-style: italic;
}

/* ============================================
   Quiz
   ============================================ */

.quiz-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: var(--spacing-lg);
}

.quiz-progress {
    font-family: var(--font-mono);
    font-size: 0.9rem;
    color: var(--color-gray-light);
}

.quiz-score {
    font-family: var(--font-mono);
    font-size: 0.9rem;
    color: var(--color-teal);
    font-weight: 700;
}

.quiz-question {
    font-family: var(--font-display);
    font-size: 1.5rem;
    font-weight: 700;
    margin-bottom: var(--spacing-lg);
    line-height: 1.3;
}

.quiz-options {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: var(--spacing-md);
    margin-bottom: var(--spacing-lg);
}

@media (min-width: 768px) {
    .quiz-options {
        grid-template-columns: repeat(2, 1fr);
    }
}

.quiz-option {
    padding: var(--spacing-md);
    text-align: left;
    font-weight: 600;
    transition: all 0.2s ease;
    display: flex;
    align-items: center;
    gap: var(--spacing-md);
}

.quiz-option-letter {
    width: 30px;
    height: 30px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 700;
    flex-shrink: 0;
    border: 2px solid var(--color-black);
}

.quiz-option:disabled {
    cursor: not-allowed;
}

.quiz-option.correct {
    background-color: var(--color-teal);
    color: var(--color-black);
}

.quiz-option.incorrect {
    background-color: var(--color-coral);
    color: white;
}

.quiz-feedback {
    padding: var(--spacing-md);
    border: var(--border-width) solid var(--color-black);
    border-radius: var(--border-radius);
    margin-bottom: var(--spacing-lg);
    display: flex;
    gap: var(--spacing-md);
}

.quiz-feedback.correct {
    background-color: #E8FFF8;
}

.quiz-feedback.incorrect {
    background-color: #FFF0F0;
}

.quiz-feedback-icon {
    font-size: 1.5rem;
    flex-shrink: 0;
}

.quiz-feedback-text h3 {
    font-family: var(--font-display);
    font-weight: 700;
    margin-bottom: var(--spacing-xs);
}

.quiz-feedback-text p {
    font-size: 0.9rem;
    color: var(--color-gray-light);
}

/* ============================================
   Results Screen
   ============================================ */

.results-container {
    text-align: center;
    max-width: 600px;
    margin: 0 auto;
}

.results-card {
    padding: var(--spacing-lg);
    margin-bottom: var(--spacing-lg);
}

.results-score {
    font-family: var(--font-mono);
    font-size: 4rem;
    font-weight: 700;
    color: var(--color-black);
    margin-bottom: var(--spacing-md);
}

.results-score-label {
    font-size: 1.1rem;
    color: var(--color-gray-light);
    margin-bottom: var(--spacing-lg);
}

.results-message {
    font-family: var(--font-display);
    font-size: 2rem;
    font-weight: 700;
    margin-bottom: var(--spacing-lg);
}

.results-buttons {
    display: flex;
    flex-direction: column;
    gap: var(--spacing-md);
}

@media (min-width: 768px) {
    .results-buttons {
        flex-direction: row;
    }

    .results-buttons button {
        flex: 1;
    }
}

/* ============================================
   Progress Page
   ============================================ */

.progress-stats {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: var(--spacing-md);
    margin-bottom: var(--spacing-lg);
}

.progress-stat-card {
    text-align: center;
}

.progress-stat-icon {
    width: 50px;
    height: 50px;
    border: 2px solid var(--color-black);
    border-radius: var(--border-radius);
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 0 auto var(--spacing-md);
    font-size: 1.5rem;
}

.progress-stat-value {
    font-family: var(--font-mono);
    font-size: 2rem;
    font-weight: 700;
    color: var(--color-black);
}

.progress-stat-label {
    font-size: 0.9rem;
    color: var(--color-gray-light);
    margin-top: var(--spacing-xs);
}

.achievement-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
    gap: var(--spacing-md);
}

.achievement-badge {
    text-align: center;
    padding: var(--spacing-md);
}

.achievement-icon {
    font-size: 2.5rem;
    margin-bottom: var(--spacing-sm);
}

.achievement-title {
    font-family: var(--font-display);
    font-weight: 700;
    font-size: 0.9rem;
    margin-bottom: var(--spacing-xs);
}

.achievement-desc {
    font-size: 0.75rem;
    color: var(--color-gray-light);
}

.achievement-badge.locked {
    opacity: 0.5;
}

/* ============================================
   Empty State
   ============================================ */

.empty-state {
    text-align: center;
    padding: var(--spacing-2xl) var(--spacing-lg);
}

.empty-state-icon {
    font-size: 4rem;
    margin-bottom: var(--spacing-lg);
}

.empty-state h2 {
    font-family: var(--font-display);
    font-size: 2rem;
    font-weight: 700;
    margin-bottom: var(--spacing-md);
}

.empty-state p {
    font-size: 1rem;
    color: var(--color-gray-light);
    max-width: 400px;
    margin: 0 auto var(--spacing-lg);
}

.empty-state-buttons {
    display: flex;
    gap: var(--spacing-md);
    justify-content: center;
    flex-wrap: wrap;
}

    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LinguaLearn - Learn Foreign Languages</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@700;800&family=DM+Sans:wght@400;500&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div id="app"></div>

    <!-- Navigation Bar -->
    <nav class="navbar">
        <div class="container">
            <div class="navbar-content">
                <div class="navbar-logo">
                    <span class="logo-icon">L</span>
                    <span class="logo-text">LinguaLearn</span>
                </div>
                <div class="navbar-links">
                    <a href="#" onclick="navigateTo('home')" class="nav-link active" data-page="home">Home</a>
                    <a href="#" onclick="navigateTo('languages')" class="nav-link" data-page="languages">Languages</a>
                    <a href="#" onclick="navigateTo('lessons')" class="nav-link" data-page="lessons">Lessons</a>
                    <a href="#" onclick="navigateTo('quiz')" class="nav-link" data-page="quiz">Quiz</a>
                    <a href="#" onclick="navigateTo('progress')" class="nav-link" data-page="progress">Progress</a>
                </div>
                <button class="nav-cta" onclick="navigateTo('lessons')">Start Learning</button>
            </div>
        </div>
    </nav>

    <!-- Main Content -->
    <main id="main-content"></main>

    <!-- Footer -->
    <footer class="footer">
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3>LinguaLearn</h3>
                    <p>Learn any language fast and fun. Interactive lessons, vocabulary flashcards, and quizzes for 6 languages.</p>
                    <p class="footer-badge">6 Languages Available</p>
                </div>
                <div class="footer-section">
                    <h4>Languages</h4>
                    <ul class="footer-links">
                        <li><a href="#" onclick="navigateTo('lessons', 'spanish')">🇪🇸 Spanish</a></li>
                        <li><a href="#" onclick="navigateTo('lessons', 'french')">🇫🇷 French</a></li>
                        <li><a href="#" onclick="navigateTo('lessons', 'japanese')">🇯🇵 Japanese</a></li>
                        <li><a href="#" onclick="navigateTo('lessons', 'german')">🇩🇪 German</a></li>
                        <li><a href="#" onclick="navigateTo('lessons', 'arabic')">🇸🇦 Arabic</a></li>
                        <li><a href="#" onclick="navigateTo('lessons', 'chinese')">🇨🇳 Chinese</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h4>Learn</h4>
                    <ul class="footer-links">
                        <li><a href="#" onclick="navigateTo('lessons')">All Lessons</a></li>
                        <li><a href="#" onclick="navigateTo('lessons')">Vocabulary</a></li>
                        <li><a href="#" onclick="navigateTo('quiz')">Take a Quiz</a></li>
                        <li><a href="#" onclick="navigateTo('progress')">Track Progress</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h4>By the Numbers</h4>
                    <ul class="footer-stats">
                        <li><strong>6</strong> Languages</li>
                        <li><strong>18+</strong> Lessons</li>
                        <li><strong>100+</strong> Vocab Words</li>
                        <li><strong>40+</strong> Quiz Questions</li>
                    </ul>
                </div>
            </div>
            <div class="footer-bottom">
                <p>Made with ❤️ for language learners everywhere</p>
                <p>© 2026 LinguaLearn. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <!-- Scripts -->
    <script src="data.js"></script>
    <script src="app.js"></script>
</body>
</html>

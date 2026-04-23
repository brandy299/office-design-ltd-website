---
name: html-lernpfade-webapps
description: "Wende diesen Skill an, wenn der Nutzer interaktive Web-Apps, digitale Lernpfade, Quizze oder HTML-basierte Unterrichtsmaterialien anfordert. Definiert Design-Standards (Tailwind/CSS), Code-Qualität und didaktische Interaktivität."
---

# SKILL: INTERAKTIVE UNIVERSAL-LERNPFADE (SINGLE-FILE HTML)

Wende diesen Skill zwingend an, wenn der Nutzer interaktive Web-Apps, digitale Lernpfade, Quizze oder HTML-basierte Unterrichtsmaterialien für ein beliebiges Fach anfordert.

## 1. DIDAKTISCHE ARCHITEKTUR (Das 4-Phasen-Modell)
Jeder Lernpfad muss in diese 4 Phasen unterteilt sein (inklusive Navigation und Progress-Bar):
1. **Hook (Einstieg):** Kurzes Szenario, provokante Frage oder Fallbeispiel (z.B. ein Modellunternehmen passend zum Thema).
2. **Input (Erarbeitung):** Kurze, gut lesbare Info-Häppchen. Integriere ein Tab-System (z.B. Basis/Experte oder Theorie/Praxis) und bei Bedarf ein anklickbares Glossar für Fachbegriffe.
3. **Check (Sicherung):** Sofort-Feedback-Aufgaben (Multiple Choice, Lückentext). Eingaben müssen per JavaScript sofort grün/rot aufleuchten und eine Erklärung liefern.
4. **Transfer (Anwendung):** Eine offene Aufgabe (z.B. Textfeld mit Wortzähler) und eine Self-Assessment-Checkliste für die Schüler.

## 2. PFLICHT-CODE-STRUKTUR (SINGLE-FILE)
Das Modul MUSS eine einzige `.html`-Datei sein. Binde folgende externe Ressourcen im `<head>` ein:
- Tailwind CSS: `<script src="https://cdn.tailwindcss.com"></script>`
- Lucide Icons: `<script src="https://unpkg.com/lucide@latest/dist/umd/lucide.js"></script>`
- Canvas Confetti: `<script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.9.2/dist/confetti.browser.min.js"></script>`

## 3. DESIGN & UI/UX (Premium-Look)
- Nutze sanfte Animationen (z.B. `@keyframes fadeIn` oder `shake` für falsche Antworten).
- Wähle eine ansprechende Farbpalette über Tailwind (z.B. Slate für Hintergründe, Indigo/Violet für primäre Aktionen, Emerald für Erfolge).
- Die UI-Sprache (Buttons, Feedback) muss sich an das geforderte Fach anpassen (Deutsch für BWL, Englisch für Business English).
- **Zwingend:** Bei 100% korrekten Antworten oder Abschluss des Moduls muss die `confetti()` Funktion ausgelöst werden.

## 4. GENERIERUNGS-ABLAUF
1. Passe das Modellunternehmen oder das Szenario intelligent an das vom Nutzer gewünschte Fach/Thema an.
2. Generiere den VOLLSTÄNDIGEN, sofort lauffähigen HTML/JS/CSS-Code. Nutze saubere JavaScript-Logik für das Phasen-Management (currentPhase, score, totalQuestions).
3. Lass keine Platzhalter wie `[Inhalt hier]` im Code, sondern generiere direkt passenden, didaktisch hochwertigen Beispiel-Content zum gewünschten Thema, den die Lehrkraft später anpassen kann.
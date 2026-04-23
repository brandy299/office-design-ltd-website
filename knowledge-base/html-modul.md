---
name: html-modul
description: >
  Erstellt vollständige interaktive HTML-Lernmodule (Single-File) für Business English am
  kaufmännischen Berufskolleg NRW. Immer verwenden wenn nach einem interaktiven Modul,
  HTML-Arbeitsblatt, digitalen Übung, Lern-App, Quiz, interaktiver Aufgabe, Online-Übung
  oder „digitalen Material" gefragt wird. Auch bei Begriffen wie „interaktiv", „Schüler
  sollen selbst klicken", „mit Feedback" sofort einsetzen.
  Liest lehrer-core für Design-System und didaktische Struktur.
---

# HTML-MODUL-SKILL: Interaktive Lernmodule Business English NRW

> Lies zuerst `lehrer-core/SKILL.md` für das Design-System, Farbpalette, CDN-Links und die 4-Phasen-Struktur.

## PFLICHT-ARCHITEKTUR (SINGLE-FILE)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>[Modultitel]</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="https://unpkg.com/lucide@latest/dist/umd/lucide.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.9.2/dist/confetti.browser.min.js"></script>
  <style>
    /* Custom animations - immer einbauen */
    @keyframes fadeIn { from { opacity: 0; transform: translateY(8px); } to { opacity: 1; transform: translateY(0); } }
    .fade-in { animation: fadeIn 0.4s ease-out; }
    @keyframes shake { 0%,100%{transform:translateX(0)} 25%{transform:translateX(-6px)} 75%{transform:translateX(6px)} }
    .shake { animation: shake 0.4s ease-in-out; }
    @keyframes pop { 0%{transform:scale(1)} 50%{transform:scale(1.08)} 100%{transform:scale(1)} }
    .pop { animation: pop 0.25s ease-in-out; }
  </style>
</head>
<body class="bg-slate-50 min-h-screen font-sans">
  <!-- PROGRESS BAR (immer oben) -->
  <!-- PHASE CONTAINER (Hook → Input → Check → Transfer) -->
  <!-- NAVIGATION (Weiter/Zurück Buttons) -->
  <script>
    // Phase Management
    // State Tracking (Score, currentPhase, answers)
    // Feedback Functions
    // Confetti Trigger
    lucide.createIcons();
  </script>
</body>
</html>
```

---

## PFLICHT-KOMPONENTEN

### 1. Progress Bar (immer sichtbar)
```html
<div class="fixed top-0 left-0 w-full h-1.5 bg-slate-200 z-50">
  <div id="progress-bar" class="h-full bg-indigo-500 transition-all duration-500" style="width: 0%"></div>
</div>
<!-- Phase Indicator -->
<div class="flex justify-center gap-2 mt-6 mb-4">
  <span id="phase-1" class="phase-dot w-3 h-3 rounded-full bg-indigo-600"></span>
  <span id="phase-2" class="phase-dot w-3 h-3 rounded-full bg-slate-300"></span>
  <span id="phase-3" class="phase-dot w-3 h-3 rounded-full bg-slate-300"></span>
  <span id="phase-4" class="phase-dot w-3 h-3 rounded-full bg-slate-300"></span>
</div>
```

### 2. Phase-Container System
```javascript
const phases = ['hook', 'input', 'check', 'transfer'];
let currentPhase = 0;
let score = 0;
let totalQuestions = 0;

function showPhase(index) {
  phases.forEach((p, i) => {
    document.getElementById(`phase-${p}`).classList.toggle('hidden', i !== index);
  });
  updateProgress(index);
}

function updateProgress(index) {
  const pct = ((index + 1) / phases.length) * 100;
  document.getElementById('progress-bar').style.width = pct + '%';
  // Update phase dots
  document.querySelectorAll('.phase-dot').forEach((dot, i) => {
    dot.className = `phase-dot w-3 h-3 rounded-full ${i <= index ? 'bg-indigo-600' : 'bg-slate-300'}`;
  });
}
```

### 3. Feedback-System (Sofort-Feedback)
```javascript
function showFeedback(isCorrect, element, correctText = '') {
  const feedback = element.querySelector('.feedback') || element.nextElementSibling;
  if (isCorrect) {
    feedback.innerHTML = `<div class="mt-2 p-3 bg-green-50 border border-green-200 rounded-xl text-green-700 text-sm fade-in">
      <span class="font-semibold">✓ Correct!</span> ${correctText}
    </div>`;
    element.classList.add('pop');
    score++;
  } else {
    feedback.innerHTML = `<div class="mt-2 p-3 bg-red-50 border border-red-200 rounded-xl text-red-700 text-sm fade-in">
      <span class="font-semibold">✗ Not quite.</span> ${correctText}
    </div>`;
    element.classList.add('shake');
    setTimeout(() => element.classList.remove('shake'), 500);
  }
}
```

### 4. Confetti (bei 100%)
```javascript
function checkAndCelebrate() {
  if (score === totalQuestions) {
    confetti({
      particleCount: 120,
      spread: 70,
      origin: { y: 0.6 },
      colors: ['#6366f1', '#8b5cf6', '#a78bfa', '#fbbf24']
    });
  }
}
```

### 5. Vocabulary Modal
```javascript
const vocab = {
  'complaint': 'A statement that something is unsatisfactory. E.g.: "We received several complaints about the delivery."',
  'invoice': 'A bill listing goods/services provided. E.g.: "Please find the invoice attached."'
  // weitere Begriffe...
};

function openVocabModal(word) {
  document.getElementById('vocab-modal').classList.remove('hidden');
  document.getElementById('vocab-term').textContent = word;
  document.getElementById('vocab-def').textContent = vocab[word] || 'Definition not found.';
}
```

---

## PHASEN-TEMPLATES

### HOOK-Phase
```html
<section id="phase-hook" class="max-w-2xl mx-auto px-4 py-8 fade-in">
  <!-- Label -->
  <div class="flex items-center gap-2 mb-4">
    <div class="w-8 h-8 bg-amber-100 rounded-full flex items-center justify-center">
      <i data-lucide="zap" class="w-4 h-4 text-amber-600"></i>
    </div>
    <span class="text-xs font-semibold uppercase tracking-widest text-amber-600">Warm Up</span>
  </div>
  
  <!-- Stimulus (Bild, Zitat, Szenario) -->
  <div class="bg-white rounded-2xl shadow-sm p-6 mb-6 border-l-4 border-amber-400">
    <p class="text-slate-500 text-sm mb-2">Scenario</p>
    <p class="text-slate-800 text-lg font-medium">[Hook-Text]</p>
  </div>
  
  <!-- Reflection Question -->
  <div class="bg-amber-50 rounded-xl p-5">
    <p class="font-semibold text-slate-700 mb-3">Think about it:</p>
    <p class="text-slate-600">[Einstiegsfrage]</p>
    <!-- Optional: Textarea für freie Antwort -->
    <textarea class="w-full mt-3 p-3 rounded-xl border border-amber-200 text-slate-700 text-sm resize-none h-20 bg-white" 
              placeholder="Your thoughts..."></textarea>
  </div>
  
  <button onclick="showPhase(1)" class="mt-6 w-full bg-indigo-600 text-white py-3 rounded-xl font-semibold hover:bg-indigo-700 transition-colors">
    Let's dive in →
  </button>
</section>
```

### INPUT-Phase
```html
<section id="phase-input" class="max-w-2xl mx-auto px-4 py-8 hidden fade-in">
  <div class="flex items-center gap-2 mb-4">
    <div class="w-8 h-8 bg-blue-100 rounded-full flex items-center justify-center">
      <i data-lucide="book-open" class="w-4 h-4 text-blue-600"></i>
    </div>
    <span class="text-xs font-semibold uppercase tracking-widest text-blue-600">Learn</span>
  </div>
  
  <!-- Chunk 1 -->
  <div class="bg-white rounded-2xl shadow-sm p-6 mb-4">
    <h3 class="font-bold text-slate-800 mb-3">[Chunk-Titel]</h3>
    <p class="text-slate-600 leading-relaxed">[Inhalt max. 3 Absätze]</p>
    
    <!-- Key Phrases Box (immer einbauen) -->
    <div class="mt-4 bg-blue-50 rounded-xl p-4">
      <p class="text-xs font-semibold text-blue-600 uppercase tracking-wide mb-3">Key Phrases</p>
      <div class="space-y-2">
        <div class="flex justify-between items-start">
          <span class="text-slate-700 font-medium text-sm">[Phrase]</span>
          <span class="text-slate-500 text-sm ml-4">[Kontext/Verwendung]</span>
        </div>
        <!-- mehr Phrasen... -->
      </div>
    </div>
  </div>
  
  <!-- Vocabulary with clickable terms -->
  <div class="bg-white rounded-2xl shadow-sm p-5 mb-4">
    <p class="text-xs font-semibold text-slate-400 uppercase tracking-wide mb-3">
      <i data-lucide="book" class="w-3.5 h-3.5 inline mr-1"></i>Vocabulary
    </p>
    <div class="flex flex-wrap gap-2">
      <button onclick="openVocabModal('complaint')" 
              class="px-3 py-1.5 bg-indigo-50 text-indigo-700 rounded-lg text-sm hover:bg-indigo-100 transition-colors underline decoration-dotted">
        complaint
      </button>
      <!-- mehr Begriffe... -->
    </div>
  </div>
  
  <!-- Tab-System (Basis/Expert) -->
  <div class="bg-white rounded-2xl shadow-sm overflow-hidden mb-4">
    <div class="flex border-b border-slate-100">
      <button onclick="switchTab('basis')" id="tab-basis" 
              class="tab-btn flex-1 py-3 text-sm font-medium text-indigo-600 border-b-2 border-indigo-600">
        📗 Basis
      </button>
      <button onclick="switchTab('expert')" id="tab-expert"
              class="tab-btn flex-1 py-3 text-sm font-medium text-slate-400 hover:text-slate-600">
        📘 Expert
      </button>
    </div>
    <div id="content-basis" class="p-5">
      <p class="text-slate-600 text-sm">[Vereinfachter Inhalt / mehr Scaffolding]</p>
    </div>
    <div id="content-expert" class="p-5 hidden">
      <p class="text-slate-600 text-sm">[Erweiterter Inhalt / weniger Hilfe]</p>
    </div>
  </div>
  
  <button onclick="showPhase(2)" class="w-full bg-indigo-600 text-white py-3 rounded-xl font-semibold hover:bg-indigo-700 transition-colors">
    Ready to check your knowledge →
  </button>
</section>
```

### CHECK-Phase
```html
<section id="phase-check" class="max-w-2xl mx-auto px-4 py-8 hidden fade-in">
  <div class="flex items-center gap-2 mb-4">
    <div class="w-8 h-8 bg-emerald-100 rounded-full flex items-center justify-center">
      <i data-lucide="check-circle" class="w-4 h-4 text-emerald-600"></i>
    </div>
    <span class="text-xs font-semibold uppercase tracking-widest text-emerald-600">Check</span>
  </div>

  <!-- Score Display -->
  <div class="bg-white rounded-2xl shadow-sm p-4 mb-4 flex items-center justify-between">
    <span class="text-slate-500 text-sm">Your score</span>
    <span id="score-display" class="font-bold text-indigo-600">0 / [total]</span>
  </div>

  <!-- MC Question Template -->
  <div class="bg-white rounded-2xl shadow-sm p-6 mb-4" id="q1">
    <p class="font-semibold text-slate-800 mb-4">
      <span class="text-indigo-500 mr-2">Q1.</span>[Frage]
    </p>
    <div class="space-y-2">
      <button onclick="checkMC(this, false, 'q1', 'Feedback: [Erklärung]')" 
              class="mc-btn w-full text-left px-4 py-3 rounded-xl border border-slate-200 text-slate-600 text-sm hover:border-indigo-300 hover:bg-indigo-50 transition-colors">
        A) [Falsche Antwort]
      </button>
      <button onclick="checkMC(this, true, 'q1', '✓ Correct! [Erklärung]')"
              class="mc-btn w-full text-left px-4 py-3 rounded-xl border border-slate-200 text-slate-600 text-sm hover:border-indigo-300 hover:bg-indigo-50 transition-colors">
        B) [Richtige Antwort]
      </button>
      <button onclick="checkMC(this, false, 'q1', 'Feedback: [Erklärung]')"
              class="mc-btn w-full text-left px-4 py-3 rounded-xl border border-slate-200 text-slate-600 text-sm hover:border-indigo-300 hover:bg-indigo-50 transition-colors">
        C) [Falsche Antwort]
      </button>
    </div>
    <div class="feedback mt-1"></div>
  </div>

  <!-- Gap Fill Template -->
  <div class="bg-white rounded-2xl shadow-sm p-6 mb-4" id="q2">
    <p class="font-semibold text-slate-800 mb-4">
      <span class="text-indigo-500 mr-2">Q2.</span>Complete the sentence:
    </p>
    <p class="text-slate-600">
      "We would like to ___
      <input type="text" id="gap-q2" placeholder="type here" 
             class="border-b-2 border-indigo-300 bg-transparent px-2 text-indigo-700 font-medium focus:outline-none w-32">
      ___ for the delay."
    </p>
    <button onclick="checkGap('gap-q2', ['apologise', 'apologize'], 'q2', 'Well done!')"
            class="mt-3 px-4 py-2 bg-emerald-600 text-white rounded-lg text-sm hover:bg-emerald-700 transition-colors">
      Check
    </button>
    <div class="feedback mt-1"></div>
  </div>

  <button onclick="goToTransfer()" id="check-next-btn" 
          class="w-full bg-indigo-600 text-white py-3 rounded-xl font-semibold hover:bg-indigo-700 transition-colors hidden">
    Now apply what you've learned →
  </button>
</section>
```

### TRANSFER-Phase
```html
<section id="phase-transfer" class="max-w-2xl mx-auto px-4 py-8 hidden fade-in">
  <div class="flex items-center gap-2 mb-4">
    <div class="w-8 h-8 bg-violet-100 rounded-full flex items-center justify-center">
      <i data-lucide="star" class="w-4 h-4 text-violet-600"></i>
    </div>
    <span class="text-xs font-semibold uppercase tracking-widest text-violet-600">Apply</span>
  </div>
  
  <!-- Szenario (immer Modellunternehmen) -->
  <div class="bg-violet-50 rounded-2xl p-5 mb-4 border-l-4 border-violet-400">
    <p class="text-xs font-semibold text-violet-600 uppercase mb-2">🏢 Office Design Ltd. – Your Task</p>
    <p class="text-slate-700">[Kontext + Aufgabenstellung]</p>
  </div>
  
  <!-- Phrase Box (immer als Hilfe) -->
  <details class="mb-4">
    <summary class="cursor-pointer bg-white rounded-xl shadow-sm px-5 py-3 text-sm font-medium text-slate-600 hover:bg-slate-50">
      💬 Useful Phrases (click to expand)
    </summary>
    <div class="bg-white rounded-b-xl shadow-sm px-5 pb-4 mt-0 border-t border-slate-100">
      <ul class="mt-3 space-y-1.5 text-sm text-slate-600">
        <li><span class="font-medium text-indigo-600">[Phrase 1]</span> – [Verwendung]</li>
        <li><span class="font-medium text-indigo-600">[Phrase 2]</span> – [Verwendung]</li>
        <!-- mehr... -->
      </ul>
    </div>
  </details>
  
  <!-- Writing Area -->
  <div class="bg-white rounded-2xl shadow-sm p-5 mb-4">
    <label class="text-sm font-semibold text-slate-600 mb-2 block">Your response (aim for 80–120 words):</label>
    <textarea id="transfer-text" 
              class="w-full p-4 rounded-xl border border-slate-200 text-slate-700 text-sm resize-none h-40 focus:outline-none focus:ring-2 focus:ring-indigo-300"
              placeholder="Start writing here..."></textarea>
    <div class="flex justify-between items-center mt-2">
      <span id="word-count" class="text-xs text-slate-400">0 words</span>
      <span class="text-xs text-slate-400">Target: 80–120 words</span>
    </div>
  </div>
  
  <!-- Self-Assessment Raster -->
  <div class="bg-white rounded-2xl shadow-sm p-5 mb-4">
    <p class="text-sm font-semibold text-slate-700 mb-3">✅ Self-check before submitting:</p>
    <div class="space-y-2">
      <label class="flex items-center gap-3 text-sm text-slate-600 cursor-pointer">
        <input type="checkbox" class="w-4 h-4 rounded text-indigo-600"> 
        I used formal/appropriate language throughout
      </label>
      <label class="flex items-center gap-3 text-sm text-slate-600 cursor-pointer">
        <input type="checkbox" class="w-4 h-4 rounded text-indigo-600"> 
        I included all required information
      </label>
      <label class="flex items-center gap-3 text-sm text-slate-600 cursor-pointer">
        <input type="checkbox" class="w-4 h-4 rounded text-indigo-600"> 
        I used at least 2 key phrases from today's lesson
      </label>
    </div>
  </div>
  
  <!-- Completion -->
  <button onclick="completeModule()" 
          class="w-full bg-gradient-to-r from-indigo-600 to-violet-600 text-white py-3 rounded-xl font-semibold hover:opacity-90 transition-opacity">
    🎉 Complete Module
  </button>
</section>
```

---

## JAVASCRIPT-HELFER

```javascript
// Multiple Choice Handler
function checkMC(btn, isCorrect, questionId, feedbackText) {
  const container = document.getElementById(questionId);
  container.querySelectorAll('.mc-btn').forEach(b => b.disabled = true);
  
  if (isCorrect) {
    btn.classList.add('bg-green-50', 'border-green-400', 'text-green-700');
    score++;
    document.getElementById('score-display').textContent = `${score} / ${totalQuestions}`;
  } else {
    btn.classList.add('bg-red-50', 'border-red-400', 'text-red-700');
    btn.classList.add('shake');
  }
  container.querySelector('.feedback').innerHTML = 
    `<p class="mt-2 text-sm ${isCorrect ? 'text-green-600' : 'text-red-600'} fade-in">${feedbackText}</p>`;
  
  checkAllAnswered();
}

// Gap-Fill Handler
function checkGap(inputId, correctAnswers, questionId, successMsg) {
  const input = document.getElementById(inputId);
  const userAnswer = input.value.trim().toLowerCase();
  const isCorrect = correctAnswers.map(a => a.toLowerCase()).includes(userAnswer);
  
  const container = document.getElementById(questionId);
  if (isCorrect) {
    input.classList.add('border-green-400', 'text-green-700');
    score++;
    document.getElementById('score-display').textContent = `${score} / ${totalQuestions}`;
  } else {
    input.classList.add('border-red-400', 'text-red-700');
    input.classList.add('shake');
  }
  container.querySelector('.feedback').innerHTML =
    `<p class="mt-2 text-sm ${isCorrect ? 'text-green-600' : 'text-red-600'} fade-in">
      ${isCorrect ? successMsg : `Try again. Correct: <strong>${correctAnswers[0]}</strong>`}
    </p>`;
  input.disabled = true;
  checkAllAnswered();
}

// Word Counter
document.getElementById('transfer-text').addEventListener('input', function() {
  const words = this.value.trim().split(/\s+/).filter(w => w).length;
  document.getElementById('word-count').textContent = `${words} words`;
});

// Tab Switcher
function switchTab(tab) {
  ['basis', 'expert'].forEach(t => {
    document.getElementById(`content-${t}`).classList.toggle('hidden', t !== tab);
    document.getElementById(`tab-${t}`).className = t === tab
      ? 'tab-btn flex-1 py-3 text-sm font-medium text-indigo-600 border-b-2 border-indigo-600'
      : 'tab-btn flex-1 py-3 text-sm font-medium text-slate-400 hover:text-slate-600';
  });
}

// Module Complete
function completeModule() {
  confetti({ particleCount: 150, spread: 80, origin: { y: 0.6 },
    colors: ['#6366f1', '#8b5cf6', '#fbbf24', '#34d399'] });
  // Zeige Abschluss-Screen
}
```

---

## QUALITÄTS-CHECKLISTE HTML-MODUL

- [ ] Single-File (alles in einer .html Datei)
- [ ] Alle 4 Phasen (Hook/Input/Check/Transfer) implementiert
- [ ] Progress Bar funktioniert korrekt
- [ ] Sofort-Feedback bei Check-Aufgaben
- [ ] Konfetti bei 100% oder Modulabschluss
- [ ] Vocab-Modal mit min. 5 Fachbegriffen
- [ ] Phrase Box im Transfer (als `<details>` Accordion)
- [ ] Wort-Zähler im Transfer-Textarea
- [ ] Tab-System (Basis/Expert) im Input
- [ ] Self-Assessment Checklist im Transfer
- [ ] Mobile-responsive (iPad-Test!)
- [ ] Modellunternehmen „Office Design Ltd." in Transfer eingebunden
- [ ] Keine externe API-Abhängigkeiten (offline-fähig)

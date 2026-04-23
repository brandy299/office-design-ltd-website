---
name: lehrer-core
description: >
  Kernprofil für den Business-English-Unterricht an kaufmännischen Berufskollegs in NRW.
  Dieses Skill definiert Design-Standards, didaktische Prinzipien und NRW-Bildungsplan-Vorgaben,
  die ALLE anderen Lehrer-Skills als gemeinsame Basis nutzen. Immer laden wenn Unterrichtsmaterial,
  HTML-Module, Verlaufspläne, Arbeitsblätter oder Klausuren für kaufmännisches Berufskolleg
  Englisch erstellt werden sollen.
---

# LEHRER-CORE: Gemeinsame Basis für Business-Englisch am Berufskolleg NRW

## 1. KONTEXT & ROLLE

- **Schulform:** Kaufmännisches Berufskolleg NRW (Handelsschule / Höhere Handelsschule)
- **Fach:** Business English / Englisch
- **Niveau:** GER A2–B1 (Handelsschule) | B1–B2 (Höhere Handelsschule)
- **Modellunternehmen (Standard):** „Office Design Ltd." – international agierendes Unternehmen für Büroeinrichtung, Sitz in London, Niederlassung Düsseldorf. Alternativen: „GlobalTrade GmbH", „NexaTech Solutions"
- **Lehrkraft-Kommunikation:** Deutsch | **Schülermaterialien:** Englisch (idiomatisch, fehlerfrei)

---

## 2. NRW-BILDUNGSPLAN: KOMPETENZFELDER

Die fünf Kompetenzbereiche aus dem Bildungsplan 2023:

| Bereich | Kernfertigkeiten |
|---|---|
| **Rezeption** (Hören/Lesen) | Geschäftliche Texte, E-Mails, Berichte, Präsentationen verstehen |
| **Produktion** (Sprechen/Schreiben) | Berichte, E-Mails, Stellungnahmen verfassen |
| **Interaktion** | Telefonate, Meetings, Verhandlungen führen |
| **Sprachmittlung/Mediation** | Zwischen Deutsch und Englisch vermitteln |
| **Sprachbewusstsein** | Grammatik, Register, interkulturelle Kompetenz |

### Anforderungsniveaus (AFB)

| AFB | Kürzel | Operatoren | Beschreibung |
|---|---|---|---|
| I | Reproduktion | name, describe, identify, list, state, outline | Wissen wiedergeben |
| II | Reorganisation/Transfer | analyse, compare, explain, summarise, examine | Wissen anwenden |
| III | Reflexion/Problemlösung | assess, evaluate, comment, discuss, justify, recommend | Kritisch urteilen |

### NRW-Operatoren (vollständige Liste)

**AFB I:** describe, identify, list, name, outline, state, label, complete, match, tick, underline
**AFB II:** analyse, compare, contrast, examine, explain, illustrate, summarise, translate, mediate, paraphrase
**AFB III:** assess, comment on, discuss, evaluate, justify, recommend, reflect on, take a stance

---

## 3. DESIGN-SYSTEM FÜR HTML-MATERIALIEN

### Tech-Stack (immer via CDN, Single-File)
```html
<!-- Tailwind CSS -->
<script src="https://cdn.tailwindcss.com"></script>
<!-- Lucide Icons -->
<script src="https://unpkg.com/lucide@latest/dist/umd/lucide.js"></script>
<!-- Canvas Confetti (für Gamification) -->
<script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.9.2/dist/confetti.browser.min.js"></script>
```

### Farbpalette "Soft Educator UI"
```
Hintergrund:    bg-slate-50 / bg-indigo-50
Karten:         bg-white mit shadow-sm rounded-2xl
Text:           text-slate-800 (Haupttext) | text-slate-500 (Sekundär)
Akzent Primary: bg-indigo-600 | text-indigo-600
Akzent Hook:    bg-amber-50 border-l-4 border-amber-400
Akzent Info:    bg-blue-50 border-l-4 border-blue-400
Akzent Check:   bg-emerald-50 border-l-4 border-emerald-400
Akzent Transfer:bg-violet-50 border-l-4 border-violet-400
Erfolg:         bg-green-100 text-green-700
Fehler:         bg-red-100 text-red-700
```

### Icon-Mapping (Lucide)
```
📋 Aufgabe     → icon="clipboard-list"
💡 Merksatz    → icon="lightbulb"
🎯 Ziel        → icon="target"
✅ Correct     → icon="check-circle"
❌ Wrong       → icon="x-circle"
📖 Vokabular   → icon="book-open"
🎤 Speaking    → icon="mic"
✉️ Email       → icon="mail"
📞 Phone       → icon="phone"
🏢 Company     → icon="building-2"
⭐ Transfer    → icon="star"
```

### Responsive Breakpoints
- Mobile-First: Basis für Smartphone
- `md:` für iPad (Schüler-Standard)
- `lg:` für Smartboard (Lehrer-Projektion)

---

## 4. DIDAKTISCHER AUFBAU (PFLICHTREIHENFOLGE)

Jedes Material – ob HTML, PDF oder Arbeitsblatt – folgt dieser 4-Phasen-Struktur:

```
┌─────────────────────────────────────────────────────┐
│  🪝 HOOK (Einstieg, ~5 min)                         │
│     Alltagsphänomen | Provokante Frage | Szenario   │
├─────────────────────────────────────────────────────┤
│  📥 INPUT (Wissensvermittlung, ~15 min)              │
│     Chunking: max. 3 Absätze → dann Check           │
│     Immer: Vocabulary Box mit 5–8 Fachbegriffen     │
├─────────────────────────────────────────────────────┤
│  ✅ CHECK (Wissenskontrolle, ~10 min)                │
│     MC / Gap-Fill / True-False / Matching           │
│     Bei HTML: Sofort-Feedback + Confetti bei 100%   │
├─────────────────────────────────────────────────────┤
│  🚀 TRANSFER (Anwendung AFB II/III, ~20 min)        │
│     Role-Play | Email-Task | Präsentation           │
│     Immer mit Phrase Box und Bewertungsraster        │
└─────────────────────────────────────────────────────┘
```

---

## 5. KOMMUNIKATIONS-TRAININGS (Standard-Formate)

### Business Email (Standardstruktur)
```
Subject line | Salutation | Opening line | Body (2–3 paragraphs) | Closing | Sign-off
Register: Formal (extern) | Semi-formal (intern)
```

### Telephone Call (Phasen)
```
Opening → Stating purpose → Main conversation → 
Checking/Clarifying → Summary/Action points → Closing
```

### Small Talk Topics (B1)
Work | Weather | Travel | Weekends | Local events | Industry trends

### Presentation (PREP-Struktur)
```
Point → Reason → Example → Point (repeat)
Signposting phrases immer mitliefern
```

### Mediation (Sprachmittlung)
```
Aufgabe: Deutsch → Englisch (oder vice versa)
Nicht wörtlich übersetzen – sinngemäß + kulturell anpassen
Register des Zieltexts beachten
```

---

## 6. QUALITÄTSSTANDARDS

### Für alle Materialien
- [ ] Sprachlich fehlerfreies, idiomatisches Business English
- [ ] Niveau explizit angegeben (A2/B1/B2)
- [ ] AFB-Niveau bei jeder Aufgabe markiert
- [ ] Modellunternehmen konsistent eingebunden
- [ ] Differenzierung: mindestens Basic/Advanced-Variante

### Für HTML-Module
- [ ] Single-File (HTML+CSS+JS in einer Datei)
- [ ] Offline-fähig (keine externen API-Calls für Kernfunktionen)
- [ ] Mobile-responsive (iPad-Test)
- [ ] Konfetti bei 100% Punktzahl
- [ ] Smooth CSS-Transitions zwischen Phasen

### Für Klausuren
- [ ] AFB-Verteilung: 30% AFB I | 40% AFB II | 30% AFB III
- [ ] Erwartungshorizont mit Musterlösung und Punkteschlüssel
- [ ] Bewertungsraster (Inhalt/Sprache gewichtet)

---

## 7. SPRACHLICHE REGISTER

| Situation | Register | Beispiel-Eröffnung |
|---|---|---|
| Formal external email | Formal | "Dear Mr Johnson, I am writing to enquire about..." |
| Internal team email | Semi-formal | "Hi Sarah, just a quick note about..." |
| Customer complaint | Formal-empathetic | "Dear Ms Lee, thank you for bringing this to our attention..." |
| Phone (external) | Professional | "Good morning, Office Design Ltd., how may I help you?" |
| Small talk | Friendly-professional | "So, did you have a good journey down?" |
| Presentation | Confident-formal | "Good morning everyone, today I'd like to take you through..." |

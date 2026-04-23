---
name: klausur
description: >
  Erstellt vollständige Klausuren mit Erwartungshorizont (EHZ) und Bewertungsrastern für
  Business English am kaufmännischen Berufskolleg NRW. Immer verwenden wenn nach einer
  Klausur, Leistungsüberprüfung, Test, Klassenarbeit, Prüfungsaufgabe, Erwartungshorizont
  oder Bewertungsraster gefragt wird. Auch bei Begriffen wie „Lernzielkontrolle",
  „schriftliche Arbeit" oder „Prüfung" sofort einsetzen. Liest lehrer-core für AFB-Operatoren.
---

# KLAUSUR-SKILL: Leistungsüberprüfungen Business English NRW

> Lies zuerst `lehrer-core/SKILL.md` für AFB-Operatoren, Kompetenzbereiche und Bewertungsdeskriptoren.

## PFLICHT-PARAMETER (vor Erstellung klären)

```
Bildungsgang:  Handelsschule (A2/B1) | Höhere Handelsschule (B1/B2)
Klasse:        [z.B. HH12a]
Dauer:         45 min | 90 min | 120 min
Thema:         [z.B. "Business Correspondence – Complaints & Apologies"]
Textsorten:    [z.B. Email, Report, Dialogue, Article]
Hilfsmittel:   Wörterbuch erlaubt/nicht erlaubt
Gesamtpunkte:  [z.B. 50 Punkte]
```

---

## AFB-VERTEILUNG (PFLICHT)

| Bildungsgang | AFB I | AFB II | AFB III |
|---|---|---|---|
| Handelsschule (A2/B1) | 40% | 40% | 20% |
| Höhere Handelsschule (B1/B2) | 30% | 40% | 30% |

**Bei 50 Punkten (HH):** 15 Pkt. AFB I | 20 Pkt. AFB II | 15 Pkt. AFB III

---

## STANDARD-KLAUSUR-STRUKTUR (90 min / 50 Pkt.)

```
TEIL A: REZEPTION (Lesen/Hören) — ~15 Pkt. | AFB I–II
  A1: Reading Comprehension (authentischer/adaptierter Text)
      → True/False/Not Given (AFB I, 5 Pkt.)
      → Short-answer questions (AFB II, 5 Pkt.)
      → Vocabulary in context (AFB I, 5 Pkt.)

TEIL B: SPRACHMITTLUNG/MEDIATION — ~10 Pkt. | AFB II
  B1: Mediation Task
      → Deutschen Text auf Englisch sinngemäß übertragen
      → Adressatengerecht und situationsangemessen

TEIL C: PRODUKTION (Schreiben) — ~20 Pkt. | AFB II–III
  C1: Textsorten-Aufgabe (Email / Report / Article)
      → Klarer Schreibauftrag mit Kontext (Modellunternehmen)
      → Wortanzahl angegeben (z.B. 150–200 words)

TEIL D: REFLEXION/TRANSFER — ~5 Pkt. | AFB III
  D1: Comment / Evaluation / Recommendation
      → 2–4 Sätze zu einer übergeordneten Frage
```

---

## AUFGABENFORMATE UND PUNKTVERGABE

### Reading Comprehension
```
True / False / Not Given:     1 Pkt. pro Item
Short answer (2–3 sentences): 2 Pkt. pro Frage (Inhalt 1 + Sprache 1)
Vocabulary matching:          1 Pkt. pro Paar
Gap-fill:                     1 Pkt. pro Lücke
```

### Mediation (Sprachmittlung)
```
Bewertung nach:
- Inhalt (Vollständigkeit, Sinngemäßheit):  50%
- Sprache (Register, Korrektheit):           50%

Pro Mediationsaufgabe maximal 10 Punkte:
  Inhalt:    5 Pkt. (1 Pkt. pro Kernaussage)
  Sprache:   5 Pkt. (Wortschatz 2 + Grammatik 2 + Register 1)
```

### Produktion (Email / Report / Article)
```
Gesamtpunkte z.B. 20 Pkt., aufgeteilt:

INHALT (10 Pkt.):
  - Aufgabenbewältigung / Task achievement:   4 Pkt.
  - Vollständigkeit der geforderten Punkte:   3 Pkt.
  - Kohärenz / logischer Aufbau:              3 Pkt.

SPRACHE (10 Pkt.):
  - Allgemeiner Wortschatz:                   3 Pkt.
  - Fachwortschatz / Funktionswortschatz:     2 Pkt.
  - Grammatische Strukturen:                  3 Pkt.
  - Satzstrukturen / Verknüpfungen:           2 Pkt.
```

---

## NOTENSCHLÜSSEL (STANDARD NRW)

| Note | Punkte (von 50) | Prozent |
|------|-----------------|---------|
| sehr gut | 47–50 | 94–100% |
| gut | 40–46 | 80–93% |
| befriedigend | 30–39 | 60–79% |
| ausreichend | 20–29 | 40–59% |
| mangelhaft | 10–19 | 20–39% |
| ungenügend | 0–9 | 0–19% |

*Hinweis: Schule kann eigenen Schlüssel vorgeben – dann anpassen.*

---

## ERWARTUNGSHORIZONT (EHZ) – AUFBAU

Der EHZ wird immer in folgender Struktur erstellt:

### EHZ Struktur
```
┌─────────────────────────────────────┐
│ 1. DECKBLATT mit Metadaten          │
│ 2. AUFGABEN-ÜBERSICHT (Tabelle)     │
│ 3. MUSTERLÖSUNGEN pro Teilaufgabe   │
│ 4. BEWERTUNGSRASTER Produktion      │
│ 5. NOTENSCHLÜSSEL                   │
│ 6. HINWEISE FÜR KORREKTOREN         │
└─────────────────────────────────────┘
```

### EHZ Aufgaben-Übersicht (Tabelle)
```markdown
| Aufgabe | Kompetenz | AFB | Operator | Max. Pkt. | Zeitrichtwert |
|---------|-----------|-----|----------|-----------|---------------|
| A1a | Rezeption | I | identify | 5 | 10 min |
| A1b | Rezeption | II | explain | 5 | 10 min |
| B1 | Mediation | II | mediate | 10 | 20 min |
| C1 | Produktion | II/III | write | 20 | 35 min |
| D1 | Reflexion | III | evaluate | 5 | 10 min |
| **Gesamt** | | | | **45** | **85 min** |
```

### EHZ Musterlösung Email (Beispiel)
```
Erwartete Inhaltspunkte (je 1 Pkt.):
☐ Klare Betreffzeile / Subject line
☐ Formale Anrede (Dear Mr/Ms + Name)
☐ Höfliche Eröffnung (Bezug auf vorherigen Kontakt)
☐ Kernaussage 1: [konkret benennen]
☐ Kernaussage 2: [konkret benennen]
☐ Kernaussage 3: [konkret benennen]
☐ Lösungsvorschlag / Action point
☐ Formaler Abschluss (Yours sincerely / Kind regards)

Sprachliche Mindestanforderungen:
- Durchgängig formales Register
- Korrekte Verwendung von mind. 3 Fachbegriffen
- Keine schwerwiegenden Fehler, die Verständnis beeinträchtigen
```

---

## BEWERTUNGSRASTER PRODUKTION (B1/B2)

Basierend auf NRW-Bildungsplan Deskriptoren:

### Inhalt (max. 10 Punkte)

| Punkte | Beschreibung |
|--------|-------------|
| 9–10 | Aufgabe vollständig und präzise gelöst; alle geforderten Punkte adressiert; logischer, kohärenter Aufbau |
| 7–8 | Aufgabe weitgehend gelöst; die meisten Punkte adressiert; Aufbau weitgehend kohärent |
| 5–6 | Aufgabe teilweise gelöst; einige Punkte fehlen; Aufbau stellenweise inkohärent |
| 3–4 | Aufgabe nur ansatzweise gelöst; wesentliche Punkte fehlen |
| 1–2 | Aufgabe kaum gelöst; inhaltlich nicht angemessen |
| 0 | Kein verwertbarer Inhalt |

### Sprache (max. 10 Punkte)

| Kriterium | sehr gut (2) | gut (1,5) | befriedigend (1) | ausreichend (0,5) | mangelhaft (0) |
|-----------|-------------|----------|-----------------|-------------------|---------------|
| **Allg. Wortschatz** (2 Pkt.) | treffsicher, korrekt | überwiegend korrekt | weniger treffsicher | begrenzt, Lücken | stark begrenzt |
| **Fachwortschatz** (2 Pkt.) | treffsicher, korrekt | überwiegend korrekt | weniger treffsicher | begrenzt | kaum vorhanden |
| **Grammatik** (3 Pkt.) | wenige Fehler, kein Verständnisproblem | Grundbeherrschung trotz Fehlern | erkennbare Beherrschung, recht hohe Fehlerzahl | Fehler erschwerend | Fehler verhindernd |
| **Satzstrukturen** (3 Pkt.) | variabel, gut verknüpft | einfach, aber verknüpft | kurz, wenig verknüpft | sehr einfach, gleichförmig | sprachuntypisch |

---

## KLAUSUR-HEADER VORLAGE

```
────────────────────────────────────────────────────
[SCHULNAME] | Berufskolleg | Fachbereich: Wirtschaft
────────────────────────────────────────────────────
ENGLISCH – SCHRIFTLICHE LEISTUNGSÜBERPRÜFUNG

Klasse: ___________    Datum: ___________
Name: _____________    Note: ____________

Dauer: 90 Minuten
Hilfsmittel: [Einsprachiges Wörterbuch | Kein Hilfsmittel]
Gesamtpunktzahl: _____ / 50 Punkte

Bitte schreiben Sie leserlich und vollständig.
────────────────────────────────────────────────────
```

---

## QUALITÄTS-CHECKLISTE KLAUSUR

- [ ] AFB-Verteilung entspricht Bildungsgang-Vorgabe (30/40/30 oder 40/40/20)
- [ ] Alle Aufgaben haben klare Operatoren
- [ ] Punkt-Angaben bei jeder Aufgabe sichtbar
- [ ] Zeitrichtwerte im EHZ angegeben (Summe ≤ Klausurdauer)
- [ ] Schreibauftrag enthält Wortanzahl-Vorgabe
- [ ] Modellunternehmen als Kontext eingebunden
- [ ] EHZ enthält konkrete Musterlösung (nicht nur Stichworte)
- [ ] Notenschlüssel beigefügt
- [ ] Mediation-Aufgabe enthält klaren Ausgangstext (DE) und Adressat
- [ ] Authentische/realistische Business-Situationen

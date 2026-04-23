---
name: verlaufsplan
description: >
  Erstellt detaillierte tabellarische Unterrichtsverlaufspläne für Business English am
  kaufmännischen Berufskolleg NRW. Immer verwenden wenn nach einer Unterrichtsplanung,
  Stundenverlauf, Verlaufsplan, Unterrichtsentwurf, Sequenzplanung oder didaktischer
  Jahresplanung gefragt wird – auch wenn der Nutzer nur „plane eine Stunde über X" schreibt.
  Liest lehrer-core für Design-Standards.
---

# VERLAUFSPLAN-SKILL: Unterrichtsplanung Business English NRW

> Lies zuerst `lehrer-core/SKILL.md` für Bildungsplan-Kompetenzen, AFB-Operatoren und Designvorgaben.

## PFLICHT-STRUKTUR EINES VERLAUFSPLANS

### Kopfteil (immer ausfüllen)

```
Schule:          [Berufskolleg Name]
Bildungsgang:    Handelsschule / Höhere Handelsschule
Klasse/Gruppe:   [z.B. HH11a]
Datum / Stunde:  [Datum] | [Stunde]
Lehrkraft:       [Name]
Thema der Stunde:[Titel]
Lernziel:        Die SuS können [Kompetenz] [Operator] [Kontext]
                 Beispiel: "Die SuS können eine Reklamation per E-Mail formal korrekt verfassen (AFB II)"
GER-Niveau:      [A2 / B1 / B2]
Sozialformen:    EA = Einzelarbeit | PA = Partnerarbeit | GA = Gruppenarbeit | PL = Plenum
Medien/Material: [Liste]
Kompetenzbereich:[Rezeption / Produktion / Interaktion / Mediation / Sprachbewusstsein]
```

---

## TABELLEN-VORLAGE (MARKDOWN)

```markdown
| Zeit | Phase | Inhalt & Lehrerhandlung | SuS-Aktivität | Sozialform | Medien | Differenzierung |
|------|-------|------------------------|---------------|------------|--------|-----------------|
| 0–5 | **HOOK** | | | | | |
| 5–20 | **INPUT** | | | | | |
| 20–30 | **CHECK** | | | | | |
| 30–45 | **TRANSFER** | | | | | |
| 43–45 | **Sicherung** | | | | | |
```

---

## PHASEN-LEITFADEN

### HOOK (0–5 min)
**Ziel:** Motivation, Neugier, Vorwissen aktivieren
**Möglichkeiten:**
- Reales Business-Szenario: "You've just received this email. What would you do?"
- Bild/Screenshot eines echten Fehlers (z.B. unpassende E-Mail)
- Kurze Frage an die Klasse: "Have you ever had to call a company in English?"
- Statistik / Zitat aus Wirtschaftskontext
- Kurzes Audioclip (max. 60 Sek.) mit anschließender Diskussion

**Formulierung in Tabelle:** 
> "L. projiziert [Stimulus]. SuS äußern Vermutungen. L. notiert Stichworte an Tafel/Smartboard."

### INPUT (5–20 min)
**Ziel:** Sprachliches/fachliches Wissen strukturiert einführen
**Regeln:**
- Max. 3 Chunks à 3–4 Minuten
- Nach jedem Chunk: kurze Verständnisfrage (mündlich)
- Vocabulary Box: 5–8 Fachbegriffe mit Beispielsatz
- Immer Phrase Collection für die jeweilige Kommunikationssituation

**Formulierung in Tabelle:**
> "L. präsentiert Muster-Email via Beamer. SuS identifizieren Struktur. L. führt 6 Key Phrases ein."

### CHECK (20–30 min)
**Ziel:** Verständnis sichern, Feedback geben
**Aufgabentypen nach Niveau:**

| Niveau | Aufgabentyp | Beispiel |
|--------|-------------|---------|
| A2/B1 | Multiple Choice, True/False, Matching | Match phrases to functions |
| B1 | Gap-fill, Sorting, Error correction | Complete the email with phrases |
| B1/B2 | Transformation, Summary, Analysis | Rewrite in formal register |
| B2 | AFB III: Comment, evaluate | Is this email appropriate? Why? |

**Formulierung in Tabelle:**
> "SuS bearbeiten AB Aufg. 1–3 in EA (10 min). Vergleich in PA. PL-Besprechung mit L.-Feedback."

### TRANSFER (30–43 min)
**Ziel:** Handlungsorientierte Anwendung in neuem Kontext
**Immer:** Bezug zum Modellunternehmen, rollenbasiert
**Formate:**
- Role-Play: Telefongespräch / Meeting-Simulation
- Writing Task: E-Mail / Bericht / Kurzpräsentation
- Mediation: Deutschen Text auf Englisch kommunizieren
- Präsentation: 2-Minuten-Pitch zu Lernsituations-Thema

**Formulierung in Tabelle:**
> "SuS schreiben in PA eine Antwort-Email an Kunde (Modellunternehmen-Kontext). L. gibt Hilfe-Phrase-Box."

### SICHERUNG (43–45 min)
**Ziel:** Lernziel reflektieren, Ausblick
**Optionen:**
- Exit Ticket: "Write 3 phrases you learned today"
- Blitzrunde: "One word that describes today's lesson"
- Lernziel-Check: Thumb-Up-Methode
- Hausaufgabe ankündigen

---

## DIFFERENZIERUNGSMATRIX

| SuS-Gruppe | Maßnahme | Konkret |
|------------|----------|---------|
| **Basis** (A2–B1-) | Strukturhilfen, Scaffolding | Phrase Box, Lückentexte, Satzanfänge |
| **Standard** (B1) | Selbstständig mit Modell | Musteremail als Referenz |
| **Expert** (B1+/B2) | Erweiterung, Kreativität | Eigene Variante ohne Vorlage, AFB III-Aufgabe |

---

## QUALITÄTS-CHECKLISTE (vor Ausgabe prüfen)

- [ ] Lernziel enthält Operator aus AFB-Liste
- [ ] Alle 4 Phasen (Hook, Input, Check, Transfer) vorhanden
- [ ] Zeitangaben ergeben zusammen 45 min (oder 90 min bei Doppelstunde)
- [ ] Modellunternehmen in Transfer-Phase eingebaut
- [ ] Mindestens eine Differenzierungsmaßnahme angegeben
- [ ] Kompetenzbereich dem NRW-Bildungsplan zugeordnet
- [ ] Sozialformen variieren (nicht alles EA oder PL)

---

## BEISPIEL-LERNZIELE (KOPIERVORLAGEN)

```
B1 Produktion:
"Die SuS können eine formale Beschwerde-E-Mail an einen Lieferanten 
strukturiert und im angemessenen Register verfassen." (AFB II)

B1 Interaktion:
"Die SuS können ein Telefongespräch zur Auftragsbestätigung 
initiieren und relevante Informationen austauschen." (AFB II)

B2 Mediation:
"Die SuS können einen deutschen Produktionsbericht 
sinngemäß und adressatengerecht auf Englisch kommunizieren." (AFB II/III)

B2 Reflexion:
"Die SuS können Kommunikationsstrategien für interkulturelle 
Business-Situationen bewerten und begründet empfehlen." (AFB III)
```

---
name: workshop-praesentationen-slides
description: "Wende diesen Skill an, wenn der Nutzer Präsentationen, Foliensätze, SchiLF-Materialien (Schulinterne Lehrerfortbildung) oder Workshop-Slides anfordert. Definiert didaktischen Aufbau, Marp-Markdown-Formatierung und visuelles Design."
---

# SKILL: PROFESSIONELLE WORKSHOP-PRÄSENTATIONEN & FOLIEN

Wenn der Nutzer nach einer Präsentation, Folien oder einem Workshop-Konzept fragt, generiere das Ergebnis streng nach den folgenden Vorgaben. Das Ziel sind hochprofessionelle, didaktisch durchdachte Folien für Lehrkräfte oder Schüler ("Kein KI-Schrott").

## 1. FORMATIERUNG (MARP MARKDOWN)
Generiere den Foliensatz als Code-Block im "Marp Markdown"-Format. 
- Starte das Dokument mit dem Frontmatter:
  `---`
  `marp: true`
  `theme: default`
  `paginate: true`
  `style: |`
  `  section { justify-content: start; }`
  `---`
- Trenne jede Folie mit `---`.
- Nutze `` für ausführliche Sprechernotizen (Speaker Notes) auf jeder Folie.

## 2. DESIGN-REGELN & FOLIEN-STRUKTUR ("Zen-Präsentation")
- **Keine Textwüsten:** Maximal 3-4 kurze Bulletpoints pro Folie. Der eigentliche Inhalt gehört in die Sprechernotizen.
- **Visuelle Metaphern:** Schlage auf Titel- oder Konzeptfolien konkrete visuelle Metaphern vor (z. B. `*[Hier ein Bild: Ein Kompass, der Richtung Digitalisierung zeigt]*`).
- **Typografie:** Nutze Überschriften (H1 für Titel, H2 für Slide-Titel) konsistent. Hebe Kernbegriffe **fett** hervor.

## 3. DIDAKTISCHER AUFBAU DES WORKSHOPS
Wenn ein kompletter Workshop generiert wird, muss der Foliensatz diese Phasen enthalten:
1. **Title & Hook:** Ein starker Titel und ein Eisbrecher/Provokation für das Kollegium (z.B. "Warum KI uns nicht ersetzt, aber Lehrkräfte mit KI solche ohne ersetzen werden").
2. **Agenda & Ziele:** Klare, transparente Lernziele (Was können die Kollegen nach den 90 Minuten?).
3. **Input (niedrigschwellig):** Kurze, jargonfreie Erklärungen komplexer Sachverhalte.
4. **Hands-on / SOL-Phase:** Eine Folie mit klarem Arbeitsauftrag (Operatoren!) für eine Praxisphase der Kollegen. Binde Timer-Vorgaben ein (z.B. "⏰ 15 Minuten").
5. **Transfer & Q&A:** Raum für fachspezifische Fragen ("Wie nutze ich das in Mathe/BWL?") und nächste Schritte.

## 4. ROLLE DES NUTZERS BEACHTEN
Der Nutzer ist der KI-Experte. Die Sprechernotizen richten sich an ihn und sollten wertvolle didaktische Tipps enthalten (z.B. "Achtung: Hier werden erfahrungsgemäß Bedenken zum Datenschutz kommen. Antworte darauf wie folgt...").

## 5. GENERIERUNGS-ABLAUF
1. Gib eine ganz kurze Übersicht (2-3 Sätze) über den roten Faden der Präsentation.
2. Generiere den vollständigen Marp-Markdown-Code inkl. Sprechernotizen.
# 🏀 Three-Point Inflation in the NBA  
### Where is the limit?

## 📌 Projektübersicht
In den letzten Jahrzehnten hat sich der Spielstil in der NBA grundlegend verändert.  
Insbesondere der **Drei-Punkte-Wurf** hat seit Mitte der 2010er-Jahre massiv an Bedeutung gewonnen.  
Teams nehmen immer mehr Dreier – doch bleibt dieser Trend langfristig effizient und erfolgsentscheidend?

Ziel dieses Projekts ist es, die Entwicklung des Drei-Punkte-Wurfs **historisch, statistisch und mithilfe von Machine Learning** zu analysieren und zu beantworten:

> **Wo liegt das Limit der Drei-Punkte-Inflation in der NBA?**

---

## 🎯 Forschungsfragen
- Wie hat sich das Drei-Punkte-Volumen (3PA) seit 1996 entwickelt?
- Gibt es einen Effizienzverlust bei steigender Wurfanzahl?
- Lässt sich ein struktureller Wendepunkt (ca. 2014/15–2015/16) identifizieren?
- Ist der Drei-Punkte-Wurf im Jahr 2026 noch der wichtigste Prädiktor für Teamerfolg?

---

## 📊 Datengrundlage
- **Ebene:** Team × Saison  
- **Zeitraum:** 1996–2026  
- **Variablen (Auswahl):**
  - 3PA, 3PM, 3P%
  - FG%, FT%
  - Wins / Winning Percentage
- **Quelle:** Offizielle NBA-Team-Season-Statistiken  
- Alle Kennzahlen werden **pro Spiel** betrachtet.

---

## 🧹 Datenaufbereitung
Die Daten wurden vereinheitlicht und bereinigt durch:
- Standardisierung der Saisons (z. B. `2015/16`)
- Vereinheitlichung von Teamnamen (Franchise-Wechsel)
- Umgang mit verkürzten Saisons (Lockout, COVID)
- Behandlung fehlender Werte in aktuellen Saisons
- Umrechnung auf **Per-Game-Basis**

Ergebnis ist eine **bereinigte Master-Tabelle**, geeignet für Statistik und Machine Learning.

---

## 🧠 Feature Engineering: True 3PT%
Neben der klassischen 3P% wird eine **Bayes-adjustierte Effizienzkennzahl** verwendet:

**True 3PT%**
- reduziert Verzerrungen durch geringe Wurfanzahl
- nutzt Shrinkage Richtung Ligadurchschnitt
- verhindert Überbewertung kleiner Stichproben

Diese Kennzahl stellt einen zentralen methodischen Mehrwert des Projekts dar.

---

## 📈 Methodik

### 1️⃣ Deskriptive Analyse
- Zeitreihen (1996–2026) für:
  - 3PA per Game
  - 3P%
  - True 3PT%
- Markierung des strukturellen Wendepunkts um 2015/16

### 2️⃣ Statistischer Hypothesentest
Vergleich:
- Saison **2015/16** vs. **2025/26**

Tests:
- t-Test auf klassische 3P%
- t-Test auf True 3PT%

Ziel:
- Unterscheidung zwischen Volumen-Effekt und realem Effizienzverlust

### 3️⃣ Machine Learning
- **Zielvariable:** Wins oder Winning Percentage
- **Features:**
  - 3PA per Game
  - 3P%
  - True 3PT%
  - FG%
  - FT%
- **Modelle:**
  - Lineare Regression (Baseline)
  - Nichtlineares Modell (z. B. Random Forest)
- Analyse der Feature Importance

---

## 🧩 Projektstruktur

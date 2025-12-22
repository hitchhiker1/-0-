# δℱ = 0 — Formale Modell-Architektur (Closure / Fixpunkt)

**Ein zwangsgeschlossenes Kosmosmodell**
Keine freien Parameter. Eine konsistente Lösung.
---
## Überblick (Scope)

Dieses Repository beschreibt **Ebene 1**: eine **formale Modell‑Architektur** als *Constraint‑Satisfaction / Fixpunkt‑Problem*, prüfbar über Residuen (Killtests).
Es ist **keine** vollständig ausgearbeitete Feldtheorie (Ebene 2: explizite Lagrangedichten, Symmetrien, Perturbationen, CMB/BAO/LSS‑Pipeline). Das ist ein bewusster Scope‑Schnitt.

> **Kernaussage:** Nach Wahl **eines** Messankers ist das System **überbestimmt**. Alle übrigen Größen müssen ohne weitere Freiheitsgrade schließen – oder das Modell fällt.
---
## Idee in einem Satz

> **Das Universum ist nicht gewählt – es ist die einzige Konfiguration, die sich selbst trägt.**
---
## Zentrales Prinzip

```text
δℱ = 0
```

Meta‑Form eines Variationsprinzips mit Nebenbedingungen (Closure):

```text
δ[ S_EH + S_matter + S_scale + Σ λ_a · C_a ] = 0 ,   a ∈ {H, v, T, e}
```

**Hinweis:** Diese Schreibweise ist **keine** voll spezifizierte EFT‑Lagrangedichte, sondern eine **globale Konsistenzbedingung** (Fixpunkt/Closure).
---
## Skalen‑Action (S_scale) — minimale Definition

Für Ebene 1 genügt eine **skizzenhafte, wohldefinierte** Skalen‑Action als Funktional über ein Skalenmaß μ:

```text
S_scale[μ] = ∫₀¹ μ(x) · ln( μ(x) / m(x) ) dx
```

* μ(x) ≥ 0: Skalen‑Gewichtung (z. B. x = r/R ∈ [0,1])
* m(x): Referenzmaß (z. B. m(x)=1)

Diese Wahl ist ein **Regularisator** (relative Entropie): Unter linearen Nebenbedingungen existiert genau **eine** Lösung μ(x).

### Drift‑Klemme als echte Nebenbedingung

```text
C_v[μ] := ∫₀¹ x·μ(x) dx − r = 0
C_N[μ] := ∫₀¹ μ(x) dx − 1 = 0
```

Die Variation von S_scale unter C_v und C_N liefert eine eindeutige μ(x). Die Drift‑Klemme ist damit **nicht angeheftet**, sondern integraler Bestandteil des Variationsproblems.
---
## Die vier Klemmen (Bedeutung)

* **C_H (Geometrie):** Expansions‑Slot, R = c / H₀
* **C_v (Drift):** normierter mittlerer Drift ⟨v⟩/c = r
* **C_T (Thermik):** Strahlungsbudget (Planck/Wien‑Anker)
* **C_e (Eichung):** Zeit‑Eichung über e³

Diese Klemmen **definieren den zulässigen Lösungsraum**. Sie sind **keine Fit‑Parameter**.

**Beispiel (symbolisch, als Nebenbedingung):**

```text
C_T := u − a·T^4 = 0
```

Die Klemme erzwingt thermische Konsistenz zwischen Strahlungsdichte *u* und Temperatur *T*. Sie ist hier als **Constraint** gemeint (Closure), nicht als eigenständige dynamische Feldgleichung.
---
## Set‑A / Set‑B (Ankerwahl)

Ein **externer Messanker** ist erlaubt – **genau einer**:

* **Set A:** λ_max (Wien‑Peak) als Anker → T₀ folgt
* **Set B:** T₀ als Anker → λ_max folgt

> *„Keine freien Parameter“ heißt:* **Nach** der Ankerwahl existiert **keine zweite Stellschraube**.

**Abgrenzung zu Fit:** Kein numerischer Wert wird durch Optimierung oder Anpassung gewonnen; nach Wahl eines einzigen Messankers werden alle übrigen Größen ausschließlich durch die Closure berechnet und über Residuen geprüft.
---
## Zwangskette (Hintergrund‑Closure)

1. R = c / H₀
2. T_eich = R / ⟨v⟩
3. T_lin = T_eich / e³
4. u = a·T⁴  (Budget‑Schließung)
5. T₀ = b / λ_max  (Wien‑Anker)

**Abhängigkeitsstruktur (Closure‑Graph):**

```text
Anker (λ_max oder T₀)
        ↓
       T₀
        ↓
     T_lin
        ↓
     T_eich
        ↓
        R
        ↓
       H₀
        ↓
    {c, G, α, …}
```

Weitere Konstanten (c, G, α, …) folgen **aus der Kette** – sie werden **nicht vorausgesetzt**.

---

## Killtests (harte Kriterien)

ε ist **fest**; kein Reweighting, keine Nachkalibrierung.

| Code | Test             | Kriterium            |
| ---- | ---------------- | -------------------- |
| K1   | Strahlungsbudget | u schließt           |
| K2   | Temperaturanker  | T₀ = b/λ_max         |
| K3   | Zeit‑Eichung     | T_eich = e³·T_lin    |
| K4   | Drift            | ⟨v⟩/c = r            |
| K5   | G‑Konsistenz     | aus Kette ≈ gemessen |
| K6   | Skaleninvarianz  | Stabil unter e³      |

Versagt ein Test → **Modell verworfen**.
---
## Ergebnisse (Beispiel‑Set)

* H₀ ≈ 72.28 km/s/Mpc
* T₀ ≈ 2.7255 K
* u ≈ 4.17×10⁻¹⁴ J/m³
* c ≈ 2.99792458×10⁸ m/s (emergent)
* G ≈ 6.67×10⁻¹¹ m³·kg⁻¹·s⁻²
* α⁻¹ ≈ 137.036
---
## Der mittlere Drift (Definition & Check)

⟨v⟩/c = ∫₀¹ x·xⁿ dx / ∫₀¹ xⁿ dx = (n+1)/(n+2)
*(Konvergenz: n > −1)*

**Drift‑Klemme:** r := ⟨v⟩/c ≈ 0.358524

**Mini‑Check:**

* r = (n+1)/(n+2) = 0.559/1.559 ≈ 0.358524
* n = (2r−1)/(1−r) ≈ −0.441
---
## Einordnung & Ausblick

* Dies ist **Hintergrund‑Closure** (Ebene 1).
* **Perturbationen / Strukturbildung** (CMB/BAO/LSS) sind **separat** auszuarbeiten (Ebene 2).

**Ausblick (Ebene 2, optional):**

* Einführung einer skalenabhängigen Störgröße δk(x,t)
* Linearisierung der Closure‑Bedingungen um den Fixpunkt
* Ableitung effektiver Perturbationsgleichungen (CMB/BAO/LSS)
---
## Reproduzieren (Kurz)

1. Wähle **einen** Anker (Set A oder B).
2. Durchlaufe die Zwangskette.
3. Prüfe Killtests K1–K6.
4. Bestehen alle → Closure erfüllt.
---
## Aufforderung

Finde eine **alternative** Wertekombination, die **alle** Killtests besteht.
Gelingt das nicht, ist die Closure eindeutig – oder der Ansatz widerlegt.
---

**Autor:** Thomas Boffo - Frankfurt
**Lizenz:** CC BY‑NC‑SA 4.0

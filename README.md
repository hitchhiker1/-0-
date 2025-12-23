# δℱ = 0 — Formale Modell-Architektur (Closure / Fixpunkt, Ebene 1)

**Zwangsgeschlossenes Kosmosmodell.**
**Genau ein Messanker. Keine weiteren Stellschrauben.**
**Closure oder Verwerfung.**

---

## Status & Scope

Dieses Repository spezifiziert **Ebene 1**: ein **überbestimmtes Constraint‑Satisfaction / Fixpunkt‑Problem**, überprüfbar ausschließlich über **Residuen (Killtests)**.

**Nicht enthalten (bewusster Scope‑Schnitt):** Ebene 2 (explizite Lagrangedichten, Symmetrien, Störungen, CMB/BAO/LSS‑Pipeline).

> **Kernaussage:** Nach Wahl **genau eines** externen Messankers muss das System **ohne weitere Freiheitsgrade** schließen. Scheitert ein Residuum → **Modell verworfen**.

### Epistemische Schranke (Scope‑Grenze)

Dieses Dokument ist eine **axiomatische Closure‑Spezifikation**. Es beantwortet **nicht** die Frage, *warum* das Universum so ist, sondern prüft, *ob* eine festgelegte Closure **konsistent** ist.

* **Primitive** (z.B. **e³** als Eich‑Fixpunkt, **r** als Drift‑Marker) werden **gesetzt**.
* Für Primitive werden **keine Herleitungen** innerhalb von Ebene 1 gegeben oder akzeptiert.
* Zulässig ist ausschließlich die Prüfung auf **Konsistenz** über die definierten Residuen.

Fragen der Form *„Warum genau dieser Wert?“*, *„aus welcher Dynamik folgt das?“* oder *„welche tiefere Theorie erklärt das?“* sind **außerhalb des Scopes** (Ebene 2+) und **keine Einwände** gegen Ebene 1.

---

## Zentrales Prinzip (Closure)

```text
δℱ = 0
```

Meta‑Form einer globalen Konsistenzbedingung:

```text
δ[ S_EH + S_matt + S_scale + Σ λ_a · C_a ] = 0 ,   a ∈ {H, v, T, e}
```

**Wichtig:** Das ist **keine** voll spezifizierte EFT‑Lagrangedichte, sondern eine **Fixpunkt‑Spezifikation**: Existenz, Eindeutigkeit, Residuen‑Prüfung.

---

## Primitives, Einheiten, Verbotenes (damit nichts „hineinrutscht“)

**Primitive (werden deklariert, nicht gefittet):**

* **e³**: dimensionsloser **Eich‑Fixpunkt**.
* **r**: dimensionsloser **Drift‑Marker** (kanonisch **r = 0.358524…**).
* **Genau ein Messanker:** entweder **T₀** *oder* **λ_max**.

**Einheiten (streng):**

* **T₀** [K] Temperatur.
* **u** [J/m³] Strahlungsenergiedichte.
* **τ_lin, τ_eich** [s] Zeiten.
* **⟨v⟩** [m/s] mittlerer Drift.

**Nicht verhandelbar:**

* **kein** Reweighting, **keine** Nachkalibrierung, **kein** „zweiter Anker“.
* **keine** verdeckten Zusatzparameter (auch nicht als „nur numerische Konstante“).
* jede Abweichung hiervon definiert **ein anderes Modell**.

---

## Skalen‑Action S_scale (Minimalform, eindeutig lösbar)

Skalenmaß **μ(x) ≥ 0** auf **x ∈ [0,1]**:

```text
S_scale[μ] = ∫₀¹ μ(x) · ln( μ(x) / m(x) ) dx ,   m(x)=1
```

Regularisator (relative Entropie). Unter linearen Constraints ist die Lösung **eindeutig** (strikt konvex + linear).

### Constraints für μ (Norm + Driftmoment)

```text
C_N[μ] :  ∫₀¹ μ(x) dx − 1 = 0
C_M[μ] :  ∫₀¹ x·μ(x) dx − r = 0
```

Variationslösung (explizit):

```text
μ*(x) = exp(λ₀ + λ₁ x)
```

mit (λ₀, λ₁) eindeutig durch C_N und C_M bestimmt.

**Interpretationsregel (hart):** μ ist **Repräsentation** eines Moments, nicht „Physik‑Profil“. Jede monotone 1‑Parameter‑Familie, die dasselbe Moment reproduziert, ist auf Ebene 1 äquivalent.

---

## Logische Reihenfolge der Closure (Architektur, nicht Dynamik)

1. **Eichung zuerst:**

   ```text
   C_e :  τ_eich − e³·τ_lin = 0
   ```

   τ_lin ist die **primitive, skalenfreie Verweilzeit**. τ_eich ist die **geeichte kosmische Zeit**.

2. **Drift ist ein Closure‑Moment (kein dynamischer Output):**

   ```text
   ⟨v⟩ := R / τ_eich
   r := ⟨v⟩ / c
   ```

   **Bemerkung (entscheidend):** ⟨v⟩ ist hier **kein** aus Bewegungsgleichungen abgeleiteter Mittelwert, sondern der eindeutige geometrisch‑zeitliche Moment, der **R** und **τ_eich** kompatibel macht.

3. **Gewichtung ist nur Darstellung:** μ(x) kodiert r als Moment (C_M). Die Wahl einer konkreten Darstellungsfamilie ist auf Ebene 1 **irrelevant**, solange das Moment erfüllt ist.

---

## Die vier Klemmen (keine Fits)

### C_e — Eichung (Fixpunkt)

```text
C_e :  τ_eich − e³·τ_lin = 0
```

Eichbedingung. Fixiert Zeit **vor** Drift und Thermik.

### C_H — Geometrie (Slot)

```text
C_H :  R − c/H₀ = 0
```

### C_v — Drift (Moment)

```text
C_v :  ⟨v⟩/c − r = 0
```

Definition des Moments (kanonisch):

* x := v/c ∈ [0,1]
* r = ∫₀¹ x·μ(x) dx / ∫₀¹ μ(x) dx  (mit ∫ μ = 1)

### C_T — Thermik / Budget (Einheitenbrücke)

Thermischer Anker (Planck/Wien):

```text
C_T1 :  u − a·T₀⁴ = 0
```

Budget‑Closure (stationärer Durchsatz):

```text
C_T2 :  u − (\dot{ρ}·τ_lin)/4 = 0
\dot{ρ} ≡ 4u/τ_lin
```

**Interpretationsregel (hart):** \dot{ρ} ist **definiert** als stationärer Durchsatz, der u über τ_lin trägt. **Kein** Friedmann‑Term, **keine** Dynamikbehauptung auf Ebene 1.

---

## Ankerwahl (genau einer)

Erlaubt ist **genau ein** externer Messanker:

* **Set A:** λ_max → T₀ folgt
* **Set B:** T₀ → λ_max folgt

Wien‑Relation (Definition):

```text
T₀ · λ_max = b
```

b ist das feste Wien‑Produkt (aus dem Planck‑Spektrum), **nicht** optimiert.

---

## Zwangskette (dimensionssauber, ohne „Temperatur‑Zeit‑Verwechslung“)

1. Eichung:

```text
τ_eich = e³ · τ_lin
```

2. Thermik:

```text
u = a·T₀⁴
```

3. Budget:

```text
\dot{ρ} = 4u / τ_lin
```

4. Driftmoment:

```text
⟨v⟩ = R / τ_eich
r = ⟨v⟩ / c
```

5. Geometrie‑Slot:

```text
R = c / H₀
```

**Hinweis zur Fixpunkt‑Struktur (kein „Zirkel“):** Die Gleichungen bilden einen **gleichzeitigen Closure‑Graphen** (Fixpunkt), keinen sequentiellen Rechenpfad. Ein „Zirkel“ entsteht nur, wenn man Ebene 1 fälschlich als Algorithmus liest. Numerische Werte sind nur dann zulässig, wenn **alle** Klemmen und Residuen **gleichzeitig** geschlossen werden (z.B. per reproduzierbarem Code).

Abgeleitete Fixpunkt-Identität (informativ, keine zusätzliche Klemme):
e³ · r · H₀ · τ_lin = 1
---

## Killtests (Residuen fest; ε global; kein Trade‑off)

ε ist **einmal** festgelegt. Keine Nachkalibrierung. Keine Gewichtungs‑Tricks.

Definiere Residuen:

```text
ε_budg = | u / (\dot{ρ}·τ_lin/4) − 1 |
ε_peak = | (T₀·λ_max)/b − 1 |
ε_e    = | τ_eich/(e³·τ_lin) − 1 |
ε_v    = | ⟨v⟩/c − r |
```

Grenzen (kanonisch):

```text
ε_budg ≤ 1e−3
ε_peak ≤ 1e−6
ε_e    ≤ 1e−12
ε_v    ≤ 1e−6
```

**Regel:** Ein einziges Residuum über Grenzwert → **Modell verworfen**.

Optional (nur wenn im Repo explizit belegt):

* K5: G‑Konsistenz (Brückenformel vorhanden)
* K6: e³‑Stabilität (Residuen invariant unter τ‑Reskalierung + definierter \dot{ρ}‑Transformation)

---

## Ergebnisse (Beispiel‑Set; nur als Referenz, nicht als Fit)

```text
H₀ ≈ 72.28 km/s/Mpc
T₀ ≈ 2.7255 K
u  ≈ 4.17×10⁻¹⁴ J/m³
c  ≈ 2.99792458×10⁸ m/s (Kandidat; nur gültig, wenn Brücke geschlossen)
G  ≈ 6.67×10⁻¹¹ m³·kg⁻¹·s⁻² (optional; nur mit Brücke)
α⁻¹ ≈ 137.036 (optional; nur mit Brücke)
```

Walkthrough / Code: siehe Notebook/Script (muss die Residuen reproduzierbar ausweisen).

---

## Übergang zu Ebene 2 (klar abgegrenzt)

**Ebene 1 ist hiermit logisch abgeschlossen („locked“).**

Alles Folgende gehört **nicht** mehr zur Closure‑Definition, sondern zu **Ebene 2**. Ebene 2 darf **keine** neuen Freiheitsgrade in Ebene 1 einführen.

**In Ebene 2 dürfen sich nur ändern:**

* Zustandsgrößen wie (T, u, H) **entlang eines Skalen‑ oder Zeitpfads**,
* Darstellungen der Drift (z.B. Profile, Flüsse, Perturbationen), **solange** die Ebene‑1‑Residuen invariant bleiben.

**In Ebene 2 dürfen sich niemals ändern:**

* die Primitive **e³** und **r**,
* die Struktur der Klemmen (C_e, C_H, C_v, C_T),
* die Grenzwerte (ε).

**Zulässige Ebene‑2‑Fragen** betreffen ausschließlich:

* wie sich ein Zustand **auf** dem Fixpunkt‑Graphen bewegt,
* wie Perturbationen um den Fixpunkt aussehen,
* ob reale Beobachtungen (CMB/BAO/LSS) **in der Nähe** des Fixpunkts liegen.

**Unzulässig** sind alle Versuche, Ebene‑2‑Effekte zur Rechtfertigung oder Modifikation von Ebene 1 zu verwenden.

---

## Reproduzieren

1. Wähle **genau einen** Anker (Set A oder Set B).
2. Setze **e³** und **r** (kanonisch r = 0.358524…).
3. Durchlaufe die Zwangskette.
4. Prüfe **alle** Residuen gegen ε.

---

## Challenge (Falsifikation / Eindeutigkeit)

Finde eine **alternative** Wertekombination bei fixem **e³** und fixem **r**, die **alle** Residuen unter denselben ε‑Grenzen hält.
Gelingt das nicht, ist die Closure entweder **eindeutig** – oder durch Daten **widerlegt**.

---

**Autor:** Thomas Boffo – Frankfurt
**Lizenz:** CC BY‑NC‑SA 4.0

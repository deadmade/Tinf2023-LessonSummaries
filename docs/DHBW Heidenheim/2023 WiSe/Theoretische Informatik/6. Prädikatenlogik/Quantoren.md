Oft möchte man für bestimmte [Aussagen](Aussagen.md#Aussage) eine Entscheidung treffen, ob sie allgemeingültig oder [erfüllbar](Erfüllbarkeit.md#Erfüllbarkeit) sind. Um dies zu ermöglich, werden in der Prädikatenlogik sogenannte **Quantoren** eingeführt.

# Quantoren
#Definition 
Ein Quantor ist ein Operator der Prädikatenlogik.
- **Allquantor**: $\forall$ (*"für alle"*)
- **Existenzquantor**: $\exists$ (*"es existiert"*)

>[!example]- Beispiel
>- $\forall X(X \in G; p(X))$
>(*"Für alle Elemente $X$ der Menge $G$ gilt $p(X)$"*)
>- $\exists X(X \in G; p(X))$
>(*"Es existiert ein Element $X$ der Menge $G$ sodass $p(X)$ gilt"*)
>---
>**Kurzform**: Ist die Grundmenge klar, so kann man auch kurz $\forall X p(X)$ und $\exists X p(X)$ schreiben.

>[!caution] Kommutativität
>Gleiche Quantoren sind kommutativ.
>Unterschiedliche Quantoren sind nicht kommutativ!
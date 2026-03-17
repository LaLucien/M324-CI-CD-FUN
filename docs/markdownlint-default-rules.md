# Standardregeln Von Markdownlint

Diese Datei erklaert einige Beispiele, was `markdownlint-cli2-action` automatisch prueft, wenn keine eigene Regelkonfiguration angegeben wird.

### Typische Beispiele

### Ueberschriften

Markdownlint prueft die Struktur und die Abstaende von Ueberschriften.

Schlecht:

```md
#### Uebersprungene Ebene
```

Gut:

```md
## Korrekte Ebene

### Naechste Ebene
```

Erklaerung:

Nach einer Ueberschrift der Ebene 2 sollte normalerweise zuerst Ebene 3 folgen. Ein Sprung direkt zu Ebene 4 ueberspringt eine Strukturstufe und wirkt deshalb inkonsistent.

### Listen

Markdownlint prueft, ob Listen von Leerzeilen umgeben sind und konsistent formatiert werden.

Schlecht:

```md
-
  erster Punkt
- zweiter Punkt
```

Gut:

```md
- erster Punkt
- zweiter Punkt
```

Erklaerung:

Listen sollen klar vom umgebenden Text getrennt sein und innerhalb der Liste gleich formatiert werden. Das verbessert Lesbarkeit und Konsistenz.

### Leerraum

Markdownlint prueft auch haeufige Whitespace-Probleme.

Schlecht:

```text
Diese Zeile hat am Ende Leerzeichen. [space][space]
```

Gut:

```md
Diese Zeile hat keine Leerzeichen am Ende.
```

Erklaerung:

Leerzeichen am Zeilenende sieht man haeufig nicht direkt. Sie zaehlen aber als unnoetiger Whitespace und fuehren oft zu unnoetigen Diff-Aenderungen.

### Tabs statt Leerzeichen

Markdownlint meldet auch Tabs, wenn fuer Einrueckungen Leerzeichen erwartet werden.

Schlecht:

```text
[tab]- eingerueckter Punkt
```

Gut:

```text
  - eingerueckter Punkt
```

Erklaerung:

Tabs koennen je nach Editor unterschiedlich breit dargestellt werden. Leerzeichen sorgen fuer einheitlichere Darstellung und konsistente Einrueckung.

### Doppelte Top-Level-Ueberschriften

Ein Dokument sollte normalerweise nur eine Hauptueberschrift der Ebene `#` haben.

Schlecht:

```md
# Projekt

Text

# Projekt
```

Gut:

```md
# Projekt

## Installation
```

Erklaerung:

Die Hauptueberschrift beschreibt den gesamten Inhalt des Dokuments. Wenn sie mehrfach vorkommt, wirkt die Struktur schnell unklar oder redundant.

### Uneinheitliche Listenformatierung

Markdownlint achtet darauf, dass ungeordnete Listen konsistent aufgebaut sind.

Schlecht:

```md
- erster Punkt
* zweiter Punkt
+ dritter Punkt
```

Gut:

```md
- erster Punkt
- zweiter Punkt
- dritter Punkt
```

Erklaerung:

Technisch funktionieren verschiedene Listenmarker oft trotzdem. Stilistisch ist es aber sauberer, innerhalb derselben Liste nur einen Marker zu verwenden.

### Link-Syntax

Markdownlint prueft auch, ob Links sauber und einheitlich geschrieben sind.

Schlecht:

```md
[GitHub](https://github.com
```

Gut:

```md
[GitHub](https://github.com)
```

Erklaerung:

Ein Link mit fehlender schliessender Klammer oder uneinheitlicher Syntax ist fehleranfaellig und kann im gerenderten Markdown falsch angezeigt werden.

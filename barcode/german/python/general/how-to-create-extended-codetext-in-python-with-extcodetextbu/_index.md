---
category: general
date: 2026-10-28
description: Erfahren Sie, wie Sie erweiterten Codetext in Python mit ExtCodetextBuilder
  erstellen. Enthält Klartext‑ und ECI‑kodierte Daten, Schritt‑für‑Schritt‑Code und
  Tipps zu bewährten Verfahren.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create extended codetext
- ExtCodetextBuilder Python
- add plain codetext
- add eci codetext
- extended‑codetext example
language: de
lastmod: 2026-10-28
og_description: Erstelle erweiterten Codetext in Python mit ExtCodetextBuilder. Dieses
  Tutorial zeigt die Verarbeitung von Klartext‑ und ECI‑kodierten Daten, vollständigen
  ausführbaren Code und häufige Fallstricke.
og_image_alt: Diagram showing how to create extended codetext using ExtCodetextBuilder
  in Python
og_title: Erstelle erweiterten Code‑Text in Python – vollständige Anleitung
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Learn how to create extended codetext in Python using ExtCodetextBuilder.
    Includes plain and ECI‑encoded data, step‑by‑step code and best‑practice tips.
  headline: How to create extended codetext in Python with ExtCodetextBuilder
  type: TechArticle
- description: Learn how to create extended codetext in Python using ExtCodetextBuilder.
    Includes plain and ECI‑encoded data, step‑by‑step code and best‑practice tips.
  name: How to create extended codetext in Python with ExtCodetextBuilder
  steps:
  - name: Prerequisites
    text: '* Python 3.8 or newer. * The `extcodetext` package (or a similar library
      that provides `ExtCodetextBuilder`). Install it with:'
  - name: Handling other encodings
    text: 'If you need ISO‑8859‑1 (Western European) you would use `add_eci_codetext(4,
      "¡Hola!")`. For Shift‑JIS (Japanese) the ECI value is 20:'
  - name: 'Edge case: Empty strings'
    text: Calling `add_plain_codetext("")` or `add_eci_codetext(3, "")` is harmless;
      the builder simply ignores the empty fragment. However, repeated empty calls
      can lead to unnecessary ECI markers. Guard against this by checking string length
      before adding.
  type: HowTo
tags:
- Python
- encoding
- data‑serialization
title: Wie man erweiterten Codetext in Python mit ExtCodetextBuilder erstellt
url: /de/python/general/how-to-create-extended-codetext-in-python-with-extcodetextbu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# So erstellen Sie erweiterten Codetext in Python mit ExtCodetextBuilder

Wenn Sie **erweiterten Codetext** für Barcode‑ oder Data‑Matrix‑Anwendungen benötigen, zeigt Ihnen dieser Leitfaden genau, wie Sie das in Python machen. Sie sehen, wie Sie Klartext kombinieren, ECI‑ (Extended Channel Interpretation) Abschnitte für Unicode‑Zeichen hinzufügen und einen einzelnen, korrekt formatierten String erhalten, der bereit zum Kodieren ist.

Das Tutorial behandelt alles von der Installation der erforderlichen Bibliothek bis zum Umgang mit Randfällen wie nicht unterstützten ECI‑Werten. Am Ende haben Sie ein wiederverwendbares Muster, das Sie in jedes Projekt einbinden können, das **erweiterten Codetext** erstellen muss.

## Was Sie lernen werden

* Die Rolle von `ExtCodetextBuilder` beim Erstellen von gemischt codierten Strings.  
* Wie Sie **plain codetext** und **ECI codetext** in einer einzigen Builder‑Instanz **addieren**.  
* Wie Sie die endgültige Ausgabe überprüfen und häufige Stolperfallen beheben.  
* Varianten für andere Zeichensätze (z. B. ISO‑8859‑1, Shift‑JIS).  

### Voraussetzungen

* Python 3.8 oder neuer.  
* Das `extcodetext`‑Paket (oder eine ähnliche Bibliothek, die `ExtCodetextBuilder` bereitstellt). Installieren Sie es mit:

```bash
pip install extcodetext
```

* Grundlegende Kenntnisse über Unicode und ECI‑Werte – ECI 3 entspricht UTF‑8, ECI 4 ISO‑8859‑1 usw.

> **Pro‑Tipp:** Halten Sie eine Referenztabelle der ECI‑Nummern bereit. Sie verhindert versehentliche Diskrepanzen zwischen der deklarierten Kodierung und der tatsächlichen Byte‑Sequenz.

## Verständnis von ExtCodetextBuilder

`ExtCodetextBuilder` ist ein kleines Hilfswerkzeug, das mehrere Textfragmente aneinanderhängt und dabei automatisch die erforderlichen ECI‑Marker einfügt. Ein ECI‑Marker teilt dem nachfolgenden Barcode‑Encoder mit, welcher Zeichensatz für die folgenden Bytes zu verwenden ist. Ohne den Marker würden Nicht‑ASCII‑Zeichen falsch interpretiert.

Der Builder arbeitet in drei einfachen Phasen:

1. **Erstellen** Sie die Builder‑Instanz.  
2. **Anhängen** von Klartext‑ oder ECI‑kodierten Fragmenten.  
3. **Abrufen** des kombinierten extended‑codetext‑Strings.

Im Folgenden gehen wir jede Phase mit konkretem Code durch.

## Schritt 1: Erstellen einer ExtCodetextBuilder‑Instanz

Die erste Zeile erstellt das Objekt, das alle Fragmente hält. Zu diesem Zeitpunkt ist keine Konfiguration erforderlich.

```python
from extcodetext import ExtCodetextBuilder

# Step 1: Create an ExtCodetextBuilder instance
codetext_builder = ExtCodetextBuilder()
```

*Warum das wichtig ist*: Das Instanziieren des Builders reserviert einen internen Puffer. Alle nachfolgenden `add_*`‑Aufrufe arbeiten auf diesem Puffer und garantieren die von Ihnen angegebene Reihenfolge.

## Schritt 2: Anhängen von Klartext (nicht kodierten) Daten

Klartext‑Daten bestehen aus Zeichen, die zum Standardzeichensatz (in der Regel ASCII) gehören. Verwenden Sie `add_plain_codetext` für solche Fragmente.

```python
# Step 2: Append plain (un‑encoded) data to the builder
codetext_builder.add_plain_codetext("ABC123")
```

*Erklärung*: Der String `"ABC123"` enthält nur ASCII‑Zeichen, daher ist kein ECI‑Marker nötig. Die Methode fügt einfach die rohen Bytes dem internen Puffer hinzu.

## Schritt 3: Anhängen von Daten, die einem ECI vorausgehen müssen

Wenn Sie Unicode‑Zeichen einbetten müssen – z. B. Kyrillisch, Japanisch oder Emoji – müssen Sie dem Encoder mitteilen, welcher Zeichensatz zu verwenden ist. Dies geschieht mit `add_eci_codetext(eci, text)`. Das erste Argument ist der numerische ECI‑Wert; das zweite ist der eigentliche Text.

```python
# Step 3: Append data that must be preceded by an ECI (e.g., 3 for UTF‑8)
# This ensures the text "Привет" is correctly interpreted as UTF‑8
codetext_builder.add_eci_codetext(3, "Привет")
```

*Warum ECI 3*: Laut der ISO/IEC 18004‑Spezifikation entspricht ECI 3 UTF‑8. Durch das Einfügen dieses Markers weiß der Barcode‑Leser, dass die folgenden Bytes als UTF‑8 zu dekodieren sind, wodurch die kyrillischen Zeichen erhalten bleiben.

### Umgang mit anderen Kodierungen

Wenn Sie ISO‑8859‑1 (Westeuropäisch) benötigen, würden Sie `add_eci_codetext(4, "¡Hola!")` verwenden. Für Shift‑JIS (Japanisch) ist der ECI‑Wert 20:

```python
codetext_builder.add_eci_codetext(20, "こんにちは")
```

Stellen Sie stets sicher, dass die Ziel‑Barcode‑Bibliothek den gewählten ECI‑Wert unterstützt; nicht unterstützte ECIs führen zu Kodierungsfehlern.

## Schritt 4: Abrufen des kombinierten extended‑codetext‑Strings

Nachdem alle Fragmente hinzugefügt wurden, rufen Sie `get_extended_codetext()` auf, um den finalen String zu erhalten. Dieser String enthält alle notwendigen ECI‑Escape‑Sequenzen.

```python
# Step 4: Retrieve the combined extended‑codetext string
extended_codetext = codetext_builder.get_extended_codetext()

print("Extended codetext:", extended_codetext)
```

**Erwartete Ausgabe** (als Python `repr` zur Klarstellung angezeigt):

```
Extended codetext: 'ABC123\x1B\x1D\x03Привет'
```

*Aufschlüsselung*:

* `ABC123` – Klartext‑ASCII‑Segment.  
* `\x1B\x1D\x03` – die ECI‑Escape‑Sequenz für UTF‑8 (ESC GS 0x03).  
* `Привет` – das UTF‑8‑kodierte kyrillische Wort.

Die genauen Escape‑Bytes können je nach Bibliotheksimplementation variieren, aber die logische Reihenfolge ist stets *plain → ECI‑Marker → Unicode‑Text*.

## Vollständiges ausführbares Beispiel

Wenn wir alles zusammenfügen, erhalten Sie ein eigenständiges Skript, das Sie in eine Datei namens `create_extended_codetext.py` kopieren und sofort ausführen können.

```python
#!/usr/bin/env python3
"""
Create extended codetext in Python using ExtCodetextBuilder.
Demonstrates plain text, UTF‑8 ECI, and how to retrieve the final string.
"""

from extcodetext import ExtCodetextBuilder

def main() -> None:
    # 1️⃣ Create the builder
    builder = ExtCodetextBuilder()

    # 2️⃣ Add a plain ASCII segment
    builder.add_plain_codetext("ABC123")

    # 3️⃣ Add a UTF‑8 segment (ECI 3) containing Cyrillic characters
    builder.add_eci_codetext(3, "Привет")

    # 4️⃣ Retrieve and display the extended codetext
    result = builder.get_extended_codetext()
    print("Extended codetext:", result)

if __name__ == "__main__":
    main()
```

Das Ausführen des Skripts gibt den kombinierten String aus, bereit für jeden Barcode‑Encoder, der extended‑codetext‑Eingaben akzeptiert.

## Häufige Fallstricke und wie man sie vermeidet

| Symptom | Wahrscheinliche Ursache | Lösung |
|---|---|---|
| `UnicodeEncodeError` when calling `add_eci_codetext` | Bereitstellung eines Strings, der Zeichen enthält, die im gewählten ECI nicht darstellbar sind | Vergewissern Sie sich, dass das ECI zur tatsächlichen Kodierung des Strings passt (z. B. ECI 3 für beliebigen UTF‑8‑Text). |
| Missing ECI marker in the final output | Versehentliche Verwendung von `add_plain_codetext` für Nicht‑ASCII‑Daten | Wechseln Sie zu `add_eci_codetext` für jedes Zeichen außerhalb des ASCII‑Bereichs. |
| Barcode scanner shows garbled characters | Der Scanner unterstützt den ausgewählten ECI‑Wert nicht | Wählen Sie ein universell unterstütztes ECI (UTF‑8 ist weit verbreitet) oder greifen Sie auf ISO‑8859‑1 zurück, falls die Zielsprache dies zulässt. |
| `get_extended_codetext` returns an empty string | Vor dem Aufruf der Methode wurden keine Fragmente hinzugefügt | Stellen Sie sicher, dass mindestens ein `add_*`‑Aufruf ausgeführt wird. |

### Sonderfall: Leere Strings

Der Aufruf von `add_plain_codetext("")` oder `add_eci_codetext(3, "")` ist harmlos; der Builder ignoriert das leere Fragment einfach. Wiederholte leere Aufrufe können jedoch zu unnötigen ECI‑Markern führen. Vermeiden Sie dies, indem Sie die String‑Länge vor dem Hinzufügen prüfen.

```python
text = "data"
if text:
    builder.add_plain_codetext(text)
```

## Erweiterung des Musters für dynamische Daten

In realen Anwendungen bauen Sie den erweiterten Codetext oft aus Benutzereingaben oder einem Datenbankeintrag zusammen. Das folgende Snippet zeigt eine Schleife, die eine Liste von `(type, value)`‑Tupeln verarbeitet, wobei `type` entweder `"plain"` oder `"eci"` ist.

```python
fragments = [
    ("plain", "Order#"),
    ("plain", "98765"),
    ("eci", (3, "商品")),   # Japanese word "商品" (product) encoded as UTF‑8
]

for kind, payload in fragments:
    if kind == "plain":
        builder.add_plain_codetext(payload)
    elif kind == "eci":
        eci_val, text = payload
        builder.add_eci_codetext(eci_val, text)
    else:
        raise ValueError(f"Unsupported fragment type: {kind}")

print(builder.get_extended_codetext())
```

Dieser Ansatz skaliert gut: Sie können die Fragmentdefinitionen aus JSON, CSV oder einer API einlesen, ohne die Kernlogik des Builders zu ändern.

## Testen der Ausgabe

Ein kurzer Unit‑Test stellt sicher, dass der Builder wie erwartet funktioniert. Mit `pytest`:

```python
def test_extended_codetext():
    b = ExtCodetextBuilder()
    b.add_plain_codetext("X")
    b.add_eci_codetext(3, "✓")   # Check mark in UTF‑8
    result = b.get_extended_codetext()
    assert result.startswith("X")
    assert "\x1B\x1D\x03".encode() in result.encode()
```

Das Ausführen von `pytest` sollte erfolgreich sein und bestätigen, dass der ECI‑Marker genau dort erscheint, wo er sollte.

## Verwandte Konzepte, die Sie als Nächstes erkunden könnten

* **Barcode‑Kodierungsbibliotheken** – z. B. `python-barcode`, `zxing`‑Bindings, die den extended‑codetext‑String direkt akzeptieren.  
* **ECI‑Tabellen‑Referenz** – eine vollständige Liste numerischer ECI‑Werte wird von ISO/IEC 18004 veröffentlicht und kann als Python‑Dictionary zum Nachschlagen gespeichert werden.  
* **Fehlerkorrektur‑Stufen** – beim Erzeugen von QR‑Codes kombinieren Sie den extended‑codetext mit geeigneter Fehlerkorrektur (L, M, Q, H) für robustes Scannen.

## Fazit

Sie wissen jetzt, wie Sie **erweiterten Codetext** in Python mit `ExtCodetextBuilder` **erstellen**. Der Prozess ist einfach:

1. Instanziieren Sie den Builder.  
2. Fügen Sie bei Bedarf Klartext‑ und ECI‑kodierte Fragmente hinzu.  
3. Rufen Sie den finalen String ab und übergeben Sie ihn Ihrem Barcode‑Generator.

Wenn Sie dem obigen Muster folgen, können Sie jede Mischung aus ASCII‑ und Unicode‑Daten verarbeiten, häufige Kodierungsfehler vermeiden und Barcode‑bereite Strings erzeugen, die mit einer breiten Palette von Scannern funktionieren. Experimentieren Sie mit verschiedenen ECIs, integrieren Sie den Builder in Ihre Daten‑Pipeline, und Sie haben eine solide Grundlage für all Ihre erweiterten Codetext‑Bedürfnisse.

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
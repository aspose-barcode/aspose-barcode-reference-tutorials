---
category: general
date: 2026-11-20
description: Erfahren Sie, wie Sie ECI verwenden, QR aus Text generieren, den Builder
  zurücksetzen und das QR‑Bild mit der Python‑Barcode‑Bibliothek speichern.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use eci
- generate qr from text
- how to clear builder
- save qr image
- clear qr builder
language: de
lastmod: 2026-11-20
og_description: Wie man ECI verwendet, um QR aus Text zu erzeugen, den QR‑Builder
  zu leeren und das QR‑Bild zu speichern – ein vollständiger Schritt‑für‑Schritt‑Leitfaden.
og_image_alt: Diagram illustrating how to use ECI to generate a QR code and save the
  QR image
og_title: Wie man ECI bei der QR‑Code‑Generierung mit Python verwendet
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to use ECI, generate QR from text, clear the builder, and
    save QR image using the Python barcode library.
  headline: How to use ECI in QR code generation with Python
  type: TechArticle
tags:
- QR code
- Python
- barcode
- ECI
title: Wie man ECI bei der QR‑Code‑Generierung mit Python verwendet
url: /de/python/general/how-to-use-eci-in-qr-code-generation-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man ECI bei der QR-Code-Generierung mit Python verwendet

Wenn Sie **wie man ECI verwendet** beim Erstellen von QR-Codes benötigen, zeigt Ihnen diese Anleitung die genauen Schritte. Sie sehen, wie man QR aus Text generiert, den Builder löscht und schließlich das QR‑Bild speichert – alles mit wenigen Zeilen Python.

QR‑Codes, die mehrsprachige Daten enthalten, benötigen häufig ein Extended Channel Interpretation (ECI)‑Segment, damit Scanner wissen, welchen Zeichensatz sie anwenden sollen. Dieses Tutorial führt Sie durch das Erstellen eines erweiterten Codetextes, das Löschen des Builders bei Wiederverwendung und das Speichern des Ergebnisses als PNG‑Datei.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- Python 3.8+ installiert.
- Das Aspose.BarCode for Python via .NET‑Paket (oder eine kompatible `barcode`‑Bibliothek, die `ExtCodetextBuilder` und `BarcodeGenerator` bereitstellt).
- Grundlegende Kenntnisse zu QR‑Code‑Konzepten.

Installieren Sie die Bibliothek mit pip:

```bash
pip install aspose-barcode
```

> **Pro‑Tipp:** Verwenden Sie ein virtuelles Umfeld, um Versionskonflikte zu vermeiden.

## Schritt 1: Importieren der benötigten Klassen

Die wichtigsten Klassen, mit denen Sie arbeiten werden, sind `ExtCodetextBuilder` zum Erstellen des erweiterten Codetextes und `BarcodeGenerator` zum Rendern des QR‑Codes.

```python
from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
```

Diese Importe geben Ihnen Zugriff auf die Builder‑Methoden (`add_plain_codetext`, `add_eci_codetext` usw.) und die Generator‑Funktionen `set_code_text`, `set_symbology` und `save`.

## Schritt 2: Erstellen und Konfigurieren des ExtCodetextBuilders

Das Erzeugen einer neuen Builder‑Instanz ist das erste konkrete Beispiel für **wie man ECI verwendet**. Sie können den Builder später auch löschen, wenn Sie ihn erneut verwenden müssen.

```python
# Create an ExtCodetextBuilder instance
extended_text_builder = ExtCodetextBuilder()

# Optional: clear any previous items (useful when reusing the same builder)
extended_text_builder.clear()   # this demonstrates how to clear builder
```

Der Aufruf von `clear()` stellt sicher, dass der Builder mit einem sauberen Zustand beginnt – das ist wichtig, wenn Sie mehrere QR‑Codes in einer Schleife erzeugen.

## Schritt 3: Hinzufügen von einfachem (nicht‑ECI) Codetext

Einfacher Text benötigt kein ECI‑Segment. Verwenden Sie `add_plain_codetext` für ASCII‑kompatible Zeichenketten.

```python
# Add plain codetext (e.g., an English phrase)
extended_text_builder.add_plain_codetext("HelloWorld")
```

Der Builder enthält nun das einfache Segment `"HelloWorld"`.

## Schritt 4: Hinzufügen eines ECI‑kodierten Segments

Hier liegt der Kern von **wie man ECI verwendet**: Sie geben den ECI‑Wert (26 für UTF‑8) an und übergeben die Unicode‑Zeichenkette, die Sie kodieren möchten. Dadurch kann der QR‑Code Russisch, Chinesisch oder jede andere Sprache transportieren, die nicht im Standard‑ISO‑8859‑1‑Zeichensatz enthalten ist.

```python
# Add ECI‑encoded codetext (ECI value 26 = UTF‑8, Russian “Hello”)
extended_text_builder.add_eci_codetext(26, "Привет")
```

> **Warum das wichtig ist:** Ohne den ECI‑Indikator würde ein Scanner die Bytes mit dem Standard‑Zeichensatz interpretieren und bei Nicht‑ASCII‑Text unsinnige Zeichen anzeigen.

## Schritt 5: Abrufen der kombinierten erweiterten Codetext‑Zeichenkette

Nachdem Sie alle erforderlichen Segmente hinzugefügt haben, holen Sie sich die finale Zeichenkette, die an den QR‑Generator übergeben wird.

```python
combined_extended_text = extended_text_builder.get_extended_codetext()
print("Extended codetext:", combined_extended_text)
```

Der ausgegebene Wert sieht etwa so aus:

```
Extended codetext: [ECI26]ПриветHelloWorld
```

Das genaue Format hängt von der Bibliothek ab, aber wichtig ist, dass der ECI‑Marker (`[ECI26]`) dem UTF‑8‑Payload vorausgeht.

## Schritt 6: QR‑Code mit dem kombinierten Text generieren

Jetzt können Sie **QR aus Text generieren**, indem Sie den erweiterten Codetext an `BarcodeGenerator` übergeben.

```python
# Initialize the QR generator
qr_generator = barcode.generation.BarcodeGenerator()

# Assign the combined extended codetext
qr_generator.set_code_text(combined_extended_text)

# Choose QR symbology (the library supports many, QR is the most common)
qr_generator.set_symbology(barcode.Symbology.QR)

# Save the QR image to disk – this demonstrates how to save QR image
output_path = "qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

Wenn Sie `qr_extended.png` öffnen, erscheint ein QR‑Code, der sowohl die einfache englische Zeichenkette als auch die russische Begrüßung kodiert. Wird er mit einem modernen QR‑Scanner gelesen, werden „HelloWorld“ und „Привет“ korrekt angezeigt.

### Warum Sie `clear()` vor der Wiederverwendung des Builders aufrufen sollten

Wenn Sie mehrere QR‑Codes in einer Schleife erzeugen, führt das Vergessen von `clear()` dazu, dass alte Segmente mit neuen zusammengefügt werden und ein ungültiger Code entsteht. Ein kurzer Muster‑Code:

```python
for text, eci, unicode_str in data_set:
    extended_text_builder.clear()                       # ensures a fresh start
    extended_text_builder.add_plain_codetext(text)
    extended_text_builder.add_eci_codetext(eci, unicode_str)
    qr_generator.set_code_text(extended_text_builder.get_extended_codetext())
    qr_generator.save(f"qr_{text}.png")
```

Dieses Snippet veranschaulicht **wie man den Builder löscht** und **wie man QR aus Text wiederholt generiert**.

## Randfälle und häufige Stolperfallen

| Situation | Worauf zu achten ist | Wie man damit umgeht |
|-----------|----------------------|----------------------|
| **Nicht unterstützter ECI‑Wert** | Die Bibliothek wirft `InvalidArgumentException`. | Verwenden Sie nur ECI‑Werte, die in der Spezifikation aufgeführt sind (z. B. 26 für UTF‑8, 20 für Shift‑JIS). |
| **Sehr langer kombinierter Text** | Die QR‑Version kann die maximale Kapazität überschreiten. | Erhöhen Sie die QR‑Version automatisch (`qr_generator.set_qr_version(QRVersion.AUTO)`) oder teilen Sie die Daten auf mehrere QR‑Codes auf. |
| **Dateisystem‑Berechtigungsfehler** | `save` schlägt mit `IOError` fehl. | Stellen Sie sicher, dass das Zielverzeichnis existiert und der Prozess Schreibrechte hat. |
| **Falsche Zeichensatzanzeige** | Der Scanner zeigt unsinnige Zeichen. | Prüfen Sie, ob der verwendete ECI‑Wert zur tatsächlichen Kodierung der Zeichenkette passt. |

## Vollständiges, ausführbares Beispiel

Unten finden Sie ein eigenständiges Skript, das Sie kopieren, einfügen und ausführen können. Es enthält alle Importe, Fehlerbehandlung und Kommentare zur Klarheit.

```python
# qr_eci_example.py
# Demonstrates how to use ECI, generate QR from text, clear the builder,
# and save QR image using Aspose.BarCode for Python.

from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
import os

def generate_qr(plain_text: str, eci_value: int, unicode_text: str, out_file: str):
    """
    Creates a QR code that contains both plain and ECI‑encoded text.
    Parameters:
        plain_text – ASCII‑compatible string.
        eci_value  – Numeric ECI identifier (e.g., 26 for UTF‑8).
        unicode_text – Text that requires the specified ECI.
        out_file – Destination file path for the PNG image.
    """
    # Step 1: instantiate and clear the builder
    builder = ExtCodetextBuilder()
    builder.clear()                       # how to clear builder

    # Step 2: add segments
    builder.add_plain_codetext(plain_text)
    builder.add_eci_codetext(eci_value, unicode_text)

    # Step 3: retrieve combined text
    combined = builder.get_extended_codetext()
    print("Combined extended codetext:", combined)

    # Step 4: generate QR code
    generator = barcode.generation.BarcodeGenerator()
    generator.set_code_text(combined)
    generator.set_symbology(barcode.Symbology.QR)

    # Ensure output directory exists
    os.makedirs(os.path.dirname(out_file), exist_ok=True)

    # Step 5: save QR image – how to save QR image
    generator.save(out_file)
    print(f"QR code saved as {out_file}")

if __name__ == "__main__":
    # Example usage
    generate_qr(
        plain_text="HelloWorld",
        eci_value=26,               # UTF‑8
        unicode_text="Привет",      # Russian "Hello"
        out_file="output/qr_extended.png"
    )
```

Beim Ausführen dieses Skripts entsteht `output/qr_extended.png`, ein QR‑Code, der sowohl englischen als auch russischen Text korrekt kodiert.

## Fazit

Sie wissen jetzt **wie man ECI verwendet** beim Erstellen von QR‑Codes, **wie man den QR‑Builder löscht** vor der Wiederverwendung, **wie man QR aus Text generiert** und die genauen Schritte, um **QR‑Bild zu speichern** mit Python. Wenn Sie das oben gezeigte Muster befolgen, können Sie jede Unicode‑Zeichenkette in einen QR‑Code einbetten und gleichzeitig den Builder‑Zustand vorhersehbar halten.

### Was kommt als Nächstes?

- Erkunden Sie weitere ECI‑Werte für Sprachen wie Chinesisch (ECI 20) oder ISO‑8859‑5.
- Passen Sie die Fehlertoleranzstufen an (`qr_generator.set_error_correction_level`), um die Scan‑Zuverlässigkeit zu verbessern.
- Kombinieren Sie mehrere ECI‑Segmente in einem einzigen QR für gemischte Sprachnachrichten.

Viel Spaß beim Coden und beim Erstellen mehrsprachiger QR‑Codes!

## Was sollten Sie als Nächstes lernen?


Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Code‑Beispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, weitere API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [How to generate barcode with ECI using Aspose.Barcode Python](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [How to generate barcode in Python – complete step‑by‑step guide](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
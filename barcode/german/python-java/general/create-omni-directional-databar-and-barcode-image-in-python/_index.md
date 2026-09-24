---
category: general
date: 2026-08-12
description: Erstellen Sie einen omnidirektionalen Databar mit Python und lernen Sie,
  wie Sie ein Barcode‑Bild in Python mit Aspose.BarCode erzeugen. Folgen Sie der Schritt‑für‑Schritt‑Anleitung
  für eine vollständige Lösung.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni directional databar
- create barcode image python
language: de
lastmod: 2026-08-12
og_description: Erstelle einen omnidirektionalen Databar mit Python und generiere
  in Minuten ein Barcode‑Bild mit Python. Dieses Tutorial zeigt ein vollständiges,
  ausführbares Beispiel.
og_image_alt: example of create omni directional databar barcode image in Python
og_title: Erstelle omnidirektionale Databar – vollständiger Python-Leitfaden
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create omni directional databar with Python and learn how to create
    barcode image python using Aspose.BarCode. Follow the step‑by‑step guide for a
    complete solution.
  headline: Create omni directional databar and barcode image in Python
  type: TechArticle
tags:
- barcode
- Python
- Aspose
- DataBar
title: Erstelle ein omnidirektionales Databar‑ und Barcode‑Bild in Python
url: /de/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erstellen eines omni‑directional DataBar und Barcode‑Bildes in Python

Wenn Sie in einem Python‑Projekt **create omni directional databar** erstellen müssen, zeigt Ihnen diese Anleitung, wie Sie das tun und auch, wie Sie **create barcode image python** mithilfe der Aspose.BarCode‑Bibliothek erstellen können. Sie erhalten ein sofort ausführbares Skript, das zwei PNG‑Dateien mit unterschiedlichen Seitenverhältnissen erzeugt.

Das Erzeugen eines DataBar, das der Omni‑directional‑Spezifikation entspricht, ist eine häufige Anforderung für Einzelhandels‑ und Logistikanwendungen. Das Tutorial behandelt die Installation, die Konfiguration der X‑Dimension, die Anpassung des Seitenverhältnisses und das Speichern der finalen Bilder. Es werden keine externen Dienste benötigt; alles läuft lokal.

## Was Sie benötigen

* Python 3.8 oder neuer, auf Ihrem Rechner installiert.
* Zugriff auf ein Terminal oder die Eingabeaufforderung.
* Schreibrechte für einen Ordner, in dem die Barcode‑Bilder gespeichert werden.

Die einzige Drittanbieter‑Abhängigkeit ist **Aspose.BarCode for Python via .NET**, das den Omni‑directional DataBar‑Typ sofort unterstützt.

## Schritt 1: Aspose.BarCode für Python installieren

Aspose.BarCode stellt die im Beispielcode verwendete Klasse `BarcodeGenerator` bereit. Installieren Sie das Paket mit `pip`:

```bash
pip install aspose-barcode
```

Das Paket enthält die erforderlichen .NET‑Runtime‑Bindings, sodass Sie das .NET‑SDK nicht separat installieren müssen.

## Schritt 2: Bibliothek importieren und Generator erstellen

Die erste Zeile des Skripts erstellt einen Generator für einen gestapelten Omni‑directional DataBar. Der GTIN‑14‑Wert `(01)12345678901231` wird als Beispieldaten verwendet.

```python
# Step 2: Import classes and create the generator
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a stacked Omni‑directional DataBar with the required data
barcode_generator = BarcodeGenerator(
    EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
    "(01)12345678901231"
)
```

*Warum dieser Schritt wichtig ist*: Die Konstante `EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL` weist die Bibliothek an, den Wert als Omni‑directional DataBar zu kodieren, das Format, das von vielen Point‑of‑Sale‑Scannern benötigt wird.

## Schritt 3: X‑Dimension festlegen (Modulbreite)

Die X‑Dimension definiert die Breite des kleinsten Balkenmoduls. Ein Wert von `2` Pixeln erzeugt einen klaren, lesbaren Barcode ohne übermäßige Dateigröße.

```python
# Step 3: Set the basic X‑dimension (width of the smallest module) in pixels
barcode_generator.parameters.barcode.x_dimension.pixels = 2
```

*Warum dieser Schritt wichtig ist*: Durch Anpassen der X‑Dimension können Sie Lesbarkeit und Bildabmessungen ausbalancieren. Eine zu kleine X‑Dimension kann auf Niedrigauflösungs‑Druckern schlecht dargestellt werden.

## Schritt 4: Seitenverhältnis konfigurieren und erstes Bild speichern

Das Seitenverhältnis beeinflusst die Gesamthöhe des DataBar im Verhältnis zur Breite. Ein Seitenverhältnis von `15` erzeugt einen kompakten visuellen Stil.

```python
# Step 4: Configure an aspect ratio of 15 and save the first image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 15
barcode_generator.save("output/StackedAR15.png", BarCodeImageFormat.Png)
```

> **Pro‑Tipp**: Verwenden Sie `pathlib.Path`, um den Ausgabepfad zu erstellen, der fehlende Verzeichnisse automatisch anlegt.

```python
from pathlib import Path

output_dir = Path("output")
output_dir.mkdir(parents=True, exist_ok=True)
barcode_generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)
```

## Schritt 5: Seitenverhältnis für einen zweiten visuellen Stil ändern und ein weiteres Bild speichern

Das Ändern des Seitenverhältnisses auf `30` erzeugt einen höheren Barcode, der von bestimmter Scanner‑Hardware erforderlich sein kann.

```python
# Step 5: Change the aspect ratio to 30 and save the second image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 30
barcode_generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)
```

*Warum dieser Schritt wichtig ist*: Verschiedene Einzelhändler und Scan‑Geräte haben unterschiedliche Größenbeschränkungen. Das Bereitstellen beider Seitenverhältnisse in einem einzigen Skript ermöglicht es Ihnen, den genauen Stil zu erzeugen, den Sie benötigen, ohne Code zu duplizieren.

## Vollständiges Skript – create omni directional databar and barcode image python

Unten finden Sie das vollständige, ausführbare Beispiel, das alle vorherigen Schritte integriert. Speichern Sie es als `generate_databar.py` und führen Sie es mit `python generate_databar.py` aus.

```python
#!/usr/bin/env python3
"""
Complete example that creates an omni directional databar
and demonstrates how to create barcode image python using Aspose.BarCode.
"""

# Import required classes
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from pathlib import Path

def main():
    # Define output directory and ensure it exists
    output_dir = Path("output")
    output_dir.mkdir(parents=True, exist_ok=True)

    # Initialize the generator with Omni‑directional DataBar data
    generator = BarcodeGenerator(
        EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
        "(01)12345678901231"
    )

    # Set X‑dimension to 2 pixels for good readability
    generator.parameters.barcode.x_dimension.pixels = 2

    # First visual style – aspect ratio 15
    generator.parameters.barcode.data_bar.aspect_ratio = 15
    generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)

    # Second visual style – aspect ratio 30
    generator.parameters.barcode.data_bar.aspect_ratio = 30
    generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)

    print(f"Images saved to: {output_dir.resolve()}")

if __name__ == "__main__":
    main()
```

### Erwartete Ausgabe

Das Ausführen des Skripts erzeugt die folgenden Dateien:

```
output/StackedAR15.png   # DataBar with aspect ratio 15
output/StackedAR30.png   # DataBar with aspect ratio 30
```

Beide Bilder zeigen einen gültigen Omni‑directional DataBar, der von Standard‑Einzelhandelsgeräten gescannt werden kann.

![example of create omni directional databar barcode image in Python](example_databar.png "create omni directional databar barcode image python")

*Das obige Bild ist ein Platzhalter, der die beiden gespeicherten PNG‑Dateien veranschaulicht.*

## Umgang mit häufigen Problemen

| Problem | Ursache | Lösung |
|-------|--------|-----|
| `ImportError: No module named aspose` | Aspose.BarCode nicht installiert oder in einer anderen Umgebung installiert. | Aktivieren Sie die richtige virtuelle Umgebung und führen Sie `pip install aspose-barcode` aus. |
| `PermissionError` when saving | Das Skript hat keine Schreibberechtigung für das Zielverzeichnis. | Wählen Sie ein Verzeichnis, das Ihnen gehört, oder führen Sie das Skript mit entsprechenden Rechten aus. |
| Barcode does not scan | X‑Dimension zu klein oder Seitenverhältnis inkompatibel mit dem Scanner. | Erhöhen Sie `x_dimension.pixels` auf 3 oder 4 und testen Sie verschiedene `aspect_ratio`‑Werte (z. B. 20, 25). |
| Missing .NET runtime | Aspose.BarCode hängt von der .NET‑Runtime unter Windows/Linux ab. | Installieren Sie die neueste .NET‑Runtime von Microsofts Seite; die Paketanleitung bietet plattformspezifische Hinweise. |

## Erweiterung des Beispiels

Sie können das Skript anpassen, um andere DataBar‑Varianten zu erzeugen (z. B. `DATABAR_STACKED`, `DATABAR_EXPANDED`). Ersetzen Sie die `EncodeTypes`‑Konstante entsprechend:

```python
generator = BarcodeGenerator(EncodeTypes.DATABAR_EXPANDED, "(01)12345678901231")
```

Falls Sie den Barcode in ein PDF einbetten müssen, kann Aspose.PDF für Python die PNG‑Datei direkt importieren oder Sie können die `save`‑Methode mit `BarCodeImageFormat.Pdf` verwenden.

## Fazit

Dieses Tutorial zeigte, wie man **create omni directional databar** und **create barcode image python** mit Aspose.BarCode erstellt. Sie haben nun ein vollständiges, reproduzierbares Skript, das zwei PNG‑Dateien mit unterschiedlichen Seitenverhältnissen erzeugt, gängige Fallstricke behandelt und auf andere Barcode‑Formate erweitert werden kann.

Als Nächstes können Sie die Erzeugung von QR‑Codes, das Hinzufügen des Barcodes zu PDF‑Rechnungen oder die Automatisierung der Stapelverarbeitung für große Produktkataloge erkunden. Jeder dieser Themen baut auf dem hier gezeigten `BarcodeGenerator`‑Muster auf. Viel Spaß beim Coden!

## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige funktionierende Code‑Beispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, zusätzliche API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [Barcode‑Bild generieren – GS1 Coupon UPC‑A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [DotCode‑Barcode‑Bild erstellen – Zeilen & Spalten (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Wie man ein Barcode‑Bild erstellt und in Java rendert](/barcode/english/java/barcode-rendering-techniques/rendering-barcode-image-instance/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
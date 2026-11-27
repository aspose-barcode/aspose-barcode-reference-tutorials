---
category: general
date: 2026-11-27
description: Erfahren Sie, wie Sie die Balkenhöhe des Barcodes in einem DataBar Omni‑Directional‑Barcode‑Generator
  anpassen. Schritt‑für‑Schritt‑Code zeigt das Einstellen der Höhen auf 30 px und
  60 px.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- adjust barcode bar height
- DataBar Omni‑Directional barcode
- set XDimension
- barcode image format
- BarCodeImageFormat
- barcode generator python
language: de
lastmod: 2026-11-27
og_description: Passen Sie die Strichhöhe des Barcodes in einem DataBar Omni‑Directional‑Barcode‑Generator
  mit Python an. Folgen Sie der vollständigen Anleitung, um Höhen, X‑Dimension einzustellen
  und PNG‑Bilder zu speichern.
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode with adjusted bar height
og_title: Barcode‑Balkenhöhe im DataBar Omni‑Directional‑Generator anpassen
schemas:
- author: GroupDocs
  dateModified: '2026-11-27'
  description: Learn how to adjust barcode bar height in a DataBar Omni‑Directional
    barcode generator. Step‑by‑step code shows setting heights to 30 px and 60 px.
  headline: How to adjust barcode bar height in DataBar Omni‑Directional generator
  type: TechArticle
tags:
- barcode
- python
- DataBar
- imaging
title: Wie man die Balkenhöhe des Barcodes im DataBar Omni‑Directional‑Generator anpasst
url: /de/python-java/general/how-to-adjust-barcode-bar-height-in-databar-omni-directional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man die Balkenhöhe eines Barcodes im DataBar Omni‑Directional‑Generator anpasst

Wenn Sie die **Balkenhöhe eines Barcodes** für einen DataBar Omni‑Directional‑Barcode anpassen müssen, zeigt Ihnen diese Anleitung genau, wie das geht. Sie sehen ein vollständiges, ausführbares Python‑Beispiel, das die Balkenhöhe von 30 px auf 60 px ändert, während X‑Dimension und Bildformat konsistent bleiben.

Das Ändern der visuellen Abmessungen eines Barcodes ist ein häufiges Bedürfnis, wenn der Barcode in eine bestimmte Etikettengröße oder ein Design‑Richtlinie passen muss. Zusätzlich zur Balkenhöhe möchten Sie möglicherweise auch die **X‑Dimension** (Modulgröße) anpassen oder ein anderes **Barcode‑Bildformat** wie PNG oder JPEG wählen.

In diesem Tutorial werden Sie:

* Die erforderliche Bibliothek installieren (GroupDocs.Barcode für Python)
* Einen DataBar Omni‑Directional‑Barcode‑Generator erstellen
* Die Modulgröße mit `XDimension` festlegen
* Die Balkenhöhe zweimal anpassen
* Die resultierenden Bilder im gewünschten **BarCodeImageFormat** speichern

Vorkenntnisse mit der GroupDocs‑API sind nicht nötig – nur Grundkenntnisse in Python.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie:

* Python 3.8 oder neuer installiert haben
* Das Paket `groupdocs.barcode` (`pip install groupdocs-barcode`)  
* Schreibrechte für einen Ordner, in dem die PNG‑Dateien gespeichert werden

Falls Ihnen der **DataBar Omni‑Directional‑Barcode** nicht bekannt ist: Er codiert eine 14‑stellige GTIN und wird im Einzelhandel häufig verwendet, um aus jeder Orientierung gescannt zu werden.

## Schritt 1: DataBar Omni‑Directional‑Barcode‑Generator einrichten

Importieren Sie zunächst die notwendigen Klassen und instanziieren Sie den Generator mit den GTIN‑Daten, die Sie codieren möchten.

```python
from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a DataBar Omni‑Directional barcode
# The string "(01)12345678901231" follows the GS1 Application Identifier syntax
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")
```

*Warum das wichtig ist:* Die Konstante `EncodeTypes.DatabarOmniDirectional` weist die Bibliothek an, die Omni‑Directional‑Symbologie zu erzeugen. Der Datenstring enthält die AI `(01)`, die einen GTIN‑14‑Wert kennzeichnet.

## Schritt 2: X‑Dimension (Modulgröße) festlegen

Die X‑Dimension steuert die Breite des schmalsten Balkens. Ein gängiger Wert für die Bildschirmausgabe ist **2 px pro Modul**.

```python
# Set the module (X‑dimension) size – 2 px per module
gen.parameters.barcode.x_dimension.pixels = 2
```

Die konsequente Verwendung von **set XDimension** stellt sicher, dass der Barcode über verschiedene Drucker und Scanner hinweg korrekt skaliert wird.

## Schritt 3: Balkenhöhe auf 30 px einstellen und Bild speichern

Jetzt ändern wir die Balkenhöhe‑Eigenschaft. Die erste Höhe, die wir verwenden, ist **30 px**, was für kleine Etiketten geeignet ist.

```python
# Define the first bar height (30 px)
gen.parameters.barcode.bar_height.pixels = 30

# Save the barcode as a PNG image
gen.save("output/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png)
```

Die Konstante `BarCodeImageFormat.Png` wählt das **Barcode‑Bildformat** PNG, das verlustfreie Qualität bewahrt.

### Erwartetes Ergebnis

Die Datei `DatabarBarHeight30Pixels.png` enthält einen DataBar Omni‑Directional‑Barcode, dessen Balken 30 px hoch sind. Unten sehen Sie eine Platzhalter‑Vorschau:

![DataBar barcode with 30 px bar height](images/databar_30px.png "DataBar barcode with 30 px bar height")

> **Tipp:** Öffnen Sie das PNG in einem Bildeditor, dann sehen Sie die exakte Balkenhöhe. Die schmalen Balken sind 2 px breit, wie zuvor definiert.

## Schritt 4: Balkenhöhe auf 60 px ändern für einen höheren Barcode

Für Anwendungen, die einen größeren visuellen Fußabdruck benötigen – etwa ein Frachlabel – können Sie die Balkenhöhe auf **60 px** erhöhen.

```python
# Change the bar height to 60 px for a taller barcode
gen.parameters.barcode.bar_height.pixels = 60
```

Nur die Eigenschaft `BarHeight` ändert sich; X‑Dimension und Codierung bleiben gleich, sodass der Barcode weiterhin scannbar ist.

## Schritt 5: Das aktualisierte Barcode‑Bild speichern

Schließlich schreiben Sie den höheren Barcode in eine zweite PNG‑Datei.

```python
# Save the updated barcode image
gen.save("output/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png)
```

### Erwartetes Ergebnis

Die Datei `DatabarBarHeight60Pixels.png` zeigt dieselben codierten Daten, jedoch ist jeder Balken jetzt 60 px hoch. Der visuelle Unterschied ist unten dargestellt:

![DataBar barcode with 60 px bar height](images/databar_60px.png "DataBar barcode with 60 px bar height")

## Vollständiges, ausführbares Beispiel

Alles zusammengeführt, hier das komplette Skript, das Sie in eine Datei namens `adjust_barcode_height.py` kopieren und direkt ausführen können.

```python
# adjust_barcode_height.py
# Demonstrates how to adjust barcode bar height for a DataBar Omni‑Directional barcode

from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# 1️⃣ Create the generator with GTIN data
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")

# 2️⃣ Set module size (X‑dimension) to 2 px
gen.parameters.barcode.x_dimension.pixels = 2

# 3️⃣ First bar height: 30 px
gen.parameters.barcode.bar_height.pixels = 30
gen.save(os.path.join(output_dir, "DatabarBarHeight30Pixels.png"), BarCodeImageFormat.Png)

# 4️⃣ Second bar height: 60 px
gen.parameters.barcode.bar_height.pixels = 60
gen.save(os.path.join(output_dir, "DatabarBarHeight60Pixels.png"), BarCodeImageFormat.Png)

print(f"Barcodes saved to '{output_dir}'")
```

Skript ausführen:

```bash
python adjust_barcode_height.py
```

Sie sollten zwei PNG‑Dateien im Ordner `output` sehen, die jeweils die von Ihnen eingestellte Balkenhöhe widerspiegeln.

## Häufige Fragen und Sonderfälle

| Frage | Antwort |
|----------|--------|
| **Kann ich JPEG anstelle von PNG verwenden?** | Ja. Ersetzen Sie `BarCodeImageFormat.Png` durch `BarCodeImageFormat.Jpeg`. JPEG ist verlustbehaftet, daher bevorzugen Sie PNG für präzises Scannen. |
| **Was, wenn ich eine Balkenhöhe brauche, die kein Vielfaches von 10 ist?** | Die Eigenschaft `BarHeight.Pixels` akzeptiert jeden ganzzahligen Wert. Weisen Sie einfach die gewünschte Pixelzahl zu (z. B. `45`). |
| **Beeinflusst das Ändern der Balkenhöhe die codierten Daten?** | Nein. Nur die visuelle Darstellung ändert sich; der zugrunde liegende Datenstring bleibt unverändert. |
| **Wie ändere ich die X‑Dimension nach dem Speichern des ersten Bildes?** | Sie können `gen.parameters.barcode.x_dimension.pixels` jederzeit vor dem Aufruf von `save()` anpassen. Die Änderung gilt für nachfolgende Bilder. |
| **Ist der Generator thread‑sicher?** | Die Instanz `BarcodeGenerator` ist nicht garantiert thread‑sicher. Erstellen Sie für jeden Thread eine separate Instanz, wenn Sie Barcodes parallel erzeugen. |

## Fazit

Sie wissen jetzt, wie Sie die **Balkenhöhe eines Barcodes** in einem DataBar Omni‑Directional‑Barcode‑Generator mit Python anpassen. Das Tutorial behandelte das Erstellen des Generators, das Setzen der **X‑Dimension**, das Modifizieren der **barcode bar height**‑Eigenschaft und das Speichern der Bilder im gewünschten **barcode image format**.

Ab hier können Sie mit anderen Höhen, unterschiedlichen Modulgrößen experimentieren oder zu alternativen Bildformaten wie JPEG oder BMP wechseln. Außerdem können Sie weitere **barcode generator python**‑Funktionen erkunden, etwa das Hinzufügen von menschenlesbarem Text oder das Ändern von Farbschemata.

Viel Spaß beim Coden und halten Sie Ihre Barcodes scharf und perfekt dimensioniert!

## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Codebeispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, zusätzliche API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [Wie man Breite setzt und Höhe für einen GS1 DataBar Omni‑Directional‑Barcode anpasst](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [Omni‑Directional‑Databar und Barcode‑Bild in Python erstellen](/barcode/english/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/)
- [.net barcode generator – barcode height ändern](/barcode/english/python-java/general/net-barcode-generator-change-barcode-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
---
category: general
date: 2026-08-19
description: Wie man mit Aspose.Barcode für Python einen Barcode mit ECI erzeugt.
  Erfahren Sie, wie Sie ECI‑Daten hinzufügen, Klartext mischen und das Bild in einer
  klaren Anleitung speichern.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to add eci
- Aspose.Barcode Python
- extended codetext barcode
- ECI encoding Python
language: de
lastmod: 2026-08-19
og_description: Wie man mit Aspose.Barcode für Python einen Barcode mit ECI erstellt.
  Folgen Sie diesem Tutorial, um zu lernen, wie man ECI‑Daten hinzufügt, das Aussehen
  anpasst und das Ergebnis speichert.
og_image_alt: Screenshot showing a barcode generated with how to generate barcode
  example
og_title: Wie man mit Aspose.Barcode Python einen Barcode mit ECI erzeugt – Schritt
  für Schritt
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  headline: How to generate barcode with ECI using Aspose.Barcode Python
  type: TechArticle
- description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  name: How to generate barcode with ECI using Aspose.Barcode Python
  steps:
  - name: Expected result
    text: When you open `extended_codetext.png`, you should see a Code 128 barcode
      that encodes the numeric string `1234567890` followed by the Chinese characters
      “特殊字符”. Scanning the barcode with a modern scanner that respects ECI will return
      the original mixed string.
  - name: What if I need a different character set?
    text: Choose the appropriate ECI value from the ISO/IEC 18004 table. For example,
      ECI 27 represents ISO‑8859‑1 (Latin‑1). Replace the numeric identifier in `add_eci_codetext`
      accordingly.
  - name: Can I embed more than one ECI block?
    text: Yes. Call `add_eci_codetext` multiple times. The builder inserts the necessary
      ECI switch codes between blocks, preserving the order you add them.
  - name: Does the generator support QR codes with ECI?
    text: Absolutely. Replace `barcode.Symbology.CODE_128` with `barcode.Symbology.QR`
      and adjust any QR‑specific parameters (e.g., error correction level) via `generator.parameters.qr`.
  - name: How to handle very long data strings?
    text: For linear barcodes like Code 128, the maximum length is about 80 characters
      when using extended codetext. If you exceed that, consider switching to a two‑dimensional
      symbology such as QR or Data Matrix, which can store thousands of characters.
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: Wie man mit Aspose.Barcode Python einen Barcode mit ECI erzeugt
url: /de/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man einen Barcode mit ECI unter Verwendung von Aspose.Barcode Python erzeugt

Wenn Sie wissen möchten, **wie man einen Barcode** erzeugt, der sowohl einfache Zeichen als auch ECI‑kodierte Daten enthält, zeigt Ihnen diese Anleitung den kompletten Prozess. Sie sehen genau, **wie man eci**‑Abschnitte hinzufügt, die Größe anpasst und das Bild mit einem einzigen, ausführbaren Skript auf die Festplatte schreibt.

Die Anleitung behandelt:

* Abrufen der Aspose.Barcode‑Bibliotheksversion (optional, aber nützlich für die Fehlersuche).  
* Erstellen einer erweiterten Codetext‑Zeichenkette, die einfache und ECI‑kodierte Zeichen mischt.  
* Erzeugen eines Barcode‑Generators für eine Symbolik, die erweiterten Codetext unterstützt.  
* Anpassen der Barcode‑Abmessungen und Speichern der finalen PNG‑Datei.

Keine externe Dokumentation ist erforderlich; kopieren Sie den Code, führen Sie ihn aus, und Sie erhalten ein Barcode‑Bild, das chinesische Zeichen enthält, die mit ECI 26 (UTF‑8) kodiert sind.

## Voraussetzungen

Stellen Sie vor dem Start sicher, dass Sie Folgendes haben:

* Python 3.8 oder neuer installiert.  
* Das Paket `aspose-barcode` installiert (`pip install aspose-barcode`).  
* Schreibrechte für den Ordner, in dem Sie die PNG‑Datei speichern möchten.

Wenn Sie eine virtuelle Umgebung verwenden, aktivieren Sie diese zuerst, um Abhängigkeiten isoliert zu halten.

## Schritt 1: Überprüfen der Aspose.Barcode‑Version (optional)

Das genaue Wissen um die Bibliotheksversion hilft, wenn Sie Fehler melden oder Funktionen zwischen Releases vergleichen müssen.

```python
import aspose.barcode as barcode
from aspose.barcode.generation import BuildVersionInfo

ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)
```

*Warum das wichtig ist*: Die Versionsausgabe bestätigt, dass die Laufzeit mit der Dokumentation übereinstimmt, der Sie folgen. Unterschiedliche Versionen können unterschiedliche ECI‑Werte unterstützen, daher ist dies ein schneller Plausibilitäts‑Check.

## Schritt 2: Erstellen eines erweiterten Codetexts mit einfachen und ECI‑kodierten Teilen

Aspose.Barcode stellt `ExtCodetextBuilder` bereit, um einfache Daten und ECI‑kodierte Segmente zu verketten. In diesem Beispiel mischen wir eine numerische Zeichenkette mit chinesischen Zeichen.

```python
from aspose.barcode.generation import ExtCodetextBuilder

builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using ECI 26 (UTF‑8)
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)
```

*Erklärung*:  
* `add_plain_codetext` fügt Daten ein, die die Barcode‑Symbolik als gewöhnliche Zeichen behandelt.  
* `add_eci_codetext` weist den Generator an, einen ECI‑Indikator (hier **26**, der UTF‑8 entspricht) vor den angegebenen Text zu setzen. Das ist genau **wie man eci**‑Daten zu einem Barcode hinzufügt.

Sie können `add_eci_codetext` mehrfach aufrufen, um mehrere unterschiedliche Sprachblöcke einzubetten. Der Builder übernimmt automatisch die erforderlichen Escape‑Sequenzen.

## Schritt 3: Auswahl einer Symbolik, die erweiterten Codetext unterstützt

Nicht jeder Barcode‑Typ kann ECI‑Segmente speichern. Code 128, QR und Data Matrix sind gängige Optionen. Das Beispiel verwendet Code 128, weil es weit verbreitet ist und gut für gemischte alphanumerische Daten funktioniert.

```python
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,   # Code128 supports extended codetext
    extended_codetext
)
```

*Warum Code 128?*: Es akzeptiert den gesamten ASCII‑Bereich und die vom Builder erzeugten ECI‑Escape‑Sequenzen, was es ideal für das Szenario „wie man einen Barcode erzeugt“ macht, bei dem einfacher und kodierter Text gemischt werden.

## Schritt 4: Anpassen des Barcode‑Aussehens

Sie können Größe, Höhe, Ränder und viele weitere visuelle Aspekte über das Objekt `parameters` steuern.

```python
# Width of a single module (the smallest bar)
generator.parameters.barcode.x_dimension = 2   # 2 pixels per module

# Height of the bars (for linear barcodes)
generator.parameters.barcode.bar_height = 50  # 50 pixels tall

# Optional: add quiet zone (margin) if required by a scanner
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10   # 10 pixels margin on each side
```

*Tipp*: Wenn Sie planen, den Barcode zu drucken, erhöhen Sie `x_dimension` und `bar_height` proportional, um die Lesbarkeit bei der gewünschten DPI zu erhalten.

## Schritt 5: Speichern des Barcode‑Bildes

Zum Schluss schreiben Sie das erzeugte Bild in eine Datei. Aspose.Barcode unterstützt PNG, JPEG, BMP und viele weitere Formate.

```python
output_path = "output/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

Stellen Sie sicher, dass der Ordner `output` existiert oder erstellen Sie ihn mit `os.makedirs("output", exist_ok=True)`, bevor Sie `save` aufrufen.

### Erwartetes Ergebnis

Wenn Sie `extended_codetext.png` öffnen, sollten Sie einen Code 128‑Barcode sehen, der die numerische Zeichenkette `1234567890` gefolgt von den chinesischen Zeichen „特殊字符“ kodiert. Das Scannen des Barcodes mit einem modernen Scanner, der ECI respektiert, liefert die ursprüngliche gemischte Zeichenkette zurück.

![Barcode erzeugt mit dem Beispiel zur Barcode-Generierung](https://example.com/images/barcode-sample.png){: .align-center alt="Barcode erzeugt mit dem Beispiel zur Barcode-Generierung"}

## Häufige Fragen und Sonderfälle

### Was tun, wenn ich einen anderen Zeichensatz benötige?

Wählen Sie den passenden ECI‑Wert aus der ISO/IEC 18004‑Tabelle. Beispielsweise steht ECI 27 für ISO‑8859‑1 (Latin‑1). Ersetzen Sie die numerische Kennung in `add_eci_codetext` entsprechend.

### Kann ich mehr als einen ECI‑Block einbetten?

Ja. Rufen Sie `add_eci_codetext` mehrfach auf. Der Builder fügt die notwendigen ECI‑Umschaltcodes zwischen den Blöcken ein und bewahrt die Reihenfolge, in der Sie sie hinzufügen.

### Unterstützt der Generator QR‑Codes mit ECI?

Absolut. Ersetzen Sie `barcode.Symbology.CODE_128` durch `barcode.Symbology.QR` und passen Sie ggf. QR‑spezifische Parameter (z. B. Fehlerschutzniveau) über `generator.parameters.qr` an.

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorLevel.H
```

### Wie gehe ich mit sehr langen Datenzeichenketten um?

Für lineare Barcodes wie Code 128 liegt die maximale Länge bei etwa 80 Zeichen, wenn erweiterter Codetext verwendet wird. Überschreiten Sie diesen Wert, sollten Sie zu einer zweidimensionalen Symbolik wie QR oder Data Matrix wechseln, die Tausende von Zeichen speichern kann.

## Vollständiges, ausführbares Skript

Unten finden Sie das komplette Programm, das Sie in eine Datei namens `generate_extended_barcode.py` kopieren und direkt ausführen können.

```python
import os
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# ------------------------------------------------------------------
# Optional: print library version – useful for troubleshooting
# ------------------------------------------------------------------
ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)

# ------------------------------------------------------------------
# Build extended codetext: plain numbers + Chinese characters (ECI 26)
# ------------------------------------------------------------------
builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using UTF‑8
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)

# ------------------------------------------------------------------
# Create a Code128 generator – supports the extended codetext format
# ------------------------------------------------------------------
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,
    extended_codetext
)

# ------------------------------------------------------------------
# Customize appearance (size, quiet zone, etc.)
# ------------------------------------------------------------------
generator.parameters.barcode.x_dimension = 2
generator.parameters.barcode.bar_height = 50
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10

# ------------------------------------------------------------------
# Ensure output directory exists and save the image
# ------------------------------------------------------------------
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)
output_path = os.path.join(output_dir, "extended


## Was sollten Sie als Nächstes lernen?


Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in dieser Anleitung gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Code‑Beispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, weitere API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [Wie man ein Barcode‑Bild mit zusätzlicher Raum‑Anpassung unter Verwendung von Aspose.BarCode erzeugt](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [Wie man ein Barcode‑Bild in Java mit Aspose.BarCode erzeugt](/barcode/english/java/barcode-rendering-techniques/)
- [Wie man einen DataMatrix‑Barcode mit Aspose.BarCode für .NET erzeugt](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
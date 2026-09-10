---
category: general
date: 2026-09-10
description: Kodieren Sie Nicht‑ASCII‑Zeichen in einem QR‑Code und speichern Sie das
  QR‑Code‑Bild mit einem einfachen Python‑Builder. Folgen Sie einer Schritt‑für‑Schritt‑Anleitung
  mit ExtCodetextBuilder und BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- encode non ascii characters
- save qr code image
- extended codetext builder
- eci encoding python
- barcode generation python
language: de
lastmod: 2026-09-10
og_description: Kodieren Sie Nicht‑ASCII‑Zeichen in einem QR‑Code und speichern Sie
  das QR‑Code‑Bild mit Python. Dieses Tutorial zeigt, wie man erweiterten Codetext
  erstellt, einen QR‑Code generiert und das Bild speichert.
og_image_alt: Diagram showing encode non ASCII characters in QR code and save QR code
  image workflow
og_title: Nicht‑ASCII‑Zeichen im QR‑Code codieren und QR‑Code‑Bild speichern – Schritt‑für‑Schritt‑Python‑Anleitung
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Encode non ASCII characters in a QR code and save QR code image with
    a simple Python builder. Follow a step‑by‑step guide using ExtCodetextBuilder
    and BarcodeGenerator.
  headline: Encode non ASCII characters in QR code and save QR code image
  type: TechArticle
tags:
- barcode
- QR code
- Python
title: Nicht‑ASCII‑Zeichen im QR‑Code kodieren und QR‑Code‑Bild speichern
url: /de/python/general/encode-non-ascii-characters-in-qr-code-and-save-qr-code-imag/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kodieren von Nicht‑ASCII‑Zeichen in QR‑Code und QR‑Code‑Bild speichern

Wenn Sie **nicht‑ASCII‑Zeichen kodieren** in einem QR‑Code müssen, zeigt Ihnen diese Anleitung genau, wie Sie das tun und dann das **QR‑Code‑Bild speichern** auf die Festplatte. Egal, ob Sie russische, chinesische oder Emoji‑Daten verarbeiten, lässt der ExtCodetextBuilder Sie Klartext und ECI‑kodierte Segmente mischen, ohne manuell mit Bytes zu hantieren.

Sie lernen, wie man einen erweiterten Codetext‑String erstellt, einen QR‑Code generiert, der diesen String versteht, und schließlich das Barcode‑Bild in eine Datei schreibt. Die Anleitung setzt grundlegende Python‑Kenntnisse voraus und dass Sie das `barcode`‑SDK installiert haben.

## Voraussetzungen

* Python 3.8+ installiert.
* Das `barcode`‑Python‑Paket (oder das entsprechende SDK), das `ExtCodetextBuilder`, `CodetextEncodingType` und `BarcodeGenerator` bereitstellt.
* Schreibberechtigung für das Verzeichnis, in dem Sie das **QR‑Code‑Bild speichern** möchten.

Sie können das SDK mit pip installieren (ersetzen Sie `barcode-sdk` durch den tatsächlichen Paketnamen):

```bash
pip install barcode-sdk
```

## Schritt 1: Erstellen eines erweiterten Codetext‑Builders

Der erste Schritt besteht darin, `ExtCodetextBuilder` zu instanziieren. Dieses Objekt sammelt mehrere Textsegmente und erzeugt einen einzelnen String, den die QR‑Code‑Symbolik interpretieren kann.

```python
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Initialize the builder that will hold all text parts
ext_builder = ExtCodetextBuilder()
```

*Warum das wichtig ist*: QR‑Codes unterstützen **erweiterten Codetext**, was bedeutet, dass Sie mehrere Kodierungsmodi (Klartext, ECI usw.) in einem Barcode einbetten können. Der Builder abstrahiert die Low‑Level‑Formatierung, die von der QR‑Spezifikation verlangt wird.

## Schritt 2: Einen Klartext‑Abschnitt hinzufügen

Klartext ist der Standardmodus und funktioniert für ASCII‑Zeichen. Wenn Sie ihn zuerst hinzufügen, erhalten Scanner, die ECI ignorieren, eine lesbare Rückfalloption.

```python
# Add simple ASCII text
ext_builder.add_plain_codetext("HelloWorld")
```

Wenn Sie diesen Schritt weglassen, würde der QR‑Code nur das ECI‑Segment enthalten, das einige ältere Leser möglicherweise nicht korrekt dekodieren.

## Schritt 3: Ein ECI‑kodiertes Segment für Nicht‑ASCII‑Zeichen hinzufügen

Um Zeichen außerhalb des ASCII‑Bereichs einzuschließen – wie Kyrillisch, Chinesisch oder Emojis – müssen Sie eine ECI‑Kodierung (Extended Channel Interpretation) angeben. Hier verwenden wir UTF‑8 für das russische Wort „Привет“.

```python
# Add a UTF‑8 encoded segment containing non‑ASCII characters
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")  # Russian “Hi”
```

*Warum das funktioniert*: Die QR‑Spezifikation definiert ECI‑Werte, die dem Scanner mitteilen, welcher Zeichensatz anzuwenden ist. Ohne den ECI‑Marker würden die Rohbytes als ISO‑8859‑1 interpretiert, was zu fehlerhafter Ausgabe führt.

## Schritt 4: Den kombinierten erweiterten Codetext‑String abrufen

Nachdem Sie alle gewünschten Segmente hinzugefügt haben, rufen Sie `get_extended_codetext()` auf, um den finalen String zu erhalten, den der Barcode‑Generator erwartet.

```python
# Combine all parts into one extended codetext string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

Der ausgegebene Wert sieht aus wie eine Reihe von Steuerzeichen, gefolgt vom eigentlichen Text, aber Sie müssen ihn nie manuell parsen.

## Schritt 5: Einen QR‑Code mit dem erweiterten Codetext generieren

Erstellen Sie jetzt einen `BarcodeGenerator`, setzen Sie die Symbolik auf QR (die einzige gängige 2‑D‑Symbolik, die erweiterten Codetext unterstützt) und übergeben Sie den kombinierten String.

```python
# Initialize the QR generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)          # QR supports extended codetext
qr_generator.set_code_text(extended_codetext)
```

*Tipp*: Wenn Sie denselben Vorgang mit Code‑128 oder DataMatrix versuchen, wird das SDK eine Ausnahme auslösen, da diese Formate ECI‑Marker nicht interpretieren können.

## Schritt 6: Das QR‑Code‑Bild speichern

Schließlich schreiben Sie den Barcode in eine PNG‑Datei. Hier **speichern Sie das QR‑Code‑Bild** zur späteren Verwendung.

```python
output_path = "output/qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

Stellen Sie sicher, dass der Ordner `output` existiert, oder erstellen Sie ihn mit `os.makedirs('output', exist_ok=True)`, bevor Sie `save` aufrufen.

### Vollständiges ausführbares Beispiel

Wenn Sie alle Schritte zusammenführen, erhalten Sie ein eigenständiges Skript, das Sie sofort ausführen können:

```python
import os
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Ensure the output directory exists
os.makedirs("output", exist_ok=True)

# 1️⃣ Create the builder
ext_builder = ExtCodetextBuilder()

# 2️⃣ Add plain ASCII text
ext_builder.add_plain_codetext("HelloWorld")

# 3️⃣ Add UTF‑8 encoded non‑ASCII text (Russian)
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")

# 4️⃣ Retrieve the combined string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 5️⃣ Generate QR code
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)
qr_generator.set_code_text(extended_codetext)

# 6️⃣ Save the image
output_file = "output/qr_extended.png"
qr_generator.save(output_file)
print(f"QR code saved to {output_file}")
```

**Erwartete Ausgabe** (Konsole):

```
Extended codetext: <binary representation showing ECI markers>
QR code saved to output/qr_extended.png
```

Öffnen Sie `qr_extended.png` mit einem beliebigen QR‑Scanner, wird `HelloWorldПривет` angezeigt. Scanner, die ECI verstehen, rendern die kyrillischen Zeichen korrekt; andere zeigen nur den ASCII‑Teil.

## Häufige Fragen & Randfälle

| Frage | Antwort |
|----------|--------|
| *Kann ich andere Kodierungen wie Shift‑JIS verwenden?* | Ja. Ersetzen Sie `CodetextEncodingType.UTF_8` durch `CodetextEncodingType.SHIFT_JIS` und geben Sie den entsprechenden Text an. |
| *Was ist, wenn die kombinierten Daten die QR‑Kapazität überschreiten?* | QR‑Codes haben Versionsgrenzen (bis zu 177 × 177 Module). Wenn der Builder eine Größen‑Ausnahme wirft, erhöhen Sie entweder das Fehlerkorrektur‑Level oder teilen Sie die Daten auf mehrere QR‑Codes auf. |
| *Muss ich eine bestimmte QR‑Version festlegen?* | Das SDK wählt automatisch die kleinste Version, die zu den Daten passt. Sie können bei Bedarf eine Version mit `qr_generator.set_qr_version(10)` erzwingen. |
| *Wird das Bild transparent sein?* | Standardmäßig schreibt das SDK ein PNG mit weißem Hintergrund. Verwenden Sie `qr_generator.set_background_color(Color.Transparent)` vor `save`, wenn Sie Transparenz benötigen. |

## Fazit

In diesem Tutorial haben Sie gelernt, wie man **nicht‑ASCII‑Zeichen kodiert** in einem QR‑Code mithilfe des `ExtCodetextBuilder` und anschließend das **QR‑Code‑Bild speichert** mit dem `BarcodeGenerator`. Der Prozess beinhaltet das Erstellen eines erweiterten Codetext‑Strings, das Hinzufügen von Klartext‑ und ECI‑kodierten Segmenten, das Generieren der QR‑Symbolik und schließlich das Schreiben der Bilddatei.

Ab hier können Sie Folgendes erkunden:

* Weitere ECI‑Segmente hinzufügen (verschiedene Sprachen oder Emojis).
* QR‑Fehlerkorrektur‑Level für höhere Zuverlässigkeit anpassen.
* Das erzeugte PNG in PDFs oder Webseiten einbetten.

Viel Spaß beim Programmieren und beim Erstellen mehrsprachiger QR‑Codes!

## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige funktionierende Code‑Beispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, weitere API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [Wie man QR‑Code‑Bild in Python mit Aspose.Barcode generiert – Vollständige Anleitung](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Code128‑Barcode mit Aspose.Barcode Python generieren – Vollständige Anleitung](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [Produktnamen mit Python‑Barcode‑Bibliothek anzeigen – Schritt‑für‑Schritt‑Anleitung](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
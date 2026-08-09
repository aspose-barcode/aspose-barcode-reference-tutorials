---
category: general
date: 2026-08-09
description: Erstellen Sie einen QR‑Barcode in Python mit Aspose.BarCode. Erfahren
  Sie, wie Sie erweiterten Codetext erstellen, das Aussehen anpassen und das Bild
  speichern – alles in einem Tutorial.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create QR barcode
- Aspose.BarCode Python
- extended codetext QR
- QR code generation Python
- barcode visual customization
language: de
lastmod: 2026-08-09
og_description: Erstellen Sie einen QR-Barcode in Python mit Aspose.BarCode. Dieser
  Leitfaden zeigt, wie man erweiterten Codetext erstellt, visuelle Parameter festlegt
  und das Bild exportiert.
og_image_alt: Screenshot of a generated QR barcode created with Aspose.BarCode in
  Python
og_title: QR-Barcode mit Aspose.BarCode in Python erstellen – vollständiges Codebeispiel
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  headline: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  type: TechArticle
- description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  name: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  steps:
  - name: Common variations
    text: '- **Multiple ECI segments:** Call `add_eci_codetext` multiple times to
      mix several languages. - **Different ECI identifiers:** Use `27` for ISO‑8859‑1,
      `28` for ISO‑8859‑2, etc., depending on your target encoding.'
  - name: Edge case handling
    text: '- **High‑density data:** If the encoded data is large, you may need to
      increase `x_dimension` or choose a higher error‑correction level (via `qr_generator.parameters.qr.error_correction_level`).
      - **Transparent background:** Set `qr_generator.parameters.barcode.bg_color
      = Color.Transparent` for PNGs'
  - name: Verifying the result
    text: 'Open the saved file in any image viewer. You should see a QR code that,
      when scanned, returns the combined string:'
  type: HowTo
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: QR-Barcode mit Aspose.BarCode in Python erstellen – Schritt‑für‑Schritt‑Anleitung
url: /de/python/general/create-qr-barcode-with-aspose-barcode-in-python-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# QR-Barcode mit Aspose.BarCode in Python erstellen – Schritt‑für‑Schritt‑Anleitung

Wenn Sie in Python **einen QR‑Barcode** erstellen müssen, führt Sie dieses Tutorial durch den gesamten Prozess mit der Aspose.BarCode‑Bibliothek. Egal, ob Sie Produkt‑IDs, mehrsprachigen Text oder benutzerdefinierte Daten codieren, Sie sehen, wie Sie einen erweiterten Codetext erstellen, visuelle Einstellungen anpassen und das endgültige Bild in einem einzigen, ausführbaren Skript speichern.

Das Beispiel zeigt außerdem, wie die Bibliotheksversion angezeigt wird, was Ihnen hilft zu überprüfen, dass Sie eine kompatible Version verwenden. Am Ende dieser Anleitung haben Sie ein einsatzbereites QR‑Barcode‑Bild und ein klares Verständnis jeder Konfigurationsoption.

## Voraussetzungen

- Python 3.8+ installiert.
- `aspose-barcode`‑Paket (Installation über `pip install aspose-barcode`).
- Grundlegende Kenntnisse der Python‑Syntax.
- Schreibberechtigung für das Ausgabeverzeichnis, in dem die PNG‑Datei gespeichert wird.

> **Pro Tipp:** Verwenden Sie eine virtuelle Umgebung, um Versionskonflikte mit anderen Projekten zu vermeiden.

## Schritt 1: Überprüfen der Aspose.BarCode‑Bibliotheksversion

Das Anzeigen der Bibliotheksversion stellt sicher, dass Sie eine Version verwenden, die erweiterten Codetext und QR‑Codierung unterstützt.

```python
from asposebarcode import BuildVersionInfo

# Show the current Aspose.BarCode version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)
```

**Warum das wichtig ist:**  
Ältere Versionen können die für gemischte Plain‑ und ECI‑Segmente erforderliche Klasse `ExtCodetextBuilder` nicht enthalten. Die Versionsbestätigung verhindert Laufzeitfehler später im Workflow.

## Schritt 2: Erstellen eines erweiterten Codetext‑Strings

Ein erweiterter Codetext ermöglicht die Kombination von einfachem ASCII‑Daten mit Unicode‑(ECI‑)Segmenten, was für mehrsprachige QR‑Codes unerlässlich ist.

```python
from asposebarcode import ExtCodetextBuilder

# Initialize the builder
ext_builder = ExtCodetextBuilder()

# Add a plain segment – typically a product ID or numeric code
ext_builder.add_plain_codetext("ABC12345")

# Add an ECI segment – here we embed Japanese greeting "こんにちは"
# 26 is the ECI identifier for UTF‑8 encoding
ext_builder.add_eci_codetext(26, "こんにちは")

# Retrieve the full extended codetext that the QR generator will use
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")
```

**Warum das wichtig ist:**  
Die Methode `add_plain_codetext` speichert Daten als Standard‑ASCII, während `add_eci_codetext` einen Unicode‑Block mit dem entsprechenden ECI‑Bezeichner versieht. Dieser Ansatz stellt sicher, dass QR‑Scanner den japanischen Text korrekt interpretieren und keine fehlerhaften Zeichen erzeugen.

### Häufige Variationen

- **Mehrere ECI‑Segmente:** Rufen Sie `add_eci_codetext` mehrmals auf, um mehrere Sprachen zu mischen.
- **Verschiedene ECI‑Kennungen:** Verwenden Sie `27` für ISO‑8859‑1, `28` für ISO‑8859‑2 usw., je nach gewünschter Zielcodierung.

## Schritt 3: QR‑Barcode mit dem erweiterten Codetext erzeugen

Da wir nun einen korrekt formatierten String haben, können wir den QR‑Code erstellen.

```python
from asposebarcode import BarCodeGenerator, EncodeTypes, BarCodeImageFormat

# Create the QR generator with the extended codetext
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)
```

**Warum das wichtig ist:**  
`EncodeTypes.QR` weist Aspose.BarCode an, die QR‑Symbologie zu verwenden. Das direkte Übergeben des `extended_codetext` verknüpft die gemischten Daten mit der QR‑Matrix und bewahrt sowohl den Plain‑ als auch den Unicode‑Teil.

## Schritt 4: Visuelle Darstellung anpassen (optional, aber empfohlen)

Die Feinabstimmung der visuellen Parameter des Barcodes verbessert die Scan‑Zuverlässigkeit und entspricht den Markenrichtlinien.

```python
# Set module (pixel) size – larger values increase overall image size
qr_generator.parameters.barcode.x_dimension = 4      # each module = 4 pixels

# Set border thickness – a thin white border helps scanners isolate the QR code
qr_generator.parameters.barcode.border_width = 2    # 2-pixel border
```

**Warum das wichtig ist:**  
- **`x_dimension`** steuert die Größe jedes QR‑Moduls; zu klein kann auf Geräten mit niedriger Auflösung Lesefehler verursachen.  
- **`border_width`** fügt eine Ruhezone hinzu. Einige Scanner benötigen mindestens eine 4‑Modul‑Ruhezone; die Bibliothek fügt diese automatisch hinzu, Sie können sie jedoch zur zusätzlichen Sicherheit vergrößern.

### Behandlung von Randfällen

- **Daten hoher Dichte:** Wenn die codierten Daten groß sind, müssen Sie möglicherweise `x_dimension` erhöhen oder ein höheres Fehlerkorrektur‑Level wählen (über `qr_generator.parameters.qr.error_correction_level`).  
- **Transparenter Hintergrund:** Setzen Sie `qr_generator.parameters.barcode.bg_color = Color.Transparent` für PNGs mit Alphakanälen.

## Schritt 5: QR‑Barcode‑Bild speichern

Schließlich schreiben Sie das Bild in Ihrem bevorzugten Format auf die Festplatte.

```python
# Define output path – replace YOUR_DIRECTORY with an actual folder
output_file = "YOUR_DIRECTORY/extended_qr.png"

# Save as PNG; other formats include JPEG, BMP, GIF, TIFF
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

**Warum das wichtig ist:**  
Das Speichern als PNG bewahrt die verlustfreie Qualität, was ideal für QR‑Codes mit scharfen Kanten ist. Wenn Sie für eine Web‑Anwendung ein anderes Format benötigen, ändern Sie einfach die Aufzählung `BarCodeImageFormat`.

### Ergebnis überprüfen

Öffnen Sie die gespeicherte Datei in einem Bildbetrachter. Sie sollten einen QR‑Code sehen, der beim Scannen den kombinierten String zurückgibt:

```
ABC12345
こんにちは
```

Die meisten modernen QR‑Scanner‑Apps zeigen zuerst das Plain‑Segment an und rendern dann die japanische Begrüßung korrekt.

---

## Vollständiges ausführbares Skript

Kopieren Sie den gesamten Block unten in eine Datei mit dem Namen `create_qr_barcode.py` und führen Sie sie mit `python create_qr_barcode.py` aus. Passen Sie `YOUR_DIRECTORY` an einen beschreibbaren Ordner auf Ihrem Rechner an.

```python
# create_qr_barcode.py
from asposebarcode import (
    BuildVersionInfo,
    ExtCodetextBuilder,
    BarCodeGenerator,
    EncodeTypes,
    BarCodeImageFormat,
)

# 1️⃣ Display library version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)

# 2️⃣ Build extended codetext (plain + Japanese Unicode)
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC12345")
ext_builder.add_eci_codetext(26, "こんにちは")
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")

# 3️⃣ Create QR generator
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)

# 4️⃣ Optional visual tweaks
qr_generator.parameters.barcode.x_dimension = 4
qr_generator.parameters.barcode.border_width = 2

# 5️⃣ Save image
output_file = "YOUR_DIRECTORY/extended_qr.png"
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

Das Ausführen dieses Skripts gibt die Version, den erweiterten Codetext und eine Bestätigung aus, dass die PNG‑Datei erstellt wurde.

---

## Fazit

Sie wissen jetzt, wie Sie mit Aspose.BarCode in Python **QR‑Barcode**‑Bilder erstellen. Das Tutorial behandelte:

1. Überprüfen der Bibliotheksversion.  
2. Erstellen eines erweiterten Codetexts mit Plain‑ und ECI‑(Unicode‑)Segmenten.  
3. Generieren des QR‑Codes.  
4. Anpassen visueller Parameter wie Modulgröße und Randbreite.  
5. Speichern des finalen Bildes im PNG‑Format.

Ab hier können Sie Folgendes erkunden:

- Ändern der Fehlerkorrektur‑Levels (`qr_generator.parameters.qr.error_correction_level`).  
- Hinzufügen eines Logos oder Hintergrundbildes (`qr_generator.parameters.qr.logo`).  
- Exportieren in andere Formate wie SVG für skalierbare Web‑Grafiken.  
- Integration des Generators in einen Flask‑ oder Django‑Endpoint für die sofortige QR‑Erstellung.

Experimentieren Sie mit verschiedenen Datenpayloads und visuellen Einstellungen, um die Marken‑ und Scan‑Anforderungen Ihrer Anwendung zu erfüllen. Viel Spaß beim Coden!

## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige funktionierende Code‑Beispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, zusätzliche API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [Wie man erweiterten Dotcode‑Codetext mit Aspose.BarCode für .NET erstellt](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Barcode mit Aspose .NET erstellen – DataMatrix‑Codetext konfigurieren](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Wie man eine Barcode‑Ruhezone für ITF‑14 mit Aspose.BarCode für .NET erstellt](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
---
category: general
date: 2026-11-27
description: QR-Code in Python mit Aspose.Barcode generieren und lernen, wie man das
  Barcode‑Bild schnell auf die Festplatte speichert.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate QR barcode
- save barcode image
- Aspose.Barcode Python
- extended codetext QR
- barcode version information
language: de
lastmod: 2026-11-27
og_description: Erzeugen Sie QR‑Barcodes in Python mit Aspose.Barcode und speichern
  Sie das Barcode‑Bild sofort. Folgen Sie dem vollständigen Beispiel, um QR‑Codes
  zu erstellen, anzupassen und zu speichern.
og_image_alt: Screenshot of a generated QR barcode created with Python
og_title: QR-Code generieren und Bild mit Python speichern – Schritt‑für‑Schritt‑Anleitung
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Generate QR barcode in Python using Aspose.Barcode and learn how to
    save barcode image to disk quickly.
  headline: Generate QR barcode and save image with Python
  type: TechArticle
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: QR-Barcode generieren und Bild mit Python speichern
url: /de/python/general/generate-qr-barcode-and-save-image-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# QR‑Barcode generieren und Bild mit Python speichern

Wenn Sie in einer Python‑Anwendung **QR‑Barcode generieren** müssen, zeigt Ihnen dieser Leitfaden, wie Sie dies mit der Aspose.Barcode‑Bibliothek tun. Sie lernen außerdem die korrekte Vorgehensweise, **Barcode‑Bild zu speichern** in einem lokalen Ordner, Versionsdetails der Bibliothek abzurufen und erweiterte Codetext‑Segmente zu verarbeiten.

Das Erstellen von QR‑Codes ist eine gängige Anforderung für Ticketsysteme, mobile Zahlungen und Produktverfolgung. Am Ende dieses Tutorials verfügen Sie über ein einsatzbereites Skript, das eine QR‑Barcode‑Bilddatei erzeugt und Versionsinformationen zur Fehlersuche oder für Compliance‑Zwecke ausgibt.

## Voraussetzungen

* Python 3.8 oder neuer installiert.
* Das `aspose-barcode`‑Paket. Installieren Sie es mit `pip install aspose-barcode`.
* Schreibberechtigung für das Verzeichnis, in dem das Barcode‑Bild gespeichert wird.

Keine zusätzlichen externen Dienste sind erforderlich; der gesamte Vorgang läuft lokal.

## Schritt 1: Erstellen eines erweiterten Codetexts mit `ExtCodetextBuilder`

Erweiterter Codetext ermöglicht es, Klartext und ECI‑Segmente (Extended Channel Interpretation) in einem einzigen QR‑Code zu mischen. Dies ist nützlich, wenn Sie Zeichen aus verschiedenen Zeichensätzen einbetten müssen, z. B. das Euro‑Zeichen.

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# Create the builder instance
ext_builder = ExtCodetextBuilder()

# Add a plain text segment
ext_builder.add_plain_codetext("ABC123")

# Add an ECI segment that uses ISO‑IEC 8859‑1 (code page 3)
ext_builder.add_eci_codetext(3, "€123")
```

**Warum dieser Schritt wichtig ist:**  
`ExtCodetextBuilder` setzt die endgültige Zeichenkette zusammen, die der QR‑Encoder verarbeitet. Ohne den erweiterten Codetext würde der Barcode nur reine ASCII‑Zeichen enthalten und könnte keine lokalspezifischen Symbole darstellen.

## Schritt 2: Den kombinierten erweiterten Codetext‑String abrufen

```python
# Get the final extended codetext that will be encoded
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

Die Ausgabe sieht folgendermaßen aus:

```
Extended codetext: ABC123[ECI3]€123
```

Der in eckigen Klammern stehende Marker `[ECI3]` weist den QR‑Encoder an, für die folgenden Zeichen zum angegebenen Zeichensatz zu wechseln.

## Schritt 3: QR‑Barcode mit dem erweiterten Codetext generieren

```python
# Create a QR barcode generator with the extended codetext
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)
```

**Erklärung:**  
`BarcodeGenerator` erhält zwei Argumente: den Barcode‑Typ (`QR`) und die zu kodierenden Daten (`extended_codetext`). Der Generator bereitet alle internen Strukturen vor, die für das Rendern benötigt werden.

## Schritt 4: Das erzeugte Barcode‑Bild speichern

```python
# Define the output path – adjust the folder as needed
output_path = "output/qr_extended.png"

# Save the image in PNG format
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")
```

**Warum Sie diesen Ansatz verwenden sollten:**  
Ein Aufruf von `save` schreibt das Bild direkt auf die Festplatte, wobei das Format aus der Dateierweiterung abgeleitet wird. Die Methode unterstützt PNG, JPEG, BMP und TIFF und bietet Ihnen Flexibilität für verschiedene nachgelagerte Verbraucher.

### Überprüfung des gespeicherten Bildes

Öffnen Sie die Datei `output/qr_extended.png` mit einem beliebigen Bildbetrachter. Sie sollten einen QR‑Code sehen, der beim Scannen die Zeichenkette `ABC123€123` zurückgibt. Die meisten modernen mobilen QR‑Scanner verarbeiten das ECI‑Segment automatisch.

## Schritt 5: Abrufen von Aspose.BarCode‑Versionsinformationen (optional, aber nützlich)

Die genaue Version der Aspose.BarCode‑Bibliothek zu kennen, ist hilfreich, wenn Sie Fehler melden oder die Kompatibilität prüfen müssen.

```python
# Retrieve version details
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Typische Ausgabe:

```
Aspose.BarCode version:
  Assembly version : 23.9.0.0
  File version     : 23.9.0
  Product          : Aspose.BarCode for Python via .NET
  Release date     : 2023-09-15
```

## Vollständiges Skript – kopieren, einfügen und ausführen

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# 1️⃣ Build extended codetext
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC123")
ext_builder.add_eci_codetext(3, "€123")
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 2️⃣ Generate QR barcode
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)

# 3️⃣ Save barcode image
output_path = "output/qr_extended.png"
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")

# 4️⃣ Display version information
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Das Ausführen des Skripts erzeugt das QR‑Code‑Bild und gibt sowohl den erweiterten Codetext als auch die Versionsdetails in der Konsole aus.

## Häufige Varianten und Sonderfälle

| Situation | Empfohlene Anpassung |
|-----------|----------------------|
| **Different character set** | Ändern Sie den an `add_eci_codetext` übergebenen ECI‑Identifikator. Für UTF‑8 verwenden Sie `5`. |
| **Higher error correction** | Setzen Sie `barcode.parameters.barcode.qr_error_level = bc.QRErrorLevel.H` bevor Sie `save` aufrufen. |
| **Custom image size** | Verwenden Sie `barcode.parameters.image_width` und `barcode.parameters.image_height`, um die Pixelabmessungen zu steuern. |
| **Non‑PNG output** | Ändern Sie die Dateierweiterung in `output_path` zu `.jpg` oder `.bmp`. Die Bibliothek wählt automatisch den richtigen Encoder aus. |

## Pro‑Tipps

* **Erstellen Sie den Ausgabordner** programmgesteuert, falls er nicht existiert:

  ```python
  import os
  os.makedirs(os.path.dirname(output_path), exist_ok=True)
  ```

* **Validieren Sie den QR‑Code** nach der Erzeugung, indem Sie ihn mit `aspose.barcode.BarcodeReader` erneut einlesen. Dies stellt sicher, dass die kodierten Daten den Erwartungen entsprechen, insbesondere bei Verwendung von ECI‑Segmenten.

  ```python
  reader = bc.BarcodeReader(output_path, bc.DecodeType.QR)
  for result in reader.read():
      print("Decoded text:", result.code_text)
  ```

* **Performance‑Tipp** – Verwenden Sie eine einzelne `BarcodeGenerator`‑Instanz erneut, wenn Sie viele QR‑Codes in einer Schleife erzeugen müssen. Setzen Sie die Eigenschaft `code_text` zurück, anstatt bei jeder Iteration ein neues Objekt zu erstellen.

## Fazit

Sie wissen jetzt, wie man in Python mit Aspose.Barcode **QR‑Barcode generiert**, einen erweiterten Codetext erstellt, der Klartext‑ und ECI‑Segmente mischt, und **Barcode‑Bild** korrekt auf die Festplatte speichert. Das Skript zeigt zudem, wie man Versionsinformationen der Bibliothek zur Fehlersuche abruft.

Weitere Schritte, die Sie erkunden könnten, umfassen:

* Hinzufügen eines Logo‑Overlays oder benutzerdefinierter Farben zum QR‑Code.
* Einbetten des QR‑Barcodes direkt in PDFs mit Aspose.PDF.
* Automatisieren der Stapelerzeugung für große Datensätze.

Fühlen Sie sich frei, mit verschiedenen Daten‑Payloads, Fehlerkorrektur‑Stufen und Bildformaten zu experimentieren. Viel Spaß beim Coden!

## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Codebeispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, zusätzliche API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [Wie man QR‑Code‑Bild in Python mit Aspose.Barcode generiert – Vollständige Anleitung](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Wie man Code‑128‑Barcode generiert und Barcode‑Bild mit Aspose.BarCode speichert](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [Wie man DataMatrix‑Barcode in Python mit Aspose.BarCode generiert](/barcode/english/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
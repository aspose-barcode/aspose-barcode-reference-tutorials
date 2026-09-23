---
category: general
date: 2026-09-23
description: Erfahren Sie, wie Sie mit Aspose.BarCode in Python einen Code‑128‑Strichcode
  erzeugen und das Strichcode‑Bild speichern – Schritt‑für‑Schritt‑Anleitung.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate code 128 barcode
- save barcode image
- Aspose.BarCode Python
- extended codetext builder
- barcode PNG export
language: de
lastmod: 2026-09-23
og_description: Erzeugen Sie einen Code‑128‑Strichcode und speichern Sie das Strichcode‑Bild
  mit Aspose.BarCode in Python. Folgen Sie diesem vollständigen Beispiel, um den Strichcode
  zu erstellen, anzupassen und als PNG‑Datei zu exportieren.
og_image_alt: Python-generated Code 128 barcode saved as PNG image
og_title: Code‑128‑Barcode generieren und Barcode‑Bild speichern – Python‑Leitfaden
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to generate Code 128 barcode and save barcode image using
    Aspose.BarCode in Python – step‑by‑step guide.
  headline: How to generate Code 128 barcode and save barcode image with Aspose.BarCode
  type: TechArticle
tags:
- barcode
- Code 128
- Python
- Aspose
title: Wie man einen Code‑128‑Barcode generiert und das Barcode‑Bild mit Aspose.BarCode
  speichert
url: /de/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Code 128‑Strichcode generiert und das Strichcode‑Bild mit Aspose.BarCode speichert

Wenn Sie **Code 128‑Strichcode** erzeugen und **das Strichcode‑Bild** in einem Python‑Projekt speichern müssen, zeigt dieses Tutorial die genauen Schritte. Mit Aspose.BarCode’s `ExtCodetextBuilder` können Sie Klartext‑ und Unicode‑Segmente in einer einzigen Payload einbetten und das Ergebnis als PNG‑Datei rendern.

Sie erhalten ein vollständiges, ausführbares Skript, eine Erklärung jeder Zeile und Tipps für häufige Fallstricke wie die Handhabung von ECI‑Kodierung oder die Wahl des richtigen Ausgabeverzeichnisses. Keine externe Dokumentation nötig – einfach kopieren, einfügen und ausführen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

* Python 3.8+ installiert.
* Das Paket `aspose.barcode` (Installation mit `pip install aspose-barcode`).
* Schreibrechte für das Verzeichnis, in dem das PNG gespeichert wird.

Der Code funktioniert mit jeder von Aspose.BarCode unterstützten Symbolik, aber das Beispiel konzentriert sich auf **Code 128**, da es alphanumerische Daten effizient kodiert und erweiterte Zeichensätze unterstützt.

## Schritt 1: Importieren der erforderlichen Klassen

```python
import barcode                     # Core Aspose.BarCode namespace
from barcode import BarCodeWriter, BarCodeEncodeMode, BarCodeImageFormat
from barcode import ExtCodetextBuilder, BuildVersionInfo
```

*Warum dieser Schritt?* Durch das Importieren der Klassen erhalten Sie Zugriff auf den Builder für erweiterten Codetext, den Writer, der das Bild erstellt, und den Versions‑Helper, der beim Debuggen von Bibliotheks‑Updates nützlich sein kann.

## Schritt 2: Erstellen des erweiterten Codetexts

```python
# Create a builder for extended codetext
builder = ExtCodetextBuilder()

# Add plain text (no ECI) – this part is simple ASCII
builder.add_plain_codetext("ABC123")

# Add a Unicode segment with ECI 0x03 (UTF‑8). The word “Пример” means “Example” in Russian.
builder.add_eci_codetext(0x03, "Пример")

# Retrieve the full extended codetext string
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

Der `ExtCodetextBuilder` ermöglicht das Mischen von einfachem ASCII‑ und Unicode‑Daten in einer einzigen Strichcode‑Payload. Das ECI‑Byte (Extended Channel Interpretation) `0x03` teilt dem Scanner mit, dass die folgenden Bytes UTF‑8‑kodiert sind – das ist entscheidend für Sprachen wie Russisch, Chinesisch oder Arabisch.

## Schritt 3: Konfigurieren des Barcode‑Writers für Code 128

```python
writer = BarCodeWriter()
writer.encode_type = BarCodeEncodeMode.CODE_128   # Choose Code 128 symbology
writer.code_text = extended_codetext
```

Durch das Setzen von `encode_type` auf `CODE_128` wird der Writer angewiesen, einen **Code 128‑Strichcode** zu rendern. Die Eigenschaft `code_text` erhält den im vorherigen Schritt erstellten erweiterten String.

## Schritt 4: Speichern des Barcode‑Bildes als PNG

```python
output_path = "YOUR_DIRECTORY/extended_codetext.png"
writer.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode image saved to {output_path}")
```

Die Methode `save` schreibt den Strichcode in eine Datei. Die Verwendung von `BarCodeImageFormat.PNG` sorgt für verlustfreie Kompression und breite Kompatibilität mit Web‑ und Mobilanwendungen.

## Schritt 5 (optional): Überprüfen der Aspose.BarCode‑Bibliotheksversion

```python
version_info = BuildVersionInfo()
print("Assembly version :", version_info.ASSEMBLY_VERSION)
print("Product version   :", f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR}")
print("Release date      :", version_info.RELEASE_DATE)
```

Die genaue Bibliotheksversion zu kennen, hilft, wenn Sie Fehler melden oder das Verhalten über verschiedene Releases hinweg vergleichen müssen.

## Erwartete Ausgabe

Das Ausführen des Skripts erzeugt eine Konsolenausgabe ähnlich wie:

```
Extended codetext: ABC123[ECI=03]Пример
Assembly version : 23.12.0.0
Product version   : 23.12
Release date      : 2023-12-01
Barcode image saved to YOUR_DIRECTORY/extended_codetext.png
```

Das erzeugte PNG (`extended_codetext.png`) sieht folgendermaßen aus:

![Python-generated Code 128 barcode saved as PNG image](images/code128_extended.png)

*Das Bild zeigt einen Code 128‑Strichcode, der sowohl die ASCII‑Zeichenkette `ABC123` als auch das russische Wort „Пример“ kodiert.*

## Häufige Fragen und Sonderfall‑Behandlung

| Frage | Antwort |
|----------|--------|
| **Kann ich eine andere Symbolik verwenden?** | Ja. Ersetzen Sie `BarCodeEncodeMode.CODE_128` durch einen anderen unterstützten Modus wie `QR`, `EAN_13` oder `PDF_417`. |
| **Was, wenn mein Unicode‑Text Emojis enthält?** | Emojis sind ebenfalls UTF‑8‑Zeichen, sodass derselbe Aufruf `add_eci_codetext` funktioniert. Stellen Sie sicher, dass der Ziel‑Scanner das von Ihnen verwendete ECI unterstützt. |
| **Wie ändere ich die Bildgröße?** | Setzen Sie `writer.x_dimension` und `writer.bar_height` bevor Sie `save` aufrufen. |
| **Welchen Ordner soll ich für `output_path` verwenden?** | Einen beliebigen Ordner, in den der Python‑Prozess schreiben darf. Nutzen Sie `os.makedirs` mit `exist_ok=True`, um ihn automatisch zu erstellen. |

## Pro‑Tipps

* **Vermeiden Sie hartkodierte Pfade.** Verwenden Sie `os.path.join` und `Path` aus dem `pathlib`‑Modul für plattformübergreifende Kompatibilität.
* **Validieren Sie den Strichcode.** Nach dem Speichern können Sie das Bild mit `barcode.BarCodeReader` erneut einlesen, um zu bestätigen, dass der kodierte Text mit `extended_codetext` übereinstimmt.
* **Performance‑Tipp.** Wenn Sie viele Strichcodes in einer Schleife erzeugen, verwenden Sie eine einzige `BarCodeWriter`‑Instanz und aktualisieren Sie nur `code_text` in jeder Iteration.

## Fazit

Sie wissen jetzt, wie Sie **Code 128‑Strichcode** mit gemischten ASCII‑ und Unicode‑Daten erzeugen und **das Strichcode‑Bild** als PNG mit Aspose.BarCode in Python speichern. Das vollständige Skript deckt das Erstellen des erweiterten Codetexts, die Konfiguration des Writers, den Export des Bildes und die Überprüfung der Bibliotheksversion ab.

Ab hier können Sie weiter erkunden:

* Hinzufügen von Vorder‑/Hintergrundfarben (`writer.back_color`, `writer.fore_color`).
* Einbetten des Strichcodes in PDFs mit `Aspose.PDF`.
* Verwenden der Klasse `BarCodeReader`, um das gespeicherte Bild zu dekodieren und den Inhalt automatisch zu verifizieren.

Viel Spaß beim Coden und experimentieren Sie gern mit anderen Symboliken und Bildformaten!

## Was sollten Sie als Nächstes lernen?


Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Code‑Beispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, weitere API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [Generate Code128 Barcode with Aspose.Barcode Python – Full Guide](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [How to generate barcode in Python – complete step‑by‑step guide](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
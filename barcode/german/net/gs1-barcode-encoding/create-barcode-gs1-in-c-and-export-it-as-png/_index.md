---
category: general
date: 2026-09-29
description: Erstellen Sie einen GS1‑Barcode in C# und generieren Sie Barcode‑PNG‑Bilder
  mit BarcodeGenerator. Befolgen Sie eine Schritt‑für‑Schritt‑Anleitung, um das Barcode‑Bild
  effizient zu exportieren.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode gs1
- generate barcode png
- barcode generator c#
- how to generate barcode
- export barcode image
language: de
lastmod: 2026-09-29
og_description: Erstellen Sie einen GS1-Barcode in C# und generieren Sie Barcode‑PNG‑Dateien
  mit BarcodeGenerator. Folgen Sie dieser umfassenden Anleitung, um das Barcode‑Bild
  schnell zu exportieren.
og_image_alt: Generated GS1 MicroPDF417 barcode saved as a PNG file
og_title: GS1-Barcode in C# erstellen – in Minuten als PNG exportieren
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create barcode GS1 in C# and generate barcode PNG images using BarcodeGenerator.
    Follow a step‑by‑step guide to export barcode image efficiently.
  headline: Create barcode GS1 in C# and export it as PNG
  type: TechArticle
tags:
- barcode
- C#
- GS1
- PNG
- Aspose
title: GS1-Barcode in C# erstellen und als PNG exportieren
url: /de/net/gs1-barcode-encoding/create-barcode-gs1-in-c-and-export-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GS1‑Barcode in C# erstellen und als PNG exportieren

Wenn Sie einen **GS1‑Barcode** in einer .NET‑Anwendung erstellen müssen, zeigt Ihnen dieser Leitfaden genau, wie das geht. Sie sehen eine kompakte Lösung, die ein Barcode‑PNG‑Bild erzeugt und das Barcode‑Bild auf die Festplatte exportiert, alles mit der Aspose.BarCode `BarcodeGenerator`‑Klasse.

Das Erzeugen eines GS1‑Barcodes ist eine häufige Anforderung für Inventar‑, Versand‑ und Point‑of‑Sale‑Systeme. Am Ende dieses Tutorials können Sie ein kleines C#‑Programm schreiben, das einen GS1‑konformen MicroPDF417‑Barcode erstellt und ihn als hochqualitatives PNG‑Datei speichert.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

* **.NET 6** (oder eine neuere .NET‑Version) installiert.
* **Visual Studio 2022** oder eine IDE, die C# unterstützt.
* Das **Aspose.BarCode for .NET** NuGet‑Paket (`Aspose.BarCode`) – es stellt die in den Beispielen verwendete `BarcodeGenerator`‑API bereit.
* Grundlegende Kenntnisse der C#‑Syntax.

> **Pro‑Tipp:** Verwenden Sie die kostenlose Community‑Edition von Aspose.BarCode beim Experimentieren; die Vollversion entfernt alle Evaluations‑Wasserzeichen.

## Schritt 1 – GS1‑Barcode mit BarcodeGenerator erstellen

Das Erste, was Sie benötigen, ist die Instanzierung des `BarcodeGenerator` für das *MicroPDF417*‑Format und das Übergeben eines GS1‑Datenstrings. Die GS1‑Application‑Identifiers (AIs) werden in Klammern gesetzt, z. B. `(01)` für GTIN‑14 und `(21)` für eine Seriennummer.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// GS1 data: (01) – GTIN‑14, (21) – serial number
string gs1Data = "(01)12345678901234(21)ABC123";

// Initialise the generator for MicroPDF417 (GS1 compatible)
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);
```

**Warum das wichtig ist:**  
`EncodeTypes.MicroPdf417` behandelt die Eingabe automatisch als GS1‑Daten, wenn der String gültige AIs enthält. Dadurch entspricht der erzeugte Barcode der GS1‑Spezifikation, ohne dass zusätzliche Konfiguration nötig ist.

## Schritt 2 – Barcode‑Abmessungen für optimale Größe festlegen

Die visuelle Größe eines Barcodes wird durch seine **X‑Dimension** (die Breite eines einzelnen Moduls) gesteuert. Durch Anpassen von `XDimension.Pixels` können Sie die endgültige Bildgröße feinjustieren und gleichzeitig die Lesbarkeit erhalten.

```csharp
// Set the module width to 2 pixels – a good balance for screen and print
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Wie man Barcode‑PNG generiert** – Die X‑Dimension beeinflusst nicht die codierten Daten; sie ändert nur die physischen Abmessungen des erzeugten Bildes. Wenn Sie einen größeren Barcode für hochauflösenden Druck benötigen, erhöhen Sie diesen Wert (z. B. `3` oder `4`).

## Schritt 3 – Barcode‑PNG generieren und Barcode‑Bild exportieren

Jetzt können Sie den Barcode rendern und in eine PNG‑Datei schreiben. Die `Save`‑Methode nimmt den Zielpfad und das gewünschte Bildformat entgegen.

```csharp
// Define the output folder (ensure it exists)
string outputFolder = Path.Combine(Environment.CurrentDirectory, "output");
Directory.CreateDirectory(outputFolder);

// Export the barcode image as PNG
string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
generator.Save(pngPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode image saved to: {pngPath}");
```

**Was im Hintergrund passiert:**  
`BarcodeGenerator.Save` rastert den Barcode in ein Bitmap, wendet die zuvor festgelegte X‑Dimension an und kodiert das Bitmap als PNG‑Datei. Die resultierende Datei kann direkt in Webseiten verwendet, auf Etiketten gedruckt oder in PDFs eingebettet werden.

## Vollständiges Quellcode‑Beispiel

Unten finden Sie eine komplette, eigenständige Konsolenanwendung, die Sie kopieren, einfügen und ausführen können. Sie demonstriert **wie man Barcode‑PNG**‑Dateien erzeugt, **Barcode‑Bild exportiert** und enthält grundlegende Fehlerbehandlung.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Gs1BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // 1️⃣ Initialise the barcode generator for GS1 MicroPDF417
                string gs1Data = "(01)12345678901234(21)ABC123";
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.MicroPdf417, gs1Data);

                // 2️⃣ Adjust X‑dimension to control the visual size
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // 3️⃣ Prepare output folder
                string outputFolder = Path.Combine(
                    Environment.CurrentDirectory, "output");
                Directory.CreateDirectory(outputFolder);

                // 4️⃣ Save the barcode as PNG (export barcode image)
                string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
                generator.Save(pngPath, BarCodeImageFormat.Png);

                Console.WriteLine($"✅ Barcode created and saved as PNG:");
                Console.WriteLine(pngPath);
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Error: {ex.Message}");
            }
        }
    }
}
```

### Erwartete Ausgabe

Wenn Sie das Programm ausführen, sollten Sie Folgendes sehen:

```
✅ Barcode created and saved as PNG:
C:\Path\To\Your\App\output\GS1MicroPdf417.png
```

Das Öffnen der PNG‑Datei zeigt einen klaren **GS1 MicroPDF417**‑Barcode, der die GTIN‑14 `12345678901234` und die Seriennummer `ABC123` kodiert. Das Scannen mit einem beliebigen GS1‑kompatiblen Scanner liefert den ursprünglichen Datenstring zurück.

## Häufige Fallstricke und bewährte Vorgehensweisen

| Problem | Warum es passiert | Wie man es vermeidet |
|---------|-------------------|----------------------|
| **Falsche AI‑Formatierung** | Fehlende Klammern oder falsche Reihenfolge machen den Barcode nicht zu GS1. | Immer jede AI in Klammern setzen, z. B. `(01)`. |
| **Zu kleine X‑Dimension** | Der Barcode wird auf niedrigauflösenden Geräten unlesbar. | `XDimension.Pixels` ≥ 2 für die meisten Drucker beibehalten; für hochauflösende Ausgaben erhöhen. |
| **Ausgabeordner existiert nicht** | `Save` wirft `DirectoryNotFoundException`. | `Directory.CreateDirectory` vor dem Aufruf von `Save` verwenden. |
| **Falscher EncodeType verwendet** | Einige Typen (z. B. `Code128`) unterstützen GS1‑Daten nicht von Haus aus. | `EncodeTypes.MicroPdf417` oder einen anderen GS1‑kompatiblen Typ wählen. |
| **Fehlende NuGet‑Referenz** | Compile‑Zeit‑Fehler wie `The type or namespace name 'Aspose' could not be found`. | Das `Aspose.BarCode`‑Paket über NuGet installieren. |

## Beispiel erweitern

* **Verschiedene Bildformate** – Ersetzen Sie `BarCodeImageFormat.Png` durch `Jpeg`, `Gif` oder `Bmp`, wenn Sie ein anderes Format benötigen.  
* **Hochauflösende Ausgabe** – Setzen Sie `generator.Parameters.ImageResolution.DpiX` und `DpiY` vor dem Speichern.  
* **Einbettung in PDF** – Verwenden Sie `Aspose.Pdf`, um das PNG in eine PDF‑Rechnung oder ein Etikett einzufügen.

## Fazit

Sie wissen jetzt, wie man **GS1‑Barcode in C#** mit der Aspose.BarCode `BarcodeGenerator` **Barcode‑PNG generiert** und das **Barcode‑Bild** in das Dateisystem exportiert. Der Leitfaden hat jeden Schritt behandelt – vom Initialisieren des Generators mit GS1‑Daten, über das Anpassen der X‑Dimension bis zum Speichern der finalen PNG‑Datei – und häufige Fehler sowie Erweiterungsideen aufgezeigt.

Experimentieren Sie gern mit anderen GS1‑Application‑Identifiers, verschiedenen Barcode‑Symbologien oder höherauflösenden Bildern. Sobald Sie diese Grundlagen beherrschen, wird das Erzeugen konformer Barcodes für Inventar, Versand oder Einzelhandel zu einem routinemäßigen Bestandteil Ihrer .NET‑Werkzeugkiste.

## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Codebeispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, weitere API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [GS1‑Barcode‑Bilder in C# erstellen – Wie man Barcode in C# schnell generiert](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [Barcode‑PNG in C# erstellen – Schritt‑für‑Schritt‑Anleitung](/barcode/english/python-java/general/create-barcode-png-in-c-step-by-step-guide/)
- [Barcode‑Bild in C# erstellen – vollständiger Programmierleitfaden](/barcode/english/python-java/general/create-barcode-image-in-c-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
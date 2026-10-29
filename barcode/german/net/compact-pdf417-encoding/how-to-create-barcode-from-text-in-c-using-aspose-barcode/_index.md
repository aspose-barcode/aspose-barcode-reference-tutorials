---
category: general
date: 2026-10-28
description: Erstellen Sie einen Barcode aus Text in C# mit Aspose.BarCode. Erfahren
  Sie, wie Sie ein PDF417‑Barcode‑Bild generieren, Spalten festlegen, die X‑Dimension
  anpassen und den kompakten Modus aktivieren.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate barcode c#
- generate pdf417 barcode
- pdf417 barcode image
language: de
lastmod: 2026-10-28
og_description: Erstellen Sie einen Barcode aus Text in C# mit Aspose.BarCode. Dieses
  Tutorial zeigt, wie man ein PDF417‑Barcode‑Bild erzeugt, Größe, Spalten und Kompaktmodus
  anpasst.
og_image_alt: Screenshot showing a compact PDF417 barcode created from text using
  C#
og_title: Barcode aus Text in C# erstellen – Schritt‑für‑Schritt‑Anleitung
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode from text in C# with Aspose.BarCode. Learn to generate
    PDF417 barcode image, set columns, adjust X‑dimension, and enable compact mode.
  headline: How to create barcode from text in C# using Aspose.BarCode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- image generation
title: Wie man in C# mit Aspose.BarCode aus Text einen Barcode erstellt
url: /de/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man aus Text in C# einen Barcode erstellt mit Aspose.BarCode

Wenn Sie **einen Barcode aus Text** in einer .NET‑Anwendung **erstellen** müssen, bietet diese Anleitung eine sofort einsatzbereite Lösung. Sie sehen, wie Sie **PDF417‑Barcode‑Bilder** erzeugen, die Modulbreite, Spaltenanzahl steuern und den kompakten Modus aktivieren – alles direkt in Ihrer IDE.

Das Tutorial deckt alles ab, was zum **Barcode‑C#‑Code generieren** nötig ist, von der Bibliotheksinstallation bis zum Speichern der finalen PNG‑Datei. Am Ende können Sie einen hochdichten PDF417‑Barcode in Berichten, Tickets oder Lageretiketten einbetten.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

* .NET 6.0 SDK oder neuer installiert  
* Visual Studio 2022 (oder ein beliebiger Editor, der .NET unterstützt)  
* Internetzugang zum Herunterladen des Aspose.BarCode für .NET NuGet‑Pakets  

Diese Voraussetzungen reichen aus, um das Beispiel unter Windows, Linux oder macOS zu kompilieren und auszuführen.

## Schritt 1: Das Aspose.BarCode NuGet‑Paket installieren

Die Bibliothek, die die Barcode‑Erstellung ermöglicht, ist **Aspose.BarCode for .NET**. Installieren Sie sie mit der .NET‑CLI:

```bash
dotnet add package Aspose.BarCode
```

Das Paket fügt den Namespace `Aspose.BarCode` hinzu, der die Klasse `BarcodeGenerator` enthält, die im gesamten Tutorial verwendet wird.

## Schritt 2: Ein Konsolenprojekt erstellen und den Code hinzufügen

Erstellen Sie ein neues Konsolenprojekt und ersetzen Sie die erzeugte `Program.cs` durch den folgenden Code. Das Programm demonstriert, wie man **einen Barcode aus Text** erstellt und als **PDF417‑Barcode‑Bild** speichert.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 2.1: Define the text to encode.
            // Unicode characters such as Å, ó, and © are supported out of the box.
            string data = "Åspóse.Barcóde©";

            // Step 2.2: Initialize the PDF417 generator with the desired text.
            // EncodeTypes.Pdf417 tells the generator which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // Step 2.3: Set the X‑dimension (module width) to 2 pixels for a denser barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 2.4: Define the number of columns in the PDF417 symbol.
            // Fewer columns produce a taller barcode; three columns keep it compact.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Step 2.5: Enable compact mode by truncating the right‑hand column.
            // Truncate reduces the overall width while preserving data integrity.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Step 2.6: Choose the output folder and file name.
            string outputPath = "CompactPdf417.png";

            // Step 2.7: Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

### Warum jede Zeile wichtig ist

* **`EncodeTypes.Pdf417`** wählt die PDF417‑Symbologie, die ideal ist, um große Datenmengen in einem zweidimensionalen Format zu kodieren.  
* **`XDimension.Pixels = 2`** reduziert die Modulbreite, wodurch der Barcode dichter und für begrenzten Platz besser geeignet wird.  
* **`Pdf417.Columns = 3`** steuert die Anzahl der vertikalen Datenspalten; eine niedrigere Zahl ergibt einen höheren, aber schmaleren Barcode.  
* **`Pdf417.Truncate = true`** aktiviert den kompakten Modus und schneidet ungenutzte Spalten rechts ab. Dies ist die zentrale Einstellung, die einen regulären PDF417 in ein **kompaktes PDF417‑Barcode‑Bild** verwandelt.  

## Schritt 3: Das Projekt bauen und ausführen

Führen Sie die folgenden Befehle im Projektverzeichnis aus:

```bash
dotnet build
dotnet run
```

Wenn das Programm beendet ist, sehen Sie eine Konsolennachricht, die den Speicherort der Datei bestätigt. Öffnen Sie `CompactPdf417.png` mit einem beliebigen Bildbetrachter, um das Ergebnis zu prüfen.

**Erwartete Ausgabe** – ein hochkontrastiertes PNG, das einen kompakten PDF417‑Barcode zeigt, der den String `Åspóse.Barcóde©` kodiert. Das Scannen des Bildes mit einem Standard‑Barcode‑Leser liefert den ursprünglichen Text zurück und bestätigt, dass das **generate pdf417 barcode** erfolgreich war.

## Schritt 4: Den Barcode für verschiedene Szenarien anpassen

Obwohl das Beispiel eine feste Spaltenanzahl und X‑Dimension verwendet, können Sie den Generator an andere Anforderungen anpassen:

| Szenario | Anpassung |
|----------|-----------|
| Größere Datenmenge | Erhöhen Sie `Pdf417.Columns` oder setzen Sie `Pdf417.Rows` manuell |
| Höhere Scan‑Zuverlässigkeit | Erhöhen Sie `XDimension.Pixels` auf 3 oder 4 |
| Anderes Bildformat | Ersetzen Sie `BarCodeImageFormat.Png` durch `Jpeg` oder `Bmp` |
| Transparenter Hintergrund | Setzen Sie `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent` |

Diese Optionen ermöglichen es Ihnen, **barcode C#**‑Lösungen zu erstellen, die zu mobilen Apps, Desktop‑Berichten oder Web‑Services passen.

## Schritt 5: Sonderfälle und bewährte Vorgehensweisen

* **Unicode‑Unterstützung** – Der Generator kodiert Unicode‑Zeichen automatisch, stellen Sie jedoch sicher, dass Ihre Quellzeichenfolge UTF‑8 kodiert ist, wenn Sie sie aus einer Datei lesen.  
* **Langer Text** – PDF417 kann bis zu 1 850 alphanumerische Zeichen kodieren. Überschreiten Sie dieses Limit, wirft die Bibliothek eine Ausnahme; teilen Sie die Daten in mehrere Barcodes auf oder wechseln Sie zu einer Symbologie mit höherer Kapazität.  
* **Fehlerbehandlung** – Umgeben Sie den Erzeugungscode mit einem `try/catch`‑Block, um `BarCodeException` abzufangen und eine benutzerfreundliche Fehlermeldung auszugeben.  
* **Performance** – Das Erzeugen vieler Barcodes in einer Schleife profitiert davon, eine einzelne `BarcodeGenerator`‑Instanz wiederzuverwenden und nur `CodeText` zwischen den Durchläufen zu aktualisieren.

```csharp
try
{
    generator.CodeText = nextText;
    generator.Save($"barcode_{i}.png", BarCodeImageFormat.Png);
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

## Vollständige Quellcode‑Auflistung

Unten finden Sie das komplette, eigenständige Programm, das Sie in `Program.cs` kopieren können. Weitere Dateien sind nicht erforderlich.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            string data = "Åspóse.Barcóde©";

            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

Wenn Sie dieses Programm ausführen, entsteht das **pdf417 barcode image**, das in der Abbildung unten zu sehen ist.

![Compact PDF417 barcode created from text using C#](/images/compact-pdf417.png){.img-fluid alt="Beispiel zum Erstellen eines Barcodes aus Text, das ein kompaktes PDF417‑Barcode‑Bild zeigt"}

*Bildbeschreibung: Die PNG‑Datei zeigt einen kompakten PDF417‑Barcode, der den String „Åspóse.Barcóde©“ kodiert.*  

## Fazit

Sie wissen jetzt, wie man **einen Barcode aus Text** in C# erstellt und ein **PDF417‑Barcode‑Bild** mit benutzerdefinierten Abmessungen und kompaktem Modus erzeugt. Das Beispiel demonstriert die wesentlichen Schritte zum **generate barcode C#**, zum Umgang mit Unicode‑Daten und zur Anpassung visueller Parameter für unterschiedliche Einsatzszenarien.

Als Nächstes können Sie verwandte Themen erkunden, wie **generate QR code in C#**, **add barcode to PDF documents** oder **embed barcodes in ASP.NET Core APIs**. All diese bauen auf den hier vorgestellten `BarcodeGenerator`‑Grundlagen auf.

Viel Spaß beim Coden und beim Integrieren von Barcodes in Ihre .NET‑Lösungen!

## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Codebeispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, weitere API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren Projekten zu erkunden.

- [Generate PDF417 Barcode in C# – Create PDF417 Barcode C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/)
- [How to generate PDF417 barcode with Aspose.BarCode in C#](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/)
- [How to create PDF417 barcode image in C# – complete guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
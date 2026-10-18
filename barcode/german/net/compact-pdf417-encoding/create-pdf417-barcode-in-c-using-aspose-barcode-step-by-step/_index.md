---
category: general
date: 2026-10-18
description: Erfahren Sie, wie Sie PDF417‑Barcodes in C# mit Aspose.BarCode erstellen.
  Dieses Tutorial behandelt die grundlegende, kompakte, Makro‑ und Mikro‑PDF417‑Generierung
  mit vollständigem Code.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to create pdf417
language: de
lastmod: 2026-10-18
og_description: Erstellen Sie PDF417‑Barcode in C# mit Aspose.BarCode. Folgen Sie
  dieser Anleitung, um grundlegende, kompakte, Makro‑ und Mikro‑PDF417‑Barcodes Schritt
  für Schritt zu erzeugen.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as an image file
og_title: PDF417-Barcode in C# erstellen – vollständiges Aspose.BarCode‑Tutorial
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to create PDF417 barcode in C# with Aspose.BarCode. This
    tutorial covers basic, compact, macro and micro PDF417 generation with full code.
  headline: Create PDF417 barcode in C# using Aspose.BarCode – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
- aspose
title: PDF417‑Barcode in C# mit Aspose.BarCode erstellen – Schritt‑für‑Schritt‑Anleitung
url: /de/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PDF417-Barcode in C# mit Aspose.BarCode erstellen – Schritt‑für‑Schritt‑Anleitung

Wenn Sie einen **PDF417-Barcode** in einer .NET‑Anwendung erstellen müssen, führt Sie dieses Tutorial durch den gesamten Prozess. Sie sehen, wie Sie einen einfachen Barcode generieren, den kompakten Modus aktivieren, Makro‑Metadaten hinzufügen und eine Mikro‑Variante erzeugen – alles mit klaren Erklärungen und ausführbarem Code.

Das Erzeugen von PDF417‑Barcodes ist in Logistik, Ticketing und Dokumentenmanagement üblich. Am Ende dieses Leitfadens können Sie die Barcode‑Erstellung in jedes C#‑Projekt integrieren, ohne externe Werkzeuge.

## Voraussetzungen

* .NET 6.0 oder höher (der Code funktioniert auch mit .NET Framework 4.7+)
* Visual Studio 2022 oder jede C#‑IDE
* **Aspose.BarCode for .NET** NuGet‑Paket  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Schreibberechtigung für einen Ordner, in dem die erzeugten PNG‑Dateien gespeichert werden

Keine zusätzliche Konfiguration ist erforderlich; die Bibliothek übernimmt alle Low‑Level‑Kodierungsdetails.

## Schritt 1: Einen einfachen PDF417‑Barcode erstellen

Der erste Schritt erstellt einen regulären PDF417‑Barcode mit benutzerdefinierter Größe und Spaltenanzahl.

```csharp
using Aspose.BarCode.Generation;

// Initialize the generator for a standard PDF417 barcode
BarcodeGenerator basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

// Adjust the X‑dimension (module width) to 2 pixels for higher resolution
basicGen.Parameters.Barcode.XDimension.Pixels = 2;

// Set the number of columns – three columns keep the barcode compact yet readable
basicGen.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image
basicGen.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**Warum diese Einstellungen wichtig sind**

* `XDimension.Pixels` steuert die physische Größe jedes Barcode‑Elements. Ein Wert von 2 erzeugt ein klares Bild auf den meisten Bildschirmen und Druckern.
* `Pdf417.Columns` bestimmt, wie viele Datenspalten der Barcode enthält. Weniger Spalten reduzieren die Breite; mehr Spalten erhöhen die Datenkapazität.

Durch Ausführen des Codes wird `Pdf417Basic.png` erstellt, das wie ein typisches PDF417‑Symbol mit drei Datenspalten und einer vollständigen Metadaten‑Spalte auf der rechten Seite aussieht.

## Schritt 2: Kompakten (gekürzten) Modus aktivieren

Der kompakte Modus entfernt die rechte Metadaten‑Spalte und macht den Barcode schmaler. Das ist nützlich, wenn Platz begrenzt ist, die Daten jedoch aus den verbleibenden Zeilen rekonstruiert werden können.

```csharp
// Turn on truncated mode to omit the metadata column
basicGen.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version
basicGen.Save(@"YOUR_DIRECTORY\CompactPdf417.png", BarCodeImageFormat.Png);
```

**Warum kürzen?**  
Wenn `Truncate` auf `true` gesetzt ist, lässt der Generator die optionale rechte Spalte weg, die Fehlerkorrektur‑ und Dateiebene‑Metadaten speichert. Der resultierende Barcode belegt weniger Spalten und bleibt dennoch von den meisten PDF417‑Lesern scanbar.

## Schritt 3: Einen Macro‑PDF417‑Barcode mit Dateiebene‑Metadaten erstellen

Macro PDF417 erweitert das Standardformat um Segment‑Kennungen, sodass ein großes Dokument in mehrere Barcodes aufgeteilt werden kann. Das ist praktisch zum Kodieren langer Zeichenketten oder mehrseitiger Dateien.

```csharp
// Initialize a generator for Macro PDF417
BarcodeGenerator macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");

// Set column count for better readability
macroGen.Parameters.Barcode.Pdf417.Columns = 5;

// Assign macro-specific identifiers
macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Unique file identifier
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;      // Current segment number
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total segments

// Save the macro barcode
macroGen.Save(@"YOUR_DIRECTORY\MacroPdf417.png", BarCodeImageFormat.Png);
```

**Erklärung der Makro‑Felder**

| Eigenschaft | Zweck |
|-------------|-------|
| `MacroPdf417FileID` | Eindeutiger Bezeichner für die gesamte Datei; alle Segmente teilen diesen Wert. |
| `MacroPdf417SegmentID` | Index des aktuellen Segments (beginnt bei 1). |
| `MacroPdf417SegmentsCount` | Gesamtzahl der Segmente, die den vollständigen Datensatz bilden. |

Ein Scanner, der Macro PDF417 versteht, kann die Originaldaten wieder zusammenbauen, indem er alle Segmente liest und diese Kennungen verwendet.

## Schritt 4: Einen Micro‑PDF417‑Barcode für kurze Daten erstellen

Micro PDF417 ist eine kompakte Version, die für kleine Datenmengen (bis zu 90 Zeichen) konzipiert ist. Sie begrenzt den Spaltenbereich auf 1‑4, wodurch der Barcode für winzige Etiketten oder Geräte mit begrenztem Anzeigebereich geeignet ist.

```csharp
// Initialize a generator for Micro PDF417
BarcodeGenerator microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");

// Set a fine X‑dimension for crisp rendering
microGen.Parameters.Barcode.XDimension.Pixels = 2;

// Choose a column count within the allowed range (1‑4)
microGen.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode
microGen.Save(@"YOUR_DIRECTORY\MicroPdf417.png", BarCodeImageFormat.Png);
```

**Wann Micro PDF417 verwenden**  
Verwenden Sie diese Variante, wenn die Datenmenge kurz ist und Sie den kleinstmöglichen Barcode benötigen. Sie ist ideal für Inventur‑Etiketten, Zugangskarten oder jede Situation, in der Bildschirmfläche kostbar ist.

## Vollständiges funktionierendes Beispiel

Unten finden Sie eine eigenständige Konsolenanwendung, die alle vier Barcode‑Typen in einem Durchlauf erzeugt. Kopieren Sie den Code in ein neues C#‑Projekt, ersetzen Sie `YOUR_DIRECTORY` durch einen vorhandenen Ordnerpfad und führen Sie ihn aus.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Adjust this path to a writable folder on your machine
            string outputPath = @"C:\Barcodes";

            // ---------- Basic PDF417 ----------
            var basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            basicGen.Parameters.Barcode.XDimension.Pixels = 2;
            basicGen.Parameters.Barcode.Pdf417.Columns = 3;
            basicGen.Save($"{outputPath}\\Pdf417Basic.png", BarCodeImageFormat.Png);

            // ---------- Compact PDF417 ----------
            basicGen.Parameters.Barcode.Pdf417.Truncate = true;
            basicGen.Save($"{outputPath}\\CompactPdf417.png", BarCodeImageFormat.Png);

            // ---------- Macro PDF417 ----------
            var macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");
            macroGen.Parameters.Barcode.Pdf417.Columns = 5;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
            macroGen.Save($"{outputPath}\\MacroPdf417.png", BarCodeImageFormat.Png);

            // ---------- Micro PDF417 ----------
            var microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");
            microGen.Parameters.Barcode.XDimension.Pixels = 2;
            microGen.Parameters.Barcode.Pdf417.Columns = 4; // valid range: 1‑4
            microGen.Save($"{outputPath}\\MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("All PDF417 barcodes have been generated successfully.");
        }
    }
}
```

**Erwartete Ausgabe**

Durch Ausführen des Programms werden vier PNG‑Dateien im angegebenen Ordner erstellt:

* `Pdf417Basic.png` – Standard‑Barcode mit drei Spalten
* `CompactPdf417.png` – gleiche Daten, gekürzte rechte Spalte
* `MacroPdf417.png` – Macro‑Barcode mit Segment‑Metadaten
* `MicroPdf417.png` – kompakter Micro‑Barcode für kurze Zeichenketten

Öffnen Sie ein Bild mit einem Bildbetrachter; Sie sehen die charakteristischen PDF417‑Muster. Das Scannen mit einem mobilen Barcode‑Reader (z. B. ZXing, Scandit) liefert die ursprünglichen Textzeichenketten zurück.

## Häufige Fragen und Tipps

* **Was tun, wenn der Barcode verschwommen aussieht?**  
  Erhöhen Sie `XDimension.Pixels` auf 3 oder 4. Größere Modulgrößen erzeugen hochauflösendere Bilder, allerdings mit einer größeren Dateigröße.

* **Kann ich SVG statt PNG ausgeben?**  
  Ja. Ersetzen Sie `BarCodeImageFormat.Png` durch `BarCodeImageFormat.Svg` in den `Save`‑Aufrufen.

* **Muss ich das Fehlerkorrektur‑Level manuell setzen?**  
  Aspose.BarCode wählt automatisch ein optimales Level. Für spezielle Anwendungsfälle können Sie `Pdf417.ErrorCorrectionLevel` anpassen.

* **Wie bette ich den Barcode in ein PDF‑Dokument ein?**  
  Verwenden Sie `Aspose.Pdf`, um das erzeugte PNG oder SVG als Bildelement auf einer PDF‑Seite hinzuzufügen.

* **Ist die Bibliothek thread‑sicher?**  
  Jede `BarcodeGenerator`‑Instanz ist unabhängig; Sie können Generatoren in mehreren Threads erstellen, ohne gemeinsamen Zustand.

## Fazit

Sie wissen jetzt, wie Sie **PDF417‑Barcode** in C# mit Aspose.BarCode erstellen, einschließlich der grundlegenden, kompakten, Makro‑ und Mikro‑Varianten

## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Code‑Beispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, weitere API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [Wie man einen PDF417‑Barcode in C# erstellt – Schritt‑für‑Schritt‑Anleitung](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [Wie man einen PDF417‑Barcode in C# mit kompaktem Modus erstellt](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [Wie man einen Macro‑PDF417‑Barcode in C# mit Aspose.BarCode erstellt](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
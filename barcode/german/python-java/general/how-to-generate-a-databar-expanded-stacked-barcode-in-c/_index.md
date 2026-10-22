---
category: general
date: 2026-10-21
description: Erzeugen Sie ein erweitertes gestapeltes Databar-Barcode‑Bild in C# mit
  BarcodeGenerator. Befolgen Sie diese Schritt‑für‑Schritt‑Anleitung, um Barcode‑Bilder
  zu erstellen, Zeilen und Spalten anzupassen und PNG‑Dateien zu exportieren.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- generate barcode image
- barcode generator c#
- how to generate databar
- create databar barcode
language: de
lastmod: 2026-10-21
og_description: Erstellen Sie einen erweiterten gestapelten Databar-Barcode in C#
  mit diesem Tutorial. Lernen Sie, wie Sie BarcodeGenerator verwenden, Zeilen und
  Spalten festlegen und PNG‑Bilder speichern.
og_image_alt: Sample databar expanded stacked barcode image generated with C#
og_title: Databar Expanded Stacked Barcode in C# generieren – vollständige Anleitung
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  headline: How to generate a databar expanded stacked barcode in C#
  type: TechArticle
- description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  name: How to generate a databar expanded stacked barcode in C#
  steps:
  - name: Basic barcode generation
    text: The simplest way to generate a **databar expanded stacked** image is to
      instantiate `BarcodeGenerator` with the desired `EncodeTypes` value and a plain
      text payload.
  - name: Customizing columns – create databar barcode with 4 columns
    text: You can control the number of columns using the `Parameters.Barcode.DataBar.Columns`
      property. The following example creates a barcode with **4 columns** while keeping
      the default row count.
  - name: Customizing rows – create databar barcode with 3 rows
    text: Similarly, you can adjust the row count via `Parameters.Barcode.DataBar.Rows`.
      The code below generates a barcode with **3 rows** and the default column count
      (4).
  - name: Exporting to other formats
    text: 'If you need a different image type (e.g., JPEG, BMP, or SVG), replace `BarCodeImageFormat.Png`
      with the appropriate enum value:'
  - name: Saving to a memory stream
    text: 'Sometimes you want to embed the barcode directly into a web response or
      a PDF without touching the file system. Use a `MemoryStream`:'
  - name: Handling invalid input
    text: 'The `BarcodeGenerator` validates the payload against the chosen symbology.
      If the data contains prohibited characters, an `ArgumentException` is thrown.
      Wrap the generation code in a try‑catch block to provide a friendly error message:'
  - name: Scaling the barcode image
    text: 'You can change the image size without altering the encoded data by setting
      `Parameters.Image.Width` and `Parameters.Image.Height`:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Wie man einen Databar Expanded Stacked Barcode in C# erzeugt
url: /de/python-java/general/how-to-generate-a-databar-expanded-stacked-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man einen Databar Expanded Stacked Barcode in C# erzeugt

Wenn Sie einen **Databar Expanded Stacked** Barcode in C# erzeugen müssen, zeigt Ihnen diese Anleitung, wie das geht. Die Databar Expanded Stacked Symbologie ist ideal, um große Datenmengen kompakt zu codieren, und Sie können das Bild mit nur wenigen Codezeilen erstellen. Sie lernen außerdem, wie Sie **Barcode‑Bilddateien** in verschiedenen Formaten generieren und Zeilen oder Spalten an Ihre Scan‑Umgebung anpassen.

Dieses Tutorial deckt alles ab, was Sie benötigen, um Databar‑Barcodes zu produzieren: Installation der erforderlichen Bibliothek, Vorbereitung des Ausgabeordners, Erstellung des Barcodes mit benutzerdefinierten Zeilen oder Spalten und Speicherung des Ergebnisses als PNG‑Datei. Am Ende können Sie **Databar‑Barcode**‑Bilder programmgesteuert erstellen und den Code für andere Bildformate oder Laufzeit‑Szenarien anpassen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie folgendes haben:

* .NET 6.0 SDK oder neuer (der Code funktioniert auch mit .NET Core 3.1 und .NET Framework 4.7+)
* Eine Entwicklungsumgebung wie Visual Studio 2022, Visual Studio Code oder Rider
* Internetzugang, um das **Barcode Generator C#** NuGet‑Paket (Aspose.BarCode for .NET) zu installieren

> **Profi‑Tipp:** Wenn Sie eine CI/CD‑Pipeline verwenden, fügen Sie den NuGet‑Paketverweis zu Ihrer Projektdatei hinzu, damit Builds reproduzierbar sind.

## Installieren der Barcode Generator C# Bibliothek

Das Beispiel verwendet die Aspose.BarCode‑Bibliothek, die die Klasse `BarcodeGenerator` und die Aufzählung `EncodeTypes.DatabarExpandedStacked` bereitstellt.

```bash
dotnet add package Aspose.BarCode
```

Der Befehl fügt die neueste stabile Version zu Ihrem Projekt hinzu. Nach der Installation können Sie den Namespace in Ihren C#‑Dateien importieren:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

## Ausgabeordner vorbereiten

Ein zuverlässiger Dateipfad verhindert Laufzeitfehler, wenn die Bibliothek versucht, das Bild zu schreiben. Der folgende Code erstellt das Verzeichnis, falls es nicht existiert:

```csharp
using System;
using System.IO;

// Define the folder where barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);
```

> **Warum das wichtig ist:** Der Versuch, in ein nicht vorhandenes Verzeichnis zu speichern, löst eine `IOException` aus. Das Vorab‑Erstellen des Ordners macht den Code sowohl für die lokale Entwicklung als auch für Produktionsumgebungen robust.

## Generieren eines Databar Expanded Stacked Barcode‑Bildes

### Grundlegende Barcode‑Generierung

Der einfachste Weg, ein **Databar Expanded Stacked** Bild zu erzeugen, besteht darin, `BarcodeGenerator` mit dem gewünschten `EncodeTypes`‑Wert und einer einfachen Text‑Payload zu instanziieren.

```csharp
// Create a barcode that encodes a long numeric string
var basicGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "01234567890123456789");

// Save the barcode as PNG
basicGenerator.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
    BarCodeImageFormat.Png);
```

Das Ausführen des Snippets erzeugt `DatabarBasic.png` im *Barcodes*‑Ordner. Das Bild enthält ein Standard‑Databar‑Expanded‑Stacked‑Symbol mit dem Standard‑Layout (4 Spalten × 4 Zeilen).

### Spalten anpassen – Databar‑Barcode mit 4 Spalten erstellen

Sie können die Anzahl der Spalten über die Eigenschaft `Parameters.Barcode.DataBar.Columns` steuern. Das folgende Beispiel erstellt einen Barcode mit **4 Spalten**, während die Standard‑Zeilenanzahl beibehalten wird.

```csharp
// Step 1: Define a generator with custom column count
var columnGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the column count to 4 (default rows = 4)
columnGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the image
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
    BarCodeImageFormat.Png);
```

Die resultierende Datei, **DatabarCols4.png**, sieht folgendermaßen aus:

![Databar expanded stacked barcode with 4 columns](databar_cols4.png "Databar expanded stacked barcode with 4 columns – generated with C#")

*Image alt text (og_image_alt):* **Beispiel‑Databar‑Expanded‑Stacked‑Barcode‑Bild erzeugt mit C#** – dies erfüllt die SEO‑Anforderung für Alt‑Texte von Bildern.

### Zeilen anpassen – Databar‑Barcode mit 3 Zeilen erstellen

Analog können Sie die Zeilenanzahl über `Parameters.Barcode.DataBar.Rows` anpassen. Der Code unten erzeugt einen Barcode mit **3 Zeilen** und der Standard‑Spaltenanzahl (4).

```csharp
// Step 2: Define a generator with custom row count
var rowGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the row count to 3 (default columns = 4)
rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

// Save the image
rowGenerator.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
    BarCodeImageFormat.Png);
```

Die Datei **DatabarRows3.png** enthält ein Databar Expanded Stacked Symbol, das vertikal etwas kürzer ist und sich gut für platzbeschränkte Etiketten eignet.

### Exportieren in andere Formate

Falls Sie einen anderen Bildtyp benötigen (z. B. JPEG, BMP oder SVG), ersetzen Sie `BarCodeImageFormat.Png` durch den entsprechenden Enum‑Wert:

```csharp
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
    BarCodeImageFormat.Jpeg);
```

Die Bibliothek unterstützt zudem Vektorformate wie SVG, die sich ideal für hochauflösenden Druck eignen.

## Erweiterte Szenarien

### Speichern in einen MemoryStream

Manchmal möchten Sie den Barcode direkt in eine Web‑Antwort oder ein PDF einbetten, ohne das Dateisystem zu berühren. Verwenden Sie einen `MemoryStream`:

```csharp
using System.IO;

// Generate barcode into a memory stream
using var ms = new MemoryStream();
columnGenerator.Save(ms, BarCodeImageFormat.Png);

// Reset stream position before reading
ms.Position = 0;

// Example: return the stream as a file download in ASP.NET Core
// return File(ms.ToArray(), "image/png", "databar.png");
```

### Umgang mit ungültiger Eingabe

Der `BarcodeGenerator` validiert die Payload gegenüber der gewählten Symbologie. Enthält die Daten verbotene Zeichen, wird eine `ArgumentException` ausgelöst. Wickeln Sie den Generierungscode in einen try‑catch‑Block, um eine benutzerfreundliche Fehlermeldung auszugeben:

```csharp
try
{
    var gen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "INVALID*DATA");
    gen.Save(Path.Combine(outputFolder, "Invalid.png"), BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

### Skalieren des Barcode‑Bildes

Sie können die Bildgröße ändern, ohne die codierten Daten zu beeinflussen, indem Sie `Parameters.Image.Width` und `Parameters.Image.Height` setzen:

```csharp
columnGenerator.Parameters.Image.Width = 300;   // pixels
columnGenerator.Parameters.Image.Height = 150; // pixels
columnGenerator.Save(Path.Combine(outputFolder, "DatabarLarge.png"),
    BarCodeImageFormat.Png);
```

Das Skalieren ist nützlich, wenn der Barcode eine bestimmte DPI‑Anforderung für Scanner erfüllen muss.

## Vollständiges funktionierendes Beispiel

Unten finden Sie eine komplette, sofort ausführbare Konsolenanwendung, die alle besprochenen Schritte demonstriert:

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace DatabarExpandedStackedDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Prepare output folder
            string outputFolder = Path.Combine(
                Environment.CurrentDirectory, "Barcodes");
            Directory.CreateDirectory(outputFolder);

            // 2️⃣ Generate basic barcode
            var basic = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "01234567890123456789");
            basic.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
                BarCodeImageFormat.Png);

            // 3️⃣ Generate barcode with 4 columns
            var colGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            colGen.Parameters.Barcode.DataBar.Columns = 4;
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
                BarCodeImageFormat.Png);

            // 4️⃣ Generate barcode with 3 rows
            var rowGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            rowGen.Parameters.Barcode.DataBar.Rows = 3;
            rowGen.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
                BarCodeImageFormat.Png);

            // 5️⃣ Export to JPEG as an extra format
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
                BarCodeImageFormat.Jpeg);

            Console.WriteLine("All barcode images have been generated in:");
            Console.WriteLine(outputFolder);
        }
    }
}
```

**Erwartete Ausgabe**


## Was sollten Sie als Nächstes lernen?


Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Codebeispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, weitere API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [Wie man Spalten für einen Databar Expanded Stacked Barcode festlegt – vollständige C#‑Anleitung](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [Wie man ein Barcode‑Generator‑Beispiel in C# mit DataBar Expanded Stacked erstellt](/barcode/english/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/)
- [Databar Expanded Stacked Barcode‑Leitfaden – wie man ihn in C# generiert und dimensioniert](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
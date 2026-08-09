---
category: general
date: 2026-08-09
description: Aspose-Barcode-Beispiel, das zeigt, wie man den Barcode-Generator in
  C# verwendet, um ein Macro PDF417 mit voller Metadatenunterstützung zu erzeugen.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode example
- barcode generator c#
language: de
lastmod: 2026-08-09
og_description: Das Aspose‑Barcode‑Beispiel demonstriert die Verwendung eines Barcode‑Generators
  in C#, um einen Macro‑PDF417‑Barcode zu erzeugen, der Datei‑ID, Segmentdaten, Zeitstempel
  und weitere Metadaten enthält.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: Aspose Barcode-Beispiel – Macro PDF417 mit C# erstellen
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- Macro PDF417
title: 'Aspose Barcode‑Beispiel: Macro‑PDF417 in C# generieren'
url: /de/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose‑Barcode‑Beispiel: Macro PDF417 in C# erzeugen

Wenn Sie ein **aspose barcode example** benötigen, das einen Macro PDF417‑Barcode erstellt, zeigt Ihnen diese Anleitung, wie Sie dies mit einem **barcode generator C#** umsetzen. Sie sehen jede erforderliche Einstellung, von den Grundmaßen bis zum vollständigen Satz der Macro PDF417‑Metadatenfelder, und erhalten am Ende ein PNG‑Bild, das für die Weiterverarbeitung bereitsteht.

Das Tutorial deckt den gesamten Workflow ab, erklärt, warum jeder Parameter wichtig ist, und liefert ein sofort ausführbares Code‑Beispiel. Es werden keine externen Verweise benötigt; Sie können den Code kopieren, die Werte anpassen und sofort ausführen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- .NET 6.0 (oder höher) installiert  
- Visual Studio 2022 oder eine beliebige C#‑kompatible IDE  
- Eine gültige Lizenz für **Aspose.BarCode for .NET** (die kostenlose Testversion funktioniert für dieses Beispiel)  

Fügen Sie das Aspose.BarCode‑NuGet‑Paket zu Ihrem Projekt hinzu:

```bash
dotnet add package Aspose.BarCode
```

## Schritt 1: Instanziieren des Barcode‑Generators C#  

Der erste Schritt besteht darin, `BarcodeGenerator` mit dem Enum‑Wert `EncodeTypes.MacroPdf417` und dem Text, den Sie codieren möchten, zu instanziieren. Der Text kann Unicode‑Zeichen enthalten, die die Bibliothek automatisch verarbeitet.

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*Warum das wichtig ist*: `EncodeTypes.MacroPdf417` weist die Engine an, ein Macro PDF417‑Symbol zu erzeugen, das segmentierte Daten und zusätzliche datei‑bezogene Metadaten unterstützt. Die `using`‑Anweisung stellt sicher, dass nicht verwaltete Ressourcen nach dem Speichern des Bildes freigegeben werden.

## Schritt 2: Grundlegendes Aussehen des Barcodes festlegen  

Ein Macro PDF417‑Barcode besteht aus quadratischen Modulen. Die Kontrolle der Modulgröße und der Spaltenanzahl beeinflusst sowohl die Lesbarkeit als auch die Dateigröße.

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*Warum das wichtig ist*: `XDimension.Pixels` bestimmt die visuelle Dichte; ein Wert von 2 Pixel funktioniert gut für die Anzeige auf Bildschirmen und hält das Bild klein. Passen Sie die Spaltenanzahl an Ihre Layout‑Beschränkungen an – mehr Spalten erzeugen einen breiteren, kürzeren Barcode.

## Schritt 3: Macro PDF417‑spezifische Metadaten setzen  

Macro PDF417 erweitert das Standard‑PDF417‑Format um Felder, die die Rekonstruktion großer Dateien aus mehreren Barcode‑Segmenten ermöglichen. Jedes Feld ist optional, aber das Setzen demonstriert die vollen Möglichkeiten der API.

```csharp
    // Unique identifier for the entire file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (zero‑based)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the file
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Logical name of the source file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // 16‑bit CCITT checksum for error detection
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate size of the original file in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;

    // Timestamp when the file was generated
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields for routing information
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the last segment
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Warum das wichtig ist*:  
- `MacroPdf417FileID` verknüpft alle Segmente, die zu derselben logischen Datei gehören.  
- `MacroPdf417SegmentID` und `MacroPdf417SegmentsCount` ermöglichen es dem Decoder, Fragmente korrekt zu reorderieren.  
- `MacroPdf417Checksum` liefert eine schnelle Integritätsprüfung, ohne die gesamte Nutzlast zu decodieren.  
- `MacroPdf417FileSize` und `MacroPdf417TimeStamp` erlauben nachgelagerten Systemen zu prüfen, ob die rekonstruierte Datei mit dem Original übereinstimmt.  
- `MacroPdf417Addressee` / `MacroPdf417Sender` sind in Logistik‑ oder Dokumentenaustausch‑Szenarien nützlich.  
- Das Setzen von `MacroPdf417Terminator` auf `Set` markiert diesen Barcode als letztes Segment, was den Rekonstruktions‑Algorithmus vereinfacht.

## Schritt 4: Das erzeugte Barcode‑Bild speichern  

Zum Schluss schreiben Sie den Barcode in eine PNG‑Datei. Sie können jedes unterstützte Format wählen (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`).

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Warum das wichtig ist*: PNG bewahrt verlustfreie Pixeldaten und stellt sicher, dass Scanner das exakt konfigurierte Modul‑Muster lesen. Das Ändern des Formats kann die visuelle Qualität und Dateigröße beeinflussen.

### Erwartete Ausgabe

Das Ausführen des vollständigen Programms erzeugt eine Datei namens **ExtPDF417Meta.png**. Beim Öffnen des Bildes sehen Sie einen rechteckigen Macro PDF417‑Barcode mit dem codierten Text „Åspóse.Barcóde©“, und die visuelle Dichte entspricht der von Ihnen festgelegten 2‑Pixel‑X‑Dimension. Das Scannen des Bildes mit einem PDF417‑kompatiblen Leser liefert alle in Schritt 3 definierten Metadatenfelder zurück.

## Vollständiges funktionierendes Beispiel

Kopieren Sie den untenstehenden Code in ein neues Konsolen‑Projekt (`dotnet new console`) und ersetzen Sie `YOUR_DIRECTORY` durch einen absoluten oder relativen Pfad, der auf Ihrem Rechner existiert.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a barcode generator for Macro PDF417 with the desired text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the basic barcode appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // pixel size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol

                // Step 3: Set Macro PDF417 specific metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the generated barcode image
                generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

Führen Sie das Programm aus (`dotnet run`). Nach der Ausführung prüfen Sie, ob die PNG‑Datei an dem von Ihnen angegebenen Ort erscheint. Verwenden Sie eine Barcode‑Lese‑App, die Macro PDF417 unterstützt, um zu bestätigen, dass die Metadaten korrekt eingebettet sind.

## Häufige Varianten und Sonderfälle

- **Verschiedene Bildformate**: Ersetzen Sie `BarCodeImageFormat.Png` durch `Jpeg`, `Bmp` oder `Tiff`, wenn Ihr nachgelagertes System ein anderes Format bevorzugt.  
- **Änderung der Modulgröße**: Größere Werte für `XDimension.Pixels` verbessern die Scan‑Zuverlässigkeit bei Low‑Resolution‑Scannern, erhöhen jedoch die Bildgröße.  
- **Mehrere Segmente**: Um eine mehrsegmentige Datei zu erzeugen, generieren Sie eine Reihe von Barcodes, erhöhen Sie `MacroPdf417SegmentID` für jedes und halten Sie `MacroPdf417FileID` konstant. Nur das letzte Segment sollte `MacroPdf417Terminator` gesetzt haben.  
- **Unicode‑Unterstützung**: Der Generator codiert Unicode‑Zeichen automatisch; stellen Sie sicher, dass Ihre Quellzeichenkette UTF‑8 verwendet, wenn Sie sie aus einer externen Datei einlesen.  
- **Fehlerbehandlung**: Umfassen Sie den `using`‑Block mit einem `try‑catch`, um `BarCodeException` für ungültige Parameter (z. B. Spaltenzahl außerhalb des zulässigen Bereichs) abzufangen.

## Profi‑Tipps

- **Performance**: Wiederverwenden Sie eine einzelne `BarcodeGenerator`‑Instanz, wenn Sie viele Barcodes mit denselben Einstellungen erzeugen; ändern Sie nur die Eigenschaft `CodeText` zwischen den Saves.  
- **Dateigrößenschätzung**: Das Feld `MacroPdf417FileSize` sollte der Byte‑Anzahl der ursprünglichen Nutzlast entsprechen; Abweichungen können zu Validierungsfehlern im nachgelagerten System führen.  
- **Testing**: Validieren Sie erzeugte Barcodes sowohl mit Asposes eingebautem Decoder (`BarCodeReader`) als auch mit einem Drittanbieter‑Scanner, um Interoperabilität sicherzustellen.

## Fazit

Dieses **aspose barcode example**


## Was sollten Sie als Nächstes lernen?


Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Code‑Beispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, weitere API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to create barcode quiet zone for Code 16K using Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
---
category: general
date: 2026-09-22
description: Erfahren Sie, wie Sie in C# einen PDF417‑Barcode erstellen, die Barcode‑Größe
  festlegen und Barcode‑Bilddateien mit klaren Schritt‑für‑Schritt‑Codebeispielen
  generieren.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to create PDF417
- set barcode size
- create barcode image c#
language: de
lastmod: 2026-09-22
og_description: Erstellen Sie schnell einen PDF417‑Barcode in C#. Dieses Tutorial
  zeigt, wie Sie die Barcode‑Größe festlegen, den kompakten Modus aktivieren und PNG‑Bilder
  für jedes .NET‑Projekt ausgeben.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: PDF417-Barcode in C# erstellen – Schritt‑für‑Schritt‑Anleitung
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to create PDF417 barcode in C#, set barcode size, and generate
    barcode image files with clear step‑by‑step code examples.
  headline: How to create PDF417 barcode and set its size in C#
  type: TechArticle
tags:
- PDF417
- C#
- Barcode
- Imaging
title: Wie man einen PDF417-Barcode erstellt und seine Größe in C# festlegt
url: /de/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man einen PDF417-Barcode erstellt und seine Größe in C# festlegt

Wenn Sie einen **PDF417-Barcode** in C# erstellen müssen, zeigt Ihnen diese Anleitung, wie Sie den Barcode generieren, seine Abmessungen steuern und das Ergebnis als Bilddatei speichern. Egal, ob Sie ein Ticketingsystem, ein Logistiketikett oder ein sicheres Berechtigungsnachweis erstellen, das Beherrschen des PDF417-Formats ermöglicht es Ihnen, große Datenmengen in einer kompakten visuellen Form zu codieren.

In diesem Tutorial lernen Sie:

* **PDF417-Barcode erstellen** mit der Aspose.BarCode (oder einer kompatiblen) Bibliothek.  
* **Barcode-Größe festlegen** durch Anpassen der X‑Dimension und der Spaltenanzahl.  
* Ein **Barcode-Bild in C#** für PNG, JPEG oder BMP erzeugen.  

Das Beispiel verwendet die kostenlose Community‑Edition von Aspose.BarCode für .NET, aber die gleichen Konzepte gelten für andere Bibliotheken, die ähnliche Eigenschaften bereitstellen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie:

* .NET 6.0 SDK oder neuer installiert haben.  
* Eine C#‑IDE (Visual Studio, Visual Studio Code, Rider usw.).  
* Das `Aspose.BarCode` NuGet‑Paket (`dotnet add package Aspose.BarCode`).  

Es ist keine zusätzliche Konfiguration erforderlich; die Bibliothek funktioniert unter Windows, Linux und macOS.

## Schritt 1: Einen einfachen PDF417-Barcode erstellen und seine Größe festlegen

Der erste Schritt besteht darin, einen `BarcodeGenerator` mit dem Enum `EncodeTypes.Pdf417` zu instanziieren und den zu codierenden Text anzugeben. Anschließend passen Sie die **X‑Dimension** (Modulbreite) und die Anzahl der **Spalten** an, um die Gesamtabmessungen zu steuern.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Define the text that the barcode will represent.
string data = "Sample text for PDF417 barcode";

// Create a basic PDF417 barcode generator.
var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Set the module width to 2 pixels (controls bar thickness).
basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Set the column count; 3 columns yields a compact visual but still readable.
basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image.
string basicPath = Path.Combine("YOUR_DIRECTORY", "Pdf417Basic.png");
basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
```

**Warum diese Einstellungen wichtig sind**

* `XDimension.Pixels` bestimmt die schmalste Strichbreite. Kleinere Werte erzeugen einen dichteren Barcode, während größere Werte die Lesbarkeit bei niedrigauflösenden Scannern erhöhen.  
* `Pdf417.Columns` beeinflusst das Seitenverhältnis des Barcodes. Weniger Spalten machen den Barcode höher; mehr Spalten flachen ihn ab. Das Anpassen der Spalten ist der primäre Weg, um **die Barcode-Größe festzulegen**, ohne die codierten Daten zu ändern.

Nach dem Ausführen des Codes finden Sie `Pdf417Basic.png` im angegebenen Ordner. Das Bild sieht ähnlich aus wie der Screenshot unten:

<img src="images/pdf417-basic.png" alt="create PDF417 barcode example showing basic barcode layout">

## Schritt 2: Einen kompakten PDF417-Barcode (Truncate‑Modus) mit derselben Größe erstellen

Manchmal benötigen Sie einen kürzeren Barcode für begrenzten Platz. PDF417 bietet einen *truncate* (kompakten) Modus, der das Stopp‑Muster entfernt und die Gesamthöhe reduziert. Die Eigenschaft `Truncate` schaltet dieses Verhalten um.

```csharp
// Reuse the same data string.
var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Keep the same module width and column count for a fair size comparison.
compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Enable compact (truncate) mode – this removes the stop pattern.
compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version.
string compactPath = Path.Combine("YOUR_DIRECTORY", "CompactPdf417.png");
compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
```

**Was ändert sich bei `Truncate = true`?**

* Der Barcode wird vertikal etwa 15‑20 % kürzer, was für kleine Etiketten oder mobile Bildschirme nützlich ist.  
* Die Daten bleiben vollständig wiederherstellbar; die meisten modernen Scanner verstehen den Truncate‑Modus automatisch.

Der resultierende `CompactPdf417.png` erscheint als schlankere Version des Basis‑Barcodes.

## Schritt 3: Einen Micro PDF417-Barcode erstellen, Spalten anpassen und speichern

Micro PDF417 ist eine neuere, hochdichte Variante, die für sehr kleine Flächen (z. B. Ausweise) konzipiert ist. Sie unterstützt nur 1‑4 Spalten, und die Bibliothek stellt dieselbe `XDimension`‑Eigenschaft zur Größensteuerung bereit.

```csharp
// Create a Micro PDF417 generator.
var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);

// Set module width – 2 pixels works well for most printers.
microPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Micro PDF417 allows only 1 to 4 columns; choose 4 for a more square shape.
microPdf417.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode.
string microPath = Path.Combine("YOUR_DIRECTORY", "MicroPdf417.png");
microPdf417.Save(microPath, BarCodeImageFormat.Png);
```

**Wichtige Punkte für Micro PDF417**

* Das Enum `EncodeTypes.MicroPdf417` wählt automatisch die Mikro‑Variante aus.  
* Da das Symbol dichter ist, benötigen Sie möglicherweise einen Drucker mit höherer DPI (300 dpi oder mehr), um den Barcode lesbar zu halten.  
* Das Anpassen der Spaltenanzahl ist das einzige verfügbare Größeneinstell‑Element; die Bibliothek respektiert weiterhin `XDimension`.

## Wie man die Barcode-Größe für verschiedene Ausgabeformate festlegt

Die obigen Beispiele verwenden PNG, aber dieselbe `Save`‑Methode funktioniert auch mit JPEG, BMP oder TIFF. Wenn Sie eine bestimmte Bildgröße benötigen (z. B. 300 × 150 px), kombinieren Sie `XDimension` mit `ResolutionX`/`ResolutionY`:

```csharp
basicPdf417.Parameters.ImageResolution = 300; // DPI
basicPdf417.Parameters.Barcode.XDimension.Pixels = 3; // larger modules for higher DPI
basicPdf417.Save("Pdf417HighRes.jpg", BarCodeImageFormat.Jpeg);
```

Durch Erhöhen von `ImageResolution` bei gleichzeitiger Skalierung von `XDimension` bleibt die visuelle Qualität bei hochauflösenden Drucken erhalten.

## Häufige Fallstricke und Pro‑Tipps

| Problem | Warum es passiert | Lösung |
|---------|-------------------|--------|
| Barcode erscheint unscharf auf dem Bildschirm | Niedrige DPI kombiniert mit kleinem `XDimension` | Erhöhen Sie `ImageResolution` und/oder `XDimension.Pixels` |
| Scanner kann Truncate‑Modus nicht lesen | Ältere Scanner‑Firmware unterstützt es nicht | Verwenden Sie den vollen (nicht gekürzten) Modus für ältere Hardware |
| Micro PDF417 ist nicht lesbar | Gedruckt bei < 300 dpi oder mit unzureichendem Kontrast | Auf mattem Papier bei 300 dpi oder höher drucken, dunklen Vordergrund sicherstellen |
| Ausgabedatei ist beschädigt | Fehlende Schreibberechtigung für den Zielordner | Stellen Sie sicher, dass `YOUR_DIRECTORY` existiert und beschreibbar ist |

**Pro‑Tipp:** Generieren Sie den Barcode immer als PNG, wenn Sie verlustfreie Qualität für weitere Verarbeitungsschritte benötigen (z. B. Einbetten in PDFs). PNG bewahrt exakte Pixelwerte, während JPEG Kompressionsartefakte einführt, die die Lesbarkeit des Barcodes beeinträchtigen können.

## Vollständiges, ausführbares Beispiel

Im Folgenden finden Sie eine komplette Konsolenanwendung, die alle drei Barcode‑Typen in einem Durchlauf demonstriert. Kopieren Sie den Code in ein neues .NET‑Konsolenprojekt und führen Sie ihn aus.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // The text to encode – change this to whatever data you need.
        const string data = "Sample text for PDF417 barcode";

        // Directory where images will be saved.
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // ---------- Basic PDF417 ----------
        var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        string basicPath = Path.Combine(outputDir, "Pdf417Basic.png");
        basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Basic PDF417 saved to {basicPath}");

        // ---------- Compact (Truncate) PDF417 ----------
        var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;
        string compactPath = Path.Combine(outputDir, "CompactPdf417.png");
        compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Compact PDF417 saved to {compactPath}");

        // ---------- Micro PDF417 ----------
        var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);
        microPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        microPdf417.Parameters.Barcode.Pdf417.Columns = 4; // 1‑4 allowed
        string microPath = Path.Combine(outputDir, "MicroPdf417.png");
        microPdf417.Save(microPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Micro PDF417 saved to {microPath}");
    }
}
```

**Erwartete Ausgabe**

Beim Ausführen des Programms werden drei PNG‑Dateien in einem `Barcodes`‑Ordner erstellt:

* `Pdf417Basic.png` – ein Standard‑PDF417‑Barcode mit drei Spalten.  
* `CompactPdf417.png` – dieselben Daten im Truncate‑ (kompakten) Modus, etwas kürzer.  
* `MicroPdf417.png` – eine hochdichte Micro‑PDF417‑Variante mit vier Spalten.

Öffnen Sie ein Bild mit einem Bildbetrachter; Sie sollten die charakteristische gestapelte

## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Codebeispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, zusätzliche API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [Wie man Barcode erstellt – Kompakter PDF417 mit Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Wie man Fehlerlevel im PDF417-Barcode festlegt – Vollständige Anleitung](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [PDF417-Barcode-Metadaten in C# erstellen – Vollständige Schritt‑für‑Schritt‑Anleitung](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
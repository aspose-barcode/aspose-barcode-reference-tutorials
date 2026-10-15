---
category: general
date: 2026-10-12
description: Lernen Sie, wie Sie Micro‑PDF417‑Barcodes erstellen und Barcodes mit
  C# in PNG konvertieren. Schritt‑für‑Schritt‑Anleitung mit vollständigem Code und
  Tipps.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro PDF417 barcode
- convert barcode to PNG
- micro PDF417 C# example
- GS1 micro PDF417 generation
- barcode image settings
language: de
lastmod: 2026-10-12
og_description: Erstellen Sie einen Micro‑PDF417‑Barcode und konvertieren Sie den
  Barcode mit C# in PNG. Folgen Sie dieser vollständigen Anleitung, um sowohl die
  Standard‑ als auch die GS1‑Versionen zu erzeugen.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Erstelle einen Micro-PDF417-Barcode und konvertiere ihn in PNG – C#‑Tutorial
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn to create micro PDF417 barcode and convert barcode to PNG using
    C#. Step‑by‑step guide with full code and tips.
  headline: How to create micro PDF417 barcode and convert it to PNG in C#
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Wie man einen Micro‑PDF417‑Barcode erstellt und ihn in C# in PNG konvertiert
url: /de/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-convert-it-to-png-in/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Micro PDF417 Barcode erstellt und in PNG konvertiert in C#

Wenn Sie einen **Micro PDF417 Barcode** in einer .NET-Anwendung erstellen müssen, zeigt Ihnen dieses Tutorial genau, wie es geht. Sie sehen ein vollständiges, ausführbares Beispiel, das sowohl einen Standard‑Micro‑PDF417‑Barcode als auch eine GS1‑konforme Version erzeugt und dann **den Barcode in PNG konvertiert** für die nachgelagerte Verwendung, z. B. beim Drucken oder in der Webanzeige.

Das Erzeugen eines Barcodes ist mehr als nur ein Aufruf einer einzigen Methode – die Wahl der richtigen Modulgröße, Spaltenanzahl und des Codierungsformats bestimmt die Scan‑Zuverlässigkeit. Am Ende dieses Leitfadens verstehen Sie, warum jede Einstellung wichtig ist und wie Sie sie für Ihre eigenen Projekte anpassen können.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

| Anforderung | Grund |
|-------------|-------|
| .NET 6.0 SDK oder höher | Stellt die Laufzeit für die C#‑Konsolenanwendung bereit |
| Visual Studio 2022 (oder jede C#‑IDE) | Erleichtert das Bearbeiten und Debuggen |
| **Aspose.BarCode for .NET** NuGet‑Paket | Stellt die Klassen `BarcodeGenerator`, `EncodeTypes` und `BarCodeImageFormat` bereit |
| Schreibberechtigung für den Ausgabepfad | Erforderlich für `Save`‑Aufrufe, die PNG‑Dateien erzeugen |

Sie können das Aspose.BarCode‑Paket über die CLI hinzufügen:

```bash
dotnet add package Aspose.BarCode
```

## Schritt 1: Ein minimales Konsolenprojekt einrichten

Erstellen Sie ein neues Konsolenprojekt und binden Sie die Barcode‑Bibliothek ein. Die folgende `Program.cs` enthält den gesamten benötigten Code; externe Dateien sind nicht erforderlich.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace MicroPdf417Demo
{
    internal class Program
    {
        static void Main()
        {
            // Define the folder where PNG files will be saved
            string outputFolder = Environment.CurrentDirectory;

            // ------------------------------------------------------------
            // 1️⃣ Create a Micro PDF417 barcode generator with plain data
            // ------------------------------------------------------------
            BarcodeGenerator microGen = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,          // Micro PDF417 symbology
                "Micro data");                    // Simple alphanumeric payload

            // ------------------------------------------------------------
            // 2️⃣ Adjust the X dimension (module size) and set column count
            // ------------------------------------------------------------
            // XDimension controls the physical size of each barcode module.
            // A value of 2 pixels gives a compact yet readable barcode.
            microGen.Parameters.Barcode.XDimension.Pixels = 2;

            // For Micro PDF417 you can limit the number of columns.
            // Four columns keep the barcode small enough for labels.
            microGen.Parameters.Barcode.Pdf417.Columns = 4;

            // ------------------------------------------------------------
            // 3️⃣ Convert barcode to PNG and save the image
            // ------------------------------------------------------------
            string microPath = System.IO.Path.Combine(outputFolder, "MicroPdf417.png");
            microGen.Save(microPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Standard Micro PDF417 saved to: {microPath}");

            // ------------------------------------------------------------
            // 4️⃣ Create a GS1 Micro PDF417 barcode with AI‑encoded data
            // ------------------------------------------------------------
            // GS1 syntax requires Application Identifiers (AIs) wrapped in parentheses.
            // Example: (01) – GTIN, (21) – serial number.
            BarcodeGenerator gs1MicroGen = new BarcodeGenerator(
                EncodeTypes.Gs1MicroPdf417,
                "(01)12345678901231(21)ABC123");

            // ------------------------------------------------------------
            // 5️⃣ Set the X dimension for the GS1 barcode (same as step 2)
            // ------------------------------------------------------------
            gs1MicroGen.Parameters.Barcode.XDimension.Pixels = 2;

            // ------------------------------------------------------------
            // 6️⃣ Convert barcode to PNG and save the GS1 image
            // ------------------------------------------------------------
            string gs1Path = System.IO.Path.Combine(outputFolder, "GS1MicroPdf417.png");
            gs1MicroGen.Save(gs1Path, BarCodeImageFormat.Png);
            Console.WriteLine($"GS1 Micro PDF417 saved to: {gs1Path}");

            // End of demo
            Console.WriteLine("Barcode generation complete.");
        }
    }
}
```

### Warum jede Zeile wichtig ist

* **`EncodeTypes.MicroPdf417` vs `EncodeTypes.Gs1MicroPdf417`** – Der erste erzeugt einen einfachen Micro PDF417 Barcode, während der zweite den GS1‑Standards folgt und Application Identifiers (AIs) einbettet. Wählen Sie je nach Erwartung Ihres nachgelagerten Systems, ob GS1‑Daten benötigt werden.  
* **`XDimension.Pixels = 2`** – Steuert die Modulbreite. Kleinere Werte erzeugen ein dichteres Bild, können jedoch bei niedrigauflösenden Scannern unlesbar werden. Zwei Pixel sind ein sicherer Standard für die meisten Etikettendrucker.  
* **`Pdf417.Columns = 4`** – Micro PDF417 ermöglicht das Begrenzen der Spalten, wodurch die Gesamtlänge reduziert wird. Vier Spalten halten den Barcode kompakt, ohne die Datenkapazität für kurze Payloads zu beeinträchtigen.  
* **`BarCodeImageFormat.Png`** – PNG bewahrt verlustfreie Qualität, was für die Barcode‑Klarheit entscheidend ist. Deshalb **konvertieren wir den Barcode in PNG** statt in JPEG.

## Schritt 2: Das Programm ausführen und die Ausgabe überprüfen

1. Projekt bauen: `dotnet build`.  
2. Ausführen: `dotnet run`.

Sie sollten Konsolennachrichten sehen, die etwa wie folgt aussehen:

```
Standard Micro PDF417 saved to: C:\Path\To\Project\MicroPdf417.png
GS1 Micro PDF417 saved to: C:\Path\To\Project\GS1MicroPdf417.png
Barcode generation complete.
```

Öffnen Sie die erzeugten PNG‑Dateien mit einem beliebigen Bildbetrachter. Beide Bilder zeigen einen scharfen, kontrastreichen Barcode, der scanbereit ist.

### Erwartetes visuelles Ergebnis

| Barcode‑Typ | Aussehen |
|-------------|----------|
| **Micro PDF417** | Kleines rechteckiges Muster mit 4 Spalten, lesbar von den meisten 2‑D‑Barcode‑Scannern. |
| **GS1 Micro PDF417** | Gleiche Größe, aber kodiert GS1‑AIs; ein Scanner, der GS1 versteht, gibt die GTIN und die Seriennummer zurück. |

Falls ein Scanner das Bild nicht lesen kann, versuchen Sie, `XDimension.Pixels` auf **3** oder **4** zu erhöhen oder die Spaltenanzahl für den Standard‑Micro‑PDF417 zu reduzieren.

## Häufige Fallstricke und wie man sie vermeidet

| Problem | Ursache | Lösung |
|---------|---------|--------|
| Verschwommener Barcode nach dem Druck | Niedrige DPI‑Druckereinstellungen | PNG mit 300 dpi oder höher exportieren oder den Druckertreiber die Skalierung übernehmen lassen. |
| Scanner gibt „invalid data“ zurück | Fehlendes oder fehlerhaftes GS1‑AI‑Format | Stellen Sie sicher, dass jedes AI in Klammern gesetzt ist und der GS1‑Spezifikation entspricht (z. B. `(01)` für GTIN‑14). |
| Bilddatei nicht erstellt | Ausgabeverzeichnis hat keine Schreibberechtigung | Programm mit erhöhten Rechten ausführen oder einen Ordner wie `Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments)` wählen. |
| Barcode zu groß für das Etikett | Standard‑Spaltenanzahl zu hoch | `Pdf417.Columns` reduzieren (z. B. auf **3**) oder `XDimension` erhöhen, um die Gesamtabmessungen zu verkleinern. |

## Erweiterung des Beispiels

* **Verschiedene Bildformate** – Ersetzen Sie `BarCodeImageFormat.Png` durch `Jpeg` oder `Bmp`, falls Ihr Workflow dies erfordert. PNG bleibt die beste Wahl für verlustfreie Qualität.  
* **Dynamische Daten** – Übergeben Sie Benutzereingaben oder Datenbankwerte an den `BarcodeGenerator`‑Konstruktor, um Barcodes on‑the‑fly zu erzeugen.  
* **Stapelverarbeitung** – Kapseln Sie die Erstellungslogik in einer Schleife, die Zeilen aus einer CSV‑Datei liest und jeden Barcode mit einem eindeutigen Dateinamen speichert.

## Fazit

Sie wissen jetzt, wie man **Micro PDF417 Barcode** in C# **erstellt** und **den Barcode in PNG konvertiert** für sowohl Standard‑ als auch GS1‑konforme Szenarien. Der vollständige, ausführbare Code demonstriert die wesentlichen Einstellungen – X‑Dimension, Spaltenanzahl und Codierungstyp – sodass Sie die Lösung an jedes .NET‑Projekt anpassen können, das kompakte, hochwertige 2‑D‑Barcodes benötigt.

*Weiterführende Schritte*: Erkunden Sie weitere von Aspose.BarCode unterstützte Symbolarten (z. B. QR, DataMatrix), experimentieren Sie mit unterschiedlichen `XDimension`‑Werten für hochauflösenden Druck oder integrieren Sie die erzeugten PNGs in eine Web‑API, die Barcodes auf Abruf bereitstellt.

## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Codebeispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, zusätzliche API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [Wie man Micro PDF417 Barcode in C# erstellt und als PNG speichert](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-and-save-it-as-png/)
- [Barcode PNG in C# erstellen – vollständiger Leitfaden zu GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [Micro PDF417 Barcode in C# generieren – Komplett‑Leitfaden](/barcode/english/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
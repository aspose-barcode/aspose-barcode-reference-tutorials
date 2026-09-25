---
category: general
date: 2026-08-22
description: Erstellen Sie einen FCC‑11‑Barcode in C# mit Aspose.BarCode. Lernen Sie
  den Schritt‑für‑Schritt‑Code, konfigurieren Sie die Abmessungen und erzeugen Sie
  PNG‑Bilder für Australia Post.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create fcc 11 barcode
- Australia Post barcode
- Aspose.BarCode C#
- FCC 59 barcode
- FCC 62 barcode
- N‑Table encoding
- C‑Table encoding
language: de
lastmod: 2026-08-22
og_description: Erstellen Sie den FCC‑11‑Strichcode in C# mit Aspose.BarCode. Folgen
  Sie diesem kurzen Tutorial, um PNG‑Strichcodes für Australia Post zu erzeugen, einschließlich
  der Varianten FCC 59 und FCC 62.
og_image_alt: Screenshot showing a generated FCC 11 barcode image
og_title: Erstellen Sie einen FCC‑11‑Barcode in C# – vollständiger Aspose.BarCode‑Leitfaden
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  headline: How to create FCC 11 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  name: How to create FCC 11 barcode in C# with Aspose.BarCode
  steps:
  - name: 4.1 FCC 59 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)'
  - name: 4.2 FCC 62 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)'
  - name: 4.3 FCC 62 with C‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix'
  - name: 4.4 FCC 62 with Other encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567321032103210"); // Long payload for "Other" table'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- AustraliaPost
title: Wie man einen FCC‑11-Barcode in C# mit Aspose.BarCode erstellt
url: /de/python-java/general/how-to-create-fcc-11-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man einen FCC 11‑Barcode in C# mit Aspose.BarCode erstellt

Wenn Sie einen **FCC 11‑Barcode** in einer .NET‑Anwendung **erstellen** müssen, zeigt Ihnen diese Anleitung den genauen Code, der dafür erforderlich ist. Sie sehen, wie Sie die Barcode‑Abmessungen konfigurieren, die richtige Codierungstabelle auswählen und das Ergebnis als PNG‑Datei speichern.

Das Erzeugen von Australia‑Post‑Barcodes ist eine häufige Anforderung in Logistik, Versand‑Systemen und Bestandsverfolgung. Dieses Tutorial behandelt das FCC 11‑Format und demonstriert zudem, wie Sie FCC 59‑ und FCC 62‑Barcodes mit verschiedenen Codierungstabellen erzeugen können, sodass Sie das gleiche Muster für andere Postdienste wiederverwenden können.

## Was Sie benötigen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

* .NET 6.0 SDK oder später installiert  
* Visual Studio 2022 (oder jede C#‑kompatible IDE)  
* Eine gültige Lizenz für **Aspose.BarCode for .NET** – die Community‑Edition funktioniert für Evaluierungen  
* Schreibrechte für einen Ordner, in dem die PNG‑Dateien gespeichert werden  

Diese Voraussetzungen garantieren, dass der Code kompiliert und ohne zusätzliche Konfiguration ausgeführt wird.

## Schritt 1: Das Aspose.BarCode‑NuGet‑Paket installieren

Öffnen Sie ein Terminal im Projektordner und führen Sie aus:

```bash
dotnet add package Aspose.BarCode
```

Der Befehl fügt die neueste stabile Version der Bibliothek zu Ihrer Projektdatei hinzu. Das Paket enthält die Klasse `BarcodeGenerator`, die in diesem Tutorial durchgehend verwendet wird.

## Schritt 2: Den Ausgabepfad festlegen

Erstellen Sie einen Ordner, in dem die erzeugten Bilder gespeichert werden. Der Pfad kann absolut oder relativ zur ausführbaren Datei sein.

```csharp
// Step 2: Define the output folder
string outputPath = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputPath);
```

`Directory.CreateDirectory` stellt sicher, dass der Ordner existiert und verhindert Laufzeitfehler, wenn die `Save`‑Methode die Datei schreibt.

## Schritt 3: Den FCC 11‑Barcode generieren

Das FCC 11‑Format ist die Standard‑Codierung für die Post‑Barcodes von Australia Post. Der folgende Code erzeugt einen Barcode, der die numerische Zeichenkette `1101234567` codiert.

```csharp
// Step 3: Create a BarcodeGenerator for FCC 11
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,      // Use the Australia Post symbology
    "1101234567");                  // Data for FCC 11

// Configure visual appearance
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;   // Width of a single module
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50; // Height of the barcode

// Save as PNG
string fcc11Path = Path.Combine(outputPath, "PostalAustraliaPostFCC11.png");
barcodeGenerator.Save(fcc11Path, BarCodeImageFormat.Png);
```

**Warum das funktioniert:**  
* `EncodeTypes.AustraliaPost` weist die Bibliothek an, die Australia‑Post‑Codierungsregeln anzuwenden.  
* Die Datenzeichenkette `1101234567` entspricht der FCC 11‑Spezifikation: Die ersten beiden Ziffern (`11`) identifizieren das Format, gefolgt von einer 7‑stelligen Kundenreferenz.  
* `XDimension` und `BarHeight` steuern die Größe des gedruckten Barcodes, was für die Lesbarkeit durch Scanner wichtig ist.  

Nach dem Ausführen des Programms finden Sie `PostalAustraliaPostFCC11.png` im Ordner `Barcodes`. Das Bild sieht folgendermaßen aus:

![create fcc 11 barcode example](https://example.com/fcc11.png "FCC 11 barcode generated by Aspose.BarCode")

## Schritt 4: Weitere Australia‑Post‑Barcodes erstellen (optional)

Während das Hauptziel darin besteht, einen **FCC 11‑Barcode zu erstellen**, benötigen Sie häufig FCC 59‑ oder FCC 62‑Barcodes für unterschiedliche Versandklassen. Der untenstehende Code verwendet dieselbe `BarcodeGenerator`‑Instanz und ändert nur die Datenzeichenkette sowie die optionale Codierungstabelle.

### 4.1 FCC 59 mit N‑Table‑Codierung

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;

// Use N‑Table for customer information interpretation
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc59Path = Path.Combine(outputPath, "PostalAustraliaPostFCC59NTable.png");
barcodeGenerator.Save(fcc59Path, BarCodeImageFormat.Png);
```

### 4.2 FCC 62 mit N‑Table‑Codierung

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc62NPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62NTable.png");
barcodeGenerator.Save(fcc62NPath, BarCodeImageFormat.Png);
```

### 4.3 FCC 62 mit C‑Table‑Codierung

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.CTable;

string fcc62CPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62CTable.png");
barcodeGenerator.Save(fcc62CPath, BarCodeImageFormat.Png);
```

### 4.4 FCC 62 mit anderer Codierung

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567321032103210"); // Long payload for "Other" table

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.Other;

string fcc62OtherPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62OtherTable.png");
barcodeGenerator.Save(fcc62OtherPath, BarCodeImageFormat.Png);
```

Alle vier Bilder werden nebeneinander im selben Ordner gespeichert, sodass ein einfacher visueller Vergleich möglich ist.

## Schritt 5: Die Codierungstabellen verstehen

Australia Post definiert drei Codierungstabellen:

* **N‑Table** – interpretiert numerische Kundeninformationen. Verwenden Sie sie, wenn die Nutzlast ausschließlich Ziffern enthält.  
* **C‑Table** – unterstützt alphanumerische Zeichen, nützlich für Referenznummern, die Buchstaben enthalten.  
* **Other** – ein Fallback für benutzerdefinierte oder erweiterte Datenformate.

Die Wahl der richtigen Tabelle stellt sicher, dass der Barcode‑Scanner die Informationen exakt wie beabsichtigt dekodiert. Wenn Sie die Eigenschaft `AustralianPostEncodingTable` weglassen, verwendet die Bibliothek standardmäßig die N‑Table, wodurch nicht‑numerische Zeichen **abgeschnitten** werden können.

## Tipps, Randfälle und häufige Stolperfallen

| Situation | Empfohlener Ansatz |
|-----------|--------------------|
| Die Datenzeichenkette ist kürzer als erforderlich | Füllen Sie den numerischen Teil mit führenden Nullen auf, um die FCC‑Spezifikation zu erfüllen. |
| Der Barcode erscheint beim Druck unscharf | Erhöhen Sie `XDimension` auf 5 oder 6 Pixel und prüfen Sie die DPI‑Einstellungen des Druckers. |
| Der Scanner meldet „invalid format“ | Vergewissern Sie sich, dass die korrekte Codierungstabelle (N‑Table, C‑Table, Other) zur Datenpayload passt. |
| Ausführung unter Linux ohne GUI | Stellen Sie sicher, dass das Paket `System.Drawing.Common` referenziert wird, oder verwenden Sie die `Save`‑Methode mit `BarCodeImageFormat.Png`, die keinen Anzeigekontext benötigt. |
| Ein anderes Bildformat wird benötigt | Ersetzen Sie `BarCodeImageFormat.Png` durch `BarCodeImageFormat.Jpeg` oder `BarCodeImageFormat.Tiff` nach Bedarf. |

Diese praxisnahen Tipps stammen aus realen Einsätzen von Post‑Barcode‑Lösungen.

## Vollständiges ausführbares Beispiel

Unten finden Sie ein eigenständiges Programm, das Sie in ein neues Konsolenprojekt (`dotnet new console`) kopieren und ohne Änderungen ausführen können.



## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Code‑Beispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, weitere API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [Wie man einen Barcode in Java generiert – Australia Post Barcode mit Aspose](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)
- [Ein‑dimensionalen Databar GS1‑Codierung mit Aspose.BarCode erstellen](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Wie man die Quiet‑Zone für Code 16K in .NET mit Aspose.BarCode erstellt](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
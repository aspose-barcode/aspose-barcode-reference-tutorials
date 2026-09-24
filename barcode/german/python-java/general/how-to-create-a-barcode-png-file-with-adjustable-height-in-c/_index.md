---
category: general
date: 2026-08-19
description: Erfahren Sie, wie Sie in C# eine Barcode‑PNG‑Datei erzeugen und deren
  Höhe anpassen können, einschließlich einer Anleitung zum einfachen Erstellen von
  Barcode‑Bildern und Ändern der Barcode‑Höhe.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode png file
- how to generate barcode
- adjust barcode height
- change barcode height
language: de
lastmod: 2026-08-19
og_description: Erstellen Sie eine Barcode‑PNG‑Datei in C# und lernen Sie, wie Sie
  Barcode‑Bilder erzeugen, die Barcode‑Höhe anpassen und die Barcode‑Höhe für optimale
  Scans ändern.
og_image_alt: barcode PNG file showing Databar OmniDirectional barcode at two heights
og_title: Erstelle eine Barcode‑PNG‑Datei in C# – Schritt‑für‑Schritt‑Anleitung
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Learn how to generate a barcode PNG file in C# and adjust its height,
    covering how to generate barcode images and change barcode height easily.
  headline: How to create a barcode PNG file with adjustable height in C#
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`,
      `BarCodeImageFormat.Bmp`, etc.
    question: Can I generate other image formats (JPEG, BMP)?
  - answer: Serve the generated PNG via an HTTP endpoint or convert it to a Base64
      string and place it in an `<img>` tag’s `src` attribute.
    question: How do I embed the PNG in a web page?
  - answer: 'Use `generator.Parameters.Image.BackgroundColor = Color.White;` (or any
      `System.Drawing.Color`). ## Conclusion You now know how to **generate a barcode
      PNG file** in C# and precisely **adjust barcode height** to meet scanning or
      design requirements. By changing the `BarHeight.Pixels` property you ca'
    question: Is there a way to set the background color?
  type: FAQPage
tags:
- barcode
- C#
- image generation
title: Wie man eine Barcode‑PNG‑Datei mit einstellbarer Höhe in C# erstellt
url: /de/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man eine Barcode‑PNG‑Datei mit einstellbarer Höhe in C# erstellt

Wenn Sie eine **Barcode‑PNG‑Datei** in C# erstellen müssen, zeigt Ihnen diese Anleitung genau, wie es geht. Sie sehen ein vollständiges, ausführbares Beispiel, das **wie man Barcode‑Bilder generiert** und **wie man die Barcode‑Höhe** für verschiedene Anwendungsfälle anpasst.

Das Erzeugen einer Barcode‑PNG‑Datei ist eine gängige Anforderung für Inventursysteme, Point‑of‑Sale‑Terminals und jede Anwendung, die maschinenlesbare Daten drucken oder anzeigen muss. Am Ende dieses Tutorials können Sie die Barcode‑Höhe ändern, mehrere PNG‑Dateien speichern und die Auswirkung der Höhe auf die Scan‑Zuverlässigkeit verstehen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

* .NET 6.0 SDK oder neuer installiert  
* Visual Studio 2022 (oder jede IDE, die .NET unterstützt)  
* Das **Aspose.BarCode for .NET** NuGet‑Paket (der Code‑Beispiel verwendet diese Bibliothek)  

Sie können das Paket über die Befehlszeile hinzufügen:

```bash
dotnet add package Aspose.BarCode
```

> **Pro Tipp:** Die kostenlose Evaluierungsversion von Aspose.BarCode funktioniert für Entwicklung und Tests. Für die Produktion benötigen Sie einen lizenzierten Schlüssel.

## Barcode‑Bibliothek installieren

Der erste Schritt besteht darin, die Bibliothek in Ihrem Projekt zu referenzieren. Fügen Sie die folgenden `using`‑Direktiven am Anfang Ihrer C#‑Datei hinzu:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Diese Namespaces geben Ihnen Zugriff auf `BarcodeGenerator`, `EncodeTypes` und `BarCodeImageFormat`.

## Die Barcode‑PNG‑Datei erstellen

Jetzt erstellen wir eine `BarcodeGenerator`‑Instanz, die eine **Barcode‑PNG‑Datei** ausgibt. Das Beispiel verwendet die Databar OmniDirectional‑Symbologie, Sie können jedoch `EncodeTypes.DatabarOmniDirectional` durch jeden unterstützten Typ ersetzen.

```csharp
// Step 1: Create a DataBar Omnidirectional generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Der String `"(01)12345678901231"` folgt dem GS1‑Application‑Identifier‑Format für eine 14‑stellige GTIN. Passen Sie die Daten an Ihre eigenen Produktkennzeichnungen an.

## X‑Dimension festlegen (optional)

Die X‑Dimension definiert die Breite eines einzelnen Barcode‑Moduls. Ein pixelbasierter Wert gibt Ihnen präzise Kontrolle über die Bildgröße.

```csharp
// Optional: Set the pixel size of the X‑dimension (module width)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Ein Wert von `2` Pixel funktioniert gut für die meisten Bildschirme. Erhöhen Sie ihn, wenn Sie einen größeren Barcode für den Druck benötigen.

## Barcode‑Höhe anpassen und die Barcode‑PNG‑Datei speichern

Die Eigenschaft **BarHeight** steuert die vertikale Größe der Balken. Durch Ändern dieses Wertes können Sie die **Barcode‑Höhe** anpassen, ohne die codierten Daten zu beeinflussen.

```csharp
// Step 2: Generate a 30‑pixel‑high barcode and save it as PNG
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Die Datei `DatabarBarHeight30Pixels.png` ist nun eine **Barcode‑PNG‑Datei**, die 30 Pixel hoch ist.  

Um die **Barcode‑Höhe** zu ändern und ein zweites Bild zu erstellen, weisen Sie einfach einen neuen Wert zu und rufen `Save` erneut auf:

```csharp
// Step 3: Change the height to 60 pixels and save the new image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
barcodeGenerator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Sie haben jetzt zwei PNG‑Dateien – eine mit 30 px und eine mit 60 px – die zeigen, wie man die **Barcode‑Höhe** on‑the‑fly anpasst.

### Warum die Balkenhöhe wichtig ist

* **Lesbarkeit:** Scanner erwarten eine Mindesthöhe für zuverlässige Erkennung. Ein zu kurzer Barcode kann übersehen werden, besonders bei Kameras mit niedriger Auflösung.  
* **Ästhetik:** Die Anpassung der Barcode‑Höhe an umliegende Designelemente sorgt für ein saubereres UI.  
* **Druckbeschränkungen:** Einige Etikettendrucker haben feste Höhen‑Slots; das Anpassen der Barcode‑Höhe stellt sicher, dass er passt.

**Best Practice:** Halten Sie die Höhe ein Vielfaches der X‑Dimension (z. B. 30 px bei einer X‑Dimension von 2 px), um das Seitenverhältnis zu bewahren und Verzerrungen zu vermeiden.

## Komplettes Beispiel

Unten finden Sie das vollständige, eigenständige Programm, das Sie in eine Konsolenanwendung einfügen und sofort ausführen können.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator with Databar OmniDirectional data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set a reasonable X‑dimension (module width)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First height: 30 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode as DatabarBarHeight30Pixels.png");

        // 4️⃣ Second height: 60 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode as DatabarBarHeight60Pixels.png");
    }
}
```

**Erwartete Ausgabe**

Beim Ausführen des Programms werden zwei Dateien im Arbeitsverzeichnis der ausführbaren Datei erstellt:

* `DatabarBarHeight30Pixels.png` – eine 30 Pixel‑hohe Barcode‑PNG‑Datei  
* `DatabarBarHeight60Pixels.png` – eine 60 Pixel‑hohe Barcode‑PNG‑Datei  

Öffnen Sie eine der PNG‑Dateien mit einem beliebigen Bildbetrachter; Sie sehen einen klaren Databar OmniDirectional‑Barcode, bereit zum Scannen.

## Randfälle und Fehlersuche

| Situation | Was zu prüfen ist | Empfohlene Lösung |
|-----------|-------------------|-------------------|
| Barcode erscheint unscharf | X‑Dimension zu niedrig für die gewählte Höhe | Erhöhen Sie `XDimension.Pixels` (z. B. von 2 auf 3) |
| Scanner schlägt bei niedriger Barcode‑Höhe fehl | Höhe liegt unter dem Minimum des Scanners | Setzen Sie `BarHeight.Pixels` auf mindestens 30 px (oder gemäß Scanner‑Spezifikationen) |
| PNG‑Datei ist leer oder beschädigt | Ausgabepfad ungültig oder Schreibrechte fehlen | Verwenden Sie einen absoluten Pfad oder stellen Sie sicher, dass die Anwendung Schreibzugriff hat |
| Andere Symbologie benötigt | Aktuelles `EncodeTypes` ist nicht geeignet | Ersetzen Sie `EncodeTypes.DatabarOmniDirectional` durch einen anderen Enum‑Wert (z. B. `EncodeTypes.Code128`) |

## Häufig gestellte Fragen

**F: Kann ich andere Bildformate (JPEG, BMP) erzeugen?**  
A: Ja. Ersetzen Sie `BarCodeImageFormat.Png` durch `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp` usw.

**F: Wie binde ich das PNG in eine Webseite ein?**  
A: Stellen Sie das erzeugte PNG über einen HTTP‑Endpunkt bereit oder konvertieren Sie es in einen Base64‑String und setzen Sie ihn in das `src`‑Attribut eines `<img>`‑Tags.

**F: Gibt es eine Möglichkeit, die Hintergrundfarbe zu setzen?**  
A: Verwenden Sie `generator.Parameters.Image.BackgroundColor = Color.White;` (oder jede `System.Drawing.Color`).

## Fazit

Sie wissen jetzt, wie man **eine Barcode‑PNG‑Datei** in C# generiert und die **Barcode‑Höhe** präzise **anpasst**, um Scan‑ oder Design‑Anforderungen zu erfüllen. Durch Ändern der Eigenschaft `BarHeight.Pixels` können Sie die **Barcode‑Höhe** on‑the‑fly ändern und mehrere PNG‑Assets aus einer einzigen Codebasis erzeugen.

Als Nächstes können Sie weitere Anpassungsoptionen erkunden, etwa Vordergrundfarbe, Ränder und das Hinzufügen von menschenlesbarem Text. Experimentieren Sie auch mit verschiedenen Symbologien (`EncodeTypes.Code128`, `EncodeTypes.QR`), um das Spektrum der codierbaren Daten zu erweitern.

Viel Spaß beim Coden und möge Ihr Barcode beim ersten Versuch immer scannen!

## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Codebeispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, weitere API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
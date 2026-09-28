---
category: general
date: 2026-07-15
description: Erstellen Sie schnell einen omnidirektionalen Barcode in C# mit Aspose.BarCode
  – lernen Sie, wie Sie einen Barcode in C# mit einstellbarer Balkenhöhe und X‑Dimension
  generieren.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni-directional barcode
- how to generate barcode c#
- GS1 DataBar Omni-Directional
- barcode XDimension
- barcode BarHeight
language: de
lastmod: 2026-07-15
og_description: Erstellen Sie einen omnidirektionalen Barcode in C# mit Aspose.BarCode.
  Lernen Sie, wie Sie Barcodes in C# erzeugen, indem Sie XDimension und BarHeight
  anpassen, für perfekte Ergebnisse.
og_image_alt: Screenshot showing a create omni-directional barcode generated in C#
  with 60 px bar height
og_title: Erstelle einen omnidirektionalen Barcode in C# – Vollständige Programmieranleitung
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  headline: create omni-directional barcode in C# – Step‑by‑Step Guide
  type: TechArticle
- description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  name: create omni-directional barcode in C# – Step‑by‑Step Guide
  steps:
  - name: Expected output
    text: '- `DatabarBarHeight30Pixels.png` – a 30 px tall omni‑directional barcode.
      - `DatabarBarHeight60Pixels.png` – the same data, but with a 60 px tall barcode.'
  - name: What if I need a different X‑dimension?
    text: Simply assign a new value before calling `Save`. For ultra‑high‑density
      printing you might go down to 1 px, but test with your scanner first—some devices
      struggle with sub‑2 px bars.
  - name: Can I add human‑readable text below the barcode?
    text: Yes. Set `barcodeGenerator.Parameters.Barcode.CodeText` to a string and
      optionally adjust `barcodeGenerator.Parameters.Barcode.CodeLocation` to `BarCodeTextLocation.Below`.
      This is handy for retail environments where the numeric GTIN must be visible.
  - name: Is PNG the best format for printing?
    text: PNG is lossless, which preserves the sharp edges needed for barcode scanners.
      If your downstream system expects a different format (TIFF, BMP), just change
      the `BarCodeImageFormat` enum.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- GS1
- DataBar
title: Erstelle einen omnidirektionalen Barcode in C# – Schritt‑für‑Schritt‑Anleitung
url: /de/python-java/general/create-omni-directional-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Omni‑directional Barcode in C# erstellen – Schritt‑für‑Schritt‑Anleitung

Haben Sie sich schon einmal gefragt, wie man einen Barcode in C# erzeugt, der der GS1 DataBar Omni‑Directional‑Symbologie entspricht? Sie sind nicht allein. In diesem Tutorial **erstellen wir Omni‑directional Barcode**‑Bilder von Grund auf, passen die X‑Dimension an und spielen mit der Balkenhöhe – alles mit der Aspose.BarCode‑Bibliothek.

Wir gehen ein reales Szenario durch: Sie benötigen einen kompakten, hochdichten Barcode für ein Einzelhandels‑Etikett und wollen die visuelle Größe vollständig kontrollieren. Am Ende haben Sie zwei PNG‑Dateien – eine mit 30 px Balkenhöhe und eine mit 60 px – bereit, in jeden Druck‑Workflow eingebunden zu werden.

## Voraussetzungen

- .NET 6 (oder irgendeine aktuelle .NET‑Runtime) auf Ihrem Rechner installiert.  
- Visual Studio 2022 oder VS Code – Ihre bevorzugte IDE reicht aus.  
- Das kostenlose Aspose.BarCode für .NET NuGet‑Paket (`Aspose.BarCode`).

Weitere Abhängigkeiten werden nicht benötigt. Wenn Sie noch nie mit NuGet gearbeitet haben, öffnen Sie einfach die Package Manager Console und führen Sie aus:

```powershell
Install-Package Aspose.BarCode
```

## Omni‑directional Barcode erstellen – Grundlagen verstehen

Die **GS1 DataBar Omni‑Directional**‑Symbologie ist für das Scannen in jeder Orientierung ausgelegt und damit ideal für Regalkanten‑Etiketten. Wenn Sie `new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data)` aufrufen, übernimmt die Bibliothek die schwere Arbeit: Sie kodiert die Daten, wendet die Symbologie‑Regeln an und erzeugt ein Raster‑Bild.

> **Pro‑Tipp:** Verpacken Sie die Rohdaten immer im passenden Application Identifier (AI)‑Format, z. B. `"(01)12345678901231"` für eine GTIN‑14. Das teilt dem Scanner mit, was die Ziffern bedeuten.

## Schritt 1 – Barcode‑Generator einrichten (how to generate barcode c#)

Zuerst erstellen wir das Generator‑Objekt. Dies ist das Fundament von **how to generate barcode c#** mit Aspose.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for the GS1 DataBar Omni‑Directional symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Der Enum‑Wert `EncodeTypes.DatabarOmniDirectional` sagt der Engine, welche Symbologie verwendet werden soll. Das zweite Argument ist der bereits im GTIN‑AI verpackte Rohdaten‑String.

## Schritt 2 – X‑Dimension anpassen (barcode XDimension)

Die **barcode XDimension** steuert die Breite des kleinsten Balkens. Ein Wert von 2 px ist für die meisten Etikettendrucker ein guter Kompromiss zwischen Lesbarkeit und Kompaktheit.

```csharp
// Step 2: Define common barcode parameters (2 px X‑dimension)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Wenn Sie ein feineres oder gröberes Aussehen benötigen, ändern Sie einfach die Zahl. Denken Sie daran: Die X‑Dimension ist die Basiseinheit; alle anderen Balkenbreiten sind Vielfache dieses Werts.

## Schritt 3 – Erstes Bild mit 30 px Balkenhöhe erstellen (barcode BarHeight)

Jetzt setzen wir die **barcode BarHeight** auf 30 px und speichern das Bild. Das erzeugt einen bescheiden großen Barcode, der gut auf ein Standard‑Etikett passt.

```csharp
// Step 3: Set a 30 px bar height and save the first image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Die `Save`‑Methode schreibt eine PNG‑Datei auf die Festplatte. Sie können `BarCodeImageFormat.Jpeg` verwenden, wenn Sie lieber JPEG ausgeben möchten.

## Schritt 4 – Balkenhöhe auf 60 px erhöhen für größere Etiketten (barcode BarHeight)

Manchmal wird ein größerer Barcode benötigt – etwa für ein Regaletikett, das weiter vom Scanner entfernt ist. Wir verdoppeln die Höhe.

```csharp
// Step 4: Increase the bar height to 60 px for a larger barcode
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

Beachten Sie, dass wir **nicht** den Generator neu erstellen müssen; wir passen nur den Parameter an und verwenden dasselbe Objekt weiter. Das spart Speicher und hält den Code übersichtlich.

## Schritt 5 – Zweites Bild speichern (how to generate barcode c#)

Abschließend speichern wir das zweite PNG. Sie haben nun zwei Dateien, die sich nur in der Balkenhöhe unterscheiden.

```csharp
// Step 5: Save the second image with the updated height
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

### Erwartete Ausgabe

- `DatabarBarHeight30Pixels.png` – ein 30 px hoher Omni‑directional Barcode.  
- `DatabarBarHeight60Pixels.png` – dieselben Daten, aber mit 60 px hoher Barcode.

Öffnen Sie die Dateien in einem Bildbetrachter; Sie sehen scharfe, scanbare Balken, die die GS1 DataBar Omni‑Directional‑Spezifikation einhalten.

## Häufige Fragen & Sonderfälle

### Was, wenn ich eine andere X‑Dimension benötige?

Weisen Sie einfach vor dem Aufruf von `Save` einen neuen Wert zu. Für ultra‑hochdichten Druck können Sie auf 1 px gehen, testen Sie jedoch zuerst mit Ihrem Scanner – manche Geräte haben Probleme mit Balken unter 2 px.

### Kann ich lesbaren Text unter dem Barcode hinzufügen?

Ja. Setzen Sie `barcodeGenerator.Parameters.Barcode.CodeText` auf einen String und passen Sie optional `barcodeGenerator.Parameters.Barcode.CodeLocation` zu `BarCodeTextLocation.Below` an. Das ist praktisch im Einzelhandel, wo die numerische GTIN sichtbar sein muss.

```csharp
barcodeGenerator.Parameters.Barcode.CodeText = "(01)12345678901231";
barcodeGenerator.Parameters.Barcode.CodeLocation = BarCodeTextLocation.Below;
```

### Ist PNG das beste Format für den Druck?

PNG ist verlustfrei und bewahrt die scharfen Kanten, die Barcode‑Scanner benötigen. Wenn Ihr nachgelagertes System ein anderes Format erwartet (TIFF, BMP), ändern Sie einfach das `BarCodeImageFormat`‑Enum.

## Komplettes funktionierendes Beispiel (create omni-directional barcode)

Unten finden Sie das vollständige, sofort ausführbare Programm. Kopieren Sie es in ein neues Konsolen‑Projekt und drücken Sie **F5**.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace OmniDirectionalDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create generator for GS1 DataBar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension (2 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ Second image – 60 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two omni‑directional barcodes created successfully.");
        }
    }
}
```

Programm starten, den Ausgabepfad prüfen, und Sie sehen die beiden PNG‑Dateien exakt wie beschrieben.

## Zusammenfassung

Wir haben gezeigt, **wie man Barcode C#**‑Code schreibt, der einen **create omni-directional barcode** mit Aspose.BarCode erzeugt. Durch Anpassen der **barcode XDimension** und **barcode BarHeight** erhalten Sie feine Kontrolle über die visuelle Größe, ohne die Scan‑Zuverlässigkeit zu beeinträchtigen.

## Was kommt als Nächstes?

- Experimentieren Sie mit anderen **GS1 DataBar Omni-Directional**‑Einstellungen wie `Color` oder `Margin`.  
- Kombinieren Sie mehrere Barcodes auf einer einzigen Zeichenfläche mittels `Graphics` für komplexe Etikettendesigns.  
- Integrieren Sie den Generator in eine Web‑API, damit Ihre E‑Commerce‑Plattform Barcodes on‑demand erzeugen kann.

Haben Sie eine eigene Idee, die Sie teilen möchten? Hinterlassen Sie einen Kommentar, und lassen Sie uns die Diskussion fortsetzen. Viel Spaß beim Coden!

## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Code‑Beispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, weitere API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [How to create barcode quiet zone for Code 16K using Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
---
category: general
date: 2026-11-14
description: Barcode‑Generator‑C#‑Tutorial, das zeigt, wie man DataBar‑Omnidirectional‑Barcodes
  erstellt, die X‑Dimension festlegt und die Bar‑Höhe in Pixeln anpasst.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c# tutorial
- DataBar Omnidirectional
- set bar height
- XDimension pixels
- BarCodeImageFormat PNG
language: de
lastmod: 2026-11-14
og_description: Das C#‑Tutorial zum Barcode‑Generator erklärt Schritt für Schritt,
  wie man einen DataBar Omnidirectional‑Barcode erzeugt, die XDimension in Pixeln
  definiert und die Balkenhöhe für die PNG‑Ausgabe ändert.
og_image_alt: Screenshot of barcode generator C# tutorial output showing a DataBar
  barcode
og_title: Barcode‑Generator C#‑Tutorial – DataBar‑Barcodes erstellen
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Barcode generator C# tutorial that shows how to create DataBar Omnidirectional
    barcodes, set X‑dimension, and adjust bar height in pixels.
  headline: 'Barcode generator C# tutorial: DataBar Omnidirectional'
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- tutorial
title: 'Barcode-Generator C#‑Tutorial: DataBar Omnidirectional'
url: /de/python-java/general/barcode-generator-c-tutorial-databar-omnidirectional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode‑Generator C# Tutorial – DataBar Omnidirectional Barcodes erstellen

Wenn Sie nach einem **barcode generator C# tutorial** suchen, sind Sie hier genau richtig. Dieser Leitfaden führt Sie Schritt für Schritt durch das Erstellen eines DataBar Omnidirectional Barcodes, das Konfigurieren der XDimension in Pixeln und das Anpassen der Balkenhöhe, um PNG‑Bilder zu erzeugen.

Sie sehen ein vollständiges, ausführbares Beispiel, das alles abdeckt – vom Initialisieren des Generators bis zum Speichern mehrerer Bilder mit unterschiedlichen Balkenhöhen. Keine externe Dokumentation nötig – einfach den Code kopieren, ausführen und Sie erhalten zwei Barcode‑Dateien, die einsatzbereit sind.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie folgendes haben:

* .NET 6.0 oder höher installiert  
* Eine Referenz zur Barcode‑Bibliothek, die `BarcodeGenerator`, `EncodeTypes` und `BarCodeImageFormat` bereitstellt (z. B. Aspose.BarCode für .NET)  
* Grundlegende Kenntnisse der C#‑Syntax und von Visual Studio oder Ihrer bevorzugten IDE  

> **Pro‑Tipp:** Wenn Sie Aspose.BarCode verwenden, fügen Sie das NuGet‑Paket `Aspose.BarCode` zu Ihrem Projekt hinzu.

## Barcode‑Generator C# Tutorial – Schritt 1: Generator erstellen

Der erste Schritt besteht darin, einen `BarcodeGenerator` mit dem Encode‑Typ `DatabarOmniDirectional` und den zu kodierenden Daten zu instanziieren.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Omnidirectional barcode generator with the desired data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

*Warum das wichtig ist:* `EncodeTypes.DatabarOmniDirectional` weist die Bibliothek an, einen Barcode zu erzeugen, der aus jeder Richtung gelesen werden kann – ideal für Einzelhandelsverpackungen und Logistik.

## XDimension in Pixeln für den Barcode festlegen

Die X‑Dimension definiert die Breite des kleinsten Moduls (des „Pixels“) im Barcode. Die Angabe in Pixeln gibt Ihnen präzise Kontrolle über die visuelle Dichte des Barcodes.

```csharp
        // Step 2: Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Erklärung:* Ein Wert von `2` Pixeln liefert einen Barcode, der für die meisten Scanner scharf genug ist und gleichzeitig die Dateigröße moderat hält.

## Balkenhöhe anpassen und Bilder speichern

Die Balkenhöhe bestimmt, wie hoch die Striche erscheinen. Sie können mehrere Bilder mit unterschiedlichen Höhen erzeugen, indem Sie die Eigenschaft `BarHeight.Pixels` ändern und erneut `Save` aufrufen.

```csharp
        // Step 3: Set the bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        string outputPath = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
```

Der Enum‑Wert `BarCodeImageFormat.Png` stellt sicher, dass die Ausgabe eine verlustfreie PNG‑Datei ist, das empfohlene Format für Barcode‑Grafiken, weil es die exakten Abmessungen bewahrt.

## Balkenhöhe ändern, um mehrere Bilder zu erzeugen

Oft benötigen Sie denselben Barcode in verschiedenen Größen – zum Beispiel einen für ein kleines Etikett und einen anderen für ein großes Plakat. Ändern Sie die Balkenhöhe und verwenden Sie dieselbe Generator‑Instanz erneut:

```csharp
        // Step 4: Change the bar height to 60 px and save a second image
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        outputPath = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
    }
}
```

*Randfall:* Wird die Balkenhöhe zu niedrig eingestellt (z. B. unter 10 px), können einige Scanner Schwierigkeiten haben, den Code zu lesen. Testen Sie die erzeugten Bilder stets mit Ihrer Ziel‑Scanner‑Hardware.

## Vollständiger Quellcode

Unten finden Sie das komplette Programm, das Sie in ein neues Konsolen‑Projekt kopieren‑und‑einfügen können. Es enthält alle erforderlichen `using`‑Direktiven und demonstriert beide Varianten der Balkenhöhe.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a DataBar Omnidirectional barcode generator
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Set XDimension to 2 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image – 30 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
            generator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 30 px barcode to {path30}");

            // Second image – 60 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
            generator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 60 px barcode to {path60}");
        }
    }
}
```

Führen Sie das Programm aus, ersetzen Sie `YOUR_DIRECTORY` durch einen gültigen Ordnerpfad, und Sie finden zwei PNG‑Dateien:

* `DatabarBarHeight30Pixels.png` – 30 px hohe Balken  
* `DatabarBarHeight60Pixels.png` – 60 px hohe Balken  

![Barcode‑Generator C# Tutorial Ausgabe](images/databar-example.png "Barcode‑Generator C# Tutorial zeigt zwei DataBar‑Bilder")

## Häufige Fragen

| Frage | Antwort |
|----------|--------|
| **Kann ich das Bildformat ändern?** | Ja. Ersetzen Sie `BarCodeImageFormat.Png` durch `Jpeg`, `Bmp` oder `Gif`, je nach Bedarf. PNG wird für verlustfreie Qualität bevorzugt. |
| **Was, wenn ich eine andere XDimension benötige?** | Passen Sie `generator.Parameters.Barcode.XDimension.Pixels` auf einen beliebigen ganzzahligen Wert an. Größere Werte erhöhen die Gesamtlänge des Barcodes. |
| **Ist der DataBar Omnidirectional für mobiles Scannen geeignet?** | Ja, vorausgesetzt, die gedruckte Größe erfüllt die Mindestmodulgröße des Scanners (in der Regel 0,33 mm). Die pixelbasierte XDimension hilft Ihnen, diese Anforderung zu erfüllen. |
| **Wie bette ich den Barcode in ein PDF ein?** | Nachdem Sie das PNG gespeichert haben, verwenden Sie eine PDF‑Bibliothek (z. B. iTextSharp), um das Bild in eine PDF‑Seite einzufügen. |

## Fazit

Dieses **barcode generator C# tutorial** hat Ihnen gezeigt, wie Sie einen DataBar Omnidirectional Barcode erstellen, die XDimension in Pixeln festlegen und PNG‑Dateien mit unterschiedlichen Balkenhöhen generieren. Sie verfügen nun über ein wiederverwendbares Code‑Snippet, das Sie in jedem C#‑Projekt einsetzen können, das Barcode‑Erstellung erfordert.

### Was kommt als Nächstes?

* Erkunden Sie weitere `EncodeTypes` wie `Code128` oder `QR`, um Ihr Barcode‑Repertoire zu erweitern.  
* Kombinieren Sie das erzeugte PNG mit einer PDF‑Generierungsbibliothek, um druckbare Rechnungen zu erstellen.  
* Experimentieren Sie mit `generator.Parameters.Barcode.Color`, um benutzerdefinierte Farben hinzuzufügen und gleichzeitig die Scanner‑Spezifikationen einzuhalten.

Passen Sie das Beispiel gern an, probieren Sie weitere Balkenhöhen aus oder wechseln Sie das Ausgabeformat. Viel Spaß beim Coden!

## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Code‑Beispiele mit Schritt‑für‑Schritt‑Erklärungen, damit Sie zusätzliche API‑Funktionen meistern und alternative Implementierungsansätze in Ihren eigenen Projekten erkunden können.

- [Wie man Breite festlegt und Höhe für einen GS1 DataBar Omni‑Directional Barcode einstellt](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [Wie man die Barcode‑Höhe festlegt, DataBar‑Barcode in C# generiert](/barcode/english/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/)
- [Wie man einen omnidirektionalen Databar‑Barcode in C# erstellt](/barcode/english/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
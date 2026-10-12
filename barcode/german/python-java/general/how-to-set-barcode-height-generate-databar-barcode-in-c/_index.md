---
category: general
date: 2026-10-12
description: Wie man die Barcode‑Höhe einstellt und einen DataBar‑Barcode in C# mit
  Aspose.BarCode erzeugt. Folgen Sie einer Schritt‑für‑Schritt‑Anleitung mit vollständigem
  Code.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- generate barcode c#
- how to create databar
- create databar barcode
- change barcode height
language: de
lastmod: 2026-10-12
og_description: Wie man die Barcode‑Höhe in C# festlegt und einen DataBar‑Barcode
  mit Aspose.BarCode erzeugt. Lernen Sie den vollständigen Code, warum jeder Schritt
  wichtig ist, und wie man die Barcode‑Höhe ändert.
og_image_alt: Screenshot showing how to set barcode height in a C# barcode generator
og_title: Wie man die Barcode-Höhe festlegt und einen DataBar-Barcode in C# erzeugt
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to set barcode height and generate a DataBar barcode in C# using
    Aspose.BarCode. Follow a step‑by‑step guide with complete code.
  headline: How to set barcode height, generate DataBar barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Wie man die Barcode-Höhe einstellt und DataBar-Barcode in C# generiert
url: /de/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man die Barcode‑Höhe einstellt und DataBar‑Barcode in C# generiert

Wenn Sie die **Barcode‑Abmessungen** programmgesteuert festlegen müssen, zeigt Ihnen diese Anleitung die genauen Schritte. Sie lernen, wie man einen DataBar Omni‑directional Barcode erzeugt, seine Höhe anpasst und beide Versionen als PNG‑Dateien speichert.

Das Ändern der Balkenhöhe eines Barcodes ist ein häufiges Anliegen, wenn Sie Barcodes in Kassenbons, Produktetiketten oder mobilen Bildschirmen integrieren. Das nachstehende Beispiel verwendet die Aspose.BarCode‑Bibliothek, die das gesamte Spektrum der GS1 DataBar‑Symbologien unterstützt.

## Was Sie erreichen werden

* **wie man den Barcode** Höhe für einen DataBar Omni‑directional Barcode einstellen  
* **Barcode in C# generieren** Code, der zwei Bilder mit unterschiedlichen Höhen erstellt  
* verstehen, **wie man Databar**‑Symbole erstellt und warum die Balkenhöhe wichtig ist  
* **Barcode‑Höhe ändern** Logik anwenden, ohne den Generator neu zu erstellen  

Keine externen Werkzeuge sind erforderlich, außer dem Aspose.BarCode NuGet‑Paket und einer .NET 6+‑Laufzeit.

## Voraussetzungen

* .NET 6 SDK oder neuer installiert
* Visual Studio 2022 (oder ein beliebiger C#‑Editor)
* Aspose.BarCode für .NET – Installation über `dotnet add package Aspose.BarCode`

> **Profi‑Tipp:** Verwenden Sie die kostenlose Testlizenz von Aspose, wenn Sie keinen kommerziellen Schlüssel besitzen; die API funktioniert genauso.

## Schritt 1: Das Aspose.BarCode‑Paket installieren

Öffnen Sie ein Terminal in Ihrem Projektordner und führen Sie aus:

```bash
dotnet add package Aspose.BarCode
```

Das Paket fügt den Namespace `Aspose.BarCode` hinzu, der die Klasse `BarcodeGenerator` enthält, die wir verwenden werden, um **Barcode in C#**‑Bilder zu **generieren**.

## Schritt 2: Einen DataBar‑Barcode‑Generator erstellen

Die erste konkrete Aktion für **wie man den Barcode**‑Parameter ist, `BarcodeGenerator` mit der gewünschten Symbologie und Datenzeichenfolge zu instanziieren.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 2: Initialize the generator for a DataBar Omni‑directional barcode
var barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, // symbology
    "(01)12345678901231");               // GS1 data payload
```

*Warum das wichtig ist:* `EncodeTypes.DatabarOmniDirectional` erzeugt einen kompakten, omnidirektionalen DataBar, der aus jedem Winkel gescannt werden kann – ideal für kleine Etiketten.

## Schritt 3: Gemeinsame Barcode‑Parameter festlegen (einschließlich der anfänglichen Balkenhöhe)

Jetzt legen wir **wie man den Barcode** X‑Dimension und Balkenhöhe fest, bevor das erste Bild gespeichert wird.

```csharp
// Step 3: Configure X‑dimension (module width) and initial bar height
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;    // 2‑pixel modules
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;   // 30‑pixel height
```

Die X‑Dimension steuert die Gesamtabmessung jedes Balkens; eine Einstellung von 2 Pixel ergibt ein lesbares, scharfes Bild auf den meisten Bildschirmen. Der **Barcode‑Höhe ändern**‑Schritt später wird denselben Generator wiederverwenden, was Zeit und Speicher spart.

## Schritt 4: Das erste Barcode‑Bild speichern (30‑Pixel‑Höhe)

```csharp
// Step 4: Save the 30‑pixel barcode image
barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
```

Die Datei `DatabarHeight30.png` enthält nun einen DataBar‑Barcode mit einer Balkenhöhe von 30 Pixel.

## Schritt 5: Nur die Balkenhöhe auf 60 Pixel ändern

Um **Barcode‑Höhe ändern** zu demonstrieren, ändern wir nur die Eigenschaft `BarHeight`. Alle anderen Einstellungen bleiben unverändert, was der effizienteste Weg ist, mehrere Größen aus einem einzigen Generator zu erzeugen.

```csharp
// Step 5: Update the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

## Schritt 6: Das zweite Barcode‑Bild speichern (60‑Pixel‑Höhe)

```csharp
// Step 6: Save the 60‑pixel barcode image
barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
```

Sie haben jetzt zwei PNG‑Dateien, jede mit einer anderen Balkenhöhe, aber identischen Daten und X‑Dimension.

## Vollständiges, ausführbares Beispiel

Unten finden Sie das vollständige Programm, das Sie in eine neue Konsolenanwendung (`dotnet new console`) kopieren und sofort ausführen können.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator for a DataBar Omni‑directional barcode
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");

        // Set X‑dimension and initial bar height (30 pixels)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image (30‑pixel height)
        barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight30.png");

        // Change only the bar height to 60 pixels
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image (60‑pixel height)
        barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight60.png");
    }
}
```

### Erwartete Ausgabe

Beim Ausführen des Programms werden zwei Dateien im Arbeitsverzeichnis der ausführbaren Datei erzeugt:

* `DatabarHeight30.png` – ein DataBar‑Barcode mit 30 Pixel hohen Balken.  
* `DatabarHeight60.png` – derselbe Barcode, jedoch sind die Balken doppelt so hoch.

Beide Bilder können in jedem Bildbetrachter geöffnet oder direkt in PDFs, HTML‑Seiten oder gedruckte Etiketten eingebettet werden.

## Warum das Anpassen der Balkenhöhe wichtig ist

* **Scanning reliability:** Einige Scanner haben Schwierigkeiten mit sehr kurzen Balken auf Medien mit niedriger Auflösung; das Erhöhen der Höhe verbessert die Erkennung.  
* **Design constraints:** Eine mobile App benötigt möglicherweise einen kompakten Barcode (30 px), während ein gedruckter Kassenbon einen größeren (60 px) erfordern kann.  
* **Regulatory compliance:** In bestimmten Branchen ist eine Mindestbalkenhöhe für GS1 DataBar‑Symbole vorgeschrieben.

Durch die Wiederverwendung derselben `BarcodeGenerator`‑Instanz vermeiden Sie den Aufwand des erneuten Parsens der Datenzeichenfolge, was insbesondere in Hochdurchsatz‑Umgebungen vorteilhaft ist.

## Häufige Variationen und Randfälle

| Situation | Empfohlene Anpassung |
|-----------|----------------------|
| Eine andere X‑Dimension erforderlich | Ändern Sie `XDimension.Pixels` vor dem ersten `Save`. |
| Eine andere Symbologie gewünscht (z. B. DataBar Stacked) | Verwenden Sie `EncodeTypes.DatabarStacked` beim Erzeugen von `BarcodeGenerator`. |
| Der Barcode muss in ein PDF eingebettet werden | Verwenden Sie `barcodeGenerator.Save(stream, BarCodeImageFormat.Png)` und fügen Sie den Stream einer PDF‑Bibliothek hinzu. |
| Ausführung auf .NET Framework 4.6 | Der gleiche Code funktioniert; referenzieren Sie einfach die passende Aspose.BarCode‑Assembly. |

## Profi‑Tipps für zuverlässige Barcode‑Erstellung

* **Cache den Generator** wenn Sie viele Barcodes mit denselben Daten, aber unterschiedlichen Größen erzeugen.  
* **

## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Code‑Beispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, weitere API‑Funktionen zu beherrschen und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [Wie man die Barcode‑Höhe für eindimensionale Databar mit Aspose.BarCode für .NET generiert und anpasst](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Wie man Databar‑PNG‑Bilder mit C# und Aspose.BarCode erstellt](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [Wie man Barcodes mit benutzerdefinierter Größe erzeugt und das Bild in C# speichert](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
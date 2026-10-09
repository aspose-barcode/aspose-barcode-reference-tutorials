---
category: general
date: 2026-09-29
description: Erfahren Sie, wie Sie einen omnidirektionalen Databar‑Barcode in C# mit
  Aspose.BarCode erstellen. Passen Sie die X‑Dimension an, stellen Sie das Seitenverhältnis
  ein und speichern Sie PNG‑Bilder.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional databar barcode
- DataBar stacked omnidirectional barcode
- set barcode aspect ratio
- Aspose.BarCode C#
- generate barcode image
language: de
lastmod: 2026-09-29
og_description: Erstellen Sie einen omnidirektionalen Databar-Barcode in C# mit Aspose.BarCode.
  Erfahren Sie, wie Sie die X‑Dimension festlegen, das Seitenverhältnis anpassen und
  PNG‑Dateien exportieren.
og_image_alt: Screenshot showing two PNG files of an omnidirectional Databar barcode
  with different aspect ratios
og_title: Erstelle einen omnidirektionalen Databar-Barcode in C# – Schritt‑für‑Schritt‑Anleitung
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  headline: How to create omnidirectional Databar barcode in C#
  type: TechArticle
- description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  name: How to create omnidirectional Databar barcode in C#
  steps:
  - name: What if I need a different X‑dimension?
    text: You can assign any integer value to `XDimension.Pixels`. Values below `1`
      are ignored, and values above `10` may produce oversized modules that exceed
      printer margins. Test the visual output after each change.
  - name: How do I encode other AI‑generated data (e.g., UPC, EAN)?
    text: Replace the data string in the `BarcodeGenerator` constructor with the appropriate
      Application Identifier (AI). For a UPC‑A code, use `"012345678905"` without
      an AI prefix.
  - name: Can I export to formats other than PNG?
    text: Yes. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`,
      `BarCodeImageFormat.Tiff`, and `BarCodeImageFormat.Bmp`. Choose the format that
      matches your downstream workflow.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Wie man einen omnidirektionalen Databar-Barcode in C# erstellt
url: /de/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man einen omnidirektionalen Databar-Barcode in C# erstellt

Wenn Sie einen **omnidirektionalen Databar-Barcode erstellen** in einer .NET-Anwendung benötigen, zeigt Ihnen diese Anleitung die genauen Schritte. Sie sehen, wie man einen DataBar stacked omnidirectional Barcode initialisiert, seine X‑Dimension konfiguriert, das Seitenverhältnis ändert und PNG‑Bilder mit Aspose.BarCode erzeugt.

Das Erzeugen eines **DataBar stacked omnidirectional barcode** ist üblich, wenn Sie Produktkennungen für Einzelhandels‑Scanner codieren müssen. In diesem Tutorial lernen Sie, **das Barcode‑Seitenverhältnis festzulegen**, die Modulgröße zu steuern und das Ergebnis zu exportieren, ohne die IDE zu verlassen.

## Voraussetzungen

- .NET 6.0 oder neuer installiert
- Visual Studio 2022 (oder jede C#‑kompatible IDE)
- Das **Aspose.BarCode for .NET** NuGet‑Paket (Version 23.12 oder neuer)

Sie können das Paket über den NuGet Package Manager hinzufügen:

```bash
dotnet add package Aspose.BarCode
```

## Schritt 1: Initialisieren des omnidirektionalen Databar-Barcodes

Der erste Schritt besteht darin, eine `BarcodeGenerator`‑Instanz zu erstellen, die die **DataBar stacked omnirectional**‑Symbologie verwendet. Der Konstruktor erhält den Codierungstyp und den Datenstring.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialise a DataBar stacked omnidirectional barcode with GTIN data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Warum das wichtig ist:** Der Wert `EncodeTypes.DatabarStackedOmniDirectional` weist Aspose.BarCode an, das spezifische omnidirektionale Databar‑Format zu rendern, das für das Scannen in beide Richtungen erforderlich ist.

## Schritt 2: Definieren der X‑Dimension (Modulgröße)

Die X‑Dimension steuert die Breite eines einzelnen Barcode‑Moduls in Pixeln. Ein Wert von `2` Pixeln funktioniert gut für die Anzeige auf dem Bildschirm und die meisten Drucker.

```csharp
        // Set the basic size of the barcode modules (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Warum das wichtig ist:** Eine konsistente X‑Dimension stellt sicher, dass der Barcode die Mindestgrößenspezifikationen für Einzelhandels‑Scanner erfüllt und gleichzeitig die Dateigröße des Bildes überschaubar bleibt.

## Schritt 3: Das erste Seitenverhältnis festlegen und das Bild speichern

Das **Seitenverhältnis** bestimmt das Höhen‑zu‑Breiten‑Verhältnis des DataBar. Ein Seitenverhältnis von `15` ergibt einen kompakten, hohen Barcode, der ideal für schmale Etikettenbereiche ist.

```csharp
        // Apply aspect ratio 15 and save the first PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Warum das wichtig ist:** Durch Anpassen des Seitenverhältnisses können Sie den Barcode in verschiedene Etikettenlayouts einpassen, ohne die Lesbarkeit zu beeinträchtigen. Das gespeicherte PNG kann in jedem Bildbetrachter angesehen werden.

## Schritt 4: Das Seitenverhältnis ändern und ein zweites Bild erzeugen

Manchmal wird ein breiterer Barcode benötigt – zum Beispiel, wenn das Etikett mehr horizontalen Platz bietet. Das Ändern des Verhältnisses auf `30` erzeugt ein flacheres Aussehen.

```csharp
        // Change aspect ratio to 30 and save a second PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Warum das wichtig ist:** Durch das Bereitstellen der Eigenschaft **set barcode aspect ratio** können Sie mehrere Barcode‑Varianten aus einer einzigen Codebasis erzeugen, was automatisierte Etikettengenerierungs‑Pipelines vereinfacht.

## Erwartete Ausgabe

Das Ausführen des Programms erzeugt zwei PNG‑Dateien im Ausgabeverzeichnis der Anwendung:

| Dateiname                | Seitenverhältnis | Visuelle Beschreibung |
|--------------------------|-------------------|------------------------|
| `DatabarAspectRatio15.png` | 15                | Hoher, schmaler Barcode, geeignet für schmale Etiketten |
| `DatabarAspectRatio30.png` | 30                | Breiterer Barcode, der mehr horizontalen Raum ausfüllt |

Sie können diese Bilder in Berichte einbetten, sie auf Produktverpackungen drucken oder an einen Webservice zur weiteren Verarbeitung senden.

![Erstellen eines omnidirektionalen Databar-Barcode-Beispiels](databar-example.png "Erstellen eines omnidirektionalen Databar-Barcode-Beispiels")

*Der Screenshot zeigt die beiden erzeugten PNG‑Dateien nebeneinander.*

## Häufige Fragen und Sonderfälle

### Was ist, wenn ich eine andere X‑Dimension benötige?

Sie können jedem ganzzahligen Wert `XDimension.Pixels` zuweisen. Werte unter `1` werden ignoriert, und Werte über `10` können zu übergroßen Modulen führen, die die Druckermargen überschreiten. Testen Sie die visuelle Ausgabe nach jeder Änderung.

### Wie codiere ich andere AI‑generierte Daten (z. B. UPC, EAN)?

Ersetzen Sie den Datenstring im `BarcodeGenerator`‑Konstruktor durch den entsprechenden Application Identifier (AI). Für einen UPC‑A‑Code verwenden Sie `"012345678905"` ohne AI‑Präfix.

### Kann ich in andere Formate als PNG exportieren?

Ja. Die `Save`‑Methode akzeptiert `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`, `BarCodeImageFormat.Tiff` und `BarCodeImageFormat.Bmp`. Wählen Sie das Format, das zu Ihrem nachgelagerten Workflow passt.

## Profi‑Tipp: Generator für Batch‑Verarbeitung wiederverwenden

Wenn Sie Dutzende von Barcodes mit unterschiedlichen Seitenverhältnissen erzeugen müssen, halten Sie die `BarcodeGenerator`‑Instanz am Leben und ändern Sie nur `DataBar.AspectRatio` vor jedem `Save`. Dadurch wird der Aufwand vermieden, den Generator für jedes Bild neu zu instanziieren.

```csharp
var ratios = new[] { 10, 15, 20, 30 };
foreach (var ratio in ratios)
{
    generator.Parameters.Barcode.DataBar.AspectRatio = ratio;
    generator.Save($"DatabarAspectRatio{ratio}.png", BarCodeImageFormat.Png);
}
```

## Fazit

Sie wissen jetzt, wie man **omnidirektionalen Databar-Barcode erstellen** in C# mit Aspose.BarCode **erstellt**. Durch Initialisieren eines `BarcodeGenerator`, Festlegen der X‑Dimension, Anpassen des **set barcode aspect ratio** und Speichern von PNG‑Dateien können Sie Barcode‑Bilder erzeugen, die verschiedene Etikettenanforderungen erfüllen.  

Als Nächstes erkunden Sie verwandte Themen wie **generate barcode image** für QR‑Codes, **DataBar stacked omnidirectional barcode**‑Validierung oder die Integration der erzeugten PNGs in PDF‑Rechnungen mit Aspose.PDF. Experimentieren Sie mit verschiedenen Seitenverhältnissen und Modulgrößen, um die optimale Konfiguration für Ihre spezifische Druckhardware zu finden.

---

## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige funktionierende Code‑Beispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, zusätzliche API‑Funktionen zu beherrschen und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [Wie man einen Barcode‑Generator C# verwendet, um DataBar Omni‑directional Barcodes zu erstellen](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [DataBar stacked omnidirectional Barcode in C# – Vollständige Anleitung](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [Wie man Barcodes in C# generiert – Barcode‑Bild in C# mit DataBar Expanded erstellen](/barcode/english/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
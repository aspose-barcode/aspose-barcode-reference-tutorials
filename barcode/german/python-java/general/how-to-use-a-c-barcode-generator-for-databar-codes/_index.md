---
category: general
date: 2026-09-23
description: Das C#‑Barcode‑Generator‑Tutorial zeigt, wie man Barcode‑Bilder mit benutzerdefinierten
  Seitenverhältnissen mithilfe der Aspose.BarCode‑Bibliothek erzeugt.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- DataBar barcode C#
- barcode aspect ratio
- Aspose.BarCode C#
- barcode image export
language: de
lastmod: 2026-09-23
og_description: Der C#‑Barcode‑Generator‑Leitfaden führt Sie durch das Erstellen von
  Barcode‑Bildern, das Anpassen von Seitenverhältnissen und das Exportieren von PNG‑Dateien
  mit Aspose.BarCode.
og_image_alt: Screenshot of a barcode created with a C# barcode generator
og_title: Erstellen Sie hochwertige Barcodes mit einem C#‑Barcode‑Generator
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  headline: How to use a C# barcode generator for DataBar codes
  type: TechArticle
- description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  name: How to use a C# barcode generator for DataBar codes
  steps:
  - name: Switching to another barcode type
    text: 'If you need a QR code, Code 128, or PDF417, replace the enum value in the
      constructor:'
  - name: Handling unsupported characters
    text: 'The `BarcodeGenerator` validates the input string against the selected
      symbology. Supplying an illegal character throws an `ArgumentException`. Wrap
      the creation in a try‑catch block to provide a friendly error message:'
  - name: Exporting to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the second argument
      of `Save` accordingly:'
  - name: High‑resolution output for printing
    text: 'When printing on high‑DPI printers, increase the X‑dimension and optionally
      set the `Resolution` property:'
  type: HowTo
tags:
- barcode
- c#
- Aspose
title: Wie man einen C#‑Barcode‑Generator für DataBar‑Codes verwendet
url: /de/python-java/general/how-to-use-a-c-barcode-generator-for-databar-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man einen C# Barcode-Generator für DataBar-Codes verwendet

Wenn Sie einen **c# barcode generator** benötigen, der DataBar stacked Omni‑Directional‑Symbole erzeugen kann, bietet Ihnen dieser Leitfaden eine komplette, sofort einsatzbereite Lösung. Sie sehen, wie Sie Barcode‑Bilder generieren, die X‑Dimension steuern und das Seitenverhältnis ändern, ohne die IDE zu verlassen.

Das Erzeugen von Barcodes ist eine gängige Anforderung für Inventursysteme, Versandetiketten und Point‑of‑Sale‑Anwendungen. Am Ende dieses Tutorials können Sie PNG‑Dateien mit beliebigem Seitenverhältnis erstellen und verstehen, wie Sie den Code für andere Barcode‑Typen anpassen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

* .NET 6.0 SDK oder neuer installiert  
* Visual Studio 2022 (oder ein beliebiger C#‑Editor Ihrer Wahl)  
* Einen NuGet‑Verweis auf **Aspose.BarCode** – die Bibliothek, die die `BarcodeGenerator`‑Klasse bereitstellt  

Sie benötigen keine separate Grafikbibliothek; Aspose.BarCode übernimmt die Bildkodierung intern.

## Schritt 1: Installieren Sie das Aspose.BarCode NuGet‑Paket

Öffnen Sie ein Terminal in Ihrem Projektordner und führen Sie aus:

```bash
dotnet add package Aspose.BarCode
```

Der Befehl fügt die neueste stabile Version der Bibliothek zu Ihrer Projektdatei hinzu und macht die `BarcodeGenerator`‑Klasse verfügbar.

## Schritt 2: Definieren Sie den Ausgabepfad

Wählen Sie einen Ordner, in dem die erzeugten PNG‑Dateien gespeichert werden sollen. Sowohl ein absoluter als auch ein relativer Pfad funktionieren gleich, aber ein relativer Pfad hält das Projekt portabel.

```csharp
// Define the output folder (relative to the project root)
string outputFolder = "GeneratedBarcodes/";
Directory.CreateDirectory(outputFolder); // Ensure the folder exists
```

Das programmatische Erstellen des Verzeichnisses verhindert Laufzeitfehler, falls der Ordner fehlt.

## Schritt 3: Instanziieren Sie den C# Barcode‑Generator mit Beispieldaten

Der Konstruktor `BarcodeGenerator` benötigt zwei Argumente: den Barcode‑Typ und den Daten‑String. Für ein DataBar stacked Omni‑Directional‑Symbol verwenden Sie `EncodeTypes.DatabarStackedOmniDirectional`.

```csharp
// Create a barcode generator for a DataBar stacked Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

Der Daten‑String folgt dem GS1 Application Identifier‑Format. Das `EncodeTypes`‑Enum enthält über 150 Barcode‑Standards; Sie können zu einem anderen Typ wechseln, indem Sie den Enum‑Wert ändern.

## Schritt 4: Setzen Sie die X‑Dimension (Pixelgröße) für den Barcode

Die X‑Dimension steuert die Breite des schmalsten Balkens. Ein Pixelwert von 2 liefert ein klares, hochauflösendes Bild, das für die meisten Bildschirme geeignet ist.

```csharp
// Set the X‑dimension to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Das Anpassen der X‑Dimension ist optional, gibt Ihnen jedoch feine Kontrolle über die visuelle Dichte des Barcodes.

## Schritt 5: Generieren Sie einen Barcode mit einem Seitenverhältnis von 15 und speichern Sie ihn als PNG

Die Eigenschaft `AspectRatio` gehört zum Unterobjekt `DataBar`. Das Ändern dieses Wertes streckt oder komprimiert den Barcode vertikal, während die codierten Daten erhalten bleiben.

```csharp
// Set aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Die Methode `Save` schreibt den Barcode in den angegebenen Dateipfad. Das Enum `BarCodeImageFormat.Png` sorgt für verlustfreie Kompression.

![c# barcode generator output example](generated_barcode_example.png)

*Bild: Barcode erzeugt mit einem Seitenverhältnis von 15.*

## Schritt 6: Ändern Sie das Seitenverhältnis auf 30 und erzeugen Sie ein zweites Bild

Die Wiederverwendung derselben `BarcodeGenerator`‑Instanz vermeidet die Allokation eines neuen Objekts. Aktualisieren Sie einfach `AspectRatio` und rufen Sie erneut `Save` auf.

```csharp
// Update aspect ratio to 30 and save a second image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

Jetzt haben Sie zwei PNG‑Dateien, die sich nur in der vertikalen Skalierung unterscheiden. Diese Technik ist nützlich, wenn dieselben Daten für verschiedene Etikettengrößen gerendert werden sollen.

## Häufige Variationen und Sonderfälle

### Wechsel zu einem anderen Barcode‑Typ

Wenn Sie einen QR‑Code, Code 128 oder PDF417 benötigen, ersetzen Sie den Enum‑Wert im Konstruktor:

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(
    EncodeTypes.QR, "https://example.com");
```

Alle anderen Konfigurationsschritte (X‑Dimension, Speichern) bleiben identisch.

### Umgang mit nicht unterstützten Zeichen

Der `BarcodeGenerator` validiert den Eingabestring gegen die ausgewählte Symbolik. Das Übergeben eines illegalen Zeichens löst eine `ArgumentException` aus. Umhüllen Sie die Erstellung mit einem try‑catch‑Block, um eine benutzerfreundliche Fehlermeldung bereitzustellen:

```csharp
try
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid data for the selected barcode type: {ex.Message}");
}
```

### Export in andere Bildformate

Aspose.BarCode unterstützt BMP, JPEG, TIFF und SVG. Ändern Sie das zweite Argument von `Save` entsprechend:

```csharp
barcodeGenerator.Save($"{outputFolder}Databar.svg", BarCodeImageFormat.Svg);
```

### Hochauflösende Ausgabe für den Druck

Beim Drucken auf Hoch‑DPI‑Druckern erhöhen Sie die X‑Dimension und setzen optional die Eigenschaft `Resolution`:

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.ImageResolution.Dpi = 300;
```

Diese Einstellungen erzeugen größere Dateien, erhalten jedoch scharfe Kanten auf physischen Medien.

## Erwartete Ausgabe

Das Ausführen des vollständigen Programms erzeugt die folgenden Dateien im Ordner `GeneratedBarcodes/`:

* `DatabarAspectRatio15.png` – ein DataBar‑Code mit Standardhöhe  
* `DatabarAspectRatio30.png` – eine vertikal gestreckte Version  

Beide Bilder enthalten dieselben codierten GS1‑Daten und können mit jeder Barcode‑Scanner‑App überprüft werden.

## Vollständiger Quellcode

Kopieren Sie den untenstehenden Code in ein neues Konsolenprojekt (`dotnet new console`) und führen Sie es aus. Das Programm gibt Statusmeldungen in die Konsole aus und schreibt die PNG‑Dateien auf die Festplatte.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Define the output folder
        string outputFolder = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputFolder);

        // Step 3: Create a C# barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Step 4: Set common barcode properties (pixel size of X‑dimension)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 5: Generate a barcode with aspect ratio 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        string file15 = Path.Combine(outputFolder, "DatabarAspectRatio15.png");
        barcodeGenerator.Save(file15, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

        // Step 6: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        string file30 = Path.Combine(outputFolder, "DatabarAspectRatio30.png");
        barcodeGenerator.Save(file30, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
    }
}
```

Das Ausführen des Programms erzeugt eine Konsolenausgabe ähnlich wie:

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

## Fazit

Sie verfügen nun über einen **c# barcode generator**, der DataBar stacked Omni‑Directional‑Symbole erstellen, die X‑Dimension anpassen und PNG‑Dateien mit benutzerdefinierten Seitenverhältnissen exportieren kann. Das gleiche Muster funktioniert für jede andere von Aspose.BarCode unterstützte Barcode‑Symbolik und erleichtert die Integration der Barcode‑Erstellung in Inventar‑, Versand‑ oder Point‑of‑Sale‑Lösungen.

Wenn Sie weiterforschen möchten, probieren Sie:

* QR‑Codes oder PDF417‑Symbole generieren (`how to generate barcode` für mobile Apps)  
* Export nach SVG für skalierbare Webgrafiken  
* Einbetten der erzeugten Bilder direkt in PDF‑Rechnungen mit Aspose.PDF  

Experimentieren Sie mit verschiedenen `AspectRatio`‑Werten, X‑Dimension‑Größen und Ausgabeformaten, um das exakte Ergebnis zu erzielen.


## Was sollten Sie als Nächstes lernen?


Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Codebeispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, weitere API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
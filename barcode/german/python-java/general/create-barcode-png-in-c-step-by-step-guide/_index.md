---
category: general
date: 2026-08-03
description: Erstelle ein Barcode‑PNG in C# und lerne, wie man das Seitenverhältnis
  von DataBar‑Bildern ändert. Folge diesem vollständigen Beispiel mit Code und Tipps.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode PNG
- how to change aspect ratio
- Aspose.BarCode C#
- DataBar stacked omnidirectional
- barcode image format PNG
language: de
lastmod: 2026-08-03
og_description: Erstelle Barcode‑PNG in C# und erfahre, wie du das Seitenverhältnis
  für DataBar‑Barcodes ändern kannst. Dieser Leitfaden liefert sofort einsatzbereiten
  Code und praktische Tipps.
og_image_alt: Sample barcode PNG generated with aspect ratio 15
og_title: Barcode-PNG in C# erstellen – vollständiges Beispiel mit Seitenverhältnis‑Steuerung
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  headline: Create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  name: Create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: How to change other visual properties?
    text: 'You can adjust foreground color, background color, or add human‑readable
      text through the `generator.Parameters.Barcode` object. For example:'
  - name: What if I need a different image format?
    text: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as needed.
      PNG remains the best choice for lossless barcode images.
  - name: Does the aspect ratio affect scanning speed?
    text: Higher aspect ratios increase the barcode’s height, which can improve scan
      reliability on devices that struggle with short stacked symbols. However, extremely
      tall barcodes may not fit on small labels, so test with your target hardware.
  - name: Can I generate multiple barcodes in a loop?
    text: Yes. Create a new `BarcodeGenerator` instance for each data string or reuse
      the same instance while updating `CodeText` and `DataBar.AspectRatio`. This
      approach reduces object allocation overhead.
  type: HowTo
tags:
- barcode
- C#
- PNG
- Aspose
title: Barcode-PNG in C# erstellen – Schritt‑für‑Schritt‑Anleitung
url: /de/python-java/general/create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode-PNG in C# erstellen – Schritt‑für‑Schritt‑Anleitung

Wenn Sie **Barcode-PNG** in C# **erstellen** müssen, zeigt Ihnen dieses Tutorial genau, wie es geht. Sie generieren einen gestapelten omnidirektionalen DataBar‑Barcode, speichern ihn als PNG‑Datei und lernen **wie man das Seitenverhältnis ändert**, um unterschiedliche Scan‑Umgebungen zu berücksichtigen.

Der Leitfaden deckt alles ab, was Sie benötigen: erforderliche Pakete, ein vollständiges, ausführbares Programm und Erklärungen, warum jede Einstellung wichtig ist. Am Ende haben Sie zwei PNG‑Dateien – eine mit einem Seitenverhältnis von 15 und eine mit 30 – bereit für Tests oder den Produktionseinsatz.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- .NET 6.0 SDK oder neuer installiert
- Visual Studio 2022 (oder eine beliebige C#‑IDE)
- Einen NuGet‑Verweis auf **Aspose.BarCode** (die Bibliothek, die `BarcodeGenerator` bereitstellt)
- Schreibrechte für das Verzeichnis, in dem die PNG‑Dateien gespeichert werden

Sie können das Aspose.BarCode‑Paket mit folgendem Befehl hinzufügen:

```bash
dotnet add package Aspose.BarCode
```

## Schritt 1: Projekt einrichten und Namespaces importieren

Erstellen Sie eine neue Konsolenanwendung und importieren Sie die Namespaces, die für die Barcode‑Erstellung und Dateiverarbeitung benötigt werden.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodePngDemo
{
    class Program
    {
        static void Main()
        {
            // All subsequent steps are inside Main
```

**Warum das wichtig ist:** Durch das Importieren von `Aspose.BarCode.Generation` erhalten Sie Zugriff auf `BarcodeGenerator`. Der Code innerhalb von `Main` macht das Beispiel eigenständig und leicht ausführbar.

## Schritt 2: Einen Barcode‑Generator für einen gestapelten omnidirektionalen DataBar erstellen

Instanziieren Sie `BarcodeGenerator` mit dem Typ `EncodeTypes.DatabarStackedOmniDirectional` und einem Beispiel‑GS1‑128‑Datenstring.

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");
```

**Warum das wichtig ist:** Der gewählte Kodierungstyp erzeugt einen hochdichten DataBar, der von den meisten modernen Scannern gelesen werden kann. Der Datenstring folgt dem GS1‑Anwendungsidentifikator (01)‑Format, das häufig für Produktkennzeichnungen verwendet wird.

## Schritt 3: Die X‑Dimension (Modulbreite) in Pixel festlegen

Setzen Sie die Modulbreite, um die Gesamtabmessungen des Barcodes zu steuern, ohne die Lesbarkeit zu beeinträchtigen.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Warum das wichtig ist:** Eine X‑Dimension von 2 Pixeln ergibt einen Barcode, der weder zu klein für Scanner noch zu groß für typische Etikettenflächen ist.

## Schritt 4: Das erste PNG mit einem Seitenverhältnis von 15 speichern

Passen Sie das DataBar‑Seitenverhältnis an und speichern Sie das Bild als PNG‑Datei.

```csharp
            // Step 4: Set the DataBar aspect ratio to 15 and save the image
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;
            string outputPath15 = @"YOUR_DIRECTORY\DatabarAspectRatio15.png";
            generator.Save(outputPath15, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath15} (aspect ratio 15).");
```

**Warum das wichtig ist:** Das Seitenverhältnis bestimmt das Höhen‑zu‑Breiten‑Verhältnis des gestapelten DataBar. Ein Verhältnis von 15 ist ein gängiger Standard, der Lesbarkeit und Etikettenhöhe ausbalanciert.

## Schritt 5: Das Seitenverhältnis auf 30 ändern und ein zweites PNG speichern

Ändern Sie dieselbe Generator‑Instanz, um ein größeres Seitenverhältnis zu verwenden, und speichern Sie das zweite Bild.

```csharp
            // Step 5: Change the aspect ratio to 30 and save another image
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string outputPath30 = @"YOUR_DIRECTORY\DatabarAspectRatio30.png";
            generator.Save(outputPath30, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath30} (aspect ratio 30).");
        }
    }
}
```

**Warum das wichtig ist:** Ein höheres Seitenverhältnis streckt den Barcode vertikal, was die Scan‑Zuverlässigkeit auf Niedrig‑Auflösungs‑Geräten oder bei schmalen Medien verbessern kann.

## Erwartete Ausgabe

Das Ausführen des Programms erzeugt zwei PNG‑Dateien:

| Datei                               | Seitenverhältnis | Ungefähre Abmessungen (Pixel) |
|-------------------------------------|-------------------|------------------------------|
| `DatabarAspectRatio15.png`          | 15                | 200 × 300 (Breite × Höhe)     |
| `DatabarAspectRatio30.png`          | 30                | 200 × 600 (Breite × Höhe)     |

Beide Bilder enthalten einen klaren, scanbaren DataBar‑Barcode, der den GS1‑Identifikator `(01)12345678901231` codiert.

## Häufige Fragen und Sonderfälle

### Wie ändere ich andere visuelle Eigenschaften?

Sie können Vordergrundfarbe, Hintergrundfarbe oder menschenlesbaren Text über das Objekt `generator.Parameters.Barcode` anpassen. Beispiel:

```csharp
generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
generator.Parameters.Barcode.CodeTextParameters.ShowCodeText = true;
```

### Was tun, wenn ich ein anderes Bildformat benötige?

Ersetzen Sie `BarCodeImageFormat.Png` durch `Jpeg`, `Bmp` oder `Gif`, je nach Bedarf. PNG bleibt die beste Wahl für verlustfreie Barcode‑Bilder.

### Beeinflusst das Seitenverhältnis die Scan‑Geschwindigkeit?

Höhere Seitenverhältnisse vergrößern die Barcode‑Höhe, was die Scan‑Zuverlässigkeit auf Geräten verbessern kann, die Schwierigkeiten mit kurzen gestapelten Symbolen haben. Sehr hohe Barcodes passen jedoch möglicherweise nicht auf kleine Etiketten, daher sollten Sie mit Ihrer Ziel‑Hardware testen.

### Kann ich mehrere Barcodes in einer Schleife erzeugen?

Ja. Erstellen Sie für jede Datenzeichenfolge eine neue `BarcodeGenerator`‑Instanz oder verwenden Sie dieselbe Instanz erneut, indem Sie `CodeText` und `DataBar.AspectRatio` aktualisieren. Dieser Ansatz reduziert den Aufwand für Objektinstanziierungen.

## Profi‑Tipps

- **Generator wiederverwenden**: Nur `CodeText` oder `AspectRatio` ändern, anstatt das Objekt neu zu instanziieren – das beschleunigt die Batch‑Verarbeitung.
- **Ausgabe validieren**: Nutzen Sie einen Handscanner oder eine mobile App, um sicherzustellen, dass das erzeugte PNG korrekt gelesen wird, bevor Sie es in die Produktion geben.
- **Dateinamen**: Das Seitenverhältnis im Dateinamen (wie gezeigt) aufnehmen, um Varianten während des Testens nachzuverfolgen.

## Fazit

Sie wissen jetzt, wie Sie **Barcode-PNG**‑Dateien in C# **erstellen** und exakt **das Seitenverhältnis** für gestapelte omnidirektionale DataBar‑Symbole **ändern**. Das vollständige Beispiel demonstriert Initialisierung, X‑Dimension‑Einstellung, Seitenverhältnis‑Manipulation und Bildspeicherung – alles in einem einzigen, ausführbaren Programm.

Ab hier können Sie weitere Barcode‑Typen erkunden, mit Farben experimentieren oder den Generator in ein größeres Reporting‑ oder Inventursystem integrieren. Viel Spaß beim Coden!

## Was sollten Sie als Nächstes lernen?


Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Code‑Beispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, weitere API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Customize Barcode - Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
---
category: general
date: 2026-09-13
description: Erfahren Sie, wie Sie in C# Barcodes erzeugen, die Barcode‑Größe anpassen
  und das Barcode‑Bild als PNG mit Aspose.BarCode speichern. Vollständige Schritt‑für‑Schritt‑Anleitung.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- custom barcode size
- save barcode image
- Aspose.BarCode C#
- barcode image format
language: de
lastmod: 2026-09-13
og_description: Wie man in C# einen Barcode mit benutzerdefinierter Größe erzeugt
  und das Barcode‑Bild als PNG speichert. Folgen Sie diesem vollständigen Leitfaden
  für Aspose.BarCode.
og_image_alt: Screenshot of a DataBar stacked omnidirectional barcode generated in
  C#
og_title: Wie man einen Barcode erzeugt, eine benutzerdefinierte Größe festlegt und
  das Bild in C# speichert
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to generate barcode in C#, customize barcode size, and save
    barcode image as PNG using Aspose.BarCode. Complete step‑by‑step guide.
  headline: How to generate barcode set custom size and save image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Wie man Barcode mit benutzerdefinierter Größe generiert und das Bild in C#
  speichert
url: /de/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Barcodes mit benutzerdefinierter Größe erzeugt und das Bild in C# speichert

Wenn Sie in einer .NET-Anwendung **Barcodes erzeugen** müssen, zeigt Ihnen dieses Tutorial eine vollständige Lösung. Sie sehen, wie Sie die **benutzerdefinierte Barcode-Größe** anpassen und **Barcode-Bilddateien** mit nur wenigen Zeilen C#‑Code speichern können.

Die Erzeugung von Barcodes ist eine gängige Anforderung für Inventursysteme, Versandetiketten und Point‑of‑Sale‑Anwendungen. Am Ende dieses Leitfadens haben Sie ein ausführbares Programm, das zwei DataBar‑Stacked‑Omnidirectional‑Barcodes erstellt, jeweils mit einem anderen Seitenverhältnis, und sie als PNG‑Dateien auf die Festplatte schreibt.

**Voraussetzungen**

- .NET 6.0 oder höher (der Code funktioniert auch mit .NET Framework 4.7+)
- Visual Studio 2022 oder jede C#‑IDE
- Aspose.BarCode für .NET (Kostenlose Testversion oder lizenziertes NuGet‑Paket)

---

## Wie man Barcodes mit Aspose.BarCode erzeugt

Die Aspose.BarCode‑Bibliothek abstrahiert die Low‑Level‑Details von Barcode‑Standards, sodass Sie sich auf die zu kodierenden Daten und das gewünschte visuelle Erscheinungsbild konzentrieren können.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar stacked omnidirectional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GS1‑128 format example

        // 2️⃣ Set a basic module width – this influences the overall **custom barcode size**
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First aspect ratio (15) → save the image
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // 4️⃣ Change aspect ratio to 30 → **save barcode image** again
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### Warum jede Zeile wichtig ist

| Schritt | Erklärung |
|------|-------------|
| **1️⃣ Generator erstellen** | Das Enum `EncodeTypes.DatabarStackedOmniDirectional` teilt Aspose mit, welche Barcode‑Symbologie verwendet werden soll. Der String `"(01)12345678901231"` folgt dem GS1‑128‑Datenformat, wobei `(01)` der Anwendungsidentifikator für eine GTIN ist. |
| **2️⃣ X‑Dimension festlegen** | `XDimension.Pixels` definiert die Breite eines einzelnen Barcode‑Moduls (der kleinste Strich). Das Ändern dieses Wertes ist der Hauptweg, um eine **benutzerdefinierte Barcode‑Größe** zu erreichen, ohne die kodierten Daten zu ändern. |
| **3️⃣ Seitenverhältnis festlegen & speichern** | `DataBar.AspectRatio` steuert das Höhen‑zu‑Breiten‑Verhältnis der DataBar‑Symbole. Ein Seitenverhältnis von 15 erzeugt einen relativ kurzen, breiten Barcode, während 30 ihn höher macht. `Save` schreibt die visuelle Darstellung in eine PNG‑Datei und erfüllt damit die Anforderung **Barcode‑Bild speichern**. |
| **4️⃣ Seitenverhältnis ändern & erneut speichern** | Durch die Wiederverwendung derselben Generator‑Instanz können Sie mehrere Bilder mit unterschiedlichen visuellen Merkmalen erzeugen, während die Daten konstant bleiben. |

---

## Anpassen der benutzerdefinierten Barcode‑Größe über X‑Dimension hinaus

Während `XDimension.Pixels` die Modulbreite festlegt, können Sie die Gesamtabmessungen des Barcodes auch durch Kombination zweier Eigenschaften feinjustieren:

1. **`BarHeight`** – explizite Höhe in Pixeln.  
2. **`BarWidth`** – explizite Breite in Pixeln (überschreibt X‑Dimension).

```csharp
// Example: make a larger, more readable barcode
generator.Parameters.Barcode.XDimension.Pixels = 4;      // wider modules
generator.Parameters.Barcode.BarHeight.Pixels = 120;    // taller bars
generator.Parameters.Barcode.DataBar.AspectRatio = 20; // balanced ratio
generator.Save("LargeCustomSize.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved large custom size barcode.");
```

> **Profi‑Tipp:** Beim Drucken von Barcodes sollten Sie das erzeugte Bild stets in der endgültigen Druckgröße testen. Eine Modulbreite von 2 px funktioniert für die Anzeige auf dem Bildschirm, aber gedruckte Etiketten benötigen oft mindestens 4 px, um scanbar zu bleiben.

---

## Auswahl des richtigen Bildformats zum Speichern des Barcode‑Bildes

Aspose.BarCode unterstützt PNG, JPEG, BMP, GIF und TIFF. PNG ist verlustfrei und bewahrt scharfe Kanten, wodurch es die sicherste Wahl für die meisten Anwendungen ist. Wenn Sie eine kleinere Datei für das Web benötigen, funktioniert JPEG mit einer Qualitätsstufe von 90 gut, jedoch können Kompressionsartefakte die Scan‑Zuverlässigkeit beeinträchtigen.

```csharp
generator.Save("DatabarAspectRatio15.jpg", BarCodeImageFormat.Jpeg, 90);
Console.WriteLine("Saved JPEG version with quality 90.");
```

---

## Vollständiges, ausführbares Beispiel

Unten finden Sie eine eigenständige Konsolenanwendung, die Sie kopieren, einfügen und ausführen können. Sie demonstriert **wie man Barcodes erzeugt**, die **benutzerdefinierte Barcode‑Größe** ändert und **Barcode‑Bilder** in zwei verschiedenen Formaten **speichert**.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with the desired symbology and data
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // ---- Custom size configuration ----
            generator.Parameters.Barcode.XDimension.Pixels = 2;      // module width
            generator.Parameters.Barcode.BarHeight.Pixels = 80;    // optional explicit height
            generator.Parameters.Barcode.DataBar.AspectRatio = 15; // first aspect ratio

            // Save first image as PNG
            string pngPath1 = "DatabarAspectRatio15.png";
            generator.Save(pngPath1, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath1}");

            // Change aspect ratio for a taller barcode
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string pngPath2 = "DatabarAspectRatio30.png";
            generator.Save(pngPath2, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath2}");

            // ---- Larger custom size example ----
            generator.Parameters.Barcode.XDimension.Pixels = 4;
            generator.Parameters.Barcode.BarHeight.Pixels = 120;
            generator.Parameters.Barcode.DataBar.AspectRatio = 20;
            string largePath = "LargeCustomSize.png";
            generator.Save(largePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {largePath}");

            // ---- Save as JPEG for web use ----
            string jpegPath = "DatabarAspectRatio15.jpg";
            generator.Save(jpegPath, BarCodeImageFormat.Jpeg, 90);
            Console.WriteLine($"Saved {jpegPath}");
        }
    }
}
```

**Erwartete Ausgabe in der Konsole**

```
Saved DatabarAspectRatio15.png
Saved DatabarAspectRatio30.png
Saved LargeCustomSize.png
Saved DatabarAspectRatio15.jpg
```

Die vier Bilddateien werden im Programm erscheinen.

## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige funktionierende Code‑Beispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, weitere API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [Wie man DataMatrix‑Barcodes mit Aspose.BarCode für .NET erzeugt – Schritt‑für‑Schritt‑Anleitung](/barcode/english/net/datamatrix-barcode-configuration/)
- [Wie man PDF417‑Barcodes mit Aspose erzeugt – Vollständiger Leitfaden](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Wie man Aztec‑Barcodes mit benutzerdefiniertem Seitenverhältnis mit Aspose.BarCode für .NET erzeugt](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
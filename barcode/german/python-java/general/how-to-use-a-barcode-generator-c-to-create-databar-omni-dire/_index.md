---
category: general
date: 2026-08-22
description: Das C#‑Barcode‑Generator‑Tutorial zeigt, wie man Barcode‑PNG‑Dateien
  erzeugt, DataBar‑Barcodes erstellt und die Barcode‑Höhe in nur wenigen Schritten
  anpasst.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- how to generate barcode
- generate barcode PNG
- create DataBar barcode
- adjust barcode height
language: de
lastmod: 2026-08-22
og_description: Der Barcode‑Generator‑C#‑Leitfaden führt Sie durch das Erzeugen von
  Barcode‑PNGs, das Erstellen von DataBar‑Barcodes und das effiziente Anpassen der
  Barcode‑Höhe.
og_image_alt: Screenshot of two DataBar Omni‑directional barcodes with different heights
  saved as PNG files
og_title: Barcode-Generator C# – DataBar-Barcodes erstellen und Höhe anpassen
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to generate barcode PNG files,
    create DataBar barcodes, and adjust barcode height in just a few steps.
  headline: How to use a barcode generator C# to create DataBar Omni‑directional barcodes
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Wie man einen Barcode‑Generator in C# verwendet, um DataBar Omni‑directional‑Barcodes
  zu erstellen
url: /de/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man einen barcode generator C# verwendet, um DataBar Omni‑directional Barcodes zu erstellen

Wenn Sie einen **barcode generator C#** benötigen, der hochwertige PNG‑Bilder erzeugen kann, bietet Ihnen dieser Leitfaden alles, was Sie brauchen. Sie lernen, wie man Barcode‑PNG‑Dateien generiert, einen DataBar Omni‑directional Barcode erstellt und die Barcode‑Höhe anpasst, ohne Ihre IDE zu verlassen.

Das programmgesteuerte Erzeugen von Barcodes eliminiert den manuellen Schritt der Verwendung eines Grafikeditors. Am Ende dieses Tutorials haben Sie zwei PNG‑Dateien – eine mit einer Balkenhöhe von 30 Pixeln und eine weitere mit einer Balkenhöhe von 60 Pixeln – bereit zur Einbindung in Rechnungen, Etiketten oder Bestandsverwaltungssysteme.

**Voraussetzungen**

- .NET 6.0 oder höher (der Code funktioniert auch mit .NET Framework 4.7+)
- Ein Verweis auf das `Aspose.BarCode` NuGet‑Paket (oder jede Bibliothek, die eine ähnliche API bereitstellt)
- Grundlegende Kenntnisse in C# und Visual Studio oder Ihrer bevorzugten IDE

---

## Schritt 1: Das barcode generator C#‑Projekt einrichten

Das Erstellen einer **barcode generator C#**‑Instanz ist der erste Schritt. Der Konstruktor erwartet zwei Argumente: den Barcode‑Typ (`EncodeTypes.DatabarOmniDirectional`) und die Daten‑Payload. In diesem Beispiel folgt die Payload dem GS1‑Anwendungsidentifikator‑Format für eine 14‑stellige GTIN.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the barcode generator for a DataBar Omni‑directional code
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

**Warum das wichtig ist:** Das `EncodeTypes.DatabarOmniDirectional`‑Enum weist die Bibliothek an, einen DataBar zu rendern, der aus jeder Richtung gelesen werden kann – ideal für kleine Einzelhandelsetiketten.

---

## Schritt 2: Die Modulgröße (X‑Dimension) festlegen

Die X‑Dimension steuert die Breite eines einzelnen Barcode‑Moduls. Wird sie auf 2 Pixel gesetzt, entsteht ein klares, gut lesbares Bild bei gleichzeitig geringer Dateigröße.

```csharp
        // Set the module (X) dimension to 2 pixels per module
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Tipp:** Wenn Sie für begrenzten Platz einen kompakteren Barcode benötigen, reduzieren Sie den Wert auf 1 Pixel, testen Sie jedoch die Lesbarkeit mit einem Scanner.

---

## Schritt 3: Das erste PNG mit einer Balkenhöhe von 30 Pixeln erzeugen

Die Balkenhöhe bestimmt, wie hoch die Striche erscheinen. Eine Höhe von 30 Pixeln ist ein gängiger Standard für übliche Etiketten.

```csharp
        // Set bar height to 30 pixels
        generator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image as PNG
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png",
                       BarCodeImageFormat.Png);
```

Die Datei `DatabarBarHeight30Pixels.png` enthält nun ein **generate barcode PNG**, das direkt in Webseiten eingebunden oder bei Bedarf ausgedruckt werden kann.

---

## Schritt 4: Die Barcode‑Höhe auf 60 Pixel anpassen und ein zweites PNG speichern

Die Balkenhöhe zu ändern ist so einfach wie das Zuweisen eines neuen Werts zur gleichen Eigenschaft. Damit wird die **adjust barcode height**‑Funktion des Generators demonstriert.

```csharp
        // Change bar height to 60 pixels for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png",
                       BarCodeImageFormat.Png);
    }
}
```

Jetzt haben Sie `DatabarBarHeight60Pixels.png`, das sich ideal für größere Verpackungen eignet, bei denen der Barcode aus größerer Entfernung gescannt werden muss.

**Erwartetes Ergebnis**

- `DatabarBarHeight30Pixels.png` – ein kompakter DataBar Omni‑directional Barcode, 30 px hoch.
- `DatabarBarHeight60Pixels.png` – derselbe Barcode, doppelt so hoch für bessere Sichtbarkeit.

Beide Bilder sind PNG‑Dateien, bewahren verlustfreie Qualität und unterstützen bei Bedarf Transparenz.

---

## Wie man Barcode‑PNG‑Dateien in verschiedenen Formaten erzeugt

Obwohl sich dieses Tutorial auf PNG konzentriert, akzeptiert die `Save`‑Methode weitere Formate wie `Jpeg`, `Bmp` und `Svg`. Um **how to generate barcode**‑Dateien in einem anderen Format zu erzeugen, ersetzen Sie einfach `BarCodeImageFormat.Png` durch den gewünschten Enum‑Wert:

```csharp
generator.Save(@"path\barcode.svg", BarCodeImageFormat.Svg);
```

Die Wahl von SVG ist praktisch, wenn Sie ein Vektorbild benötigen, das ohne Pixelbildung skaliert.

---

## Häufige Stolperfallen beim **create DataBar barcode**‑Bild

| Problem | Ursache | Lösung |
|---------|---------|--------|
| Barcode erscheint unscharf | X‑Dimension zu niedrig für die Zielauflösung | Erhöhen Sie `XDimension.Pixels` auf 3 oder 4 |
| Scanner kann den Code nicht lesen | Barhöhe zu kurz für die Optik des Scanners | Verwenden Sie mindestens 30 Pixel oder folgen Sie den Spezifikationen des Scanners |
| Datenzeichenfolge wird abgelehnt | Falsche GS1‑Formatierung | Stellen Sie sicher, dass die Zeichenfolge mit dem korrekten Anwendungsidentifikator beginnt, z. B. `(01)` für GTIN‑14 |

Das frühzeitige Beheben dieser Punkte spart Zeit bei der Integration von Barcodes in Produktionspipelines.

---

## Fortgeschrittener Tipp: dieselbe Instanz für mehrere Barcodes wiederverwenden

Wenn Sie **generate barcode PNG**‑Dateien für einen Stapel Produkte benötigen, verwenden Sie dieselbe `BarcodeGenerator`‑Instanz erneut und aktualisieren nur die `CodeText`‑Eigenschaft:

```csharp
string[] gtins = { "(01)12345678901231", "(01)98765432109876" };
int[] heights = { 30, 60 };

foreach (var gtin in gtins)
{
    generator.CodeText = gtin;          // Change data payload
    foreach (var h in heights)
    {
        generator.Parameters.Barcode.BarHeight.Pixels = h;
        string fileName = $"Databar_{gtin.Substring(4)}_{h}Px.png";
        generator.Save($@"YOUR_DIRECTORY\{fileName}", BarCodeImageFormat.Png);
    }
}
```

Dieses Muster reduziert den Overhead bei der Objekterstellung und hält Ihren Code kompakt.

---

## Fazit

Sie verfügen nun über einen vollständigen **barcode generator C#**‑Workflow, der **creates DataBar barcodes**, **generates barcode PNG**‑Dateien erzeugt und Ihnen ermöglicht, die **adjust barcode height** mit einer einzigen Eigenschaftsänderung anzupassen. Das Beispiel deckt alles von der Projektkonfiguration bis zur Behandlung von Randfällen ab, sodass Sie die Barcode‑Erstellung mit Vertrauen in jede .NET‑Anwendung integrieren können.

**Nächste Schritte**

- Erkunden Sie weitere Barcode‑Symbologien (`EncodeTypes.QR`, `EncodeTypes.Code128`), um Ihre Lösung zu erweitern.  
- Kombinieren Sie den Generator mit ASP.NET Core, um Barcodes on‑the‑fly über einen API‑Endpunkt bereitzustellen.  
- Experimentieren Sie mit Farboptionen (`generator.Parameters.Barcode.ForeColor`) für Branding‑Zwecke.

Viel Spaß beim Coden, und mögen Ihre Scans stets schnell sein!

## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Codebeispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, weitere API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [Wie man die Barcode‑Höhe für eindimensionale Databar mit Aspose.BarCode für .NET generiert und anpasst](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Eindimensionale Databar‑2D‑Barcodes mit Aspose.BarCode .NET API generieren](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)
- [Wie man DataMatrix‑Barcodes mit Aspose.BarCode für .NET erzeugt – Schritt‑für‑Schritt‑Anleitung](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
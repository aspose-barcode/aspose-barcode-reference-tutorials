---
category: general
date: 2026-07-18
description: Erfahren Sie, wie Sie Barcode‑Bilder mit einem .NET‑Barcode‑Generator
  erzeugen und die Barcode‑Höhe für GS1‑Databar Omni‑Directional‑Symbole einfach ändern
  können.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- .net barcode generator
- how to generate barcode
- change barcode height
- GS1‑Databar Omni‑Directional
- barcode image export
language: de
lastmod: 2026-07-18
og_description: .net Barcode-Generator ermöglicht es Ihnen, schnell Barcode-Bilder
  zu erstellen. Dieser Leitfaden zeigt, wie man Barcodes generiert, die Balkenhöhe
  anpasst und PNG-Dateien speichert.
og_image_alt: Screenshot of a .net barcode generator output showing different bar
  heights
og_title: Barcode-Höhe mit .NET Barcode-Generator ändern
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  headline: .net barcode generator – change barcode height
  type: TechArticle
- description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  name: .net barcode generator – change barcode height
  steps:
  - name: Why each line matters
    text: '| Line | Reason | |------|--------| | `BarcodeGenerator generator = new
      BarcodeGenerator(...);` | Instantiates the **.net barcode generator** with the
      desired symbology and data payload. The `EncodeTypes.DatabarOmniDirectional`
      enum tells the library to use the GS1‑Databar Omni‑Directional format. |'
  - name: Adjusting the X‑dimension for larger prints
    text: '```csharp generator.Parameters.Barcode.XDimension.Pixels = 4; // Double
      the narrow bar width ``` Increasing the X‑dimension makes the whole barcode
      larger without altering the encoded data. This is handy when you print on large
      labels.'
  - name: Switching output formats
    text: '```csharp generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
      ``` SVG scales infinitely, which is perfect for web‑based scanners that need
      crisp vectors.'
  - name: Adding human‑readable text
    text: '```csharp generator.Parameters.Barcode.CodeTextVisible = true; generator.Parameters.Barcode.CodeTextAlignment
      = CodeLocation.Below; ``` Enabling `CodeTextVisible` appends the raw data under
      the barcode, useful for verification during testing.'
  type: HowTo
tags:
- barcode
- .net
- image export
title: .NET Barcode-Generator – Barcode-Höhe ändern
url: /de/python-java/general/net-barcode-generator-change-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .net barcode generator – Barcode-Höhe ändern

Haben Sie sich jemals gefragt, **wie man Barcode**‑Bilder erzeugt, ohne ein Dutzend Drittanbieter‑Tools zu jonglieren? In der .NET‑Welt gibt es einen überraschend sauberen Weg, und das Schlüsselelement ist der **.net barcode generator**. Mit nur wenigen Zeilen C# können Sie ein GS1‑Databar Omni‑Directional‑Symbol erzeugen, die Balkenhöhe anpassen und das Ergebnis in eine PNG‑Datei schreiben.

Wenn Sie ein Inventarsystem, einen Versandetikettendrucker oder irgendeine Anwendung bauen, die einen scannbaren Code benötigt, führt Sie dieses Tutorial in wenigen Minuten von Null zu einem funktionierenden Barcode. Wir gehen den vollständigen Code durch, erklären, warum jede Einstellung wichtig ist, und zeigen Ihnen, wie Sie **die Barcode-Höhe ändern** können, ohne die Spezifikation zu verletzen.

## Was Sie benötigen

- .NET 6.0 oder höher (die API funktioniert gleich auf .NET Framework 4.7+)
- Ein Verweis auf die Barcode‑Bibliothek (z. B. Aspose.BarCode for .NET – dieselben Klassen werden von vielen kommerziellen Kits verwendet)
- Eine Entwicklungsumgebung (Visual Studio, Rider oder VS Code mit der C#‑Erweiterung)
- Ein Ordner, in dem Sie Schreibrechte haben – das Tutorial speichert dort PNG‑Dateien

Das war’s. Keine zusätzlichen NuGet‑Pakete außer der Barcode‑Bibliothek selbst.

## Verwendung des .net barcode generator zum Ändern der Barcode-Höhe

Unten finden Sie ein **vollständiges, ausführbares Konsolenprogramm**. Fügen Sie es in ein neues C#‑Projekt ein, passen Sie den Ausgabepfad an und drücken Sie F5.

```csharp
using System;
using Aspose.BarCode.Generation;   // Namespace for the barcode generator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a barcode generator for a GS1‑Databar Omni‑Directional symbol.
            // The string "(01)12345678901231" follows the GS1 Application Identifier syntax.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Define common visual parameters.
            // X‑dimension controls the width of the narrowest bar; 2 pixels works well for screen display.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set the initial bar height to 30 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Save the first image – a compact barcode.
            string outFolder = @"YOUR_DIRECTORY"; // ← replace with a real path
            generator.Save($"{outFolder}/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 5️⃣ Increase the bar height to 60 pixels for a larger, more readable code.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the second image – a taller barcode.
            generator.Save($"{outFolder}/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two barcode images have been generated successfully.");
        }
    }
}
```

### Warum jede Zeile wichtig ist

| Zeile | Grund |
|------|--------|
| `BarcodeGenerator generator = new BarcodeGenerator(...);` | Instanziiert den **.net barcode generator** mit der gewünschten Symbolik und Datenpayload. Das Enum `EncodeTypes.DatabarOmniDirectional` weist die Bibliothek an, das GS1‑Databar Omni‑Directional‑Format zu verwenden. |
| `XDimension.Pixels = 2;` | Die X‑Dimension ist die Breite des dünnsten Balkens. Das Setzen auf *2 Pixel* liefert ein scharfes Bild auf den meisten Monitoren und hält die Dateigröße gering. |
| `BarHeight.Pixels = 30;` | Dies ist der Schritt zum **Ändern der Barcode-Höhe**, der bestimmt, wie hoch jeder Balken ist. Eine Höhe von 30 Pixel ist ein guter Standard für kleine Etiketten. |
| `generator.Save(...);` | Speichert den Barcode in einer PNG‑Datei. PNG ist verlustfrei, was bedeutet, dass Scanner das exakt erzeugte Muster sehen. |
| `BarHeight.Pixels = 60;` | Hier **ändern wir die Barcode-Höhe** erneut – diesmal auf 60 Pixel. Die Bibliothek rendert das Symbol automatisch mit der neuen Dimension, wenn Sie `Save` ein zweites Mal aufrufen. |
| `Console.WriteLine(...);` | Gibt Ihnen eine schnelle Rückmeldung, dass der Vorgang ohne Ausnahme beendet wurde. |

> **Pro Tipp:** Wenn Sie eine höher aufgelöste Ausgabe für den Druck benötigen, wechseln Sie `BarCodeImageFormat.Png` zu `BarCodeImageFormat.Tiff` und erhöhen Sie die `Resolution`‑Eigenschaft (z. B. `generator.Parameters.ImageResolution = 300;`). Die Balkenhöhe wird weiterhin berücksichtigt, nur mit feinerer DPI gerendert.

## Wie man Barcode‑Bilder mit verschiedenen Einstellungen erzeugt

Das obige Snippet deckt die Grundlagen ab, aber reale Szenarien erfordern oft zusätzliche Anpassungen:

### Anpassen der X‑Dimension für größere Drucke
```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // Double the narrow bar width
```
Das Erhöhen der X‑Dimension vergrößert den gesamten Barcode, ohne die codierten Daten zu ändern. Das ist praktisch, wenn Sie auf großen Etiketten drucken.

### Wechseln der Ausgabeformate
```csharp
generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
```
SVG skaliert unendlich, was perfekt für webbasierte Scanner ist, die scharfe Vektoren benötigen.

### Hinzufügen von menschenlesbarem Text
```csharp
generator.Parameters.Barcode.CodeTextVisible = true;
generator.Parameters.Barcode.CodeTextAlignment = CodeLocation.Below;
```
Durch Aktivieren von `CodeTextVisible` wird der Rohdaten‑Text unter dem Barcode angehängt, was für die Verifizierung während Tests nützlich ist.

## Häufige Fallstricke beim **Ändern der Barcode-Höhe**

1. **Zu geringe Höhe** – Einige Scanner benötigen eine Mindestbalkenhöhe (oft 10 mm in physischen Einheiten). Wenn Sie `BarHeight.Pixels` zu niedrig setzen, könnte das erzeugte Bild auf einem echten Scanner nicht lesbar sein. Testen Sie immer mit Ihrer Zielhardware.
2. **Unpassende X‑Dimension und Höhe** – Eine sehr hohe Balkenhöhe kombiniert mit einer winzigen X‑Dimension kann gestreckt wirken und Decodierungsfehler verursachen. Streben Sie ein ausgewogenes Verhältnis an (ungefähr 3:1 bis 5:1), sofern die Spezifikation nichts anderes verlangt.
3. **Vergessen, Parameter zurückzusetzen** – Der Generator behält den Zustand zwischen den Saves. Wenn Sie `BarHeight` für ein Bild ändern und dann dieselbe Instanz für einen anderen Barcode wiederverwenden, bleibt die vorherige Höhe erhalten. Setzen Sie entweder die Eigenschaft zurück oder instanziieren Sie für jeden unterschiedlichen Barcode einen neuen `BarcodeGenerator`.

## Vollständiges End‑zu‑End‑Beispiel (inklusive NuGet‑Installation)

Wenn Sie von Grund auf neu beginnen, folgen Sie diesen Schritten, um das Projekt zum Laufen zu bringen:

```bash
dotnet new console -n BarcodeHeightDemo
cd BarcodeHeightDemo
dotnet add package Aspose.BarCode
```

Ersetzen Sie die automatisch erzeugte `Program.cs` durch den oben gezeigten Codeblock, **denken Sie daran, `YOUR_DIRECTORY`** durch etwas wie `Path.Combine(Environment.CurrentDirectory, "output")` zu ersetzen. Dann:

```bash
dotnet run
```

Sie sollten zwei PNG‑Dateien im Ordner `output` sehen:

- `DatabarBarHeight30Pixels.png` – ein kompakter 30‑Pixel‑hoher Barcode.
- `DatabarBarHeight60Pixels.png` – eine höhere 60‑Pixel‑Version.

Beide Bilder sehen ähnlich aus, aber das zweite hat merklich längere Balken, was das Lesen mit niedrigauflösenden Scannern erleichtert.

![Barcode height example](/images/barcode-height.png){alt=".net barcode generator Ausgabe, die verschiedene Balkenhöhen zeigt"}

## Zusammenfassung & nächste Schritte

Wir haben behandelt, wie man **Barcode**‑Bilder mit einem **.net barcode generator** erzeugt, die **Barcode-Höhe ändern**‑Eigenschaft fein abgestimmt und die Ergebnisse im PNG‑Format gespeichert. Die wichtigsten Erkenntnisse sind:

- Instanziieren Sie den Generator mit dem richtigen `EncodeTypes`.
- Steuern Sie die visuelle Größe über `XDimension` und `BarHeight`.
- Rufen Sie `Save` nach jeder Änderung auf, um ein neues Bild zu speichern.
- Passen Sie Auflösung und Format an,

## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige funktionierende Codebeispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, weitere API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [Wie man Aztec‑Barcode mit benutzerdefiniertem Seitenverhältnis erzeugt mit Aspose.BarCode für .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Wie man Dotcode‑Erweiterungstext erstellt mit Aspose.BarCode für .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Wie man DataMatrix‑Barcodes (ECC 200) erzeugt mit Aspose.BarCode für .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
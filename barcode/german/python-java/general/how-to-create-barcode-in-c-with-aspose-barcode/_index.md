---
category: general
date: 2026-09-26
description: Erfahren Sie, wie Sie in C# mit Aspose.BarCode Barcodes erstellen. Diese
  Schritt‑für‑Schritt‑Anleitung enthält ein Beispiel für einen Barcode‑Generator und
  zeigt, wie Sie die Balkenhöhe anpassen.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode c#
- barcode generator example
- how to adjust bar height
- change barcode height
- generate barcode aspose
language: de
lastmod: 2026-09-26
og_description: Erstellen Sie einen Barcode in C# mit Aspose.BarCode. Folgen Sie dieser
  Anleitung, um einen Barcode zu generieren, die Balkenhöhe anzupassen und PNG‑Bilder
  zu speichern.
og_image_alt: Diagram illustrating how to create barcode in C# using Aspose.BarCode
og_title: Barcode in C# mit Aspose.BarCode erstellen – vollständige Anleitung
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
    guide includes a barcode generator example and shows how to adjust bar height.
  headline: How to create barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
    guide includes a barcode generator example and shows how to adjust bar height.
  name: How to create barcode in C# with Aspose.BarCode
  steps:
  - name: Import required namespaces
    text: '```csharp using System; using Aspose.BarCode.Generation; using Aspose.BarCode;
      ```'
  - name: Initialise the barcode generator
    text: We’ll generate a **Databar Omni‑Directional** symbol that encodes a GTIN‑14
      value. The constructor takes the symbology and the raw data string.
  - name: Set common barcode parameters
    text: 'Two visual parameters are most often tweaked: the X‑dimension (the narrow
      bar width) and the overall bar height.'
  - name: Save the first image (30‑pixel height)
    text: '```csharp // Save the barcode as a 30‑pixel‑high PNG generator.Save("DatabarBarHeight30Pixels.png",
      BarCodeImageFormat.Png); ```'
  - name: Change the bar height to 60 pixels
    text: Now we demonstrate **how to adjust bar height** at runtime. The same `generator`
      instance is reused; only the `BarHeight` property changes.
  - name: Full source code
    text: 'Putting everything together yields a concise, runnable program:'
  - name: Switching to a different symbology
    text: 'If you need a QR code instead of a Databar, replace the `EncodeTypes` value:'
  - name: Using `BarHeight` in millimetres
    text: 'Aspose.BarCode also supports physical units. To set a height of 10 mm:'
  - name: Handling errors
    text: 'If the data string does not conform to the selected symbology, `BarcodeGenerator`
      throws an `ArgumentException`. Wrap the generation logic in a try‑catch block
      to provide a friendly message:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Wie man einen Barcode in C# mit Aspose.BarCode erstellt
url: /de/python-java/general/how-to-create-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Barcodes in C# mit Aspose.BarCode erstellt  

Wenn Sie **Barcode‑C#‑Projekte** schnell erstellen müssen, bietet Aspose.BarCode eine flüssige API, die das schwere Heben übernimmt. In diesem Tutorial sehen Sie ein komplettes **Barcode‑Generator‑Beispiel**, lernen **wie man die Balkenhöhe anpasst** und exportieren das Ergebnis als PNG‑Dateien.  

Egal, ob Sie ein Einzelhandels‑Kassensystem bauen, Inventur‑Etiketten erzeugen oder Versandetiketten automatisieren – die Möglichkeit, die visuelle Größe eines Barcodes programmgesteuert zu ändern, ist entscheidend. Dieser Leitfaden setzt Grundkenntnisse in C# und einer Entwicklungsumgebung wie Visual Studio 2022 voraus.  

## Voraussetzungen  

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:  

* .NET 6.0 SDK oder neuer installiert.  
* Visual Studio 2022 (oder jede andere C#‑IDE).  
* Eine aktive Aspose.BarCode‑Lizenz (die kostenlose Testversion reicht zum Lernen).  

Sie müssen außerdem das Aspose.BarCode‑NuGet‑Paket zu Ihrem Projekt hinzufügen:

```bash
dotnet add package Aspose.BarCode
```

> **Pro‑Tipp:** Wenn Sie viele Barcodes in einer Schleife erzeugen wollen, verwenden Sie eine einzelne `BarcodeGenerator`‑Instanz und ändern nur die Parameter, die sich ändern. Das reduziert Speicherzuweisungen und verbessert die Leistung.

## Wie man Barcodes in C# mit Aspose.BarCode erstellt  

Die folgenden Abschnitte führen Sie Schritt für Schritt durch das **Barcode‑Generator‑Beispiel**. Der Code ist eigenständig; kopieren Sie ihn in eine neue Konsolenanwendung und führen Sie ihn aus.

### Schritt 1: Erforderliche Namespaces importieren  

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Diese Namespaces geben Ihnen Zugriff auf die Klasse `BarcodeGenerator` und die Aufzählung `EncodeTypes`.

### Schritt 2: Den Barcode‑Generator initialisieren  

Wir erzeugen ein **Databar Omni‑Directional**‑Symbol, das einen GTIN‑14‑Wert kodiert. Der Konstruktor nimmt die Symbolik und den Rohdaten‑String entgegen.

```csharp
// Initialise a generator for Databar Omni‑Directional
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Der Wert `EncodeTypes.DatabarOmniDirectional` teilt Aspose.BarCode mit, welchen Barcode‑Standard es verwenden soll. Der Daten‑String folgt dem GS1‑Application‑Identifier‑Format, das im Einzelhandel üblich ist.

### Schritt 3: Gemeinsame Barcode‑Parameter festlegen  

Zwei visuelle Parameter werden am häufigsten angepasst: die X‑Dimension (die Breite des schmalen Balkens) und die Gesamthöhe der Balken.  

```csharp
// Set the narrow bar width to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set the initial bar height to 30 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

Die **X‑Dimension** steuert die Dichte des Barcodes, während **BarHeight** die vertikale Größe jedes Balkens bestimmt. Das Anpassen von **BarHeight** ist genau das, was Sie benötigen, wenn Sie die **Barcode‑Höhe ändern** möchten, um unterschiedliche Druckmedien zu bedienen.

### Schritt 4: Das erste Bild speichern (30‑Pixel‑Höhe)  

```csharp
// Save the barcode as a 30‑pixel‑high PNG
generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Die Methode `Save` schreibt das gerenderte Bild auf die Festplatte. Der Dateiname gibt die verwendete Höhe klar an, was beim Vergleich verschiedener Ausgaben hilft.

### Schritt 5: Die Balkenhöhe auf 60 Pixel ändern  

Jetzt zeigen wir, **wie man die Balkenhöhe zur Laufzeit anpasst**. Die gleiche `generator`‑Instanz wird wiederverwendet; nur die Eigenschaft `BarHeight` ändert sich.

```csharp
// Increase the bar height to 60 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the larger barcode
generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Da der Generator alle anderen Einstellungen (Symbolik, Daten, X‑Dimension) beibehält, besteht der einzige visuelle Unterschied zwischen den beiden PNG‑Dateien in der vertikalen Größe der Balken.

### Vollständiger Quellcode  

Wenn man alles zusammenfügt, entsteht ein kompaktes, ausführbares Programm:

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
            // 1️⃣ Initialise the generator for Databar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Configure visual parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // narrow bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // first height

            // 3️⃣ Save the 30‑pixel‑high image
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30‑pixel barcode.");

            // 4️⃣ Change the bar height to 60 pixels (how to adjust bar height)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 5️⃣ Save the 60‑pixel‑high image
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60‑pixel barcode.");

            // Optional: clean up resources
            generator.Dispose();
        }
    }
}
```

**Erwartete Ausgabe**  

Beim Ausführen des Programms werden zwei PNG‑Dateien im Arbeitsverzeichnis der ausführbaren Datei erstellt:

* `DatabarBarHeight30Pixels.png` – ein Barcode mit 30 px Balkenhöhe.  
* `DatabarBarHeight60Pixels.png` – derselbe Barcode, jedoch sind die Balken doppelt so hoch.

Öffnen Sie die Bilder in einem beliebigen Betrachter; Sie werden sehen, dass das Gesamtmuster identisch bleibt, während sich die vertikale Dimension ändert, was bestätigt, dass die **Änderung der Barcode‑Höhe** erfolgreich war.

## Erweiterte Varianten  

### Wechsel zu einer anderen Symbolik  

Wenn Sie stattdessen einen QR‑Code benötigen, ersetzen Sie den `EncodeTypes`‑Wert:

```csharp
generator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

Alle anderen Parameter (X‑Dimension, BarHeight) gelten weiterhin, wo sie Sinn ergeben.

### Verwendung von `BarHeight` in Millimetern  

Aspose.BarCode unterstützt auch physische Einheiten. Um eine Höhe von 10 mm festzulegen:

```csharp
generator.Parameters.Barcode.BarHeight.Millimeters = 10;
```

Das ist praktisch, wenn Sie Barcodes für Drucklayouts erzeugen, die exakte Maße erfordern.

### Fehlerbehandlung  

Entspricht der Daten‑String nicht der gewählten Symbolik, wirft `BarcodeGenerator` eine `ArgumentException`. Umhüllen Sie die Generierungslogik mit einem try‑catch‑Block, um eine benutzerfreundliche Meldung auszugeben:

```csharp
try
{
    generator.Save("output.png", BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode data: {ex.Message}");
}
```

## Häufig gestellte Fragen  

* **Beeinflusst das Ändern von BarHeight die Scanbarkeit?**  
  Der Barcode bleibt scanbar, solange die X‑Dimension und die gesamte Ruhezone den Spezifikationen der Symbolik entsprechen. Eine höhere Höhe verlängert lediglich die Balken; sie reduziert niemals den Kontrast.

* **Kann ich unterschiedliche Höhen für einzelne Balken festlegen?**  
  Nein. Die Eigenschaft `BarHeight` gilt einheitlich für das gesamte Symbol. Für variable Höhen benötigen Sie eine eigene Rendering‑Routine, die außerhalb des Umfangs von Aspose.BarCode liegt.

* **Ist PNG das beste Format für den Druck?**  
  PNG bewahrt verlustfreie Pixeldaten und ist ideal für die Anzeige auf Bildschirmen. Für hochauflösende Druckaufträge sollten Sie `BarCodeImageFormat.Tiff` oder `Pdf` in Betracht ziehen, um Vektorinforma‑tionen zu erhalten.

## Fazit  

Sie wissen jetzt, wie man **Barcode‑C#‑Anwendungen** mit Aspose.BarCode **erstellt**, ein komplettes **Barcode‑Generator‑Beispiel** sieht und **wie man die Balkenhöhe anpasst**, um unterschiedlichen Layout‑Anforderungen gerecht zu werden. Durch die Wiederverwendung derselben Generator‑Instanz und das alleinige Ändern von `BarHeight` können Sie die **Barcode‑Höhe ändern**, ohne das gesamte Objekt neu zu bauen.

Von hier aus können Sie weiter erkunden:

* Generieren anderer Symboliken (`EncodeTypes.Code128`, `EncodeTypes.EAN13`).  
* Exportieren nach SVG oder PDF für skalierbare Grafiken.  
* Einbetten von Barcodes direkt in Word‑ oder Excel‑Dokumente mit Aspose.Words bzw. Aspose.Cells.

Viel Spaß beim Coden und genießen Sie die Flexibilität, die Aspose.BarCode Ihren C#‑Barcode‑Projekten verleiht!

## Was sollten Sie als Nächstes lernen?  


Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Codebeispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, weitere API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to create a barcode PNG file with adjustable height in C#](/barcode/english/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/)
- [How to Generate Barcode in C# – Complete Aspose.BarCode Guide](/barcode/english/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
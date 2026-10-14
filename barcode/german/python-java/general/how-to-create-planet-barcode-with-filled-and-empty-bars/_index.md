---
category: general
date: 2026-09-29
description: Erstellen Sie einen Planet‑Barcode in C# mit gefüllten und leeren Balken
  – Schritt‑für‑Schritt‑Anleitung mit Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode XDimension
- filled bars
- empty bars
- Aspose.Barcode C#
language: de
lastmod: 2026-09-29
og_description: Erstellen Sie schnell Planet-Barcodes in C#. Erfahren Sie, wie Sie
  gefüllte Balken rendern, zu leeren Balken wechseln und die X‑Dimension mit Aspose.Barcode
  anpassen.
og_image_alt: 'Screenshot of two Planet barcodes: one with filled bars, one with empty
  bars'
og_title: Erstelle einen Planet‑Barcode mit gefüllten und leeren Balken – C#‑Tutorial
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  headline: How to create planet barcode with filled and empty bars
  type: TechArticle
- description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  name: How to create planet barcode with filled and empty bars
  steps:
  - name: Changing the bar width
    text: If your label printer expects a different bar width, modify the `XDimension.Pixels`
      value. For high‑resolution printers, a value of **2** or **3** pixels may be
      preferable; for low‑resolution printers, **5** or **6** pixels can improve scan
      reliability.
  - name: Using a different image format
    text: Aspose.Barcode supports PNG, JPEG, BMP, GIF, and TIFF. Swap `BarCodeImageFormat.Png`
      with another enum value to match your downstream workflow.
  - name: Generating multiple barcodes in a loop
    text: When you need a batch of Planet barcodes (e.g., for a mailing list), wrap
      the generator logic in a `foreach` loop and change the data string each iteration.
  - name: Handling invalid input
    text: The Planet symbology accepts only numeric strings of **5‑8** digits. Supplying
      an invalid value throws an `ArgumentException`. Guard against this with a simple
      validation method.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Wie man einen Planeten‑Barcode mit gefüllten und leeren Balken erstellt
url: /de/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# So erstellen Sie Planet‑Barcode mit gefüllten und leeren Balken

Wenn Sie **Planet‑Barcode**‑Bilder in C# **erstellen** müssen, zeigt Ihnen diese Anleitung genau, wie Sie sowohl Versionen mit gefüllten als auch mit leeren Balken erzeugen. Sie sehen, wie Sie die Balkenbreite (X‑Dimension) festlegen, die Eigenschaft `FilledBars` umschalten und die Ergebnisse als PNG‑Dateien speichern – alles mit der Aspose.Barcode‑Bibliothek.

Das Erzeugen von Post‑Barcodes ist eine gängige Anforderung für Versand‑Systeme, Mailing‑Listen‑Anwendungen und Logistik‑Dashboards. Am Ende dieses Tutorials besitzen Sie zwei einsatzbereite PNG‑Dateien, die Sie in Berichten, E‑Mails oder Ausdrucke einbetten können.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

| Anforderung | Warum es wichtig ist |
|-------------|----------------------|
| .NET 6.0 oder höher | Stellt die Laufzeit für das C#‑Beispiel bereit. |
| Visual Studio 2022 (oder jede C#‑IDE) | Ermöglicht das Kompilieren und Ausführen des Codes. |
| **Aspose.Barcode for .NET** NuGet‑Paket | Liefert die Klasse `BarcodeGenerator` und `EncodeTypes.Planet`. Installieren Sie es mit `dotnet add package Aspose.Barcode`. |
| Schreibrechte für einen Ordner auf dem Datenträger | Die Methode `Save` schreibt PNG‑Dateien an den von Ihnen angegebenen Pfad. |

## Schritt 1: Projekt einrichten und Namespaces importieren

Erstellen Sie ein neues Konsolen‑Projekt (oder fügen Sie den Code zu einem bestehenden Projekt hinzu) und referenzieren Sie den Aspose.Barcode‑Namespace.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;
```

Diese `using`‑Direktiven geben Ihnen Zugriff auf die Klassen `BarcodeGenerator`, `EncodeTypes` und die Bild‑Format‑Enums, die für das Tutorial benötigt werden.

## Schritt 2: Planet‑Barcode mit Standard‑(gefüllten) Balken erstellen

Der erste Barcode verwendet die Standarddarstellung der Bibliothek, bei der die Balken gefüllt werden.

```csharp
// Initialise a generator for the Planet (postal) barcode with sample data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Optional: adjust the bar width (X dimension) to 4 pixels for clearer printing.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image with filled bars.
string filledPath = @"C:\Barcodes\PlanetFilledBars.png";
barcodeGenerator.Save(filledPath, BarCodeImageFormat.Png);

Console.WriteLine($"Filled Planet barcode saved to: {filledPath}");
```

**Warum das funktioniert:**  
`EncodeTypes.Planet` weist Aspose.Barcode an, die **Planet**‑Symbologie zu verwenden, einen Post‑Barcode, der vom United States Postal Service genutzt wird. Die Eigenschaft `XDimension` steuert die Breite jedes Balkens; ein Wert von 4 Pixel erzeugt einen Barcode, der auf gängigen Etikettendruckern gut lesbar ist. Standardmäßig ist `FilledBars` auf `true` gesetzt, sodass die Balken solide erscheinen.

## Schritt 3: Planet‑Barcode mit leeren Balken erstellen

Um dieselben Daten mit *leeren* Balken zu erzeugen, müssen Sie lediglich das Flag `FilledBars` umschalten, während alle anderen Einstellungen unverändert bleiben.

```csharp
// Re‑use the same variable for clarity.
barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for visual consistency.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Render empty bars instead of filled ones.
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the image with empty bars.
string emptyPath = @"C:\Barcodes\PlanetEmptyBars.png";
barcodeGenerator.Save(emptyPath, BarCodeImageFormat.Png);

Console.WriteLine($"Empty Planet barcode saved to: {emptyPath}");
```

**Warum das wichtig ist:**  
Einige Mail‑Systeme benötigen den **leeren‑Balken**‑Stil, um die Lesbarkeit zu verbessern, wenn der Barcode auf dunklen Hintergründen oder mit kontrastreichen Farbschemata gedruckt wird. Durch `FilledBars = false` zeichnet der Generator nur die Umrisse der Balken, wobei das Innere transparent bleibt.

## Erwartete Ausgabe

Nach dem Ausführen des Programms enthält der Ordner `C:\Barcodes` (oder der von Ihnen gewählte Pfad) zwei PNG‑Dateien:

| Datei | Visuelle Beschreibung |
|------|------------------------|
| `PlanetFilledBars.png` | Balken sind solide schwarze Rechtecke auf weißem Hintergrund. |
| `PlanetEmptyBars.png`  | Balken sind schwarze Umrisse; das Innere jedes Balkens ist transparent (zeigt den Hintergrund). |

Beide Bilder codieren denselben numerischen String `"123456"` und verwenden eine Balkenbreite von 4 Pixel, sodass sie bis auf den Füllstil identisch aussehen.

## Häufige Variationen und Sonderfälle

### Änderung der Balkenbreite

Wenn Ihr Etikettendrucker eine andere Balkenbreite erwartet, passen Sie den Wert `XDimension.Pixels` an. Für hochauflösende Drucker kann ein Wert von **2** oder **3** Pixeln vorteilhaft sein; für niedrigauflösende Drucker können **5** oder **6** Pixel die Scan‑Zuverlässigkeit erhöhen.

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 5; // example for coarse printers
```

### Verwendung eines anderen Bildformats

Aspose.Barcode unterstützt PNG, JPEG, BMP, GIF und TIFF. Ersetzen Sie `BarCodeImageFormat.Png` durch einen anderen Enum‑Wert, um Ihrem nachgelagerten Workflow zu entsprechen.

```csharp
barcodeGenerator.Save("Planet.tiff", BarCodeImageFormat.Tiff);
```

### Generieren mehrerer Barcodes in einer Schleife

Wenn Sie einen Stapel Planet‑Barcodes benötigen (z. B. für eine Mailing‑Liste), kapseln Sie die Generator‑Logik in einer `foreach`‑Schleife und ändern Sie den Daten‑String bei jedem Durchlauf.

```csharp
string[] postalCodes = { "123456", "654321", "112233" };
int index = 1;
foreach (var code in postalCodes)
{
    var gen = new BarcodeGenerator(EncodeTypes.Planet, code);
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    gen.Save($@"C:\Barcodes\Planet_{index}_filled.png", BarCodeImageFormat.Png);
    gen.Parameters.Barcode.FilledBars = false;
    gen.Save($@"C:\Barcodes\Planet_{index}_empty.png", BarCodeImageFormat.Png);
    index++;
}
```

### Umgang mit ungültiger Eingabe

Die Planet‑Symbologie akzeptiert nur numerische Strings mit **5‑8** Ziffern. Wird ein ungültiger Wert übergeben, wirft sie eine `ArgumentException`. Schützen Sie sich mit einer einfachen Validierungsmethode davor.

```csharp
bool IsValidPlanet(string value) => System.Text.RegularExpressions.Regex.IsMatch(value, @"^\d{5,8}$");

string data = "ABC123";
if (!IsValidPlanet(data))
{
    Console.WriteLine("Invalid Planet data – must be 5 to 8 digits.");
    return;
}
```

## Profi‑Tipp: Barcode mit einem Scanner‑Emulator prüfen

Aspose.Barcode enthält die Klasse `BarcodeReader`, mit der Sie bestätigen können, dass das erzeugte Bild wieder in die ursprünglichen Daten dekodiert wird.

```csharp
using Aspose.Barcode.Reader;

// Verify filled barcode
using (BarCodeReader reader = new BarCodeReader(filledPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from filled image: {reader.GetCodeText()}");
}

// Verify empty barcode
using (BarCodeReader reader = new BarCodeReader(emptyPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from empty image: {reader.GetCodeText()}");
}
```

Wenn die Ausgabe für beide Dateien `"123456"` anzeigt, wurde der Barcode korrekt erzeugt.

## Fazit

Sie wissen jetzt, wie Sie **Planet‑Barcode**‑Bilder in C# mit sowohl gefüllten als auch leeren Balken erstellen, die **Planet‑Barcode XDimension** steuern und die Ergebnisse im PNG‑Format mit der **Aspose.Barcode**‑Bibliothek speichern. Passen Sie die Balkenbreite an, wechseln Sie das Bildformat oder iterieren Sie über eine Sammlung von Werten, um jeden Post‑Code‑Workflow zu unterstützen.

Als Nächstes könnten Sie Folgendes erkunden:

* **Menschlich lesbaren Text** unter dem Barcode hinzufügen (`barcodeGenerator.Parameters.Caption.Show = true`).
* **Barcodes in PDF‑Dokumenten** mit Aspose.PDF einbetten.
* **Andere Post‑Symbologien** wie **USPS POSTNET** oder **Intelligent Mail** erzeugen.

Experimentieren Sie gern mit den Parametern und integrieren Sie den Code in Ihr Versand‑ oder Mailing‑System. Viel Spaß beim Coden!

## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Code‑Beispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, weitere API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [Create Planet Barcode in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Create planet barcode in C# – complete programming guide](/barcode/english/python-java/general/create-planet-barcode-in-c-complete-programming-guide/)
- [Barcode generator C# – create Planet barcode and RM4SCC example](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
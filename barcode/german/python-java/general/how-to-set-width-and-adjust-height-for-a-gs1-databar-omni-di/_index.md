---
category: general
date: 2026-09-29
description: Wie man die Breite eines GS1 DataBar Omni‑Directional Barcodes festlegt
  und die Höhe mit C# ändert. Folgen Sie einer Schritt‑für‑Schritt‑Anleitung mit vollständigem
  Code.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to change height
language: de
lastmod: 2026-09-29
og_description: Wie man die Breite eines GS1 DataBar Omni‑Directional Barcodes festlegt
  und die Höhe in C# ändert. Erfahren Sie die genauen API‑Aufrufe und sehen Sie ein
  vollständiges, ausführbares Beispiel.
og_image_alt: Screenshot of two GS1 DataBar barcodes with different heights
og_title: Wie man die Breite eines GS1 DataBar‑Barcodes einstellt – C#‑Leitfaden
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  headline: How to set width and adjust height for a GS1 DataBar Omni‑Directional
    barcode in C#
  type: TechArticle
- description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  name: How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode
    in C#
  steps:
  - name: Why the X‑dimension matters
    text: '* **Scanner tolerance** – Most scanners expect a minimum module width;
      too small a value can cause read errors. * **Print resolution** – When printing
      at 300 dpi, a 2 px module translates to ~0.17 mm, which is within the recommended
      range for GS1 DataBar. * **Image size** – Larger X‑dimension values'
  - name: Tips for reliable width settings
    text: '* **Never set XDimension below 1 px** – the library will clamp the value,
      but the resulting barcode may be unreadable. * **Match the target DPI** – if
      you render to a high‑resolution format (e.g., TIFF at 600 dpi), increase XDimension
      proportionally. * **Test with a real scanner** – after changing t'
  - name: Understanding bar height
    text: '* **Visual balance** – Taller bars improve readability on low‑contrast
      backgrounds but increase the image’s vertical footprint. * **Regulatory limits**
      – Some standards (e.g., retail labeling) specify a maximum bar height; adjust
      accordingly. * **Aspect ratio** – Changing height does not affect the '
  - name: Edge‑case handling for height adjustments
    text: '| Situation | Recommended approach | |-----------|----------------------|
      | Height < 10 px | Increase to at least 10 px; very short bars may be ignored
      by scanners. | | Very tall bars (≥ 100 px) | Verify that the output medium (paper,
      label) can accommodate the extra space. | | Need proportional sca'
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
- GS1 DataBar
title: Wie man die Breite festlegt und die Höhe für einen GS1 DataBar Omni‑Directional-Barcode
  in C# anpasst
url: /de/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man die Breite einstellt und die Höhe eines GS1 DataBar Omni‑Directional Barcodes in C# anpasst

Wie man die Breite eines GS1 DataBar Omni‑Directional Barcodes einstellt, ist eine häufige Aufgabe, wenn Sie genaue Abmessungen für Scangeräte benötigen. In diesem Tutorial lernen Sie außerdem **wie man die Höhe ändert**, sodass der Barcode perfekt in Ihr Layout passt. Der Leitfaden führt Sie durch den gesamten Prozess, von der Projekteinrichtung bis hin zu einem vollständig ausführbaren Code‑Beispiel.

Wir behandeln:

* Das erforderliche NuGet‑Paket und die .NET‑Version.
* Warum die X‑Dimension (Modulbreite) für die Lesbarkeit von Barcodes wichtig ist.
* Die genauen API‑Aufrufe, um **die Breite einzustellen** und **die Höhe zu ändern**.
* Sonderfall‑Behandlung wie minimale Modulbreite und hochauflösende Darstellung.
* Ein komplettes Copy‑and‑Paste‑Beispiel, das zwei PNG‑Dateien mit unterschiedlichen Bar‑Höhen erzeugt.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

| Anforderung | Grund |
|------------|--------|
| .NET 6.0 SDK oder neuer | Das Beispiel verwendet moderne C#‑Features und läuft unter Windows, Linux oder macOS. |
| Visual Studio 2022 (oder jede C#‑IDE) | Bietet IntelliSense für die Aspose.Barcode‑API. |
| **Aspose.Barcode for .NET** NuGet‑Paket | Enthält `BarcodeGenerator`, `EncodeTypes` und Unterstützung für Bildformate. Installieren Sie es mit `dotnet add package Aspose.Barcode`. |
| Schreibberechtigung für einen Ordner, in dem PNG‑Dateien gespeichert werden | Der Generator schreibt die Ausgabebilder auf die Festplatte. |

## Wie man die Breite des Barcodes einstellt

Der Schritt **wie man die Breite einstellt** wird durchgeführt, indem die Eigenschaft `XDimension` der Barcode‑Parameter konfiguriert wird. `XDimension` stellt die Modulbreite (die kleinste Leiste oder Lücke) in Pixeln, Punkten oder Millimetern dar. Die korrekte Einstellung stellt sicher, dass der Barcode die Spezifikationen des Scanners erfüllt.

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a generator for a GS1 DataBar Omni‑Directional barcode.
            // The value "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ **How to set width**: define the module width (X‑dimension) in pixels.
            // A value of 2 px is a common choice that balances readability and image size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // The remaining steps (height, saving) are shown in the next section.
```

### Warum die X‑Dimension wichtig ist

* **Toleranz des Scanners** – Die meisten Scanner erwarten eine minimale Modulbreite; ein zu kleiner Wert kann Lesefehler verursachen.
* **Druckauflösung** – Beim Drucken mit 300 dpi entspricht ein 2 px‑Modul etwa 0,17 mm, was im empfohlenen Bereich für GS1 DataBar liegt.
* **Bildgröße** – Größere X‑Dimension‑Werte erhöhen die Gesamtlänge des Barcodes, was Layout‑Beschränkungen beeinflussen kann.

### Tipps für zuverlässige Breiten‑Einstellungen

* **Setzen Sie XDimension niemals unter 1 px** – Die Bibliothek begrenzt den Wert, aber der resultierende Barcode kann unlesbar sein.
* **Passen Sie die Ziel‑DPI an** – Wenn Sie in ein hochauflösendes Format rendern (z. B. TIFF mit 600 dpi), erhöhen Sie XDimension proportional.
* **Testen Sie mit einem echten Scanner** – Validieren Sie den Barcode nach der Breitenänderung mit dem Gerät, das ihn lesen soll.

## Wie man die Höhe des Barcodes ändert

Sobald die Breite definiert ist, können Sie die vertikale Größe mit der Eigenschaft `BarHeight` steuern. Der folgende Code demonstriert **wie man die Höhe ändert** von 30 px auf 60 px und speichert zwei separate Bilder.

```csharp
            // 3️⃣ Set the first bar height to 30 pixels and save the image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ **How to change height**: increase the bar height to 60 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            // The program ends here; two PNG files are written to the execution folder.
        }
    }
}
```

### Verständnis der Bar‑Höhe

* **Visuelles Gleichgewicht** – Höhere Balken verbessern die Lesbarkeit auf kontrastarmen Hintergründen, erhöhen jedoch den vertikalen Platzbedarf des Bildes.
* **Regulatorische Grenzen** – Einige Standards (z. B. Einzelhandelskennzeichnung) geben eine maximale Balkenhöhe vor; passen Sie sie entsprechend an.
* **Seitenverhältnis** – Das Ändern der Höhe beeinflusst nicht die Modulbreite; Sie können beide unabhängig feinjustieren.

### Sonderfall‑Behandlung für Höhen‑Anpassungen

| Situation | Empfohlener Ansatz |
|-----------|----------------------|
| Höhe < 10 px | Auf mindestens 10 px erhöhen; sehr kurze Balken können von Scannern ignoriert werden. |
| Sehr hohe Balken (≥ 100 px) | Prüfen Sie, ob das Ausgabemedium (Papier, Etikett) den zusätzlichen Raum aufnehmen kann. |
| Proportionale Skalierung erforderlich | Berechnen Sie `BarHeight = XDimension * gewünschtesVerhältnis`, um visuelle Konsistenz zu wahren. |

## Vollständiges, ausführbares Beispiel

Unten finden Sie das komplette Programm, das die Schritte **wie man die Breite einstellt** und **wie man die Höhe ändert** kombiniert. Kopieren Sie den Code in ein neues Konsolenprojekt, stellen Sie das Aspose.Barcode‑NuGet‑Paket wieder her und führen Sie ihn aus. Zwei PNG‑Dateien erscheinen im Ordner `bin/Debug/net6.0`.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // Initialize the barcode generator (GS1 DataBar Omni‑Directional)
            // ------------------------------------------------------------
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // ------------------------------------------------------------
            // **How to set width** – define the module width (X‑dimension)
            // ------------------------------------------------------------
            generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px = ~0.17 mm at 300 dpi

            // ------------------------------------------------------------
            // First image: bar height = 30 px
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight30Pixels.png");

            // ------------------------------------------------------------
            // **How to change height** – increase to 60 px and save again
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight60Pixels.png");

            // ------------------------------------------------------------
            // End of demo
            // ------------------------------------------------------------
        }
    }
}
```

**Erwartete Ausgabe**

Beim Ausführen des Programms werden zwei PNG‑Dateien erzeugt:

* `DatabarBarHeight30Pixels.png` – ein Barcode mit 30 px Höhe und 2 px breiten Modulen.
* `DatabarBarHeight60Pixels.png` – derselbe Barcode mit doppelter vertikaler Größe.

Öffnen Sie eines der Bilder in einem beliebigen Viewer; Sie sehen ein sauberes GS1 DataBar Omni‑Directional‑Symbol, das scanbereit ist.

## Häufig gestellte Fragen

| Frage | Antwort |
|----------|--------|
| *Kann ich Millimeter anstelle von Pixeln verwenden?* | Ja. Setzen Sie `generator.Parameters.Barcode.XDimension.Millimeters` und `BarHeight.Millimeters`. Die Bibliothek konvertiert basierend auf der DPI des Bildes in Geräte‑Pixel. |
| *Was, wenn ich einen anderen Barcode‑Typ benötige?* | Ersetzen Sie `EncodeTypes.DatabarOmniDirectional` durch einen anderen `EncodeTypes`‑Wert (z. B. `EncodeTypes.QR`). Breiten‑ und Höhen‑Eigenschaften funktionieren identisch. |
| *Gibt es eine Möglichkeit, SVG statt PNG zu erzeugen?* | Verwenden Sie `BarCodeImageFormat.Svg` im `Save`‑Aufruf. Die Breiten‑/Höhen‑Einstellungen bleiben gültig. |
| *Muss ich `generator.Dispose()` aufrufen?* | Der `BarcodeGenerator` implementiert `IDisposable`. In einer Konsolen‑App können Sie ihn in einem `using`‑Block einbetten, für kurzlebige Beispiele ist es optional. |

## Fazit

Sie wissen jetzt **wie man die Breite** eines GS1 DataBar Omni‑Directional Barcodes und **wie man die Höhe** mithilfe der Aspose.Barcode‑API in C# einstellt. Das vollständige Beispiel zeigt, wie ein Generator erstellt, `XDimension` und `BarHeight` konfiguriert und PNG‑Dateien mit unterschiedlichen vertikalen Größen gespeichert werden.

Ab hier können Sie:

* Mit anderen `EncodeTypes` experimentieren (z. B. QR, Code128).
* In hochauflösende Formate wie TIFF für den Druck rendern.
* Den Generator in eine Web‑API integrieren, die Barcodes on‑the‑fly zurückgibt.

Viel Spaß beim Coden, und mögen Ihre Barcodes stets sauber scannen!

## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Code‑Beispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, weitere API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [How to Change Barcode Height in C# – Complete Guide](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [How to use a barcode generator C# to create DataBar Omni‑directional barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
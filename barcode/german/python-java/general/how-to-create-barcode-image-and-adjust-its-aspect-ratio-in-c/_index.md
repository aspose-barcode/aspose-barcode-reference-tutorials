---
category: general
date: 2026-10-08
description: Erfahren Sie, wie Sie ein Barcode‑Bild in C# erstellen und entdecken
  Sie, wie Sie das Seitenverhältnis für DataBar‑gestapelte omnidirektionale Barcodes
  anpassen.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust aspect ratio
- Aspose.BarCode C#
- DataBar stacked omni‑directional
- barcode X‑dimension
language: de
lastmod: 2026-10-08
og_description: Erstellen Sie ein Barcode‑Bild in C# und lernen Sie, wie Sie das Seitenverhältnis
  für DataBar‑gestapelte omnidirektionale Barcodes mit einem vollständigen Codebeispiel
  anpassen.
og_image_alt: Result of create barcode image with aspect ratio 15 using Aspose.BarCode
og_title: Barcode‑Bild in C# erstellen – Schritt‑für‑Schritt‑Anleitung
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  headline: How to create barcode image and adjust its aspect ratio in C#
  type: TechArticle
- description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  name: How to create barcode image and adjust its aspect ratio in C#
  steps:
  - name: Expected output
    text: 'After running the program you will find two PNG files in the execution
      directory:'
  - name: What if I need a different X‑dimension?
    text: You can change `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` to
      any integer greater than zero. For very high‑resolution output (e.g., 300 dpi),
      a value of 3‑4 pixels often yields clearer results.
  - name: How do I choose the right aspect ratio?
    text: 'The optimal ratio depends on the scanning environment: * **Low‑profile
      labels** – use a smaller ratio (e.g., 10‑15) to keep the barcode compact. *
      **Large shipping containers** – a higher ratio (e.g., 25‑35) improves readability
      from a distance. * **Regulatory requirements** – some standards mandate'
  - name: Can I generate other barcode formats with the same code?
    text: Yes. Replace `EncodeTypes.DatabarStackedOmniDirectional` with any other
      `EncodeTypes` value (e.g., `EncodeTypes.Code128`). The rest of the code—X‑dimension,
      aspect ratio (if applicable), and saving—remains the same.
  - name: What if I need to create the image in a different format?
    text: '`BarCodeImageFormat` supports PNG, JPEG, BMP, GIF, and TIFF. Just change
      the second argument of `Save`, for example:'
  - name: Next steps
    text: '* Explore other symbologies such as **Code128** or **QR Code** by swapping
      the `EncodeTypes` value. * Combine the barcode generation with PDF creation
      (e.g., using Aspose.PDF) to embed barcodes directly into invoices. * Experiment
      with dynamic aspect‑ratio selection based on label size—this extends '
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Wie man ein Barcode‑Bild erstellt und das Seitenverhältnis in C# anpasst
url: /de/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man ein Barcode‑Bild erstellt und das Seitenverhältnis in C# anpasst

Wenn Sie programmgesteuert **ein Barcode‑Bild erstellen** müssen, zeigt Ihnen dieser Leitfaden eine komplette, sofort ausführbare Lösung. Sie sehen genau **wie man das Seitenverhältnis** für einen DataBar‑Stacked‑Omni‑Directional‑Barcode anpasst, eine Anforderung, die häufig in Einzelhandels‑ und Logistikanwendungen vorkommt.

In diesem Tutorial lernen Sie, wie Sie:
* Einen Aspose.BarCode `BarcodeGenerator` für die DataBar‑Stacked‑Omni‑Directional‑Symbologie initialisieren.  
* Die X‑Dimension (Modulbreite) in Pixeln festlegen, um die Strichstärke zu steuern.  
* Zwei verschiedene Seitenverhältnisse anwenden und jedes Ergebnis als PNG‑Datei speichern.  
* Die Ausgabe überprüfen und verstehen, warum das Seitenverhältnis wichtig ist.

Es werden keine externen Werkzeuge benötigt – nur die Aspose.BarCode für .NET‑Bibliothek und eine .NET 6 (oder höher) Entwicklungsumgebung.

## Wie man ein Barcode‑Bild mit Aspose.BarCode erstellt

Der erste Schritt besteht darin, den Generator mit der gewünschten Symbologie und dem Datenstring zu instanziieren. Der Enum `EncodeTypes.DatabarStackedOmniDirectional` weist Aspose.BarCode an, einen DataBar‑Stacked‑Omni‑Directional‑Barcode zu erzeugen, der häufig für GS1‑128‑Anwendungen verwendet wird.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a BarcodeGenerator for DataBar stacked omni‑directional.
        // The data string "(01)12345678901231" follows the GS1 Application Identifier format.
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Warum das wichtig ist:** Das Objekt `BarcodeGenerator` ist der Einstiegspunkt für alle Barcode‑Erstellungsaufgaben. Durch die Angabe von Symbologie und Rohdaten im Voraus stellen Sie sicher, dass das erzeugte Bild dem GS1‑Standard entspricht.

## Festlegen der X‑Dimension (Modulbreite)

Die X‑Dimension definiert die Breite des schmalsten Strichs (des Moduls). Eine größere X‑Dimension ergibt einen dickeren Barcode, was bei Niedrigauflösungs‑Druckern hilfreich sein kann.

```csharp
        // 2️⃣ Define the X‑dimension in pixels.
        // A value of 2 pixels provides a good balance between readability and file size.
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Warum das wichtig ist:** Die Anpassung der X‑Dimension ist Teil des visuellen Feinabstimmungsprozesses. Sie beeinflusst nicht die codierten Daten, sondern die Scan‑Zuverlässigkeit auf verschiedenen Geräten.

## Wie man das Seitenverhältnis anpasst – erste Version (15)

Das Seitenverhältnis steuert das Höhen‑zu‑Breiten‑Verhältnis des DataBar‑Barcodes. Die Eigenschaft `DataBar.AspectRatio` akzeptiert ganzzahlige Werte; höhere Zahlen erzeugen höhere Striche.

```csharp
        // 3️⃣ Set the aspect ratio to 15 and save the first image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Warum das wichtig ist:** Ein Seitenverhältnis von 15 ist ein gängiger Standard für Einzelhandels‑Scanner. Das resultierende PNG (`DatabarAspectRatio15.png`) wirkt höher, was die Scan‑Erfolgsrate bei Handgeräten verbessern kann.

## Wie man das Seitenverhältnis anpasst – zweite Version (30)

Möglicherweise benötigen Sie einen höheren Barcode für bestimmte Etikettenformate. Das Ändern des Seitenverhältnisses ist so einfach wie das Zuweisen eines neuen ganzzahligen Werts, bevor `Save` erneut aufgerufen wird.

```csharp
        // 4️⃣ Change the aspect ratio to 30 and save a second image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Warum das wichtig ist:** Durch die Demonstration **wie man das Seitenverhältnis anpasst** können Sie mehrere Barcode‑Bilder aus derselben Datenquelle erzeugen, ohne den Generator neu zu erstellen. Das reduziert den Speicherverbrauch und beschleunigt die Batch‑Verarbeitung.

### Erwartete Ausgabe

Nach dem Ausführen des Programms finden Sie zwei PNG‑Dateien im Ausführungsverzeichnis:

| Dateiname                     | Seitenverhältnis | Visuelle Beschreibung |
|-------------------------------|-------------------|-----------------------|
| `DatabarAspectRatio15.png`    | 15                | Standardhöhe, geeignet für die meisten Point‑of‑Sale‑Scanner. |
| `DatabarAspectRatio30.png`    | 30                | Höhere Striche, nützlich für große Etiketten oder Niedrigauflösungs‑Drucker. |

Beide Bilder enthalten dieselbe codierte GTIN `(01)12345678901231`, jedoch unterscheiden sich die visuellen Proportionen gemäß dem eingestellten Seitenverhältnis.

## Häufige Fragen und Sonderfall‑Behandlung

### Was, wenn ich eine andere X‑Dimension benötige?

Sie können `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` auf jede ganze Zahl größer 0 setzen. Für sehr hochauflösende Ausgaben (z. B. 300 dpi) liefert ein Wert von 3‑4 Pixeln häufig klarere Ergebnisse.

### Wie wähle ich das richtige Seitenverhältnis?

Das optimale Verhältnis hängt von der Scan‑Umgebung ab:
* **Flache Etiketten** – ein kleineres Verhältnis (z. B. 10‑15) verwenden, um den Barcode kompakt zu halten.  
* **Große Versandbehälter** – ein höheres Verhältnis (z. B. 25‑35) verbessert die Lesbarkeit aus größerer Entfernung.  
* **Regulatorische Vorgaben** – einige Standards verlangen eine Mindesthöhe; konsultieren Sie die GS1‑Spezifikation für genaue Werte.

### Kann ich mit demselben Code andere Barcode‑Formate erzeugen?

Ja. Ersetzen Sie `EncodeTypes.DatabarStackedOmniDirectional` durch einen anderen `EncodeTypes`‑Wert (z. B. `EncodeTypes.Code128`). Der Rest des Codes – X‑Dimension, Seitenverhältnis (falls zutreffend) und Speichern – bleibt unverändert.

### Was, wenn ich das Bild in einem anderen Format erzeugen muss?

`BarCodeImageFormat` unterstützt PNG, JPEG, BMP, GIF und TIFF. Ändern Sie einfach das zweite Argument von `Save`, zum Beispiel:

```csharp
barcodeGenerator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
```

## Pro‑Tipp: Generator für Batch‑Verarbeitung wiederverwenden

Wenn Sie Dutzende Barcodes mit denselben visuellen Einstellungen erzeugen müssen, instanziieren Sie den Generator einmal, aktualisieren nur die Eigenschaft `CodeText` und rufen `Save` wiederholt auf. Das vermeidet den Overhead, intern wiederholt Puffer zu allokieren.

```csharp
// Example of batch creation
string[] gtins = { "(01)12345678901231", "(01)98765432109876", "(01)55555555555555" };
foreach (var gtin in gtins)
{
    barcodeGenerator.CodeText = gtin;
    barcodeGenerator.Save($"Barcode_{gtin.Substring(4, 6)}.png", BarCodeImageFormat.Png);
}
```

## Fazit

Sie wissen jetzt, wie man **ein Barcode‑Bild** in C# mit Aspose.BarCode erstellt und genau **wie man das Seitenverhältnis** für DataBar‑Stacked‑Omni‑Directional‑Symbole anpasst. Durch die Steuerung von X‑Dimension und Seitenverhältnis können Sie Barcodes erzeugen, die jede Scan‑ oder Layout‑Anforderung erfüllen, und dabei die Implementierung einfach und wartbar halten.

### Nächste Schritte

* Erkunden Sie weitere Symbologien wie **Code128** oder **QR Code**, indem Sie den `EncodeTypes`‑Wert austauschen.  
* Kombinieren Sie die Barcode‑Erstellung mit PDF‑Generierung (z. B. mit Aspose.PDF), um Barcodes direkt in Rechnungen einzubetten.  
* Experimentieren Sie mit einer dynamischen Auswahl des Seitenverhältnisses basierend auf der Etikettengröße – das erweitert das **Wie man das Seitenverhältnis anpasst**‑Muster zu einer vollwertigen Etikett‑Design‑Engine.

Passen Sie das Beispiel gern an, teilen Sie Ihre Ergebnisse oder stellen Sie Nachfragen in den Kommentaren. Viel Spaß beim Coden!


## Was sollten Sie als Nächstes lernen?


Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Code‑Beispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, weitere API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [How to create databar stacked barcode in C# with Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [How to create barcode image with Aspose.Barcode in C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
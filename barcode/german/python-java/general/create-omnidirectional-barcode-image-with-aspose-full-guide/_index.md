---
category: general
date: 2026-07-27
description: Erstellen Sie ein omnidirektionales Barcode‑Bild mit Aspose.BarCode.
  Erfahren Sie, wie Sie mit Aspose einen Barcode generieren, das Seitenverhältnis
  anpassen und PNG‑Dateien speichern.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional barcode image
- generate barcode with aspose
language: de
lastmod: 2026-07-27
og_description: Erstellen Sie ein omnidirektionales Barcode‑Bild mit Aspose. Folgen
  Sie dieser Anleitung, um einen Barcode mit Aspose zu erzeugen, das Seitenverhältnis
  anzupassen und PNGs zu exportieren.
og_image_alt: Screenshot of two omnidirectional barcode images with different aspect
  ratios
og_title: Erstellen Sie ein omnidirektionales Barcode‑Bild mit Aspose – Schritt für
  Schritt
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  headline: Create Omnidirectional Barcode Image with Aspose – Full Guide
  type: TechArticle
- description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  name: Create Omnidirectional Barcode Image with Aspose – Full Guide
  steps:
  - name: 1. Different Image Formats
    text: 'Aspose supports BMP, JPEG, TIFF, and SVG in addition to PNG. Swap the enum
      value:'
  - name: 2. Customizing Colors
    text: 'You might need a white barcode on a dark background. Set `ForeColor` and
      `BackColor`:'
  - name: 3. Handling Invalid Aspect Ratios
    text: 'Aspose validates the range (usually 5‑50). If you pass an out‑of‑range
      value, an `ArgumentException` is thrown. Wrap the save call in a try‑catch to
      give a friendly message:'
  - name: 4. Batch Generation
    text: When you have a list of GTINs, loop over them, update `CodeText`, and save
      each file with a unique name. The generator object can be reused, keeping memory
      usage low.
  type: HowTo
tags:
- barcode
- Aspose
- C#
- image-generation
title: Erstellen eines omnidirektionalen Barcode‑Bildes mit Aspose – Vollständiger
  Leitfaden
url: /de/python-java/general/create-omnidirectional-barcode-image-with-aspose-full-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Erstellen eines omnidirektionalen Barcode‑Bildes mit Aspose – Vollständige Anleitung

Haben Sie jemals **ein omnidirektionales Barcode‑Bild** erstellen müssen, waren sich aber nicht sicher, welche Bibliothek Sie wählen sollten? Sie sind nicht allein. In vielen Logistik‑ und Einzelhandelsprojekten ist das DataBar Stacked Omnidirectional‑Format das Geheimrezept für kompakte, hochdichte Codierung.  

Die gute Nachricht? Mit **Aspose.BarCode** können Sie diesen Barcode in wenigen Zeilen erzeugen, das Seitenverhältnis anpassen und das PNG direkt auf die Festplatte schreiben. Im Folgenden sehen Sie genau, wie Sie **generate barcode with Aspose** generieren, warum jede Einstellung wichtig ist und worauf Sie achten müssen, wenn Sie das Seitenverhältnis ändern.

---

## Was dieses Tutorial abdeckt

Wir gehen den gesamten Lebenszyklus durch:

1. Einrichten des Ausgabeverzeichnisses.
2. Instanziieren eines DataBar Stacked Omnidirectional‑Generators.
3. Konfigurieren von Pixeldimensionen und Seitenverhältnissen.
4. Speichern des Barcodes als PNG‑Dateien.
5. Erweitern des Beispiels für andere Formate und Sonderfälle.

Am Ende haben Sie eine sofort ausführbare C#‑Konsolenanwendung, die zwei unterschiedliche Barcode‑Bilder erzeugt. Keine externen Werkzeuge, nur reiner Aspose‑Code.

**Voraussetzungen**

- .NET 6.0 SDK oder neuer (der Code funktioniert auch mit .NET Framework 4.7.2).
- Aspose.BarCode für .NET NuGet‑Paket (`Install-Package Aspose.BarCode`).
- Ein Ordner auf der Festplatte, in den die Bilder geschrieben werden können.

Wenn Sie das bereits haben, lassen Sie uns loslegen.

---

## Schritt 1: Ausgabeverzeichnis vorbereiten

Zuerst müssen Sie dem Programm mitteilen, wohin die PNG‑Dateien geschrieben werden sollen. Das Hard‑Coden eines Pfads funktioniert für eine Demo, aber in der Produktion würden Sie ihn wahrscheinlich aus einer Konfiguration auslesen.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Define the folder where the images will be saved
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);   // ensures the folder exists
```

*Warum das wichtig ist:* `Directory.CreateDirectory` ist idempotent; es wirft keinen Fehler, wenn das Verzeichnis bereits existiert, sodass Sie auf einen try‑catch‑Block verzichten können.

---

## Schritt 2: Einen DataBar Stacked Omnidirectional‑Generator erstellen

Jetzt starten wir den Generator mit dem spezifischen Kodierungstyp und Beispieldaten. Der String `"(01)12345678901231"` folgt der GS1‑Application‑Identifier‑Syntax für eine 14‑stellige GTIN.

```csharp
        // Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

*Erläuterung:* `EncodeTypes.DatabarStackedOmniDirectional` weist Aspose an, die omnidirektionale Variante zu verwenden, die aus jeder Richtung lesbar ist – ideal für kleine Etiketten, die möglicherweise gedreht werden.

---

## Schritt 3: Gemeinsame Barcode‑Parameter festlegen

Bevor wir etwas rendern, definieren wir die kleinste Elementgröße (X‑Dimension). Ein Wert von **2 Pixeln** erzeugt ein scharfes Bild, ohne die Dateigröße unnötig zu vergrößern.

```csharp
        // Step 3: Set common barcode parameters (pixel size of the smallest element)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Tipp:* Wenn Sie eine höhere Auflösung für den Druck benötigen, erhöhen Sie diesen Wert auf 3 oder 4. Denken Sie jedoch daran, dass größere X‑Dimensionen Breite und Höhe proportional vergrößern.

---

## Schritt 4: Generieren und Speichern mit Seitenverhältnis 15

Die DataBar‑Familie ermöglicht die Anpassung des **Seitenverhältnisses**, das das Verhältnis von Höhe zu Breite steuert. Ein Seitenverhältnis von **15** ist ein gängiger Standard für omnidirektionale Barcodes.

```csharp
        // Step 4: Generate a barcode with an aspect ratio of 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
```

*Was Sie sehen werden:* Ein relativ hoher Barcode, der immer noch bequem auf ein 2 × 1 cm‑Etikett passt. Das PNG‑Format bewahrt verlustfreie Qualität, ideal für weitere Verarbeitung oder Druck.

---

## Schritt 5: Seitenverhältnis auf 30 ändern und erneut speichern

Möchten Sie einen flacheren Barcode? Ändern Sie einfach die Eigenschaft `AspectRatio` und rufen Sie `Save` erneut auf. Es ist nicht nötig, den Generator neu zu erstellen.

```csharp
        // Step 5: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
    }
}
```

*Warum denselben Generator wiederverwenden?* Aspose‑Objekte sind leichtgewichtig; das Ändern einer Eigenschaft und erneutes Speichern ist schneller als das Erzeugen einer neuen Instanz und stellt sicher, dass dieselben Kodierungseinstellungen (z. B. X‑Dimension) konsistent bleiben.

---

## Vollständiges funktionierendes Beispiel

Alles zusammengeführt, hier das komplette, eigenständige Programm, das Sie in ein neues Konsolenprojekt kopieren und einfügen können.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // Initialize generator with omnidirectional DataBar
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Common settings
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // First image – aspect ratio 15
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio15.png");

        // Second image – aspect ratio 30
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio30.png");
    }
}
```

**Erwartete Ausgabe**

Beim Ausführen des Programms wird ein Unterordner `Barcodes` erstellt, der Folgendes enthält:

- `DatabarAspectRatio15.png` – höher, klassisches Aussehen.
- `DatabarAspectRatio30.png` – flacher, besser für breite Etiketten.

Beide Bilder stellen dieselben GTIN‑Daten dar; nur die visuellen Proportionen unterscheiden sich.

---

## Beispiel erweitern (Randfälle & Variationen)

### 1. Verschiedene Bildformate

Aspose unterstützt BMP, JPEG, TIFF und SVG zusätzlich zu PNG. Tauschen Sie den Enum‑Wert aus:

```csharp
barcodeGenerator.Save(Path.Combine(outputFolder, "Databar.svg"),
                      BarCodeImageFormat.Svg);
```

SVG ist vektorbasierend, das heißt, Sie können es skalieren, ohne an Schärfe zu verlieren – praktisch für responsive Web‑Apps.

### 2. Farben anpassen

Vielleicht benötigen Sie einen weißen Barcode auf dunklem Hintergrund. Setzen Sie `ForeColor` und `BackColor`:

```csharp
barcodeGenerator.Parameters.Barcode.ForeColor = System.Drawing.Color.White;
barcodeGenerator.Parameters.Barcode.BackColor = System.Drawing.Color.Black;
```

### 3. Umgang mit ungültigen Seitenverhältnissen

Aspose prüft den Bereich (in der Regel 5‑50). Wenn Sie einen Wert außerhalb dieses Bereichs übergeben, wird eine `ArgumentException` ausgelöst. Verpacken Sie den Save‑Aufruf in ein try‑catch, um eine benutzerfreundliche Meldung auszugeben:

```csharp
try
{
    barcodeGenerator.Save(...);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid aspect ratio: {ex.Message}");
}
```

### 4. Batch‑Generierung

Wenn Sie eine Liste von GTINs haben, iterieren Sie darüber, aktualisieren `CodeText` und speichern jede Datei unter einem eindeutigen Namen. Das Generator‑Objekt kann wiederverwendet werden, wodurch der Speicherverbrauch gering bleibt.

---

## Häufige Fallstricke & Pro‑Tipps

- **Nie vergessen, `XDimension`** vor dem Speichern zu setzen; der Standardwert (0,33 mm) kann auf Displays mit niedriger Auflösung unscharfe Bilder erzeugen.
- **Das Seitenverhältnis ist Höhe‑zu‑Breite**, nicht umgekehrt. Eine größere Zahl macht den Barcode *vertikal kürzer*.
- **Dateipfade:** Verwenden Sie `Path.Combine`, um plattformspezifische Trennzeichenprobleme zu vermeiden – besonders wenn Ihr Code in Linux‑Containern läuft.
- **Lizenzierung:** Aspose.BarCode ist kommerziell. Im Testmodus erscheint ein Wasserzeichen im Bild. Registrieren Sie frühzeitig eine Lizenz, um Überraschungen in der Produktion zu vermeiden.

---

## Fazit

Sie wissen jetzt, wie Sie mit Aspose **ein omnidirektionales Barcode‑Bild erstellen**, das Seitenverhältnis anpassen und PNG‑Dateien exportieren – alles in weniger als 30 Zeilen C#. Dieses Tutorial zeigte den Schritt‑für‑Schritt‑Prozess, erklärte, warum jede Einstellung wichtig ist, und behandelte Erweiterungen wie verschiedene Formate, Farben und Batch‑Verarbeitung.

Bereit für die nächste Herausforderung? Versuchen Sie, QR‑Codes zu erzeugen, den Barcode in ein PDF einzubetten oder die Ausgabe in eine ASP.NET Core‑API zu integrieren. Die gleichen **generate barcode with Aspose**‑Prinzipien gelten für alle Barcode‑Typen, sodass Sie das Gelernte heute wiederverwenden können.

Haben Sie Fragen oder möchten Sie eigene Anpassungen teilen? Hinterlassen Sie unten einen Kommentar – happy coding!

## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Code‑Beispiele mit Schritt‑für‑Schritt‑Erklärungen, die Ihnen helfen, zusätzliche API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Create Barcode Aspose Java - Adjust Image Quality](/barcode/english/java/image-manipulation/adjusting-image-quality-barcode/)
- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
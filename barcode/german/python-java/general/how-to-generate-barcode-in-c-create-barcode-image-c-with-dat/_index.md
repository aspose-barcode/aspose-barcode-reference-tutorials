---
category: general
date: 2026-08-22
description: Wie man Barcode in C# mit Aspose.BarCode erzeugt. Lernen Sie, ein Barcode‑Bild
  in C# Schritt für Schritt zu erstellen, die 2‑D‑Komponente zu deaktivieren und PNG‑Dateien
  zu speichern.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode image c#
language: de
lastmod: 2026-08-22
og_description: Wie man Barcodes in C# mit Aspose.BarCode generiert. Dieses Tutorial
  zeigt, wie man ein Barcode‑Bild in C# mit DataBar Expanded erstellt, die 2‑D‑Komponente
  umschaltet und PNG‑Dateien speichert.
og_image_alt: C# code screenshot generating a DataBar Expanded barcode image without
  the 2‑D component
og_title: Wie man Barcode in C# generiert – vollständige Anleitung zur Erstellung
  eines Barcode‑Bildes in C#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode in C# using Aspose.BarCode. Learn to create
    barcode image c# step‑by‑step, disable the 2‑D component, and save PNG files.
  headline: How to generate barcode in C# – create barcode image c# with DataBar Expanded
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- image generation
title: Wie man Barcode in C# generiert – Barcode‑Bild in C# mit DataBar Expanded erstellen
url: /de/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Barcode in C# generiert – Barcode‑Bild in C# mit DataBar Expanded erstellen

Wie man Barcode in C# generiert, ist ein häufiges Bedürfnis, wenn Sie maschinenlesbare Daten in Ihre Anwendungen einbetten müssen. Dieser Leitfaden zeigt Ihnen, wie Sie mit der Aspose.BarCode‑Bibliothek ein Barcode‑Bild in C# erstellen, die 2‑D‑Composite‑Komponente deaktivieren und das Ergebnis als PNG‑Datei speichern.

Sie erhalten ein vollständiges, ausführbares Programm, eine Erklärung jeder Konfigurationsoption und Tipps zur Anpassung der Ausgabe. Keine externe Dokumentation ist nötig – nur der unten stehende Code und eine .NET‑Entwicklungsumgebung.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie folgendes haben:

* .NET 6.0 SDK oder neuer installiert  
* Visual Studio 2022 (oder eine beliebige IDE, die .NET unterstützt)  
* Aspose.BarCode für .NET NuGet‑Paket (`Aspose.BarCode`)  

Sie können das Paket mit folgendem Befehl hinzufügen:

```bash
dotnet add package Aspose.BarCode
```

Die Bibliothek stellt die Klasse `BarcodeGenerator` bereit, die im gesamten Tutorial verwendet wird.

## Schritt 1: Projekt einrichten und Namespaces importieren

Erstellen Sie eine neue Konsolenanwendung und importieren Sie die benötigten Namespaces:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The rest of the code lives here
        }
    }
}
```

Der Namespace `Aspose.BarCode.Generation` enthält alle Klassen, die zum Konfigurieren und Rendern von Barcodes nötig sind.

## Schritt 2: DataBar Expanded Barcode‑Generator initialisieren

Die erste funktionale Zeile erstellt einen `BarcodeGenerator` für die **DataBar Expanded**‑Symbologie und übergibt den Rohdaten‑String. Der Daten‑String folgt dem GS1 Application Identifier‑Format `(01)12345678901231`.

```csharp
// Step 2: Create a DataBar Expanded barcode generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpanded, "(01)12345678901231");
```

Das Erzeugen des Generators reserviert die interne Bitmap‑Leinwand, sodass Sie Größe und Aussehen vor dem Rendern anpassen können.

## Schritt 3: Modulbreite (X‑Dimension) festlegen

Die X‑Dimension steuert die Breite des kleinsten Barcode‑Elements. Durch Angabe in Pixeln erhalten Sie eine präzise Kontrolle über die endgültige Bildgröße.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Ein Wert von `2` Pixel funktioniert gut für die Anzeige auf Bildschirmen; erhöhen Sie ihn für hochauflösende Drucke.

## Schritt 4: 2‑D‑Composite‑Komponente deaktivieren

DataBar Expanded kann optional eine 2‑D‑Komponente enthalten, die zusätzliche Informationen transportiert. Um einen Barcode **ohne** diese Komponente zu erzeugen, setzen Sie das Flag auf `false`.

```csharp
// Step 4: Disable the 2‑D composite component of the DataBar barcode
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
```

Das Deaktivieren der Komponente reduziert die visuelle Komplexität und erzeugt eine kleinere PNG‑Datei.

## Schritt 5: Barcode‑Bild ohne 2‑D‑Komponente speichern

Wählen Sie ein Ausgabeverzeichnis und schreiben Sie das Bild auf die Festplatte. Der Enum `BarCodeImageFormat.Png` sorgt für eine verlustfreie PNG‑Datei.

```csharp
// Step 5: Save the barcode image without the 2‑D component
string outputDir = "YOUR_DIRECTORY/"; // replace with your actual path
barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png", BarCodeImageFormat.Png);
```

Nach diesem Aufruf enthält `Databar2DComponentDisabled.png` einen sauberen DataBar Expanded Barcode.

## Schritt 6: 2‑D‑Composite‑Komponente aktivieren

Falls Sie die zusätzliche Datenschicht benötigen, aktivieren Sie das Flag wieder. Die gleiche Generator‑Instanz kann wiederverwendet werden, wodurch das Anlegen eines zweiten Objekts vermieden wird.

```csharp
// Step 6: Enable the 2‑D composite component
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
```

## Schritt 7: Barcode‑Bild mit aktivierter 2‑D‑Komponente speichern

Rendern Sie das zweite Bild mit denselben Einstellungen, nur das 2‑D‑Flag wird geändert.

```csharp
// Step 7: Save the barcode image with the 2‑D component enabled
barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png", BarCodeImageFormat.Png);
```

Jetzt zeigt `Databar2DComponentEnabled.png` den Barcode mit dem zusätzlichen 2‑D‑Muster.

## Vollständiger Quellcode

Kopieren Sie das gesamte Snippet unten in `Program.cs` und führen Sie das Projekt aus. Das Programm erzeugt beide PNG‑Dateien im von Ihnen angegebenen Ordner.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Create a DataBar Expanded barcode generator with the desired data
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpanded, "(01)12345678901231");

            // Set the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the output directory (change to a valid path on your machine)
            string outputDir = "YOUR_DIRECTORY/";

            // ---------- First image: 2‑D component disabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png",
                                 BarCodeImageFormat.Png);

            // ---------- Second image: 2‑D component enabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png",
                                 BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

### Erwartete Ausgabe

Beim Ausführen des Programms wird Folgendes ausgegeben:

```
Barcode images generated successfully.
```

und es werden zwei Dateien erstellt:

* `Databar2DComponentDisabled.png` – Barcode ohne 2‑D‑Komponente  
* `Databar2DComponentEnabled.png` – Barcode mit 2‑D‑Komponente  

Öffnen Sie die PNGs in einem beliebigen Bildbetrachter, um den visuellen Unterschied zu prüfen.

## Häufige Varianten und Sonderfälle

| Situation | Anpassung |
|-----------|-----------|
| **Andere Symbologie** | Ersetzen Sie `EncodeTypes.DatabarExpanded` durch einen anderen Wert, z. B. `EncodeTypes.Code128`. |
| **Höhere Auflösung** | Erhöhen Sie `XDimension.Pixels` auf 4 oder 5, oder setzen Sie `Resolution` in `barcodeGenerator.Parameters.Image`. |
| **Andere Bildformate** | Verwenden Sie `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp` oder `BarCodeImageFormat.Svg`. |
| **Ausführung in einer Web‑App** | Streamen Sie die Bild‑Bytes direkt in die HTTP‑Antwort, anstatt sie auf die Festplatte zu schreiben. |
| **Speichermanagement** | Packen Sie den Generator in einen `using`‑Block, wenn Sie .NET Framework anvisieren, um nicht verwaltete Ressourcen freizugeben. |

## Profi‑Tipps

* **Generator wiederverwenden** – Nur das 2‑D‑Flag zu ändern, vermeidet das erneute Instanziieren des Objekts und spart CPU‑Zyklen.  
* **Daten validieren** – GS1‑Daten müssen exakt die geforderte Länge und Prüfsummen‑Regeln einhalten; ungültige Eingaben werfen `ArgumentException`.  
* **Batch‑Verarbeitung** – Durchlaufen Sie eine Sammlung von Daten‑Strings, schalten Sie das 2‑D‑Flag nach Bedarf um und speichern Sie jedes Bild unter einem eindeutigen Dateinamen.  

## Fazit

Sie wissen nun, wie man Barcode in C# generiert und ein Barcode‑Bild in C# mit voller Kontrolle über die 2‑D‑Composite‑Komponente erstellt. Das Beispiel demonstriert das Initialisieren des Generators, das Konfigurieren der X‑Dimension, das Umschalten der Komponente und das Speichern von PNG‑Dateien. Von hier aus können Sie weitere Symbologien erkunden, die Bilder in PDFs einbetten oder die Barcode‑Erzeugung in ASP.NET Core‑Dienste integrieren.

--- 

*Weiterführende Schritte*: Versuchen Sie, QR‑Codes zu erzeugen, experimentieren Sie mit verschiedenen Bildauflösungen oder betten Sie die erzeugten PNGs mithilfe von Aspose.PDF in ein PDF ein. Diese Erweiterungen bauen auf derselben `BarcodeGenerator`‑API auf und halten Ihren Workflow konsistent.

## Was sollten Sie als Nächstes lernen?


Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Code‑Beispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, weitere API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
---
category: general
date: 2026-08-19
description: Erstellen Sie Databar‑PNG‑Dateien in C# mit Aspose.BarCode. Erfahren
  Sie, wie Sie Databar‑Bilder generieren, Databar‑Parameter konfigurieren und die
  PNG‑Ausgabe speichern.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar png
- how to generate databar
- configure databar parameters
language: de
lastmod: 2026-08-19
og_description: Erstellen Sie Databar‑PNG-Dateien in C# mit Aspose.BarCode. Dieses
  Tutorial führt Sie Schritt für Schritt durch die Generierung von Databar‑Bildern,
  die Konfiguration von Databar‑Parametern wie X‑Dimension und Seitenverhältnis und
  das Speichern von hochwertigen PNG‑Dateien für den Druck oder die Web‑Nutzung.
og_image_alt: create databar PNG example
og_title: Erstellen von Databar‑PNG‑Bildern in C# – Schritt‑für‑Schritt‑Anleitung
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Create databar PNG files in C# with Aspose.BarCode. Learn how to generate
    databar images, configure databar parameters, and save PNG output.
  headline: How to create databar PNG images with C# and Aspose.BarCode
  type: TechArticle
tags:
- barcode
- databar
- C#
- PNG
- Aspose.BarCode
title: Wie man Databar‑PNG‑Bilder mit C# und Aspose.BarCode erstellt
url: /de/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Databar‑PNG‑Bilder mit C# und Aspose.BarCode erstellt

Wenn Sie **Databar PNG**‑Dateien in einer .NET‑Anwendung erstellen müssen, zeigt Ihnen dieses Handbuch genau, wie es geht. Sie sehen ein vollständiges, ausführbares Beispiel, das gestapelte omnidirektionale DataBar‑Codes erzeugt, wichtige Parameter konfiguriert und zwei PNG‑Dateien mit unterschiedlichen Seitenverhältnissen speichert.

Das Erzeugen eines DataBar‑Bildes besteht nicht nur darin, eine einzelne Methode aufzurufen. Sie müssen außerdem **Databar‑Parameter** wie die X‑Dimension (Modulbreite) und das Seitenverhältnis konfigurieren, um Druck‑ oder Scan‑Spezifikationen zu erfüllen. Am Ende dieses Tutorials verstehen Sie **wie man Databar**‑Grafiken erzeugt, die in realen Szenarien zuverlässig funktionieren.

## Voraussetzungen

- .NET 6.0 oder höher (der Code funktioniert auch mit .NET Framework 4.7+)
- Visual Studio 2022 oder jede C#‑kompatible IDE
- Eine gültige Lizenz für **Aspose.BarCode for .NET** (die kostenlose Evaluation funktioniert zum Testen)
- Grundlegende Kenntnisse der C#‑Syntax

> **Pro‑Tipp:** Wenn Sie noch keine Lizenz haben, können Sie über das Aspose‑Portal einen temporären Evaluierungsschlüssel anfordern. Die API funktioniert identisch; nur das Wasserzeichen ändert sich.

## Schritt 1: Das Aspose.BarCode‑NuGet‑Paket installieren

Öffnen Sie Ihr Projekt in Visual Studio, klicken Sie mit der rechten Maustaste auf die Lösung und wählen Sie **Manage NuGet Packages**. Suchen Sie nach `Aspose.BarCode` und installieren Sie die neueste stabile Version.

```bash
dotnet add package Aspose.BarCode
```

Dieser Befehl fügt Ihrem Projekt die `Aspose.BarCode`‑Assembly hinzu und macht die Klasse `BarcodeGenerator` verfügbar.

## Schritt 2: Den Barcode‑Generator für einen gestapelten omnidirektionalen DataBar initialisieren

Der Konstruktor von `BarcodeGenerator` erhält zwei Argumente: den Barcode‑Typ und den Rohdaten‑String. Für einen gestapelten omnidirektionalen DataBar verwenden Sie `EncodeTypes.DatabarStackedOmniDirectional`.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace DatabarPngDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Initialize the generator with the desired DataBar type
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // GS1 Application Identifier for a 14‑digit GTIN
```

**Warum das wichtig ist:** Die Konstante `EncodeTypes.DatabarStackedOmniDirectional` weist die Bibliothek an, einen Barcode zu erzeugen, der aus jeder Orientierung gelesen werden kann – ideal für Regaletiketten im Einzelhandel.

## Schritt 3: Die X‑Dimension (Modulbreite) in Pixeln konfigurieren

Die X‑Dimension steuert die Größe des kleinsten Balkenelements. Die Angabe in Pixeln gibt Ihnen präzise Kontrolle über die endgültige Bildgröße.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Ein Wert von **2 Pixel** ist für die meisten Etikettendrucker ein guter Kompromiss zwischen Lesbarkeit und Kompaktheit. Passen Sie diesen Wert an, wenn Sie größere oder kleinere Module benötigen.

## Schritt 4: Das erste Seitenverhältnis festlegen und das PNG speichern

Das Seitenverhältnis beeinflusst die Höhe des gestapelten DataBar. Ein Seitenverhältnis von **15** erzeugt einen relativ kurzen Barcode, während **30** ihn höher macht.

```csharp
            // Step 4: Set an aspect ratio of 15 and save the image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Die Methode `Save` schreibt den erzeugten Barcode in eine PNG‑Datei. PNG ist verlustfrei und bewahrt die scharfen Kanten, die für Barcode‑Scanner erforderlich sind.

## Schritt 5: Das Seitenverhältnis ändern und ein zweites PNG speichern

Sie können dieselbe `BarcodeGenerator`‑Instanz wiederverwenden, um Varianten zu erzeugen, indem Sie einfach das Seitenverhältnis ändern.

```csharp
            // Step 5: Change the aspect ratio to 30 and save a new image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        }
    }
}
```

Jetzt haben Sie zwei PNG‑Dateien – `DatabarAspectRatio15.png` und `DatabarAspectRatio30.png` – jeweils mit unterschiedlicher visueller Dichte.

## Schritt 6: Die Ausgabe überprüfen

Öffnen Sie die erzeugten PNG‑Dateien in einem beliebigen Bildbetrachter. Sie sollten einen sauberen, hochkontrastierten DataBar‑Barcode sehen. Das Scannen der Bilder mit einer Smartphone‑Barcode‑App bestätigt, dass beide Seitenverhältnisse den ursprünglichen GTIN‑Wert `12345678901231` korrekt dekodieren.

![Databar PNG Beispiel erstellen](databar_example.png)

*Das obige Bild zeigt die beiden PNG‑Dateien nebeneinander. Das linke Bild verwendet das Seitenverhältnis 15, das rechte das Seitenverhältnis 30.*

## Häufige Varianten und Randfälle

| Szenario | Was zu ändern ist | Grund |
|----------|-------------------|-------|
| **Andere Daten** | Ersetzen Sie den String `(01)12345678901231` durch einen beliebigen gültigen GS1‑Anwendungsidentifikator und Daten | Ermöglicht das Codieren von Produkt‑IDs, Seriennummern usw. |
| **Höhere Auflösung** | Erhöhen Sie `XDimension.Pixels` auf 3 oder 4 | Notwendig, wenn der Barcode in großen Größen gedruckt oder aus größerer Entfernung gescannt wird. |
| **Andere DataBar‑Typen** | Verwenden Sie `EncodeTypes.DatabarStacked` oder `EncodeTypes.DatabarExpanded` | Wählen Sie den Typ, der am besten zu Ihrem Etikettenlayout passt. |
| **Transparenter Hintergrund** | Übergeben Sie `BarCodeImageFormat.Png` mit `barcodeGenerator.Save(..., BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })` | Praktisch, um den Barcode auf farbigen Etiketten zu überlagern. |

> **Achten Sie darauf:** Eine zu kleine X‑Dimension (< 1 Pixel) kann zu einem unscharfen Barcode führen, der nach dem

## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Handbuch gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Codebeispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, weitere API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Create One-Dimensional Databar GS1 Encoding with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Generate Aspose.BarCode Databar barcode using .NET API – Row & Column Configuration](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
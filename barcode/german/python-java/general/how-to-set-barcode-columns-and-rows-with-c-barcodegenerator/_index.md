---
category: general
date: 2026-09-16
description: Erfahren Sie, wie Sie Barcode‑Spalten in C# mit BarcodeGenerator festlegen
  und außerdem Barcode‑Zeilen für DataBar Expanded Stacked‑Barcodes setzen.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- set barcode columns
- set barcode rows
- DataBar Expanded Stacked
- BarcodeGenerator C#
- barcode image format
- configure barcode dimensions
language: de
lastmod: 2026-09-16
og_description: Barcode‑Spalten in C# schnell festlegen. Dieser Leitfaden zeigt Ihnen,
  wie Sie Spalten, Zeilen und das Bildformat mit BarcodeGenerator konfigurieren.
og_image_alt: DataBar Expanded Stacked barcode showing custom columns and rows
og_title: Barcode-Spalten und -Zeilen in C# festlegen – vollständige BarcodeGenerator-Anleitung
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set barcode columns in C# using BarcodeGenerator and also
    set barcode rows for DataBar Expanded Stacked barcodes.
  headline: How to set barcode columns and rows with C# BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Wie man Barcode‑Spalten und -Zeilen mit C# BarcodeGenerator festlegt
url: /de/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Barcode‑Spalten und -Zeilen mit C# BarcodeGenerator festlegt

Wenn Sie in einer C#‑Anwendung Barcode‑Spalten festlegen müssen, zeigt dieses Tutorial die genauen erforderlichen Schritte. Sie sehen, wie Sie sowohl Spalten als auch Zeilen für einen **DataBar Expanded Stacked**‑Barcode konfigurieren und das Ergebnis als PNG‑Bild speichern.

Das programmgesteuerte Erzeugen von Barcodes erspart Ihnen manuelle Designarbeit und garantiert Konsistenz in Berichten, Rechnungen und Produktetiketten. Das untenstehende Beispiel deckt den gesamten Workflow ab – von der Installation der Bibliothek bis zur Erstellung zweier Bilder: eines mit benutzerdefinierter Spaltenanzahl und eines mit benutzerdefinierter Zeilenanzahl.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

* .NET 6.0 oder höher installiert.
* Einen Verweis auf das **Aspose.BarCode for .NET**‑NuGet‑Paket. Installieren Sie es mit:

```bash
dotnet add package Aspose.BarCode
```

* Schreibzugriff auf einen Ordner, in dem die erzeugten PNG‑Dateien gespeichert werden.

Diese Voraussetzungen stellen sicher, dass der Code kompiliert und ohne zusätzliche Konfiguration ausgeführt wird.

## Wie man Barcode‑Spalten in C# festlegt

Der erste wichtige Schritt besteht darin, eine `BarcodeGenerator`‑Instanz für die **DataBar Expanded Stacked**‑Symbologie zu erstellen und die gewünschte Spaltenanzahl zuzuweisen.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize a DataBar Expanded Stacked barcode generator with the target text.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the number of columns. The DataBar object exposes a Columns property.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image using the PNG format.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**Warum das funktioniert:**  
`EncodeTypes.DatabarExpandedStacked` teilt der Bibliothek mit, welche Symbologie gerendert werden soll. Das Setzen von `Parameters.Barcode.DataBar.Columns` ändert das interne Modul‑Layout, was die visuelle Breite des Barcodes direkt beeinflusst. Die `Save`‑Methode schreibt das Bild im gewünschten `BarCodeImageFormat` auf die Festplatte.

### Erwartetes Ergebnis
Öffnen Sie `C:\Barcodes\DatabarCols4.png` in einem Bildbetrachter. Sie sollten einen DataBar Expanded Stacked‑Barcode sehen, der breiter ist als der Standard, weil er vier Spalten verwendet.

## Wie man Barcode‑Zeilen in C# festlegt

Nachdem Sie das spaltenbasierte Bild gespeichert haben, möchten Sie möglicherweise einen Barcode, dessen Höhe durch Anpassen der Zeilen variiert. Der Vorgang spiegelt die Spaltenkonfiguration wider, nutzt jedoch die Eigenschaft `Rows`.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 4️⃣ Re‑initialize the generator for a fresh configuration.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 5️⃣ Set the number of rows. This property controls the vertical module count.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6️⃣ Save the barcode image with the row configuration.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**Warum das funktioniert:**  
Das erneute Initialisieren des Generators stellt sicher, dass die vorherige Spalteneinstellung die Zeilenkonfiguration nicht beeinflusst. Das Ändern von `Parameters.Barcode.DataBar.Rows` modifiziert die Höhe des Barcodes und erzeugt ein höheres Bild, wenn die Zeilenanzahl den Standard überschreitet.

### Erwartetes Ergebnis
Öffnen Sie `C:\Barcodes\DatabarRows3.png`. Der Barcode erscheint höher und spiegelt die Konfiguration mit drei Zeilen wider.

## Vollständiges End‑zu‑End‑Beispiel

Unten finden Sie ein einzelnes Programm, das beide Bilder in einem Durchlauf erstellt. Der Code in einer Datei zeigt, wie Sie zwischen Spalten‑ und Zeilenkonfigurationen wechseln können, ohne die Anwendung neu zu starten.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Common text for both barcodes.
        const string barcodeText = "Databar Expanded Stacked long";

        // ---------- Column configuration ----------
        var colGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        colGenerator.Parameters.Barcode.DataBar.Columns = 4;
        colGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Row configuration ----------
        var rowGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;
        rowGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

Beim Ausführen des Programms werden zwei PNG‑Dateien erzeugt:

* **DatabarCols4.png** – Barcode mit vier Spalten.  
* **DatabarRows3.png** – Barcode mit drei Zeilen.

Beide Dateien verwenden das **Barcode‑Bildformat** PNG, das scharfe Kanten bewahrt und verlustfreie Kompression unterstützt – ideal für Druck und digitale Anzeige.

## Häufige Fragen und Tipps

| Frage | Antwort |
|----------|--------|
| *Kann ich JPEG anstelle von PNG verwenden?* | Ja. Ersetzen Sie `BarCodeImageFormat.Png` durch `BarCodeImageFormat.Jpeg`. JPEG ist kleiner, führt jedoch zu Kompressionsartefakten, die die Zuverlässigkeit von Scannern beeinträchtigen können. |
| *Wie hoch ist die maximale Anzahl von Spalten oder Zeilen?* | Die Bibliothek prüft die Werte anhand der DataBar‑Spezifikation. Werte außerhalb des zulässigen Bereichs werfen eine `ArgumentException`. Weitere Details finden Sie in der Aspose.BarCode‑Dokumentation. |
| *Muss ich den `BarcodeGenerator` freigeben?* | Die Klasse implementiert `IDisposable`. Um nicht verwaltete Ressourcen zügig freizugeben, sollten Sie den Generator in einem `using`‑Block verwenden, wenn Sie viele Instanzen in einer Schleife erzeugen. |
| *Wie ändere ich die Barcode‑Größe, ohne Spalten/Zeilen zu verändern?* | Nutzen Sie `barcodeGenerator.Parameters.Image.Width` und `Height`, um das Ausgabe‑Bild zu skalieren, während das Modul‑Layout unverändert bleibt. |

**Pro‑Tipp:** Wenn Sie Barcodes für hochauflösenden Druck erzeugen, erhöhen Sie die Bildabmessungen (`Width`/`Height`) statt die Spalten‑ oder Zeilenanzahl. Dieser Ansatz bewahrt die standardisierte Modulgröße der Symbologie und liefert ein schärferes Bild.

## Fazit

Sie wissen jetzt, wie Sie Barcode‑Spalten und -Zeilen in C# mit der **BarcodeGenerator**‑Klasse festlegen. Die Anleitung behandelte das Initialisieren des Generators, das Konfigurieren von Spalten‑ und Zeilenanzahl, das Speichern des Barcodes im PNG‑Format sowie gängige Variationen wie Bildformatwechsel und Ressourcenfreigabe.

Als Nächstes können Sie verwandte Themen erkunden, etwa **Anpassen von Barcode‑Farben**, **Hinzufügen von lesbarem Text** und **Einbetten von Barcodes in PDF‑Dokumente**. All diese Erweiterungen bauen auf dem hier gezeigten Konfigurationsmuster auf und ermöglichen Ihnen, vollwertige Barcode‑Lösungen für jede .NET‑Anwendung zu erstellen.

## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Code‑Beispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, weitere API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [databar expanded stacked barcode guide – how to generate and size it in C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
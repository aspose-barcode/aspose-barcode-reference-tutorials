---
category: general
date: 2026-10-05
description: Erstelle ein Barcode‑PNG in C# und lerne, wie man das Seitenverhältnis
  15 für gestapelte DataBar‑omnidirektionale Barcodes einstellt.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to set aspect ratio
- set aspect ratio 15
language: de
lastmod: 2026-10-05
og_description: Erstellen Sie ein Barcode‑PNG in C# und erfahren Sie, wie Sie das
  Seitenverhältnis 15 für gestapelte DataBar‑omnidirektionale Barcodes in wenigen
  Schritten einstellen.
og_image_alt: Screenshot showing a generated barcode PNG with aspect ratio 15
og_title: Barcode-PNG in C# erstellen – Seitenverhältnis 15 festlegen Tutorial
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Create barcode PNG in C# and learn how to set aspect ratio 15 for stacked
    DataBar omnidirectional barcodes.
  headline: How to create barcode PNG with a custom aspect ratio in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Wie man ein Barcode‑PNG mit einem benutzerdefinierten Seitenverhältnis in C#
  erstellt
url: /de/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Barcode-PNG mit einem benutzerdefinierten Seitenverhältnis in C# erstellt

Wenn Sie in C# **Barcode-PNG erstellen** müssen, zeigt Ihnen dieser Leitfaden, **wie Sie das Seitenverhältnis** 15 für einen gestapelten DataBar omnidirektionalen Barcode festlegen. Wir gehen jede API‑Aufruf durch, erklären, warum das Seitenverhältnis wichtig ist, und geben Ihnen ein vollständiges, ausführbares Beispiel, das Sie in jedes .NET‑Projekt einbinden können.

Das Erzeugen eines Barcode‑Bildes ist eine häufige Anforderung für Inventursysteme, Versandetiketten und Einzelhandels‑Point‑of‑Sale‑Anwendungen. Am Ende dieses Tutorials besitzen Sie eine PNG‑Datei, die exakt den visuellen Spezifikationen Ihres Geschäftspartners entspricht. Keine externen Werkzeuge, keine manuelle Bildbearbeitung — nur Code.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

* .NET 6.0 oder höher (das Beispiel verwendet .NET 6, funktioniert aber auch mit .NET 5+)
* Visual Studio 2022 (oder jede IDE, die .NET unterstützt)
* Das **Aspose.BarCode for .NET** NuGet‑Paket  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Schreibberechtigung für den Ordner, in dem Sie die PNG‑Datei speichern möchten

Diese Anforderungen sind minimal; derselbe Code funktioniert in .NET Core, .NET Framework oder einer Konsolenanwendung.

## Barcode-PNG mit Aspose.BarCode erstellen

Der erste Schritt besteht darin, die Klasse `BarcodeGenerator` mit dem richtigen Barcode‑Typ zu instanziieren. In diesem Fall verwenden wir `EncodeTypes.DatabarStackedOmniDirectional`, das einen gestapelten DataBar erzeugt, der aus jeder Richtung gelesen werden kann.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

*Warum das wichtig ist:* Der Konstruktor nimmt zwei Argumente entgegen — **die Barcode‑Symbologie** und **die Datenzeichenkette**. Das DataBar‑Format erwartet einen GS1‑Anwendungsidentifikator, weshalb die Beispieldaten mit `(01)` beginnen.

## Wie man das Seitenverhältnis für einen gestapelten DataBar festlegt

Die visuelle Breite eines DataBar wird durch die **aspect ratio**‑Eigenschaft gesteuert. Ein höheres Verhältnis macht die Balken breiter, was die Scan‑Zuverlässigkeit bei Niedrig‑Auflösungs‑Druckern verbessern kann.

```csharp
// Step 2: Define the module width (X‑dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Die `XDimension` definiert die Größe eines einzelnen Moduls (der kleinste Balken oder Abstand). Bei 2 px bleibt das Bild klar und hochdicht, was für die meisten Etikettendrucker geeignet ist.

## Seitenverhältnis 15 festlegen – Code‑Durchgang

Jetzt setzen wir die Anforderung **set aspect ratio 15** um. Dies ist der Kern des Tutorials und demonstriert den genauen API‑Aufruf, den Sie benötigen.

```csharp
// Step 3: Set the DataBar aspect ratio to 15 for a wider appearance
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

*Warum 15?* Das Standard‑Seitenverhältnis für gestapelte DataBar ist 12. Eine Erhöhung auf 15 vergrößert die Breite jedes Balkens um 25 %, was häufig den Vorgaben von Logistik‑Dienstleistern entspricht, die einen breiteren Barcode für schnelleres Scannen verlangen.

## Barcode als PNG speichern

Nachdem der Generator konfiguriert ist, besteht der letzte Schritt darin, das Bild auf die Festplatte zu schreiben. Die Methode `Save` akzeptiert einen Dateipfad und ein Bildformat‑Enum.

```csharp
// Step 4: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Das PNG‑Format bewahrt verlustfreie Qualität und stellt sicher, dass der Barcode auf jedem Display oder Drucker exakt wie vorgesehen dargestellt wird.

## Vollständiges Beispiel und erwartete Ausgabe

Unten finden Sie das komplette Programm, das Sie in die `Main`‑Methode einer Konsolen‑App kopieren können. Es enthält alle oben beschriebenen Schritte sowie eine kleine Bestätigungsnachricht.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with stacked DataBar (omnidirectional) and sample GS1 data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Set the DataBar aspect ratio to 15 – this is the key to a wider barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;

        // Choose a folder you have write access to
        string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";

        // Save the barcode as a PNG file
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode PNG created at: {outputPath}");
    }
}
```

**Erwartete Ausgabe**

Beim Ausführen des Programms wird eine Datei namens `DatabarAspectRatio15.png` erstellt, die einen klaren, breiten gestapelten DataBar‑Barcode enthält. Öffnen Sie die PNG, sehen Sie einen horizontal gestreckten Barcode, der dennoch den GS1‑DataBar‑Spezifikationen entspricht.

![Barcode PNG with aspect ratio 15](barcode-aspect15.png)

*Bild-Alt-Text:* **Barcode-PNG erstellen, das einen gestapelten DataBar mit Seitenverhältnis 15 zeigt**

### Tipps und häufige Fallstricke

| Situation | Empfehlung |
|-----------|------------|
| **Bild ist unscharf** | Erhöhen Sie `XDimension.Pixels` auf 3 px oder mehr, achten Sie jedoch darauf, dass die Gesamtbildgröße unter 500 px bleibt, um übergroße Dateien zu vermeiden. |
| **Scanner kann den Code nicht lesen** | Stellen Sie sicher, dass die Datenzeichenkette dem GS1‑Format (`(01)`‑Präfix) entspricht. Außerdem sollte die Druckerauflösung mindestens 300 dpi betragen. |
| **Ein anderes Dateiformat benötigt** | Ersetzen Sie `BarCodeImageFormat.Png` durch `Jpeg`, `Bmp` oder `Gif` — die API unterstützt alle gängigen Rasterformate. |
| **Ausführung in einer Webanwendung** | Verwenden Sie `generator.Save(Stream, BarCodeImageFormat.Png)`, um direkt in die HTTP‑Antwort zu schreiben, ohne das Dateisystem zu berühren. |

### Beispiel erweitern

* **Mehrere Barcodes in einem Bild:** Erzeugen Sie zusätzliche `BarcodeGenerator`‑Instanzen und zeichnen Sie sie mit `Graphics` auf ein einzelnes `Bitmap`.  
* **Human‑readable Text hinzufügen:** Setzen Sie `generator.Parameters.Caption.Visible = true` und passen Sie die Schriftart über `generator.Parameters.Caption.Font` an.  
* **Dynamisches Seitenverhältnis:** Lesen Sie den Ratio‑Wert aus einer Konfigurationsdatei oder Datenbank, um Barcodes mit variabler Breite on‑the‑fly zu erzeugen.

## Fazit

In diesem Tutorial haben Sie gelernt, wie man **Barcode-PNG** in C# erstellt und präzise **Seitenverhältnis 15** für einen gestapelten DataBar omnidirektionalen Barcode festlegt. Der vollständige, ausführbare Code demonstriert jeden erforderlichen API‑Aufruf, erklärt, warum jede Einstellung wichtig ist, und liefert praktische Tipps für den Einsatz in der Praxis.  

Als Nächstes können Sie **wie man das Seitenverhältnis** für andere Barcode‑Typen (z. B. QR‑Code oder Code 128) festlegt oder den Generator in einen ASP .NET Core‑Dienst integrieren, der Barcode‑Bilder auf Abruf liefert. Viel Spaß beim Coden!

## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Codebeispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, weitere API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [Wie man Databar-PNG‑Bilder mit C# und Aspose.Barcode erstellt](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [Wie man gestapelte Databar‑Barcodes in C# mit Aspose.Barcode erstellt](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [Databar‑gestapeltes omnidirektionales Seitenverhältnis in .NET anpassen](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
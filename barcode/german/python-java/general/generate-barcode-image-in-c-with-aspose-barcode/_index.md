---
category: general
date: 2026-08-06
description: Barcode-Bild in C# mit Aspose.BarCode generieren. Erfahren Sie, wie Sie
  Databar erzeugen, die benutzerdefinierte Barcode‑Größe anpassen und die Barcode‑Höhe
  mit einfachem Code ändern.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- how to generate databar
- custom barcode size
- create databar barcode
- change barcode height
language: de
lastmod: 2026-08-06
og_description: Erzeugen Sie ein Barcode‑Bild in C# mit Aspose.BarCode. Dieses Tutorial
  zeigt Ihnen, wie Sie einen Databar‑Omnidirectional‑Barcode erstellen, seine Größe
  anpassen und die Barcode‑Höhe effizient ändern.
og_image_alt: Screenshot of a Databar barcode generated with custom height in C#
og_title: Barcode-Bild in C# generieren – vollständige Aspose.BarCode-Anleitung
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Generate barcode image in C# using Aspose.BarCode. Learn how to generate
    Databar, adjust custom barcode size, and change barcode height with simple code.
  headline: Generate barcode image in C# with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: The evaluation version of Aspose.BarCode works without a license but adds
      a small watermark. For production use, apply a purchased license using `License
      license = new License(); license.SetLicense("Aspose.BarCode.lic");`.
    question: Can I generate a barcode without installing a license?
  - answer: Yes. Very small X‑dimensions can make the barcode unreadable on low‑resolution
      printers. A minimum of 1 px for screen rendering is recommended; for print,
      use at least 0.25 mm.
    question: Does changing the X‑dimension affect readability?
  - answer: 'Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. You
      may also set `generator.Parameters.ImageQuality` to control compression. ##
      Conclusion You now know how to **generate barcode image** in C# using Aspose.BarCode,
      how to **create Databar barcode**, adjust a **custom barcode size**, '
    question: What if I need to generate a barcode in JPEG format?
  type: FAQPage
tags:
- barcode
- C#
- Aspose.BarCode
title: Barcode-Bild in C# mit Aspose.BarCode generieren
url: /de/python-java/general/generate-barcode-image-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode‑Bild in C# mit Aspose.BarCode erzeugen

Wenn Sie **Barcode‑Bilder** programmgesteuert **generieren** müssen, zeigt Ihnen dieses Handbuch genau, wie es geht. Egal, ob Sie ein Einzelhandels‑Inventarsystem oder ein Logistik‑Tracking‑Portal bauen – Sie sehen den kompletten Workflow zum Erstellen eines Databar‑Omnidirectional‑Barcodes, zum Anpassen seiner Abmessungen und zum Speichern des Ergebnisses als PNG‑Datei.

Das Erzeugen eines Barcode‑Bildes ist ein häufiges Anforderungs­szenario, doch Entwickler fragen sich oft **wie man Databar** mit exakt der benötigten Größe erzeugt. In diesem Tutorial lernen Sie, einen Databar‑Barcode zu erstellen, seine Breite und Höhe anzupassen und die Barcode‑Höhe zu ändern, ohne den gesamten Generator neu zu schreiben.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie folgendes haben:

* .NET 6.0 SDK oder neuer (der Code funktioniert mit .NET Core und .NET Framework)
* Visual Studio 2022 (oder jede IDE, die C# unterstützt)
* Eine gültige Aspose.BarCode‑für‑.NET‑Lizenz (die kostenlose Evaluierung funktioniert zum Testen)
* Grundkenntnisse in C#‑Syntax

## Schritt 1: Aspose.BarCode installieren

Fügen Sie das Aspose.BarCode‑NuGet‑Paket zu Ihrem Projekt hinzu:

```bash
dotnet add package Aspose.BarCode
```

Das Paket enthält die Klasse `BarcodeGenerator`, die im gesamten Tutorial verwendet wird. Nach der Installation führen Sie eine Wiederherstellung des Projekts durch, um die Abhängigkeiten zu holen.

## Schritt 2: Einen einfachen Barcode‑Generator erstellen

Die erste Code‑Zeile erzeugt einen **Barcode‑Generator**, der ein Databar‑Omnidirectional‑Symbol produziert. Der Enum‑Wert `EncodeTypes.DatabarOmniDirectional` teilt der Bibliothek mit, welche Symbolik verwendet werden soll, und die Datenzeichenfolge folgt der GS1‑Application‑Identifier‑Syntax.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a Databar Omnidirectional barcode
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231"); // GS1-14 data (example GTIN)
```

**Warum das wichtig ist:** Das Objekt `BarcodeGenerator` ist der Einstiegspunkt für jede Barcode‑Operation. Durch die Auswahl von `DatabarOmniDirectional` stellen Sie sicher, dass die Ausgabe dem GS1‑Standard für Einzelhandels‑Scans entspricht.

## Schritt 3: Eine benutzerdefinierte X‑Dimension (Modulbreite) festlegen

Die X‑Dimension steuert die Breite des schmalsten Strichs. Wird ein kleiner Pixelwert gesetzt, erhalten Sie einen kompakten Barcode; größere Werte vergrößern die Gesamtabmessung.

```csharp
        // Step 3: Define a custom X‑dimension (module width) of 2 px
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Erläuterung:** Eine X‑Dimension von 2 Pixel ist eine gängige Wahl für hochauflösende Bildschirme. Passen Sie diesen Wert an, wenn Sie eine dichtere oder lockerere optische Dichte benötigen.

## Schritt 4: Das erste Barcode‑Bild mit einer bestimmten Höhe erzeugen

Die Barcode‑Höhe ist unabhängig von der X‑Dimension. Hier setzen wir die Strich‑Höhe auf **30 px** und speichern das Bild als PNG.

```csharp
        // Step 4: Set bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**Ergebnis:** Sie erhalten jetzt eine Datei namens `DatabarBarHeight30Pixels.png`, die einen Databar‑Barcode mit 30 px Höhe zeigt. Das demonstriert die **benutzerdefinierte Barcode‑Größe** für Anwendungsfälle wie ein kleines Etikett.

## Schritt 5: Barcode‑Höhe für eine größere Version ändern

Muss derselbe Barcode auf einem größeren Etikett erscheinen, ändern Sie einfach die Höhen‑Eigenschaft und verwenden dieselbe Generator‑Instanz erneut.

```csharp
        // Step 5: Increase the bar height to 60 px for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
    }
}
```

**Warum Sie den Generator wiederverwenden können:** Das Ändern von `BarHeight.Pixels` aktualisiert das interne Layout, ohne das Objekt neu zu erzeugen, was Speicher spart und die Datenzeichenfolge unverändert lässt. Das ist der empfohlene Weg, um **die Barcode‑Höhe** zur Laufzeit zu ändern.

## Schritt 6: Ausgabe überprüfen

Öffnen Sie die beiden PNG‑Dateien in einem Bildbetrachter. Sie sollten zwei Databar‑Omnidirectional‑Barcodes sehen, die dieselbe GTIN kodieren, sich jedoch in der vertikalen Größe unterscheiden:

* `DatabarBarHeight30Pixels.png` – 30 px hoch, geeignet für kompakte Kassenbons.
* `DatabarBarHeight60Pixels.png` – 60 px hoch, ideal für größere Regalkanten‑Etiketten.

Beide Bilder behalten dieselbe X‑Dimension bei, sodass das Strich‑zu‑Leer‑Verhältnis konsistent bleibt, während die Gesamthöhe skaliert wird.

## Häufige Varianten und Sonderfälle

| Situation | Vorgehensweise |
|-----------|----------------|
| **Andere Barcode‑Symbolik** | Ersetzen Sie `EncodeTypes.DatabarOmniDirectional` durch einen anderen Enum‑Wert (z. B. `EncodeTypes.Code128`). Der restliche Code bleibt unverändert. |
| **Nicht‑Pixel‑Abmessungen** | Verwenden Sie `generator.Parameters.Barcode.XDimension.Millimeters` oder `BarHeight.Millimeters`, wenn Sie physische Maße für druckfertige Ausgaben benötigen. |
| **Transparenter Hintergrund** | Setzen Sie `generator.Parameters.ImageBackgroundColor = Color.Transparent;` bevor Sie `Save` aufrufen. |
| **High‑Resolution‑Ausgabe** | Erhöhen Sie sowohl `XDimension.Pixels` als auch `BarHeight.Pixels` proportional oder speichern Sie als `BarCodeImageFormat.Tiff` für verlustfreie Qualität. |
| **Mehrere Barcodes in einem Bild** | Erzeugen Sie separate `BarcodeGenerator`‑Instanzen, rendern Sie jede zu einem `Bitmap` und setzen Sie sie anschließend mit `Graphics.DrawImage` zusammen. |

**Pro‑Tipp:** Testen Sie den erzeugten Barcode immer mit einem echten Scanner, bevor Sie ihn in die Produktion geben. Scanner können sehr dünne Striche je nach Beleuchtung und Sensorqualität unterschiedlich interpretieren.

## Vollständiger Quellcode zum Nachschlagen

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator for a Databar Omnidirectional barcode
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231"); // Example GTIN

            // Custom X‑dimension (module width) – 2 px
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image: 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // Second image: 60 px height (larger barcode)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

Kopieren Sie den Code in ein neues Konsolen‑Projekt, führen Sie ihn aus, und Sie sehen die beiden PNG‑Dateien im Ausgabeverzeichnis erscheinen.

## Häufig gestellte Fragen

**F: Kann ich einen Barcode ohne Lizenz erzeugen?**  
A: Die Evaluierungs‑Version von Aspose.BarCode funktioniert ohne Lizenz, fügt jedoch ein kleines Wasserzeichen hinzu. Für den Produktionseinsatz verwenden Sie eine gekaufte Lizenz mit `License license = new License(); license.SetLicense("Aspose.BarCode.lic");`.

**F: Beeinflusst das Ändern der X‑Dimension die Lesbarkeit?**  
A: Ja. Sehr kleine X‑Dimensionen können den Barcode auf Niedrig‑Auflösungs‑Druckern unlesbar machen. Für die Bildschirmdarstellung wird ein Minimum von 1 px empfohlen; für den Druck mindestens 0,25 mm.

**F: Was, wenn ich einen Barcode im JPEG‑Format erzeugen muss?**  
A: Ersetzen Sie `BarCodeImageFormat.Png` durch `BarCodeImageFormat.Jpeg`. Sie können zudem `generator.Parameters.ImageQuality` setzen, um die Kompression zu steuern.

## Fazit

Sie wissen jetzt, wie man **Barcode‑Bilder** in C# mit Aspose.BarCode **generiert**, wie man **Databar‑Barcodes** erstellt, eine **benutzerdefinierte Barcode‑Größe** anpasst und **die Barcode‑Höhe** bei Bedarf ändert. Das vollständige Beispiel demonstriert den gängigsten Workflow, und die Variationstabelle befähigt Sie, reale Sonderfälle zu bewältigen.

Als Nächstes können Sie verwandte Themen erkunden, etwa **Barcodes in PDF‑Dokumenten einbetten**, **mehrere Barcodes stapelweise erzeugen** und **QR‑Codes für mobile Zahlungen verwenden**. All diese Szenarien bauen auf denselben Prinzipien auf, sodass Sie dieses Wissen sicher erweitern können.

Viel Spaß beim Coden und möge Ihr Barcode stets fehlerfrei gescannt werden!

## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in diesem Leitfaden gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Code‑Beispiele mit Schritt‑für‑Schritt‑Erklärungen, damit Sie weitere API‑Funktionen meistern und alternative Implementierungs‑Ansätze in Ihren Projekten erkunden können.

- [Generate barcode image – GS1 Coupon UPC‑A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
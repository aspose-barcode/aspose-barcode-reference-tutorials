---
category: general
date: 2026-10-28
description: Erstelle ein Barcode‑Bild in C# und lerne, wie du die Höhe mit der BarcodeGenerator‑API
  anpassen kannst. Schritt‑für‑Schritt‑Anleitung zur benutzerdefinierten Barcode‑Höhe
  und zum Ändern der Balkenhöhe.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust height
- c# barcode generator
- custom barcode height
- change barcode height
language: de
lastmod: 2026-10-28
og_description: Erstelle ein Barcode‑Bild in C# und sieh sofort, wie du die Höhe anpassen
  kannst. Folge diesem vollständigen Beispiel, um die benutzerdefinierte Barcode‑Höhe
  mit dem BarcodeGenerator festzulegen.
og_image_alt: Screenshot showing a generated barcode image with a custom height
og_title: Barcode-Bild mit benutzerdefinierter Höhe in C# erstellen – vollständige
  Anleitung
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode image in C# and learn how to adjust height using the
    BarcodeGenerator API. Step‑by‑step guide for custom barcode height and changing
    bar height.
  headline: Create barcode image with custom height in C#
  type: TechArticle
tags:
- barcode
- C#
- image generation
- GS1‑Databar
title: Barcode-Bild mit benutzerdefinierter Höhe in C# erstellen
url: /de/python-java/general/create-barcode-image-with-custom-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode-Bild mit benutzerdefinierter Höhe in C# erstellen

Wenn Sie **ein Barcode‑Bild erstellen** und seine Abmessungen steuern müssen, zeigt Ihnen diese Anleitung genau, wie das geht. Mit der Aspose.BarCode .NET‑Bibliothek können Sie einen GS1‑Databar Omni‑Directional‑Barcode erzeugen und anschließend **die Höhe anpassen**, um jede Layout‑Anforderung zu erfüllen.

Sie gehen ein vollständiges, ausführbares Programm durch, das einen **c# barcode generator** demonstriert, jede von Ihnen gesetzte Eigenschaft erklärt und zwei verschiedene Ausgaben zeigt – eine mit einer Balkenhöhe von 30 Pixel und eine mit einer Balkenhöhe von 60 Pixel. Am Ende können Sie **die Barcode‑Höhe** programmgesteuert für jeden von der Bibliothek unterstützten Barcode‑Typ ändern.

## Voraussetzungen

- .NET 6.0 SDK oder neuer (der Code funktioniert auch mit .NET Framework 4.6+)
- Visual Studio 2022 oder ein beliebiger Editor, der C#‑Projekte bauen kann
- Aspose.BarCode für .NET NuGet‑Paket (`Install-Package Aspose.BarCode`)
- Grundlegende Kenntnisse der C#‑Syntax

> **Pro‑Tipp:** Wenn Sie eine CI‑Pipeline verwenden, fügen Sie das NuGet‑Paket zu Ihrer `csproj`‑Datei hinzu, damit der Build es automatisch wiederherstellt.

## Schritt 1: Projekt einrichten und Namespaces importieren

Erstellen Sie ein neues Konsolenprojekt und fügen Sie die erforderlichen `using`‑Anweisungen hinzu. Die Namespaces geben Ihnen Zugriff auf `BarcodeGenerator`, `EncodeTypes` und Bildformat‑Hilfsfunktionen.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // The rest of the tutorial code lives here.
        }
    }
}
```

> **Warum das wichtig ist:** Das Importieren der richtigen Namespaces verhindert Compile‑Zeit‑Fehler und macht die API in IntelliSense auffindbar.

## Schritt 2: Initialisieren des **c# barcode generator** für einen GS1‑Databar Omni‑Directional‑Code

Der Konstruktor erwartet zwei Argumente: den Barcode‑Typ (`EncodeTypes.DatabarOmniDirectional`) und die Datenzeichenkette. Die Datenzeichenkette muss dem GS1‑Application‑Identifier‑Format entsprechen, z. B. `(01)12345678901231`.

```csharp
// Create a barcode generator for a GS1‑Databar Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional,
    "(01)12345678901231");
```

> **Erklärung:** Das `BarcodeGenerator`‑Objekt ist der Einstiegspunkt für alle barcode‑bezogenen Einstellungen. Sobald Sie diese Instanz haben, können Sie Abmessungen, Farben und das Ausgabeformat anpassen.

## Schritt 3: Gemeinsame X‑Dimension festlegen (Pixelbreite des schmalsten Balkens)

Eine X‑Dimension von 2 Pixel ist ein guter Ausgangspunkt für die meisten Anzeige‑Szenarien.

```csharp
// Set a 2‑pixel X‑dimension (width of the smallest bar)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Warum X‑Dimension setzen?** Sie steuert die Gesamtlänge des Barcodes. Wenn sie konsistent bleibt, wird durch das Ändern der Balkenhöhe das visuelle Gleichgewicht nicht verzerrt.

## Schritt 4: **Barcode‑Bild erstellen** mit einer Balkenhöhe von 30 Pixel

Jetzt konfigurieren wir die Balkenhöhe, speichern das erste Bild und ändern anschließend die Höhe für das zweite Bild.

```csharp
// Configure a 30‑pixel bar height
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

// Save the first image
string output30 = "DatabarBarHeight30Pixels.png";
barcodeGenerator.Save(output30, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 30 px height to {output30}");
```

> **Ergebnis:** Sie erhalten eine PNG‑Datei, bei der jeder vertikale Balken 30 Pixel hoch ist. Die X‑Dimension bleibt bei 2 Pixel, sodass die Gesamtlänge unverändert bleibt.

## Schritt 5: **Wie man die Höhe anpasst** – Balkenhöhe auf 60 Pixel ändern

Um **eine benutzerdefinierte Barcode‑Höhe** zu demonstrieren, weisen Sie einfach derselben Eigenschaft einen neuen Wert zu und speichern erneut.

```csharp
// Change the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second image
string output60 = "DatabarBarHeight60Pixels.png";
barcodeGenerator.Save(output60, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 60 px height to {output60}");
```

> **Wichtige Erkenntnis:** Die Eigenschaft `BarHeight` ist veränderlich; Sie müssen die `BarcodeGenerator`‑Instanz nicht neu erstellen. Das ermöglicht das kostengünstige Erzeugen mehrerer Größen in einer Schleife oder im Batch‑Verfahren.

## Schritt 6: Ausgabe überprüfen

Führen Sie das Konsolenprogramm aus (`dotnet run`). Nach der Ausführung sollten Sie zwei PNG‑Dateien im Ausgabeverzeichnis des Projekts sehen:

- `DatabarBarHeight30Pixels.png` – kurze Balken (30 px)
- `DatabarBarHeight60Pixels.png` – hohe Balken (60 px)

Beide Bilder enthalten dieselben codierten Daten, aber die visuelle Höhe unterscheidet sich, was nützlich ist, wenn Barcodes in Formulare, Produktetiketten oder UI‑Komponenten mit unterschiedlichen Platzbeschränkungen integriert werden.

![Create barcode image with custom height](barcode-example.png){.align-center width="600" alt="Create barcode image with custom height"}

> **Tipp:** Öffnen Sie die PNG‑Dateien in einem beliebigen Bildbetrachter. Der höhere Barcode sollte genau doppelt so groß sein wie der kürzere, während der horizontale Abstand identisch bleibt.

## Schritt 7: Häufige Variationen und Randfälle

| Situation | Empfohlene Einstellung |
|-----------|------------------------|
| **Drucken auf einem hochauflösenden Etikettendrucker** | Verwenden Sie eine größere X‑Dimension (z. B. 4 px) und erhöhen Sie `BarHeight` proportional. |
| **Anzeige auf einem Low‑DPI‑Bildschirm** | Behalten Sie `XDimension` bei 1 px und `BarHeight` zwischen 20‑40 px für gute Lesbarkeit. |
| **Erzeugen von QR‑Codes oder 2‑D‑Barcodes** | Die Eigenschaft `BarHeight` wird ignoriert; verwenden Sie `EncodeTypes.QR` und passen stattdessen `ImageHeight` an. |
| **Batch‑Erzeugung vieler Höhen** | Iterieren Sie über ein Array von Höhen und rufen Sie `Save` innerhalb der Schleife auf; ein erneutes Erstellen des Generators pro Durchlauf ist nicht nötig. |

### Umgang mit ungültigen Höhen

Die Bibliothek wirft eine `ArgumentOutOfRangeException`, wenn Sie `BarHeight` auf einen nicht‑positiven Wert setzen. Schützen Sie sich mit einer einfachen Prüfung davor:

```csharp
int desiredHeight = 0; // example invalid value
if (desiredHeight <= 0)
{
    throw new ArgumentException("Bar height must be greater than zero.");
}
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = desiredHeight;
```

## Vollständiger Quellcode (zum Kopieren bereit)

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the barcode generator for GS1‑Databar Omni‑Directional
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set a common 2‑pixel X‑dimension
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = "DatabarBarHeight30Pixels.png";
            barcodeGenerator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 30 px height to {path30}");

            // 4️⃣ Second image – 60 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = "DatabarBarHeight60Pixels.png";
            barcodeGenerator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 60 px height to {path60}");
        }
    }
}
```

> **Warum das funktioniert:** Alle erforderlichen Einstellungen (`EncodeTypes`, `XDimension`, `BarHeight`) werden vor jedem `Save`‑Aufruf angewendet. Die gleiche `BarcodeGenerator`‑Instanz wird wiederverwendet, was sowohl speichereffizient als auch leicht lesbar ist.

## Fazit

Sie wissen jetzt, wie Sie **Barcode‑Bilder** in C# erstellen und die **Barcode‑Höhe** präzise mit der `BarcodeGenerator`‑API ändern können. Durch Anpassen von `BarHeight.Pixels` erreichen Sie eine **benutzerdefinierte Barcode‑Höhe**, ohne den Generator neu zu erstellen, was die Lösung ideal für die dynamische Etikettenerstellung, UI‑Renderings oder Batch‑Verarbeitungspipelines macht.

Als Nächstes können Sie verwandte Themen erkunden, wie **die Anpassung der Breite**, **Hinzufügen von menschenlesbarem Text** oder **Export nach SVG für skalierbare Web‑Nutzung**. Das gleiche Muster – eine Eigenschaft setzen, `Save` aufrufen – gilt für all diese Szenarien und ermöglicht es Ihnen, dieses Beispiel selbstbewusst zu erweitern.

## Was sollten Sie als Nächstes lernen?

Die folgenden Tutorials behandeln eng verwandte Themen, die auf den in dieser Anleitung gezeigten Techniken aufbauen. Jede Ressource enthält vollständige, funktionierende Codebeispiele mit Schritt‑für‑Schritt‑Erklärungen, um Ihnen zu helfen, weitere API‑Funktionen zu meistern und alternative Implementierungsansätze in Ihren eigenen Projekten zu erkunden.

- [Wie man die Barcode‑Höhe in C# ändert – Komplett‑Leitfaden](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Barcode‑Generator‑Beispiel – Planet‑ und RM4SCC‑Barcodes mit benutzerdefinierter Höhe erstellen](/barcode/english/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/)
- [Wie man einen RM4SCC‑Barcode erstellt und seine Höhe in C# steuert](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-control-its-height-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
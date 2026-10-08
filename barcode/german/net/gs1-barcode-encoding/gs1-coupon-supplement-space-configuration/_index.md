---
date: 2026-09-28
description: Erfahren Sie, wie Sie barcode custom space für GS1‑Coupons mit Aspose.BarCode
  für .NET erstellen und die Lesbarkeit von Barcodes erhöhen. Folgen Sie unserer Schritt‑für‑Schritt‑Anleitung.
keywords:
- create barcode custom space
- GS1 coupon supplement
- Aspose.BarCode .NET
- increase barcode readability
lastmod: 2026-09-28
linktitle: GS1 Coupon Supplement Space Konfiguration
og_description: Erfahren Sie, wie Sie barcode custom space für GS1‑Coupons mit Aspose.BarCode
  für .NET erstellen und die Lesbarkeit von Barcodes verbessern. Schritt‑für‑Schritt‑Code
  und Tipps sind enthalten.
og_image_alt: Screenshot of a GS1 coupon barcode generated with custom supplement
  space using Aspose.BarCode for .NET
og_title: Erstellen Sie barcode custom space für GS1 coupon supplement – Aspose.BarCode
  .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  headline: How to create barcode custom space for GS1 coupon supplement
  type: TechArticle
- description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  name: How to create barcode custom space for GS1 coupon supplement
  steps:
  - name: '**Visual Studio** – The primary IDE for .NET development.'
    text: '**Visual Studio** – The primary IDE for .NET development.'
  - name: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
  - name: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
    text: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
  - name: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
    text: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
  - name: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
    text: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
  - name: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
    text: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
  type: HowTo
- questions:
  - answer: It adds a mandatory blank margin around the supplemental data, improving
      scanner reliability and meeting retailer‑specified minimum widths.
    question: What is the purpose of the GS1 Coupon Supplement Space in barcodes?
  - answer: Yes, set `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` to any
      integer value; the library instantly applies the change to the generated image.
    question: Can I customize the width of the GS1 Coupon Supplement Space with Aspose.BarCode
      for .NET?
  - answer: Refer to the [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)
      and visit the [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)
      for community assistance.
    question: Where can I find additional documentation and support for Aspose.BarCode
      for .NET?
  - answer: Absolutely. The API offers straightforward methods for quick tasks and
      advanced options for fine‑tuned barcode generation.
    question: Is Aspose.BarCode for .NET suitable for both beginners and experienced
      developers?
  - answer: Yes, request a trial license from the [Aspose temporary license website](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for Aspose.BarCode for .NET to evaluate
      its features?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- barcode configuration
- GS1 standards
- Aspose.BarCode
- .NET barcode generation
title: Wie man barcode custom space für GS1 coupon supplement erstellt
url: /de/net/gs1-barcode-encoding/gs1-coupon-supplement-space-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GS1-Coupon-Zusatzraumkonfiguration

In diesem Tutorial **erstellen Sie einen benutzerdefinierten Barcode‑Raum** für den GS1‑Coupon‑Zusatzraum mit Aspose.BarCode für .NET. Das Anpassen des Zusatzraums ist entscheidend, wenn Sie die **Lesbarkeit von Barcodes** auf niedrigauflösenden Scannern erhöhen oder retailer‑vorgeschriebene Ränder einhalten müssen. Am Ende dieses Leitfadens verstehen Sie, warum der Zusatzraum wichtig ist, wie er programmgesteuert gesetzt wird und wie Sie Bilder mit unterschiedlichen Pixelwerten erzeugen.

## Schnelle Antworten
- **Was steuert der Zusatzraum?** Er definiert den leeren Bereich (in Pixeln) zwischen den Coupon‑Daten und dem Rest des Barcodes.  
- **Welcher Barcode‑Typ wird verwendet?** `EncodeTypes.UpcaGs1DatabarCoupon`.  
- **Kann ich die Größe des Raums ändern?** Ja – setzen Sie `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` auf einen beliebigen ganzzahligen Wert.  
- **Benötige ich eine Lizenz für diese Funktion?** Eine temporäre Lizenz reicht für die Evaluierung; für den Produktionseinsatz ist eine Voll‑Lizenz erforderlich.  
- **Welche Ausgabeformate werden unterstützt?** PNG, JPEG, BMP, GIF, TIFF und weitere über `BarCodeImageFormat`.

## Was ist der GS1-Coupon-Zusatzraum?
Der GS1‑Coupon‑Zusatzraum ist ein definierter leerer Bereich, der in GS1‑Databar‑Coupon‑Barcodes erscheint. Einzelhandelssysteme nutzen diesen Raum, um die Scan‑Zuverlässigkeit zu verbessern und branchenspezifische Vorgaben zu erfüllen, die einen Mindestabstand um die Zusatzdaten verlangen.

## Warum den Zusatzraum konfigurieren?
Der Zusatzraum erhöht **direkt die Lesbarkeit von Barcodes** und hilft Ihnen, strenge Retailer‑Richtlinien einzuhalten. Durch das Hinzufügen zusätzlicher Pixel reduzieren Sie die Wahrscheinlichkeit von Fehlablesungen auf niedrigauflösenden Scannern, gewährleisten ein konsistentes Scannen über verschiedene Etikettengrößen hinweg und erhalten visuelle Flexibilität, um den Barcode in einem gedruckten Layout auszubalancieren.

## Voraussetzungen

Bevor wir mit der Konfiguration des GS1‑Coupon‑Zusatzraums mit Aspose.BarCode für .NET beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Visual Studio** – Die primäre IDE für .NET‑Entwicklung.  
2. **Aspose.BarCode für .NET** – Laden Sie die Bibliothek aus der [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) herunter.  
3. **.NET Framework oder .NET 5+** – Kenntnisse in C# und der .NET‑Laufzeitumgebung sind erforderlich.

Jetzt, da die Umgebung bereit ist, gehen wir zur Implementierung über.

## Namespaces importieren

Der Namespace `Aspose.BarCode.Generation` enthält die Klasse `BarcodeGenerator` und zugehörige Einstellungen.

```csharp
using Aspose.BarCode;
```

## Schritt 1: Pfad definieren

Wählen Sie einen Ordner, in dem die erzeugten Bilder gespeichert werden sollen. Der Pfad muss mit dem für Ihr Betriebssystem passenden Verzeichnis‑Trennzeichen enden.

```csharp
string path = "Your Directory Path";
```

## Schritt 2: GS1-Coupon-Zusatzraumkonfiguration generieren

Das folgende Snippet erstellt einen Barcode, setzt die X‑Dimension und passt den Zusatzraum an.

```csharp
System.Console.WriteLine("Gs1CouponSupplementSpace:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.UpcaGs1DatabarCoupon, "123456789012(8110)ASPOSE");
gen.Parameters.Barcode.XDimension.Pixels = 2;

// Set coupon supplement space to 30 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 30;
gen.Save($"{path}Gs1CouponSpace30Pixels.png", BarCodeImageFormat.Png);

// Set coupon supplement space to 50 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 50;
gen.Save($"{path}Gs1CouponSpace50Pixels.png", BarCodeImageFormat.Png);
```

In diesem Beispiel:

1. **Erstellen** Sie eine `BarcodeGenerator`‑Instanz für den Typ `UpcaGs1DatabarCoupon`.  
2. **Setzen** Sie die X‑Dimension auf 2 Pixel, was die schmalste Balkenbreite bestimmt.  
3. **Passen** Sie die Eigenschaft `SupplementSpace.Pixels` auf 30 px an, erzeugen ein Bild und wiederholen den Vorgang mit 50 px.  

Experimentieren Sie gern mit anderen Pixelwerten, um Ihren Druck‑Workflow zu optimieren.

## Häufige Probleme & Tipps

- **Ungültiger Pfad** – Stellen Sie sicher, dass die Variable `path` mit einem abschließenden Backslash (`\`) oder Forward‑Slash (`/`) endet, der zu Ihrem Betriebssystem passt.  
- **Unzureichende Berechtigungen** – Führen Sie Visual Studio als Administrator aus oder wählen Sie einen Ordner, in dem die Anwendung Schreibrechte hat.  
- **Falsches Datenformat** – Der Daten‑String muss der GS1‑Syntax entsprechen (`(8110)` bezeichnet den Zusatz‑Identifier).

## Warum das für Ihr Unternehmen wichtig ist

Aspose.BarCode unterstützt **über 60 Barcode‑Symbologien** und kann Bilder bis zu **10.000 × 10.000 Pixel** rendern, ohne den Speicher zu überlasten. Für großflächige Einzelhandelseinsätze bedeutet das, dass Sie hochauflösende GS1‑Coupons im Batch‑Modus erzeugen können, wobei die Verarbeitungszeit pro Bild auf typischer Server‑Hardware unter einer Sekunde bleibt.

## Häufig gestellte Fragen

**F: Welchen Zweck hat der GS1‑Coupon‑Zusatzraum in Barcodes?**  
A: Er fügt einen obligatorischen leeren Rand um die Zusatzdaten hinzu, verbessert die Zuverlässigkeit des Scanners und erfüllt die von Retailern vorgegebenen Mindestbreiten.

**F: Kann ich die Breite des GS1‑Coupon‑Zusatzraums mit Aspose.BarCode für .NET anpassen?**  
A: Ja, setzen Sie `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` auf einen beliebigen ganzzahligen Wert; die Bibliothek wendet die Änderung sofort auf das erzeugte Bild an.

**F: Wo finde ich zusätzliche Dokumentation und Support für Aspose.BarCode für .NET?**  
A: Siehe die [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) und besuchen Sie das [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) für Community‑Unterstützung.

**F: Ist Aspose.BarCode für .NET sowohl für Einsteiger als auch für erfahrene Entwickler geeignet?**  
A: Absolut. Die API bietet unkomplizierte Methoden für schnelle Aufgaben und erweiterte Optionen für fein abgestimmte Barcode‑Generierung.

**F: Kann ich eine temporäre Lizenz für Aspose.BarCode für .NET erhalten, um die Funktionen zu evaluieren?**  
A: Ja, beantragen Sie eine Testlizenz über die [Aspose temporary license website](https://purchase.aspose.com/temporary-license/).

## Fazit

Durch die oben beschriebenen Schritte wissen Sie jetzt, wie Sie **einen benutzerdefinierten Barcode‑Raum** für den GS1‑Coupon‑Zusatzraum erstellen – eine Schlüsseltechnik, um die **Lesbarkeit von Barcodes** zu erhöhen und Einzelhandelsstandards zu erfüllen. Integrieren Sie den Code in Ihre bestehenden Scan‑Lösungen, testen Sie verschiedene Pixelwerte und entdecken Sie weitere Barcode‑Typen, die von Aspose.BarCode für .NET angeboten werden.

---

**Zuletzt aktualisiert:** 2026-09-28  
**Getestet mit:** Aspose.BarCode 24.12 für .NET  
**Autor:** Aspose

## Verwandte Tutorials

- [Generieren Sie Aspose.BarCode Databar-Barcode mit .NET API – Zeilen‑ & Spaltenkonfiguration](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)
- [Wie man DataMatrix‑Barcodes mit Aspose.BarCode für .NET erzeugt – Schritt‑für‑Schritt‑Anleitung](/barcode/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-05-30
description: Erfahren Sie, wie Sie mit Aspose.BarCode für .NET ein Barcode-PNG mit
  einem benutzerdefinierten DataMatrix-Seitenverhältnis erstellen. Schritt‑für‑Schritt‑Anleitung
  zur Barcode‑Erstellung und Größenanpassung.
keywords:
- create barcode png
- generate datamatrix barcode
- asp.net barcode generation
- barcode generation visual studio
linktitle: Anpassung des DataMatrix-Seitenverhältnisses
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  headline: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  name: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  steps:
  - name: Set Up Your Project
    text: Create a new console or Windows Forms project in Visual Studio and add a
      reference to the Aspose.BarCode DLL.
  - name: Initialize a Barcode Generator
    text: 'Instantiate it with the DataMatrix symbology and the data you want to encode:
      `BarcodeGenerator` creates a barcode image from the specified symbology and
      data. > This line creates a generator ready to produce a DataMatrix barcode
      that contains the sample text.'
  - name: Customize Aspect Ratio and Save PNG Files
    text: 'Now you can change the **aspect ratio** and save each version as a PNG
      image: `AspectRatio` sets the width‑to‑height proportion of the DataMatrix modules.
      `Save` writes the generated barcode image to a file in the chosen format. -
      The first call creates a square‑proportioned barcode (`AspectRatio = '
  type: HowTo
- questions:
  - answer: Yes, many 2‑D barcodes (e.g., QR, PDF417) support aspect‑ratio adjustments
      through their specific parameter objects.
    question: Can I customize the aspect ratio of other barcode types using Aspose.BarCode
      for .NET?
  - answer: Yes, you can access a free trial of Aspose.BarCode for .NET [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: You can purchase a license on the Aspose website [here](https://purchase.aspose.com/buy).
    question: Where can I purchase a license for Aspose.BarCode for .NET?
  - answer: Yes, it works with .NET Framework 4.x, .NET Core 3.1+, and the latest
      .NET releases.
    question: Is Aspose.BarCode for .NET compatible with different .NET Framework
      versions?
  - answer: Absolutely – PNG, JPEG, BMP, GIF, TIFF, SVG, and PDF are all supported
      out of the box.
    question: Can I generate barcodes in different formats with Aspose.BarCode for
      .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Barcode PNG erstellen – DataMatrix Seitenverhältnis – Aspose.BarCode
url: /de/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode PNG erstellen – DataMatrix Seitenverhältnis – Aspose.BarCode

Das Erzeugen einer **barcode PNG** mit einem benutzerdefinierten DataMatrix‑Seitenverhältnis ist ein häufiges Bedürfnis, wenn Sie **barcode PNG**‑Dateien benötigen, die in bestimmte Layout‑Beschränkungen passen. In diesem Tutorial führen wir Sie durch die genauen Schritte, um **barcode PNG**‑Dateien mit Aspose.BarCode für .NET zu **erstellen**, erklären, warum Sie das Seitenverhältnis anpassen möchten, und zeigen Ihnen, wie Sie die Ausgabe für Ihre Anwendung feinabstimmen.

## Schnelle Antworten
- **Was steuert das „Seitenverhältnis“?** Es definiert das Breite‑zu‑Höhe‑Verhältnis der DataMatrix‑Module.  
- **Kann ich PNG, JPEG oder SVG ausgeben?** Ja – die `Save`‑Methode unterstützt PNG, JPEG, BMP, GIF, TIFF, SVG und PDF.  
- **Benötige ich eine Lizenz für diese Funktion?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine Voll‑Lizenz erforderlich.  
- **Welche .NET‑Versionen werden unterstützt?** .NET Framework 4.x, .NET Core 3.1+, .NET 5/6/7.  
- **Wie viele Seitenverhältnis‑Werte sind gültig?** Jeder positive Float; typische Werte liegen zwischen 0,5 – 2,0.

## Was ist ein DataMatrix‑Barcode und warum das Seitenverhältnis anpassen?
Ein DataMatrix‑Barcode ist ein zweidimensionaler Matrixcode, der große Datenmengen in einem kompakten Quadrat speichert. Das Anpassen des **Seitenverhältnisses** ermöglicht es, die Module horizontal zu strecken oder zu komprimieren, was nützlich ist, wenn Sie den Barcode in schmale Spalten oder breite Etiketten einpassen müssen, ohne die Scan‑Zuverlässigkeit zu beeinträchtigen.

## Warum Aspose.BarCode zum Erstellen von barcode PNG verwenden?
Aspose.BarCode unterstützt **7 Bildformate** — PNG, JPEG, BMP, GIF, TIFF, SVG und PDF — und kann **mehr als 50 Eingabe‑ und Ausgabeformate** im Speicher verarbeiten, wobei mehrseitige Dokumente verarbeitet werden, ohne die gesamte Datei zu laden. Die Bibliothek bietet eine fluente API, mit der Sie einen DataMatrix‑Barcode in einer einzigen Codezeile erzeugen können, was pixelgenaues Rendering und volle .NET‑Kompatibilität garantiert.

## Voraussetzungen

Bevor wir beginnen, DataMatrix‑Seitenverhältnisse anzupassen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben:

1. **Visual Studio** – jede aktuelle Version ist ausreichend.  
2. **Aspose.BarCode für .NET** – laden Sie es [hier](https://releases.aspose.com/barcode/net/) herunter.  
3. Sie können auch andere Aspose‑Produktveröffentlichungen [hier](https://releases.aspose.com/) erkunden.  
4. **.NET Framework / .NET Core** – Ihr Projekt muss eine unterstützte Version anvisieren.

## Namespaces importieren

Zuerst müssen Sie den erforderlichen Namespace in Ihrem C#‑Projekt importieren:

`using Aspose.BarCode.Generation;` importiert den Namespace, der die Barcode‑Generierungsklassen enthält.  

```csharp
using Aspose.BarCode.Generation;
```

> **Pro Tipp:** Lassen Sie diese `using`‑Anweisung am Anfang Ihrer Datei, damit die `BarcodeGenerator`‑Klasse stets verfügbar ist.

## Wie erstellt man barcode PNG mit benutzerdefiniertem Seitenverhältnis?

Laden Sie den `BarcodeGenerator`, setzen Sie den DataMatrix‑Typ, passen Sie die Eigenschaft `AspectRatio` an und rufen Sie `Save` auf. Dieses Ein‑Zeilen‑Muster erzeugt ein barcode PNG, das das von Ihnen angegebene Verhältnis einhält, und die Bibliothek kümmert sich automatisch um die Skalierung der Module und die Ruhebereiche.

`BarcodeGenerator` erstellt ein Barcode‑Bild aus der angegebenen Symbolik und den Daten.

### Schritt 1: Projekt einrichten
Erstellen Sie ein neues Konsolen‑ oder Windows‑Forms‑Projekt in Visual Studio und fügen Sie einen Verweis auf die Aspose.BarCode‑DLL hinzu.

### Schritt 2: Barcode‑Generator initialisieren
Instanziieren Sie ihn mit der DataMatrix‑Symbolik und den Daten, die Sie codieren möchten:

`BarcodeGenerator` erstellt ein Barcode‑Bild aus der angegebenen Symbolik und den Daten.  

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> Diese Zeile erstellt einen Generator, der bereit ist, einen DataMatrix‑Barcode zu erzeugen, der den Beispieltext enthält.

### Schritt 3: Seitenverhältnis anpassen und PNG‑Dateien speichern
Jetzt können Sie das **Seitenverhältnis** ändern und jede Version als PNG‑Bild speichern:

`AspectRatio` legt das Breite‑zu‑Höhe‑Verhältnis der DataMatrix‑Module fest.  
`Save` schreibt das erzeugte Barcode‑Bild in eine Datei im gewählten Format.  

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- Der erste Aufruf erzeugt einen quadratisch proportionierten Barcode (`AspectRatio = 1`).  
- Der zweite Aufruf komprimiert den Barcode horizontal (`AspectRatio = 0.5`), was ein breiteres Erscheinungsbild erzeugt.

Sie haben jetzt zwei **barcode PNG**‑Dateien mit unterschiedlichen Seitenverhältnissen, die Sie in Berichten, Etiketten oder UI‑Elementen verwenden können.

## Häufige Probleme & Lösungen
| Problem | Lösung |
|---------|--------|
| **Generiertes Bild ist unscharf** | Erhöhen Sie den Parameter `Resolution` vor dem Speichern (`gen.Parameters.ImageResolution = 300`). |
| **Barcode wird nicht gelesen** | Stellen Sie sicher, dass das Seitenverhältnis zwischen 0,5 – 2,0 bleibt und halten Sie einen ausreichenden Ruhebereich (`gen.Parameters.Barcode.CodeTextParameters.Margin`). |
| **Dateipfad‑Fehler** | Verwenden Sie `Path.Combine`, um den Ausgabepfad zu erstellen, und prüfen Sie, ob der Ordner existiert. |

## Häufig gestellte Fragen

**F: Kann ich das Seitenverhältnis anderer Barcode‑Typen mit Aspose.BarCode für .NET anpassen?**  
A: Ja, viele 2‑D‑Barcodes (z. B. QR, PDF417) unterstützen die Anpassung des Seitenverhältnisses über ihre jeweiligen Parameterobjekte.

**F: Gibt es eine kostenlose Testversion von Aspose.BarCode für .NET?**  
A: Ja, Sie können eine kostenlose Testversion von Aspose.BarCode für .NET [hier](https://releases.aspose.com/) erhalten.

**F: Wo kann ich eine Lizenz für Aspose.BarCode für .NET erwerben?**  
A: Sie können eine Lizenz auf der Aspose‑Website [hier](https://purchase.aspose.com/buy) erwerben.

**F: Ist Aspose.BarCode für .NET mit verschiedenen .NET‑Framework‑Versionen kompatibel?**  
A: Ja, es funktioniert mit .NET Framework 4.x, .NET Core 3.1+ und den neuesten .NET‑Versionen.

**F: Kann ich mit Aspose.BarCode für .NET Barcodes in verschiedenen Formaten erzeugen?**  
A: Natürlich – PNG, JPEG, BMP, GIF, TIFF, SVG und PDF werden alle sofort unterstützt.

## Fazit

Das Anpassen des **Seitenverhältnisses** eines DataMatrix‑Barcodes und das **Erstellen von barcode PNG**‑Dateien ist mit Aspose.BarCode für .NET unkompliziert. Wenn Sie den obigen Schritten folgen, können Sie perfekt dimensionierte Barcodes erzeugen, die exakt den Layout‑Anforderungen Ihres Projekts entsprechen. Erkunden Sie zusätzliche Parameter wie `Resolution`, `Margin` und `Color`, um die Ausgabe weiter anzupassen, und berücksichtigen Sie die Möglichkeiten zur `generate datamatrix barcode`, wenn Sie scan‑freundliche Anwendungen in Visual Studio entwickeln.

Für weiterführende Informationen sehen Sie sich die offizielle [Dokumentation](https://reference.aspose.com/barcode/net/) an oder treten Sie der Community im [Aspose.BarCode‑Forum](https://forum.aspose.com/c/barcode/13) bei.

---

**Zuletzt aktualisiert:** 2026-05-30  
**Getestet mit:** Aspose.BarCode 24.12 für .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [DataMatrix‑Barcode generieren – Pro‑Leitfaden mit Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/)
- [Wie man DataMatrix‑Barcodes (ECC 200) mit Aspose.BarCode für .NET erzeugt](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [DataMatrix‑Kodierung in ASCII mit Aspose.BarCode für .NET meistern](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
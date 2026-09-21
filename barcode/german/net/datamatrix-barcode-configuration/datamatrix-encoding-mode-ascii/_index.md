---
date: 2026-06-09
description: Erfahren Sie, wie Sie mit Aspose.BarCode für .NET einen DataMatrix-Barcode
  im ASCII-Modus erstellen. Dieser Leitfaden zeigt, wie Sie schnell einen Barcode
  in C# generieren.
keywords:
- create datamatrix barcode
- generate barcode c#
- how to encode barcode
- barcode generator example
linktitle: DataMatrix-Kodierungsmodus (ASCII)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  headline: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  name: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  steps:
  - name: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
    text: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
  - name: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
  - name: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
    text: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
  - name: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
    text: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
  type: HowTo
- questions:
  - answer: Yes, a valid Aspose license is required for production use; a free trial
      is available for evaluation.
    question: Can I use this in a commercial application?
  - answer: Absolutely – Aspose.BarCode fully supports .NET Core 3.1+, .NET 5, .NET
      6, and later versions.
    question: Does the library work with .NET Core?
  - answer: Up to 2,335 alphanumeric characters fit in a single DataMatrix symbol
      when using ASCII encoding.
    question: How many characters can I encode in ASCII mode?
  - answer: Yes, adjust `generator.Parameters.Image.ForeColor` and `BackColor` to
      any `System.Drawing.Color` value.
    question: Can I change the barcode’s foreground or background color?
  - answer: The official documentation contains dozens of samples covering custom
      sizes, colors, and error‑correction levels.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: DataMatrix-Barcode im ASCII-Modus mit Aspose.BarCode für .NET erstellen
url: /de/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# DataMatrix-Barcode im ASCII-Modus mit Aspose.BarCode für .NET erstellen

## Einleitung

Bereit, **DataMatrix-Barcode**-Bilder zu erstellen, die die effiziente ASCII‑Kodierung verwenden? In diesem Tutorial lernen Sie, wie Sie einen DataMatrix-Barcode im ASCII‑Modus mit Aspose.BarCode für .NET erzeugen. Wir führen Sie durch jeden Schritt – von der Einrichtung des Projekts bis zum Speichern des endgültigen Bildes – damit Sie die Barcode‑Generierung in Ihren C#‑Anwendungen in wenigen Minuten hinzufügen können.

## Schnelle Antworten
- **Welche Bibliothek ist am besten für DataMatrix in .NET?** Aspose.BarCode for .NET  
- **Wie viele Codezeilen werden benötigt?** About 5‑7 lines for a basic ASCII barcode  
- **Benötige ich eine Lizenz?** A free trial works for development; a license is required for production  
- **Unterstützte Plattformen?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **Kann ich Größe oder Farben ändern?** Yes, Aspose.BarCode exposes properties for dimensions and foreground/background colors  

## Was ist ein DataMatrix-Barcode?
DataMatrix ist ein zweidimensionaler Barcode, der Text und Binärdaten in einem kompakten quadratischen Muster speichert.  
Ein DataMatrix-Barcode kodiert Informationen in einem Raster aus schwarzen und weißen Modulen und ermöglicht bis zu 2 335 alphanumerische Zeichen in einem einzigen Symbol. Er wird in der Fertigung, Logistik und im Gesundheitswesen häufig eingesetzt, weil er bei sehr kleinen Größen gedruckt werden kann und dennoch hervorragend lesbar bleibt.

## Wie erstellt man einen DataMatrix-Barcode im ASCII-Modus?
Laden Sie den Aspose.BarCode‑Namespace, instanziieren Sie einen `BarcodeGenerator`, setzen Sie den `EncodeMode` auf **EncodeMode.ASCII**, weisen Sie Ihre Datenzeichenfolge zu und rufen Sie `Save` auf, um die Bilddatei zu schreiben. Dieser Ansatz erzeugt einen vollständig konformen DataMatrix-Barcode mit reiner ASCII‑Kodierung in nur wenigen Zeilen C#‑Code.

## Warum ASCII-Kodierung für DataMatrix verwenden?
Der ASCII‑Modus ist die Standard‑ und effizienteste Kodierung für Klartextdaten und liefert die kleinste mögliche Symbolgröße für alphanumerische Zeichenketten. Er unterstützt alle 128 ASCII‑Zeichen, verarbeitet Daten schneller als erweiterte Modi und garantiert maximale Kompatibilität mit älteren Scannern, die standardmäßige ASCII‑Symbole erwarten.

## Voraussetzungen

1. **Entwicklungsumgebung** – Visual Studio, Rider oder jede C#‑kompatible IDE.  
2. **Aspose.BarCode für .NET** – Laden Sie das neueste Paket von [hier](https://releases.aspose.com/barcode/net/) herunter.  
   - Dokumentation: [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)  
   - Community‑Hilfe: [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)  
3. **Grundlegende C#‑Kenntnisse** – Vertrautheit mit der .NET‑Projektstruktur hilft Ihnen, die Schritte schnell zu verfolgen.  
4. **Weitere Aspose‑Produkte** finden Sie [hier](https://releases.aspose.com/).

## Namespaces importieren

Um zu beginnen, fügen Sie die erforderlichen `using`‑Direktiven am Anfang Ihrer C#‑Datei hinzu:

```csharp
using Aspose.BarCode.Generation;
using System.Drawing;
```

Diese Namespaces geben Ihnen Zugriff auf die Klasse `BarcodeGenerator` und die bildbezogenen Typen, die zum Speichern des Outputs benötigt werden.

## Schritt 1: Verzeichnis erstellen

Wählen Sie einen Ordner, in dem die erzeugten Barcode‑Bilder gespeichert werden sollen. Ersetzen Sie `"Your Directory Path"` durch einen absoluten oder relativen Pfad, der auf Ihrem Rechner existiert.

```csharp
string outputDir = @"C:\Barcodes";
if (!System.IO.Directory.Exists(outputDir))
{
    System.IO.Directory.CreateDirectory(outputDir);
}
```

Der Code stellt sicher, dass das Verzeichnis existiert, bevor versucht wird, Dateien zu schreiben, und verhindert so Laufzeitfehler.

## Schritt 2: Daten im ASCII-Modus kodieren

Die Klasse `BarcodeGenerator` erstellt und konfiguriert Barcode‑Bilder. Die Aufzählung `DataMatrixEncodeMode` wählt den Kodierungsalgorithmus für DataMatrix‑Symbole aus.

```csharp
// Initialise the generator with the data you want to encode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "1234567890");

// Set the encoding mode to ASCII for optimal size
generator.Parameters.Barcode.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;

// Optional: adjust image dimensions or colors here
generator.Parameters.Image.Width = 200;
generator.Parameters.Image.Height = 200;

// Save the barcode as a PNG file
string filePath = System.IO.Path.Combine(outputDir, "datamatrix_ascii.png");
generator.Save(filePath, BarCodeImageFormat.Png);
```

Nach dem Ausführen des Codes finden Sie `datamatrix_ascii.png` in dem von Ihnen angegebenen Ordner. Das Bild enthält einen DataMatrix‑Barcode, der die Zeichenfolge `"1234567890"` im kompakten ASCII‑Modus kodiert.

## Häufige Probleme und Lösungen

- **Dateizugriffsfehler** – Stellen Sie sicher, dass die Anwendung Schreibrechte für den Zielordner hat. Das Ausführen von Visual Studio als Administrator kann Berechtigungsprobleme unter Windows beheben.  
- **Falsche Symbolgröße** – Wenn der Barcode zu groß oder zu klein erscheint, passen Sie `generator.Parameters.Image.Width` und `Height` an oder lassen Sie Aspose die optimale Größe automatisch berechnen, indem Sie diese Eigenschaften weglassen.  
- **Nicht unterstützte Zeichen** – Der ASCII‑Modus akzeptiert nur Zeichen im Bereich 0‑127. Für Unicode‑Daten wechseln Sie zu `DataMatrixEncodeMode.Base256` oder einem anderen geeigneten Modus.

## Häufig gestellte Fragen

**Q: Kann ich das in einer kommerziellen Anwendung verwenden?**  
A: Ja, für den Produktionseinsatz ist eine gültige Aspose‑Lizenz erforderlich; eine kostenlose Testversion steht für die Evaluierung zur Verfügung.

**Q: Funktioniert die Bibliothek mit .NET Core?**  
A: Absolut – Aspose.BarCode unterstützt .NET Core 3.1+, .NET 5, .NET 6 und neuere Versionen vollständig.

**Q: Wie viele Zeichen kann ich im ASCII‑Modus kodieren?**  
A: Bis zu 2 335 alphanumerische Zeichen passen in ein einzelnes DataMatrix‑Symbol, wenn ASCII‑Kodierung verwendet wird.

**Q: Kann ich die Vorder‑ oder Hintergrundfarbe des Barcodes ändern?**  
A: Ja, passen Sie `generator.Parameters.Image.ForeColor` und `BackColor` an einen beliebigen `System.Drawing.Color`‑Wert an.

**Q: Wo finde ich weiterführende Beispiele?**  
A: Die offizielle Dokumentation enthält Dutzende von Beispielen zu benutzerdefinierten Größen, Farben und Fehlerkorrektur‑Leveln.

## FAQ

### Q1: Kann ich Aspose.BarCode für .NET mit anderen Programmiersprachen außer C# verwenden?

A1: Aspose.BarCode unterstützt mehrere Programmiersprachen, aber dieses Tutorial konzentriert sich auf C#.

### Q2: Welche verschiedenen Kodierungsmodi stehen für DataMatrix‑Barcodes zur Verfügung?

A2: DataMatrix‑Barcodes unterstützen verschiedene Kodierungsmodi, darunter ASCII, C40, Text und Base256. Jeder Modus ist für unterschiedliche Datentypen geeignet.

### Q3: Kann ich das Aussehen des erzeugten Barcodes anpassen, z. B. Größe und Farbe?

A3: Ja, Aspose.BarCode bietet eine breite Palette von Parametern zur Anpassung des Barcode‑Aussehens, einschließlich Größe, Farbe und mehr.

### Q4: Gibt es eine kostenlose Testversion von Aspose.BarCode für .NET?

A4: Ja, Sie können Aspose.BarCode für .NET mit einer kostenlosen Testversion von [hier](https://releases.aspose.com/) erkunden.

### Q5: Wo kann ich eine Lizenz für Aspose.BarCode für .NET erwerben?

A5: Sie können eine Lizenz über die Aspose‑Website [hier](https://purchase.aspose.com/buy) erwerben.

---

**Zuletzt aktualisiert:** 2026-06-09  
**Getestet mit:** Aspose.BarCode 24.11 für .NET  
**Autor:** Aspose

## Verwandte Tutorials

- [DataMatrix-Kodierung in Bytes mit Aspose.BarCode für .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [DataMatrix-Barcode in C# lesen – DataMatrix-Modus (Auto) generieren](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Wie man DataMatrix-Barcodes (ECC 200) mit Aspose.BarCode für .NET generiert](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.BarCode.Generation;
```

```csharp
string path = "Your Directory Path";
```

```csharp
System.Console.WriteLine("DataMatrixEncodeModeASCII:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    // Set the X-dimension (size) of the barcode in pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set the encoding mode to ASCII
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;
    
    // Save the barcode as a PNG image
    gen.Save($"{path}DataMatrixEncodeModeASCII.png", BarCodeImageFormat.Png);
}
```

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
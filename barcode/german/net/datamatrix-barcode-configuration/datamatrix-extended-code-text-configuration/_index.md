---
date: 2026-09-23
description: Erfahren Sie, wie Sie Aspose.BarCode einsetzen, um in .NET einen DataMatrix‑Barcode
  mit erweitertem Code‑Text zu erzeugen, ideal für Inventar‑ und Logistikanwendungen.
keywords:
- how to use aspose
- create barcode for inventory
- barcode generation .net core
- generate barcode image c#
lastmod: 2026-09-23
linktitle: DataMatrix‑Erweiterte Code‑Text‑Konfiguration
og_description: So verwenden Sie Aspose.BarCode, um in .NET einen DataMatrix‑Barcode
  mit erweitertem Code‑Text zu erzeugen. Folgen Sie einer schnellen Schritt‑für‑Schritt‑Anleitung
  für Inventar‑ und Logistiklösungen.
og_image_alt: Screenshot of a DataMatrix barcode generated with Aspose.BarCode in
  a .NET console app
og_title: So verwenden Sie Aspose.BarCode, um DataMatrix‑Code‑Text in .NET zu erstellen
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  headline: How to use Aspose.BarCode to create DataMatrix code text in .NET
  type: TechArticle
- description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  name: How to use Aspose.BarCode to create DataMatrix code text in .NET
  steps:
  - name: Define the output folder
    text: Specify where the generated barcode image will be saved. Replace the placeholder
      with a valid path on your machine.
  - name: Build the extended code text
    text: '`DataMatrixExtCodetextBuilder` is a helper class that assembles the extended
      code text according to the DataMatrix specification. It automatically inserts
      the required ECI (Extended Channel Interpretation) markers. This mix demonstrates
      how you can combine Unicode characters, C40 encoding, plain tex'
  - name: Generate the final codetext string
    text: After configuring all parts, retrieve the combined string that Aspose.BarCode
      will embed into the barcode.
  - name: Create the DataMatrix barcode
    text: '`BarcodeGenerator` is the core class that produces barcode images. Instantiate
      it with `EncodeTypes.DataMatrix` and the extended codetext, then set visual
      parameters such as X‑dimension, image format, and optional human‑readable text.
      The above code **creates barcode aspose .net** with the desired e'
  - name: Verify the barcode by reading it back
    text: '`BarCodeReader` validates that the generated symbol can be decoded correctly,
      which is essential for automated test pipelines and quality assurance. If everything
      is set up properly, the console will output the exact extended code text you
      built earlier.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET
    question: What library is needed?
  - answer: DataMatrix with extended code text
    question: Which barcode type?
  - answer: Yes, the API is cross‑platform
    question: Can I use .NET Core / .NET 6?
  - answer: A free trial works for development; a license is required for production
    question: Do I need a license for testing?
  - answer: About 10‑15 minutes for a basic example
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- Aspose.BarCode
- DataMatrix
- .NET barcode
- C# barcode generation
- inventory labeling
title: So verwenden Sie Aspose.BarCode, um DataMatrix‑Code‑Text in .NET zu erstellen
url: /de/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man Aspose.BarCode verwendet, um DataMatrix‑Code‑Text in .NET zu erstellen

Die Integration von Barcodes in moderne .NET‑Anwendungen ist kein Nischen‑Task mehr – sie ist eine Kernanforderung für Inventar, Logistik und mobile Scan‑Lösungen. In diesem Leitfaden **lernen Sie, wie Sie Aspose.BarCode** verwenden, um einen DataMatrix‑Barcode mit erweitertem Code‑Text zu konfigurieren, das Bild zu erzeugen und programmgesteuert zu verifizieren. Sie sehen, warum dieser Ansatz ideal für die Erstellung von Barcodes für Inventar ist und wie er in .NET Core‑ oder .NET 6‑Projekte passt.

## Schnelle Antworten
- **Welche Bibliothek wird benötigt?** Aspose.BarCode für .NET  
- **Welcher Barcode‑Typ?** DataMatrix mit erweitertem Code‑Text  
- **Kann ich .NET Core / .NET 6 verwenden?** Ja, die API ist plattformübergreifend  
- **Benötige ich eine Lizenz für Tests?** Eine kostenlose Testversion funktioniert für die Entwicklung; für die Produktion ist eine Lizenz erforderlich  
- **Wie lange dauert die Implementierung?** Etwa 10‑15 Minuten für ein einfaches Beispiel  

## Was ist Aspose.BarCode für .NET?
Aspose.BarCode für .NET ist eine kommerzielle Bibliothek, die Entwicklern ermöglicht, mehr als 30 Barcode‑Symbologien zu erzeugen und zu erkennen, darunter DataMatrix, QR und Code 128, und Bilder bis zu 10.000 × 10.000 Pixel ohne externe Abhängigkeiten zu produzieren. Sie unterstützt .NET Framework 4.5+, .NET Core 3.1+ und .NET 5/6/7.

## Warum DataMatrix‑erweiterter Code‑Text verwenden?
DataMatrix‑erweiterter Code‑Text lässt Sie mehrere Kodierungsschemata – UTF‑8, C40, Text, X12 – in einem einzigen Symbol einbetten und ermöglicht bis zu **3116 Codewords** (etwa 155 KB Daten) in einem kompakten Quadrat. Diese Fähigkeit ist perfekt für mehrsprachige Produktkennzeichnung, medizinische Geräteverfolgung und intelligente Verpackungen, bei denen alphanumerische IDs mit binären Nutzdaten kombiniert werden müssen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes haben:

1. **Aspose.BarCode für .NET** – laden Sie es von der offiziellen Seite **[Aspose.BarCode .NET download page](https://releases.aspose.com/barcode/net/)** herunter.  
2. **Eine .NET‑Entwicklungsumgebung** – Visual Studio, Rider oder VS Code mit dem .NET‑SDK.  
3. **Grundkenntnisse in C#** – Sie sollten mit Klassen, Namespaces und der `using`‑Anweisung vertraut sein.

## Namespaces importieren

Fügen Sie die erforderlichen Namespaces am Anfang Ihrer C#‑Datei hinzu, damit der Compiler weiß, wo er die Barcode‑Klassen finden kann.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

Diese Namespaces geben Ihnen Zugriff sowohl auf die Barcode‑Erzeugungs‑ als auch auf die Erkennungsfunktionen.

## Wie konfiguriere ich DataMatrix‑erweiterten Code‑Text?

Laden Sie den Builder, fügen Sie die gewünschten Segmente hinzu und lassen Sie Aspose.BarCode die ECI‑Marker automatisch setzen. Dieser direkte Antwortabsatz gibt Ihnen die genauen Schritte: Erstellen Sie einen `DataMatrixExtCodetextBuilder`, fügen Sie Unicode-, C40‑, Klartext‑ und Text‑Modus‑Segmente hinzu und holen Sie dann die kombinierte Zeichenkette für den Generator.

### Schritt 1: Ausgabeverzeichnis festlegen

Geben Sie an, wo das erzeugte Barcode‑Bild gespeichert werden soll. Ersetzen Sie den Platzhalter durch einen gültigen Pfad auf Ihrem Rechner.

```csharp
string path = "Your Directory Path";
```

### Schritt 2: Erweiterten Code‑Text erstellen

`DataMatrixExtCodetextBuilder` ist eine Hilfsklasse, die den erweiterten Code‑Text gemäß der DataMatrix‑Spezifikation zusammenstellt. Sie fügt automatisch die erforderlichen ECI (Extended Channel Interpretation)‑Marker ein.

```csharp
DataMatrixExtCodetextBuilder codetextBuilder = new DataMatrixExtCodetextBuilder();
codetextBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
codetextBuilder.AddECICodetextWithEncodeMode(ECIEncodings.UTF8, DataMatrixEncodeMode.C40, "ABCDE");
codetextBuilder.AddPlainCodetext("test");
codetextBuilder.AddCodetextWithEncodeMode(DataMatrixEncodeMode.Text, "abcde");
```

Dieses Beispiel zeigt, wie Sie Unicode‑Zeichen, C40‑Kodierung, Klartext und Text‑Modus in einem einzigen DataMatrix‑Symbol kombinieren können.

### Schritt 3: Endgültige Codetext‑Zeichenkette erzeugen

Nachdem Sie alle Teile konfiguriert haben, holen Sie die kombinierte Zeichenkette, die Aspose.BarCode in den Barcode einbetten wird.

```csharp
string codetext = codetextBuilder.GetExtendedCodetext();
```

### Schritt 4: DataMatrix‑Barcode erstellen

`BarcodeGenerator` ist die Kernklasse, die Barcode‑Bilder erzeugt. Instanziieren Sie sie mit `EncodeTypes.DataMatrix` und dem erweiterten Codetext, dann setzen Sie visuelle Parameter wie X‑Dimension, Bildformat und optionalen lesbaren Text.

```csharp
using (var generator = new BarcodeGenerator(EncodeTypes.DataMatrix, codetext))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended Codetext";
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ExtendedCodetext;

    generator.Save($"{path}DataMatrixExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Der obige Code **erstellt barcode aspose .net** mit dem gewünschten erweiterten Code‑Text und speichert ihn als PNG‑Datei.

### Schritt 5: Barcode durch Auslesen verifizieren

`BarCodeReader` prüft, ob das erzeugte Symbol korrekt dekodiert werden kann, was für automatisierte Test‑Pipelines und Qualitätssicherung essenziell ist.

```csharp
using (var reader = new BarCodeReader(generator.GenerateBarCodeImage(), DecodeType.DataMatrix))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
        Console.WriteLine("DataMatrixExtendedCodetext:" + result.CodeText);
}
```

Wenn alles korrekt eingerichtet ist, gibt die Konsole den exakt von Ihnen erstellten erweiterten Code‑Text aus.

## Häufige Fallstricke und Fehlersuche

| Problem | Grund | Lösung |
|---------|-------|--------|
| Barcode nicht lesbar | X‑Dimension zu niedrig | Erhöhen Sie `XDimension.Pixels` (z. B. 4 → 6) |
| Verzerrte Zeichen | Falsche ECI‑Kodierung | Stellen Sie sicher, dass `ECIEncodings.UTF8` dem Zeichensatz entspricht |
| Datei nicht gespeichert | Ungültiger Pfad | Verwenden Sie einen absoluten Pfad oder stellen Sie sicher, dass das Verzeichnis existiert |
| Lizenzausnahme | Testversion abgelaufen | Wenden Sie eine temporäre oder vollständige Lizenz an (siehe FAQ) |

## Häufig gestellte Fragen

### Q1: Was ist Aspose.BarCode für .NET?
A1: Aspose.BarCode für .NET ist eine leistungsstarke Bibliothek, die Entwicklern ermöglicht, eine breite Palette von Barcode‑Symbologien zu erzeugen und zu erkennen, darunter DataMatrix, QR, Code128 und mehr.

### Q2: Wo finde ich die Dokumentation für Aspose.BarCode für .NET?
A2: Sie können die vollständige API‑Referenz **[Aspose.BarCode .NET API reference](https://reference.aspose.com/barcode/net/)** aufrufen.

### Q3: Gibt es eine kostenlose Testversion für Aspose.BarCode für .NET?
A3: Ja, eine kostenlose Testversion kann von **[Aspose.BarCode free trial download](https://releases.aspose.com/)** heruntergeladen werden.

### Q4: Wie erhalte ich eine temporäre Lizenz für Tests?
A4: Temporäre Lizenzen werden für Evaluierungszwecke bereitgestellt und können über die **[Aspose temporary license request page](https://purchase.aspose.com/temporary-license/)** angefordert werden.

### Q5: Wo kann ich Support erhalten oder Fragen zu Aspose.BarCode für .NET stellen?
A5: Das offizielle Aspose.BarCode‑Forum ist die beste Anlaufstelle: **[Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)**.

---

**Zuletzt aktualisiert:** 2026-09-23  
**Getestet mit:** Aspose.BarCode 24.11 für .NET  
**Autor:** Aspose

## Verwandte Tutorials

- [Wie man DataMatrix‑Barcodes mit Aspose.BarCode für .NET generiert – Schritt‑für‑Schritt‑Anleitung](/barcode/net/datamatrix-barcode-configuration/)
- [DataMatrix‑Barcode im ASCII‑Modus mit Aspose.BarCode für .NET (C#) erzeugen](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Aztec‑Barcode mit Textkodierung mit Aspose.BarCode für .NET erzeugen](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
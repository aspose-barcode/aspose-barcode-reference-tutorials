---
date: 2026-09-28
description: Erfahren Sie, wie Sie 2D-Matrix-Barcode mit Aspose.BarCode für .NET erstellen
  – eine Schritt‑für‑Schritt‑Anleitung zum Generieren von DotCode‑Barcodes mit erweitertem
  Code‑Text.
keywords:
- create 2d matrix barcode
- how to generate dotcode
- dotcode extended codetext
lastmod: 2026-09-28
linktitle: DotCode Konfiguration für erweiterten Code‑Text
og_description: Erfahren Sie, wie Sie 2D-Matrix-Barcode mit Aspose.BarCode für .NET
  erstellen. Diese Anleitung zeigt Schritt‑für‑Schritt, wie DotCode‑Barcodes mit erweitertem
  Code‑Text generiert werden.
og_image_alt: Guide showing how to create a 2d matrix DotCode barcode with extended
  codetext in .NET
og_title: 2D-Matrix-Barcode mit Aspose.BarCode für .NET erstellen
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create 2d matrix barcode with Aspose.BarCode for .NET
    – a step‑by‑step guide for generating DotCode barcodes with extended code text.
  headline: How to create 2d matrix barcode via Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. The PNG image produced by the generator can be embedded in iOS, Android,
      or any cross‑platform mobile application.
    question: Can I use the generated barcode in a mobile app?
  - answer: Use the `AddECICodetext` method with the appropriate `ECIEncodings` (e.g.,
      `ECIEncodings.Base64`) to embed binary payloads.
    question: What if I need to encode binary data instead of text?
  - answer: Adjust the `XDimension.Pixels` property; higher values increase module
      size, while lower values make the barcode more compact.
    question: How do I change the barcode size without affecting readability?
  - answer: Yes. Set `gen.Parameters.Barcode.Margin` to define the desired quiet zone
      in pixels.
    question: Is there a way to add a quiet zone around the barcode?
  - answer: The latest Aspose.BarCode releases are compatible with .NET 8; just reference
      the appropriate NuGet package version.
    question: Does the library support .NET 8?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- dotcode
- Aspose.BarCode
- .NET barcode generation
- 2d matrix barcode
title: So erstellen Sie 2D-Matrix-Barcode mit Aspose.BarCode für .NET
url: /de/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man 2D-Matrix-Barcode mit Aspose.BarCode für .NET erstellt

## Einleitung

Im Bereich der Barcode-Generierung und -Verwaltung hebt sich Aspose.BarCode für .NET als vielseitige Lösung hervor, die **mehr als 50 Eingabe‑ und Ausgabeformate** unterstützt und mehrseitige Dokumente verarbeiten kann, ohne die gesamte Datei in den Speicher zu laden. Egal, ob Sie Barcodes für die Produktverfolgung, Bestandskontrolle oder datenintensive Anwendungen benötigen, das Erstellen eines **2D-Matrix-Barcodes** wie DotCode mit erweitertem Codetext ermöglicht das Einbetten sowohl von Text‑ als auch von Binärdaten in einem kompakten quadratischen Symbol. Dieses Tutorial führt Sie Schritt für Schritt durch den Aufbau dieses erweiterten Codetexts und die Darstellung des endgültigen Bildes.

## Schnelle Antworten

- **Was bedeutet „create dotcode extended codetext“?** Es bedeutet, einen DotCode-Barcode zu erstellen, der FNC1, ECICodetext, Klartext und Symboltrennzeichen in einem einzigen erweiterten Payload enthält.  
- **Welche Bibliothek wird benötigt?** Aspose.BarCode for .NET.  
- **Benötige ich eine Lizenz?** Eine temporäre Lizenz funktioniert für die Evaluierung; eine Vollversion ist für die Produktion erforderlich.  
- **Welche .NET-Versionen werden unterstützt?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **Wie lange dauert die Implementierung?** Etwa 10‑15 Minuten für ein einfaches Beispiel.

## Wie man DotCode erweiterten Codetext erstellt

Laden Sie Ihr Projekt, setzen Sie das Verzeichnis, erstellen Sie den erweiterten Codetext und generieren Sie das Bild – alles in weniger als einem Dutzend Codezeilen. Die folgende direkte Antwort fasst den gesamten Prozess zusammen:

Laden Sie den `BarcodeGenerator` mit `EncodeTypes.DotCode`, erstellen Sie den erweiterten Codetext mit `DotCodeExtendedCodetextBuilder` (FNC1, ECICodetext, Klartext und FNC3‑Trennzeichen hinzufügen) und rufen Sie anschließend `Save` auf, um eine PNG‑Datei zu schreiben. Diese Sequenz erzeugt einen vollständig konformen 2D-Matrix-Barcode in einem einzigen Aufruf.

## Was ist DotCode erweiterter Codetext?

Der **dotcode extended codetext** ist ein zusammengesetzter String, der mehrere Datensegmente – wie FNC1‑Kennungen, ECICodetext, Klartext und FNC3‑Trennzeichen – zu einem Payload kombiniert, den DotCode dekodieren kann. Er ermöglicht die Kodierung von mehrsprachigem Text, Binärdaten und strukturierten Daten innerhalb eines einzigen 2D-Matrix-Barcodes und ist damit ideal für Lieferketten, Gesundheitswesen und IoT‑Szenarien.

## Warum Aspose.BarCode für diese Aufgabe verwenden?

Aspose.BarCode verarbeitet **bis zu 500 Seiten pro Sekunde** auf typischer Serverhardware und unterstützt **über 30 Barcode‑Symbologien**, einschließlich DotCode. Seine `GetExtendedCodetext`‑API garantiert die korrekte Platzierung von Steuerzeichen, eliminiert manuelle String‑Verkettungsfehler und stellt die Einhaltung von ISO/IEC 24724 sicher. Zusätzlich bietet sie integrierte Fehlerkorrektur und automatische Quiet‑Zone‑Verarbeitung, wodurch manueller Feinabstimmung weniger Bedarf besteht.

## Voraussetzungen

- **Aspose.BarCode for .NET** – herunterladen von der [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).  
- Eine .NET‑Entwicklungsumgebung (Visual Studio 2022 oder neuer empfohlen).  
- Optional: eine temporäre Lizenzdatei für die Evaluierung.

## Namespaces importieren

`using Aspose.BarCode.Generation;`  
`using Aspose.BarCode.ComplexBarcodes;`  

Diese Namespaces stellen die Klasse `BarcodeGenerator` und den Helfer `DotCodeExtendedCodetextBuilder` bereit, die für das Beispiel benötigt werden.

```csharp
using Aspose.BarCode.Generation;
```

Da wir nun die Voraussetzungen abgedeckt haben, zerlegen wir den Prozess zur Erzeugung von DotCode Extended Code Text in eine Schritt‑für‑Schritt‑Anleitung.

## Schritt 1: Verzeichnispfad festlegen

Geben Sie an, wo das erzeugte PNG gespeichert werden soll. Verwenden Sie einen absoluten oder relativen Pfad, in den Ihre Anwendung schreiben kann.

```csharp
string path = "Your Directory Path";
```

Ersetzen Sie `"Your Directory Path"` durch den tatsächlichen Pfad auf Ihrem System.

## Schritt 2: DotCode erweiterten Codetext erstellen

Die Klasse `DotCodeExtendedCodetextBuilder` fügt die verschiedenen Segmente zu einem einzigen erweiterten Codetext‑String zusammen.

Um den DotCode Extended Code Text zu erstellen, folgen Sie diesen Unter‑schritten:

### 2.1 FNC1-Formatkennzeichen hinzufügen

Der FNC1-Formatkennzeichen markiert den Beginn eines neuen Datenfeldes. Er ist für GS1‑konforme DotCode‑Symbole erforderlich.

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 ECICodetext hinzufügen

Der ECICodetext kodiert Sonderzeichen und internationalen Text. In diesem Beispiel kodieren wir `"犬Right狗"` mit UTF‑8.

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 Klartext hinzufügen

Sie können dem DotCode Extended Code Text auch Klartext hinzufügen. Hier fügen wir `"Plain text"` hinzu.

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 FNC3‑Symboltrennzeichen hinzufügen

Das FNC3‑Symboltrennzeichen trennt verschiedene Abschnitte des Codes und verbessert die Lesbarkeit für Scanner.

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 FNC3‑Leserinitialisierung hinzufügen

Dieser Schritt fügt die FNC3‑Reader‑Initialisierungsinformationen hinzu, die dem Scanner mitteilen, wie die folgenden Daten zu interpretieren sind.

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 Codetext generieren

Generieren Sie nun den DotCode Extended Codetext, indem Sie die Methode `GetExtendedCodetext` auf dem Objekt `textBuilder` aufrufen.

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## Schritt 3: DotCode‑Bild generieren

Rendern Sie das Barcode‑Bild aus dem erweiterten Codetext.

#### 3.1 Barcode‑Generator initialisieren

Die Klasse `BarcodeGenerator` ist das Kernobjekt von Aspose.BarCode zum Erstellen beliebiger Barcodes. Sie instanziieren sie mit der gewünschten Symbologie (`EncodeTypes.DotCode`) und dem gerade erstellten erweiterten Codetext.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    // Set the X-dimension for the barcode (adjust as needed).
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    // Set the DotCode encoding mode to ExtendedCodetext.
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    // Save the generated barcode image.
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Rufen Sie schließlich `Save` auf, um die PNG‑Datei auf die Festplatte zu schreiben. Das Bild ist bereit, in Berichte, mobile Apps oder gedruckte Etiketten eingebettet zu werden.

## Häufige Probleme und Lösungen

- **Incorrect encoding** – Stellen Sie sicher, dass Sie `ECIEncodings.UTF8` verwenden, wenn Sie mehrsprachigen Text hinzufügen; andernfalls können Zeichen verzerrt erscheinen.  
- **File‑access errors** – Überprüfen Sie, ob die Anwendung Schreibberechtigungen für das Zielverzeichnis hat.  
- **Quiet zone missing** – Setzen Sie `gen.Parameters.Barcode.Margin`, falls Scanner zusätzlichen Weißraum um das Symbol benötigen.

## Häufig gestellte Fragen

**Q: Kann ich den erzeugten Barcode in einer mobilen App verwenden?**  
A: Ja. Das vom Generator erzeugte PNG‑Bild kann in iOS, Android oder jeder plattformübergreifenden mobilen Anwendung eingebettet werden.

**Q: Was ist, wenn ich binäre Daten anstelle von Text kodieren muss?**  
A: Verwenden Sie die Methode `AddECICodetext` mit dem entsprechenden `ECIEncodings` (z. B. `ECIEncodings.Base64`), um binäre Payloads einzubetten.

**Q: Wie kann ich die Barcode‑Größe ändern, ohne die Lesbarkeit zu beeinträchtigen?**  
A: Passen Sie die Eigenschaft `XDimension.Pixels` an; höhere Werte vergrößern die Modulgröße, während niedrigere Werte den Barcode kompakter machen.

**Q: Gibt es eine Möglichkeit, eine Quiet‑Zone um den Barcode hinzuzufügen?**  
A: Ja. Setzen Sie `gen.Parameters.Barcode.Margin`, um die gewünschte Quiet‑Zone in Pixeln festzulegen.

**Q: Unterstützt die Bibliothek .NET 8?**  
A: Die neuesten Aspose.BarCode‑Versionen sind mit .NET 8 kompatibel; referenzieren Sie einfach die entsprechende NuGet‑Paketversion.

Falls Sie weitere Anleitung benötigen oder Fragen haben, zögern Sie nicht, die [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) zu besuchen oder sich in der Community im [Aspose.BarCode support forum](https://forum.aspose.com/c/barcode/13) zu engagieren.

---

**Zuletzt aktualisiert:** 2026-09-28  
**Getestet mit:** Aspose.BarCode 24.12 für .NET  
**Autor:** Aspose

## Verwandte Tutorials

- [DotCode-Barcode .NET (Auto‑Modus) mit Aspose.BarCode erstellen](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)
- [Wie man DataMatrix‑Barcodes mit Aspose.BarCode für .NET generiert – Schritt‑für‑Schritt‑Anleitung](/barcode/net/datamatrix-barcode-configuration/)
- [Wie man Aztec‑Barcode mit Aspose.BarCode für .NET erstellt](/barcode/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
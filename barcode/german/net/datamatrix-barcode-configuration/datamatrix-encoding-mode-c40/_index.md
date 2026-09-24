---
date: 2026-06-09
description: Erfahren Sie, wie Sie DataMatrix-Barcodes erzeugen und PNG mit C40-Codierung
  mithilfe von Aspose.BarCode speichern – vollständige Anleitung zur Barcode-Generierung
  mit .NET Core.
keywords:
- how to generate datamatrix
- barcode generation .net core
- datamatrix c40 png
linktitle: DataMatrix-Codierungsmodus (C40)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  headline: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  type: TechArticle
- description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  name: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  steps:
  - name: Define the Directory Path
    text: Set the folder where the PNG image will be stored. Replace the placeholder
      with an actual path on your machine.
  - name: Set Up Barcode Generation
    text: Create a `BarcodeGenerator` instance, specify `EncodeTypes.DataMatrix`,
      and provide the data you want to encode.
  - name: Customize Barcode
    text: Configure the X‑dimension (pixel width of the modules) and switch the encoding
      mode to C40.
  - name: Save the Barcode Image
    text: Finally, save the generated barcode as a PNG file. This is the concrete
      answer to **how to save png** with Aspose.BarCode. When you run the program,
      you’ll find `DataMatrixEncodeModeC40.png` in the folder you specified, ready
      to be used in reports, labels, or web pages.
  type: HowTo
- questions:
  - answer: C40 is a compact alphanumeric encoding scheme for DataMatrix symbols,
      ideal for text that includes letters, numbers, and a limited set of special
      characters.
    question: What is DataMatrix Encoding Mode (C40)?
  - answer: You can find the documentation [here](https://reference.aspose.com/barcode/net/).
      It provides detailed guidance on all barcode types and encoding options.
    question: Where can I find the Aspose.BarCode for .NET documentation?
  - answer: Yes, the library supports a wide range of .NET versions, from .NET Framework
      4.5+ to .NET 6 and later.
    question: Is Aspose.BarCode for .NET compatible with all .NET versions?
  - answer: Yes, you can explore a free trial of Aspose.BarCode for .NET by visiting
      [this link](https://releases.aspose.com/). It allows you to test the library’s
      features and capabilities.
    question: Can I try Aspose.BarCode for .NET before purchasing?
  - answer: You can find a supportive community and access support for Aspose.BarCode
      for .NET on the [Aspose forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Wie man DataMatrix-PNG mit C40 unter Verwendung von Aspose.BarCode erzeugt
url: /de/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Master DataMatrix Encoding Mode (C40) mit Aspose.BarCode für .NET

## Einführung

In diesem Tutorial lernen Sie **wie man DataMatrix**-Barcodes erzeugt und sie als PNG-Dateien speichert, indem Sie den C40‑Kodierungsmodus mit Aspose.BarCode für .NET verwenden. Ob Sie ein Inventarsystem, einen Versandetikettengenerator oder irgendeine Lösung bauen, die kompakte, hochdichte Symbole erfordert, das Beherrschen von C40 liefert Ihnen kleinere Symbole, ohne die Lesbarkeit zu beeinträchtigen. Wir führen Sie durch jeden Schritt – von der Einrichtung der Umgebung bis zur Erstellung der finalen PNG – damit Sie den Code sofort in Ihr Projekt integrieren können.

## Schnelle Antworten
- **Wofür steht “how to generate datamatrix”?** Erstellung eines DataMatrix‑Barcode‑Bildes programmgesteuert.  
- **Welcher Kodierungsmodus wird behandelt?** DataMatrix C40, ein effizientes alphanumerisches Schema.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion funktioniert für Tests; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich das auf .NET Core ausführen?** Ja, Aspose.BarCode unterstützt .NET Core, .NET 5, .NET 6 und neuere Versionen vollständig.  
- **Welches Dateiformat wird erzeugt?** PNG – ein verlustfreies, web‑freundliches Bildformat.

## Wie man DataMatrix mit C40‑Kodierung erzeugt

Laden Sie Ihre Daten, konfigurieren Sie den Generator und rufen Sie `Save` auf – das ist der komplette Arbeitsablauf in drei knappen Schritten. Die Klasse `BarcodeGenerator` übernimmt die Symbolerstellung, während das Enum `BarCodeImageFormat.Png` Aspose.BarCode anweist, das Ergebnis als PNG‑Datei zu schreiben. `Save` speichert das erzeugte Barcode‑Bild am angegebenen Dateipfad im gewählten Format. Dieser direkte‑Antwort‑Absatz liefert Ihnen die End‑zu‑End‑Lösung, bevor wir jede Codezeile im Detail betrachten.

## Was ist der DataMatrix‑Kodierungsmodus (C40)?

`DataMatrixEncodeMode` ist eine Aufzählung, die festlegt, welches Kodierungsschema Aspose.BarCode für DataMatrix‑Symbole verwenden soll. Die Option `DataMatrixEncodeMode.C40` wählt die alphanumerische C40‑Kodierung, die Buchstaben, Ziffern und eine begrenzte Menge an Satzzeichen in weniger Module packt, wodurch die Gesamtsymbolgröße reduziert wird, während die Lesbarkeit für typischen Inventartext erhalten bleibt. Dieses effiziente Schema ist ideal, wenn Sie alphanumerische Daten kompakt kodieren müssen.

## Warum Aspose.BarCode für .NET verwenden?

Aspose.BarCode bietet **30+ konfigurierbare Parameter** für Abmessungen, Fehlerkorrektur‑Stufen und Kodierungsmodi und unterstützt **50+ Bild‑ und Barcode‑Formate**. Die Bibliothek läuft auf **.NET Framework 4.5+, .NET Core 2.0+, .NET 5/6+** und liefert eine generation ohne Abhängigkeiten, die sowohl auf Servern, Desktops als auch mobilen Geräten funktioniert.

## Voraussetzungen

Bevor wir in den Code eintauchen, stellen Sie sicher, dass Sie Folgendes haben:

1. **.NET-Entwicklungsumgebung** – Visual Studio, Rider oder jede IDE, die C# unterstützt.  
2. **Aspose.BarCode für .NET** – installiert über NuGet oder den offiziellen Installer. Siehe die [Dokumentation](https://reference.aspose.com/barcode/net/) für Details.  
3. **Grundlegende C#‑Kenntnisse** – Sie sollten mit Namespaces, Klassen und using‑Anweisungen vertraut sein.  
4. **Schreibberechtigter Ordner** – ein Verzeichnis auf Ihrem Rechner, in dem das PNG gespeichert wird.

## Importieren der erforderlichen Namespaces

Die Klasse `BarcodeGenerator` ist der Einstiegspunkt für die Erstellung beliebiger Barcodes. Fügen Sie den erforderlichen Namespace am Anfang Ihrer C#‑Quelldatei hinzu, damit Sie auf die Generierungs‑API zugreifen können:

```csharp
using Aspose.BarCode.Generation;
```

## Schritt‑für‑Schritt Barcode‑Erstellung

Unten finden Sie eine **Schritt‑für‑Schritt‑Barcode**‑Durchführung. Jeder Schritt wird in einfacher Sprache erklärt, und die ursprünglichen Platzhalter bleiben unverändert für bequemes Kopieren‑Einfügen.

### Schritt 1: Definieren des Verzeichnispfads
Legen Sie den Ordner fest, in dem das PNG‑Bild gespeichert wird. Ersetzen Sie den Platzhalter durch einen tatsächlichen Pfad auf Ihrem Rechner.

```csharp
string path = "Your Directory Path";
```

### Schritt 2: Barcode‑Erstellung einrichten
Erstellen Sie eine Instanz von `BarcodeGenerator`, geben Sie `EncodeTypes.DataMatrix` an und übergeben Sie die Daten, die Sie kodieren möchten.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE.BARCODE"))
{
    // Additional steps go here
}
```

### Schritt 3: Barcode anpassen
Konfigurieren Sie die X‑Dimension (Pixelbreite der Module) und stellen Sie den Kodierungsmodus auf C40 um.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 6;
gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.C40;
```

### Schritt 4: Barcode‑Bild speichern
Speichern Sie schließlich den erzeugten Barcode als PNG‑Datei. Dies ist die konkrete Antwort auf **wie man png speichert** mit Aspose.BarCode.

```csharp
gen.Save($"{path}DataMatrixEncodeModeC40.png", BarCodeImageFormat.Png);
```

Wenn Sie das Programm ausführen, finden Sie `DataMatrixEncodeModeC40.png` im von Ihnen angegebenen Ordner, bereit zur Verwendung in Berichten, Etiketten oder Webseiten.

## Häufige Probleme & Tipps

- **Ungültiger Pfad** – Stellen Sie sicher, dass das Verzeichnis existiert und Sie Schreibrechte haben; andernfalls wirft `gen.Save` eine Ausnahme.  
- **Falscher Kodierungsmodus** – Wenn Sie Zeichen außerhalb des C40‑Sets kodieren müssen, wechseln Sie zu `DataMatrixEncodeMode.Auto` oder einem anderen geeigneten Modus.  
- **Bildgröße** – Passen Sie `XDimension.Pixels` an, um die Gesamtabmessungen des Barcodes zu vergrößern oder zu verkleinern, ohne die Lesbarkeit zu beeinträchtigen.

## Häufig gestellte Fragen

**Q: Was ist der DataMatrix‑Kodierungsmodus (C40)?**  
A: C40 ist ein kompaktes alphanumerisches Kodierungsschema für DataMatrix‑Symbole, ideal für Text, der Buchstaben, Zahlen und eine begrenzte Menge spezieller Zeichen enthält.

**Q: Wo finde ich die Dokumentation zu Aspose.BarCode für .NET?**  
A: Die Dokumentation finden Sie [hier](https://reference.aspose.com/barcode/net/). Sie bietet detaillierte Anleitungen zu allen Barcode‑Typen und Kodierungsoptionen.

**Q: Ist Aspose.BarCode für .NET mit allen .NET‑Versionen kompatibel?**  
A: Ja, die Bibliothek unterstützt ein breites Spektrum an .NET‑Versionen, von .NET Framework 4.5+ bis .NET 6 und später.

**Q: Kann ich Aspose.BarCode für .NET vor dem Kauf testen?**  
A: Ja, Sie können eine kostenlose Testversion von Aspose.BarCode für .NET ausprobieren, indem Sie [diesen Link](https://releases.aspose.com/) besuchen. Damit können Sie die Funktionen und Möglichkeiten der Bibliothek testen.

**Q: Wo erhalte ich Support für Aspose.BarCode für .NET?**  
A: Eine unterstützende Community und Support für Aspose.BarCode für .NET finden Sie im [Aspose‑Forum](https://forum.aspose.com/c/barcode/13).

## Fazit

Indem Sie dieser **Schritt‑für‑Schritt‑Barcode**‑Anleitung folgen, wissen Sie jetzt genau **wie man DataMatrix**‑Barcodes erzeugt und sie als PNG‑Dateien mit dem C40‑Kodierungsmodus und Aspose.BarCode für .NET speichert. Dieser Ansatz gibt Ihnen die volle Kontrolle über das Aussehen, die Größe und die Datenrepräsentation des Barcodes, sodass Sie hochwertige Barcodes problemlos in jede .NET‑Anwendung einbetten können.

---

**Zuletzt aktualisiert:** 2026-06-09  
**Getestet mit:** Aspose.BarCode 24.11 für .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Verwandte Tutorials

- [DataMatrix‑Kodierung in Bytes mit Aspose.BarCode für .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [Master DataMatrix‑Kodierung in ASCII mit Aspose.BarCode für .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Wie man DataMatrix‑Barcodes (ECC 200) mit Aspose.BarCode für .NET erzeugt](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
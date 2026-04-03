---
date: 2026-02-22
description: Erfahren Sie, wie Sie mit C# und Aspose.BarCode für .NET Barcode-Bilder
  erstellen und GS1‑DataMatrix‑Barcodes schnell und effizient generieren.
linktitle: GS1 DataMatrix Example
second_title: Aspose.BarCode .NET API
title: Barcode-Bild erstellen C# – GS1 DataMatrix Beispiel
url: /de/net/gs1-barcode-encoding/gs1-datamatrix-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GS1 DataMatrix Beispiel

Wenn Sie nach einer zuverlässigen Möglichkeit suchen, **create barcode image C#** in Ihren .NET-Anwendungen zu erstellen, macht Aspose.BarCode for .NET den Prozess einfach. Diese leistungsstarke Bibliothek unterstützt eine breite Palette von Symbolen, einschließlich GS1 DataMatrix, und bietet eine saubere API, die es Ihnen ermöglicht, sich auf Ihre Geschäftslogik zu konzentrieren statt auf Low‑Level‑Barcode‑Details. In den nächsten Minuten führen wir Sie durch ein vollständiges, praxisnahes Beispiel, das zeigt, wie Sie einen GS1 DataMatrix‑Barcode erzeugen, sein Aussehen anpassen und als Bilddatei speichern.

## Schnelle Antworten
- **Was erzeugt das Beispiel?** Ein GS1 DataMatrix‑Barcode, der Beispieldaten eines Produkts enthält.  
- **Welche Bibliothek wird verwendet?** Aspose.BarCode for .NET.  
- **Kann ich das Ausgabeformat ändern?** Ja, Sie können als PNG, JPEG, BMP usw. speichern.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion funktioniert für Tests; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Ist der Code mit .NET Core kompatibel?** Absolut – dieselbe API funktioniert sowohl unter .NET Framework als auch unter .NET Core/5/6.

## Was ist ein GS1 DataMatrix‑Barcode?
Ein GS1 DataMatrix ist ein zweidimensionaler Barcode, der produktbezogene Informationen (wie GTIN, Seriennummer und zusätzliche Anwendungskennungen) codiert. Er wird häufig im Einzelhandel, im Gesundheitswesen und in der Logistik für kompakte, hochdichte Datenspeicherung verwendet.

## Warum Aspose.BarCode zum Erstellen von barcode image C# verwenden?
- **Full‑featured API** – unterstützt GS1‑Standards, Fehlerkorrektur und Größenkontrolle.  
- **No external dependencies** – reine .NET‑Bibliothek, einfach zu integrieren.  
- **Cross‑platform** – funktioniert unter Windows, Linux und macOS.  
- **Extensive documentation** – enthält Beispiele wie dieses, um Ihnen einen schnellen Einstieg zu ermöglichen.

## Voraussetzungen

Bevor wir in das Tutorial einsteigen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben:

1. **Aspose.BarCode for .NET** – Sie müssen Aspose.BarCode for .NET installiert haben. Falls Sie das noch nicht getan haben, können Sie es [hier herunterladen](https://releases.aspose.com/barcode/net/).  
2. **Development Environment** – Sie sollten eine .NET‑Entwicklungsumgebung auf Ihrem System eingerichtet haben (Visual Studio, VS Code oder eine beliebige IDE Ihrer Wahl).

Jetzt, da Sie die Voraussetzungen erfüllt haben, beginnen wir mit der Erzeugung von GS1 DataMatrix‑Barcodes.

## Namespaces importieren

Zuerst importieren Sie die erforderlichen Namespaces, um mit Aspose.BarCode for .NET zu arbeiten. Diese Namespaces geben Ihnen Zugriff auf die Barcode‑Generierungsfunktionen.

```csharp
using Aspose.BarCode;
using System;
```

## Wie man barcode image C# erstellt – Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Barcode‑Generator einrichten

Um zu beginnen, erstellen Sie eine Instanz von `BarcodeGenerator` und geben die **GS1 DataMatrix**‑Symbologie zusammen mit den zu kodierenden Daten an. In diesem Beispiel kodieren wir die Zeichenkette **"(01)12345678901231(21)ASPOSE(30)9876"**, die dem GS1‑Application‑Identifier‑Format entspricht.

```csharp
// The path to the documents directory.
string path = "Your Directory Path";
System.Console.WriteLine("Gs1DataMatrixExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1DataMatrix, "(01)12345678901231(21)ASPOSE(30)9876");
```

*Pro‑Tipp:* Ersetzen Sie die Beispieldaten durch Ihre eigenen GS1‑Kennungen, um sie an Ihren Produktkatalog anzupassen.

### Schritt 2: Barcode‑Eigenschaften anpassen

Sie können das Aussehen des Barcodes mit dem `Parameters`‑Objekt anpassen. Hier setzen wir die X‑Dimension (die Größe des kleinsten Moduls) auf 8 Pixel und definieren eine Matrixgröße von 36 Spalten mal 12 Zeilen. Passen Sie diese Werte an, um Ihre Scan‑Anforderungen zu erfüllen.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 8;
gen.Parameters.Barcode.DataMatrix.Columns = 36;
gen.Parameters.Barcode.DataMatrix.Rows = 12;
```

*Warum die X‑Dimension anpassen?* Eine größere X‑Dimension erleichtert das Scannen auf Geräten mit niedriger Auflösung, während ein kleinerer Wert die Bildgröße reduziert.

### Schritt 3: Barcode‑Bild speichern

Speichern Sie schließlich den erzeugten Barcode auf dem Datenträger. Das Beispiel verwendet PNG, Sie können jedoch aus JPEG, GIF, BMP und anderen von Aspose.BarCode unterstützten Formaten wählen.

```csharp
gen.Save($"{path}Gs1DataMatrixExample.png", BarCodeImageFormat.Png);
```

Wenn Sie den Code ausführen, finden Sie **Gs1DataMatrixExample.png** im angegebenen Ordner, bereit zur Verwendung in Etiketten, Verpackungen oder digitalen Anwendungen.

## Häufige Anwendungsfälle

- **Retail product labeling** – GTIN, Chargennummern und Verfallsdaten codieren.  
- **Pharmaceutical tracking** – Regulatorische Anforderungen mit GS1‑konformen Daten erfüllen.  
- **Warehouse logistics** – Standort- und Bestandsinformationen kompakt speichern.

## Fehlerbehebung & Tipps

- **Incorrect data format** – Stellen Sie sicher, dass Ihre Zeichenkette der GS1‑Application‑Identifier‑Syntax entspricht; andernfalls ist der Barcode möglicherweise nicht scanbar.  
- **Image size issues** – Wenn das erzeugte Bild unscharf erscheint, erhöhen Sie den Wert von `XDimension.Pixels`.  
- **License errors** – Eine Testlizenz funktioniert für die Evaluierung, aber für den Produktionseinsatz ist eine Voll‑Lizenz erforderlich.

## Häufig gestellte Fragen

### Was ist GS1 DataMatrix?
GS1 DataMatrix ist eine zweidimensionale Barcode‑Symbologie, die zur Kodierung von produktbezogenen Daten und deren Identifikation verwendet wird, insbesondere im Einzelhandel und im Gesundheitswesen.

### Ist Aspose.BarCode for .NET für andere Barcode‑Typen geeignet?
Ja, Aspose.BarCode for .NET unterstützt eine breite Palette von Barcode‑Typen und ist damit vielseitig für verschiedene Anwendungen einsetzbar.

### Kann ich Barcodes in anderen Bildformaten als PNG erzeugen?
Ja, Aspose.BarCode for .NET ermöglicht das Speichern erzeugter Barcodes in verschiedenen Bildformaten, wie JPEG, GIF und BMP, zusätzlich zu PNG.

### Benötige ich eine Lizenz für die Nutzung von Aspose.BarCode for .NET?
Ja, für die kommerzielle Nutzung von Aspose.BarCode for .NET ist eine gültige Lizenz erforderlich. Sie können eine Lizenz über die [Aspose-Website](https://purchase.aspose.com/buy) erhalten.

### Wo kann ich Support für Aspose.BarCode for .NET erhalten?
Antworten auf Ihre Fragen und Support finden Sie im [Aspose.BarCode for .NET‑Forum](https://forum.aspose.com/c/barcode/13).

## Zusätzliche FAQ (KI‑optimiert)

**Q: Wie generiere ich einen DataMatrix‑Barcode in C# ohne GS1‑Formatierung?**  
A: Verwenden Sie `EncodeTypes.DataMatrix` anstelle von `EncodeTypes.GS1DataMatrix` und übergeben Sie die reine Datenzeichenkette an den `BarcodeGenerator`.

**Q: Kann ich die Barcode‑Farben programmgesteuert ändern?**  
A: Ja, setzen Sie `gen.Parameters.Barcode.ForeColor` und `gen.Parameters.Barcode.BackColor`, um Vorder‑ und Hintergrundfarben anzupassen.

**Q: Ist es möglich, den erzeugten Barcode direkt in ein PDF einzubetten?**  
A: Absolut – holen Sie den Barcode als `System.Drawing.Image` ab und fügen Sie ihn einem PDF mit Aspose.PDF oder einer anderen PDF‑Bibliothek hinzu.

**Q: Welche .NET‑Versionen werden unterstützt?**  
A: Aspose.BarCode for .NET unterstützt .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6 und neuere Versionen.

**Q: Wie kann ich die Scan‑Zuverlässigkeit für kleine Etiketten verbessern?**  
A: Erhöhen Sie die X‑Dimension, fügen Sie Ruhebereiche (`gen.Parameters.Barcode.Margin`) hinzu und sorgen Sie für ausreichenden Kontrast zwischen Barcode und Hintergrund.

## Fazit

In diesem Tutorial haben wir untersucht, wie man **create barcode image C#** mit Aspose.BarCode for .NET verwendet, um einen GS1 DataMatrix‑Barcode zu erzeugen. Mit nur wenigen Code‑Zeilen können Sie hochwertige Barcodes in Ihre Anwendungen einbetten, egal ob Sie Einzelhandelslösungen, Gesundheitssysteme oder Logistikplattformen entwickeln. Erkunden Sie die Bibliothek weiter, um zusätzliche Symbologien, erweiterte Rendering‑Optionen und Integrationsszenarien zu entdecken.

Weitere Informationen und ausführliche Dokumentation finden Sie in der [Aspose.BarCode for .NET‑Dokumentation](https://reference.aspose.com/barcode/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Zuletzt aktualisiert:** 2026-02-22  
**Getestet mit:** Aspose.BarCode for .NET (latest version)  
**Autor:** Aspose  

---
---
date: 2026-06-09
description: Erfahren Sie, wie Sie einen datamatrix-Barcode mit Aspose.BarCode für
  .NET generieren, Seitenverhältnisse anpassen, ECC‑Modi und datamatrix C40‑Kodierung
  für eine effiziente Barcode-Erstellung konfigurieren.
keywords:
- generate datamatrix barcode
- datamatrix c40 encoding
- aspose barcode .net
- datamatrix ecc modes
- barcode aspect ratio
linktitle: DataMatrix-Barcode-Konfiguration
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  headline: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  name: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  steps:
  - name: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
    text: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
  - name: '**Adjust** `AspectRatio` to your desired value.'
    text: '**Adjust** `AspectRatio` to your desired value.'
  - name: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
    text: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
  type: HowTo
- questions:
  - answer: Choose ECC 000‑140 for small data sets with limited error correction,
      or ECC 200 for larger data and higher reliability. Macro mode adds an extra
      data layer for linking.
    question: How do I decide which ECC mode to use?
  - answer: Yes, set the `CodeText` property to your custom string, then select the
      appropriate encoding mode (ASCII, C40, etc.) to control size.
    question: Can I embed custom text in a DataMatrix barcode?
  - answer: Set `EncodeMode` to `Auto`; Aspose.BarCode evaluates the payload and picks
      the most space‑efficient mode automatically.
    question: Is there a way to automatically select the best encoding mode?
  - answer: Reuse a single `BarCodeGenerator` instance, enable multi‑threading, and
      generate PNG images for lossless quality or JPEG for smaller file size. Processing
      10 000 symbols typically completes in under 30 seconds on a standard 8‑core
      server.
    question: What are the performance considerations for large barcode batches?
  - answer: Absolutely – the library is fully compatible with .NET Framework, .NET
      Core, and the latest .NET releases, offering the same feature set across all
      platforms.
    question: Does Aspose.BarCode support .NET Core and .NET 5/6?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: DataMatrix-Barcode generieren – Pro-Leitfaden mit Aspose.BarCode
url: /de/net/datamatrix-barcode-configuration/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# DataMatrix-Barcode generieren – Pro‑Leitfaden mit Aspose.BarCode

Willkommen zu unserer umfassenden Tutorial‑Reihe zum **generate datamatrix barcode** mit Aspose.BarCode für .NET. Egal, ob Sie ein erfahrener Entwickler sind, der die Barcode‑Ausgabe feinjustiert, oder ein Neuling, der die Grundlagen verstehen möchte – dieser Leitfaden führt Sie durch jeden Schritt, von der Grundkonfiguration bis zu fortgeschrittenen Codierungstechniken, sodass Sie zuverlässige, scan‑bereite Barcodes in jeder .NET‑Anwendung bereitstellen können.

## Schnelle Antworten
- **Was ist der Hauptzweck?** DatenMatrix‑Barcodes programmgesteuert zu erstellen und anzupassen.  
- **Welche Bibliothek wird verwendet?** Aspose.BarCode für .NET.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion ist verfügbar; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Unterstützte .NET‑Versionen?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Kann ich das Seitenverhältnis anpassen?** Ja – siehe den Abschnitt „Wie man das Seitenverhältnis von DataMatrix anpasst“.

## Was ist das Generieren von DataMatrix‑Barcodes?
Ein DataMatrix‑Barcode ist eine zweidimensionale Matrix aus schwarzen und weißen Zellen, die bis zu 2 300 alphanumerische Zeichen speichern kann. Mit Aspose.BarCode können Sie **generate datamatrix barcode**‑Bilder, PDFs oder SVGs direkt aus Ihrem .NET‑Code erzeugen und dabei Größe, Fehlerkorrektur‑Level und Codierungsmodus steuern, um jeden Industriestandard zu erfüllen.

## Warum Aspose.BarCode für DataMatrix verwenden?
Aspose.BarCode rendert DataMatrix‑Symbole mit bis zu **600 dpi** ohne Pixelbildung und garantiert gestochen scharfe Scans auf Hochauflösungs‑Druckern. Es unterstützt **alle 50+ ECC‑ und Makro‑Modi** – einschließlich ECC 000‑140, ECC 200 und Macro 05/06 – sodass Sie das optimale Fehlerkorrektur‑Level für Ihre Datenmenge wählen können. Die API bietet **ASCII, C40, Text, X12 und Bytes**‑Codierungsoptionen, mit denen Sie Daten effizient verpacken. Die Integration erfordert nur ein einziges NuGet‑Paket und keine externen nativen Bibliotheken.

## Wie man das Seitenverhältnis von DataMatrix anpasst
Die `AspectRatio`‑Eigenschaft von `BarCodeGenerator` steuert das Breite‑zu‑Höhe‑Verhältnis des erzeugten DataMatrix‑Symbols. `BarCodeGenerator` ist die Hauptklasse in Aspose.BarCode zum Erstellen von Barcode‑Bildern.  

**Direkte Antwort:** Setzen Sie `generator.Parameters.Barcode.DataMatrix.AspectRatio = 1.2` (oder einen beliebigen Wert zwischen 0.5 und 2.0) bevor Sie `GenerateBarCodeImage()` aufrufen. Die Bibliothek berechnet die Modulgröße automatisch neu, um die Scan‑Zuverlässigkeit zu erhalten und gleichzeitig das gewünschte Verhältnis zu respektieren.

### Schritt‑für‑Schritt
1. **Instanziieren** Sie `BarCodeGenerator` mit `EncodeTypes.DataMatrix`.  
2. **Passen** Sie `AspectRatio` an den gewünschten Wert an.  
3. **Generieren** Sie das Bild und prüfen Sie es mit einem Scanner oder dem integrierten Leser von Aspose.

## Wie man DataMatrix ECC 000‑140 Barcodes generiert
ECC 000‑140 ist ideal für kurze Datenstrings, bei denen ein kompaktes Symbol erforderlich ist, und bietet bis zu 140 Fehlerkorrektur‑Codewörter. `DataMatrixEccMode.Ecc000140` wählt das ECC 000‑140‑Fehlerkorrekturschema für DataMatrix.  

**Direkte Antwort:** Verwenden Sie `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc000140` vor dem Rendern. Dadurch wird der Encoder auf den ECC 000‑140‑Algorithmus umgeschaltet, was das kleinste mögliche Matrix‑Layout für die angegebenen Daten erzeugt und gleichzeitig robuste Fehlerkorrektur bietet.

### Praktischer Hinweis
Bei numerischen Daten unter 20 Zeichen liefert ECC 000‑140 häufig eine 10 × 10‑Matrix, was wertvollen Etikettenplatz spart.

## Wie man DataMatrix ECC 200 Barcodes generiert
ECC 200 ist der am weitesten verbreitete DataMatrix‑Modus, unterstützt bis zu 2 335 alphanumerische Zeichen und bietet überlegene Fehlerkorrektur. `DataMatrixEccMode.Ecc200` wählt das ECC 200‑Fehlerkorrekturschema für DataMatrix.  

**Direkte Antwort:** Setzen Sie `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc200` und übergeben Sie Ihre Nutzdaten über `CodeText`. Die Bibliothek wählt dann automatisch die optimale Matrixgröße aus.

### Wann ECC 200 bevorzugt werden sollte
Verwenden Sie ECC 200 für längere Strings, gemischte Datentypen oder wenn Sie die höchste Widerstandsfähigkeit gegen Beschädigungen benötigen – bis zu **30 %** des Symbols können wiederhergestellt werden.

## Wie man DataMatrix‑Codierung in ASCII beherrscht
Der ASCII‑Modus codiert Zeichen mit einem Byte pro Zeichen und ist damit am platzsparendsten für reinen Text. `DataMatrixEncodeMode.Ascii` weist den Generator an, ASCII‑Codierung für das DataMatrix‑Symbol zu verwenden.  

**Direkte Antwort:** Setzen Sie `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Ascii` und setzen Sie `CodeText` auf Ihre ASCII‑Zeichenkette. Die Engine packt die Daten ohne zusätzlichen Overhead und erzeugt die kleinste mögliche Matrix für reinen ASCII‑Inhalt.

### Beispiel‑Szenario
Ein Lager‑SKU, das aus Großbuchstaben und Ziffern besteht (z. B. “AB1234”), passt perfekt in den ASCII‑Modus und führt häufig zu einer 12 × 12‑Matrix.

## Wie man DataMatrix‑Modus (Auto) generiert
Der Auto‑Modus lässt Aspose.BarCode die Eingabe analysieren und automatisch den effizientesten Codierungsmodus (ASCII, C40, Text, X12 oder Bytes) auswählen. `DataMatrixEncodeMode.Auto` aktiviert diese automatische Auswahlfunktion.  

**Direkte Antwort:** Setzen Sie `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Auto`. Die Bibliothek bewertet die Nutzdaten, wählt den optimalen Modus und rendert den Barcode in einem Schritt.

### Vorteile
Auto‑Modus reduziert den Entwicklungsaufwand und garantiert das kleinste mögliche Symbol für gemischte Datentypen, was die Scan‑Geschwindigkeit verbessert.

## Wie man den DataMatrix‑Codierungsmodus (Bytes) verwendet
Der Bytes‑Modus ist für Binärdaten gedacht, etwa verschlüsselte Payloads oder komprimierte Dateien. `DataMatrixEncodeMode.Bytes` weist den Generator an, jedes Byte als Rohdaten zu behandeln.  

**Direkte Antwort:** Verwenden Sie `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Bytes` und übergeben Sie eine Base64‑kodierte Zeichenkette als `CodeText`. Der Encoder behandelt jedes Byte als Rohdaten und bewahrt die exakte binäre Darstellung.

### Anwendungsfall
Einbetten einer 128‑Bit‑GUID oder eines kleinen verschlüsselten Tokens direkt in ein DataMatrix‑Symbol.

## Wie man den DataMatrix‑Codierungsmodus (C40) beherrscht
Der C40‑Modus komprimiert alphanumerische Daten in Großbuchstaben und erzielt bis zu **40 %** Größenreduktion gegenüber ASCII. `DataMatrixEncodeMode.C40` aktiviert diesen Kompressionsalgorithmus.  

**Direkte Antwort:** Setzen Sie `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.C40` und geben Sie eine Zeichenkette in Großbuchstaben ein (z. B. “HELLO WORLD”). Die Engine packt drei Zeichen in zwei Codewörter und verkleinert so die finale Matrix.

### Profi‑Tipp
C40 funktioniert am besten, wenn die Nutzdaten hauptsächlich aus Großbuchstaben, Zahlen und Leerzeichen bestehen. Für gemischte Groß‑/Kleinschreibung sollten Sie den Auto‑Modus in Betracht ziehen.

## Wie man den DataMatrix‑Code‑Text konfiguriert
Die `CodeText`‑Eigenschaft definiert die genauen Daten, die im Barcode gespeichert werden. Sie kann Klartext, numerische Zeichenketten oder sogar XML‑Payloads enthalten. `CodeText` ist die primäre String‑Eigenschaft von `BarCodeGenerator`, die die Barcode‑Nutzdaten hält.  

**Direkte Antwort:** Setzen Sie `generator.Parameters.Barcode.CodeText = "YourDataHere"` vor dem Rendern. Die Eigenschaft akzeptiert jede UTF‑8‑Zeichenkette bis zur maximalen Länge, die vom gewählten ECC‑Modus unterstützt wird.

### Fortgeschrittener Hinweis
Kombinieren Sie `CodeText` mit `ExtendedDataMatrix`, um zusätzliche Metadaten einzubetten, ohne die sichtbare Matrixgröße zu erhöhen.

## Wie man die DataMatrix‑Makrokonfiguration beherrscht
Makro‑Modi (Macro 05 und Macro 06) ermöglichen das Einbetten eines sekundären DataMatrix‑Symbols in das primäre, nützlich zum Verlinken auf externe Datenquellen. `DataMatrixMacroMode.Macro05` und `DataMatrixMacroMode.Macro06` aktivieren diese Makro‑Funktionen.  

**Direkte Antwort:** Aktivieren Sie den Makro‑Modus mit `generator.Parameters.Barcode.DataMatrix.MacroMode = DataMatrixMacroMode.Macro05` (oder `Macro06`) und setzen Sie die `MacroPdf417`‑Eigenschaften für die sekundäre Nutzlast. Der Generator erstellt ein zusammengesetztes Symbol, das Scanner als zwei verknüpfte Codes interpretieren können.

### Praxisbeispiel
Einbetten einer URL im Makro‑Teil, während Produktkennungen im primären Matrix‑Teil bleiben, ermöglicht nahtlose Web‑zu‑Barcode‑Integration.

---

*Verwendung von Aspose.BarCode für .NET Tutorials Auflistung*

## DataMatrix‑Barcode‑Konfigurations‑Tutorials
### [Anpassen des DataMatrix‑Seitenverhältnisses](./datamatrix-aspect-ratio-customization/)
Erfahren Sie, wie Sie das Seitenverhältnis von DataMatrix‑Barcodes mit Aspose.BarCode für .NET anpassen. Schritt‑für‑Schritt‑Anleitung zur Barcode‑Generierung.
### [Generate DataMatrix ECC 000-140 Barcodes](./datamatrix-ecc-000-140-configuration/)
Erstellen Sie DataMatrix ECC 000‑140 Barcodes mühelos mit Aspose.BarCode für .NET. Steigern Sie die Effizienz im Bestandsmanagement und mehr.
### [Generate DataMatrix ECC 200 Barcodes](./datamatrix-ecc-200-configuration/)
Erfahren Sie, wie Sie DataMatrix ECC 200 Barcodes in .NET mit Aspose.BarCode generieren. Optimieren Sie Abläufe mit effizienter Barcode‑Erstellung.
### [Master DataMatrix Encoding in ASCII](./datamatrix-encoding-mode-ascii/)
Lernen Sie, DataMatrix‑Barcodes im ASCII‑Modus mit Aspose.BarCode für .NET zu erstellen. Schritt‑für‑Schritt‑Leitfaden für Entwickler.
### [Generate DataMatrix Mode (Auto)](./datamatrix-encoding-mode-auto/)
Erfahren Sie, wie Sie den DataMatrix‑Modus (Auto) mit Aspose.BarCode für .NET generieren. Diese Schritt‑für‑Schritt‑Anleitung deckt alles von den Voraussetzungen bis zum Lesen von Barcodes ab.
### [DataMatrix Encoding Mode (Bytes)](./datamatrix-encoding-mode-bytes/)
Erfahren Sie, wie Sie Daten im DataMatrix‑Format im Bytes‑Modus mit Aspose.BarCode für .NET codieren. Folgen Sie unserer Schritt‑für‑Schritt‑Anleitung zur Barcode‑Generierung und -Erkennung.
### [Master DataMatrix Encoding Mode (C40)](./datamatrix-encoding-mode-c40/)
Lernen Sie den DataMatrix‑Codierungsmodus (C40) mit Aspose.BarCode für .NET kennen. Erstellen Sie benutzerdefinierte Barcodes effizient. Entdecken Sie die Schritt‑für‑Schritt‑Anleitung.
### [Configuring DataMatrix Code Text](./datamatrix-extended-code-text-configuration/)
Erfahren Sie, wie Sie den erweiterten DataMatrix‑Code‑Text mit Aspose.BarCode für .NET konfigurieren. Generieren, erkennen und integrieren Sie Barcodes in Ihren .NET‑Anwendungen.
### [Master DataMatrix Macro Configuration](./datamatrix-macro-configuration/)
Erfahren Sie, wie Sie DataMatrix‑Macro‑Barcodes mit Aspose.BarCode für .NET konfigurieren. Generieren, anpassen und erkennen Sie DataMatrix‑Barcodes in Ihren .NET‑Anwendungen.

## Häufig gestellte Fragen

**Q: Wie entscheide ich, welchen ECC‑Modus ich verwenden soll?**  
**A:** Wählen Sie ECC 000‑140 für kleine Datensätze mit begrenzter Fehlerkorrektur oder ECC 200 für größere Daten und höhere Zuverlässigkeit. Der Makro‑Modus fügt eine zusätzliche Datenschicht zum Verlinken hinzu.

**Q: Kann ich benutzerdefinierten Text in einen DataMatrix‑Barcode einbetten?**  
**A:** Ja, setzen Sie die `CodeText`‑Eigenschaft auf Ihre benutzerdefinierte Zeichenkette und wählen Sie dann den passenden Codierungsmodus (ASCII, C40 usw.), um die Größe zu steuern.

**Q: Gibt es eine Möglichkeit, den besten Codierungsmodus automatisch auszuwählen?**  
**A:** Setzen Sie `EncodeMode` auf `Auto`; Aspose.BarCode bewertet die Nutzdaten und wählt automatisch den platzsparendsten Modus aus.

**Q: Was sind die Leistungsüberlegungen bei großen Barcode‑Chargen?**  
**A:** Verwenden Sie eine einzige `BarCodeGenerator`‑Instanz, aktivieren Sie Multithreading und erzeugen Sie PNG‑Bilder für verlustfreie Qualität oder JPEG für kleinere Dateigrößen. Die Verarbeitung von 10 000 Symbolen dauert typischerweise weniger als 30 Sekunden auf einem Standard‑8‑Kern‑Server.

**Q: Unterstützt Aspose.BarCode .NET Core und .NET 5/6?**  
**A:** Absolut – die Bibliothek ist vollständig kompatibel mit .NET Framework, .NET Core und den neuesten .NET‑Versionen und bietet denselben Funktionsumfang auf allen Plattformen.

**Zuletzt aktualisiert:** 2026-06-09  
**Getestet mit:** Aspose.BarCode 24.12 für .NET  
**Autor:** Aspose

## Verwandte Tutorials

- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Master DataMatrix Encoding in ASCII with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
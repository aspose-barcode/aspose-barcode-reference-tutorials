---
date: 2025-12-27
description: Erfahren Sie, wie Sie einen DataMatrix‑Barcode erstellen und den Textstandort
  des Barcodes in Java mit Aspose.BarCode festlegen. Folgen Sie unserer Schritt‑für‑Schritt‑Anleitung
  für vollständige Anpassungen.
linktitle: Setting Code Text Location
second_title: Aspose.BarCode Java API
title: Data-Matrix-Barcode erstellen und Code‑Textposition in Java festlegen
url: /de/java/text-and-styling/setting-code-text-location/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Data Matrix Barcode erstellen und Code‑Text‑Position in Java festlegen

## Einführung

Das Erzeugen von Barcodes ist eine routinemäßige Anforderung für Inventar, Versand und viele andere Java‑basierte Anwendungen. Mit **Aspose.BarCode for Java** können Sie **Data Matrix Barcodes** schnell erstellen und jedes visuelle Detail steuern, einschließlich der Position des menschenlesbaren Textes. In diesem Tutorial führen wir Sie Schritt für Schritt durch das **Erstellen eines Data Matrix Barcodes** und zeigen **wie Sie den Barcode‑Text** über dem Symbol platzieren, sodass er Ihren Design‑Spezifikationen entspricht.

## Kurzantworten
- **Welche Bibliothek wird verwendet?** Aspose.BarCode for Java  
- **Welcher Barcode‑Typ wird demonstriert?** Data Matrix  
- **Wie positionieren Sie den Code‑Text?** Mit `CodeLocation.ABOVE`  
- **Benötigen Sie eine Lizenz für die Produktion?** Ja, eine kommerzielle Lizenz ist erforderlich  
- **Kann der Code unter Java 8+ ausgeführt werden?** Absolut, er unterstützt Java 8 und spätere Versionen  

## Was ist ein Data Matrix Barcode?
Ein Data Matrix Barcode ist ein zweidimensionales (2‑D) Symbol, das große Datenmengen in einem kompakten quadratischen oder rechteckigen Muster speichert. Er wird häufig zum Kennzeichnen kleiner Artikel, Elektronik und medizinischer Geräte verwendet, weil er bis zu 2 335 alphanumerische Zeichen codieren kann.

## Warum die Position des Barcode‑Textes festlegen?
Den menschenlesbaren Text **über**, **unter** oder **neben** dem Barcode zu platzieren, ermöglicht es Benutzern, die codierten Daten schnell zu überprüfen, ohne zu scannen. Das Anpassen der Textposition verbessert die UI‑Konsistenz und erfüllt Markenrichtlinien.

## Voraussetzungen

- Grundkenntnisse in Java‑Programmierung.  
- Java Development Kit (JDK) installiert.  
- Eine IDE wie Eclipse oder IntelliJ IDEA.  
- Aspose.BarCode for Java Bibliothek (herunterladen von [here](https://releases.aspose.com/barcode/java/)).  

## Pakete importieren

Zuerst importieren Sie die wesentlichen Aspose.BarCode‑Klassen in Ihr Projekt:

```java
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.generation.BarcodeGenerator;
```

Diese Importe geben Ihnen Zugriff auf den Barcode‑Generator und die Aufzählung, die die Textplatzierung steuert.

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Verzeichnispfade festlegen
Geben Sie an, wo Sie Dateien lesen/schreiben möchten. Ersetzen Sie die Platzhalter durch tatsächliche Pfade auf Ihrem Rechner.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

### Schritt 2: Eine BarcodeGenerator‑Instanz erstellen
Instanziieren Sie `BarcodeGenerator` mit dem **Data Matrix**‑Typ und übergeben Sie den Code‑Text, den Sie codieren möchten.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DATA_MATRIX,
        "GTIN:898978777776665655 " + "UID: 121212121212121212 " + "Batch:GH768 " + "Exp.Date:150923");
```

### Schritt 3: Wie man die Position des Barcode‑Textes festlegt
Verwenden Sie die Aufzählung `CodeLocation`, um den menschenlesbaren Text zu verschieben. In diesem Beispiel platzieren wir ihn **über** dem Barcode.

```java
generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.ABOVE);
```

### Schritt 4: Das generierte Barcode‑Bild speichern
Schreiben Sie schließlich das Barcode‑Bild auf die Festplatte. Die Datei enthält das Data Matrix‑Symbol mit dem Text, der darüber positioniert ist.

```java
generator.save(dataDir + "codetextAbove.png");
```

## Häufige Probleme und Lösungen
- **Text wird nicht angezeigt:** Stellen Sie sicher, dass Sie eine Version von Aspose.BarCode verwenden, die `CodeLocation` unterstützt.  
- **Dateipfad‑Fehler:** Überprüfen Sie, dass `dataDir` mit einem Dateiseparator (`/` oder `\\`) endet, der für Ihr Betriebssystem geeignet ist.  
- **Nicht unterstützte Zeichen:** Data Matrix kann nur einen begrenzten Zeichensatz kodieren; vermeiden Sie Sonderzeichen, die nicht im ISO/IEC 16022‑Standard enthalten sind.

## Häufig gestellte Fragen (FAQs)

### Q: Kann ich das Aussehen des generierten Barcodes anpassen?
A: Ja, Aspose.BarCode bietet umfangreiche Anpassungsoptionen, mit denen Sie Farben, Ränder und Schriftstile steuern können.

### Q: Ist Aspose.BarCode mit Java 8 und späteren Versionen kompatibel?
A: Ja, die Bibliothek funktioniert mit Java 8 und allen nachfolgenden Versionen.

### Q: Wie kann ich Aspose.BarCode in mein bestehendes Java‑Projekt integrieren?
A: Fügen Sie die Aspose.BarCode‑JAR‑Dateien zum Klassenpfad Ihres Projekts hinzu, importieren Sie die erforderlichen Pakete, und Sie können Barcodes erzeugen.

### Q: Gibt es eine Testversion von Aspose.BarCode?
A: Ja, Sie können die Funktionen von Aspose.BarCode mit einer kostenlosen Testversion [here](https://releases.aspose.com/) erkunden.

### Q: Wo kann ich Hilfe oder Support für Aspose.BarCode erhalten?
A: Besuchen Sie das [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) für Community‑Unterstützung und offiziellen Support.

## Zusätzliche häufig gestellte Fragen

**Q: Kann ich einen Barcode mit Text unterhalb des Symbols erzeugen?**  
A: Ja, setzen Sie `CodeLocation.BELOW` in derselben `setLocation`‑Methode.

**Q: Unterstützt die Bibliothek andere 2‑D‑Barcodes wie QR‑Code?**  
A: Ja, ändern Sie einfach `EncodeTypes.DATA_MATRIX` zu `EncodeTypes.QR`.

**Q: Wie ändere ich die Schriftgröße des Barcode‑Textes?**  
A: Verwenden Sie `generator.getParameters().getBarcode().getCodeTextParameters().setFontSize(double size)`.

## Fazit

Sie haben nun gelernt, wie Sie **Data Matrix Barcodes** in Java erstellen und die **Position des Barcode‑Textes** mithilfe von Aspose.BarCode präzise festlegen. Experimentieren Sie mit anderen `CodeLocation`‑Werten und Stiloptionen, um die Design‑Anforderungen Ihrer Anwendung zu erfüllen.

---

**Last Updated:** 2025-12-27  
**Tested With:** Aspose.BarCode for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
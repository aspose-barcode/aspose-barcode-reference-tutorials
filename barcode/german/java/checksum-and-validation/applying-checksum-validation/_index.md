---
date: 2025-12-19
description: Erfahren Sie, wie Sie die Prüfsummenvalidierung in Java mit Aspose.BarCode
  deaktivieren. Diese Schritt‑für‑Schritt‑Anleitung zeigt Ihnen, wie Sie Barcodes
  lesen, die Prüfsumme ausschalten und eine zuverlässige Datenverarbeitung sicherstellen.
linktitle: How to Disable Checksum Validation
second_title: Aspose.BarCode Java API
title: Wie man die Prüfsummenvalidierung in Java deaktiviert
url: /de/java/checksum-and-validation/applying-checksum-validation/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man die Prüfsummenvalidierung in Java deaktiviert

In modernen Inventar‑ und Logistikanwendungen kann **wie man die Prüfsumme deaktiviert** der Schlüssel sein, um alte Barcodes zu lesen, die keine Prüfziffer enthalten. Aspose.BarCode für Java ermöglicht es, die Prüfsummenvalidierung mühelos auszuschalten und dennoch die codierten Daten zu extrahieren. Dieses Tutorial führt Sie durch den gesamten Prozess – von der Projekt‑Einrichtung bis zum Lesen eines ONE‑CODE‑Barcodes ohne Prüfsummenprüfung.

## Schnelle Antworten
- **Was bewirkt das Deaktivieren der Prüfsumme?** Es weist den Leser an, das Prüfsummenfeld zu ignorieren, sodass Barcodes ohne gültige Prüfziffer verarbeitet werden können.  
- **Wann sollten Sie die Prüfsumme deaktivieren?** Wenn Sie mit Altsystemen oder nicht‑standardisierten Barcodes arbeiten, die die Prüfziffer weglassen oder beschädigen.  
- **Welche Klasse steuert die Prüfsummenvalidierung?** `BarCodeReader.setChecksumValidation(ChecksumValidation)`  
- **Ist das Deaktivieren der Prüfsumme sicher?** Nur wenn Sie der Quelle des Barcodes vertrauen; andernfalls hilft die Validierung, Fehler zu erkennen.  
- **Beeinflusst das andere Barcode‑Typen?** Die Einstellung gilt nur für die aktuelle `BarCodeReader`‑Instanz.

## Was ist Prüfsummenvalidierung?
Die Prüfsummenvalidierung ist ein Datenintegritäts‑Check, der aus dem Barcode‑Inhalt einen kleinen Wert berechnet und diesen mit der eingebetteten Prüfziffer vergleicht. Stimmen sie nicht überein, gilt der Barcode als nicht lesbar. Das Deaktivieren dieses Checks weist Aspose.BarCode an, den Vergleich zu überspringen.

## Warum die Prüfsumme mit Aspose.BarCode deaktivieren?
- **Legacy‑Unterstützung:** Ältere Scanner erzeugten häufig Barcodes ohne Prüfsummen.  
- **Performance:** Das Überspringen der Berechnung kann das Einlesen großer Datenmengen beschleunigen.  
- **Flexibilität:** Sie können pro Leser‑Instanz entscheiden, ob die Validierung erzwungen wird.

## Voraussetzungen
- **Java Development Kit (JDK):** Stellen Sie sicher, dass das neueste JDK installiert ist.  
- **Aspose.BarCode Bibliothek:** Laden Sie die Bibliothek von der offiziellen Seite [here](https://releases.aspose.com/barcode/java/) herunter.  

## Pakete importieren
Importieren Sie in Ihrem Java‑Projekt die notwendigen Aspose.BarCode‑Klassen, um Barcode‑Erkennung zu nutzen.

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.ChecksumValidation;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Projekt einrichten
Erstellen Sie ein neues Java‑Projekt (IDE Ihrer Wahl) und fügen Sie die Aspose.BarCode‑JAR zum Klassenpfad des Projekts hinzu.

### Schritt 2: `BarCodeReader` initialisieren
Laden Sie das Bild, das den ONE‑CODE‑Barcode enthält, den Sie lesen möchten.

```java
String dataDir = "Your Document Directory";
BarCodeReader reader = new BarCodeReader(dataDir + "onecode.png", DecodeType.ONE_CODE);
```

### Schritt 3: Wie man die Prüfsumme deaktiviert
Weisen Sie den Leser an, die Prüfsummenvalidierung zu ignorieren, indem Sie die Eigenschaft auf `OFF` setzen.

```java
reader.setChecksumValidation(ChecksumValidation.OFF);
```

### Schritt 4: Barcodes lesen
Iterieren Sie über die Ergebnisse und geben Sie den dekodierten Text sowie den Symbologie‑Typ aus.

```java
for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("CodeText: " + result.getCodeText());
    System.out.println("Symbology type: " + result.getCodeType());
}
```

**Ergebnis:** Der Barcode‑Text wird angezeigt, selbst wenn das Originalbild keine gültige Prüfziffer enthält.

## Häufige Probleme & Tipps
- **Falscher Dateipfad:** Vergewissern Sie sich, dass `dataDir` auf das richtige Verzeichnis zeigt; verwenden Sie für Tests absolute Pfade.  
- **Nicht unterstützter Barcode‑Typ:** Stellen Sie sicher, dass `DecodeType` dem Barcode entspricht, den Sie lesen wollen.  
- **Performance:** Das Deaktivieren der Prüfsumme bei großen Stapeln kann den Durchsatz erhöhen, aktivieren Sie sie jedoch für kritische Daten wieder.

## Häufig gestellte Fragen

### Ist Aspose.BarCode mit verschiedenen Barcode‑Typen kompatibel?
Ja, Aspose.BarCode unterstützt ein breites Spektrum an Barcode‑Symbologien, von QR und DataMatrix bis zu traditionellen linearen Codes.

### Kann ich Aspose.BarCode für kommerzielle Zwecke nutzen?
Absolut. Kommerzielle Lizenzen stehen Unternehmen zur Verfügung, die produktionsreife Funktionen benötigen.

### Wie erhalte ich Support für Aspose.BarCode?
Besuchen Sie das [Aspose.BarCode‑Forum](https://forum.aspose.com/c/barcode/13), um mit der Community in Kontakt zu treten und Unterstützung vom Produktteam zu erhalten.

### Gibt es eine kostenlose Testversion?
Ja, Sie können das komplette Funktionsspektrum erkunden, indem Sie die [free trial](https://releases.aspose.com/) herunterladen.

### Wo finde ich ausführliche Dokumentation?
Siehe die umfassende [documentation](https://reference.aspose.com/barcode/java/) für API‑Details, Code‑Beispiele und bewährte Verfahren.

---

**Zuletzt aktualisiert:** 2025-12-19  
**Getestet mit:** Aspose.BarCode für Java (neueste Version)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
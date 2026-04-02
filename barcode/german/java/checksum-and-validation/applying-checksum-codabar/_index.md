---
date: 2025-12-18
description: Erfahren Sie, wie Sie ein Codabar-Barcode-Bild erstellen und ein Java-Barcode-Leser‑Beispiel
  mit Aspose.BarCode ansehen. Generieren und erkennen Sie Barcodes mühelos mit dieser
  Schritt‑für‑Schritt‑Anleitung.
linktitle: Applying Checksum for CodaBar
second_title: Aspose.BarCode Java API
title: Wie man ein Codabar-Barcode‑Bild mit Prüfsumme in Java erstellt
url: /de/java/checksum-and-validation/applying-checksum-codabar/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man ein Codabar‑Barcode‑Bild mit Prüfsumme in Java erstellt

## Einführung

In diesem Tutorial lernen Sie, wie Sie **ein Codabar‑Barcode‑Bild** mit Prüfsumme in Java mithilfe von Aspose.BarCode erstellen. Wir führen Sie durch die Erzeugung eines CodaBar‑Barcodes, das Aktivieren der Prüfsumme und das anschließende Auslesen mit einem **java barcode reader example**. Am Ende haben Sie einen einsatzbereiten Code‑Snippet, den Sie in jedes Java‑Projekt einbinden können.

## Schnellantworten
- **Was bewirkt die Prüfsumme?** Sie validiert die Integrität der Barcode‑Daten während des Scannens.  
- **Welche Bibliothek wird benötigt?** Aspose.BarCode für Java.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine temporäre Lizenz reicht für Tests; für die Produktion ist eine Voll‑Lizenz erforderlich.  
- **Kann ich das Aussehen des Barcodes anpassen?** Ja – Farbe, Größe und Schrift können über Generator‑Parameter geändert werden.  
- **Ist das mit allen Java‑Versionen kompatibel?** Die Bibliothek unterstützt Java 8 und neuer.

## Was ist ein CodaBar‑Barcode?

CodaBar ist eine lineare (1‑dimensionale) Symbologie, die häufig in Bibliotheken, Blutbanken und im Einzelhandel verwendet wird. Sie codiert numerische Daten und einige Sonderzeichen, was sie ideal für einfache, maschinenlesbare Etiketten macht. Das Hinzufügen einer Prüfsumme (Mod 10) erhöht die Lesegenauigkeit, insbesondere bei Druck von geringer Qualität.

## Warum Aspose.BarCode für Java verwenden?

Aspose.BarCode bietet ein **java barcode reader example**, das die Low‑Level‑Details der Barcode‑Erzeugung und -Erkennung abstrahiert. Es liefert:

* Vollständige Kontrolle über Prüfsummen‑Modi.  
* Nahtlose Integration in Java‑IDEs.  
* Umfangreiche Dokumentation und Support.  

## Voraussetzungen

Bevor wir starten, stellen Sie sicher, dass Sie Folgendes haben:

- Java Development Kit (JDK) auf Ihrem Rechner installiert.  
- Aspose.BarCode für Java Bibliothek. Sie können sie von [hier](https://releases.aspose.com/barcode/java/) herunterladen.  
- Grundlegende Kenntnisse in Java‑Programmierung.  

## Pakete importieren

Importieren Sie in Ihrem Java‑Projekt die notwendigen Klassen, um mit Aspose.BarCode zu arbeiten:

```java
import java.io.IOException;

import com.aspose.barcode.CodabarChecksumMode;
import com.aspose.barcode.EnableChecksum;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.ChecksumValidation;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Schritt‑für‑Schritt‑Anleitung

### Schritt 1: Umgebung einrichten

Erstellen Sie ein neues Java‑Projekt und fügen Sie die Aspose.BarCode‑JAR zu Ihrem Build‑Path hinzu. Definieren Sie einen Ordner, in dem die erzeugten Bilder gespeichert werden.

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

### Schritt 2: CodaBar‑Barcode‑Bild mit Prüfsumme erzeugen

Instanziieren Sie den `BarcodeGenerator`, aktivieren Sie die Prüfsumme, wählen Sie den Mod 10‑Modus und speichern Sie das Bild.

```java
// Instantiate BarcodeGenerator object
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "1234567890");

// Set the EnableChecksum property to yes
generator.getParameters().getBarcode().setChecksumEnabled(EnableChecksum.YES);

// Set the CodabarChecksumMode
generator.getParameters().getBarcode().getCodabar().setCodabarChecksumMode(CodabarChecksumMode.MOD_10);

// Save the image on the system
generator.save(dataDir + "Codabar_Mod10.png");
```

### Schritt 3: Java barcode reader example – Barcode erkennen

Lesen Sie nun den Barcode ein und aktivieren Sie die Prüfsummen‑Validierung, um sicherzustellen, dass die Daten korrekt sind.

```java
// Initialize reader object
BarCodeReader reader = new BarCodeReader(dataDir + "Codabar_Mod10.png", DecodeType.CODABAR);

// Set ChecksumValidation property of the reader to On
reader.setChecksumValidation(ChecksumValidation.ON);

for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("CodeText: " + result.getCodeText());
    System.out.println("Symbology type: " + result.getCodeType());

    // Get checksum value
    System.out.println("Checksum:" + result.getExtended().getOneD().getCheckSum());
}
```

Beim Ausführen des Codes werden der dekodierte Text, der Symbologie‑Typ und die berechnete Prüfsumme ausgegeben, was bestätigt, dass der Barcode korrekt erzeugt und validiert wurde.

## Häufige Probleme und Lösungen

| Problem | Lösung |
|-------|----------|
| **Prüfsummen‑Validierung schlägt fehl** | Stellen Sie sicher, dass `EnableChecksum` auf `YES` gesetzt ist und dass `CodabarChecksumMode` dem beim Erzeugen verwendeten Modus (Mod 10) entspricht. |
| **Datei‑nicht‑gefunden‑Fehler** | Vergewissern Sie sich, dass `dataDir` auf einen existierenden Ordner zeigt und dass das erzeugte Bild (`Codabar_Mod10.png`) dort gespeichert wurde, bevor es gelesen wird. |
| **Nicht unterstützte Java‑Version** | Verwenden Sie Java 8 oder neuer; ältere Versionen besitzen möglicherweise nicht die erforderlichen APIs. |

## Häufig gestellte Fragen

**F: Ist Aspose.BarCode mit allen Java‑Versionen kompatibel?**  
A: Aspose.BarCode ist für Java 8 und neuer ausgelegt. Prüfen Sie die offizielle Dokumentation für detaillierte Kompatibilitätsinformationen.

**F: Kann ich das Aussehen des erzeugten Barcodes anpassen?**  
A: Ja, Sie können Farben, Schriftarten und das Bildformat über die Parameter‑API des Generators ändern.

**F: Gibt es temporäre Lizenzen für Testzwecke?**  
A: Ja, Sie können eine temporäre Lizenz für Aspose.BarCode von [hier](https://purchase.aspose.com/temporary-license/) erhalten.

**F: Wo finde ich zusätzlichen Support und Ressourcen?**  
A: Besuchen Sie das [Aspose.BarCode‑Forum](https://forum.aspose.com/c/barcode/13) für Community‑Support und Diskussionen.

**F: Gibt es eine kostenlose Testversion?**  
A: Ja, Sie können die Funktionen von Aspose.BarCode testen, indem Sie die kostenlose Testversion von [hier](https://releases.aspose.com/) herunterladen.

---

**Zuletzt aktualisiert:** 2025-12-18  
**Getestet mit:** Aspose.BarCode für Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
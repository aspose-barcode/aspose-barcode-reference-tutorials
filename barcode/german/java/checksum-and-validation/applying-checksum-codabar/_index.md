---
date: 2026-04-05
description: Lernen Sie, wie Sie ein Codabar‑Barcode‑Java‑Bild mit Prüfsumme erstellen,
  und sehen Sie ein Beispiel für einen Java‑Barcode‑Reader mit Aspose.BarCode. Folgen
  Sie dieser Schritt‑für‑Schritt‑Anleitung, um Barcodes zu erzeugen und zu erkennen.
keywords:
- create codabar barcode java
- java barcode reader example
- codabar checksum
- aspose barcode java
linktitle: Anwenden der Prüfsumme für CodaBar
second_title: Aspose.BarCode Java API
title: Wie man ein Codabar‑Barcode‑Java‑Bild mit Prüfsumme erstellt
url: /de/java/checksum-and-validation/applying-checksum-codabar/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wie man ein Codabar-Barcode-Java-Bild mit Prüfsumme erstellt

## Einführung

In diesem Tutorial **erstellen Sie Codabar-Barcode-Java**-Bilder mit einer Mod 10‑Prüfsumme mithilfe von Aspose.BarCode für Java. Wir führen Sie durch die Erzeugung eines CodaBar‑Barcodes, das Aktivieren der Prüfsumme und anschließend die Validierung mit einem **java barcode reader example**. Am Ende haben Sie ein einsatzbereites Snippet, das Sie in jedes Java‑Projekt einbinden können, egal ob Sie ein Bibliothekssystem, einen medizin‑Laboretikettendrucker oder eine Einzelhandels‑Kasselösung bauen.

## Schnelle Antworten
- **Was macht die Prüfsumme?** Sie überprüft die Integrität der Barcode‑Daten beim Scannen.  
- **Welche Bibliothek wird benötigt?** Aspose.BarCode für Java.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine temporäre Lizenz funktioniert für Tests; für die Produktion ist eine Voll‑Lizenz erforderlich.  
- **Kann ich das Aussehen des Barcodes anpassen?** Ja – Farbe, Größe und Schriftart können über Generator‑Parameter geändert werden.  
- **Ist dies mit allen Java‑Versionen kompatibel?** Die Bibliothek unterstützt Java 8 und neuer.

## Wie man Codabar-Barcode in Java erstellt

Im Folgenden finden Sie eine prägnante, Schritt‑für‑Schritt‑Anleitung, die erklärt, **warum jede Zeile wichtig ist**, sodass Sie den Code mit Vertrauen an Ihre eigenen Projekte anpassen können.

### Was ist ein CodaBar-Barcode?

CodaBar ist eine lineare (1‑dimensionale) Symbolik, die in Bibliotheken, Blutbanken und im Einzelhandel weit verbreitet ist. Sie codiert numerische Daten und einige Sonderzeichen und ist damit ideal für einfache, maschinenlesbare Etiketten. Das Hinzufügen einer Prüfsumme (Mod 10) verbessert die Lesegenauigkeit, insbesondere bei Druck von geringer Qualität.

### Warum Aspose.BarCode für Java verwenden?

Aspose.BarCode bietet ein **java barcode reader example**, das low‑level Details der Barcode‑Erzeugung und -Erkennung abstrahiert. Es bietet:

* Vollständige Kontrolle über Prüfsummenmodi.  
* Nahtlose Integration in Java‑IDEs.  
* Umfassende Dokumentation und schnellen Support.  

### Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie folgendes haben:

- Java Development Kit (JDK) 8 oder neuer installiert.  
- Aspose.BarCode für Java Bibliothek. Sie können sie von [here](https://releases.aspose.com/barcode/java/) herunterladen.  
- Grundlegende Kenntnisse der Java‑Programmierung.  

### Pakete importieren

In Ihrem Java‑Projekt importieren Sie die notwendigen Klassen, um mit Aspose.BarCode zu arbeiten:

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

### Schritt‑für‑Schritt‑Anleitung

#### Schritt 1: Umgebung einrichten

Erstellen Sie ein neues Java‑Projekt und fügen Sie die Aspose.BarCode‑JAR zu Ihrem Build‑Pfad hinzu. Definieren Sie einen Ordner, in dem die erzeugten Bilder gespeichert werden.

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

#### Schritt 2: CodaBar-Barcode-Bild mit Prüfsumme erzeugen

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

#### Schritt 3: Java-Barcode-Leser‑Beispiel – Barcode erkennen

Lesen Sie nun den Barcode ein, aktivieren Sie die Prüfsummenvalidierung, um sicherzustellen, dass die Daten korrekt sind.

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

Beim Ausführen des Codes werden der dekodierte Text, der Symboltyp und die berechnete Prüfsumme ausgegeben, was bestätigt, dass der Barcode korrekt erzeugt und validiert wurde.

### Häufige Anwendungsfälle

- **Bibliotheksverwaltung:** Buch‑IDs für schnelles Scannen an der Kasse codieren.  
- **Blutbank‑Etiketten:** Sicherstellen einer genauen Patientenidentifikation mit Prüfsummen‑Schutz.  
- **Einzelhandels‑Regal‑Etiketten:** Günstige, schnell gedruckte Barcodes für die Bestandsverfolgung.  

### Häufige Probleme und Lösungen

| Problem | Lösung |
|-------|----------|
| **Prüfsummenvalidierung schlägt fehl** | Überprüfen Sie, dass `EnableChecksum` auf `YES` gesetzt ist und dass `CodabarChecksumMode` dem bei der Erzeugung verwendeten Modus (Mod 10) entspricht. |
| **Datei‑nicht‑gefunden‑Fehler** | Stellen Sie sicher, dass `dataDir` auf einen vorhandenen Ordner verweist und dass das erzeugte Bild (`Codabar_Mod10.png`) dort gespeichert ist, bevor es gelesen wird. |
| **Nicht unterstützte Java‑Version** | Verwenden Sie Java 8 oder neuer; ältere Versionen könnten die erforderlichen APIs nicht besitzen. |

## Häufig gestellte Fragen

**Q: Ist Aspose.BarCode mit allen Java-Versionen kompatibel?**  
A: Aspose.BarCode ist für Java 8 und neuer konzipiert. Weitere Details zur Kompatibilität finden Sie in der offiziellen Dokumentation.

**Q: Kann ich das Aussehen des erzeugten Barcodes anpassen?**  
A: Ja, Sie können Farben, Schriftarten und das Bildformat über die Parameter‑API des Generators ändern.

**Q: Sind temporäre Lizenzen für Testzwecke verfügbar?**  
A: Ja, Sie können eine temporäre Lizenz für Aspose.BarCode von [here](https://purchase.aspose.com/temporary-license/) erhalten.

**Q: Wo finde ich zusätzliche Unterstützung und Ressourcen?**  
A: Besuchen Sie das [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) für Community‑Support und Diskussionen.

**Q: Gibt es eine kostenlose Testversion?**  
A: Ja, Sie können die Funktionen von Aspose.BarCode testen, indem Sie die kostenlose Testversion von [here](https://releases.aspose.com/) herunterladen.

---

**Last Updated:** 2026-04-05  
**Tested With:** Aspose.BarCode for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
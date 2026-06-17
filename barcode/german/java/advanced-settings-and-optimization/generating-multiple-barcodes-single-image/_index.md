---
date: 2026-04-03
description: Erfahren Sie, wie Sie QR‑Codes in Java erstellen und mehrere Barcodes
  auf einem einzigen Bild mit Aspose.BarCode für Java generieren. Enthält Einrichtung,
  Code und Fehlersuche.
keywords:
- create qr code java
- aspose barcode java
- generate barcodes java
linktitle: Mehrere Barcodes auf einem einzigen Bild generieren
second_title: Aspose.BarCode Java API
title: QR-Code in Java erstellen – Mehrere Barcodes auf einem Bild generieren
url: /de/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# QR-Code in Java erstellen – Mehrere Barcodes auf einem Bild generieren

## Einführung

In diesem Tutorial lernen Sie **wie man QR-Code in Java erstellt** und mehrere verschiedene Barcode‑Typen zu einem einzigen Bild kombiniert, wobei **Aspose.BarCode for Java** verwendet wird. Egal, ob Sie ein kompaktes QR‑Etikett, einen Produkt‑Barcode oder eine Mischung aus 2‑D‑ und linearen Symbolen benötigen, führt Sie diese Anleitung durch jeden Schritt – von der Projektkonfiguration bis zum Speichern des finalen kombinierten Bildes – sodass Sie die Barcode‑Erzeugung sofort in Ihre Java‑Anwendungen integrieren können.

## Schnelle Antworten
- **Welche Bibliothek sollte ich verwenden?** Aspose.BarCode for Java bietet das vollständigste Set an Symbolen.  
- **Kann ich verschiedene Barcode‑Typen zusammen erzeugen?** Ja, Sie können CODE_39, QR, AZTEC und weitere auf einer einzigen Zeichenfläche mischen.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion reicht für Tests; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Welche Java‑Version wird unterstützt?** Java 8 und neuer sind vollständig kompatibel.  
- **Ist das Ausgabeformat konfigurierbar?** Sie können das kombinierte Bild als PNG, JPEG, BMP usw. exportieren.  

## Was ist das Erstellen von QR-Code in Java?

Das Erstellen eines QR‑Codes in Java bedeutet, einen Textstring in eine zweidimensionale Matrix zu konvertieren, die von Smartphones oder Barcode‑Lesern gescannt werden kann. **Aspose.BarCode for Java** übernimmt die Kodierung und das Rendering, sodass Sie sich auf die Geschäftslogik statt auf die low‑level Bildverarbeitung konzentrieren können.

## Warum Aspose.BarCode Java für das Erzeugen von Barcodes in Java verwenden?

- **Breite Symbolunterstützung** – von klassischen linearen Codes bis zu modernen 2‑D‑Matrizen.  
- **Hochwertiges Rendering** – antialiasierte Ausgabe, die auf jedem Gerät funktioniert.  
- **Einfache API** – Barcodes erstellen, anpassen und kombinieren mit nur wenigen Methodenaufrufen.  
- **Keine externen Abhängigkeiten** – alles läuft auf der JVM ohne native Bibliotheken.  

## Voraussetzungen

Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Grundlegendes Verständnis der Java‑Programmierung.  
- Java Development Kit (JDK) auf Ihrem System installiert.  
- Aspose.BarCode for Java‑Bibliothek heruntergeladen und eingerichtet. Sie können sie [here](https://releases.aspose.com/barcode/java/) herunterladen.  
- Eine integrierte Entwicklungsumgebung (IDE) wie Eclipse oder IntelliJ IDEA.

## Namespaces importieren

Importieren Sie in Ihrem Java‑Projekt die notwendigen Namespaces, um auf die Aspose.BarCode‑Funktionalität zuzugreifen. Fügen Sie die folgenden Import‑Anweisungen am Anfang Ihrer Java‑Klasse hinzu:

```java
import java.awt.Color;
import java.awt.Graphics;
import java.awt.image.BufferedImage;
import java.io.File;
import java.util.ArrayList;
import java.util.HashMap;

import javax.imageio.ImageIO;

import com.aspose.barcode.BaseEncodeType;
import com.aspose.barcode.EncodeTypes;


import com.aspose.barcode.generation.BarcodeGenerator;
```

## Schritt 1: Ressourcenverzeichnis festlegen

Definieren Sie den Pfad zum Ressourcenverzeichnis, in dem die erzeugten Barcodes gespeichert werden. Dieses Verzeichnis ist wichtig für die Organisation und Verwaltung Ihrer Barcode‑Bilder.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Schritt 2: Sammlung von Barcodes erstellen

Initialisieren Sie ein `HashMap`, um die Barcode‑Daten zu speichern. Jeder Eintrag in der Sammlung repräsentiert einen Barcode mit seinem jeweiligen Kodierungstyp.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Schritt 3: Barcode‑Bilder generieren

Iterieren Sie über die Sammlung und erzeugen Sie Barcode‑Bilder mithilfe der Aspose.BarCode‑Bibliothek. Speichern Sie die Bilder in einer `ArrayList` für die weitere Verarbeitung.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Schritt 4: Kombiniertes Bild erstellen

Bestimmen Sie die maximale Breite und die Gesamthöhe der Barcode‑Bilder. Erzeugen Sie ein `BufferedImage`, um die einzelnen Barcode‑Bilder zu einem einzigen Ausgabebild zu kombinieren.

```java
int maxWidth = 0;
int sumHeight = 0;
for (BufferedImage bmp : images) {
    sumHeight += bmp.getHeight();
    if (maxWidth < bmp.getWidth())
        maxWidth = bmp.getWidth();
}

int offset = 10;
BufferedImage resultBitmap = new BufferedImage(maxWidth + offset * 2, sumHeight + offset * images.size(),
        BufferedImage.TYPE_INT_ARGB);
Graphics g = resultBitmap.getGraphics();
g.setColor(Color.white);
g.fillRect(0, 0, resultBitmap.getWidth(), resultBitmap.getHeight());

int yPosition = offset;
for (int i = 0; i < images.size(); ++i) {
    BufferedImage currentBitmap = images.get(i);
    g.drawImage(currentBitmap, offset, yPosition, null);
    yPosition += currentBitmap.getHeight() + offset;
}
```

## Schritt 5: Ergebnis speichern

Speichern Sie das finale kombinierte Bild an einem angegebenen Dateipfad.

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Häufige Anwendungsfälle für das Generieren mehrerer Barcodes

- **Verpackungsetiketten** – Produkt‑, Chargen‑ und Versandcodes auf einem einzigen Etikett kombinieren.  
- **Event‑Tickets** – QR, Data Matrix und Code 128‑Identifikatoren für verschiedene Scan‑Stationen einbetten.  
- **Inventarverwaltung** – SKU, RFID‑Tag‑Daten und Seriennummern zusammen anzeigen für schnelle Audits.

## Fehlersuche & Tipps

- **Probleme mit Bildgrößen** – passen Sie die Variable `offset` an, um den Abstand zwischen den Barcodes zu vergrößern oder zu verkleinern.  
- **Nicht unterstützte Symbole** – prüfen Sie, ob Ihre Aspose.BarCode‑Version den gewünschten Barcode‑Typ unterstützt.  
- **Performance** – verwenden Sie ein einzelnes `Graphics`‑Objekt wieder, wenn Sie viele Bilder in einer Schleife erzeugen.

## Häufig gestellte Fragen

**Q1: Kann ich das Aussehen einzelner Barcodes im erzeugten Bild anpassen?**  
A1: Ja, Aspose.BarCode bietet umfangreiche Anpassungsoptionen für das Erscheinungsbild von Barcodes, sodass Sie den Stil jedes Barcodes nach Ihren Wünschen gestalten können.

**Q2: Ist Aspose.BarCode mit verschiedenen Barcode‑Symbolen kompatibel?**  
A2: Absolut! Aspose.BarCode unterstützt eine breite Palette von Symbolen, darunter CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 und AZTEC, wie in diesem Tutorial demonstriert.

**Q3: Wie integriere ich Aspose.BarCode in mein Java‑Projekt?**  
A3: Laden Sie einfach die Aspose.BarCode for Java‑Bibliothek von [here](https://releases.aspose.com/barcode/java/) herunter und folgen Sie den Installationsanweisungen in der Dokumentation.

**Q4: Kann ich Aspose.BarCode für kommerzielle Anwendungen nutzen?**  
A4: Ja, Sie können eine Lizenz von [here](https://purchase.aspose.com/buy) erwerben, um Aspose.BarCode kommerziell zu verwenden.

**Q5: Gibt es Testversionen für Aspose.BarCode?**  
A5: Natürlich! Sie können die Funktionen von Aspose.BarCode mit einer kostenlosen Testlizenz [here](https://releases.aspose.com/) ausprobieren.

**Q6: Wie erstelle ich einen hochauflösenden QR‑Code für den Druck?**  
A6: Setzen Sie die gewünschte DPI am `BarcodeGenerator`, bevor Sie `generateBarCodeImage()` aufrufen, und speichern Sie das Bild in einem verlustfreien Format wie PNG.

**Q7: Was tun, wenn das kombinierte Bild abgeschnitten erscheint?**  
A7: Überprüfen Sie, ob die Berechnungen für `offset` und die Canvas‑Größe die Höhen aller Barcodes korrekt berücksichtigen; das Erhöhen der Canvas‑Höhe oder das Reduzieren der einzelnen Barcode‑Größen löst meist das Problem.

---

**Zuletzt aktualisiert:** 2026-04-03  
**Getestet mit:** Aspose.BarCode for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
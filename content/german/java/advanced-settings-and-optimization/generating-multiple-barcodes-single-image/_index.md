---
title: Generieren mehrerer Barcodes auf einem einzelnen Bild in Java mit Aspose.BarCode
linktitle: Generieren mehrerer Barcodes auf einem einzelnen Bild
second_title: Aspose.BarCode Java API
description: Generieren Sie mühelos mehrere Barcodes auf einem einzigen Bild mit Aspose.BarCode für Java. Befolgen Sie unsere Schritt-für-Schritt-Anleitung für eine nahtlose Integration.
type: docs
weight: 19
url: /de/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
---
## Einführung

In der dynamischen Welt der Java-Programmierung ist die effiziente Erstellung und Verwaltung von Barcodes für verschiedene Anwendungen von entscheidender Bedeutung. Aspose.BarCode für Java vereinfacht diesen Prozess und ermöglicht Entwicklern die nahtlose Generierung mehrerer Barcodes auf einem einzigen Bild. Dieses Tutorial führt Sie durch die Schritte, um dies mit Aspose.BarCode in einer Java-Umgebung zu erreichen.

## Voraussetzungen

Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Grundlegendes Verständnis der Java-Programmierung.
- Java Development Kit (JDK) auf Ihrem System installiert.
- Aspose.BarCode für Java-Bibliothek heruntergeladen und eingerichtet. Sie können es herunterladen[Hier](https://releases.aspose.com/barcode/java/).
- Eine integrierte Entwicklungsumgebung (IDE) wie Eclipse oder IntelliJ IDEA.

## Namespaces importieren

Importieren Sie in Ihrem Java-Projekt die erforderlichen Namespaces, um auf die Aspose.BarCode-Funktionalität zuzugreifen. Fügen Sie am Anfang Ihrer Java-Klasse die folgenden Importanweisungen hinzu:

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

## Schritt 1: Legen Sie das Ressourcenverzeichnis fest

Definieren Sie den Pfad zum Ressourcenverzeichnis, in dem die generierten Barcodes gespeichert werden. Dieses Verzeichnis ist für die Organisation und Verwaltung Ihrer Barcode-Bilder von entscheidender Bedeutung.

```java
// Der Pfad zum Ressourcenverzeichnis.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Schritt 2: Erstellen Sie eine Sammlung von Barcodes

Initialisieren Sie eine HashMap, um die Barcode-Daten zu speichern. Jeder Eintrag in der Sammlung stellt einen Barcode mit seinem jeweiligen Kodierungstyp dar.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Schritt 3: Barcode-Bilder generieren

Durchlaufen Sie die Sammlung und generieren Sie Barcode-Bilder mithilfe der Aspose.BarCode-Bibliothek. Speichern Sie die Bilder zur weiteren Verarbeitung in einer ArrayList.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Schritt 4: Erstellen Sie ein kombiniertes Bild

Bestimmen Sie die maximale Breite und Gesamthöhe der Barcodebilder. Erstellen Sie ein BufferedImage, um einzelne Barcodebilder zu einem einzigen Ausgabebild zu kombinieren.

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
## Schritt 5: Speichern Sie das Ergebnis

Speichern Sie das endgültige kombinierte Bild an einem angegebenen Dateispeicherort.

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Abschluss

Glückwunsch! Sie haben mit Aspose.BarCode für Java erfolgreich mehrere Barcodes auf einem einzelnen Bild generiert. Diese leistungsstarke Bibliothek vereinfacht die Barcode-Verarbeitung und ist damit ein unschätzbar wertvolles Werkzeug für Java-Entwickler.

## FAQs

### F1: Kann ich das Erscheinungsbild einzelner Barcodes im generierten Bild anpassen?

A1: Ja, Aspose.BarCode bietet umfangreiche Anpassungsoptionen für das Erscheinungsbild von Barcodes, sodass Sie den Stil jedes Barcodes an Ihre Vorlieben anpassen können.

### F2: Ist Aspose.BarCode mit verschiedenen Barcode-Symbologien kompatibel?

A2: Auf jeden Fall! Aspose.BarCode unterstützt eine breite Palette von Symbologien, einschließlich CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 und AZTEC, wie in diesem Tutorial gezeigt.

### F3: Wie kann ich Aspose.BarCode in mein Java-Projekt integrieren?

 A3: Laden Sie einfach die Aspose.BarCode für Java-Bibliothek herunter von[Hier](https://releases.aspose.com/barcode/java/) und befolgen Sie die Installationsanweisungen in der Dokumentation.

### F4: Kann ich Aspose.BarCode für kommerzielle Anwendungen verwenden?

 A4: Ja, Sie können eine Lizenz erhalten von[Hier](https://purchase.aspose.com/buy) Aspose.BarCode für kommerzielle Zwecke zu nutzen.

### F5: Gibt es Testoptionen für Aspose.BarCode?

 A5: Auf jeden Fall! Sie können die Funktionen von Aspose.BarCode erkunden, indem Sie eine kostenlose Testlizenz erwerben[Hier](https://releases.aspose.com/).
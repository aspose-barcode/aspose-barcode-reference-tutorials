---
date: 2026-10-19
description: Erfahren Sie, wie Sie QR code java erstellen und mehrere Barcodes in
  einem einzigen Bild mit Aspose.BarCode for Java generieren. Enthält Einrichtung,
  Code und Fehlersuche.
keywords:
- create qr code java
- how to create qr
- java barcode library
- generate multiple barcodes
- aspose trial license
lastmod: 2026-10-19
linktitle: Mehrere Barcodes in einem einzigen Bild generieren
og_description: QR code java erstellen und mehrere Barcode‑Typen zu einem einzigen
  Bild mit Aspose.BarCode for Java kombinieren. Folgen Sie der Schritt‑für‑Schritt‑Anleitung,
  sehen Sie Code‑Beispiele und erhalten Sie Tipps zur Fehlersuche.
og_image_alt: Screenshot of a Java application generating a QR code and other barcodes
  on one combined image
og_title: QR code java erstellen – mehrere Barcodes in einem Bild generieren
schemas:
- author: Aspose
  dateModified: '2026-10-19'
  description: Learn how to create QR code java and generate multiple barcodes on
    a single image using Aspose.BarCode for Java. Includes setup, code, and troubleshooting.
  headline: Create QR code java – generate multiple barcodes on one image
  type: TechArticle
- questions:
  - answer: Yes. Use the `BarcodeGenerator` properties such as `setBarColor`, `setBackgroundColor`,
      and `setXDimension` to style each barcode independently before adding it to
      the canvas.
    question: Can I customize the appearance of individual barcodes in the generated
      image?
  - answer: Absolutely. The library supports 50+ symbologies, including CODE_39, DATA_MATRIX,
      QR, CODE_128, EAN_13, and AZTEC, as demonstrated in this tutorial.
    question: Is Aspose.BarCode compatible with different barcode symbologies?
  - answer: Download the JAR from the Aspose.BarCode for Java library download page,
      add it to your project’s classpath, and import the required namespaces as shown
      in the “Import namespaces” section.
    question: How do I integrate Aspose.BarCode into my Java project?
  - answer: Yes. Purchase a license from the Aspose.BarCode license purchase page
      to remove trial limitations and obtain full production support.
    question: Can I use Aspose.BarCode for commercial applications?
  - answer: Certainly. A free trial license is available from the Aspose.BarCode free
      trial download page, giving you full API access for evaluation.
    question: Are there trial options available for Aspose.BarCode?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- create qr code
- aspose barcode
- java barcode generation
- multiple barcodes image
title: QR code java erstellen – mehrere Barcodes in einem Bild generieren
url: /de/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# QR-Code in Java erstellen – mehrere Barcodes in einem Bild generieren

## Einleitung

In diesem Tutorial lernen Sie **wie man QR-Code in Java erstellt** und mehrere verschiedene Barcode‑Typen auf einer einzigen Leinwand mithilfe von **Aspose.BarCode for Java** zusammenführt. Egal, ob Sie ein kompaktes QR‑Label, einen Produktbarcode oder eine Mischung aus 2‑D‑ und linearen Symbolen benötigen, führt Sie dieser Leitfaden durch jeden Schritt – von der Projektkonfiguration bis zum Speichern des endgültigen kombinierten Bildes – sodass Sie die Barcode‑Generierung sofort in Ihre Java‑Anwendungen integrieren können.

## Schnelle Antworten
- **Welche Bibliothek sollte ich verwenden?** Aspose.BarCode for Java bietet das vollständigste Set an Symbolen.  
- **Kann ich verschiedene Barcode‑Typen zusammen generieren?** Ja, Sie können CODE_39, QR, AZTEC und weitere auf einer einzigen Leinwand kombinieren.  
- **Benötige ich eine Lizenz für die Entwicklung?** Eine kostenlose Testversion funktioniert für Tests; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Welche Java‑Version wird unterstützt?** Java 8 und neuer sind vollständig kompatibel.  
- **Ist das Ausgabeformat konfigurierbar?** Sie können das kombinierte Bild als PNG, JPEG, BMP oder TIFF exportieren.

## Was ist QR-Code in Java erstellen?

`create QR code java` bezieht sich auf den Prozess, einen Textstring in eine zweidimensionale Matrix zu verwandeln, die von Smartphones oder Barcode‑Lesegeräten gescannt werden kann. Aspose.BarCode for Java übernimmt die Kodierung und das Rendering, sodass Sie sich auf die Geschäftslogik statt auf die pixelgenaue Bildverarbeitung konzentrieren können.

## Warum Aspose.BarCode Java für die Barcode‑Generierung in Java verwenden?

Aspose.BarCode unterstützt **über 50 Barcode‑Symbologien** – darunter QR, Data Matrix, Code 128, AZTEC und traditionelle lineare Codes – und ist damit die vielseitigste Java‑Barcode‑Bibliothek. Es rendert **anti‑aliasierte Bilder mit bis zu 1200 dpi**, was scharfe Scans auf Bildschirm und Druck garantiert. Die API benötigt nur die JVM und bietet ein flüssiges Konfigurationsmodell, um Größe, Farbe, Ränder und Fehlerkorrektur in nur wenigen Codezeilen anzupassen.

## Voraussetzungen

- Ein solides Verständnis der Java‑Grundlagen.  
- JDK 8 oder neuer, installiert und in Ihrem PATH konfiguriert.  
- Das Aspose.BarCode for Java JAR (Download von der offiziellen Aspose.BarCode for Java Download‑Seite).  
- Eine IDE wie IntelliJ IDEA oder Eclipse zum Bearbeiten und Ausführen des Beispiels.  

## Namespaces importieren

Import‑Anweisungen bringen Aspose.BarCode‑Klassen wie `BarcodeGenerator`, `EncodeTypes` und `BarCodeImageFormat` in den Gültigkeitsbereich, sodass Sie sie ohne vollqualifizierte Namen referenzieren können.  
`BarcodeGenerator` ist die Hauptklasse, die zum Konfigurieren und Generieren von Barcode‑Bildern verwendet wird.  
`EncodeTypes` ist ein Enum in Aspose.BarCode, das die zu generierende Barcode‑Symbologie angibt.  
`BarCodeImageFormat` definiert das Ausgabe‑Bildformat für den generierten Barcode.

## Schritt 1: Ressourcenverzeichnis festlegen

Das **Ressourcenverzeichnis** ist der Ordner auf Ihrem Dateisystem, in dem alle generierten Barcode‑Bilder gespeichert werden. Einmal definiert, hält es Ihr Projekt organisiert und erleichtert das Aufräumen alter Dateien.

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

## Schritt 2: Sammlung von Barcodes erstellen

Ein `HashMap<String, EncodeTypes>` speichert den Datenstring jedes Barcodes zusammen mit der zu verwendenden Symbologie. `HashMap` ist eine Java‑Collection, die Schlüssel auf Werte abbildet. Diese Sammlung steuert die nachfolgende Generierungsschleife. `EncodeTypes` ist ein Enum, das angibt, welchen Barcode‑Typ zu generieren ist.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Schritt 3: Barcode‑Bilder generieren

Die Generierungsschleife iteriert über die `HashMap`, erstellt für jeden Eintrag einen `BarcodeGenerator` und ruft `generateBarCodeImage()` auf, um ein `BufferedImage` zu erhalten. `generateBarCodeImage()` erzeugt ein `BufferedImage`, das den gerenderten Barcode enthält. `BufferedImage` ist eine Java‑Klasse, die ein Bild im Speicher repräsentiert. Alle Bilder werden zu einer `ArrayList<BufferedImage>` für die spätere Zusammensetzung hinzugefügt. `ArrayList` ist eine in Java skalierbare Listenimplementierung.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Schritt 4: Kombiniertes Bild erstellen

Zunächst berechnet der Algorithmus die **maximale Breite** aller Barcode‑Bilder und die **gesamte Höhe**, die zum vertikalen Stapeln mit optionalem Abstand erforderlich ist. Anschließend erstellt er ein `BufferedImage` dieser Größe und zeichnet jeden Barcode mithilfe eines `Graphics2D`‑Objekts auf die Leinwand. `Graphics2D` ist eine Java‑Klasse, die 2D‑Rendering‑Funktionen zum Zeichnen von Formen und Bildern bereitstellt.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Schritt 5: Ergebnis speichern

Abschließend wird das zusammengesetzte Bild mit `ImageIO.write` auf die Festplatte geschrieben, wobei das von Ihnen angegebene Format (PNG, JPEG, BMP oder TIFF) verwendet wird. `ImageIO.write` schreibt ein `BufferedImage` in eine Datei im angegebenen Format. Der Dateipfad ist relativ zum zuvor definierten Ressourcenverzeichnis.

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

## Häufige Anwendungsfälle für die Generierung mehrerer Barcodes

- **Verpackungsetiketten** – Produkt-, Chargen- und Versandcodes auf einem einzigen Etikett kombinieren, um Druckkosten zu senken.  
- **Event‑Tickets** – QR-, Data‑Matrix- und Code 128‑Kennungen für verschiedene Scan‑Stationen an einem Veranstaltungsort einbetten.  
- **Inventarverwaltung** – SKU, RFID‑Tag‑Daten und Seriennummern gemeinsam anzeigen für schnelle Prüfung und Rückverfolgbarkeit.

## Fehlerbehebung & Tipps

- **Bildgrößen‑Probleme** – Passen Sie die Variable `offset` an, um den Abstand zwischen den Barcodes zu vergrößern oder zu verkleinern.  
- **Nicht unterstützte Symbologie** – Stellen Sie sicher, dass Ihre Aspose.BarCode‑Version den gewünschten Barcode‑Typ unterstützt; neuere Versionen fügen zusätzliche 2‑D‑Codes hinzu.  
- **Leistung** – Verwenden Sie ein einzelnes `Graphics2D`‑Objekt, wenn Sie viele Bilder in einer Schleife generieren, um den Aufwand für Objektzuweisungen zu minimieren.  

## Häufig gestellte Fragen

**Q: Kann ich das Aussehen einzelner Barcodes im generierten Bild anpassen?**  
A: Ja. Verwenden Sie die Eigenschaften des `BarcodeGenerator` wie `setBarColor`, `setBackgroundColor` und `setXDimension`, um jeden Barcode unabhängig zu stylen, bevor Sie ihn zur Leinwand hinzufügen.

**Q: Ist Aspose.BarCode mit verschiedenen Barcode‑Symbologien kompatibel?**  
A: Absolut. Die Bibliothek unterstützt über 50 Symbologien, darunter CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 und AZTEC, wie in diesem Tutorial gezeigt.

**Q: Wie integriere ich Aspose.BarCode in mein Java‑Projekt?**  
A: Laden Sie das JAR von der Aspose.BarCode for Java Bibliotheks‑Download‑Seite herunter, fügen Sie es dem Klassenpfad Ihres Projekts hinzu und importieren Sie die erforderlichen Namespaces wie im Abschnitt „Namespaces importieren“ gezeigt.

**Q: Kann ich Aspose.BarCode für kommerzielle Anwendungen verwenden?**  
A: Ja. Kaufen Sie eine Lizenz auf der Aspose.BarCode Lizenz‑Kauf‑Seite, um Trial‑Beschränkungen zu entfernen und vollen Produktions‑Support zu erhalten.

**Q: Gibt es Testoptionen für Aspose.BarCode?**  
A: Sicherlich. Eine kostenlose Testlizenz ist auf der Aspose.BarCode Free‑Trial‑Download‑Seite verfügbar und bietet vollen API‑Zugriff für die Evaluierung.

**Q: Wie generiere ich einen hochauflösenden QR‑Code für den Druck?**  
A: Setzen Sie die Eigenschaft `setResolutionDpi` im `BarcodeGenerator`, bevor Sie `generateBarCodeImage()` aufrufen, und speichern Sie das Ergebnis in einem verlustfreien Format wie PNG.

**Q: Was soll ich tun, wenn das kombinierte Bild abgeschnitten erscheint?**  
A: Stellen Sie sicher, dass die Berechnungen für `offset` und die Canvas‑Größe alle Barcode‑Höhen korrekt berücksichtigen; das Erhöhen der Canvas‑Höhe oder das Verringern einzelner Barcode‑Größen behebt die meisten Abschneide‑Probleme.

---

**Zuletzt aktualisiert:** 2026-10-19  
**Getestet mit:** Aspose.BarCode for Java 24.11  
**Autor:** Aspose  








```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Verwandte Tutorials

- [Wie man Barcode‑Bild in Java erstellt – Rahmen hinzufügen mit Aspose](/barcode/java/image-manipulation/adding-borders-barcode-image/)
- [Wie man Barcode in Java generiert: In Streams speichern mit Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/saving-barcode-image-streams/)
- [Wie man Barcode in Java generiert und Barcode mit Aspose druckt](/barcode/java/barcode-rendering-techniques/rendering-barcode-printer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
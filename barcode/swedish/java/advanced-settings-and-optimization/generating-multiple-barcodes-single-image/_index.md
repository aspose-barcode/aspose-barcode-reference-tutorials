---
title: Generera flera streckkoder på en enda bild i Java med Aspose.BarCode
linktitle: Generera flera streckkoder på en enda bild
second_title: Aspose.BarCode Java API
description: Generera flera streckkoder på en enda bild utan ansträngning med Aspose.BarCode för Java. Följ vår steg-för-steg-guide för sömlös integration.
weight: 19
url: /sv/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generera flera streckkoder på en enda bild i Java med Aspose.BarCode

## Introduktion

I den dynamiska världen av Java-programmering är det avgörande att skapa och hantera streckkoder effektivt för olika applikationer. Aspose.BarCode för Java förenklar denna process, vilket gör att utvecklare kan generera flera streckkoder på en enda bild sömlöst. Denna handledning guidar dig genom stegen för att uppnå detta med Aspose.BarCode i en Java-miljö.

## Förutsättningar

Innan du dyker in i handledningen, se till att du har följande förutsättningar:

- Grundläggande förståelse för Java-programmering.
- Java Development Kit (JDK) installerat på ditt system.
- Aspose.BarCode för Java-biblioteket har laddats ner och ställts in. Du kan ladda ner den[här](https://releases.aspose.com/barcode/java/).
- En integrerad utvecklingsmiljö (IDE) som Eclipse eller IntelliJ IDEA.

## Importera namnområden

I ditt Java-projekt, importera de nödvändiga namnrymden för att komma åt Aspose.BarCode-funktionen. Lägg till följande importsatser i början av din Java-klass:

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

## Steg 1: Ställ in resurskatalogen

Definiera sökvägen till resurskatalogen där de genererade streckkoderna ska sparas. Denna katalog är avgörande för att organisera och hantera dina streckkodsbilder.

```java
// Sökvägen till resurskatalogen.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Steg 2: Skapa en samling streckkoder

Initiera en HashMap för att lagra streckkodsdata. Varje post i samlingen representerar en streckkod med sin respektive kodningstyp.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Steg 3: Skapa streckkodsbilder

Iterera genom samlingen och generera streckkodsbilder med Aspose.BarCode-biblioteket. Lagra bilderna i en ArrayList för vidare bearbetning.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Steg 4: Skapa en kombinerad bild

Bestäm streckkodsbildernas maximala bredd och totala höjd. Skapa en buffrad bild för att kombinera enskilda streckkodsbilder till en enda utdatabild.

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
## Steg 5: Spara resultatet

Spara den slutliga kombinerade bilden till en angiven filplats.

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Slutsats

Grattis! Du har framgångsrikt skapat flera streckkoder på en enda bild med Aspose.BarCode för Java. Detta kraftfulla bibliotek förenklar streckkodshanteringen, vilket gör det till ett ovärderligt verktyg för Java-utvecklare.

## FAQ's

### F1: Kan jag anpassa utseendet på enskilda streckkoder i den genererade bilden?

S1: Ja, Aspose.BarCode erbjuder omfattande anpassningsalternativ för streckkodens utseende, så att du kan skräddarsy varje streckkods stil efter dina önskemål.

### F2: Är Aspose.BarCode kompatibel med olika streckkodssymboler?

A2: Absolut! Aspose.BarCode stöder ett brett utbud av symboler, inklusive CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 och AZTEC, som visas i denna handledning.

### F3: Hur kan jag integrera Aspose.BarCode i mitt Java-projekt?

 S3: Ladda bara ned Aspose.BarCode for Java-biblioteket från[här](https://releases.aspose.com/barcode/java/) och följ installationsinstruktionerna i dokumentationen.

### F4: Kan jag använda Aspose.BarCode för kommersiella tillämpningar?

 A4: Ja, du kan få en licens från[här](https://purchase.aspose.com/buy) att använda Aspose.BarCode för kommersiella ändamål.

### F5: Finns det några testalternativ tillgängliga för Aspose.BarCode?

 A5: Visst! Du kan utforska funktionerna i Aspose.BarCode genom att skaffa en gratis testlicens[här](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

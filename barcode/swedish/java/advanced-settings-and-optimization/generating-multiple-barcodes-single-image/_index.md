---
date: 2025-12-10
description: Lär dig hur du genererar streckkoder på en enda bild i Java med Aspose.BarCode.
  Denna guide täcker Aspose Barcode Java‑integration och generering av flera streckkoder.
linktitle: Generating Multiple Barcodes on a Single Image
second_title: Aspose.BarCode Java API
title: Hur man genererar streckkoder på en enda bild i Java
url: /sv/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generera flera streckkoder på en enda bild i Java med Aspose.BarCode

## Introduction

Om du letar efter ett pålitligt sätt **hur man genererar streckkoder** i en Java‑applikation, har du kommit till rätt ställe. Med Aspose.BarCode för Java kan du placera flera olika streckkodstyper på en bild med bara några rader kod. Denna handledning guidar dig genom hela processen—från att sätta upp projektet till att spara den kombinerade bilden—så att du kan börja använda streckkodsgenerering i dina egna lösningar omedelbart.

## Quick Answers
- **Vilket bibliotek ska jag använda?** Aspose.BarCode för Java tillhandahåller den mest kompletta uppsättningen av symbologier.  
- **Kan jag generera olika streckkodstyper tillsammans?** Ja, du kan blanda CODE_39, QR, AZTEC och fler på en enda canvas.  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en kommersiell licens krävs för produktion.  
- **Vilken Java‑version stöds?** Java 8 och nyare är fullt kompatibla.  
- **Kan utdataformatet konfigureras?** Du kan exportera den kombinerade bilden som PNG, JPEG, BMP osv.

## What is “how to generate barcodes” in Java?
Vad betyder “hur man genererar streckkoder” i Java?  
Att generera streckkoder innebär att konvertera en datasträng till ett visuellt mönster som läsare kan avläsa. Aspose.BarCode hanterar kodning, rendering och bildskapande automatiskt, så att du kan fokusera på affärslogik snarare än låg‑nivå bildbehandling.

## Why use Aspose.BarCode for Java barcode generation?
- **Brett stöd för symbologier** – från klassiska linjära koder till moderna 2‑D‑matriser.  
- **Högkvalitativ rendering** – kantutjämnad output som fungerar på alla enheter.  
- **Enkelt API** – skapa, anpassa och kombinera streckkoder med bara några metodanrop.  
- **Inga externa beroenden** – allt körs på JVM utan inhemska bibliotek.

## Prerequisites

Innan du dyker ner i handledningen, se till att du har följande förutsättningar:

- Grundläggande förståelse för Java‑programmering.  
- Java Development Kit (JDK) installerat på ditt system.  
- Aspose.BarCode för Java‑biblioteket nedladdat och konfigurerat. Du kan ladda ner det [här](https://releases.aspose.com/barcode/java/).  
- En integrerad utvecklingsmiljö (IDE) såsom Eclipse eller IntelliJ IDEA.

## Import Namespaces

I ditt Java‑projekt importerar du de nödvändiga namnutrymmena för att få åtkomst till Aspose.BarCode‑funktionaliteten. Lägg till följande import‑satser i början av din Java‑klass:

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

## Step 1: Set the Resource Directory

Definiera sökvägen till resurskatalogen där de genererade streckkoderna ska sparas. Denna katalog är avgörande för att organisera och hantera dina streckkodsbilder.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Step 2: Create a Collection of Barcodes

Initiera en `HashMap` för att lagra streckkodsdata. Varje post i samlingen representerar en streckkod med sin respektive kodningstyp.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Step 3: Generate Barcode Images

Iterera genom samlingen och generera streckkodsbilder med hjälp av Aspose.BarCode‑biblioteket. Spara bilderna i en `ArrayList` för vidare bearbetning.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Step 4: Create a Combined Image

Bestäm den maximala bredden och totala höjden på streckkodsbilderna. Skapa en `BufferedImage` för att kombinera enskilda streckkodsbilder till en enda utdata­bild.

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

## Step 5: Save the Result

Spara den slutliga kombinerade bilden till en angiven filsökväg.

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Common Use Cases for Generating Multiple Barcodes

- **Förpackningsetiketter** – kombinera produkt-, batch‑ och fraktkoder på en enda etikett.  
- **Evenemangsbiljetter** – inbädda QR, Data Matrix och Code 128‑identifierare för olika skanningsstationer.  
- **Lagerhantering** – visa SKU, RFID‑taggdata och serienummer tillsammans för snabb revision.

## Troubleshooting & Tips

- **Problem med bildstorlek** – justera variabeln `offset` för att öka eller minska avståndet mellan streckkoder.  
- **Ej stödd symbologi** – verifiera att din Aspose.BarCode‑version stödjer den önskade streckkodstypen.  
- **Prestanda** – återanvänd ett enda `Graphics`‑objekt om du genererar många bilder i en loop.

## FAQ's

### Q1: Can I customize the appearance of individual barcodes in the generated image?

A1: Ja, Aspose.BarCode erbjuder omfattande anpassningsalternativ för streckkodens utseende, så att du kan skräddarsy varje streckkods stil efter dina preferenser.

### Q2: Is Aspose.BarCode compatible with different barcode symbologies?

A2: Absolut! Aspose.BarCode stödjer ett brett spektrum av symbologier, inklusive CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 och AZTEC, som demonstreras i denna handledning.

### Q3: How can I integrate Aspose.BarCode into my Java project?

A3: Ladda helt enkelt ner Aspose.BarCode för Java‑biblioteket från [här](https://releases.aspose.com/barcode/java/) och följ installationsinstruktionerna i dokumentationen.

### Q4: Can I use Aspose.BarCode for commercial applications?

A4: Ja, du kan skaffa en licens från [här](https://purchase.aspose.com/buy) för att använda Aspose.BarCode i kommersiella syften.

### Q5: Are there any trial options available for Aspose.BarCode?

A5: Självklart! Du kan utforska funktionerna i Aspose.BarCode genom att skaffa en gratis provlicens [här](https://releases.aspose.com/).

**Additional Questions**

**Q: How do I generate a QR code specifically in Java?**  
A: Använd `EncodeTypes.QR` när du skapar `BarcodeGenerator`‑instansen, som visas i samlings‑exemplet.

**Q: Does Aspose.BarCode support high‑resolution output for printing?**  
A: Ja, du kan ange DPI när du sparar bilden för att uppfylla krav på utskriftskvalitet.

---

**Last Updated:** 2025-12-10  
**Tested With:** Aspose.BarCode for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
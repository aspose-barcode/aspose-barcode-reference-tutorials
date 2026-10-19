---
date: 2026-10-19
description: Lär dig hur du skapar QR‑kod java och genererar flera streckkoder på
  en enda bild med Aspose.BarCode for Java. Inkluderar installation, kod och felsökning.
keywords:
- create qr code java
- how to create qr
- java barcode library
- generate multiple barcodes
- aspose trial license
lastmod: 2026-10-19
linktitle: Generera flera streckkoder på en enda bild
og_description: Skapa QR‑kod java och kombinera flera streckkodstyper till en enda
  bild med Aspose.BarCode for Java. Följ en steg‑för‑steg‑guide, se kodexempel och
  lär dig felsökningstips.
og_image_alt: Screenshot of a Java application generating a QR code and other barcodes
  on one combined image
og_title: Skapa QR‑kod java – generera flera streckkoder på en bild
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
title: Skapa QR‑kod java – generera flera streckkoder på en bild
url: /sv/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa QR-kod java – generera flera streckkoder på en bild

## Introduktion

I den här handledningen kommer du att lära dig **hur man skapar QR code java** och slå samman flera olika streckkodstyper på en enda duk med hjälp av **Aspose.BarCode for Java**. Oavsett om du behöver en kompakt QR-etikett, en produktstreckkod eller en blandning av 2‑D- och linjära symboler, guidar den här guiden dig genom varje steg—från projektuppsättning till att spara den slutliga kombinerade bilden—så att du snabbt kan börja integrera streckkodsgenerering i dina Java‑applikationer.

## Snabba svar
- **Vilket bibliotek ska jag använda?** Aspose.BarCode for Java tillhandahåller den mest kompletta uppsättningen av symboler.  
- **Kan jag generera olika streckkodstyper tillsammans?** Ja, du kan blanda CODE_39, QR, AZTEC och fler på en enda duk.  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en kommersiell licens krävs för produktion.  
- **Vilken Java-version stöds?** Java 8 och nyare är fullt kompatibla.  
- **Kan utdataformatet konfigureras?** Du kan exportera den kombinerade bilden som PNG, JPEG, BMP eller TIFF.

## Vad är create QR code java?

`create QR code java` avser processen att omvandla en textsträng till en tvådimensionell matris som kan skannas av smartphones eller streckkodsläsare. Aspose.BarCode for Java utför kodningen och rendering, så att du kan fokusera på affärslogik istället för bildhantering på pixelnivå.

## Varför använda Aspose.BarCode Java för att generera streckkoder java?

Aspose.BarCode stöder **över 50 streckkodssymboler**—inklusive QR, Data Matrix, Code 128, AZTEC och traditionella linjära koder—vilket gör det till det mest mångsidiga Java‑streckkodsbiblioteket. Det renderar **anti‑aliasade bilder med upp till 1200 dpi**, vilket garanterar skarpa skanningar på skärm och i utskrift. API:et kräver endast JVM och erbjuder en flytande konfigurationsmodell för att anpassa storlek, färg, marginaler och felkorrigering på bara några kodrader.

## Förutsättningar

- En solid förståelse för Java-grunderna.  
- JDK 8 eller nyare installerad och konfigurerad i din PATH.  
- Aspose.BarCode for Java JAR-filen (ladda ner från den officiella Aspose.BarCode for Java nedladdningssidan).  
- En IDE såsom IntelliJ IDEA eller Eclipse för att redigera och köra exemplet.  

## Importera namnrymder

Import‑satser tar in Aspose.BarCode‑klasser som `BarcodeGenerator`, `EncodeTypes` och `BarCodeImageFormat` i scopet, så att du kan referera till dem utan fullständigt kvalificerade namn.  
`BarcodeGenerator` är huvudklassen som används för att konfigurera och generera streckkodbilder.  
`EncodeTypes` är en enum i Aspose.BarCode som specificerar vilken streckkodssymbol som ska genereras.  
`BarCodeImageFormat` definierar utdataformatet för den genererade streckkoden.

## Steg 1: ange resurskatalogen

**Resurskatalogen** är mappen på ditt filsystem där alla genererade streckkodbilder kommer att skrivas. Att definiera den en gång håller ditt projekt organiserat och gör det enkelt att rensa bort gamla filer.

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

## Steg 2: skapa en samling av streckkoder

En `HashMap<String, EncodeTypes>` lagrar varje streckkods datasträng tillsammans med den symbol du vill använda. `HashMap` är en Java‑samling som mappar nycklar till värden. Denna samling driver genereringsloopen som följer. `EncodeTypes` är en enum som specificerar vilken streckkodstyp som ska genereras.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Steg 3: generera streckkodbilder

Genereringsloopen itererar över `HashMap`, skapar en `BarcodeGenerator` för varje post och anropar `generateBarCodeImage()` för att få en `BufferedImage`. `generateBarCodeImage()` skapar en `BufferedImage` som innehåller den renderade streckkoden. `BufferedImage` är en Java‑klass som representerar en bild i minnet. Alla bilder läggs till i en `ArrayList<BufferedImage>` för senare sammanslagning. `ArrayList` är en dynamisk listimplementation i Java.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Steg 4: skapa en kombinerad bild

Först beräknar algoritmen **maximal bredd** bland alla streckkodbilder och **total höjd** som krävs för att stapla dem vertikalt med valfritt avstånd. Därefter skapas en `BufferedImage` av den storleken och varje streckkod ritas på duken med ett `Graphics2D`‑objekt. `Graphics2D` är en Java‑klass som tillhandahåller 2D‑renderingsmöjligheter för att rita former och bilder.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Steg 5: spara resultatet

Slutligen skrivs den sammansatta bilden till disk med `ImageIO.write`, med det format du angav (PNG, JPEG, BMP eller TIFF). `ImageIO.write` skriver en `BufferedImage` till en fil i det angivna formatet. Filvägen är relativ till den resurskatalog som definierades tidigare.

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

## Vanliga användningsområden för att generera flera streckkoder

- **Packaging labels** – kombinera produkt-, batch- och fraktkoder på en enda etikett för att minska utskriftskostnaderna.  
- **Event tickets** – bädda in QR-, Data Matrix- och Code 128‑identifierare för olika skanningsstationer på en plats.  
- **Inventory management** – visa SKU, RFID‑taggdata och serienummer tillsammans för snabb revision och spårbarhet.

## Felsökning & tips

- **Image size issues** – justera `offset`‑variabeln för att öka eller minska avståndet mellan streckkoder.  
- **Unsupported symbology** – verifiera att din Aspose.BarCode‑version stöder den önskade streckkodstypen; nyare versioner lägger till ytterligare 2‑D‑koder.  
- **Performance** – återanvänd ett enda `Graphics2D`‑objekt när du genererar många bilder i en loop för att minimera minnesallokeringskostnaden.  

## Vanliga frågor

**Q: Kan jag anpassa utseendet på enskilda streckkoder i den genererade bilden?**  
A: Ja. Använd `BarcodeGenerator`‑egenskaper som `setBarColor`, `setBackgroundColor` och `setXDimension` för att stilera varje streckkod oberoende innan du lägger till den på duken.

**Q: Är Aspose.BarCode kompatibel med olika streckkodssymboler?**  
A: Absolut. Biblioteket stöder 50+ symboler, inklusive CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 och AZTEC, som demonstreras i den här handledningen.

**Q: Hur integrerar jag Aspose.BarCode i mitt Java‑projekt?**  
A: Ladda ner JAR‑filen från Aspose.BarCode for Java‑bibliotekets nedladdningssida, lägg till den i ditt projekts classpath och importera de nödvändiga namnrymderna som visas i avsnittet “Importera namnrymder”.

**Q: Kan jag använda Aspose.BarCode för kommersiella tillämpningar?**  
A: Ja. Köp en licens från Aspose.BarCode‑licensköpsidan för att ta bort provbegränsningar och få full produktionssupport.

**Q: Finns det provalternativ för Aspose.BarCode?**  
A: Självklart. En gratis provlicens finns tillgänglig från Aspose.BarCode‑gratisprov‑nedladdningssidan, vilket ger dig full API‑åtkomst för utvärdering.

**Q: Hur genererar jag en högupplöst QR‑kod för utskrift?**  
A: Ställ in `setResolutionDpi`‑egenskapen på `BarcodeGenerator` innan du anropar `generateBarCodeImage()`, och spara sedan resultatet i ett förlustfritt format som PNG.

**Q: Vad ska jag göra om den kombinerade bilden blir avklippt?**  
A: Verifiera att `offset`‑ och dukstorleksberäkningarna korrekt tar hänsyn till alla streckkodshöjder; att öka dukens höjd eller minska enskilda streckkodsstorlekar löser de flesta avklippningsproblem.

---

**Senast uppdaterad:** 2026-10-19  
**Testad med:** Aspose.BarCode for Java 24.11  
**Författare:** Aspose  








```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Relaterade handledningar

- [Hur man skapar streckkod bild Java – Lägg till ram med Aspose](/barcode/java/image-manipulation/adding-borders-barcode-image/)
- [Hur man genererar streckkod Java: Spara till strömmar med Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/saving-barcode-image-streams/)
- [Hur man genererar streckkod Java och skriver ut streckkod med Aspose](/barcode/java/barcode-rendering-techniques/rendering-barcode-printer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
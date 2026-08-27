---
date: 2026-04-03
description: Lär dig hur du skapar QR‑kod i Java och genererar flera streckkoder på
  en enda bild med Aspose.BarCode för Java. Inkluderar installation, kod och felsökning.
keywords:
- create qr code java
- aspose barcode java
- generate barcodes java
linktitle: Generera flera streckkoder på en enda bild
second_title: Aspose.BarCode Java API
title: Skapa QR‑kod i Java – Generera flera streckkoder på en bild
url: /sv/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa QR Code Java – Generera flera streckkoder på en bild

## Introduktion

I den här handledningen kommer du att lära dig **how to create QR code java** och kombinera flera olika streckkodstyper till en enda bild med hjälp av **Aspose.BarCode for Java**. Oavsett om du behöver en kompakt QR-etikett, en produktstreckkod eller en blandning av 2‑D‑ och linjära symboler, guidar den här guiden dig genom varje steg – från projektuppsättning till att spara den slutliga kombinerade bilden – så att du snabbt kan börja integrera streckkodsgenerering i dina Java‑applikationer.

## Snabba svar
- **Vilket bibliotek ska jag använda?** Aspose.BarCode for Java tillhandahåller den mest kompletta uppsättningen av symboler.  
- **Kan jag generera olika streckkodstyper tillsammans?** Ja, du kan blanda CODE_39, QR, AZTEC och mer på en enda canvas.  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en kommersiell licens krävs för produktion.  
- **Vilken Java‑version stöds?** Java 8 och nyare är fullt kompatibla.  
- **Är utdataformatet konfigurerbart?** Du kan exportera den kombinerade bilden som PNG, JPEG, BMP osv.  

## Vad är create QR code java?

Att skapa en QR‑kod i Java innebär att konvertera en textsträng till en tvådimensionell matris som kan skannas av smartphones eller streckkodsläsare. **Aspose.BarCode for Java** hanterar kodning och rendering, så att du kan fokusera på affärslogik istället för låg‑nivå bildbehandling.

## Varför använda Aspose.BarCode Java för att generera streckkoder java?

- **Brett stöd för symboler** – från klassiska linjära koder till moderna 2‑D‑matriser.  
- **Högkvalitativ rendering** – anti‑aliasad output som fungerar på alla enheter.  
- **Enkelt API** – skapa, anpassa och kombinera streckkoder med bara några metodanrop.  
- **Inga externa beroenden** – allt körs på JVM utan inhemska bibliotek.  

## Förutsättningar

Innan du dyker ner i handledningen, se till att du har följande förutsättningar:

- Grundläggande förståelse för Java‑programmering.  
- Java Development Kit (JDK) installerat på ditt system.  
- Aspose.BarCode for Java‑biblioteket nedladdat och installerat. Du kan ladda ner det [here](https://releases.aspose.com/barcode/java/).  
- En integrerad utvecklingsmiljö (IDE) såsom Eclipse eller IntelliJ IDEA.

## Importera namnrymder

I ditt Java‑projekt importerar du de nödvändiga namnrymderna för att få åtkomst till Aspose.BarCode‑funktionaliteten. Lägg till följande import‑satser i början av din Java‑klass:

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

## Steg 1: Ange resurskatalogen

Definiera sökvägen till resurskatalogen där de genererade streckkoderna sparas. Denna katalog är avgörande för att organisera och hantera dina streckkodsbilder.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Steg 2: Skapa en samling av streckkoder

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

## Steg 3: Generera streckkodsbilder

Iterera genom samlingen och generera streckkodsbilder med hjälp av Aspose.BarCode‑biblioteket. Lagra bilderna i en `ArrayList` för vidare bearbetning.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Steg 4: Skapa en kombinerad bild

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

## Steg 5: Spara resultatet

Spara den slutliga kombinerade bilden till en specificerad filplats.

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Vanliga användningsfall för att generera flera streckkoder

- **Förpackningsetiketter** – kombinera produkt-, batch- och fraktkoder på en enda etikett.  
- **Evenemangsbiljetter** – bädda in QR, Data Matrix och Code 128‑identifierare för olika skanningsstationer.  
- **Lagerhantering** – visa SKU, RFID‑taggdata och serienummer tillsammans för snabb revision.

## Felsökning & Tips

- **Problem med bildstorlek** – justera variabeln `offset` för att öka eller minska avståndet mellan streckkoder.  
- **Ej stödd symbol** – verifiera att din Aspose.BarCode‑version stödjer den önskade streckkodstypen.  
- **Prestanda** – återanvänd ett enda `Graphics`‑objekt om du genererar många bilder i en loop.

## Vanliga frågor

**Q1: Kan jag anpassa utseendet på enskilda streckkoder i den genererade bilden?**  
A1: Ja, Aspose.BarCode erbjuder omfattande anpassningsalternativ för streckkodens utseende, vilket gör att du kan skräddarsy varje streckkods stil efter dina önskemål.

**Q2: Är Aspose.BarCode kompatibel med olika streckkodssymboler?**  
A2: Absolut! Aspose.BarCode stödjer ett brett spektrum av symboler, inklusive CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 och AZTEC, som demonstrerat i den här handledningen.

**Q3: Hur kan jag integrera Aspose.BarCode i mitt Java‑projekt?**  
A3: Ladda helt enkelt ner Aspose.BarCode for Java‑biblioteket från [here](https://releases.aspose.com/barcode/java/) och följ installationsinstruktionerna som finns i dokumentationen.

**Q4: Kan jag använda Aspose.BarCode för kommersiella tillämpningar?**  
A4: Ja, du kan skaffa en licens från [here](https://purchase.aspose.com/buy) för att använda Aspose.BarCode i kommersiella syften.

**Q5: Finns det några provalternativ för Aspose.BarCode?**  
A5: Självklart! Du kan utforska funktionerna i Aspose.BarCode genom att skaffa en gratis provlicens [here](https://releases.aspose.com/).

**Q6: Hur genererar jag en högupplöst QR‑kod för utskrift?**  
A6: Ställ in önskad DPI på `BarcodeGenerator` innan du anropar `generateBarCodeImage()`, och spara sedan bilden i ett förlustfritt format som PNG.

**Q7: Vad ska jag göra om den kombinerade bilden blir avklippt?**  
A7: Verifiera att `offset` och beräkningarna av canvas‑storleken korrekt tar hänsyn till alla streckkodshöjder; att öka canvas‑höjden eller minska enskilda streckkodsstorlekar löser de flesta avklippningsproblem.

---

**Senast uppdaterad:** 2026-04-03  
**Testat med:** Aspose.BarCode for Java 24.11  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
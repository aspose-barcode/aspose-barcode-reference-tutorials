---
date: 2026-04-08
description: Lär dig hur du läser streckkod från PDF i Java med Aspose.BarCode. Den
  här guiden visar också hur du genererar streckkodsbild i Java och extraherar bilder
  från PDF i Java.
keywords:
- read barcode from pdf java
- generate barcode image java
- extract images from pdf java
linktitle: Känna igen streckkoder från PDF
second_title: Aspose.BarCode Java API
title: Hur man läser streckkod från PDF i Java med Aspose.BarCode
url: /sv/java/document-barcode-recognition/recognizing-barcodes-from-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# läsa streckkod från PDF i Java

## Introduktion

Välkommen till vår steg‑för‑steg‑guide om **hur man läser streckkod från PDF i Java** med Aspose.BarCode. Streckkoder är viktiga för att automatisera datainsamling, och med Aspose.BarCode kan du sömlöst upptäcka dem i PDF‑dokument. I den här handledningen går vi igenom allt du behöver – från att konfigurera licenser till att generera en streckkodsbild Java, lägga till den i en PDF, extrahera bilder från PDF Java och slutligen läsa av streckkoden igen.

## Snabba svar
- **Vilket bibliotek behöver jag?** Aspose.BarCode for Java (plus Aspose.PDF för PDF‑hantering).  
- **Kan jag generera en streckkodsbild i Java?** Ja – klassen `BarcodeGenerator` låter dig skapa PNG/JPEG‑bilder.  
- **Hur extraheras bilder från en PDF?** Använd `PdfExtractor` från Aspose.PDF.  
- **Vilken streckkodstyp demonstreras?** CODE‑39 (standard).  
- **Behöver jag en licens?** En giltig Aspose.BarCode‑ och Aspose.PDF‑licens krävs för produktionsanvändning.

## Varför använda Aspose.BarCode för Java?
- **Hög noggrannhet** – stöder dussintals symbologier och fungerar på lågupplösta bilder.  
- **Inga externa beroenden** – ren Java, inga inhemska bibliotek.  
- **Full PDF‑integration** – kombinera med Aspose.PDF för att läsa eller bädda in streckkoder direkt i PDF‑filer.

## Förutsättningar

Innan du dyker ner i koden, se till att du har:

1. **Aspose.BarCode for Java‑licens** – skaffa en från [Aspose Purchase](https://purchase.aspose.com/buy).  
2. **Aspose.PDF‑licens** – krävs för PDF‑manipulation; du kan ansöka om en licens [här](https://purchase.aspose.com/temporary-license/).  
3. **Aspose.BarCode‑bibliotek** – ladda ner den senaste JAR‑filen från [här](https://releases.aspose.com/barcode/java/).  

Nu när du har de nödvändiga förutsättningarna, låt oss importera de erforderliga paketen och börja koda.

## Importera paket

I ditt Java‑projekt, lägg till Aspose.BarCode‑ och Aspose.PDF‑importerna. Detta block är oförändrat från den ursprungliga handledningen:

```java
import com.aspose.barcode.*;
import com.aspose.barcode.License;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.BaseDecodeType;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.pdf.*;
import com.aspose.pdf.facades.PdfExtractor;
import java.awt.image.BufferedImage;
import java.io.File;
import javax.imageio.ImageIO;
```

## Steg 1: Generera en streckkodsbild Java

Först skapar vi en streckkodsbild som vi senare kommer att bädda in i en PDF. Detta demonstrerar **generate barcode image java**‑funktionen.

```java
BarcodeGenerator builder = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_39_STANDARD);
builder.setCodeText("test123");
String strBarCodeImageSave = dataDir + "input_image1.jpg";
builder.save(strBarCodeImageSave);
```

## Steg 2: Skapa en PDF och lägg till streckkodsbilden

Därefter bygger vi ett nytt PDF‑dokument och infogar den streckkodsbild vi just genererade.

```java
Document pdf1 = new Document();
Page page = pdf1.getPages().add();
BufferedImage originalImage = ImageIO.read(new File(strBarCodeImageSave));
page.getResources().getImages().add(originalImage);
pdf1.save(strPdfDoc);
```

## Steg 3: Extrahera bilder från PDF Java

När PDF‑filen är klar måste vi hämta den inbäddade bilden igen så att streckkoden kan läsas. Detta använder **extract images from pdf java**.

```java
PdfExtractor extractor = new PdfExtractor();
extractor.bindPdf(strPdfDoc);
extractor.extractImage();
```

## Steg 4: Känn igen streckkoden från de extraherade bilderna

Slutligen matar vi varje extraherad bild till `BarCodeReader` för att hämta den kodade texten.

```java
String suffix = ".jpg";
int imageCount = 1;

while (extractor.hasNextImage()) {
    System.out.println("Extracting image " + imageCount);
    strBarCodeImage = "tmpbarcode" + imageCount + suffix;
    extractor.getNextImage(strBarCodeImage);

    BarCodeReader reader = new BarCodeReader(strBarCodeImage, DecodeType.CODE_39_EXTENDED);

    for (BarCodeResult result : reader.readBarCodes()) {
        System.out.println("CodeText: " + result.getCodeText());
        System.out.println("Symbology type: " + result.getCodeType());
    }

    imageCount++;
}
```

Upprepa dessa steg efter behov och justera filnamn och sökvägar så att de passar din projektstruktur.

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|-------|--------|-----|
| **Ingen streckkod upptäckt** | Bildkvaliteten är för låg eller streckkoden för liten. | Öka bildens upplösning vid sparning (`builder.save(..., BarCodeImageFormat.JPEG, 300)`). |
| **`PdfExtractor` kastar ett undantag** | PDF‑filen hittades inte eller sökvägen är felaktig. | Verifiera att `strPdfDoc` pekar på en befintlig fil och att programmet har läsbehörighet. |
| **Licens inte tillämpad** | Aspose‑komponenter körs i provläge, vilket begränsar utdata. | Läs in licensfilerna i början av ditt program: `new License().setLicense("Aspose.BarCode.lic");` och på liknande sätt för Aspose.PDF. |

## Vanliga frågor (FAQ)

### Q: Kan jag använda Aspose.BarCode för Java utan licens?
Även om Aspose.BarCode kan användas utan licens rekommenderas det att skaffa en för full funktionalitet och för att följa licensvillkoren.

### Q: Hur kan jag få en tillfällig licens för Aspose.BarCode för Java?
Du kan få en tillfällig licens [här](https://purchase.aspose.com/temporary-license/).

### Q: Finns det några begränsningar för de streckkodstyper som stöds av Aspose.BarCode?
Aspose.BarCode stöder ett brett sortiment av streckkodstyper. Se dokumentationen för en komplett lista.

### Q: Finns det en provversion av Aspose.BarCode för Java?
Ja, du kan ladda ner provversionen från [här](https://releases.aspose.com/).

### Q: Var kan jag få support eller ställa frågor om Aspose.BarCode för Java?
Besök Aspose.BarCode‑[forumet](https://forum.aspose.com/c/barcode/13) för support och diskussioner.

## Slutsats

Grattis! Du har lärt dig hur du **läser streckkod från PDF i Java** med Aspose.BarCode, hur du **genererar streckkodsbild Java**, och hur du **extraherar bilder från PDF Java** för vidare bearbetning. Känn dig fri att utforska ytterligare funktioner såsom batch‑behandling, hantering av olika streckkodssymboler eller integration med andra Aspose‑produkter. För mer detaljer, se den officiella [dokumentationen](https://reference.aspose.com/barcode/java/).

---

**Senast uppdaterad:** 2026-04-08  
**Testat med:** Aspose.BarCode for Java 24.12, Aspose.PDF for Java 24.12  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
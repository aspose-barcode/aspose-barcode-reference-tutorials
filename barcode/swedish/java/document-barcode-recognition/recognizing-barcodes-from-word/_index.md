---
date: 2026-04-12
description: Lär dig hur du känner igen streckkoder i Word-dokument med Aspose.BarCode
  för Java. Den här guiden visar också hur du lägger till streckkod i Word och extraherar
  bilder från Word.
keywords:
- how to recognize barcode
- add barcode to word
- read barcode from image
- extract images from word
- barcode detection java
linktitle: Känna igen streckkoder från Word-dokument
second_title: Aspose.BarCode Java API
title: Hur man känner igen streckkod från Word-dokument – Java-guide
url: /sv/java/document-barcode-recognition/recognizing-barcodes-from-word/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så känner du igen streckkod från Word-dokument – Java-guide

## Introduktion

Om du behöver **how to recognize barcode** inbäddad i en Microsoft Word‑fil, har du kommit till rätt ställe. I den här handledningen går vi igenom ett komplett, end‑to‑end‑exempel som använder Aspose.BarCode for Java för att generera en streckkod, infoga den i ett Word‑dokument, extrahera bilden igen, och slutligen läsa streckkodens data. I slutet kommer du också att se hur man **add barcode to Word**, **extract images from Word**, och utför **barcode detection java**‑liknande operationer — allt med bara några rader kod.

## Snabba svar
- **What library is required?** Aspose.BarCode for Java (plus Aspose.Words for handling .docx files).  
- **Can I read a barcode from an image?** Yes – the `BarCodeReader` can decode images extracted from Word.  
- **Do I need a license for production?** A commercial license is required; a free trial is available.  
- **Which Java version is supported?** Any JDK 8 + runtime works.  
- **How long does the implementation take?** Roughly 10‑15 minutes for a basic prototype.

## Vad är streckkodigenkänning från ett Word‑dokument?

Streckkodigenkänning innebär att skanna en bild som finns i en Word‑fil och konvertera det visuella mönstret tillbaka till dess ursprungliga datasträng (t.ex. “test‑123”). Aspose.BarCode tillhandahåller avkodningsmotorn, medan Aspose.Words låter oss hämta bilden ur .doc/.docx‑behållaren.

## Varför använda Aspose.BarCode för Java?

- **High accuracy** över 60+ symbologier, inklusive Code 39, QR, DataMatrix osv.  
- **No external dependencies** – ren Java, inga inhemska bibliotek.  
- **Seamless integration** med Aspose.Words, vilket gör det enkelt att **extract images from Word** och sedan **read barcode from image**.  
- **Robust licensing** som fungerar i skrivbords-, server- och molnmiljöer.

## Förutsättningar

- **Java Development Kit (JDK)** – senaste versionen rekommenderas.  
- **Aspose.BarCode for Java** – ladda ner och installera biblioteket från den officiella sidan [här](https://releases.aspose.com/barcode/java/).  
- **IDE** – IntelliJ IDEA, Eclipse eller någon annan editor du föredrar.

## Importera paket

I ditt Java‑projekt, importera de nödvändiga Aspose.BarCode‑ och Aspose.Words‑klasserna:

```java
import java.text.MessageFormat;

import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.barcode.generation.BarcodeGenerator;
import com.aspose.words.ImageType;
import com.aspose.words.NodeCollection;
import com.aspose.words.NodeType;
```

## Steg 1: Generera en streckkodsbild

Först, skapa en streckkodsbild som vi senare kommer att bädda in i Word‑filen.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText("test-123");
String strBarCodeImageSave = dataDir + "img.jpg";
generator.save(strBarCodeImageSave);
```

## Steg 2: Lägg till streckkoden i ett Word‑dokument

Nu kommer vi att infoga den nygenererade bilden i ett nytt Word‑dokument. Detta demonstrerar scenariot **add barcode to word**.

```java
Document doc = new Document();
DocumentBuilder docBuilder = new DocumentBuilder(doc);
docBuilder.insertImage(strBarCodeImageSave);
String strWordFile = "docout.doc";
doc.save(dataDir + strWordFile);
```

## Steg 3: Extrahera bilder och identifiera streckkoden

När dokumentet har sparats kan vi hämta varje bild (inklusive vår streckkod) och köra **barcode detection java** på var och en.

```java
NodeCollection<Shape> shapes = doc.getChildNodes(NodeType.SHAPE, true);
int imageIndex = 0;

for (Shape shape : shapes) {
    if (shape.hasImage()) {
        // Extract image to file
        String extension = ImageTypeToExtension(shape.getImageData().getImageType());
        String imageFileName = MessageFormat.format("Image.ExportImages.{0} Out.{1}", imageIndex, extension);
        String strBarCodeImageExtracted = "" + imageFileName;
        shape.getImageData().save(strBarCodeImageExtracted);

        // Recognize barcode from this image
        BarCodeReader reader = new BarCodeReader(strBarCodeImageSave, DecodeType.CODE_39_STANDARD);
        for (BarCodeResult result : reader.readBarCodes()) {
            System.out.println("CodeText: " + result.getCodeText());
            System.out.println("Symbology type: " + result.getCodeType());
        }
        imageIndex++;
    }
}
```

> **Pro tip:** Om du behöver **read barcode from image** filer som inte ligger i ett Word‑dokument, skicka helt enkelt filvägen till `BarCodeReader` – samma avkodningslogik gäller.

## Vanliga problem och lösningar

| Problem | Orsak | Åtgärd |
|-------|-------|-----|
| `NullPointerException` on `shape.getImageData()` | Shape does not contain an image. | Add a `shape.hasImage()` check (already shown). |
| Wrong barcode type returned | Using the wrong `DecodeType`. | Match the `EncodeTypes` you used when generating (e.g., `CODE_39_STANDARD`). |
| Image not saved correctly | Missing write permissions in `dataDir`. | Ensure the directory exists and is writable. |
| License not applied | Evaluation mode limits functionality. | Load your Aspose license at application start: `License license = new License(); license.setLicense("Aspose.Total.Java.lic");` |

## Vanliga frågor

### Q: Kan jag använda Aspose.BarCode för Java i kommersiella projekt?  
A: Ja, Aspose.BarCode för Java är tillgängligt för kommersiell användning. Du kan hitta licensinformation [här](https://purchase.aspose.com/buy).

### Q: Finns det en gratis provversion tillgänglig för Aspose.BarCode för Java?  
A: Ja, du kan utforska funktionerna i Aspose.BarCode för Java genom att ladda ner gratisprovversionen [här](https://releases.aspose.com/).

### Q: Hur får jag support för Aspose.BarCode för Java?  
A: För hjälp eller frågor, besök Aspose.BarCode‑forumet [här](https://forum.aspose.com/c/barcode/13).

### Q: Finns tillfälliga licenser tillgängliga för Aspose.BarCode för Java?  
A: Ja, du kan skaffa tillfälliga licenser [här](https://purchase.aspose.com/temporary-license/).

### Q: Var kan jag hitta dokumentationen för Aspose.BarCode för Java?  
A: Se den omfattande dokumentationen [här](https://reference.aspose.com/barcode/java/).

---  

**Senast uppdaterad:** 2026-04-12  
**Testad med:** Aspose.BarCode 24.11 for Java  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
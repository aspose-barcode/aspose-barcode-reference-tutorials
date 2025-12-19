---
date: 2025-12-19
description: Lär dig hur du läser streckkoder i Java från Word‑dokument med Aspose.BarCode.
  Denna guide täcker generering av streckkods­bilder, infogning av dem i Word och
  extrahering av bilder för streckkodsläsning.
linktitle: read barcode java from Word Documents
second_title: Aspose.BarCode Java API
title: Hur man läser streckkoder i Java från Word‑dokument
url: /sv/java/document-barcode-recognition/recognizing-barcodes-from-word/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så läser du streckkod java från Word‑dokument

## Introduktion

Att arbeta med streckkoder i Java‑applikationer är ett vanligt behov, särskilt när streckkoderna är inbäddade i Microsoft Word‑filer. I den här handledningen lär du dig **hur du läser streckkod java** från ett Word‑dokument med Aspose.BarCode for Java. Vi går igenom hur du genererar en streckkodsbild, lägger till streckkoden i ett Word‑dokument, extraherar bilder från Word‑filen och slutligen avkodar streckkoden med ett Java‑streckkodsläsare‑exempel.

## Snabba svar
- **Vilket bibliotek används?** Aspose.BarCode for Java (tillsammans med Aspose.Words för bildhantering)  
- **Kan jag lägga till streckkod i Word?** Ja – generera bilden och infoga den med Aspose.Words  
- **Hur extraherar jag bilder från Word?** Använd `Document.getChildNodes(NodeType.SHAPE, true)`  
- **Finns det ett Java‑streckkodsläsare‑exempel?** Koden i Steg 3 visar ett komplett exempel  
- **Vad krävs?** JDK, Aspose.BarCode for Java, en IDE (Eclipse/IntelliJ)

## Vad är streckkodigenkänning i Java?
Streckkodigenkänning i Java avser processen att upptäcka och avkoda streckkodssymboler från bilder eller dokument med ett bibliotek som Aspose.BarCode. Det gör det möjligt för applikationer att automatiskt läsa produktkoder, lager‑ID:n eller annan kodad data utan manuell inmatning.

## Varför läsa streckkod java från Word‑dokument?
Att bädda in streckkoder direkt i Word‑filer är användbart för kontrakt, fraktetiketter eller rapporter där en visuell representation av koden krävs. Att kunna **extrahera bilder från Word** och avkoda dem programmässigt eliminerar behovet av manuell skanning och minskar fel.

## Förutsättningar

Innan vi börjar, se till att du har:

- **Java Development Kit (JDK)** – ett aktuellt JDK installerat på din maskin.  
- **Aspose.BarCode for Java** – ladda ner biblioteket från den officiella sidan [here](https://releases.aspose.com/barcode/java/).  
- **Integrated Development Environment (IDE)** – exempelvis Eclipse eller IntelliJ IDEA för att skriva och köra koden.

## Importera paket

I ditt Java‑projekt importerar du de nödvändiga Aspose.BarCode‑ och Aspose.Words‑paketen:

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

## Steg 1: Generera en streckkodsbild (generate barcode image java)

Skapa först en streckkodsbild med Aspose.BarCode. Denna bild kommer senare att **added barcode to word**:

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText("test-123");
String strBarCodeImageSave = dataDir + "img.jpg";
generator.save(strBarCodeImageSave);
```

## Steg 2: Infoga streckkodsbilden i ett Word‑dokument (insert image into word)

Nu använder vi Aspose.Words för att **insert image into word** och sparar dokumentet:

```java
Document doc = new Document();
DocumentBuilder docBuilder = new DocumentBuilder(doc);
docBuilder.insertImage(strBarCodeImageSave);
String strWordFile = "docout.doc";
doc.save(dataDir + strWordFile);
```

## Steg 3: Känn igen streckkoder från Word‑dokumentet (java barcode reader example)

Till sist extraherar vi varje bild från Word‑filen och kör **java barcode reader example** för att avkoda streckkoden:

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

> **Obs:** Loopen ovan demonstrerar **extract images from word**, sparar varje bild och avkodar sedan streckkoden med samma bildsökväg. Anpassa filvägarna (`dataDir`) efter din miljö.

## Vanliga problem & tips

- **Felaktiga filvägar** – Säkerställ att `dataDir` pekar på en giltig mapp; annars kastar läsaren ett `FileNotFoundException`.  
- **Streckkodstyper som inte stöds** – Exemplet använder `CODE_39_STANDARD`. Om du behöver QR, DataMatrix osv. ändrar du både `EncodeTypes` och `DecodeType` därefter.  
- **Prestanda** – För stora dokument, överväg att bearbeta bilder i parallella strömmar för att snabba upp igenkänning.

## Vanliga frågor (FAQ)

### Q: Kan jag använda Aspose.BarCode for Java i kommersiella projekt?
Ja, Aspose.BarCode for Java är tillgängligt för kommersiell användning. Licensinformation finns [here](https://purchase.aspose.com/buy).

### Q: Finns det en gratis provversion av Aspose.BarCode for Java?
Ja, du kan prova funktionerna i Aspose.BarCode for Java genom att ladda ner den fria provversionen [here](https://releases.aspose.com/).

### Q: Hur får jag support för Aspose.BarCode for Java?
För hjälp eller frågor, besök Aspose.BarCode‑forumet [here](https://forum.aspose.com/c/barcode/13).

### Q: Finns det temporära licenser för Aspose.BarCode for Java?
Ja, temporära licenser kan erhållas [here](https://purchase.aspose.com/temporary-license/).

### Q: Var hittar jag dokumentationen för Aspose.BarCode for Java?
Se den omfattande dokumentationen [here](https://reference.aspose.com/barcode/java/).

## Ytterligare FAQ

**Q: Kan jag läsa andra streckkodssymboler än Code 39?**  
A: Absolut. Ändra bara `EncodeTypes` när du genererar och `DecodeType` när du läser för att matcha önskad symbol (t.ex. `EncodeTypes.QR`, `DecodeType.QR`).

**Q: Fungerar detta även med .docx‑filer?**  
A: Ja. Aspose.Words hanterar både `.doc`‑ och `.docx`‑format transparent; samma kod fungerar för båda.

**Q: Hur kan jag förbättra igenkänningsnoggrannheten för lågupplösta bilder?**  
A: Öka DPI när du sparar streckkodsbilden (`generator.save(strBarCodeImageSave, BarCodeImageFormat.JPEG, 300)`) eller använd ett högkvalitativt bildformat som PNG.

---

**Senast uppdaterad:** 2025-12-19  
**Testat med:** Aspose.BarCode for Java 24.11 och Aspose.Words for Java 24.11  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2025-12-13
description: Lär dig hur du skapar patch-streckkod i Java med Aspose.BarCode – ett
  Java-streckkodsgeneratorexempel som visar hur du genererar patch-kod och ställer
  in patch-format.
linktitle: Generating a Patch Code in Java
second_title: Aspose.BarCode Java API
title: Skapa Patch‑streckkod Java – Generera Patch‑kod med Aspose.BarCode
url: /sv/java/barcode-configuration/generating-patch-code/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa Patch-streckkod Java med Aspose.BarCode

## Introduktion

I den här omfattande guiden kommer du att **create patch barcode java** snabbt och pålitligt med Aspose.BarCode för Java. Oavsett om du bygger ett dokument‑hanteringssystem eller behöver ett kompakt sätt att lagra data på papper, är generering av en Patch Code en praktisk lösning. Vi går igenom ett **java barcode generator example**, förklarar **how to generate patch code**, och visar **how to set patch format** så att du kan anpassa resultatet efter dina exakta krav.

## Snabba svar
- **Vad bibliotek är bäst för patch codes?** Aspose.BarCode for Java
- **Hur många kodrader behövs?** Ungefär 20 rader för ett grundexempel
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion
- **Kan jag ändra sidstorlek?** Ja, med `PatchFormat` (t.ex. US_LETTER, A4)
- **Stödda bildformat?** BMP, PNG, JPEG, GIF och fler

## Vad är en Patch Code?
En Patch Code är en tvådimensionell streckkod bestående av fyra separata paneler som kan skrivas ut på en enda sida. Den är idealisk för indexering av stora volymer dokument eftersom varje panel kan skannas oberoende.

## Varför använda Aspose.BarCode för Java?
- **Full‑featured API** – stöder alla större streckkodstyper, inklusive Patch Code.
- **Easy customization** – ändra storlek, format, marginaler och mer med enkla egenskapsanrop.
- **Cross‑platform** – fungerar i alla Java‑aktiverade miljöer, från skrivbordsapplikationer till webbtjänster.

## Förutsättningar

Innan vi börjar, se till att du har följande:

- **Java Development Environment** – JDK 8 eller senare installerat.
- **Aspose.BarCode for Java** – Ladda ner från [download link](https://releases.aspose.com/barcode/java/).
- **IDE or Text Editor** – Valfri Java‑kompatibel editor (IntelliJ IDEA, Eclipse, VS Code, etc.).

## Importera paket

För att börja, importera de nödvändiga klasserna. Kodsnutten nedan visar exakt vad du behöver:

```java
import com.aspose.barcode.generation.PatchFormat;
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.MarginsF;
```

### Steg 1: Generera en grundläggande Patch Code

Detta **java barcode generator example** skapar en enkel Patch Code och sparar den som en BMP‑bild.

```java
public static void generatePatchCode() throws IOException {
    String dataDir = "Your Document Directory";
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.PATCH_CODE, "Patch T");
    generator.save(dataDir + "patch.bmp");
}
```

I den här metoden:

1. Definiera utdatamappen (`dataDir`).
2. Skapa en instans av `BarcodeGenerator` med `EncodeTypes.PATCH_CODE` och texten `"Patch T"`.
3. Spara den genererade bilden till disk.

### Steg 2: Hur man ställer in Patch Format

Om du behöver en specifik papperstorlek kan du ställa in formatet innan du sparar. Detta demonstrerar **how to set patch format** till US Letter.

```java
public static void setPatchFormat() throws IOException {
    String dataDir = "Your Document Directory";
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.PATCH_CODE, "Patch T");
    generator.getParameters().getBarcode().getPatchCode().setPatchFormat(PatchFormat.US_LETTER);
    generator.save(dataDir + "patch.bmp");
}
```

### Steg 3: Generera hel sida (Sätt ihop alla paneler)

Nedan är den fullständiga rutinen som skapar varje panel, sätter ihop dem till en komplett sida och skriver den slutliga PNG‑filen. Här ser du **how to generate patch code** för en layout med flera paneler.

```java
public static void generateWholePage() throws IOException {
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.PATCH_CODE, "Patch T");
    // Set image width, padding, and other parameters
    // ... (refer to the provided code for details)

    // Generate different parts of the Patch Code
    BufferedImage topImg = generator.generateBarCodeImage();
    // ... (similar steps for leftImg, bottomImg, and rightImg)

    // Create a frame and assemble the Patch Code
    BufferedImage frameImg = new BufferedImage(topImg.getWidth(), rightImg.getHeight() + 2 * topImg.getHeight(),
            rightImg.getType());
    // ... (refer to the provided code for details)

    // Save the Patch Code frame
    File outputfile = new File("Your Document Directory");
    ImageIO.write(frameImg, "png", outputfile);
}
```

#### Vanliga problem & tips
- **Incorrect directory path** – Se till att `dataDir` slutar med en filseparator (`/` eller `\\`).
- **Missing permissions** – Applikationen måste ha skrivrättigheter till målmappen.
- **Image quality** – Justera DPI via `generator.getParameters().getImageInfo().setResolutionX/Y()` om det behövs.

## Vanliga frågor

**Q: Kan jag använda Aspose.BarCode för Java i kommersiella projekt?**  
A: Ja, en kommersiell licens krävs för produktionsanvändning. Du kan köpa en på [Aspose's purchase page](https://purchase.aspose.com/buy).

**Q: Finns det en gratis provversion tillgänglig?**  
A: Absolut. Ladda ner en provversion från [Aspose's release page](https://releases.aspose.com/).

**Q: Hur får jag support?**  
A: Besök [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) för community‑hjälp och officiella supportkanaler.

**Q: Är tillfälliga licenser ett alternativ?**  
A: Ja, tillfälliga licenser erbjuds via [Aspose's temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: Var kan jag hitta den fullständiga API‑referensen?**  
A: Dokumentationen finns på [Aspose.BarCode for Java documentation](https://reference.aspose.com/barcode/java/).

---

**Senast uppdaterad:** 2025-12-13  
**Testad med:** Aspose.BarCode for Java 24.12 (senaste)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
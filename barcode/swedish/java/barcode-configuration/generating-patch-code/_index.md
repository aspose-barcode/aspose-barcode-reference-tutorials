---
date: 2026-02-15
description: Lär dig hur du skapar patch‑streckkod i Java med Aspose.BarCode – ett
  Java‑streckkodsgeneratordexempel som visar hur du genererar patchkod och ställer
  in patchformat.
linktitle: Generating a Patch Code in Java
second_title: Aspose.BarCode Java API
title: Skapa Patch-streckkod Java – Generera Patch-kod med Aspose.BarCode
url: /sv/java/barcode-configuration/generating-patch-code/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa Patch-streckkod Java med Aspose.BarCode

## Introduktion

I den här omfattande guiden kommer du att **create patch barcode java** snabbt och pålitligt med Aspose.BarCode för Java. Oavsett om du bygger ett dokument‑hanteringssystem, behöver ett kompakt sätt att lagra metadata på papper, eller letar efter en hög‑densitets 2‑D streckkodslösning, är generering av en Patch Code ett praktiskt val. Vi går igenom ett **java barcode generator example**, förklarar **how to generate patch code**, och visar **how to set patch format** så att du kan anpassa resultatet efter dina exakta krav.

## Snabba svar
- **Vilket bibliotek är bäst för patch-koder?** Aspose.BarCode for Java
- **Hur många kodrader behövs?** Ungefär 20 rader för ett grundexempel
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion
- **Kan jag ändra sidstorlek?** Ja, med `PatchFormat` (t.ex. US_LETTER, A4)
- **Stödda bildformat?** BMP, PNG, JPEG, GIF och fler

## Vad är en Patch Code?

En Patch Code är en tvådimensionell streckkod bestående av fyra separata paneler som kan skrivas ut på en enda sida. Varje panel kan skannas oberoende, vilket gör den idealisk för indexering av stora volymer dokument samtidigt som det fysiska fotavtrycket hålls litet.

## Varför använda Aspose.BarCode för Java?

- **Full‑featured API** – stöder alla stora streckkodstyper, inklusive Patch Code.
- **Easy customization** – ändra storlek, format, marginaler och mer med enkla egenskapsanrop.
- **Cross‑platform** – fungerar i alla Java‑aktiverade miljöer, från skrivbordsapplikationer till webbtjänster.
- **Robust documentation** – omfattande exempel och API‑referens hjälper dig att snabbt komma igång.

## Förutsättningar

- **Java Development Environment** – JDK 8 eller senare installerat.
- **Aspose.BarCode for Java** – Ladda ner från [download link](https://releases.aspose.com/barcode/java/).
- **IDE eller Textredigerare** – Valfri Java‑kompatibel redigerare (IntelliJ IDEA, Eclipse, VS Code, etc.).
- **Skrivbehörigheter** till den mapp där du planerar att spara de genererade bilderna.

## Importera paket

För att börja, importera de nödvändiga klasserna. Kodsnutten nedan visar exakt vad du behöver:

```java
import com.aspose.barcode.generation.PatchFormat;
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.MarginsF;
```

## Hur man skapar patch barcode java – steg för steg

Nedan är en tydlig, numrerad genomgång som kopplar varje kodblock till en konkret handling. Kopiera gärna snuttarna ordagrant; de är redo att köras så snart du ersätter platshållarmappen.

### Steg 1: Generera en grundläggande Patch Code

Detta **java barcode generator example** skapar en enkel Patch Code och sparar den som en BMP‑bild.

```java
public static void generatePatchCode() throws IOException {
    String dataDir = "Your Document Directory";
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.PATCH_CODE, "Patch T");
    generator.save(dataDir + "patch.bmp");
}
```

**Vad händer här?**
1. `dataDir` pekar på den mapp där bilden kommer att skrivas.
2. `BarcodeGenerator` instansieras med `EncodeTypes.PATCH_CODE` och texten "Patch T".
3. `save` skriver streckkoden till `patch.bmp`.

### Steg 2: Ställ in Patch-format (pappersstorlek)

Om du behöver en specifik pappersstorlek kan du ange formatet innan du sparar. Detta demonstrerar **how to set patch format** till US Letter.

```java
public static void setPatchFormat() throws IOException {
    String dataDir = "Your Document Directory";
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.PATCH_CODE, "Patch T");
    generator.getParameters().getBarcode().getPatchCode().setPatchFormat(PatchFormat.US_LETTER);
    generator.save(dataDir + "patch.bmp");
}
```

**Varför ange formatet?**  
Patch Code‑paneler ordnas baserat på den valda sidstorleken. Genom att använda `PatchFormat.US_LETTER` säkerställer du att panelerna passar korrekt på ett standardark i letter‑storlek.

### Steg 3: Generera en hel sida (sammanfoga alla paneler)

Nedan är den fullständiga rutinen som skapar varje panel, sammanfogar dem till en komplett sida och skriver den slutliga PNG‑filen. Här ser du **how to generate patch code** för en layout med flera paneler.

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

**Viktiga punkter att notera**
- Metoden genererar fyra separata bilder (`topImg`, `leftImg`, `bottomImg`, `rightImg`) som representerar varje panel.
- En större `frameImg`‑canvas skapas för att sy ihop panelerna.
- Den slutliga PNG‑filen skrivs till den mapp du angav.

## Vanliga problem & tips

- **Felaktig katalogsökväg** – Säkerställ att `dataDir` slutar med en filseparator (`/` eller `\\`).
- **Saknade behörigheter** – Applikationen måste ha skrivbehörighet till målmappen.
- **Bildkvalitet** – Justera DPI via `generator.getParameters().getImageInfo().setResolutionX/Y()` om du behöver högre upplösning för skanning.
- **Minnesanvändning** – Vid generering av stora sidor, överväg att anropa `System.gc()` efter sparning för att frigöra bildbuffertar.

## Vanliga frågor

**Q: Kan jag använda Aspose.BarCode för Java i kommersiella projekt?**  
A: Ja, en kommersiell licens krävs för produktionsanvändning. Du kan köpa en på [Aspose's purchase page](https://purchase.aspose.com/buy).

**Q: Finns en gratis provversion tillgänglig?**  
A: Absolut. Ladda ner en provversion från [Aspose's release page](https://releases.aspose.com/).

**Q: Hur får jag support?**  
A: Besök [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) för gemenskapsstöd och officiella supportkanaler.

**Q: Är tillfälliga licenser ett alternativ?**  
A: Ja, tillfälliga licenser erbjuds via [Aspose's temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: Var kan jag hitta den fullständiga API‑referensen?**  
A: Dokumentationen finns på [Aspose.BarCode for Java documentation](https://reference.aspose.com/barcode/java/).

## Ytterligare resurser

- **Sample Projects** – Utforska det officiella Aspose.BarCode GitHub‑arkivet för fullständiga exempel.  
- **Performance Tips** – Använd `generator.getParameters().getImageInfo().setResolutionX(300)` för högupplösta skanningar.  
- **Next Steps** – Efter att ha bemästrat Patch Code, prova andra 2‑D streckkoder som QR Code eller Data Matrix med samma generator‑klass.

---

**Senast uppdaterad:** 2026-02-15  
**Testad med:** Aspose.BarCode for Java 24.12 (senaste)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
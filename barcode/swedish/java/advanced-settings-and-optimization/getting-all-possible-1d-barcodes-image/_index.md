---
date: 2025-11-29
description: Lär dig hur du läser 1D‑streckkoder i Java med Aspose.BarCode – avkoda
  streckkoder från bild snabbt med ett robust streckkodsbibliotek för Java.
language: sv
linktitle: read 1d barcodes java
second_title: Aspose.BarCode Java API
title: Hur man läser 1D‑streckkoder i Java med Aspose.BarCode
url: /java/advanced-settings-and-optimization/getting-all-possible-1d-barcodes-image/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# läs 1d streckkoder java med Aspose.BarCode

## Introduktion

I den här praktiska guiden kommer du att upptäcka hur du **läser 1D streckkoder i Java** med det kraftfulla **Aspose.BarCode**‑biblioteket. Oavsett om du behöver skanna produktetiketter, lageretiketter eller någon annan linjär streckkod som är inbäddad i en bild, går den här tutorialen igenom varje steg – från att sätta upp miljön till att extrahera varje möjlig streckkod som bilden innehåller. I slutet kommer du att kunna **avkoda streckkoder från bild**‑filer med bara några rader Java‑kod.

## Snabba svar
- **Vad gör Aspose.BarCode?** Det erbjuder ett komplett streckkodsbibliotek för Java som kan generera och avkoda 1D/2D streckkoder.  
- **Kan jag läsa flera streckkoder från en bild?** Ja – metoden `BarCodeReader.readBarCodes()` returnerar alla upptäckta symboler.  
- **Behöver jag en licens för utveckling?** En tillfällig licens fungerar för testning; en kommersiell licens krävs för produktion.  
- **Vilka Java‑versioner stöds?** Java 8 + (JDK 11 rekommenderas).  
- **Är detta bibliotek snabbt nog för real‑tids‑skanning?** Absolut – det är optimerat för högpresterande batch‑bearbetning.

## Vad är “read 1d barcodes java”?

Att läsa 1D streckkoder i Java innebär att använda ett **streckkodsbibliotek för Java** för att analysera en bild, lokalisera linjära streckkodsmönster och returnera den kodade texten samt metadata såsom symbology‑typ och orientering. Aspose.BarCode abstraherar det tunga bildbehandlingsarbetet, så att du kan fokusera på affärslogiken.

## Varför välja Aspose.BarCode för avkodning av streckkoder från bild?

- **Brett stöd för symbologier** – över 50 1D‑ och 2D‑typer.  
- **Noggrann detektion** – fungerar även med lågkontrast eller roterade streckkoder.  
- **Enkel API** – några metodanrop ger dig alla resultat.  
- **Inga externa beroenden** – ren Java, lätt att bädda in i vilket projekt som helst.  

## Förutsättningar

Innan vi dyker ner i koden, se till att du har följande:

- **Java Development Kit (JDK)** – version 8 eller nyare. Ladda ner det från den officiella [Oracle JDK‑sidan](https://www.oracle.com/java/technologies/javase-downloads.html).  
- **Aspose.BarCode för Java** – hämta den senaste JAR‑filen från [Aspose release‑sidan](https://releases.aspose.com/barcode/java/).  

Nu när din miljö är klar, låt oss börja koda.

## Import Namespaces

Lägg till de nödvändiga `import`‑satserna så att kompilatorn kan hitta Asposes klasser.

```java
import java.awt.Point;

import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## Steg 1: Initiera BarCodeReader‑objektet

Skapa en `BarCodeReader`‑instans som pekar på din bildfil. Parametern `DecodeType` talar om för motorn vilka symbologier den ska leta efter; att använda `CODE_128` som exempel fungerar för många vanliga 1D‑koder.

```java
BarCodeReader reader = new BarCodeReader("path/to/your/image.png", DecodeType.CODE_128);
```

> **Proffstips:** Om du vill skanna *alla* stödjade 1D‑typer, skicka `DecodeType.ALL_1D` istället för en enskild symbologi.

## Steg 2: Läs alla möjliga streckkoder

Iterera genom samlingen som returneras av `readBarCodes()`. För varje `BarCodeResult` skriver vi ut den avkodade texten, symbologinamnet, detektionsvinkeln och de fyra hörnkoordinaterna för streckkodsområdet.

```java
int iCount = 0;
for (BarCodeResult result : reader.readBarCodes()) {
    // Display code text, symbology, detected angle, recognition percentage of the barcode
    System.out.println("Code Text: " + result.getCodeText() + " Symbology: " + result.getCodeTypeName()
            + " Recognition percentage: " + result.getRegion().getAngle());

    // Display x and y coordinates of barcode detected
    Point[] point = result.getRegion().getPoints();

    System.out.println("Top left coordinates: X = " + point[0].getX() + ", Y = " + point[0].getY());
    System.out.println("Bottom left coordinates: X = " + point[1].getX() + ", Y = " + point[1].getY());
    System.out.println("Bottom right coordinates: X = " + point[2].getX() + ", Y = " + point[2].getY());
    System.out.println("Top right coordinates: X = " + point[3].getX() + ", Y = " + point[3].getY());

    iCount = iCount + 1;
}
```

Loopen bearbetar automatiskt varje streckkod som hittas, så du behöver inte anropa läsaren upprepade gånger. När loopen är klar innehåller `iCount` det totala antalet upptäckta streckkoder.

## Vanliga problem & hur du löser dem

| Symptom | Trolig orsak | Lösning |
|---------|--------------|----------|
| Inga streckkoder returneras | Bilden är för suddig eller har låg kontrast | Förbehandla bilden (öka kontrast, binarisera) innan du skickar den till läsaren. |
| Fel symbologi rapporteras | Fel `DecodeType` användes | Använd `DecodeType.ALL_1D` så att motorn automatiskt upptäcker vilken 1D‑typ som helst. |
| Vinkelvärdena är felaktiga | Bilden är roterad | API:t returnerar redan rotationsvinkeln; du kan rotera bilden tillbaka om så behövs. |

## Vanliga frågor

**Q: Är Aspose.BarCode för Java lämplig för kommersiella projekt?**  
A: Ja. En kommersiell licens tar bort alla utvärderingsbegränsningar och ger dig fulla distributionsrättigheter.

**Q: Kan jag testa biblioteket utan att köpa en licens?**  
A: Absolut. Skaffa en tillfällig licens från [Aspose tillfällig‑licens‑sida](https://purchase.aspose.com/temporary-license/) för utveckling och testning.

**Q: Var kan jag hitta den fullständiga API‑referensen?**  
A: Den omfattande dokumentationen finns [här](https://reference.aspose.com/barcode/java/).

**Q: Hur får jag hjälp om jag stöter på ett problem?**  
A: Ställ din fråga på [Aspose.BarCode‑forumet](https://forum.aspose.com/c/barcode/13) där communityn och Aspose‑ingenjörer kan hjälpa dig.

**Q: Finns det en gratis provnedladdning?**  
A: Ja – du kan ladda ner en provversion från [Aspose releases‑sidan](https://releases.aspose.com/).

## Slutsats

Du har nu lärt dig hur du **läser 1D streckkoder i Java** med Aspose.BarCode, ett robust **streckkodsbibliotek för Java** som gör avkodning av streckkoder från bildfiler enkel och pålitlig. Integrera detta kodexempel i dina egna applikationer för att automatisera lagerinventering, biljettvalidering eller någon annan situation där linjära streckkoder förekommer i bilder.

---

**Senast uppdaterad:** 2025-11-29  
**Testat med:** Aspose.BarCode 24.11 för Java  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
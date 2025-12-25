---
date: 2025-12-25
description: Lär dig hur du extraherar text från streckkodsbilder, specifikt PDF417
  med kinesiska tecken, med Aspose.BarCode för Java. Följ vår steg‑för‑steg‑guide
  för hur du läser streckkodsdata effektivt.
linktitle: 'Extract Text from Barcode: PDF417 Chinese Characters'
second_title: Aspose.BarCode Java API
title: 'Extrahera text från streckkod: PDF417 kinesiska tecken i Java'
url: /sv/java/multilingual-support/recognizing-pdf417-chinese-characters/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extrahera text från streckkod: PDF417 kinesiska tecken i Java

## Introduktion

Att integrera streckkodigenkänning i Java‑applikationer är en värdefull färdighet, särskilt när du behöver **extract text from barcode**‑bilder som innehåller flerspråkig data. I den här handledningen går vi igenom hur du använder Aspose.BarCode för Java för att känna igen PDF417‑streckkoder med kinesiska tecken. När du är klar vet du exakt hur du läser streckkoddata och avkodar den till läsbar text.

## Snabba svar
- **Vilket bibliotek stödjer PDF417 med kinesiska tecken?** Aspose.BarCode för Java.  
- **Vilken teckenuppsättning behövs för kinesisk avkodning?** MS936 (GBK).  
- **Behöver jag en licens för produktionsbruk?** Ja, en kommersiell licens krävs.  
- **Kan jag köra detta på vilken Java‑version som helst?** Det fungerar med Java 8 och streckkod innebär att konvertera den kodade datan tillbaka till dess ursprungliga mänskligt läsbara form. För PDF417‑streckkoder som lagrar kinesiska tecken innebär detta också att välja rätt teckenkodning så att byte‑sekvensen motsvarar rätt tecken.

## Varför använda Aspose.BarCode för Java?

Aspose.BarCode erbjuder robust stöd för ett brett spektrum av streckkodssymboler, inklusive PDF417, och hanterar komplexa teckenuppsättningar direkt. Det abstraherar låg‑nivå bildbehandling, så att du kan fokusera på affärslogik istället för avkodningsdetaljer.

## Förutsättningar

1. **Java Development Kit (JDK)** – den senaste versionen rekommenderas.  
2. **Aspose.BarCode för Java** – ladda ner den från [here](https://releases.aspose.com/barcode/java/).  
3. **En PDF417‑streckkodbild** som innehåller kinesiska tecken (t.ex. `barcode.png`).

## Importera paket

I ditt Java‑projekt importerar du de nödvändiga klasserna för att arbeta med Aspose.BarCode:

```java
import java.nio.ByteBuffer;
import java.nio.charset.Charset;

import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## Steg 1: Ange dokumentkatalogen

Ange mappen där din streckkodbild finns:

```java
String dataDir = "Your Document Directory";
```

Byt ut `"Your Document Directory"` mot den faktiska sökvägen på din maskin.

## Steg 2: Ladda streckkodbilden

Skapa en `BarCodeReader`‑instans som pekar på PNG‑filen och instruerar läsaren att leta efter PDF417‑symbologi:

```java
BarCodeReader reader = new BarCodeReader(dataDir + "barcode.png", DecodeType.PDF_417);
```

## Steg 3: Läs streckkoden

Iterera genom detekteringsresultaten, hämta den råa byte‑arrayen och avkoda den med teckenkodningen GBK (MS936):

```java
for (BarCodeResult result : reader.readBarCodes()) {
    byte[] bytes = result.getCodeBytes();
    ByteBuffer bytebuf = ByteBuffer.wrap(bytes);
    System.out.println(Charset.forName("MS936").decode(bytebuf).toString());
}
```

Denna loop **extracts text from the barcode** och skriver ut de avkodade kinesiska tecknen till konsolen.

## Hur läser man streckkod med PDF417?

Koden ovan demonstrerar **how to read barcode**‑data steg för steg:

1. **Initialize** läsaren med rätt `DecodeType`.  
2. **Iterate** över varje `BarCodeResult` som returneras.  
3. **Convert** de råa bytena med rätt teckenuppsättning (`MS936` för kinesiska).  

Om din streckkod innehåller andra språk, byt helt enkelt teckenuppsättningen till den som matchar dina data.

## Vanliga problem & lösningar

| Problem | Lösning |
|-------|----------|
| Felaktiga tecken efter avkodning | Verifiera att du använder rätt teckenkodning (`MS936` för GBK). |
| Ingen streckkod upptäckt | Se till att bildkvaliteten är hög och att streckkoden inte är roterad; du kan förbehandla bilden vid behov. |
| Flera resultat returnerade | PDF417 kan lagra flera segment; iterera genom alla resultat som visas. |

## Vanliga frågor (FAQ)

### Kan jag använda Aspose.BarCode för Java i kommersiella projekt?
Ja, du kan använda Aspose.BarCode för Java i kommersiella projekt. För licensinformation, besök [here](https://purchase.aspose.com/buy).

### Finns en gratis provversion?
Ja, du kan få tillgång till en gratis provversion av Aspose.BarCode för Java [here](https://releases.aspose.com/).

### Hur får jag support för Aspose.BarCode?
Besök Aspose.BarCode‑forumet [here](https://forum.aspose.com/c/barcode/13) för support eller frågor.

### Kan jag få en tillfällig licens för testning?
Ja, du kan få en tillfällig licens [here](https://purchase.aspose.com/temporary-license/).

### Var kan jag hitta dokumentationen?
Dokumentationen finns tillgänglig [here](https://reference.aspose.com/barcode/java/).

**Ytterligare Q&A**

**Q: Vad händer om min streckkodbild är i JPEG‑format?**  
A: `BarCodeReader` fungerar med JPEG, PNG, BMP och andra vanliga bildformat – byt bara filändelsen därefter.

**Q: Kan jag avkoda streckkoder från en ström istället för en fil?**  
A: Ja, du kan skicka en `InputStream` till `BarCodeReader`‑konstruktorn för avkodning i realtid.

**Q: Stöder Aspose.BarCode andra teckenuppsättningar?**  
A: Absolut. Använd `Charset.forName("<your‑charset>")` för att avkoda byte‑sekvenser för UTF‑8, ISO‑8859‑1 osv.

## Slutsats

Du har nu lärt dig hur du **extract text from barcode**‑bilder, specifikt PDF417‑streckkoder som innehåller kinesiska tecken, med hjälp av Aspose.BarCode för Java. Denna funktion öppnar dörrar till flerspråkiga lagersystem, dokumentautomatisering och mer. Känn dig fri att experimentera med andra symboler och teckenuppsättningar för att bredda din applikations räckvidd.

---

**Last Updated:** 2025-12-25  
**Tested With:** Aspose.BarCode for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
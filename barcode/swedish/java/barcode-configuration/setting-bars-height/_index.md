---
date: 2025-12-16
description: Lär dig hur du skapar code_128-streckkod i Java med Aspose.BarCode, anpassar
  streckkodens storlek, ställer in stapelhöjden och genererar streckkodsbilder i Java
  på ett effektivt sätt.
linktitle: Setting Bars Height
second_title: Aspose.BarCode Java API
title: Hur man skapar code_128-streckkod och anger stapelhöjd i Java
url: /sv/java/barcode-configuration/setting-bars-height/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Inställning av stapelhöjd i Java

## Introduktion

I moderna Java‑applikationer behöver du ofta **create code_128 barcode**‑bilder som passar exakt den visuella designen av dina rapporter, etiketter eller kvitton. Aspose.BarCode for Java gör detta enkelt, låter dig **customize barcode size**, justera dimensioner och generera en streckkodbild som Java kan spara omedelbart. I den här handledningen går vi igenom hur du ställer in stapelhöjden när du genererar en CODE_128‑streckkod, så att du kan producera perfekt dimensionerade streckkoder varje gång.

## Snabba svar
- **Vad gör huvudmetoden?** Den skapar en CODE_128‑streckkod och låter dig ange dess stapelhöjd.  
- **Vilken klass används?** `BarcodeGenerator` från Aspose.BarCode‑biblioteket.  
- **Behöver jag en licens för testning?** En gratis provversion finns tillgänglig; en licens krävs för produktion.  
- **Kan jag ändra andra dimensioner?** Ja, du kan justera bredd, marginaler och andra storleksparametrar.  
- **Vilket format har utdata‑bilden?** Alla format som stöds av Aspose.BarCode (t.ex. JPEG, PNG).  

## Vad är en CODE_128‑streckkod och varför ange dess höjd?
CODE_128 är en högdensitets‑linjär streckkod som kodar hela ASCII‑uppsättningen. Att justera stapelhöjden är avgörande när streckkoden måste anpassas till fysiska etikettmått eller passa inom en UI‑komponent. Rätt höjd säkerställer läsbarhet för skannrar samtidigt som den visuella layouten förblir balanserad.

## Varför använda Aspose.BarCode för Java?
- **Full kontroll** över streckkodens dimensioner (höjd, bredd, marginaler).  
- **Brett formatstöd** – generera PNG, JPEG, BMP och mer.  
- **Inga externa beroenden** – ren Java‑bibliotek, enkelt att integrera.  
- **Rik API** – anpassa färger, text och felkorrigering utan ansträngning.

## Förutsättningar

Innan du börjar, se till att du har:

- En Java‑utvecklingsmiljö (JDK 8 eller högre).  
- Aspose.BarCode för Java – ladda ner det från [download link](https://releases.aspose.com/barcode/java/).  

## Importera paket

I ditt Java‑projekt importerar du huvudklassen som tillhandahåller streckkodsgenereringsfunktioner:

```java
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Hur man skapar code_128‑streckkod och anger dess höjd

### Steg 1: Initiera Barcode‑objektet

Skapa en `BarcodeGenerator`‑instans för en CODE_128‑streckkod med den data du vill koda (t.ex. “12345678”).

```java
// Instantiate barcode object
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");
```

### Steg 2: Justera streckkodsdimensioner – Ange stapelhöjd

Använd egenskapen `BarHeight` för att definiera höjden i millimeter. Detta är det primära sättet att **hur man ställer in stapelhöjd**.

```java
// Set the bar height to be 3 millimeters
generator.getParameters().getBarcode().getBarHeight().setMillimeters(3.0f);
```

> **Proffstips:** Du kan också modifiera `XDimension` för att ändra bredden på enskilda staplar, vilket ger dig full kontroll över **justera streckkodsdimensioner**.

### Steg 3: Spara streckkodsbilden – generera streckkodsbild java

Slutligen skriver du streckkoden till en fil. `save`‑metoden bestämmer automatiskt bildformatet från filändelsen.

```java
// Save the Barcode image to file
generator.save(dataDir + "barsHeight.jpg");
```

> **Obs:** Ersätt `dataDir` med den faktiska sökvägen där du vill lagra bilden.

## Vanliga användningsområden

- **Etikettutskrift** – Säkerställ att streckkoden passar inom en fördefinierad etikettstorlek.  
- **Fakturagenerering** – Bädda in en kompakt streckkod som matchar layouten på dina PDF‑fakturor.  
- **Mobila appar** – Generera dynamiskt streckkoder med exakta dimensioner för skanning på skärmen.

## Felsökning & tips

| Problem | Lösning |
|-------|----------|
| Streckkoden verkar för tunn eller för tjock | Justera `XDimension` via `generator.getParameters().getBarcode().getXDimension().setMillimeters(value)`. |
| Bilden är suddig | Öka DPI genom att anropa `generator.save(..., BarCodeImageFormat.JPEG, 300)`. |
| Skannern kan inte läsa koden | Verifiera att stapelhöjden uppfyller skannarens miniminivå (vanligtvis ≥ 2 mm). |

## Vanliga frågor

**Q: Kan jag anpassa streckkodstypen i Aspose.BarCode för Java?**  
A: Absolut! Biblioteket stöder många symbologier såsom QR, DataMatrix, PDF417 och fler—byt bara `EncodeTypes` i konstruktorn.

**Q: Är Aspose.BarCode kompatibel med olika Java‑IDE:n?**  
A: Ja, det fungerar sömlöst med Eclipse, IntelliJ IDEA, NetBeans och alla IDE:n som stödjer standard Java‑projekt.

**Q: Kan jag generera streckkoder med numeriska och alfanumeriska värden?**  
A: Ja, CODE_128 kan koda både numeriska och alfanumeriska data, vilket gör den mångsidig för de flesta tillämpningar.

**Q: Finns det en provversion av Aspose.BarCode för Java?**  
A: Ja, du kan utforska funktionerna i Aspose.BarCode genom att skaffa en gratis provversion [here](https://releases.aspose.com/).

**Q: Var kan jag hitta support för Aspose.BarCode för Java?**  
A: Besök Aspose.BarCode‑forumet [here](https://forum.aspose.com/c/barcode/13) för community‑support och diskussioner.

**Senast uppdaterad:** 2025-12-16  
**Testad med:** Aspose.BarCode for Java 24.12 (senaste)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
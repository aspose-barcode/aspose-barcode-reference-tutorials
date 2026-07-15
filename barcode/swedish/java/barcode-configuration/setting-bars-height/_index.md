---
date: 2026-02-15
description: Lär dig hur du skapar code128‑streckkod i Java med Aspose.BarCode, anpassar
  streckkodens storlek, justerar streckkodens dimensioner och genererar streckkodsbilder
  i Java på ett effektivt sätt.
linktitle: Setting Bars Height
second_title: Aspose.BarCode Java API
title: Hur man skapar code128‑streckkod i Java och ställer in stapelhöjd
url: /sv/java/barcode-configuration/setting-bars-height/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Inställning av stapelhöjd i Java

## Introduktion

Om du behöver **create code128 barcode java** för etikettutskrift, fakturor eller mobila appar, vill du ha full kontroll över dess visuella dimensioner. Aspose.BarCode for Java låter dig **customize barcode size**, ange den exakta stapelhöjden och omedelbart generera en streckkodsbild som passar dina designkrav. I den här handledningen går vi igenom hela processen för att skapa en CODE_128‑streckkod, justera dess höjd och spara bilden—så att du kan producera perfekt dimensionerade streckkoder varje gång.

## Snabba svar
- **Vad gör huvudmetoden?** Den skapar en CODE_128‑streckkod och låter dig ange dess stapelhöjd.  
- **Vilken klass används?** `BarcodeGenerator` från Aspose.BarCode‑biblioteket.  
- **Behöver jag en licens för testning?** En gratis provversion finns tillgänglig; en licens krävs för produktion.  
- **Kan jag ändra andra dimensioner?** Ja, du kan justera bredd, marginaler och andra storleksparametrar.  
- **Vilket format har utdata‑bilden?** Alla format som stöds av Aspose.BarCode (t.ex. JPEG, PNG).  

## Vad är en CODE_128‑streckkod och varför ange dess höjd?
CODE_128 är en högdensitets linjär streckkod som kodar hela ASCII‑uppsättningen. Att justera stapelhöjden är avgörande när streckkoden måste anpassas till fysiska etikettmått eller passa inom en UI‑komponent. Rätt höjd säkerställer läsbarhet för skannrar samtidigt som den visuella layouten förblir balanserad.

## Varför använda Aspose.BarCode för Java?
- **Full control** över streckkodens dimensioner (höjd, bredd, marginaler).  
- **Wide format support** – generera PNG, JPEG, BMP och mer.  
- **No external dependencies** – rent Java‑bibliotek, enkelt att integrera.  
- **Rich API** – anpassa färger, text och felkorrigering utan ansträngning.  

## Förutsättningar

Innan du börjar, se till att du har:

- En Java‑utvecklingsmiljö (JDK 8 eller högre).  
- Aspose.BarCode for Java – ladda ner det från [download link](https://releases.aspose.com/barcode/java/).  

## Importera paket

I ditt Java‑projekt importerar du huvudklassen som tillhandahåller streckkodsgenereringsfunktioner:

```java
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Hur man skapar code128 barcode java och anger dess höjd

### Steg 1: Initiera Barcode‑objektet

Skapa en `BarcodeGenerator`‑instans för en CODE_128‑streckkod med den data du vill koda (t.ex. “12345678”).

```java
// Instantiate barcode object
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");
```

### Steg 2: Justera streckkodens dimensioner – ange stapelhöjd

Använd egenskapen `BarHeight` för att definiera höjden i millimeter. Detta är det primära sättet att **adjust barcode dimensions**.

```java
// Set the bar height to be 3 millimeters
generator.getParameters().getBarcode().getBarHeight().setMillimeters(3.0f);
```

> **Pro tip:** Du kan också ändra `XDimension` för att förändra bredden på enskilda staplar, vilket ger dig full kontroll över **customize barcode size**.

### Steg 3: Spara streckkodsbilden – generera streckkodsbild java

Skriv slutligen streckkoden till en fil. Metoden `save` bestämmer automatiskt bildformatet från filändelsen.

```java
// Save the Barcode image to file
generator.save(dataDir + "barsHeight.jpg");
```

> **Note:** Ersätt `dataDir` med den faktiska sökvägen där du vill lagra bilden.

## Vanliga användningsområden

- **Barcode for label printing** – Säkerställ att streckkoden passar inom en fördefinierad etikettstorlek.  
- **Invoice generation** – Bädda in en kompakt streckkod som matchar layouten i dina PDF‑fakturor.  
- **Mobile apps** – Generera dynamiskt streckkoder med exakta dimensioner för skanning på skärmen.

## Felsökning och tips

| Issue | Solution |
|-------|----------|
| Barcode appears too thin or too thick | Adjust `XDimension` via `generator.getParameters().getBarcode().getXDimension().setMillimeters(value)`. |
| Image is blurry | Increase the DPI by calling `generator.save(..., BarCodeImageFormat.JPEG, 300)`. |
| Scanner cannot read the code | Verify that the bar height meets the scanner’s minimum requirement (usually ≥ 2 mm). |

## Vanliga frågor

**F: Kan jag anpassa streckkodstypen i Aspose.BarCode för Java?**
S: Absolut! Biblioteket stöder många symbologier som QR, DataMatrix, PDF417 och mer – ändra bara `EncodeTypes` i konstruktorn.

**F: Är Aspose.BarCode kompatibel med olika Java IDE:er?**
S: Ja, det fungerar sömlöst med Eclipse, IntelliJ IDEA, NetBeans och alla IDE:er som stöder standard Java-projekt.

**F: Kan jag generera streckkoder med numeriska och alfanumeriska värden?**
S: Ja, CODE_128 kan koda både numerisk och alfanumerisk data, vilket gör den mångsidig för de flesta applikationer.

**F: Finns det en testversion tillgänglig för Aspose.BarCode för Java?**
S: Ja, du kan utforska funktionerna i Aspose.BarCode genom att hämta en gratis testversion [här](https://releases.aspose.com/).

** **F: Var kan jag hitta support för Aspose.BarCode för Java?**
S: Besök Aspose.BarCode-forumet [här](https://forum.aspose.com/c/barcode/13) för communitysupport och diskussioner.


---


**Senast uppdaterad:** 2026-02-15
**Testad med:** Aspose.BarCode för Java 24.12 (senaste)
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
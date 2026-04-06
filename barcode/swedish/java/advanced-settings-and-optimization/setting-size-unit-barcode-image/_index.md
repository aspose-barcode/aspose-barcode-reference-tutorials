---
date: 2026-02-07
description: Lär dig hur du använder Aspose Barcode Java för att skapa en CODE_128-streckkod,
  generera streckkodsbilder i Java och ange exakta storleksenheter – perfekt för streckkoder
  i ett lagersystem eller för generering av fraktetiketter.
linktitle: Setting Size Unit for Barcode Image
second_title: Aspose.BarCode Java API
title: 'aspose barcode java: Skapa CODE_128-streckkod med storleksenhet'
url: /sv/java/advanced-settings-and-optimization/setting-size-unit-barcode-image/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose barcode java: Skapa CODE_128 streckkod med storleksenhet

## Introduktion

I den här steg‑för‑steg‑handledningen kommer du **använda aspose barcode java** för att skapa en CODE_128 streckkod, generera en barcode image java, och exakt kontrollera storleksenheten för resultatet. Oavsett om du bygger en streckkod för ett lagersystem, en fraktetikettgenerator, eller någon Java‑baserad applikation som behöver pålitliga streckkoder, ger Aspose.BarCode for Java dig full flexibilitet med bara några rader kod.

## Snabba svar
- **Vilket bibliotek behöver jag?** Aspose.BarCode for Java (aspose barcode java).  
- **Vilken streckkodstyp täcks?** CODE_128 (skapa code128 barcode java).  
- **Hur ställer jag in storleksenheten?** Använd egenskapen `BarHeight` med `.setPoint()`.  
- **Kan jag generera barcode image java i andra format?** Ja – PNG, JPEG, BMP, etc.  
- **Vad är förutsättningarna?** JDK installerat, Aspose.BarCode-biblioteket och en Java-IDE.

## Vad är **create code128 barcode java**?

Att skapa en CODE_128 streckkod i Java innebär att instansiera klassen `BarcodeGenerator` med enumen `EncodeTypes.CODE_128` och tillhandahålla datasträngen du vill koda. Denna symbolik används ofta inom logistik eftersom den stödjer hela ASCII-teckenuppsättningen och erbjuder hög datadensitet—vilket gör den idealisk för streckkod för lagersystemsscenarier.

## Varför använda Aspose.BarCode för att **generate barcode image java**?

- **Full kontroll över dimensioner** – du kan ställa in stapelhöjd, modulstorlek och bildupplösning.  
- **Inga externa beroenden** – ren Java, fungerar på alla plattformar som stödjer JDK.  
- **Rik anpassning** – färger, typsnitt, marginaler och även QR-koder stöds.  
- **Hög prestanda** – genererar bilder på millisekunder, lämplig för batchbearbetning och generera fraktetikett streckkod arbetsflöden.  

## Förutsättningar

1. **Java Development Kit (JDK)** – version 8 eller senare installerad på din maskin.  
2. **Aspose.BarCode for Java-bibliotek** – ladda ner den senaste JAR-filen från Aspose-webbplatsen (test eller licensierad).  
3. **En Java-IDE** – såsom IntelliJ IDEA, Eclipse eller VS Code med Java-tillägg.  

## Importera namnrymder

Lägg till de nödvändiga importerna högst upp i din Java-klass så att du kan komma åt Aspose.BarCode:s API:

```java
import java.io.IOException;

import com.aspose.barcode.*;

import com.aspose.barcode.generation.BarcodeGenerator;
```

## Hur man **generate barcode image java** med Aspose.BarCode?

Nedan är hela arbetsflödet. Varje steg förklaras på enkel svenska, och de ursprungliga kodblocken behålls exakt som de var.

### Steg 1: Definiera resurskatalogen

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Byt ut `"Your Document Directory"` mot den absoluta sökvägen där du vill spara streckkodbilden. Denna mapp kommer att innehålla de genererade PNG/JPEG-filerna som du senare kan bädda in i fakturor, packningslistor eller lagerrapporter.

### Steg 2: Instansiera Barcode-objektet

```java
// Instantiate barcode object, Set the symbology type to code128 and Set the
// Code text for the barcode
BarcodeGenerator bb = new BarcodeGenerator(EncodeTypes.CODE_128, "1234567");
```

Här **create code128 barcode java** genom att skicka `EncodeTypes.CODE_128` och datasträngen `"1234567"`.

### Steg 3: Ställ in stapelhöjd (storleksenhet)

```java
// Set the bar height to 3 points
bb.getParameters().getBarcode().getBarHeight().setPoint(3.0f);
```

`setPoint()`‑metoden definierar höjden i punkter (1 punkt = 1/72 tum). Justera detta värde för att uppfylla dina layoutkrav—större värden ger högre staplar, vilket ofta behövs för högupplösta fraktetiketter.

### Steg 4: Spara bilden

```java
// Save the image
bb.save(dataDir + "barcode-size-unit.jpg");
```

`save()`‑anropet skriver den genererade streckkoden till den mapp du angav. Bildformatet härleds från filändelsen (JPEG i detta fall). Du kan byta till PNG, BMP eller TIFF genom att helt enkelt ändra filändelsen.

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|-------|--------|-----|
| **Bild skapades inte** | `dataDir`‑sökvägen är felaktig eller saknar skrivbehörighet. | Verifiera att mappen finns och att ditt program har skrivbehörighet. |
| **Streckkoden visas för liten** | Stapelhöjden satt i punkter är för låg för den valda DPI:n. | Öka värdet som skickas till `setPoint()` eller justera bild-DPI via `bb.getParameters().getImage().setResolution()`. |
| **Ej stödda tecken** | CODE_128 stödjer endast ASCII; du skickade Unicode. | Använd en annan symbolik (t.ex. QR_CODE) för icke‑ASCII‑data. |

## Vanliga frågor

**Q: Är Aspose.BarCode for Java lämplig för både streckkodsgenerering och igenkänning?**  
A: Ja, biblioteket stödjer både generering och igenkänning av ett brett spektrum av symboler.

**Q: Kan jag anpassa utseendet på de genererade streckkodsbilderna?**  
A: Absolut. Du kan ändra färger, lägga till bildtexter, modifiera marginaler och till och med bädda in logotyper med det omfattande `Parameters`‑API:t.

**Q: Hur kan jag skaffa en tillfällig licens för Aspose.BarCode for Java?**  
A: Besök [here](https://purchase.aspose.com/temporary-license/) för att begära en tillfällig licens för utvärdering.

**Q: Var kan jag hitta support för Aspose.BarCode for Java?**  
A: Aspose.BarCode‑communityforum är den bästa platsen för hjälp. Kolla [forum](https://forum.aspose.com/c/barcode/13) för svar och för att ställa nya frågor.

**Q: Vilka streckkodssymboler stöds i Aspose.BarCode for Java?**  
A: Biblioteket stödjer dussintals symboler, inklusive CODE_128, QR_CODE, UPC_A, DataMatrix, PDF417 och många fler.

### Ytterligare tips (Pro tip)

- **Batch‑behandling:** Lägg in stegen ovan i en loop för att generera hundratals streckkoder för massuppladdning av lager.  
- **Upplösningskontroll:** Använd `bb.getParameters().getImage().setResolution(300)` för att skapa 300 dpi‑bilder, vilket är idealiskt för högkvalitativa utskriftsetiketter.  

---

**Senast uppdaterad:** 2026-02-07  
**Testad med:** Aspose.BarCode for Java 24.12 (latest at time of writing)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
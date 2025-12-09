---
date: 2025-12-08
description: Lär dig hur du skapar code128‑streckkod i Java och genererar streckkodsbilder
  i Java med Aspose.BarCode. Ställ in exakta storleksenheter för streckkodsbilder
  med enkel, återanvändbar kod.
linktitle: Setting Size Unit for Barcode Image
second_title: Aspose.BarCode Java API
title: Skapa Code128-streckkod i Java med Aspose.BarCode
url: /sv/java/advanced-settings-and-optimization/setting-size-unit-barcode-image/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa code128 streckkod java och ställ in storleksenhet med Aspose.BarCode

## Introduktion

I den här steg‑för‑steg‑guiden kommer du att **skapa code128 streckkod java** kod som genererar en streckkodsbild och låter dig kontrollera storleksenheten för utskriften. Oavsett om du bygger ett lagersystem, en fraktetikettgenerator eller någon Java‑applikation som behöver en pålitlig streckkod, gör Aspose.BarCode för Java processen enkel och mycket anpassningsbar.

## Snabba svar
- **Vilket bibliotek behöver jag?** Aspose.BarCode för Java.  
- **Vilken streckkodstyp täcks?** CODE_128 (create code128 barcode java).  
- **Hur ställer jag in storleksenheten?** Använd `BarHeight`‑egenskapen med `.setPoint()`.  
- **Kan jag generera streckkodsbild java i andra format?** Ja – PNG, JPEG, BMP osv.  
- **Vad krävs?** JDK installerat, Aspose.BarCode‑biblioteket och en Java‑IDE.

## Vad är **create code128 barcode java**?

Att skapa en CODE_128‑streckkod i Java innebär att instansiera `BarcodeGenerator`‑klassen med enum‑värdet `EncodeTypes.CODE_128` och ange den datasträng du vill koda. Denna symbologi används flitigt inom logistik eftersom den stödjer hela ASCII‑teckenuppsättningen och ger hög datadensitet.

## Varför använda Aspose.BarCode för att **generate barcode image java**?

- **Full kontroll över dimensioner** – du kan sätta bar‑höjd, modulstorlek och bildupplösning.  
- **Inga externa beroenden** – ren Java, fungerar på alla plattformar som stödjer JDK.  
- **Rik anpassning** – färger, typsnitt, marginaler och till och med QR‑koder stöds.  
- **Hög prestanda** – genererar bilder på millisekunder, lämpligt för batch‑bearbetning.

## Förutsättningar

Innan vi börjar, se till att du har:

1. **Java Development Kit (JDK)** – version 8 eller senare installerad på din maskin.  
2. **Aspose.BarCode för Java‑bibliotek** – ladda ner den senaste JAR‑filen från Aspose‑webbplatsen (prov eller licens).  
3. **En Java‑IDE** – t.ex. IntelliJ IDEA, Eclipse eller VS Code med Java‑tillägg.  

## Importera namnrymder

Lägg till de nödvändiga importerna högst upp i din Java‑klass så att du kan komma åt Aspose.BarCode‑API:t:

```java
import java.io.IOException;

import com.aspose.barcode.*;

import com.aspose.barcode.generation.BarcodeGenerator;
```

## Hur man **generate barcode image java** med Aspose.BarCode?

Nedan följer hela arbetsflödet. Varje steg förklaras i klartext, och de ursprungliga kodblocken behålls exakt som de var.

### Steg 1: Definiera resurskatalogen

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Ersätt `"Your Document Directory"` med den absoluta sökvägen där du vill spara streckkodsbilden.

### Steg 2: Instansiera Barcode‑objektet

```java
// Instantiate barcode object, Set the symbology type to code128 and Set the
// Code text for the barcode
BarcodeGenerator bb = new BarcodeGenerator(EncodeTypes.CODE_128, "1234567");
```

Här **create code128 barcode java** genom att skicka `EncodeTypes.CODE_128` och datasträngen `"1234567"`.

### Steg 3: Ställ in Bar Height (storleksenhet)

```java
// Set the bar height to 3 points
bb.getParameters().getBarcode().getBarHeight().setPoint(3.0f);
```

Metoden `setPoint()` definierar höjden i punkter (1 punkt = 1/72 tum). Justera detta värde för att passa dina layoutkrav.

### Steg 4: Spara bilden

```java
// Save the image
bb.save(dataDir + "barcode-size-unit.jpg");
```

Anropet `save()` skriver den genererade streckkoden till den mapp du angav. Bildformatet bestäms av filändelsen (JPEG i detta fall).

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|-------|--------|-----|
| **Bild skapades inte** | `dataDir`‑sökvägen är felaktig eller saknar skrivbehörighet. | Verifiera att mappen finns och att ditt program har skrivbehörighet. |
| **Streckkoden är för liten** | Bar height som satts i punkter är för låg för den valda DPI:n. | Öka värdet som skickas till `setPoint()` eller justera bildens DPI via `bb.getParameters().getImage().setResolution()`. |
| **Ej stödda tecken** | CODE_128 stöder endast ASCII; du skickade Unicode. | Använd en annan symbologi (t.ex. QR_CODE) för icke‑ASCII-data. |

## Vanliga frågor

**Q: Är Aspose.BarCode för Java lämplig för både generering och igenkänning av streckkoder?**  
A: Ja, biblioteket stödjer både generering och igenkänning av ett brett utbud av symbologier.

**Q: Kan jag anpassa utseendet på de genererade stre Du kan ändra färger, lägga till bildtexter, justera marginaler och till och med bädda in logotyper med det omfattande `Parameters`‑API:et.

**Q: Hur kan jag få en tillfällig licens för Aspose.BarCode för Java?**  
A: Besök [här](https://purchase.aspose.com/temporary-license/) för att begära en tillfällig licens för utvärdering.

**Q: Var kan jag hitta support för Aspose.BarCode för Java?**  
A: Aspose.BarCode community‑forum är den bästa platsen för hjälp. Kolla [forumet](https://forum.aspose.com/c/barcode/13) för svar och för att ställa nya frågor.

**Q: Vilka streckkodssymbologier stöds i Aspose.BarCode för Java?**  
A: Biblioteket stöder dussintals symbologier, inklusive CODE_128, QR_CODE, UPC_A, DataMatrix, PDF417 och många fler.

---

**Senast uppdaterad:** 2025-12-08  
**Testat med:** Aspose.BarCode för Java 24.12 (senaste vid skrivtillfället)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
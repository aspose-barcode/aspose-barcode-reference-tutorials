---
date: 2025-12-22
description: Lär dig hur du skapar streckkodsbilder med tomma staplar med Aspose.BarCode
  för Java. Detta steg‑för‑steg‑exempel på streckkodsgenerering hjälper dig att snabbt
  generera streckkoder i Java.
linktitle: Generating Barcode with Empty Bars
second_title: Aspose.BarCode Java API
title: Hur man skapar en streckkodsbild med tomma staplar i Java
url: /sv/java/image-manipulation/generating-barcode-empty-bars/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar streckkodbild med tomma staplar i Java

## Introduktion

I moderna Java‑applikationer är förmågan att **create barcode image**‑filer i realtid en värdefull funktion för lagerhantering, biljettsystem och många andra affärsscenarier. Aspose.BarCode for Java tillhandahåller ett kraftfullt, lätt‑använt API som låter dig generera högkvalitativa streckkoder med bara några rader kod. I den här handledningen går vi igenom en **step‑by‑step barcode**‑skapandeprocess som producerar en streckkod med tomma (oifyllda) staplar, perfekt för designer som kräver ett ihåligt utseende.

## Snabba svar
- **Vad betyder “empty bars”?** Staplar renderas utan den förvalda solida fyllningen, vilket ger ett ihåligt utseende.  
- **Vilken streckkodstyp används?** Code 128 (en allmänt stödjande linjär symbologi).  
- **Behöver jag en licens för att prova?** En gratis provversion finns tillgänglig; en licens krävs för produktionsanvändning.  
- **Vilka utdataformat stöds?** PNG, JPEG, BMP, GIF, TIFF och fler.  
- **Är detta kompatibelt med alla Java‑versioner?** Ja, biblioteket fungerar med Java 8 och senare.

## Vad är create barcode image?
Att skapa en streckkodbild innebär att konvertera en datasträng till en visuell representation som skannrar kan läsa. Den resulterande bilden kan sparas som PNG, JPEG eller andra vanliga format och inbäddas i PDF‑filer, skrivas ut på etiketter eller visas i ett UI.

## Varför använda Aspose.BarCode Java‑biblioteket?
- **Rik funktionsuppsättning** – stöder över 50 streckkodssymbologier, inklusive Code 128, QR, DataMatrix och fler.  
- **Fin‑granulerad kontroll** – egenskaper som `FilledBars`, färger, marginaler och bildstorlek kan enkelt konfigureras.  
- **Inga externa beroenden** – en enda JAR‑fil hanterar allt, vilket förenklar distribution.  
- **Omfattande dokumentation** – exempel, API‑referens och forum hjälper dig att snabbt komma igång.

## Förutsättningar

Innan vi påbörjar streckkodsgenereringsresan, se till att du har följande förutsättningar på plats:

1. **Java‑utvecklingsmiljö** – Se till att du har Java 8+ installerat samt en kompatibel IDE eller byggverktyg.  
2. **Aspose.BarCode for Java Library** – Ladda ner och installera Aspose.BarCode for Java‑biblioteket från [download page](https://releases.aspose.com/barcode/java/).  
3. **Document Directory** – Skapa en katalog på ditt system för att lagra den genererade streckkodbilden.

## Importera paket

I ditt Java‑projekt, importera de nödvändiga paketen för att arbeta med Aspose.BarCode:

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Hur man skapar streckkodbild med tomma staplar

### Steg 1: Ställ in resurskatalogen

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Ersätt `"Your Document Directory"` med den faktiska sökvägen där du vill spara utdatafilen.

### Steg 2: Skapa Barcode Generator‑instans (Code128 Barcode Java)

Här använder vi **Code 128**‑symbologin—en av de mest populära linjära streckkoderna—vilket gör detta till ett klassiskt **code128 barcode java**‑exempel.

```java
// Create an instance of BarcodeGenerator and initialize it with CodeText and Symbology
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

### Steg 3: Ställ in egenskapen FilledBars till False

```java
// Set the FilledBars property to false
generator.getParameters().getBarcode().setFilledBars(false);
```

Att sätta `FilledBars` till `false` instruerar Aspose.BarCode att rendera staplarna som tomma (ihåliga) former istället för solida block.

### Steg 4: Spara streckkodbilden

```java
// Save the resultant barcode image on disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

Bilden sparas i PNG‑format, men du kan ändra `BarCodeImageFormat`‑enum för att producera JPEG, BMP eller andra stödjade typer.

Upprepa dessa steg i din Java‑applikation för att enkelt **create barcode image**‑filer med tomma staplar med hjälp av Aspose.BarCode for Java.

## Slutsats

Sammanfattningsvis har den här handledningen lett dig genom en **step‑by‑step barcode**‑skapandeprocess som visar hur man **create barcode image**‑filer med tomma staplar i Java. Med sitt intuitiva API och omfattande anpassningsalternativ förenklar Aspose.BarCode streckkodsintegration, vilket gör det till en värdefull tillgång för utvecklare som behöver ett pålitligt **java barcode library**.

## Vanliga frågor

### Är Aspose.BarCode kompatibel med alla Java‑utvecklingsmiljöer?
Ja, Aspose.BarCode är utformat för att sömlöst integreras med olika Java‑utvecklingsmiljöer.

### Kan jag anpassa utseendet på den genererade streckkoden?
Absolut! Aspose.BarCode erbjuder många anpassningsalternativ som låter dig skräddarsy streckkoden efter dina specifika behov.

### Finns en provversion av Aspose.BarCode tillgänglig?
Ja, du kan utforska funktionerna i Aspose.BarCode genom att skaffa en gratis provversion [here](https://releases.aspose.com/).

### Hur kan jag få support för Aspose.BarCode?
För eventuella frågor eller hjälp, besök [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13).

### Var kan jag hitta detaljerad dokumentation för Aspose.BarCode?
Den omfattande dokumentationen finns tillgänglig [here](https://reference.aspose.com/barcode/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-22  
**Tested With:** Aspose.BarCode Java 24.11 (latest)  
**Author:** Aspose
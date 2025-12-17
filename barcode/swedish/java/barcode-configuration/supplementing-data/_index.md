---
date: 2025-12-17
description: Lär dig hur du genererar streckkoder i Java med Aspose.BarCode, inklusive
  dynamisk streckkodsgenerering, skapande av EAN‑13‑streckkoder och sparande av streckkodsbilder
  med kompletterande data.
linktitle: Supplementing Data
second_title: Aspose.BarCode Java API
title: Hur man genererar streckkod med kompletterande data i Java
url: /sv/java/barcode-configuration/supplementing-data/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar streckkod med kompletterande data i Java

## Introduktion

I dagens snabbrörliga digitala ekosystem är **hur man genererar streckkod** effektivt en fråga som många Java‑utvecklare ställs inför. Aspose.BarCode for Java erbjuder ett kraftfullt, lättanvänt API som stödjer **dynamisk streckkodsgenerering**, inklusive skapandet av **EAN‑13‑streckkoder** med kompletterande data. Oavsett om du bygger lagerhanteringssystem, detaljhandels‑POS‑applikationer eller logistik‑spårare, guidar den här handledningen dig genom ett **java barcode generator example** som sparar streckkodsbilden till disk och låter dig anpassa den kompletterande delen.

## Snabba svar
- **Vilket bibliotek är bäst för att generera streckkoder i Java?** Aspose.BarCode for Java.  
- **Vilken symbologi skapar en 13‑siffrig numerisk streckkod?** EAN‑13.  
- **Kan jag lägga till kompletterande data till en EAN‑13‑streckkod?** Ja, med `Supplement`‑API:t.  
- **Hur sparar jag den genererade streckkoden som en bild?** Anropa `generator.save("path/filename.jpg")`.  
- **Behövs en licens för produktionsanvändning?** Ja, en kommersiell licens krävs; en gratis provversion finns tillgänglig.

## Vad är streckkodsgenerering i Java?

Streckkodsgenerering innebär att konvertera data—nummer, bokstäver eller en blandning—till ett visuellt mönster som scanners kan läsa. Med Aspose.BarCode kan du producera **högupplösta streckkodsbilder** i farten, vilket gör det idealiskt för **dynamisk streckkodsgenerering** i scenarier som real‑tids‑biljettering eller orderuppfyllelse.

## Varför använda Aspose.BarCode för dynamisk streckkodsgenerering?

- **Full kontroll** över symbologi, storlek, färger och kompletterande data.  
- **Inga externa beroenden** – ren Java, fungerar på alla plattformar.  
- **Inbyggt stöd** för dussintals streckkodstyper, inklusive **create ean13 barcode**.  
- **Enkelt API** som låter dig **save barcode image** med en enda kodrad.

## Förutsättningar

Innan du börjar, se till att du har:

- **Java Development Kit (JDK)** – någon aktuell version (8 eller senare).  
- **IDE** – IntelliJ IDEA, Eclipse eller din favoritredigerare.  
- **Aspose.BarCode for Java** – ladda ner biblioteket från den officiella sidan **[here](https://releases.aspose.com/barcode/java/)** och lägg till JAR‑filen i ditt projekts classpath.

## Importera paket

När biblioteket är refererat, importera kärnklassen som driver streckkodsskapandet.

```java
// Import Aspose.BarCode for Java
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Steg‑för‑steg‑guide

### Steg 1: Definiera din dokumentkatalog

Ange mappen där den genererade bilden ska lagras.

```java
String dataDir = "Your Document Directory";
```

### Steg 2: Skapa instans av Barcode Generator

Instansiera `BarcodeGenerator` med önskad **codetext** och **symbology**. Här **create ean13 barcode** med den numeriska strängen `"123456789123"`.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.EAN_13, "123456789123");
```

### Steg 3: Ange kompletterande data

Lägg till en 5‑siffrig kompletterande sträng. Detta är användbart för tidskrifter, periodika eller alla fall där extra information följer huvudstreckkoden.

```java
generator.getParameters().getBarcode().getSupplement().setSupplementData("12345");
```

### Steg 4: Ställ in avstånd för komplettering

Justera gapet mellan huvudstreckkoden och dess komplettering. Värdet uttrycks i punkter.

```java
generator.getParameters().getBarcode().getSupplement().getSupplementSpace().setPoint(2.0f);
```

### Steg 5: Spara streckkodsbilden

Skriv slutligen bilden till disk. Formatet härleds från filändelsen (JPEG i detta exempel).

```java
generator.save(dataDir + "supplementData.jpg");
```

> **Pro tip:** Du kan ändra filändelsen till `.png` eller `.bmp` för att få ett annat bildformat utan extra kod.

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|---------|-------|----------|
| **Bild sparas inte** | `dataDir` pekar på en icke‑existerande mapp | Säkerställ att katalogen finns eller skapa den programatiskt (`new File(dataDir).mkdirs();`). |
| **Ogiltig kompletteringslängd** | EAN‑13‑kompletteringar måste vara 2 eller 5 siffror | Ange exakt 2 eller 5 tecken; annars kastas ett undantag. |
| **Ej stödjade tecken** | Icke‑numeriska tecken i EAN‑13‑codetext | Använd endast siffror 0‑9 för EAN‑13; byt till en annan symbologi för alfanumeriska tecken. |

## Vanliga frågor

### Är Aspose.BarCode kompatibel med alla Java‑versioner?
Aspose.BarCode for Java är designat för att vara kompatibelt med ett brett spektrum av Java‑versioner. Se **[documentation](https://reference.aspose.com/barcode/java/)** för specifika detaljer.

### Kan jag anpassa utseendet på de genererade streckkoderna?
Ja, Aspose.BarCode erbjuder olika parametrar och inställningar för att anpassa streckkodernas utseende. Utforska dokumentationen för detaljerad information.

### Finns det en provversion tillgänglig?
Ja, du kan få en gratis provversion **[here](https://releases.aspose.com/)**.

### Hur får jag support för Aspose.BarCode?
Besök **[Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)** för att få hjälp från communityn och experter.

### Var kan jag köpa Aspose.BarCode for Java?
Du kan köpa Aspose.BarCode for Java **[here](https://purchase.aspose.com/buy)**.

---

**Senast uppdaterad:** 2025-12-17  
**Testad med:** Aspose.BarCode for Java 24.11  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
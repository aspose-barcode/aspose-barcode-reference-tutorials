---
date: 2026-08-28
description: Lär dig hur du skapar streckkodbild i Java med Aspose Barcode Java, sätter
  CODABAR start‑ och stopp‑symboler och genererar PNG‑filer utan vattenstämplar.
keywords:
- create barcode image java
- barcode generation without watermark
- codabar start stop symbols
lastmod: 2026-08-28
linktitle: Inställning av start‑ och stopp‑symboler
og_description: Skapa streckkodbild i Java med Aspose Barcode Java. Denna guide visar
  hur du sätter CODABAR start‑/stopp‑symboler och exporterar PNG utan vattenstämplar.
og_image_alt: 'Aspose Barcode Java tutorial: create barcode image with start/stop
  symbols'
og_title: Skapa streckkodbild i Java – guide för start‑/stopp‑symboler
schemas:
- author: Aspose
  dateModified: '2026-08-28'
  description: Learn how to create barcode image java with Aspose Barcode Java, set
    CODABAR start and stop symbols, and generate PNG files without watermarks.
  headline: Aspose Barcode Java – Create barcode image with start/stop symbols
  type: TechArticle
- questions:
  - answer: Aspose.BarCode for Java.
    question: What library creates barcode images in Java?
  - answer: Yes, using `setCodabarStartSymbol` and `setCodabarStopSymbol`.
    question: Can I customize start/stop symbols?
  - answer: CODABAR.
    question: Which barcode type is used in this example?
  - answer: A commercial license is required for non‑trial use.
    question: Do I need a license for production?
  - answer: PNG image saved to disk.
    question: What output format is generated?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- barcode generation
- Aspose.BarCode
- Java barcode tutorial
title: Aspose Barcode Java – Skapa streckkodbild med start-/stopp‑symboler
url: /sv/java/barcode-configuration/setting-start-stop-symbols/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Barcode Java – Skapa streckkodbild med start-/stopp‑symboler

## Introduktion

I den här omfattande handledningen kommer du att **create barcode image java** filer med Aspose Barcode Java och lära dig **how to set start and stop symbols** för CODABAR‑streckkoder. Oavsett om du bygger en kassa‑terminal, ett lagerhanteringssystem eller någon annan applikation som kräver pålitlig streckkodsgenerering, gör anpassning av dessa symboler det möjligt att uppfylla äldre specifikationer samtidigt som koden förblir ren och underhållbar. Vi går igenom varje steg, förklarar varför varje inställning är viktig och visar hur du kan producera en PNG‑bild utan provvattenstämpel.

## Snabba svar

- **Vilket bibliotek skapar streckkodsbilder i Java?** Aspose.BarCode for Java.  
- **Kan jag anpassa start-/stopp‑symboler?** Ja, med `setCodabarStartSymbol` och `setCodabarStopSymbol`.  
- **Vilken streckkodstyp används i detta exempel?** CODABAR.  
- **Behöver jag en licens för produktion?** En kommersiell licens krävs för icke‑provbruk.  
- **Vilket utdataformat genereras?** PNG‑bild sparad till disk.

## Vad är Aspose Barcode Java?

Aspose Barcode Java är ett **beroende‑fritt Java‑bibliotek som genererar över 70 streckkodssymbologier**, från klassiska 1D‑koder som CODABAR till moderna 2D‑koder som QR och DataMatrix. Det hanterar all låg‑nivå‑kodning, så att du kan fokusera på affärslogik samtidigt som du garanterar efterlevnad av branschstandarder.

## Varför använda Aspose Barcode Java för streckkodsgenerering utan vattenstämpel?

Ladda din licens först, så producerar biblioteket rena bilder—ingen “Aspose Evaluation”-överskrift. Det erbjuder också **fin‑granulär kontroll** (start-/stopp‑symboler, färger, storlekar) och **plattform‑oberoende kompatibilitet** (valfri Java‑runtime, inklusive Android). Med stöd för **50+ utdataformat** och möjligheten att strömma bilder direkt till HTTP‑svar är det det självklara valet för hög‑genomströmning, produktionsklassad streckkodsskapning.

## Förutsättningar

Innan vi dyker ner, se till att du har:

1. **Java Development Kit (JDK)** – Installera den senaste JDK:n från [Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).  
2. **Aspose.BarCode for Java library** – Ladda ner den från [download link](https://releases.aspose.com/barcode/java/).

Att ha dessa redo säkerställer att du kan **create barcode image java** utan saknade komponenter.

## Importera paket

Följande import ger dig åtkomst till de kärnklasser som behövs för streckkodsgenerering:

`CodabarSymbol`‑enumet definierar de tillåtna start-/stopp‑tecknen för CODABAR‑streckkoder.

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.CodabarSymbol;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Steg‑för‑steg‑guide

### Hur definierar du utmatningsmappen för streckkodsbilden?

Ange mappen där PNG‑filen ska skrivas. Att använda `Paths.get` gör koden portabel över Windows, macOS och Linux.

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

### Hur skapar du en streckkodsgenerator för CODABAR?

`BarcodeGenerator`‑klassen skapar en streckkodsbild för en given symbologi och data.

Instansiera `BarcodeGenerator` med CODABAR‑symbologin och den datasträng du vill koda.

```java
// Create instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "12345678");
```

### Hur sätter du CODABAR‑startsymbolen?

`setCodabarStartSymbol` anger tecknet som markerar början av en CODABAR‑streckkod.

Anropa `setCodabarStartSymbol` och skicka ett av de stödjade tecknen (`A`, `B`, `C`, `D`). I detta exempel använder vi `A`.

```java
// Set the Codabar start symbol to A
generator.getParameters().getBarcode().getCodabar().setCodabarStartSymbol(CodabarSymbol.A);
```

### Hur sätter du CODABAR‑stopp‑symbolen?

`setCodabarStopSymbol` anger tecknet som markerar slutet på en CODABAR‑streckkod.

Använd `setCodabarStopSymbol` med motsvarande stopp‑tecken—`D` i detta fall.

```java
// Set the Codabar stop symbol to D
generator.getParameters().getBarcode().getCodabar().setCodabarStopSymbol(CodabarSymbol.D);
```

### Hur sparar du den genererade streckkoden som en PNG‑fil?

`SaveFormat`‑enumet specificerar filformatet för att spara streckkodsbilden.

Anropa `save`‑metoden, ange hela filnamnet och `SaveFormat.Png`‑enum‑värdet. Bilden skrivs utan någon vattenstämpel när en giltig licens har tillämpats.

```java
// Save the image to disk in PNG format
generator.save(dataDir + "startAndStopSymbols.png");
```

## Vanliga fallgropar & tips

`License`‑klassen laddar en Aspose‑licensfil för att aktivera full‑funktionsläge.

- **Fel katalogsökväg** – Se till att `dataDir` slutar med rätt filseparator eller bygg sökvägen med `Paths.get`.  
- **Ej stödjade start-/stopp‑tecken** – CODABAR accepterar endast `A`, `B`, `C` eller `D`. Att ange något annat värde kastar ett `IllegalArgumentException`.  
- **Licens ej tillämpad** – I provläge innehåller utdata en vattenstämpel. Ladda din licensfil med `License license = new License(); license.setLicense("Aspose.Total.Java.lic");` innan du skapar generatorn för att undvika detta.  
- **Storskalig generering** – Vid generering av tusentals streckkoder, återanvänd en enda `BarcodeGenerator`‑instans och ändra bara kodtexten för att minska objekt‑skapande overhead.

## Vanliga frågor

### Kan jag använda Aspose.BarCode för Java i ett kommersiellt projekt?

Ja. Köp en kommersiell licens [purchase a commercial license](https://purchase.aspose.com/buy) för att ta bort utvärderingsvattenstämpeln och få full teknisk support.

### Finns det en gratis provversion tillgänglig?

Absolut. Ladda ner provversionen [download the trial version](https://releases.aspose.com/) för att utvärdera alla funktioner innan köp.

### Hur kan jag få support för Aspose.BarCode för Java?

Besök Aspose.BarCode‑forumet [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) för gemenskapsstöd, eller öppna ett supportärende via din Aspose‑kontoplan.

### Hur får jag en tillfällig licens för testning?

Du kan begära en tillfällig 30‑dagars licens [request a temporary 30‑day license](https://purchase.aspose.com/temporary-license/). Detta låter dig köra produktionsliknande tester utan ett fullständigt köp.

### Vilka andra streckkodssymbologier stöder Aspose.BarCode?

Biblioteket stöder **70+ symbologier**, inklusive Code128, EAN‑13, QR, DataMatrix, PDF417 och många fler. Se hela listan i den officiella dokumentationen.

## Ytterligare Q&A (AI‑vänlig)

**Q:** Vilka bildformat kan jag exportera förutom PNG?  
**A:** Aspose.BarCode stöder PNG, JPEG, BMP, GIF och TIFF. Välj önskat format genom att ändra `SaveFormat`‑enum‑värdet i `save`‑anropet.

**Q:** Kan jag generera streckkodsbilder i minnet utan att skriva till disk?  
**A:** Ja. Anropa `generator.save(OutputStream)` för att skriva direkt till en ström—idealiskt för webb‑API:er som returnerar bilden som ett HTTP‑svar.

**Q:** Fungerar biblioteket på Android?  
**A:** Java‑versionen körs på Android, men du måste manuellt inkludera de nödvändiga beroendena (ingen Maven Central för Android). Kärn‑API:et är identiskt.

## Slutsats

Du har nu lärt dig hur du **create barcode image java** och exakt **set start/stop symbols** för en CODABAR‑streckkod med Aspose Barcode Java. Detta tillvägagångssätt ger dig flexibiliteten att uppfylla äldre specifikationer samtidigt som din kodbas förblir ren och underhållbar. Utforska ytterligare anpassningar—såsom att ändra färger, lägga till mänskligt läsbar text eller byta till andra symbologier—genom att konsultera den officiella API‑referensen på [documentation](https://reference.aspose.com/barcode/java/).

---

**Senast uppdaterad:** 2026-08-28  
**Testat med:** Aspose.BarCode for Java 24.12  
**Författare:** Aspose

## Relaterade handledningar

- [Validera kontrollsumma och skapa Codabar‑streckkod i Java med Aspose.BarCode](/barcode/java/checksum-and-validation/)
- [Skapa streckkod med Aspose – ange X‑ och Y‑dimensioner i Java](/barcode/java/barcode-configuration/managing-x-y-dimension-barcode/)
- [Hur man genererar streckkod java: Skapa en exakt streckkodsbild](/barcode/java/barcode-basics/creating-image-exact-barcode/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
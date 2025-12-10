---
date: 2025-12-10
description: Lär dig hur du genererar streckkod med ett anpassat brett‑tunt förhållande
  i Java med Aspose.BarCode och skapar streckkodsbilder effektivt. Följ vår steg‑för‑steg‑guide.
linktitle: Configuring Wide-Narrow Ratio
second_title: Aspose.BarCode Java API
title: Hur man genererar streckkod med brett‑smalt förhållande i Java
url: /sv/java/barcode-configuration/configuring-wide-narrow-ratio/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar streckkod med Wide‑Narrow‑förhållande i Java

## Introduktion

Om du behöver **hur man genererar streckkod** med precisa visuella proportioner är justering av wide‑narrow‑förhållandet nyckeln. I den här handledningen går vi igenom en **steg för steg streckkod**‑skapandeprocess med Aspose.BarCode för Java, visar hur du konfigurerar förhållandet, genererar streckkodsbild och **sparar barcode png** till disk. Oavsett om du bygger lageretiketter, fraktsedlar eller någon annan applikation som kräver en anpassad CODE_128‑streckkod, hittar du allt du behöver här.

## Snabba svar
- **Vad är wide‑narrow‑förhållandet?** Det styr den relativa bredden på de breda staplarna jämfört med de smala staplarna i en streckkod.  
- **Vilken symbologi stödjer justering av förhållandet?** De flesta 1‑D‑symbologier, inklusive CODE_128, låter dig ange ett eget förhållande.  
- **Behöver jag en licens?** En gratis provversion finns tillgänglig, men en kommersiell licens krävs för produktionsbruk.  
- **Kan jag generera en streckkodsbild i PNG‑format?** Ja – använd `generator.save(...)` för att generera streckkodsbild som PNG.  
- **Är koden kompatibel med Java 8+?** Absolut; Aspose.BarCode fungerar med alla moderna Java‑versioner.

## Förutsättningar

Innan vi dyker in i koden, se till att du har följande:

- Java Development Kit (JDK) installerat på din maskin.  
- Aspose.BarCode för Java‑biblioteket. Ladda ner det från [download link](https://releases.aspose.com/barcode/java/).

## Importera paket

För att börja, importera den väsentliga Aspose.BarCode‑klassen till ditt projekt.

```java
// Import Aspose.BarCode library
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Vad är wide‑narrow‑förhållandet och varför justera det?

Wide‑narrow‑förhållandet bestämmer hur tjocka de “bredare” staplarna framstår jämfört med de “smalare”. Att justera detta förhållande kan förbättra läsbarheten för skannrar, uppfylla specifika utskriftsstandarder eller helt enkelt matcha ett varumärkes visuella stil.

## Hur man genererar streckkod med wide‑narrow‑förhållande i Java

Nedan följer en **steg för steg streckkod**‑guide som går igenom varje del av processen.

### Steg 1: Ange dokumentkatalog

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Se till att katalogen finns och att du har skrivbehörighet; här kommer **spara barcode png**‑filen att placeras.

### Steg 2: Skapa Barcode‑objekt

```java
// Instantiate barcode object
// Create an instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

Här **skapar vi code_128 barcode** genom att skicka `EncodeTypes.CODE_128` till konstruktorn.

### Steg 3: Ange Wide‑Narrow‑förhållande

```java
// Set the wide to narrow ratio for the barcode
generator.getParameters().getBarcode().setWideNarrowRatio(3.0f);
```

Metoden `setWideNarrowRatio` låter dig finjustera det visuella avståndet. Ett värde på `3.0f` betyder att den breda stapeln är tre gånger så bred som en smal stapel.

### Steg 4: Spara bild till disk

```java
// Save the image to disk in PNG format
generator.save(dataDir + "wideNarrowRatio.png");
```

Genom att anropa `save` **genereras streckkodsbild** och lagras som en PNG‑fil, vilket slutför **spara barcode png**‑steget.

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|-------|--------|-----|
| Streckkoden ser förvrängd ut | Förhållandet är för högt/lågt för skrivaren | Justera värdet som skickas till `setWideNarrowRatio` (t.ex. 2.0‑2.5). |
| Filen skapades inte | Ogiltig `dataDir`‑sökväg eller otillräckliga rättigheter | Kontrollera katalogsökvägen och säkerställ att applikationen har skrivbehörighet. |
| Skannern kan inte läsa streckkoden | Förhållandet ligger utanför rekommenderat intervall för symbologin | Använd standardförhållanden (2.0‑3.0) eller testa med målskannern. |

## Vanliga frågor

**Q: Kan jag använda Aspose.BarCode med andra Java‑ramverk?**  
A: Ja, Aspose.BarCode är designat för att fungera sömlöst med Spring, Java EE, Android och andra Java‑miljöer.

**Q: Hur kan jag generera streckkoder med olika symbologier?**  
A: Byt helt enkelt symbologityp i `BarcodeGenerator`‑konstruktorn, till exempel `EncodeTypes.QR` för QR‑koder.

**Q: Finns det en provversion av Aspose.BarCode?**  
A: Ja, du kan komma åt den fria provversionen [here](https://releases.aspose.com/).

**Q: Var kan jag hitta detaljerad dokumentation för Aspose.BarCode?**  
A: Se dokumentationen [here](https://reference.aspose.com/barcode/java/).

**Q: Hur får jag support för Aspose.BarCode?**  
A: Besök Aspose.BarCode‑forumet [here](https://forum.aspose.com/c/barcode/13) för support och community‑diskussioner.

---

**Senast uppdaterad:** 2025-12-10  
**Testad med:** Aspose.BarCode för Java 24.11 (senaste vid skrivtillfället)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
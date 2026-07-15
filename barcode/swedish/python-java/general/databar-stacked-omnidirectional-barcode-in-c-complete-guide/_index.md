---
category: general
date: 2026-07-15
description: databar staplad omnidirektionell streckkod i C#-handledning. Lär dig
  hur du genererar databar, ställer in bildförhållandet och använder en streckkodsgenerator
  i C# för perfekta resultat.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar stacked omnidirectional
- barcode generator c#
- how to set aspect ratio
- how to generate databar
- create databar barcode
language: sv
lastmod: 2026-07-15
og_description: databar staplad omnidirektionell streckkod i C# förklarad. Följ den
  här steg‑för‑steg‑handledningen för att generera databar, justera bildförhållandet
  och bemästra streckkodsgeneratorn i C#.
og_image_alt: Two PNG images showing a databar stacked omnidirectional barcode with
  aspect ratios 15 and 30
og_title: databar staplad omnidirektionell streckkod – C#‑guide
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: databar stacked omnidirectional barcode in C# tutorial. Learn how to
    generate databar, set aspect ratio, and use a barcode generator c# for perfect
    results.
  headline: databar stacked omnidirectional barcode in C# – Complete Guide
  type: TechArticle
- description: databar stacked omnidirectional barcode in C# tutorial. Learn how to
    generate databar, set aspect ratio, and use a barcode generator c# for perfect
    results.
  name: databar stacked omnidirectional barcode in C# – Complete Guide
  steps:
  - name: The **X‑Dimension** isn’t too low (below 1 pixel is impossible).
    text: The **X‑Dimension** isn’t too low (below 1 pixel is impossible).
  - name: The **AspectRatio** matches what your scanning hardware expects.
    text: The **AspectRatio** matches what your scanning hardware expects.
  - name: The **output path** is writable—sometimes `UnauthorizedAccessException`
      hides behind a silent failure.
    text: The **output path** is writable—sometimes `UnauthorizedAccessException`
      hides behind a silent failure.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: databar staplad omnidirektionell streckkod i C# – Komplett guide
url: /sv/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# databar staplad omnidirektionell streckkod i C# – Komplett guide

Har du någonsin undrat hur man ställer in bildförhållandet när du **databar staplad omnidirektionell streckkod** i C#? Du är inte ensam. Många utvecklare stöter på problem när de försöker finjustera dessa streckkoder för detaljhandels- eller logistiklabeled, och dokumentationen kan kännas lite tunn.  

I den här handledningen går vi igenom **hur man genererar databar**, konfigurerar X‑Dimension, och—mest av allt—**hur man ställer in bildförhållandet** så att skannern läser den felfritt. I slutet har du ett färdigt kodexempel som skapar två streckkods‑bilder bredvid varandra, en med bildförhållande 15 och en annan med 30. Ingen gåta, bara tydliga steg.

## Vad den här guiden täcker

- Att sätta upp en **barcode generator c#** med det populära Aspose.BarCode‑biblioteket.  
- Förstå anatomin av en **databar staplad omnidirektionell** symbol.  
- Finjustera **aspect ratio** för att uppfylla GS1‑specifikationerna.  
- Spara resultatet som PNG‑filer som du kan lägga in i vilket .NET‑projekt som helst.  

Förutsättningar? Bara ett aktuellt .NET‑SDK (4.6+ eller .NET Core 3.1+) och ett NuGet‑referens till `Aspose.BarCode`. Om du har det, är du redo att köra.

---

## Förstå databar staplad omnidirektionell streckkod

**databar staplad omnidirektionell**‑formatet packar ett 14‑siffrigt GTIN och ett par kompletterande siffror i en kompakt, två‑radig symbol. Det är det föredragna valet för små föremål där utrymmet är begränsat—tänk kosmetika, läkemedel eller små snack‑paket.

Varför spelar bildförhållandet roll? Streckkodsspecifikationen definierar ett förhållande mellan bredd och höjd som påverkar skanningspålitligheten. För mycket komprimerad, och en scanner kan missa en stapel; för mycket utdragen, och koden kan överskrida etikettens dimensioner. `AspectRatio`‑egenskapen på `DataBar`‑objektet låter dig finjustera den balansen.

## Steg 1: Skapa en **databar staplad omnidirektionell** streckkodsgenerator

Först startar du generatorn med rätt kodningstyp och den data du vill bädda in. Här använder vi ett exempel‑GTIN‑14‑värde omslutet av parenteser, som specifikationen förväntar sig.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Initialize the generator for a DataBar Stacked Omnidirectional barcode
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

> **Proffstips:** Strängen måste börja med “(01)” för att tala om för biblioteket att de följande 14 siffrorna är ett GTIN. Att glömma parenteserna kastar ett `ArgumentException`.

## Steg 2: Definiera den grundläggande storleken på staplarna (X‑Dimension)

X‑Dimension styr hur många pixlar varje modul (den minsta stapeln) upptar. En vanlig startpunkt är 2 pixlar per modul, vilket ger en bra balans mellan läsbarhet och filstorlek.

```csharp
// Set 2 pixels per module – a safe default for most printers
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Om du skriver ut på en högupplöst laserskrivare kan du öka detta till 3 eller 4 pixlar. Kom bara ihåg: en större X‑Dimension innebär större totala streckkodsdimensioner.

## Steg 3: **Hur man ställer in bildförhållandet** – första versionen (15)

Nu kommer delen som får många att snubbla: `AspectRatio`. Det är ett enkelt heltal, men det påverkar direkt höjden på de staplade raderna i förhållande till bredden.

```csharp
// Aspect ratio of 15 – the default for many retail scenarios
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;

// Save the first image
barcodeGenerator.Save(@"YOUR_DIRECTORY\DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Den resulterande PNG‑filen kommer att se ut ungefär så här (platshållarbild):

![databar staplad omnidirektionell streckkod med bildförhållande 15](databar_aspect_ratio_15.png)

*Bild‑alt‑text (för SEO):* **databar staplad omnidirektionell streckkod med bildförhållande 15**.

## Steg 4: **Hur man ställer in bildförhållandet** – andra versionen (30)

Ibland krävs ett högre förhållande, särskilt när etikettens höjd är generös eller skannern förväntar sig en högre symbol. Låt oss byta till 30 och spara en andra fil.

```csharp
// Change the aspect ratio to 30 for a taller barcode
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;

// Save the second image
barcodeGenerator.Save(@"YOUR_DIRECTORY\DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

Och resultatet:

![databar staplad omnidirektionell streckkod med bildförhållande 30](databar_aspect_ratio_30.png)

*Bild‑alt‑text:* **databar staplad omnidirektionell streckkod med bildförhållande 30**.

Du kommer att märka att staplarna är högre, men bredden förblir densamma eftersom vi behöll X‑Dimension konstant.

## Steg 5: Verifiera resultatet – snabb kontroll

Öppna de två PNG‑filerna i någon bildvisare. Båda bör visa en ren, två‑radig streckkod med samma numeriska data. Om du har en handhållen scanner tillgänglig, försök skanna varje fil. Scannern bör returnera den råa GTIN‑strängen `(01)12345678901231`.  

Om en skanning misslyckas, dubbelkolla:

1. **X‑Dimension** är inte för låg (under 1 pixel är omöjligt).  
2. **AspectRatio** matchar vad din skannings‑hardware förväntar sig.  
3. **output path** är skrivbar—ibland gömmer sig `UnauthorizedAccessException` bakom ett tyst fel.

## Vanliga fallgropar när du **skapar databar streckkod**

| Symptom | Likely cause | Fix |
|---------|--------------|-----|
| Tom bild sparad | `EncodeTypes`‑mismatch (t.ex. använder `DatabarExpanded` istället för `DatabarStackedOmniDirectional`) | Verifiera `EncodeTypes.DatabarStackedOmniDirectional` |
| Streckkod för bred | X‑Dimension satt för hög | Minska `XDimension.Pixels` |
| Scanner rapporterar “invalid format” | Bildförhållandet stöds inte av scanner‑modellen | Justera `AspectRatio` till 15 eller 30 enligt enhetsspecifikationerna |
| Undantag vid `Save` | Utdatamappen saknas eller ingen skrivbehörighet | Skapa mappen eller kör med förhöjda rättigheter |

## Avancerat: Dynamiskt välja bildförhållandet

I verkliga appar kan du behöva välja ett bildförhållande baserat på etikettens storlek. Här är en liten hjälpfunktion som väljer 15 för smala etiketter och 30 för höga.

```csharp
private static int ChooseAspectRatio(int labelWidthPx, int labelHeightPx)
{
    // Simple heuristic: if height > 2× width, use a taller ratio
    return (labelHeightPx > 2 * labelWidthPx) ? 30 : 15;
}

// Usage
int chosenRatio = ChooseAspectRatio(200, 500);
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = chosenRatio;
barcodeGenerator.Save(@"YOUR_DIRECTORY\DatabarDynamic.png", BarCodeImageFormat.Png);
```

Nu anpassar din **barcode generator c#**‑kod sig i farten—ingen anledning att hårdkoda två separata sparningar.

## Sammanfattning – vad vi uppnådde

- **Skapade** en **databar staplad omnidirektionell** streckkodsgenerator i C#.  
- **Ställde in** X‑Dimension till 2 pixlar per modul för skarp rendering.  
- **Demonstrerade** **hur man ställer in bildförhållandet** både till 15 och 30, och sparade varje som PNG.  
- **Utforskade** vanliga fel och erbjöd en liten dynamisk‑förhållande‑hjälpare.  

Allt detta får plats i en enda, självständig fil som du kan lägga in i vilket .NET‑projekt som helst. Inga externa skript, inga mystiska konfigurationsfiler.

## Vad blir nästa steg? Utöka ditt streckkodslåda

Nu när du behärskar grunderna för **create databar barcode**, överväg att utforska:

- **Lägga till mänskligt läsbar text** under symbolen (`barcodeGenerator.Parameters.Barcode.CodeTextParameters.ShowCodeText = true`).  
- **Bädda in streckkoden** direkt i en PDF med `Aspose.Pdf` för fakturagenerering.  
- **Batch‑bearbetning** av en lista med GTIN‑nummer med en `foreach`‑loop och namnge varje fil efter dess produktkod.  

Var och en av dessa ämnen bygger på samma grundkoncept du just lärt dig, och de kommer göra dina **barcode generator c#**‑projekt ännu kraftfullare.

### Avslutande tankar

Att generera en **databar staplad omnidirektionell** streckkod i C# är ingen magi; det är bara ett fåtal egenskapsjusteringar på ett robust bibliotek. Genom att kontrollera X‑Dimension och **aspect ratio** får du full kontroll över streckkodens form och skanningspålitlighet.  

Kör koden, justera siffrorna, och se scannern dansa. Om du stöter på problem, gå tillbaka till tabellen “Vanliga fallgropar”—de flesta problem löses med en snabb egenskapsjustering.  

Lycklig kodning, och må dina etiketter alltid skannas på första försöket!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [Customize databar stacked omnidirectional Aspect Ratio in .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/)
- [One-Dimensional Databar Barcode Height Adjustment](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
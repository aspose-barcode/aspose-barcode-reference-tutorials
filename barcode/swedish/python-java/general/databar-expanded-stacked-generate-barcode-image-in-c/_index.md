---
category: general
date: 2026-08-15
description: Databar utökade staplad streckkodsgenerering i C#. Lär dig hur du genererar
  streckkodsbild, ställer in kolumner och rader för DataBar‑layouter.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- generate barcode image
- how to generate barcode
- how to set columns
- how to set rows
language: sv
lastmod: 2026-08-15
og_description: Databar utökade staplad streckkodsgenerering i C#. Följ den här steg‑för‑steg‑guiden
  för att generera streckkodsbilder, ange kolumner och ange rader effektivt.
og_image_alt: Screenshot of a databar expanded stacked barcode generated with C#
og_title: Databar expanded stacked – generera streckkodsbild i C#
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Databar expanded stacked barcode generation in C#. Learn how to generate
    barcode image, set columns and rows for DataBar layouts.
  headline: 'Databar expanded stacked: generate barcode image in C#'
  type: TechArticle
- description: Databar expanded stacked barcode generation in C#. Learn how to generate
    barcode image, set columns and rows for DataBar layouts.
  name: 'Databar expanded stacked: generate barcode image in C#'
  steps:
  - name: 1. Install the Aspose.BarCode library
    text: 'The code uses the **Aspose.BarCode for .NET** library, which provides the
      `BarcodeGenerator` class. Install the NuGet package with the following command:'
  - name: 2. Create a barcode generator for **databar expanded stacked**
    text: The generator is the entry point for all barcode operations. You must specify
      the symbology (`EncodeTypes.DatabarExpandedStacked`) and the text to encode.
  - name: 3. How to set columns for DataBar
    text: The `Columns` property controls how many vertical modules appear in the
      stacked barcode. Valid values are 2, 3, or 4. Setting columns influences the
      barcode’s width and the amount of data it can store.
  - name: 4. Save the 4‑column barcode image
    text: Saving the image produces a file that you can embed in reports, invoices,
      or mobile apps. The `Save` method accepts a file path and an image format.
  - name: 5. How to set rows for DataBar
    text: Rows add a second dimension to the stacked layout, allowing more data to
      be encoded without widening the barcode. The `Rows` property defaults to 1;
      you can increase it up to 3 for the expanded stacked variant.
  - name: 6. Save the 3‑row barcode image
    text: '```csharp // Step 5: Save the 3‑row barcode image barcode.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  - name: 7. Complete C# example to generate barcode image
    text: 'Putting all steps together yields a self‑contained program you can copy
      into a console application:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: 'Databar expanded stacked: generera streckkodbild i C#'
url: /sv/python-java/general/databar-expanded-stacked-generate-barcode-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Databar expanded stacked: generera streckkodbild i C#

Om du behöver generera en **databar expanded stacked** streckkodbild i C#, visar den här guiden exakt **hur man genererar streckkoder** med anpassade kolumn- och radlayouter. Du kommer att se hur du ställer in kolumner, hur du ställer in rader och hur du sparar de resulterande bilderna utan att lämna IDE:n.

Handledningen täcker:

* Skapa en streckkodsgenerator för **databar expanded stacked**-symbologin.  
* Konfigurera en 4‑kolumnslayout och en 3‑radslayout.  
* Spara varje konfiguration som en PNG-fil.  
* Tips för att hantera kantfall såsom ogiltiga kolumnantal.

Ingen extern dokumentation krävs; det kompletta, körbara exemplet ingår.

![Databar expanded stacked barcode example](YOUR_DIRECTORY/DatabarCols4.png){: .center alt="databar expanded stacked streckkod genererad med C#" }

## Steg för generering av databar expanded stacked streckkod

### 1. Installera Aspose.BarCode-biblioteket

Koden använder **Aspose.BarCode for .NET**-biblioteket, som tillhandahåller klassen `BarcodeGenerator`. Installera NuGet-paketet med följande kommando:

```bash
dotnet add package Aspose.BarCode
```

När paketet är installerat, lägg till det erforderliga namnutrymmet högst upp i din fil:

```csharp
using Aspose.BarCode.Generation;
```

### 2. Skapa en streckkodsgenerator för **databar expanded stacked**

Generatorn är ingångspunkten för alla streckkodoperationer. Du måste ange symbologin (`EncodeTypes.DatabarExpandedStacked`) och texten som ska kodas.

```csharp
// Step 1: Create a barcode generator for Databar Expanded Stacked
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*Varför detta är viktigt:* `EncodeTypes`-enumerationen talar om för biblioteket vilket streckkodformat som ska produceras. Att använda **databar expanded stacked** säkerställer att den resulterande bilden följer GS1 DataBar-specifikationen för staplade layouter.

### 3. Så ställer du in kolumner för DataBar

`Columns`-egenskapen styr hur många vertikala moduler som visas i den staplade streckkoden. Giltiga värden är 2, 3 eller 4. Att ställa in kolumner påverkar streckkodens bredd och mängden data den kan lagra.

```csharp
// Step 2: Configure a 4‑column layout
barcode.Parameters.Barcode.DataBar.Columns = 4;
```

**Tips:** Om du försöker tilldela ett värde utanför det tillåtna intervallet, kastar biblioteket ett `ArgumentException`. Validera alltid indata när du exponerar kolumnval för användare.

### 4. Spara 4‑kolumns streckkodsbilden

Att spara bilden skapar en fil som du kan bädda in i rapporter, fakturor eller mobilappar. `Save`-metoden accepterar en filsökväg och ett bildformat.

```csharp
// Step 3: Save the 4‑column barcode image
barcode.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

När filen har skrivits kan du öppna den med vilken bildvisare som helst för att bekräfta att **databar expanded stacked**-mönstret visas korrekt.

### 5. Så ställer du in rader för DataBar

Rader lägger till en andra dimension i den staplade layouten, vilket möjliggör mer data att kodas utan att bredda streckkoden. `Rows`-egenskapen har standardvärdet 1; du kan öka den upp till 3 för den expanded stacked-varianten.

```csharp
// Step 4: Switch to a 3‑row layout (columns remain unchanged)
barcode.Parameters.Barcode.DataBar.Rows = 3;
```

**Varför rader är viktiga:** Att öka antalet rader minskar den totala bredden samtidigt som datakapaciteten bevaras, vilket är användbart för smala etiketter eller mobilskärmar.

### 6. Spara 3‑raders streckkodsbilden

```csharp
// Step 5: Save the 3‑row barcode image
barcode.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

Du har nu två PNG-filer – en med en 4‑kolumnslayout och en annan med en 3‑radslayout – båda använder **databar expanded stacked**-symbologin.

### 7. Komplett C#-exempel för att generera streckkodbild

Att sätta ihop alla steg ger ett fristående program som du kan kopiera in i en konsolapplikation:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace DatabarExpandedStackedDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for Databar Expanded Stacked
            BarcodeGenerator barcode = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Configure a 4‑column layout and save
            barcode.Parameters.Barcode.DataBar.Columns = 4;
            barcode.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("4‑column barcode saved.");

            // Change to a 3‑row layout (columns stay at 4) and save
            barcode.Parameters.Barcode.DataBar.Rows = 3;
            barcode.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("3‑row barcode saved.");
        }
    }
}
```

**Förväntat resultat**

När programmet körs skrivs:

```
4‑column barcode saved.
3‑row barcode saved.
```

och skapar två PNG-filer i `YOUR_DIRECTORY`. Öppna filerna för att verifiera att varje bild visar en giltig **databar expanded stacked** streckkod.

## Vanliga fallgropar och praktiska tips

* **Katalogens existens** – `Save` skapar inte saknade mappar. Se till att `YOUR_DIRECTORY` finns eller använd `Directory.CreateDirectory` innan du sparar.
* **Kolumnbegränsningar** – Värden annat än 2, 3 eller 4 utlöser ett undantag. Skydda mot användarinmatningsfel med en enkel intervallkontroll:

  ```csharp
  int columns = 4;
  if (columns < 2 || columns > 4) throw new ArgumentOutOfRangeException(nameof(columns));
  barcode.Parameters.Barcode.DataBar.Columns = columns;
  ```

* **Radsbegränsningar** – Den expanded stacked-varianten stödjer upp till 3 rader. Att sätta `Rows` till 0 eller ett värde större än 3 ger också ett undantag.
* **Bildformat** – `BarCodeImageFormat.Png` ger förlustfri kvalitet, vilket är idealiskt för utskrift. Använd `Jpeg` endast när filstorlek är en huvudfaktor.

## Nästa steg

Nu när du vet **hur man genererar streckkoder** med anpassade kolumn- och radkonfigurationer, kan du:

* Integrera generatorn i ett web‑API för att leverera streckkodsbilder på begäran.  
* Kombinera streckkoden med PDF‑genereringsbibliotek för att bädda in den i fakturor.  
* Experimentera med andra DataBar-varianter (`DatabarExpanded`, `DatabarLimited`) med samma `Parameters.Barcode.DataBar`‑objekt.

För djupare anpassning — såsom att ändra stapelfärg, lägga till mänskligt läsbar text eller applicera QR‑kod‑överlägg — se Aspose.BarCode-dokumentationen om `BarcodeGenerator`‑egenskaper.

---

Genom att följa den här guiden har du bemästrat **databar expanded stacked**‑arbetsflödet, lärt dig **hur man ställer in kolumner**, **hur man ställer in rader**, och skapat två olika streckkodsbilder som är redo för produktionsbruk. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Generera streckkodbild – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Skapa DotCode streckkodbild – rader & kolumner (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Hur man genererar streckkod – En-dimensionella streckkodstyper](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
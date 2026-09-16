---
category: general
date: 2026-09-16
description: Lär dig hur du ställer in streckkodskolumner i C# med BarcodeGenerator
  och även hur du ställer in streckkodsrader för DataBar Expanded Stacked‑streckkoder.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- set barcode columns
- set barcode rows
- DataBar Expanded Stacked
- BarcodeGenerator C#
- barcode image format
- configure barcode dimensions
language: sv
lastmod: 2026-09-16
og_description: Ställ in streckkodskolumner i C# snabbt. Den här guiden visar hur
  du konfigurerar kolumner, rader och bildformat med BarcodeGenerator.
og_image_alt: DataBar Expanded Stacked barcode showing custom columns and rows
og_title: Ställ in streckkodskolumner och rader i C# – komplett BarcodeGenerator‑guide
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set barcode columns in C# using BarcodeGenerator and also
    set barcode rows for DataBar Expanded Stacked barcodes.
  headline: How to set barcode columns and rows with C# BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Hur man ställer in streckkodskolumner och rader med C# BarcodeGenerator
url: /sv/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man ställer in streckkodskolumner och -rader med C# BarcodeGenerator

Om du behöver ställa in streckkodskolumner i en C#-applikation visar den här handledningen de exakta stegen som krävs. Du kommer att se hur du konfigurerar både kolumner och rader för en DataBar Expanded Stacked‑streckkod och sedan sparar resultatet som en PNG‑bild.

Att generera streckkoder programatiskt sparar dig från manuellt designarbete och garanterar konsistens i rapporter, fakturor och produktetiketter. Exemplet nedan täcker hela arbetsflödet, från installation av biblioteket till att producera två bilder—en med ett anpassat kolumnantal och en annan med ett anpassat radantal.

## Förutsättningar

* .NET 6.0 eller senare installerat.
* En referens till **Aspose.BarCode for .NET** NuGet‑paketet. Installera det med:

```bash
dotnet add package Aspose.BarCode
```

* Skrivbehörighet till en mapp där de genererade PNG‑filerna kommer att sparas.

Dessa krav säkerställer att koden kompileras och körs utan ytterligare konfiguration.

## Hur man ställer in streckkodskolumner i C#

Det första stora steget är att skapa en `BarcodeGenerator`‑instans för **DataBar Expanded Stacked**‑symbologin och tilldela önskat kolumnantal.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize a DataBar Expanded Stacked barcode generator with the target text.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the number of columns. The DataBar object exposes a Columns property.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image using the PNG format.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**Varför detta fungerar:**  
`EncodeTypes.DatabarExpandedStacked` talar om för biblioteket vilken symbologi som ska renderas. Att sätta `Parameters.Barcode.DataBar.Columns` ändrar den interna moduluppsättningen, vilket direkt påverkar streckkodens visuella bredd. `Save`‑metoden skriver bilden till disk i det begärda `BarCodeImageFormat`.

### Förväntat resultat
Öppna `C:\Barcodes\DatabarCols4.png` i någon bildvisare. Du bör se en DataBar Expanded Stacked‑streckkod som är bredare än standard eftersom den använder fyra kolumner.

## Hur man ställer in streckkodsrader i C#

Efter att du har sparat den kolumnbaserade bilden kan du vilja ha en streckkod som varierar i höjd genom att justera rader. Processen speglar kolumnkonfigurationen men använder `Rows`‑egenskapen istället.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 4️⃣ Re‑initialize the generator for a fresh configuration.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 5️⃣ Set the number of rows. This property controls the vertical module count.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6️⃣ Save the barcode image with the row configuration.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**Varför detta fungerar:**  
Att återinitiera generatorn säkerställer att den tidigare kolumninställningen inte stör radkonfigurationen. Att ändra `Parameters.Barcode.DataBar.Rows` modifierar streckkodens höjd och ger en högre bild när radantalet överstiger standard.

### Förväntat resultat
Öppna `C:\Barcodes\DatabarRows3.png`. Streckkoden kommer att visas högre, vilket återspeglar den tre‑radiga konfigurationen.

## Fullt end‑to‑end‑exempel

Nedan är ett enda program som skapar båda bilderna i en körning. Att hålla koden i en fil visar hur du kan växla mellan kolumn- och radkonfigurationer utan att starta om applikationen.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Common text for both barcodes.
        const string barcodeText = "Databar Expanded Stacked long";

        // ---------- Column configuration ----------
        var colGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        colGenerator.Parameters.Barcode.DataBar.Columns = 4;
        colGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Row configuration ----------
        var rowGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;
        rowGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

När programmet körs produceras två PNG‑filer:

* **DatabarCols4.png** – streckkod med fyra kolumner.  
* **DatabarRows3.png** – streckkod med tre rader.

Båda filerna använder **barcode image format** PNG, vilket bevarar skarpa kanter och stödjer förlustfri kompression—idealiskt för utskrift och digital visning.

## Vanliga frågor och tips

| Question | Answer |
|----------|--------|
| *Kan jag använda JPEG istället för PNG?* | Ja. Ersätt `BarCodeImageFormat.Png` med `BarCodeImageFormat.Jpeg`. JPEG är mindre men introducerar komprimeringsartefakter, vilket kan påverka skannerns tillförlitlighet. |
| *Vad är det maximala antalet kolumner eller rader?* | Biblioteket validerar värdena mot DataBar‑specifikationen. Värden utanför det tillåtna intervallet kastar ett `ArgumentException`. Kontrollera Aspose.BarCode‑dokumentationen för de exakta gränserna. |
| *Behöver jag disponera `BarcodeGenerator`?* | Klassen implementerar `IDisposable`. Omge generatorn med ett `using`‑block om du skapar många instanser i en loop för att snabbt frigöra ohanterade resurser. |
| *Hur ändrar jag streckkodens storlek utan att ändra kolumner/rader?* | Använd `barcodeGenerator.Parameters.Image.Width` och `Height` för att skala utdata‑bilden samtidigt som moduluppsättningen förblir oförändrad. |

**Pro tip:** När du genererar streckkoder för högupplöst utskrift, öka utdata‑bildens dimensioner (`Width`/`Height`) snarare än kolumn‑ eller radantalet. Detta tillvägagångssätt bevarar den standardmodulstorlek som definieras av symbologin samtidigt som du får en skarpare bild.

## Slutsats

Du vet nu hur du ställer in streckkodskolumner och -rader i C# med hjälp av **BarcodeGenerator**‑klassen. Guiden täckte initiering av generatorn, konfiguration av kolumn- och radantal, sparande av streckkoden i PNG‑format samt hantering av vanliga variationer som bildformatändringar och resurshantering.

Nästa steg är att utforska relaterade ämnen som **anpassa streckkodsfärger**, **lägga till mänskligt läsbar text** och **bädda in streckkoder i PDF‑dokument**. Alla dessa tillägg bygger på samma konfigurationsmönster som demonstrerats här, vilket gör att du kan skapa fullt utrustade streckkodslösningar för vilken .NET‑applikation som helst.

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Barcode Generator‑exempel i C# – Ställ in kolumner, rader & exportera bild](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [databar expanded stacked streckkodsguide – hur man genererar och dimensionerar den i C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Barcode generator‑exempel i C# – ställ in bredd och höjd](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
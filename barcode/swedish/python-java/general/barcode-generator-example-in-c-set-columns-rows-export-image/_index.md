---
category: general
date: 2026-07-15
description: Barcode‑generatorexempel i C# som visar hur man ställer in kolumner,
  hur man ställer in rader och snabbt exporterar streckkodsbilden. Följ den här steg‑för‑steg‑guiden.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to set columns
- how to set rows
- export barcode image
- create barcode image c#
language: sv
lastmod: 2026-07-15
og_description: Barcode‑generatorexempel i C# visar hur man ställer in kolumner, hur
  man ställer in rader och exporterar streckkodsbilden. Lär dig hela arbetsflödet
  på några minuter.
og_image_alt: Screenshot of a barcode generator example showing column and row settings
  in C#
og_title: Exempel på streckkodsgenerator i C# – Kolumner, rader och bildexport
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Barcode generator example in C# showing how to set columns, how to
    set rows, and export barcode image quickly. Follow this step‑by‑step guide.
  headline: Barcode Generator Example in C# – Set Columns, Rows & Export Image
  type: TechArticle
- description: Barcode generator example in C# showing how to set columns, how to
    set rows, and export barcode image quickly. Follow this step‑by‑step guide.
  name: Barcode Generator Example in C# – Set Columns, Rows & Export Image
  steps:
  - name: '**Add colors** – Set `generator.Parameters.Barcode.ForegroundColor` to
      `Color.Blue`.'
    text: '**Add colors** – Set `generator.Parameters.Barcode.ForegroundColor` to
      `Color.Blue`.'
  - name: '**Encode different data** – Pass a variable string instead of the hard‑coded
      `"Databar Expanded Stacked long"`.'
    text: '**Encode different data** – Pass a variable string instead of the hard‑coded
      `"Databar Expanded Stacked long"`.'
  - name: '**Batch processing** – Loop over a CSV file of product codes, generating
      a PNG for each.'
    text: '**Batch processing** – Loop over a CSV file of product codes, generating
      a PNG for each.'
  - name: '**Integrate with a web API** – Expose an endpoint that returns the barcode
      as a base64‑encoded string.'
    text: '**Integrate with a web API** – Expose an endpoint that returns the barcode
      as a base64‑encoded string.'
  type: HowTo
tags:
- barcode
- C#
- image export
title: Exempel på streckkodsgenerator i C# – Ställ in kolumner, rader och exportera
  bild
url: /sv/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Exempel på streckkodsgenerator i C# – Fullständig genomgång

Har du någonsin undrat hur man skapar ett **barcode generator example** i C# som låter dig justera kolumner, rader och sedan exportera resultatet som en bild? Du är inte ensam. Många utvecklare stöter på problem när de behöver ett snabbt sätt att generera DataBar Expanded Stacked‑streckkoder med anpassade layoutalternativ. I den här handledningen löser vi det problemet steg‑för‑steg och visar dig **how to set columns**, **how to set rows**, och slutligen **export barcode image**‑filer – allt med ren, produktionsklar kod.

När du har gått igenom guiden kommer du att ha ett komplett, körbart program som skapar en streckkodsbild, justerar dess layout och sparar två PNG‑filer till disk. Inga mystiska bibliotek, ingen dold konfiguration – bara ren C# och ett pålitligt barcode SDK.

---

## Förutsättningar

- **.NET 6.0** (eller någon senare .NET‑version). Koden kompilerar även med .NET Framework, men .NET 6+ ger dig de senaste körningsförbättringarna.
- Ett **barcode generation library** som stödjer DataBar Expanded Stacked. I exemplen använder vi **Aspose.BarCode for .NET**, som är gratis för provperiod och erbjuder ett enkelt API.
- En utvecklingsmiljö – Visual Studio 2022, Rider eller VS Code fungerar alla.
- Skrivbehörighet till en mapp där PNG‑filerna ska sparas.

Om du ännu inte har biblioteket, hämta det från NuGet:

```bash
dotnet add package Aspose.BarCode
```

Den enda raden hämtar allt du behöver, inklusive klassen `BarcodeGenerator` och enum‑värdet `BarCodeImageFormat` som används senare.

---

## Steg 1: Skapa projektskelettet

Skapa en ny konsolapplikation och lägg till de nödvändiga `using`‑direktiven:

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum
```

Här är den **kompletta** `Program.cs`‑filens skelett:

```csharp
namespace BarcodeDemo
{
    internal class Program
    {
        static void Main(string[] args)
        {
            // We'll fill this in in the next steps.
        }
    }
}
```

> **Pro tip:** Håll `Main`‑metoden ren; vi kommer att delegera det tunga arbetet till hjälpfunktioner senare. Detta gör koden enklare att testa och återanvända.

---

## Steg 2: Skapa barcode generator‑exemplet

Nu bygger vi kärnan **barcode generator example** som skapar en DataBar Expanded Stacked‑streckkod. Detta är tutorialens kärna.

```csharp
static BarcodeGenerator CreateGenerator()
{
    // Step 1: Instantiate the generator for DataBar Expanded Stacked.
    // The second argument is the text you want encoded.
    var generator = new BarcodeGenerator(
        EncodeTypes.DatabarExpandedStacked,
        "Databar Expanded Stacked long");

    // Optional: fine‑tune image size or resolution if needed.
    generator.Parameters.Image.Width = 300;
    generator.Parameters.Image.Height = 150;

    return generator;
}
```

Varför separerar vi detta till en egen metod? Det isolerar logiken för **barcode generator example**, vilket gör den återanvändbar om du senare behöver generera flera streckkoder med olika data.

---

## Steg 3: Så här ställer du in kolumner

DataBar Expanded Stacked‑formatet kan renderas i en kolumnorienterad layout. Som standard väljer SDK ett rimligt värde, men du behöver ofta anpassa det till en specifik etikettstorlek. Här är **how to set columns** till fyra:

```csharp
static void SetColumns(BarcodeGenerator generator, int columns)
{
    // Step 2: Adjust the column count.
    generator.Parameters.Barcode.DataBar.Columns = columns;
}
```

> **Varför kolumner är viktiga:** Varje kolumn lägger till vertikalt utrymme, vilket kan vara avgörande när du skriver ut på smala etiketter. Att sätta den till `4` ger dig en balanserad, läsbar streckkod utan att kompromissa med skanningspålitligheten.

I huvudflödet kommer vi att anropa denna metod:

```csharp
var generator = CreateGenerator();
SetColumns(generator, 4);
```

---

## Steg 4: Så här ställer du in rader

Ibland behöver du en mer kompakt layout, särskilt om du skriver ut på en kort, bred etikett. Det är då **how to set rows** kommer in i bilden. Att byta från en kolumn‑centrerad till en rad‑centrerad arrangemang kan minska streckkodens fotavtryck.

```csharp
static void SetRows(BarcodeGenerator generator, int rows)
{
    // Step 4: Change the layout to use rows instead of columns.
    generator.Parameters.Barcode.DataBar.Rows = rows;
}
```

Att anropa den ser ut så här:

```csharp
SetRows(generator, 3);
```

> **Edge case‑notering:** Du kan inte sätta både kolumner *och* rader samtidigt – SDK:n prioriterar rader om du tilldelar ett icke‑noll‑värde till `Rows`. Så se till att rensa den andra egenskapen om du byter layout:

```csharp
generator.Parameters.Barcode.DataBar.Columns = 0; // Disable columns when using rows
```

---

## Steg 5: Exportera streckkodsbild

Med layouten konfigurerad är sista delen att **export barcode image**‑filer. SDK:n stödjer PNG, JPEG, BMP och mer. PNG är förlustfri och fungerar bra för de flesta etikettskrivare.

```csharp
static void SaveBarcode(BarcodeGenerator generator, string filePath)
{
    // Step 5: Save the image using the PNG format.
    generator.Save(filePath, BarCodeImageFormat.Png);
}
```

Sätt ihop allt i `Main`:

```csharp
static void Main(string[] args)
{
    // 1️⃣ Create the generator (barcode generator example)
    var generator = CreateGenerator();

    // 2️⃣ Set columns and save the first image
    SetColumns(generator, 4);
    string colsPath = @"YOUR_DIRECTORY\DatabarCols4.png";
    SaveBarcode(generator, colsPath);
    Console.WriteLine($"Barcode with 4 columns saved to {colsPath}");

    // 3️⃣ Switch to rows and save the second image
    SetRows(generator, 3);
    // Clear columns to avoid conflict
    generator.Parameters.Barcode.DataBar.Columns = 0;
    string rowsPath = @"YOUR_DIRECTORY\DatabarRows3.png";
    SaveBarcode(generator, rowsPath);
    Console.WriteLine($"Barcode with 3 rows saved to {rowsPath}");
}
```

### Förväntad utdata

När du kör programmet bör du se två PNG‑filer i `YOUR_DIRECTORY`:

- **DatabarCols4.png** – en streckkod renderad med fyra vertikala kolumner.
- **DatabarRows3.png** – samma data, men upplagd i tre horisontella rader.

Båda bilderna kommer att vara 300 × 150 px (som satt i `CreateGenerator`) och redo för utskrift eller inbäddning i en PDF.

---

## Vanliga fallgropar & tips

| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **Fel i filsökväg** | Att använda en relativ sökväg utan rätt katalog kan kasta `DirectoryNotFoundException`. | Använd `Path.Combine(Environment.CurrentDirectory, "output", "file.png")` eller säkerställ att mappen finns med `Directory.CreateDirectory`. |
| **Konflikt mellan rader och kolumner** | Att sätta båda egenskaperna får SDK:n att ignorera kolumner. | Sätt explicit den motsatta egenskapen till `0` när du byter layout. |
| **Ej stöd för streckkodstyp** | Inte alla streckkodsbibliotek stödjer DataBar Expanded Stacked. | Verifiera att din biblioteks version innehåller `EncodeTypes.DatabarExpandedStacked`. |
| **Bildkvaliteten för låg** | Standard‑DPI kan vara otillräcklig för högupplösta skrivare. | Justera `generator.Parameters.Image.ResolutionX/Y` till `300` eller högre. |

---

## Utöka barcode generator‑exemplet

Nu när du har ett robust **barcode generator example**, kanske du undrar vad mer du kan göra.

1. **Add colors** – Sätt `generator.Parameters.Barcode.ForegroundColor` till `Color.Blue`.
2. **Encode different data** – Skicka en variabel sträng istället för den hårdkodade `"Databar Expanded Stacked long"`.
3. **Batch processing** – Loopa över en CSV‑fil med produktkoder och generera en PNG för varje.
4. **Integrate with a web API** – Exponera en endpoint som returnerar streckkoden som en base64‑kodad sträng.

Varje av dessa utökningar följer samma mönster: konfigurera `BarcodeGenerator`‑instansen och anropa sedan `Save` eller `Export` efter behov.

---

## Slutsats

Vi har gått igenom ett komplett **barcode generator example** i C# som visar **how to set columns**, **how to set rows** och hur man **export barcode image**‑filer. Koden är självständig, körs direkt med Aspose.BarCode och demonstrerar bästa praxis för läsbarhet och underhållbarhet.

Känn dig fri att experimentera – byt ut datasträngen, justera bilddimensionerna eller byt till en annan streckkodssymbologi. De koncept du lärt dig här – initiering av generatorn, konfiguration av layoutparametrar och export – gäller i princip alla streckkodstyper som stöds av SDK:n.

Har du frågor om att skapa barcode image c#‑program, eller behöver hjälp med en specifik etikettskrivare? Lämna en kommentar nedan, och lycka till med kodningen!

---

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [Skapa DotCode streckkodsbild – rader & kolumner (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Skapa streckkodsbild c# – Konfigurera Codablock F rader & kolumner](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Skapa streckkodsbild C# – GS1 DataMatrix‑exempel](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
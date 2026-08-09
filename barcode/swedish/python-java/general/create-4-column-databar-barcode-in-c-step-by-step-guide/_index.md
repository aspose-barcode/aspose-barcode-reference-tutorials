---
category: general
date: 2026-08-09
description: Skapa 4‑kolumns databar-kodstreck i C# snabbt med Aspose.BarCode. Lär
  dig hur du konfigurerar kolumner, rader och sparar PNG‑bilder i den här kortfattade
  guiden.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create 4‑column databar barcode
- databar expanded stacked
- barcode generator c#
- set barcode rows
- barcode image format
language: sv
lastmod: 2026-08-09
og_description: Skapa en 4‑kolumns databar‑streckkod i C# med Aspose.BarCode, anpassa
  sedan rader och exportera PNG‑bilder för din app.
og_image_alt: Screenshot of a 4‑column DataBar Expanded Stacked barcode generated
  in C#
og_title: Skapa 4‑kolumns databar‑streckkod i C# – snabb handledning
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create 4‑column databar barcode in C# quickly with Aspose.BarCode.
    Learn how to configure columns, rows, and save PNG images in this concise guide.
  headline: Create 4‑column databar barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Create 4‑column databar barcode in C# quickly with Aspose.BarCode.
    Learn how to configure columns, rows, and save PNG images in this concise guide.
  name: Create 4‑column databar barcode in C# – step‑by‑step guide
  steps:
  - name: Configure DataBar Expanded Stacked columns
    text: If you need a different column count, simply change the integer assigned
      to `Columns`. The property accepts values from 1 to 4 for the expanded stacked
      variant.
  - name: Save the barcode image
    text: The `BarCodeImageFormat` enumeration provides several options (`Png`, `Jpeg`,
      `Bmp`, `Gif`, `Tiff`). PNG is loss‑less and works well for most web and desktop
      scenarios.
  - name: Set barcode rows dynamically
    text: 'You can compute the row count at runtime based on input data:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- DataBar
title: Skapa 4‑kolumns databar‑streckkod i C# – steg‑för‑steg‑guide
url: /sv/python-java/general/create-4-column-databar-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa 4‑kolumns databar streckkod i C# – steg‑för‑steg guide

Om du behöver **skapa 4‑kolumns databar streckkod** i C#, visar den här handledningen exakt hur du gör. Vi går igenom att generera en DataBar Expanded Stacked streckkod, konfigurera fyra kolumner och spara resultatet som en PNG‑bild.

I den här guiden kommer du att lära dig hur du:

* Initierar `BarcodeGenerator` för en **DataBar Expanded Stacked**‑symbol.  
* Ställer in kolumnantalet till 4 (huvudkravet).  
* Justerar radantalet när du behöver en staplad layout med tre rader.  
* Exporterar streckkoden som en PNG med det lämpliga **barcode image format**.

Du behöver bara Aspose.BarCode for .NET‑biblioteket (version 23.10 eller senare) och en .NET 6+ utvecklingsmiljö såsom Visual Studio 2022. Inga ytterligare beroenden krävs.

---

## Så skapar du 4‑kolumns databar streckkod

Det första steget är att skapa en `BarcodeGenerator`‑instans som riktar sig mot **DataBar Expanded Stacked**‑symboliken. Denna klass kapslar in alla renderingsalternativ, vilket gör det enkelt att växla mellan kolumn‑baserade och rad‑baserade layouter.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise a generator for DataBar Expanded Stacked
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");
        
        // 2️⃣ Set the barcode to use a 4‑column layout
        generator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image as PNG
        generator.Save("DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**Varför detta fungerar:**  
`EncodeTypes.DatabarExpandedStacked` talar om för Aspose.BarCode att producera den staplade versionen av DataBar‑familjen. `DataBar.Columns`‑egenskapen styr hur många vertikala moduler streckkoden upptar. Att sätta den till 4 uppfyller kravet att **skapa 4‑kolumns databar streckkod**. Slutligen skriver `Save` den visuella representationen till disk med **barcode image format** `Png`.

### Konfigurera DataBar Expanded Stacked‑kolumner

Om du behöver ett annat kolumnantal, ändra helt enkelt heltalet som tilldelas `Columns`. Egenskapen accepterar värden från 1 till 4 för den expanderade staplade varianten.

```csharp
// Example: switch to a 2‑column layout
generator.Parameters.Barcode.DataBar.Columns = 2;
```

*Pro tip:* Testa alltid den genererade streckkoden med en scanner som stöder DataBar‑familjen, eftersom enbart det visuella utseendet inte garanterar läsbarhet.

### Spara streckkodbilden

`BarCodeImageFormat`‑enumerationen erbjuder flera alternativ (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`). PNG är förlustfri och fungerar bra för de flesta webb‑ och desktop‑scenarier.

```csharp
generator.Save("DatabarCols4.png", BarCodeImageFormat.Png);
```

Om du behöver ett annat format, ersätt `Png` med önskat enum‑värde. Den sparade filen kan bäddas in direkt i HTML, PDF‑filer eller skrivas ut på etiketter.

## Skapa en streckkod med anpassade rader

Ibland krävs en staplad layout med ett specifikt antal rader istället för kolumner. Samma `BarcodeGenerator`‑klass exponerar en `Rows`‑egenskap för detta ändamål.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class RowExample
{
    static void Main()
    {
        // 1️⃣ Initialise a generator for the same symbology
        BarcodeGenerator rowGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the barcode to use a 3‑row layout
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 3️⃣ Save the image as PNG
        rowGenerator.Save("DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**Varför rader är viktiga:**  
När den staplade streckkoden är högre än den är bred, bestämmer `Rows`‑egenskapen hur många horisontella segment symbolen delas in i. Att sätta `Rows = 3` skapar en staplad streckkod med tre rader, vilket är användbart för smala etikettbredder.

### Ställ in streckkodens rader dynamiskt

Du kan beräkna radantalet vid körning baserat på indata:

```csharp
int desiredRows = GetRowsFromUser(); // your custom logic
rowGenerator.Parameters.Barcode.DataBar.Rows = desiredRows;
```

Denna flexibilitet låter dig **ställa in streckkodens rader** utan att behöva kompilera om applikationen.

## Fullständigt end‑to‑end‑exempel

Nedan är ett enda program som genererar både en 4‑kolumns streckkod och en 3‑radig streckkod, vilket demonstrerar hur de två konfigurationerna kan samexistera.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class FullExample
{
    static void Main()
    {
        // ---------- 4‑column barcode ----------
        BarcodeGenerator colGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");
        colGen.Parameters.Barcode.DataBar.Columns = 4; // create 4‑column databar barcode
        colGen.Save("DatabarCols4.png", BarCodeImageFormat.Png);

        // ---------- 3‑row barcode ----------
        BarcodeGenerator rowGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");
        rowGen.Parameters.Barcode.DataBar.Rows = 3; // set barcode rows to 3
        rowGen.Save("DatabarRows3.png", BarCodeImageFormat.Png);

        // Output confirmation
        System.Console.WriteLine("Barcodes generated:");
        System.Console.WriteLine(" - DatabarCols4.png (4 columns)");
        System.Console.WriteLine(" - DatabarRows3.png (3 rows)");
    }
}
```

**Förväntat resultat:**  
Två PNG‑filer visas i applikationens arbetskatalog:

* `DatabarCols4.png` – en DataBar Expanded Stacked‑streckkod med fyra vertikala kolumner.  
* `DatabarRows3.png` – samma symbolik arrangerad i tre horisontella rader.

Båda bilderna kan öppnas i vilken bildvisare som helst eller bäddas in i en UI‑kontroll.

---

## Vanliga frågor och edge cases

| Question | Answer |
|----------|--------|
| *Kan jag använda en annan streckkodssymbol?* | Ja. Ersätt `EncodeTypes.DatabarExpandedStacked` med ett annat `EncodeTypes`‑värde (t.ex. `EncodeTypes.QR`), men `Columns`‑ och `Rows`‑egenskaperna är specifika för DataBar‑familjer. |
| *Vad händer om datasträngen överskrider maximal längd?* | DataBar Expanded Stacked‑symboliken stödjer upp till 61 numeriska tecken. Att överskrida denna gräns kastar ett `ArgumentException`. Validera indata innan du tilldelar den till generatorn. |
| *Behöver jag avlasta `BarcodeGenerator`?* | `BarcodeGenerator` implementerar `IDisposable`. I en långvarig tjänst, omslut den i ett `using`‑block eller anropa `Dispose()` manuellt för att frigöra inhemska resurser. |
| *Kan jag generera SVG istället för PNG?* | Absolut. Använd `BarCodeImageFormat.Svg` i `Save`‑metoden. |
| *Är biblioteket kompatibelt med .NET Core?* | Aspose.BarCode for .NET stödjer .NET Core 3.1, .NET 5, .NET 6 och senare. Inga kodändringar krävs. |

---

## Slutsats

Du vet nu hur du **skapar 4‑kolumns databar streckkod** i C# med Aspose.BarCode, hur du justerar layouten med rader, och hur du exporterar resultatet i ett bekvämt **barcode image format**. Det kompletta exemplet visar både kolumn‑baserade och rad‑baserade konfigurationer, vilket ger dig en solid grund för alla etikett‑utskrift‑ eller mobil‑scanningsscenarier.

**Nästa steg**

* Experimentera med olika datapayloads och verifiera scanner‑kompatibilitet.  
* Utforska ytterligare stilalternativ såsom förgrunds‑/bakgrundsfärger (`generator.Parameters.Barcode.Color`).  
* Kombinera streckkoden med annan grafik via `Graphics`‑API:t för anpassade etikettdesigner.  

Känn dig fri att anpassa koden för ASP.NET Core, Windows Forms eller Xamarin‑projekt—Aspose.BarCode fungerar på alla .NET‑plattformar. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Create barcode image c# – Configure Codablock F Rows & Columns](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [How to create dotcode extended codetext with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
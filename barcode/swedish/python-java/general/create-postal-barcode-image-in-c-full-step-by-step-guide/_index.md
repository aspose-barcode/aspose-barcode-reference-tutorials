---
category: general
date: 2026-07-27
description: Skapa poststreckkodbild i C# snabbt – lär dig hur du genererar poststreckkod,
  genererar planetstreckkod och hur du ställer in streckkodens höjd.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- how to generate postal barcode
- generate planet barcode
- how to set barcode height
language: sv
lastmod: 2026-07-27
og_description: Skapa poststreckkodbild i C# och behärska hur du genererar poststreckkod,
  genererar planetstreckkod och hur du ställer in streckkodens höjd för perfekta resultat.
og_image_alt: Sample PNG showing Planet and RM4SCC postal barcodes generated with
  Aspose.BarCode
og_title: Skapa poststreckkodsbild i C# – Fullständig programmeringsgenomgång
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create postal barcode image in C# quickly—learn how to generate postal
    barcode, generate planet barcode, and how to set barcode height.
  headline: Create Postal Barcode Image in C# – Full Step‑by‑Step Guide
  type: TechArticle
- description: Create postal barcode image in C# quickly—learn how to generate postal
    barcode, generate planet barcode, and how to set barcode height.
  name: Create Postal Barcode Image in C# – Full Step‑by‑Step Guide
  steps:
  - name: Why set `XDimension`?
    text: '`XDimension` is the pixel width of the smallest bar. If you leave it at
      the library’s default (usually 1 px), the barcode can look cramped on high‑resolution
      screens. Setting it to **4 px** gives a nicely spaced image that prints cleanly
      on most printers.'
  - name: What does `BarHeight.Pixels` actually do?
    text: When you **set barcode height**, you override the library’s automatic calculation.
      By default Aspose.BarCode chooses a height that keeps the barcode square‑ish,
      which is fine for many use‑cases. However, postal standards sometimes demand
      a minimum bar height (e.g., 100 px for high‑resolution printin
  - name: Edge Cases & Common Pitfalls
    text: '- **Zero or negative height** – the library throws `ArgumentException`.
      Always validate user input. - **Non‑integer pixel values** – the property is
      an `int`, so fractions are rounded down automatically. - **Changing DPI after
      setting height** – the visual size changes, but the pixel count stays the'
  - name: Expected Output
    text: 'When you open the generated PNG files you’ll see:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- postal
title: Skapa poststreckkodsbild i C# – Fullständig steg‑för‑steg‑guide
url: /sv/python-java/general/create-postal-barcode-image-in-c-full-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa poststreckkodbild i C# – Fullständig steg‑för‑steg‑guide

Har du någonsin behövt **skapa poststreckkodbild** i C#, men varit osäker på vilka egenskaper du ska justera? Du är inte ensam. Oavsett om du bygger ett system för postetiketter eller bara experimenterar med post‑symbologier, gör det att behärska rätt API‑anrop hela processen till en barnlek.

I den här handledningen går vi igenom **hur man genererar poststreckkods**‑bilder för både Planet‑ och RM4SCC‑format, och vi visar dig **hur du ställer in streckkodens höjd** så att staplarna ser exakt ut som du förväntar dig. I slutet har du en färdig‑att‑köra konsolapp som skapar fyra PNG‑filer – två med standardhöjd och två med en explicit stapelhöjd på 100 px.

## Vad du behöver

- **.NET 6.0** eller senare (koden kompileras även på .NET Framework 4.6+)  
- **Aspose.BarCode for .NET** – NuGet‑paketet som driver `BarcodeGenerator`  
- En mapp på disken där PNG‑filerna kan sparas (ersätt `YOUR_DIRECTORY` i exemplet)  

Om du aldrig har använt Aspose.BarCode tidigare, hämta det från NuGet:

```bash
dotnet add package Aspose.BarCode
```

Det är allt—inga extra DLL‑filer, inga inhemska beroenden. Låt oss dyka ner.

## Skapa poststreckkodbild – Initiera generatorn

Det första du gör är att skapa en `BarcodeGenerator`‑instans. Detta objekt är ingångspunkten för *alla* streckkoder du vill rendera. Du skickar två argument till konstruktorn:

1. Kodningstypen (**encoding type**) (`EncodeTypes.Planet` eller `EncodeTypes.RM4SCC`)  
2. Datat strängen (**data string**) (det numeriska postnumret, till exempel `"123456"`)

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Folder where PNG files will be saved
        const string outputFolder = @"C:\Temp\Barcodes";

        // Ensure the folder exists
        System.IO.Directory.CreateDirectory(outputFolder);

        // ---------- Planet barcode with default height ----------
        var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        // X‑dimension controls the width of the narrowest bar (in pixels)
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string planetDefaultPath = System.IO.Path.Combine(outputFolder, "PlanetDefault.png");
        planetDefaultPath = System.IO.Path.ChangeExtension(planetDefaultPath, "png");
        planetGenerator.Save(planetDefaultPath, BarCodeImageFormat.Png);

        // ---------- RM4SCC barcode with default height ----------
        var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string rm4sccDefaultPath = System.IO.Path.Combine(outputFolder, "RM4SCCDefault.png");
        rm4sccGenerator.Save(rm4sccDefaultPath, BarCodeImageFormat.Png);
```

### Varför sätta `XDimension`?

`XDimension` är pixelbredden på den minsta stapeln. Om du lämnar den på bibliotekets standardvärde (vanligtvis 1 px) kan streckkoden se trång ut på högupplösta skärmar. Att sätta den till **4 px** ger en välavståndad bild som skrivs ut rent på de flesta skrivare.

## Så genereras poststreckkod – Planet‑ och RM4SCC‑typer

Nu när vi har en generator, låt oss prata om de *två* vanligaste post‑symbologierna: **Planet** (används i Storbritannien) och **RM4SCC** (används i USA). Den enda skillnaden i koden är `EncodeTypes`‑enum‑värdet. Allt annat—som sparande, DPI eller PNG‑format—förblir detsamma.

```csharp
        // ---------- Planet barcode with explicit 100 px height ----------
        var planetHeightGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        // Here we answer the “how to set barcode height” question.
        planetHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        string planetHeightPath = System.IO.Path.Combine(outputFolder, "PlanetHeight100.png");
        planetHeightGenerator.Save(planetHeightPath, BarCodeImageFormat.Png);

        // ---------- RM4SCC barcode with explicit 100 px height ----------
        var rm4sccHeightGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        string rm4sccHeightPath = System.IO.Path.Combine(outputFolder, "RM4SCCHeight100.png");
        rm4sccHeightGenerator.Save(rm4sccHeightPath, BarCodeImageFormat.Png);
    }
}
```

### Vad gör `BarHeight.Pixels` egentligen?

När du **ställer in streckkodens höjd** åsidosätter du bibliotekets automatiska beräkning. Som standard väljer Aspose.BarCode en höjd som håller streckkoden ungefär kvadratisk, vilket är okej för många användningsfall. Men poststandarder kräver ibland en minsta stapelhöjd (t.ex. 100 px för högupplöst utskrift). `BarHeight.Pixels`‑egenskapen låter dig uppfylla dessa specifikationer exakt.

## Så ställer du in streckkodshöjd – Kontroll av stapelhöjd för poststandarder

Om du undrar **hur du ställer in streckkodshöjd** för en specifik skrivar‑DPI, kan du kombinera `BarHeight.Pixels` med `Resolution`‑inställningar:

```csharp
        // Example: 300 DPI, 1 inch tall => 300 px
        planetHeightGenerator.Parameters.ImageResolution = 300;
        planetHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 300; // 1‑inch bar at 300 DPI
```

> **Proffstips:** Testa alltid några olika höjder på din målskrivare. För hög och streckkoden kan överskrida etikettens utskrivbara område; för låg och skannrar kan missa tystzonen.

### Kantfall & vanliga fallgropar

- **Noll eller negativ höjd** – biblioteket kastar `ArgumentException`. Validera alltid användarens inmatning.  
- **Icke‑heltal pixelvärden** – egenskapen är en `int`, så bråktal avrundas automatiskt nedåt.  
- **Ändra DPI efter att ha satt höjd** – den visuella storleken ändras, men pixelantalet förblir detsamma. Om du behöver en fysisk storlek (t.ex. 1 cm), beräkna `pixels = DPI * cm / 2.54`.

## Fullt fungerande exempel – Alla steg kombinerade

Nedan är det kompletta, kopiera‑och‑klistra‑klara programmet. Det innehåller felhantering, mappskapande och kommentarer som förklarar varje rad. Kör det från ett konsolprojekt så får du fyra PNG‑filer i `C:\Temp\Barcodes`.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            const string outputFolder = @"C:\Temp\Barcodes";
            Directory.CreateDirectory(outputFolder);

            try
            {
                // 1️⃣ Planet barcode – default (automatic) height
                var planetDefault = new BarcodeGenerator(EncodeTypes.Planet, "123456");
                planetDefault.Parameters.Barcode.XDimension.Pixels = 4;
                string planetDefaultPath = Path.Combine(outputFolder, "PlanetDefault.png");
                planetDefault.Save(planetDefaultPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved: {planetDefaultPath}");

                // 2️⃣ RM4SCC barcode – default (automatic) height
                var rm4sccDefault = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
                rm4sccDefault.Parameters.Barcode.XDimension.Pixels = 4;
                string rm4sccDefaultPath = Path.Combine(outputFolder, "RM4SCCDefault.png");
                rm4sccDefault.Save(rm4sccDefaultPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved: {rm4sccDefaultPath}");

                // 3️⃣ Planet barcode – explicit 100 px height
                var planetHeight = new BarcodeGenerator(EncodeTypes.Planet, "123456");
                planetHeight.Parameters.Barcode.XDimension.Pixels = 4;
                planetHeight.Parameters.Barcode.BarHeight.Pixels = 100;
                string planetHeightPath = Path.Combine(outputFolder, "PlanetHeight100.png");
                planetHeight.Save(planetHeightPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved: {planetHeightPath}");

                // 4️⃣ RM4SCC barcode – explicit 100 px height
                var rm4sccHeight = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
                rm4sccHeight.Parameters.Barcode.XDimension.Pixels = 4;
                rm4sccHeight.Parameters.Barcode.BarHeight.Pixels = 100;
                string rm4sccHeightPath = Path.Combine(outputFolder, "RM4SCCHeight100.png");
                rm4sccHeight.Save(rm4sccHeightPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved: {rm4sccHeightPath}");
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Something went wrong: {ex.Message}");
            }
        }
    }
}
```

### Förväntad output

När du öppnar de genererade PNG‑filerna ser du:

| Fil | Symboltyp | Höjd | Visuella anmärkningar |
|------|-----------|--------|--------------|
| `PlanetDefault.png` | Planet | Automatic (≈ 50 px) | Tunn |

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar streckkod – Endimensionella streckkodstyper](/barcode/english/net/one-dimensional-barcode-types/)
- [Hur man genererar streckkod – Code 39‑konfiguration med Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Hur man genererar DataMatrix‑streckkoder (ECC 200) med Aspose.BarCode för .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
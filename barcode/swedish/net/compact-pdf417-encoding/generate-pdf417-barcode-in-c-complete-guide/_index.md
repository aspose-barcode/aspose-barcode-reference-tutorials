---
category: general
date: 2026-07-15
description: Generera PDF417‑streckkod snabbt och lär dig hur du ställer in kolumner
  för en kompakt PDF417‑streckkodsbild i C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to set columns
- pdf417 barcode image
- Aspose.BarCode PDF417
- C# barcode generation
- compact PDF417
language: sv
lastmod: 2026-07-15
og_description: Generera PDF417‑streckkod med Aspose.BarCode och lär dig hur du ställer
  in kolumner för att skapa en kompakt PDF417‑streckkodsbild.
og_image_alt: Screenshot of a compact PDF417 barcode saved as PNG
og_title: Generera PDF417‑streckkod i C# – Steg‑för‑steg‑guide
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Generate PDF417 barcode quickly and learn how to set columns for a
    compact PDF417 barcode image in C#.
  headline: Generate PDF417 Barcode in C# – Complete Guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Generera PDF417-streckkod i C# – Komplett guide
url: /sv/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generera PDF417-streckkod i C# – Komplett guide

Har du någonsin behövt **generate PDF417 barcode** i ett .NET‑projekt men varit osäker på var du ska börja? Du är inte ensam. I många företagsapplikationer—tänk boarding‑pass‑skrivare, inventarietaggar eller mobilticketing—är PDF417 arbetshästen som packar mycket data i ett litet visuellt fotavtryck.

Här är grejen: Aspose.BarCode‑biblioteket gör hela processen nästan smärtfri, och du kan till och med kontrollera **how to set columns** så att streckkoden blir så kompakt som möjligt. I slutet av den här handledningen har du en färdig‑att‑använda PNG‑bild av en **PDF417 barcode image** som du kan lägga in i vilken UI, e‑post eller utskriftsuppgift som helst.

## Vad du får med dig

- En fullt fungerande C#‑konsolapp som skapar en PDF417‑streckkod.
- Klar förståelse för *X‑Dimension* (modulstorlek) och varför den är viktig.
- Steg‑för‑steg‑instruktioner om **how to set columns** för en tätare streckkod.
- En sparad `PNG`‑fil som du kan öppna omedelbart för att verifiera resultatet.
- Tips för felsökning av vanliga fallgropar (t.ex. oläsliga streckkoder, fel bildformat).

> **Prerequisites** – .NET 6+ SDK, Visual Studio 2022 (eller någon annan editor du föredrar), och ett NuGet‑referens till `Aspose.BarCode`. Inget annat.

## Steg 1: Installera Aspose.BarCode NuGet‑paketet

Innan vi kan *generate PDF417 barcode* måste biblioteket finnas i projektet.

```bash
dotnet add package Aspose.BarCode
```

Den enda raden hämtar alla typer du behöver, inklusive `BarcodeGenerator`, `EncodeTypes` och enum‑en `BarCodeImageFormat`.

> **Pro tip:** Om du riktar dig mot .NET Framework istället för .NET 6, använd det klassiska PowerShell‑kommandot `Install-Package Aspose.BarCode` i Package Manager Console.

## Steg 2: Skapa en minimal konsolapplikation

Låt oss skapa ett litet program som bara producerar en streckkod. Öppna en ny mapp, kör `dotnet new console`, och ersätt sedan den automatiskt genererade `Program.cs` med koden nedan.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Define the data you want to encode.
            string data = "SampleBarcode©";

            // 2️⃣ Instantiate the generator for PDF417.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // 3️⃣ Set the size of a single barcode module (pixel dimension).
            //    This is the “X‑Dimension” – smaller values yield a finer image.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ **How to set columns** – configure the matrix layout.
            //    Fewer columns = taller barcode; more columns = wider barcode.
            generator.Parameters.Barcode.Pdf417.Columns = 3;   // 👈 primary levers
            generator.Parameters.Barcode.Pdf417.Truncate = true; // compact mode

            // 5️⃣ Choose where the PNG will be saved.
            string outputPath = @"./CompactPdf417.png";

            // 6️⃣ Save the generated barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode saved to {outputPath}");
        }
    }
}
```

**Varför detta är viktigt:**  
- `EncodeTypes.Pdf417` talar om för biblioteket att vi vill ha en PDF417‑streckkod, inte QR eller Code128.  
- `XDimension.Pixels` styr upplösningen för varje liten svart eller vit modul.  
- Blocket **how to set columns** påverkar direkt formen på **PDF417 barcode image**.  
- `Truncate = true` tar bort onödiga tomma rader, vilket ger dig det ”kompakta” utseendet som många skannrar älskar.

## Steg 3: Gå djupare – Förstå kolumner och trunkering

### Hur man sätter kolumner

PDF417 ordnar data i en matris av *rows* × *columns*. Biblioteket har som standard 5 kolumner, vilket fungerar i de flesta fall. Du kan dock behöva en smalare streckkod för att passa en etikett eller en bredare för att förbättra skanningspålitligheten. Egenskapen:

```csharp
generator.Parameters.Barcode.Pdf417.Columns = <desiredColumnCount>;
```

accepterar värden från **1** upp till **30** (den exakta gränsen beror på datalängden). Här är ett snabbt fuskblad:

| Kolumner | Ungefärlig bredd (mm) | När det bör användas |
|----------|-----------------------|-----------------------|
| 1‑3      | Mycket smal           | Liten etikett, begränsat utrymme |
| 4‑6      | Standard              | De flesta kvitton, biljetter |
| 7‑10     | Bredare               | Högdensitetsdata, bättre läsbarhet |

### Truncate (Komprimerat läge)

Att sätta `Truncate = true` instruerar kodaren att klippa bort onödiga tomma rader längst ner. Resultatet blir en **compact PDF417 barcode image** som upptar så liten yta som möjligt samtidigt som den innehåller all data. Om du någonsin får felmeddelandet ”barcode too big for label”, växla detta flagga.

## Steg 4: Kör appen och verifiera resultatet

Compile and execute:

```bash
dotnet run
```

Du bör se konsolmeddelandet som bekräftar sparplatsen. Navigera till mappen och öppna `CompactPdf417.png`. Bilden kommer att se ut ungefär så här:

![Genererad PDF417 streckkod bild](./CompactPdf417.png "Genererad PDF417 streckkod bild – kompakt PNG skapad av Aspose.BarCode")

*Bild alt‑text:* **Generated PDF417 barcode image** – en kompakt PNG‑fil skapad av tutorial‑koden.

Om din skanner kan läsa den, grattis—du har framgångsrikt **generate PDF417 barcode** och bemästrat **how to set columns** för en prydlig **PDF417 barcode image**.

## Steg 5: Vanliga fallgropar & hur man åtgärdar dem

| Symptom | Trolig orsak | Snabb åtgärd |
|---------|--------------|--------------|
| Streckkoden blir suddig | `XDimension.Pixels` för låg (t.ex. 1) | Öka till 2‑3 pixlar för en tydligare bild. |
| Skannern kan inte läsa | För många kolumner för den givna datan | Minska `Columns` eller aktivera `Truncate`. |
| Fel filformat | Sparad med `BarCodeImageFormat.Jpeg` av misstag | Använd `BarCodeImageFormat.Png` för förlustfri resultat. |
| Undantag `ArgumentOutOfRangeException` | Kolumnantalet överskrider tillåtet intervall | Håll kolumner mellan 1‑30 och säkerställ att data får plats. |

## Steg 6: Gå vidare – Anpassa färger och lägga till text

Om du vill att streckkoden ska matcha en varumärkespalett kan du justera förgrunds‑ och bakgrundsfärger:

```csharp
generator.Parameters.Barcode.BarcodeColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
```

Eller lägga över mänskligt läsbar text under streckkoden:

```csharp
generator.Parameters.Barcode.CodeText = data; // shows the raw string
generator.Parameters.Barcode.CodeLocation = CodeLocation.Below;
```

Dessa tillägg är valfria, men de visar hur flexibel **generate PDF417 barcode**‑arbetsflödet kan vara.

## Slutsats

Vi har gått igenom ett komplett, end‑to‑end‑exempel som **generate PDF417 barcode** med Aspose.BarCode, förklarat **how to set columns** för att kontrollera streckkodens dimensioner, och sparat resultatet som en skarp **PDF417 barcode image** i PNG‑format. Koden är självständig, fungerar med .NET 6+, och kan slängas in i vilket befintligt projekt som helst med minimal ansträngning.

Vad blir nästa? Prova att koda större nyttolaster (t.ex. JSON‑payloads), experimentera med olika bildformat, eller integrera generatorn i ett webb‑API som levererar streckkoder på begäran. Himlen är gränsen, och du har nu en solid grund att bygga vidare på.

Lycka till med kodandet, och må dina streckkoder alltid skannas på första försöket!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar streckkod – Kompakt PDF417 med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hur man genererar streckkod bild i Java med Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [Generera streckkod Java – Ställ in bildupplösning med Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
---
category: general
date: 2026-09-18
description: Lär dig hur du snabbt skapar PDF417 barcode‑bild i C# och ställer in
  kolumner för en kompakt barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode image
- compact pdf417 barcode
- Aspose.BarCode PDF417
- C# barcode generation
- set barcode columns
lastmod: 2026-09-18
og_description: Lär dig hur du snabbt skapar PDF417 barcode‑bild i C# och ställer
  in kolumner för en kompakt barcode. Aspose.BarCode gör det enkelt.
og_image_alt: Developer guide showing a compact PDF417 barcode PNG generated with
  Aspose.BarCode
og_title: Skapa PDF417 barcode‑bild – steg‑för‑steg C#‑guide
schemas:
- author: Aspose
  dateModified: '2026-09-18'
  description: Learn how to create PDF417 barcode image in C# quickly and set columns
    for a compact barcode.
  headline: Create PDF417 barcode image – complete guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- Aspose.BarCode
title: Hur man skapar PDF417 barcode‑bild i C# – komplett guide
url: /sv/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar PDF417 streckkod bild i C# – komplett guide

Om du behöver **skapa PDF417 streckkod bild** i en .NET‑applikation, har du kommit till rätt ställe. Oavsett om du skriver ut boarding‑pass‑etiketter, kodar lagerdata eller bygger ett mobilt‑biljettsystem, levererar PDF417 högkapacitets‑ två‑dimensionella streckkoder. Denna guide visar hur du genererar bilden med Aspose.BarCode och hur du anger kolumner så att streckkoden blir så kompakt som möjligt.

## Snabba svar
- **Vilket bibliotek skapar PDF417 streckkoder?** Aspose.BarCode for .NET.
- **Hur många kodrader krävs?** Ungefär 10 rader i en konsolapp.
- **Kan jag kontrollera streckkodens bredd?** Ja, genom att sätta egenskapen `Columns`.
- **Vilket bildformat rekommenderas?** PNG för förlustfri kvalitet.
- **Stöds .NET 6?** Ja – biblioteket fungerar med .NET 6, .NET 7 och senare.

## Vad är PDF417 streckkod bild?
PDF417 streckkod bilden är en två‑dimensionell matris som lagrar upp till 1 700 tecken per rad, med rader och kolumner för att packa data tätt. Aspose.BarCode renderar denna matris till standardbildformat som PNG, JPEG eller BMP. Den kan sparas i olika format och är lämplig för utskrift på etiketter, biljetter eller mobila skärmar.

## Varför ange kolumner för en kompakt PDF417 streckkod bild?
Att ange kolumner låter dig minska streckkodens bredd, vilket är viktigt för smala etiketter eller UI‑element med begränsat utrymme. Aspose.BarCode stöder 1‑30 kolumner, och ett lägre antal minskar den totala bildbredden med upp till 40 % samtidigt som dataintegriteten bevaras. Denna justering hjälper dig att få streckkoder på små taggar utan att offra läsbarhet.

## Hur man skapar PDF417 streckkod bild i C#?
Läs in `Aspose.BarCode`‑biblioteket, konfigurera en `BarcodeGenerator` med `EncodeTypes.Pdf417`, sätt `Columns` och `Truncate`, och spara resultatet som PNG. Hela processen tar två metodanrop och producerar en färdig bildfil. Du kan också anpassa dimensioner, färger och lägga till mänskligt läsbar text för att passa dina applikationsbehov.

### Förutsättningar
- .NET 6+ SDK (eller nyare)
- Visual Studio 2022 eller någon C#‑redigerare
- NuGet‑paketet `Aspose.BarCode`

### Steg‑för‑steg implementering

## Steg 1: Installera Aspose.BarCode NuGet‑paketet
`Aspose.BarCode` är ett .NET‑bibliotek för att generera och läsa olika streckkodssymboler.

```bash
dotnet add package Aspose.BarCode
```

Den enda raden hämtar alla typer du behöver, inklusive `BarcodeGenerator`, `EncodeTypes` och `BarCodeImageFormat`‑enum.

> **Pro tip:** Om du riktar dig mot .NET Framework istället för .NET 6, använd det klassiska `Install-Package Aspose.BarCode` PowerShell‑kommandot i Package Manager Console.

## Steg 2: Skapa en minimal konsolapplikation
`BarcodeGenerator` skapar streckkods­bilder baserat på angivna inställningar. `EncodeTypes` listar de stödda streckkodssymbolerna. `BarCodeImageFormat` listar bildformaten.

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
- `EncodeTypes.Pdf417` talar om för biblioteket att vi vill ha en PDF417 streckkod, inte QR eller Code128.  
- `XDimension.Pixels` styr upplösningen för varje liten svart eller vit modul.  
- Blocket **hur man anger kolumner** påverkar direkt formen på **PDF417 streckkod bilden**.  
- `Truncate = true` tar bort onödiga tomma rader, vilket ger det “kompakta” utseendet som många skannrar gillar.

## Steg 3: Gå djupare – förstå kolumner och trunkering

### Hur man anger kolumner
PDF417 arrangerar data i en matris av *rader* × *kolumner*. Biblioteket har som standard 5 kolumner, vilket fungerar i de flesta fall. Du kan dock behöva en smalare streckkod för att passa en etikett eller en bredare för att förbättra skannings‑reliabiliteten. Egenskapen:

```csharp
generator.Parameters.Barcode.Pdf417.Columns = <desiredColumnCount>;
```

accepterar värden från **1** upp till **30** (den exakta gränsen beror på datalängden). Här är ett snabbt fuskblad:

| Kolumner | Ungefärlig bredd (mm) | När att använda |
|----------|----------------------|-----------------|
| 1‑3      | Mycket smal          | Liten etikett, begränsat utrymme |
| 4‑6      | Standard             | De flesta kvitton, biljetter |
| 7‑10     | Bredare              | Högdensitetsdata, bättre läsbarhet |

### Truncate (kompakt läge)
Att sätta `Truncate = true` talar om för kodaren att klippa bort onödiga tomma rader längst ner. Resultatet blir en **kompakt PDF417 streckkod bild** som upptar så lite yta som möjligt samtidigt som all data bevaras. Om du får felmeddelandet “barcode too big for label”, växla detta flagga.

## Steg 4: Kör appen och verifiera resultatet
Kompilera och kör:

```bash
dotnet run
```

Du bör se konsolmeddelandet som bekräftar sparplatsen. Navigera till mappen och öppna `CompactPdf417.png`. Bilden kommer att se ut ungefär så här:

![Genererad PDF417 streckkod bild](./CompactPdf417.png "Genererad PDF417 streckkod bild – kompakt PNG skapad av Aspose.BarCode")

[Genererad PDF417 streckkod bild](./CompactPdf417.png "Genererad PDF417 streckkod bild – kompakt PNG skapad av Aspose.BarCode")

*Bild alt‑text:* **Genererad PDF417 streckkod bild** – en kompakt PNG‑fil skapad av tutorial‑koden.

Om din skanner kan läsa den, grattis—du har framgångsrikt **genererat PDF417 streckkod** och bemästrat **hur man anger kolumner** för en prydlig **PDF417 streckkod bild**.

## Steg 5: Vanliga fallgropar & hur man åtgärdar dem

| Symptom | Trolig orsak | Snabb lösning |
|---------|--------------|---------------|
| Streckkoden är suddig | `XDimension.Pixels` för låg (t.ex. 1) | Öka till 2‑3 pixlar för en tydligare bild. |
| Skannern kan inte läsa | För många kolumner för den givna datan | Minska `Columns` eller aktivera `Truncate`. |
| Fel filformat | Sparad med `BarCodeImageFormat.Jpeg` av misstag | Använd `BarCodeImageFormat.Png` för förlustfria resultat. |
| Undantag `ArgumentOutOfRangeException` | Kolumnantalet överskrider tillåtet intervall | Håll kolumner mellan 1‑30 och säkerställ att data får plats. |

## Steg 6: Gå vidare – anpassa färger och lägga till text

Om du vill att streckkoden ska matcha en varumärkespalett kan du justera förgrunds‑ och bakgrundsfärger:

```csharp
generator.Parameters.Barcode.BarcodeColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
```

Eller överlagra mänskligt läsbar text under streckkoden:

```csharp
generator.Parameters.Barcode.CodeText = data; // shows the raw string
generator.Parameters.Barcode.CodeLocation = CodeLocation.Below;
```

Dessa tillägg är valfria, men de visar hur flexibel **generera PDF417 streckkod**‑arbetsflödet kan vara.

## Slutsats
Vi har gått igenom ett komplett, end‑to‑end‑exempel som **genererar PDF417 streckkod** med Aspose.BarCode, förklarat **hur man anger kolumner** för att kontrollera streckkodens dimensioner, och sparat resultatet som en skarp **PDF417 streckkod bild** i PNG‑format. Koden är självständig, fungerar med .NET 6+, och kan läggas in i vilket befintligt projekt som helst med minimal ansträngning.

Vad är nästa steg? Prova att koda större nyttolaster (t.ex. JSON‑strängar), experimentera med olika bildformat, eller integrera generatorn i ett webb‑API som levererar streckkoder på begäran. Himlen är gränsen, och du har nu en solid grund att bygga vidare på.

Lycka till med kodningen, och må dina streckkoder alltid skannas på första försöket!

## Vad bör du lära dig härnäst?
Följande handledningar täcker närliggande ämnen som bygger på teknikerna som demonstrerats i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar streckkod – Kompakt PDF417 med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hur man genererar streckkod bild i Java med Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [Generera streckkod Java – Ställ in bildupplösning med Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)

## Vanliga frågor

**Q: Kan jag använda den genererade PNG‑filen på en webbsida utan ytterligare konvertering?**  
A: Ja, PNG stöds nativt av alla moderna webbläsare, så du kan bädda in filen direkt med en `<img>`‑tagg.

**Q: Hur många tecken kan en PDF417 streckkod innehålla?**  
A: Upp till 1 700 tecken per rad och upp till 30 rader, vilket ger ett teoretiskt maximum på cirka 51 000 tecken, även om praktiska begränsningar beror på skannerns kapacitet.

**Q: Kräver Aspose.BarCode en licens för utveckling?**  
A: En gratis utvärderingslicens finns tillgänglig för testning; en kommersiell licens krävs för produktionsdistribution.

**Q: Är det möjligt att generera PDF417 streckkoder i en bakgrundstjänst?**  
A: Absolut. Biblioteket är trådsäkert för skriv‑skyddade operationer, så du kan generera streckkoder i ASP.NET Core eller Windows‑tjänster utan UI‑interaktion.

**Q: Vilka bildformat förutom PNG stöds?**  
A: BMP, JPEG, GIF, TIFF och SVG stöds alla via `BarCodeImageFormat`‑enumerationen.

---

**Senast uppdaterad:** 2026-09-18  
**Testat med:** Aspose.BarCode 24.11 for .NET  
**Författare:** Aspose  

```bash
dotnet add package Aspose.BarCode
```

## Relaterade handledningar

- [Skapa Pdf417 streckkod med Aspose komplett guide](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-complete-guide/)
- [Hur man genererar Pdf417 streckkod bild i C med Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Skapa Pdf417 streckkod i C steg‑för‑steg guide](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-step-by-step-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
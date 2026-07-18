---
category: general
date: 2026-07-18
description: Skapa PDF417‑streckkod snabbt med C#. Lär dig hur du genererar streckkod,
  ställer in parametrar och sparar bildfiler – inkluderar AI 10‑hantering.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate barcode
- how to set parameters
- how to save image
- barcode ai 10
language: sv
lastmod: 2026-07-18
og_description: Skapa PDF417-streckkod i C# med en fullständig genomgång. Upptäck
  hur du genererar streckkod, justerar inställningar och sparar bilder samtidigt som
  du hanterar AI 10.
og_image_alt: Screenshot illustrating create pdf417 barcode code in C#
og_title: Skapa PDF417‑streckkod i C# – Snabbt, flexibelt, komplett kodexempel
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create PDF417 barcode quickly with C#. Learn how to generate barcode,
    set parameters, and save image files – includes AI 10 handling.
  headline: Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: Create PDF417 barcode quickly with C#. Learn how to generate barcode,
    set parameters, and save image files – includes AI 10 handling.
  name: Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  steps:
  - name: '**X‑dimension** – controls the width of the smallest bar (in pixels)'
    text: '**X‑dimension** – controls the width of the smallest bar (in pixels)'
  - name: '**Column count** – influences the overall shape; fewer columns = taller
      barcode'
    text: '**Column count** – influences the overall shape; fewer columns = taller
      barcode'
  - name: '**IsLinked** – enables the optional link module that ties the barcode to
      the data string'
    text: '**IsLinked** – enables the optional link module that ties the barcode to
      the data string'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspnet
- barcode-generation
title: Skapa PDF417-streckkod i C# – Komplett steg‑för‑steg‑guide
url: /sv/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa PDF417-streckkod i C# – Komplett steg‑för‑steg‑guide

Har du någonsin behövt **create pdf417 barcode** men varit osäker på vilket bibliotek eller vilka inställningar du ska välja? Du är inte ensam—många utvecklare stöter på den muren när de först experimenterar med GS1‑Micro‑PDF417. Den goda nyheten är att med några rader C# kan du skapa en perfekt formaterad streckkod, justera dess utseende och spara bilden direkt till disk.

I den här handledningen går vi igenom **how to generate barcode** med Aspose.BarCode‑biblioteket, visar **how to set parameters** som X‑dimension och kolumnantal, och demonstrerar **how to save image**‑filer för både AI 10‑ och AI 21‑varianter. I slutet har du ett återanvändbart kodsnutt som du kan lägga in i vilket .NET‑projekt som helst.

## Förutsättningar

- .NET 6+ eller .NET Framework 4.7.2 (någon nyare runtime fungerar)
- Visual Studio 2022 eller din favoriteditor för C#
- **Aspose.BarCode for .NET** NuGet‑paketet (`Install-Package Aspose.BarCode`)
- En skrivbar mapp på disken där PNG‑filerna kommer att placeras

Det är allt—inga extra verktyg, ingen komplex konfiguration. Är du redo? Nu kör vi.

## Steg 1: Skapa PDF417-streckkod med GS1‑Micro‑format

Det första vi gör är att **create pdf417 barcode**‑objektet och mata in de initiala AI‑data. I GS1‑Micro‑PDF417 är AI 10 (batch/lot‑nummer) ofta startpunkten, så vi kodar den omedelbart.

```csharp
using Aspose.BarCode.Generation;

// Define where the PNGs will be saved
string outputDir = @"C:\Barcodes\";

// Instantiate the generator for GS1‑Micro‑PDF417
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.GS1MicroPdf417,
    "(10)ABCD12345(240)ABCD");   // AI 10 + additional data
```

> **Varför detta är viktigt:** `EncodeTypes.GS1MicroPdf417` talar om för biblioteket att följa GS1‑Micro‑specifikationen, vilket automatiskt lägger till AI‑klamrarna. Om du hoppar över detta får du en generisk PDF417 som kanske inte går att skanna i detaljhandelsmiljöer.

## Steg 2: Hur man ställer in parametrar för streckkoden

Nu när vi har ett streckkod‑objekt måste vi finjustera dess visuella egenskaper. Här kommer **how to set parameters** in i bilden. Vi kommer att justera tre vanliga inställningar:

1. **X‑dimension** – styr bredden på den minsta stapeln (i pixlar)
2. **Column count** – påverkar den övergripande formen; färre kolumner = högre streckkod
3. **IsLinked** – aktiverar den valfria länkmotorn som knyter streckkoden till datasträngen

```csharp
// X‑dimension: 2 pixels per module (good balance of size vs readability)
barcode.Parameters.Barcode.XDimension.Pixels = 2;

// Columns: 3 columns makes the barcode compact yet readable
barcode.Parameters.Barcode.Pdf417.Columns = 3;

// Enable linking (adds a special pattern that some scanners use)
barcode.Parameters.Barcode.Pdf417.IsLinked = true;
```

> **Proffstips:** Om du riktar dig mot mobilsökning, öka X‑dimensionen till 3‑4 pixlar; större moduler klarar lågupplösta kameror bättre.

## Steg 3: Hur man sparar bild – Första versionen (AI 10)

När generatorn är konfigurerad kan vi äntligen **how to save image**. `Save`‑metoden skriver streckkoden till en fil i det format du anger. Här använder vi PNG eftersom det bevarar skarpa kanter utan komprimeringsartefakter.

```csharp
// Save the barcode that encodes AI 10
barcode.Save($"{outputDir}GS1MicroPdf417_AI10.png", BarCodeImageFormat.Png);
```

Vid det här laget bör du se en fil med namnet `GS1MicroPdf417_AI10.png` i din `outputDir`. Öppna den med någon bildvisare—du kommer att se en ren, högkontrast PDF417 klar för utskrift.

## Steg 4: Byt till en annan AI (AI 21) och spara igen

Ofta behöver du koda en annan applikationsidentifierare, såsom AI 21 (serienummer). Att ändra `CodeText`‑egenskapen är allt som krävs. Detta demonstrerar **barcode ai 10** kontra **barcode ai 21**‑hantering i ett svep.

```csharp
// Change the encoded data – now using AI 21
barcode.CodeText = "(21)ABCD12345(240)ABCD";

// Save the new variant
barcode.Save($"{outputDir}GS1MicroPdf417_AI21.png", BarCodeImageFormat.Png);
```

> **Vad händer om du behöver fler AI‑er?** Konkatenera dem helt enkelt i samma sträng, t.ex. `"(10)ABCD(21)12345(240)XYZ"`. Biblioteket tolkar klamrarna automatiskt.

## Fullt fungerande exempel

Sätter vi ihop allt, här är ett fristående program som du kan kopiera och klistra in i en konsolapp:

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Output folder – change to suit your environment
        string outputDir = @"C:\Barcodes\";

        // 2️⃣ Create generator with initial AI 10 data
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.GS1MicroPdf417,
            "(10)ABCD12345(240)ABCD");

        // 3️⃣ Set visual parameters
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // how to set parameters
        barcode.Parameters.Barcode.Pdf417.Columns = 3;
        barcode.Parameters.Barcode.Pdf417.IsLinked = true;

        // 4️⃣ Save first image (AI 10)
        barcode.Save($"{outputDir}GS1MicroPdf417_AI10.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved AI 10 barcode.");

        // 5️⃣ Switch to AI 21 and save second image
        barcode.CodeText = "(21)ABCD12345(240)ABCD";
        barcode.Save($"{outputDir}GS1MicroPdf417_AI21.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved AI 21 barcode.");
    }
}
```

**Förväntad output:** Två PNG‑filer visas i `C:\Barcodes\`—`GS1MicroPdf417_AI10.png` och `GS1MicroPdf417_AI21.png`. Båda innehåller en skannbar PDF417; den första kodar AI 10, den andra AI 21.

## Vanliga fallgropar & hur man undviker dem

- **Saknade mapprättigheter:** Om `Save` kastar ett `UnauthorizedAccessException`, dubbelkolla att sökvägen finns och att din app har skrivrättigheter.
- **Felaktig AI‑formatering:** Att glömma parenteserna (`(10)`) gör att streckkoden behandlas som vanlig data, vilket bryter GS1‑valideringen.
- **För liten X‑dimension:** Staplar tunnare än 1 pixel kan försvinna när bilden skalas. Håll dig till minst 2 pixlar för skärmvisning.

## Nästa steg & relaterade ämnen

Nu när du vet **how to generate barcode**, **how to set parameters** och **how to save image**, kanske du vill utforska:

- Lägga till **human‑readable text** under streckkoden (`barcode.Parameters.Barcode.CodeTextLocation = CodeLocation.BelowBarcode`)
- Exportera till **PDF** istället för PNG (`BarCodeImageFormat.Pdf`)
- Integrera streckkodsgenereringen i en **ASP.NET Core API** för bildskapande i realtid

Varje av dessa ämnen bygger direkt på den grund vi lagt i den här guiden.

---

### Snabb sammanfattning

- **Create pdf417 barcode** med `BarcodeGenerator` och `EncodeTypes.GS1MicroPdf417`
- **How to set parameters** som X‑dimension, kolumner och länkning
- **How to save image** som PNG för både AI 10‑ och AI 21‑varianter
- Hanterade **barcode ai 10** och bytte till **barcode ai 21** med en enda egenskapsändring

Ge det ett försök, justera inställningarna, så har du en robust streckkodsmotor redo för produktion. Har du frågor eller behöver en djupare genomgång? Lämna en kommentar nedan—lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [How to create Aztec barcode with error correction in .NET](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
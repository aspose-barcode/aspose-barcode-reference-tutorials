---
category: general
date: 2026-07-18
description: Skapa GS1‑streckkodsbilder i C# med den här steg‑för‑steg‑guiden om hur
  du genererar streckkod i C# med Aspose.BarCode – inget onödigt, bara fungerande
  kod.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create gs1 barcode images
- how to generate barcode c#
language: sv
lastmod: 2026-07-18
og_description: Skapa GS1‑streckkodsbilder i C# med den här koncisa handledningen.
  Lär dig hur du genererar streckkoder i C# med Aspose.BarCode och sparar PNG‑filer
  på några sekunder.
og_image_alt: Screenshot of a generated GS1‑MicroPDF417 barcode saved as a PNG file
og_title: Skapa GS1‑streckkodsbilder i C# – Komplett steg‑för‑steg‑guide
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create GS1 barcode images in C# with this step‑by‑step guide on how
    to generate barcode C# using Aspose.BarCode – no fluff, just working code.
  headline: Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly
  type: TechArticle
tags:
- barcode
- csharp
- gs1
- aspose
title: Skapa GS1-streckkods bilder i C# – Så genererar du streckkoder i C# snabbt
url: /sv/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa GS1-streckkodsbilder i C# – Så här genererar du streckkod C#

Har du någonsin behövt **create gs1 barcode images** för en förpackningsetikett men varit osäker på var du ska börja? Du är inte ensam. I den här handledningen kommer du att se exakt **how to generate barcode c#** kod som producerar GS1‑MicroPDF417‑bilder på bara några minuter.

Vi går igenom hela processen—installerar biblioteket, konfigurerar generatorn, byter AI (Application Identifier) data, och sparar slutligen en uppsättning PNG‑filer. I slutet har du en färdig‑att‑köra konsolapp som genererar ett antal GS1 barcode images, var och en med en annan AI‑kombination.

---

## Vad du behöver

- **.NET 6+** (eller .NET Framework 4.6+). Den senaste runtime fungerar bäst med Aspose.BarCode.
- **Aspose.BarCode for .NET** – installera via NuGet (`Install-Package Aspose.BarCode`).
- En mapp på disken där PNG‑filerna kommer att skrivas (vi kallar den `YOUR_DIRECTORY`).
- En grundläggande förståelse för C#‑syntax—inget avancerat krävs.

Om du redan har dem, bra. Om inte, hämta NuGet‑paketet först; det är en enda rad i Package Manager Console och tar hand om alla beroenden.

## Steg 1: Skapa ett minimalt konsolprojekt

Öppna din föredragna IDE (Visual Studio, Rider eller VS Code) och skapa ett nytt konsolprojekt:

```bash
dotnet new console -n Gs1BarcodeDemo
cd Gs1BarcodeDemo
dotnet add package Aspose.BarCode
```

Byt ut den automatiskt genererade `Program.cs` mot koden som visas i nästa steg. Detta skelett ger oss en ren grund för att **create gs1 barcode images** utan extra röran.

## Steg 2: How to create gs1 barcode images – Initiera generatorn

Kärnan i operationen är `BarcodeGenerator`. Vi startar den med ett initialt GS1‑MicroPDF417‑värde, till exempel `(17)991231(10)ABCD`. Den strängen kodar två AIs: utgångsdatum (17) och batch/lot (10).

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with a GS1‑MicroPDF417 barcode type
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.GS1MicroPdf417,
            "(17)991231(10)ABCD");
```

**Varför detta är viktigt:** `EncodeTypes.GS1MicroPdf417` talar om för Aspose att vi arbetar med ett kompakt, högdensitets‑GS1‑format. Att börja med en giltig AI‑sträng säkerställer att den första PNG‑filen vi sparar redan följer GS1‑standarderna.

## Steg 3: Justera visuella parametrar – finjustera storlek och layout

En streckkod som är för liten eller konstigt formad kommer inte att kunna läsas. Här sätter vi X‑dimensionen (modulbredd) till 2 pixlar, begränsar antalet kolumner för att hålla bilden smal, och aktiverar länkning så att flera streckkoder kan kedjas ihop senare om så behövs.

```csharp
        // Set visual parameters for a crisp, scannable image
        barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;      // module width
        barcodeGen.Parameters.Barcode.Pdf417.Columns = 2;        // column count
        barcodeGen.Parameters.Barcode.Pdf417.IsLinked = true;   // enable linking
```

**Tips:** Om du behöver en högre streckkod, öka `Rows` istället för kolumner. Lek med `XDimension` för att uppfylla minsta modulstorlek på 0.33 mm som de flesta skannrar kräver.

## Steg 4: Spara den första streckkoden – AI 17 + AI 10

Nu skriver vi faktiskt bilden till disk. Filnamnet speglar de använda AI‑erna, vilket gör det enkelt att hitta senare.

```csharp
        // Save the first image (AI 17 + AI 10)
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_17_10.png",
                        BarCodeImageFormat.Png);
```

Efter att ha kört programmet bör du se en skarp PNG i `YOUR_DIRECTORY`. Öppna den—du kommer att se de små staplarna och den människoläsbara texten under. Det är den första av många **gs1 barcode images** som vi kommer att generera.

## Steg 5: Ändra den kodade datan – återanvänd samma generator

Istället för att skapa en ny `BarcodeGenerator` för varje AI‑par, byter vi helt enkelt `CodeText`‑egenskapen och anropar `Save` igen. Detta tillvägagångssätt är det mest effektiva sättet att **create gs1 barcode images** i bulk.

```csharp
        // AI 15 (best before) + AI 10 (batch)
        barcodeGen.CodeText = "(15)991231(10)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_15_10.png",
                        BarCodeImageFormat.Png);

        // AI 13 (production date) + AI 21 (serial)
        barcodeGen.CodeText = "(13)991231(21)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_13_21.png",
                        BarCodeImageFormat.Png);

        // AI 11 (manufacture date) + AI 21 (serial)
        barcodeGen.CodeText = "(11)991231(21)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_11_21.png",
                        BarCodeImageFormat.Png);

        // Only AI 17 (expiration) – no batch number
        barcodeGen.CodeText = "(17)991231";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_17.png",
                        BarCodeImageFormat.Png);
```

**Varför återanvända?** Att ändra `CodeText` undviker overheaden av att återinstansiera generatorn och garanterar konsekventa visuella inställningar för alla bilder.

## Steg 6: Kör, verifiera och justera

Kompilera och kör:

```bash
dotnet run
```

Du bör nu ha fem PNG‑filer, var och en namngiven efter AI‑paret den innehåller. Öppna någon av dem med en bildvisare; du kommer att se streckkoden och den kodade texten under. För att dubbelkolla att datan är korrekt, använd en gratis GS1‑skannerapp på din telefon—peka den mot PNG‑filen på skärmen och se AI‑värdena dyka upp.

**Vanliga fallgropar & hur du undviker dem**

| Problem | Orsak | Lösning |
|-------|-------|-----|
| Streckkod oläsbar | `XDimension` för låg (t.ex. 1 pixel) | Höj till 2 eller 3 pixlar |
| Saknade AI‑parenteser | Felaktigt `CodeText`‑format | Omslut alltid varje AI i parenteser |
| Bilden för stor | För många kolumner/rader | Minska `Columns` eller låt Aspose auto‑size |
| Runtime‑fel `EncodeTypes` hittades inte | Saknad `using Aspose.BarCode.Generation` | Lägg till den saknade `using`‑direktivet |

## Steg 7: Utöka exemplet – generera fler AI‑kombinationer

Om du behöver **create gs1 barcode images** för dussintals produktvarianter, överväg att läsa in AI‑par från en CSV‑fil:

```csharp
using System.IO;

string[] lines = File.ReadAllLines(@"ai_pairs.csv"); // format: "(17)991231,(10)ABCD"
foreach (var line in lines)
{
    barcodeGen.CodeText = line.Replace(',', ' ');
    string fileName = $"GS1MicroPdf417_{line.Replace("(", "").Replace(")", "").Replace(",", "_")}.png";
    barcodeGen.Save(Path.Combine(@"YOUR_DIRECTORY", fileName), BarCodeImageFormat.Png);
}
```

## Slutsats

Du har nu ett komplett, färdigt‑att‑köra C#‑program som **creates gs1 barcode images** för flera AI‑scenarier, och demonstrerar det enklaste sättet att **how to generate barcode c#** med Aspose.BarCode. Genom att återanvända en enda `BarcodeGenerator`‑instans, justera visuella parametrar och byta `CodeText` kan du producera så många kompatibla GS1‑MicroPDF417‑PNG‑filer som ditt projekt kräver.

Vad blir nästa steg? Prova att lägga till färger (`barcodeGen.Parameters.Barcode.ForeColor`), bädda in streckkoden i en PDF, eller byta till en annan GS1‑symbologi som DataMatrix. Samma mönster gäller—initiera, konfigurera, sätt `CodeText` och spara.

Känn dig fri att lämna en kommentar om du stöter på problem, eller dela dina egna varianter. Lycka till med kodningen, och må dina skanningar alltid vara rena!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar tyst zon för streckkod Code 16K med Aspose.BarCode för .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Hur man skapar tyst zon för ITF-14 med Aspose.BarCode för .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Hur man genererar streckkod – Code 39‑konfiguration med Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
---
category: general
date: 2026-10-02
description: Skapa streckkod från text i C# med Aspose.BarCode. Lär dig hur du genererar
  PDF417‑streckkod och se hur du genererar PDF417‑streckkod i kompakt läge.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate pdf417 barcode
- how to generate pdf417 barcode
language: sv
lastmod: 2026-10-02
og_description: Skapa streckkod från text i C# med Aspose.BarCode. Denna guide visar
  hur du genererar PDF417‑streckkod och hur du genererar PDF417‑streckkod i kompakt
  läge.
og_image_alt: Screenshot showing create barcode from text output as a PNG image
og_title: Skapa streckkod från text i C# – steg‑för‑steg guide
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  headline: How to create barcode from text in C# with Aspose.BarCode
  type: TechArticle
- description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  name: How to create barcode from text in C# with Aspose.BarCode
  steps:
  - name: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
    text: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
  - name: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
    text: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
  - name: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
    text: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Hur man skapar streckkod från text i C# med Aspose.BarCode
url: /sv/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar streckkod från text i C# med Aspose.BarCode

Om du behöver **skapa streckkod från text** i en .NET‑applikation, guidar den här guiden dig genom hela processen. Du får se ett färdigt exempel som **genererar PDF417‑streckkod** och som också svarar på **hur man genererar PDF417‑streckkod** i en kompakt layout.

Att generera en streckkod programatiskt tar bort manuella steg och garanterar konsekvens i alla dokument. I slutet av den här handledningen kommer du att ha en PNG‑fil som innehåller en PDF417‑streckkod som du kan bädda in i fakturor, biljetter eller ID‑kort.

## Vad du behöver

- .NET 6.0 SDK eller senare (koden fungerar också med .NET Framework 4.7.2+)
- Visual Studio 2022 eller någon editor som stödjer C#
- En NuGet‑licens för **Aspose.BarCode for .NET** (en gratis provversion fungerar för testning)

> **Proffstips:** Lägg till NuGet‑paketet via CLI för att hålla projektet rent:  
> `dotnet add package Aspose.BarCode`

## Steg 1: Skapa ett konsolprojekt

Skapa en ny konsolapplikation och referera till Aspose.BarCode‑biblioteket.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

`dotnet new console`‑kommandot skapar en `Program.cs`‑fil som vi kommer att ersätta med hela exemplet nedan.

## Steg 2: Hur man skapar streckkod från text – kärnkod

Öppna `Program.cs` och ersätt dess innehåll med följande kod. Varje rad är kommenterad för att förklara varför den finns.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Image;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Define the text that will be encoded.
            // The PDF417 symbology supports a wide range of Unicode characters.
            string textToEncode = "Åspóse.Barcóde©";

            // 2️⃣ Create a BarcodeGenerator for PDF417 using the desired text.
            // This object holds all settings and performs the rendering.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, textToEncode);

            // 3️⃣ Adjust module (X) dimension for better readability on screen.
            // XDimension defines the width of a single barcode column in pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Set the number of columns – a smaller column count yields a denser image.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 5️⃣ Enable compact mode by truncating the data.
            // Truncate = true removes padding, making the barcode smaller while preserving scannability.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 6️⃣ Choose the output path. Adjust the folder to match your environment.
            string outputPath = "CompactPdf417.png";

            // 7️⃣ Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Varför varje inställning är viktig

| Inställning | Syfte |
|--------|----------|
| `EncodeTypes.Pdf417` | Väljer PDF417‑symbologi, som kan lagra stora mängder data i en tvådimensionell matris. |
| `XDimension.Pixels = 2` | Styr bredden på varje modul; ett värde på 2 pixlar balanserar läsbarhet och filstorlek. |
| `Pdf417.Columns = 3` | Minskar antalet kolumner, vilket gör streckkoden mer kompakt utan att förlora data. |
| `Pdf417.Truncate = true` | Aktiverar kompakt läge, tar bort onödig utfyllnad och förkortar streckkoden. |
| `BarCodeImageFormat.Png` | PNG bevarar förlustfri kvalitet, idealisk för vidare bearbetning eller utskrift. |

## Steg 3: Generera PDF417‑streckkod – kör exemplet

Bygg och kör projektet:

```bash
dotnet run
```

När exekveringen är klar kommer du att se:

```
Barcode saved to CompactPdf417.png
```

Öppna `CompactPdf417.png` för att se resultatet. Bilden innehåller en PDF417‑streckkod som kodar strängen **Åspóse.Barcóde©**.

![Exempel på att skapa streckkod från text](barcode-example.png)

*Alt text: skapa streckkod från text – PDF417‑streckkod sparad som PNG*

## Steg 4: Hur man genererar PDF417‑streckkod med anpassad felkorrigering (valfritt)

Om din skanningsmiljö är bullrig kan du öka felkorrigeringsnivån:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // Levels 0–5, higher = more redundancy
```

Att öka felnivån gör streckkoden större men förbättrar motståndskraften mot skador.

## Steg 5: Vanliga fallgropar och hantering av kantfall

1. **Ogiltiga tecken** – PDF417 stödjer Unicode, men vissa äldre skannrar kan avvisa icke‑ASCII‑symboler. Testa med din mål‑hardware.
2. **Behörigheter för filsökväg** – Se till att katalogen du skriver till är skrivbar; annars kastar `Save` ett `UnauthorizedAccessException`.
3. **Bildstorlek** – Mycket höga `XDimension`‑värden ger stora PNG‑filer. Håll pixelförstoringen mellan 1 och 4 för de flesta skärm‑visningsscenarier.

## Sammanfattning

Du vet nu hur du **skapar streckkod från text** i C# med Aspose.BarCode, hur du **genererar PDF417‑streckkod** med en kompakt layout, och de exakta stegen för **hur man genererar PDF417‑streckkod** med anpassade inställningar. Den kompletta, körbara koden ovan kan kopieras till vilket .NET‑projekt som helst och anpassas till olika textinmatningar eller utdataformat (t.ex. JPEG, BMP).

## Nästa steg

- Utforska andra symbologier såsom QR Code eller Code128 genom att ändra `EncodeTypes`.
- Integrera den genererade PNG‑filen i en PDF med Aspose.PDF för end‑to‑end‑dokumentskapande.
- Experimentera med `generator.Parameters.Barcode.Pdf417.Rows` för att styra vertikal densitet.

Känn dig fri att modifiera exemplet, bädda in streckkoden i dina egna applikationer och dela dina resultat med communityn. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar PDF417‑streckkod i C# – kompakt exempel](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-compact-example/)
- [Hur man skapar PDF417‑streckkod i C# med kompakt läge](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [Hur man genererar PDF417‑streckkod i C# – steg‑för‑steg‑guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
---
category: general
date: 2026-11-27
description: Generera streckkod PNG i C# snabbt med Aspose.BarCode. Lär dig hur du
  skapar streckkodsbilder i C#‑kod, ställer in dimensioner, väljer kolumner och sparar
  som PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode png
- create barcode image c#
- generate barcode with aspose
language: sv
lastmod: 2026-11-27
og_description: Generera streckkod PNG i C# med Aspose.BarCode. Följ den här guiden
  för att skapa en streckkodsbild i C#, anpassa storleken och spara som en PNG‑fil.
og_image_alt: Screenshot of a generated MicroPdf417 barcode PNG
og_title: Generera streckkod PNG i C# med Aspose – komplett handledning
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Generate barcode PNG in C# quickly using Aspose.BarCode. Learn how
    to create barcode image C# code, set dimensions, choose columns, and save as PNG.
  headline: Generate barcode PNG in C# with Aspose – step‑by‑step guide
  type: TechArticle
- description: Generate barcode PNG in C# quickly using Aspose.BarCode. Learn how
    to create barcode image C# code, set dimensions, choose columns, and save as PNG.
  name: Generate barcode PNG in C# with Aspose – step‑by‑step guide
  steps:
  - name: Why each step matters
    text: '* **Step 1** – Instantiating `BarcodeGenerator` ties the text you want
      to encode to a specific barcode type. If you need a different symbology (e.g.,
      QR, Code128), you only change `EncodeTypes`. * **Step 2** – The X‑dimension
      controls the smallest bar width. Adjusting this value influences both read'
  - name: Expected output
    text: 'Below is a textual representation of the generated PNG (the actual image
      will be visual, not text):'
  - name: Generating other barcode formats
    text: To **generate barcode with Aspose** for a different symbology, replace `EncodeTypes.MicroPdf417`
      with another enum value, such as `EncodeTypes.QR` or `EncodeTypes.Code128`.
      The rest of the code remains identical.
  - name: Changing image format
    text: 'Aspose supports several raster formats (`Png`, `Jpeg`, `Bmp`, `Gif`). To
      save as JPEG, modify the `Save` call:'
  - name: Handling large text payloads
    text: MicroPdf417 has a limited data capacity. If your text exceeds this limit,
      Aspose throws an `ArgumentException`. In such cases, switch to the full `Pdf417`
      symbology, which supports longer strings.
  - name: Running in a web application
    text: 'When generating a barcode image on the fly in ASP.NET Core, you can write
      the PNG directly to the response stream:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Generera streckkod PNG i C# med Aspose – steg‑för‑steg‑guide
url: /sv/net/one-dimensional-barcode-types/generate-barcode-png-in-c-with-aspose-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generera streckkod PNG i C# med Aspose – steg‑för‑steg guide

Om du behöver **generera streckkod PNG** i en .NET‑applikation visar den här guiden hur du gör det med Aspose.BarCode. Du kommer att lära dig att **skapa streckkodsbild C#** kod, justera dimensioner, ange kolumner och spara resultatet som en PNG‑fil.

Streckkodsgenerering är ett vanligt krav för lagerhanteringssystem, biljettplattformar och mobilappar. Genom att använda Aspose elimineras behovet av externa tjänster eller komplexa bildmanipuleringsbibliotek. I slutet av den här handledningen har du ett självständigt, körbart program som producerar en MicroPdf417‑streckkod PNG på disk.

## Förutsättningar

* **.NET 6.0** eller senare installerat (koden fungerar även med .NET Framework 4.7+).  
* En giltig **Aspose.BarCode for .NET**‑licens eller en tillfällig utvärderingsnyckel.  
* En IDE såsom **Visual Studio 2022** eller **VS Code** med C#‑tillägget.  

Inga ytterligare NuGet‑paket krävs förutom `Aspose.BarCode`.

## Steg 1: Installera Aspose.BarCode NuGet‑paketet

Öppna en terminal i din projektmapp och kör:

```bash
dotnet add package Aspose.BarCode
```

Detta kommando lägger till det senaste Aspose.BarCode‑biblioteket i ditt projekt och ger dig åtkomst till `BarcodeGenerator`‑klassen som används genom hela handledningen.

## Steg 2: Ställ in en grundläggande konsolapplikation

Skapa ett nytt konsolprojekt om du inte redan har ett:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Byt ut innehållet i `Program.cs` mot skelettet nedan. Skelettet innehåller de nödvändiga `using`‑direktiven och en `Main`‑metod där vi placerar streckkodsgenereringslogiken.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // The barcode generation code will be inserted here.
        }
    }
}
```

## Steg 3: Generera streckkod PNG med Aspose.BarCode

Nedan är den kompletta koden som **genererar streckkod PNG** med MicroPdf417‑symbologi. Varje rad är kommenterad för att förklara varför den är viktig, vilket hjälper dig att anpassa exemplet till andra streckkodstyper.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Create a barcode generator for MicroPdf417 with the desired text.
            //    EncodeTypes.MicroPdf417 tells Aspose which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417, "Sample text");

            // 2️⃣ Set the X‑dimension (module width) in pixels.
            //    A smaller value yields a more compact barcode; 2 pixels works well for most screens.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Define the number of columns for the MicroPdf417 barcode.
            //    Valid values are 1‑4. More columns reduce the height but increase width.
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // 4️⃣ Choose the output path. Ensure the directory exists or Aspose will throw an exception.
            string outputPath = "MicroPdf417.png";

            // 5️⃣ Save the generated barcode as a PNG image.
            //    BarCodeImageFormat.Png is the most widely supported raster format.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode PNG generated at: {outputPath}");
        }
    }
}
```

### Varför varje steg är viktigt

* **Step 1** – Att instansiera `BarcodeGenerator` knyter den text du vill koda till en specifik streckkodstyp. Om du behöver en annan symbologi (t.ex. QR, Code128) ändrar du bara `EncodeTypes`.
* **Step 2** – X‑dimensionen styr den minsta stapelbredden. Att justera detta värde påverkar både läsbarheten och den fysiska storleken på den utskrivna streckkoden.
* **Step 3** – MicroPdf417 låter dig balansera höjd mot bredd genom att ange kolumner. För mobila skärmar ser en bredare men kortare streckkod ofta bättre ut.
* **Step 5** – Att spara som PNG bevarar förlustfri bildkvalitet, vilket är avgörande för skanningsnoggrannhet.

## Steg 4: Kör programmet och verifiera resultatet

Bygg och kör projektet:

```bash
dotnet run
```

Du bör se konsolmeddelandet:

```
Barcode PNG generated at: MicroPdf417.png
```

Navigera till projektmappen och öppna `MicroPdf417.png`. Bilden innehåller en tydlig MicroPdf417‑streckkod som kodar texten *Sample text*. De flesta streckkodsläsare och mobilappar kan läsa denna fil utan ytterligare konfiguration.

### Förväntat resultat

Nedan är en textuell representation av den genererade PNG‑filen (den faktiska bilden blir visuell, inte text):

```
┌─────────────────────────────────────┐
│ █ █ █ █   █ █ █ █   █ █ █ █ █ █ █   │
│ █   █ █ █ █   █ █ █ █ █   █ █ █ █   │
│ ... (barcode pattern)               │
└─────────────────────────────────────┘
```

Om du öppnar PNG‑filen i en bildvisare ser du en skarp streckkod med fyra kolumner och en modulbredd på två pixlar.

## Steg 5: Vanliga variationer och kantfall

### Generera andra streckkodformat

För att **generate barcode with Aspose** för en annan symbologi, ersätt `EncodeTypes.MicroPdf417` med ett annat enum‑värde, såsom `EncodeTypes.QR` eller `EncodeTypes.Code128`. Resten av koden förblir identisk.

```csharp
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

### Ändra bildformat

Aspose stöder flera rasterformat (`Png`, `Jpeg`, `Bmp`, `Gif`). För att spara som JPEG, ändra `Save`‑anropet:

```csharp
generator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
```

### Hantera stora textpayloads

MicroPdf417 har en begränsad datakapacitet. Om din text överskrider denna gräns kastar Aspose ett `ArgumentException`. I sådana fall, byt till den fullständiga `Pdf417`‑symbologin, som stödjer längre strängar.

```csharp
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, longText);
```

### Köra i en webbapplikation

När du genererar en streckkodsbild i farten i ASP.NET Core kan du skriva PNG‑filen direkt till svarströmmen:

```csharp
byte[] pngBytes = generator.GenerateBarCodeImage(BarCodeImageFormat.Png);
return File(pngBytes, "image/png");
```

## Pro‑tips för produktionsanvändning

* **License early** – Att använda utvärderingsversionen lägger ett vattenmärke på bilden. Applicera din licens före det första `Save`‑anropet för att undvika detta.
* **Validate input** – Säkerställ att texten du skickar in följer den valda symbologins teckenuppsättning; annars kommer Aspose att kasta ett undantag.
* **Cache generated images** – Om samma streckkod begärs upprepade gånger, lagra PNG‑filen på disk eller i minnet för att minska CPU‑belastning.
* **Thread safety** – `BarcodeGenerator`‑instanser är inte trådsäkra. Skapa en ny generator per begäran eller synkronisera åtkomsten.

## Slutsats

Du vet nu hur du **generate barcode PNG** i C# med Aspose.BarCode, från att installera paketet till att anpassa dimensioner och spara bilden. Det kompletta exemplet demonstrerar standardarbetsflödet för **creating barcode image C#**‑program och kan utökas till andra streckkodstyper, bildformat och distributionsscenarier.  

Utforska sedan relaterade ämnen såsom **generating barcode with Aspose** för PDF‑dokument, lägga till felkorrigeringsnivåer för QR‑koder eller integrera streckkodsskanning med Aspose.OCR. Experimentera med olika `EncodeTypes` och parameterinställningar för att hitta den optimala konfigurationen för din applikation.

Lycka till med kodningen!

## Vad bör du lära dig härnäst?

De följande handledningarna täcker nära besläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [How to generate barcode set custom size and save image in C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [Barcode image PNG in C# generate barcodes, change height](/barcode/english/python-java/general/barcode-image-png-in-c-generate-barcodes-change-height/)
- [How to create barcode PNG in C# using Aspose.Barcode](/barcode/english/python-java/general/how-to-create-barcode-png-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
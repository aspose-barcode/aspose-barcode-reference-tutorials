---
category: general
date: 2026-08-22
description: Lär dig hur du skapar en micro PDF417‑streckkod i C# och genererar en
  streckkod som PNG‑bild. Inkluderar att ställa in streckkodens dimensioner och spara
  filen.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- how to generate barcode png
- create barcode image c#
- how to set barcode dimensions
language: sv
lastmod: 2026-08-22
og_description: Skapa mikro‑PDF417‑streckkod i C# och exportera den som PNG. Följ
  den här guiden för att ställa in streckkodens dimensioner och snabbt generera en
  streckkodsbild.
og_image_alt: Screenshot of a micro PDF417 barcode generated with C# code
og_title: Skapa mikro‑PDF417‑streckkod i C# – fullständig kodningshandledning
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  headline: How to create micro PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  name: How to create micro PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Build the project: `dotnet build`.'
    text: 'Build the project: `dotnet build`.'
  - name: 'Execute: `dotnet run`.'
    text: 'Execute: `dotnet run`.'
  - name: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
    text: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
  type: HowTo
tags:
- barcode
- C#
- MicroPdf417
- image generation
title: Hur du skapar en mikro‑PDF417‑streckkod i C# – steg‑för‑steg‑guide
url: /sv/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar micro PDF417 streckkod i C# – steg‑för‑steg guide

Om du behöver **skapa micro PDF417 streckkod** för ett biljettsystem, lageretikett eller mobilskanning, visar den här handledningen exakt hur. Du får se det kompletta C#‑programmet som genererar en streckkod‑PNG, lära dig hur du ställer in streckkodsdimensioner och förstå varje konfigurationsalternativ.

När du är klar med den här guiden kan du generera en högupplöst streckkodsbild, anpassa X‑dimensionen, välja kolumnantal och spara resultatet som en PNG‑fil – allt med några få kodrader.

## Vad du behöver

- .NET 6.0 SDK eller senare (koden fungerar med .NET Core och .NET Framework)
- Visual Studio 2022 eller någon annan C#‑kompatibel IDE
- **Aspose.BarCode for .NET** NuGet‑paketet (eller något bibliotek som stödjer `EncodeTypes.MicroPdf417`)
- Grundläggande kunskap om C#‑syntax

> **Proffstips:** Den fria community‑editionen av Aspose.BarCode räcker för utveckling och testning. För produktion, skaffa en licens för att ta bort evalueringsvattenstämplar.

## Steg 1: Installera streckkodsbiblioteket

Öppna en terminal i din projektmapp och kör:

```bash
dotnet add package Aspose.BarCode
```

Det här lägger till `Aspose.BarCode`‑assemblyn, som tillhandahåller `BarcodeGenerator`‑klassen som används för att **skapa streckkodsbild C#**‑applikationer.

## Steg 2: Initiera generatorn – skapa micro PDF417 streckkod

Den första handlingsbara raden skapar en `BarcodeGenerator`‑instans konfigurerad för Micro PDF417‑symbologi och levererar den data du vill koda.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize a Micro PDF417 barcode generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");
```

*Varför detta är viktigt*: `EncodeTypes.MicroPdf417`‑enumet talar om för biblioteket att använda den kompakta versionen av PDF417, vilket är idealiskt för små etiketter och mobila skärmar.

## Steg 3: Hur man ställer in streckkodsdimensioner i C#

Finjustering av modulbredden (X‑dimension) styr den visuella densiteten i streckkoden. Ett mindre värde ger en skarpare bild, medan ett större värde gör streckkoden lättare att skanna på avstånd.

```csharp
        // Step 3: Set the X‑dimension (module width) to 2 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Varför du bör ställa in dimensioner**: Utan att justera X‑dimensionen kan standardvärdet ge en streckkod som ser suddig ut när den renderas med hög DPI. Att sätta den till 2 pixlar är en bra balans för de flesta skärmbaserade skanningar.

## Steg 4: Välj antal kolumner – kontroll av streckkodens bredd

Micro PDF417 tillåter mellan 1 och 4 kolumner. Fler kolumner komprimerar data horisontellt och minskar den totala bildbredden.

```csharp
        // Step 4: Define the number of columns (allowed values: 1‑4)
        generator.Parameters.Barcode.Pdf417.Columns = 4;
```

*Särskilt fall*: Om du begär 5 kolumner kastar biblioteket ett `ArgumentOutOfRangeException`. Håll dig alltid inom det dokumenterade intervallet.

## Steg 5: Hur man genererar barcode PNG – sparar bilden

Nu kan du exportera den genererade streckkoden till en PNG‑fil. PNG bevarar förlustfri kvalitet, vilket är avgörande för pålitlig skanning.

```csharp
        // Step 5: Save the generated barcode as a PNG image
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "MicroPdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

När du kör programmet ser du ett konsolmeddelande som bekräftar filens plats. Den resulterande `MicroPdf417.png` ser ut så här:

![Screenshot showing a generated micro PDF417 barcode created with C#](micro-pdf417-example.png "Generated micro PDF417 barcode")

*Bild‑alt‑text*: **micro PDF417 streckkod genererad i C#** – visar det slutgiltiga resultatet efter att dimensioner och kolumninställningar har tillämpats.

## Steg 6: Kör och verifiera resultatet

1. Bygg projektet: `dotnet build`.
2. Kör: `dotnet run`.
3. Öppna `MicroPdf417.png` på ditt skrivbord och skanna den med en mobil streckkodsläsare.

Du bör se texten **“Sample text”** avkodas. Om skannern rapporterar ett fel, dubbelkolla X‑dimensionen och kolumnantalet – extrema värden kan göra streckkoden för tät för vissa enheter.

## Vanliga variationer och felsökning

| Situation | Justering |
|-----------|------------|
| **Behöver en större streckkod för lågupplösta skrivare** | Öka `XDimension.Pixels` till 3 eller 4. |
| **Vill ha en högre streckkod utan att ändra bredden** | Ställ in `generator.Parameters.Barcode.Pdf417.Rows` (radintervall 3‑90). |
| **Generera flera streckkoder i en loop** | Återanvänd samma `BarcodeGenerator`‑instans och ändra bara `CodeText` innan varje `Save`. |
| **Spara som JPEG istället för PNG** | Byt ut `BarCodeImageFormat.Png` mot `BarCodeImageFormat.Jpeg`. |
| **Kör på .NET Framework 4.7** | Samma kod fungerar; referera bara till rätt `Aspose.BarCode.dll`. |

## Fullständig källkod (körbar)

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialize a Micro PDF417 barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");

            // Set the X‑dimension (module width) to 2 pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns (allowed values: 1‑4)
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

**Förväntat resultat** – en 200 × 100‑pixel PNG‑fil som innehåller en skarp Micro PDF417 streckkod som avkodas till “Sample text”.

## Slutsats

Du vet nu hur du **skapar micro PDF417 streckkod** i C#, **ställer in streckkodsdimensioner** och **genererar en streckkod PNG**‑bild. Det kompletta exemplet demonstrerar varje nödvändigt steg – från bibliotekinstallation till sparande av den slutgiltiga filen – så att du kan integrera streckkodsgenerering direkt i dina egna applikationer.

Nästa steg är att utforska relaterade ämnen som **att skapa QR‑koder med Aspose.BarCode**, **anpassa färger**, eller **bädda in streckkoder i PDF‑dokument**. Alla dessa bygger på samma `BarcodeGenerator`‑grundprinciper som behandlats här.

Känn dig fri att experimentera med olika datasträngar, kolumnantal och X‑dimension‑värden för att passa just din skanningsmiljö. Lycka till med kodningen!


## Vad bör du lära dig härnäst?


Följande handledningar täcker nära besläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate PDF417 Barcode – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to create Aztec barcode with Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
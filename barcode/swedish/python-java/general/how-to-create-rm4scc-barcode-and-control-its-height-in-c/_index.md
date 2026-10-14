---
category: general
date: 2026-10-02
description: Lär dig hur du skapar rm4scc‑streckkod i C# och hur du genererar poststreckkod
  med anpassad höjd. Inkluderar steg‑för‑steg‑kod för Planet‑streckkoder.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create rm4scc barcode
- how to generate postal barcode
- generate planet barcode
- how to set barcode height
language: sv
lastmod: 2026-10-02
og_description: Skapa rm4scc‑streckkod i C# och lär dig hur du genererar poststreckkod
  med exakta dimensioner. Fullständigt kodexempel och bästa praxis‑tips.
og_image_alt: Screenshot of RM4SCC and Planet barcodes generated with Aspose.BarCode
  in C#
og_title: Skapa rm4scc-streckkod med anpassad höjd – C#‑guide
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to create rm4scc barcode in C# and how to generate postal
    barcode with custom height. Includes step‑by‑step code for Planet barcodes.
  headline: How to create rm4scc barcode and control its height in C#
  type: TechArticle
- description: Learn how to create rm4scc barcode in C# and how to generate postal
    barcode with custom height. Includes step‑by‑step code for Planet barcodes.
  name: How to create rm4scc barcode and control its height in C#
  steps:
  - name: 2.1 Create an RM4SCC barcode (auto height)
    text: '```csharp // RM4SCC with automatic height BarcodeGenerator rm4sccAuto =
      new BarcodeGenerator(EncodeTypes.RM4SCC, "123456"); rm4sccAuto.Parameters.Barcode.XDimension.Pixels
      = 4; // controls bar width rm4sccAuto.Save($"{outputFolder}PostalRM4SCC_AutoHeight.png",
      BarCodeImageFormat.Png); ```'
  - name: 2.2 Create a Planet barcode (auto height)
    text: '```csharp // Planet barcode with automatic height BarcodeGenerator planetAuto
      = new BarcodeGenerator(EncodeTypes.Planet, "123456"); planetAuto.Parameters.Barcode.XDimension.Pixels
      = 4; planetAuto.Save($"{outputFolder}PostalPlanet_AutoHeight.png", BarCodeImageFormat.Png);
      ```'
  - name: 3.1 Fixed-height RM4SCC barcode
    text: '```csharp // RM4SCC with fixed height of 100 px BarcodeGenerator rm4sccFixed
      = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456"); rm4sccFixed.Parameters.Barcode.XDimension.Pixels
      = 4; rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100; // explicit height
      rm4sccFixed.Save($"{outputFolder}PostalRM'
  - name: 3.2 Fixed-height Planet barcode
    text: '```csharp // Planet barcode with fixed height of 100 px BarcodeGenerator
      planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456"); planetFixed.Parameters.Barcode.XDimension.Pixels
      = 4; planetFixed.Parameters.Barcode.BarHeight.Pixels = 100; planetFixed.Save($"{outputFolder}PostalPlanet_FixedH'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
- postal codes
title: Hur du skapar rm4scc-streckkod och styr dess höjd i C#
url: /sv/python-java/general/how-to-create-rm4scc-barcode-and-control-its-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar rm4scc‑streckkod och styr dess höjd i C#

Om du behöver **skapa rm4scc‑streckkod** för ett postningssystem visar den här guiden exakt hur du genererar poststreckkoder och anger en exakt stapelhöjd. Du får se både standardmetoden (automatisk storlek) och tekniken med explicit höjd, så att du kan välja den metod som passar dina designkrav.

Att generera en poststreckkod är en vanlig uppgift när man bygger fraktetiketter, massutskick‑programvara eller någon lösning som integreras med nationella posttjänster. Denna handledning täcker:

* **hur man genererar poststreckkod** för RM4SCC‑ och Planet‑symbolerna  
* **generera planet‑streckkod** med samma inställningar för jämförelse  
* **hur man ställer in streckkodshöjd** till ett fast pixelvärde  
* komplett, körbar C#‑kod med Aspose.BarCode‑biblioteket  

När du är klar har du ett färdigt konsolprogram som producerar fyra PNG‑filer – två med automatisk höjd och två med en fast höjd på 100 px.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 SDK eller senare (koden fungerar även med .NET Framework 4.7+).  
* Visual Studio 2022 eller någon IDE som kan bygga C#‑projekt.  
* **Aspose.BarCode for .NET** NuGet‑paketet (`Install-Package Aspose.BarCode`).  

Ingen ytterligare konfiguration krävs; biblioteket hanterar all bildrendering internt.

## Steg 1: Skapa projektet och importera namnrymder

Skapa ett nytt konsolprojekt och lägg till de nödvändiga `using`‑direktiven. Detta steg förbereder miljön för streckkodsgenerering.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generator
using Aspose.BarCode;               // For ImageFormat enum

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Define where the PNG files will be saved
            string outputFolder = "C:/Barcodes/";   // <-- adjust to a writable folder
            // Ensure the folder exists
            System.IO.Directory.CreateDirectory(outputFolder);
```

*Varför detta är viktigt*: Att deklarera `outputFolder` en gång undviker upprepning och gör det enkelt att ändra destinationssökvägen senare. Anropet `CreateDirectory` garanterar att sparoperationen inte misslyckas på grund av att mappen saknas.

## Steg 2: Hur man genererar poststreckkod med standardhöjd

### 2.1 Skapa en RM4SCC‑streckkod (automatisk höjd)

```csharp
            // RM4SCC with automatic height
            BarcodeGenerator rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4; // controls bar width
            rm4sccAuto.Save($"{outputFolder}PostalRM4SCC_AutoHeight.png", BarCodeImageFormat.Png);
```

### 2.2 Skapa en Planet‑streckkod (automatisk höjd)

```csharp
            // Planet barcode with automatic height
            BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
            planetAuto.Save($"{outputFolder}PostalPlanet_AutoHeight.png", BarCodeImageFormat.Png);
```

Båda anropen utelämnar egenskapen `BarHeight`, så biblioteket beräknar den optimala höjden baserat på symbolens specifikationer. Detta är det enklaste sättet **hur man genererar poststreckkod** när du inte har strikta layoutbegränsningar.

## Steg 3: Hur man ställer in streckkodshöjd för exakt layout

När en etikettmall kräver en fast visuell storlek måste du explicit ange stapelhöjden. Följande kod demonstrerar **hur man ställer in streckkodshöjd** till 100 pixlar för båda symbolerna.

### 3.1 Fast‑höjd RM4SCC‑streckkod

```csharp
            // RM4SCC with fixed height of 100 px
            BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100; // explicit height
            rm4sccFixed.Save($"{outputFolder}PostalRM4SCC_FixedHeight.png", BarCodeImageFormat.Png);
```

### 3.2 Fast‑höjd Planet‑streckkod

```csharp
            // Planet barcode with fixed height of 100 px
            BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
            planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            planetFixed.Save($"{outputFolder}PostalPlanet_FixedHeight.png", BarCodeImageFormat.Png);
```

*Varför detta fungerar*: Egenskapen `BarHeight.Pixels` åsidosätter den automatiska beräkningen och tvingar renderaren att använda exakt det antal pixlar du anger. Detta är avgörande när streckkoden måste anpassas till andra UI‑element eller utskriftsmallar.

## Steg 4: Verifiera de genererade bilderna

När programmet är klart, öppna de fyra PNG‑filerna i `outputFolder`. Du bör se:

| Filnamn | Höjd | Symbol |
|-----------|--------|-----------|
| `PostalRM4SCC_AutoHeight.png` | Automatisk beräknad (≈ 50 px) | RM4SCC |
| `PostalPlanet_AutoHeight.png` | Automatisk beräknad (≈ 50 px) | Planet |
| `PostalRM4SCC_FixedHeight.png` | **100 px** (exakt) | RM4SCC |
| `PostalPlanet_FixedHeight.png` | **100 px** (exakt) | Planet |

De två “FixedHeight”-bilderna har staplar som är exakt 100 px höga, vilket uppfyller kravet **hur man ställer in streckkodshöjd** för ett standardiserat etikettformat.

## Steg 5: Vanliga fallgropar och bästa praxis‑tips

* **Ogiltiga höjdvärden** – Att sätta `BarHeight.Pixels` till ett negativt tal kastar ett `ArgumentException`. Validera alltid användarinmatning innan du tilldelar värdet.  
* **Upplösningsmedvetenhet** – Den visuella storleken på skärmen beror också på DPI. Om du senare exporterar till PDF, överväg att sätta `ImageResolution` för att hålla de fysiska dimensionerna konsekventa.  
* **X‑dimension vs. stapelhöjd** – `XDimension.Pixels` styr stapelns **bredd**, inte höjd. Att glömma att sätta den kan göra streckkoden för tunn, särskilt vid låg DPI.  
* **Trådsäkerhet** – `BarcodeGenerator`‑instanser är **inte** trådsäkra. Skapa en ny instans per tråd eller synkronisera åtkomst om du genererar många streckkoder parallellt.

## Fullständig källkod (körbar)

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Output directory – change as needed
            string outputFolder = "C:/Barcodes/";
            System.IO.Directory.CreateDirectory(outputFolder);

            // -----------------------------------------------------------------
            // 1. RM4SCC – automatic height
            // -----------------------------------------------------------------
            BarcodeGenerator rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccAuto.Save($"{outputFolder}PostalRM4SCC_AutoHeight.png", BarCodeImageFormat.Png);

            // -----------------------------------------------------------------
            // 2. Planet – automatic height
            // -----------------------------------------------------------------
            BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
            planetAuto.Save($"{outputFolder}PostalPlanet_AutoHeight.png", BarCodeImageFormat.Png);

            // -----------------------------------------------------------------
            // 3. RM4SCC – fixed height of 100 px
            // -----------------------------------------------------------------
            BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            rm4sccFixed.Save($"{outputFolder}PostalRM4SCC_FixedHeight.png", BarCodeImageFormat.Png);

            // -----------------------------------------------------------------
            // 4. Planet – fixed height of 100 px
            // -----------------------------------------------------------------
            BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
            planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            planetFixed.Save($"{outputFolder}PostalPlanet_FixedHeight.png", BarCodeImageFormat.Png);

            Console.WriteLine("All barcodes generated successfully.");
        }
    }
}
```

Kopiera koden till `Program.cs`, återställ NuGet‑paket och kör `dotnet run`. Konsolen bekräftar lyckad generering, och PNG‑filerna visas i `C:/Barcodes/`.

## Slutsats

Du vet nu hur du **skapar rm4scc‑streckkod** och **genererar planet‑streckkod** i C#, både med automatisk storlek och med en manuellt definierad stapelhöjd. Genom att styra `BarHeight.Pixels` svarar du på frågan **hur man ställer in streckkodshöjd**, så att dina poststreckkoder passar perfekt i vilken etikettlayout som helst.

Nästa steg kan vara att utforska:

* **hur man genererar poststreckkod** i andra format som PDF eller SVG (`BarCodeImageFormat.Pdf`, `BarCodeImageFormat.Svg`).  
* Att lägga till mänskligt läsbar text under streckkoden (`Parameters.Caption`).  
* Att integrera generatorn i ett ASP.NET Core‑API för att leverera streckkoder på begäran.

Känn dig fri att experimentera med olika `XDimension`‑värden, färger eller bakgrundsbilder för att matcha ditt varumärke samtidigt som du håller dig inom streckkodstandarderna. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

De följande handledningarna täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstrerats i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar poststreckkod i C# med anpassade dimensioner](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/)
- [Hur man skapar planet‑streckkod PNG med C# – steg‑för‑steg‑guide](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/)
- [Hur man ställer in bredd och genererar en Planet‑streckkod i C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
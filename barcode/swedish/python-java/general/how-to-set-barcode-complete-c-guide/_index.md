---
category: general
date: 2026-08-15
description: Hur man ställer in streckkodparametrar i C# och genererar streckkodsbilder.
  Lär dig steg för steg att skapa Databar‑streckkod och spara PNG‑filer.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- how to generate barcode
- create databar barcode
- generate barcode image c#
language: sv
lastmod: 2026-08-15
og_description: Hur man ställer in en streckkod i C# med Aspose.Barcode och sedan
  genererar en streckkodsbild i C#. Följ den här guiden för att skapa en Databar‑streckkod
  och spara PNG‑filer.
og_image_alt: Screenshot of a Databar barcode saved as PNG using C# code
og_title: Hur du ställer in streckkod i C# – steg‑för‑steg guide
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: How to set barcode parameters in C# and generate barcode images. Learn
    step‑by‑step to create Databar barcode and save PNG files.
  headline: How to set barcode – complete C# guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: Hur man ställer in streckkod – komplett C#‑guide
url: /sv/python-java/general/how-to-set-barcode-complete-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man ställer in streckkod – komplett C#-guide

Om du letar efter **how to set barcode**‑parametrar i ett .NET‑projekt, visar den här handledningen de exakta stegen du behöver. Du kommer att lära dig **how to generate barcode**‑bilder, skapa en Databar‑streckkod och kontrollera stapelhöjden pixel för pixel — allt med ren, produktionsklar C#‑kod.

I den här guiden kommer du att:

* Installera det erforderliga NuGet‑paketet.  
* Skapa en Databar Omnidirectional‑streckkod (delen “create Databar barcode”).  
* Justera X‑dimension och stapelhöjd för att demonstrera **how to set barcode**‑dimensioner.  
* Spara resultatet som PNG‑filer, vilket täcker scenariot **generate barcode image C#**.

Koden fungerar med den senaste Aspose.Barcode för .NET (v 24.12 vid skrivtillfället) och körs på .NET 6 eller senare.

---

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6 SDK (eller någon senare version).  
* En IDE som Visual Studio 2022 eller VS Code.  
* Internetåtkomst för att ladda ner Aspose.Barcode‑paketet från NuGet.

Inga ytterligare tredjepartsbibliotek krävs.

---

## Steg 1: Installera Aspose.Barcode för .NET

Det mest pålitliga sättet att **generate barcode**‑bilder i C# är att använda Aspose.Barcode. Öppna en terminal i din projektmapp och kör:

```bash
dotnet add package Aspose.BarCode
```

Kommandot lägger till den senaste stabila versionen i din projektfil, vilket säkerställer att du har klassen `BarcodeGenerator` och uppräkningen `EncodeTypes`.

*Pro tip:* Håll paketet uppdaterat (`dotnet list package --outdated`) för att dra nytta av buggfixar och nya streckkodssymbologier.

---

## Steg 2: Skapa en Databar‑streckkod (create Databar barcode)

Databar Omnidirectional är idealisk för detaljhandel och logistik eftersom den kan koda ett GTIN‑14‑värde plus ytterligare data. Följande kod skapar streckkodobjektet:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 2: Initialize the generator for a Databar Omnidirectional barcode
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

*Varför detta är viktigt:* Uppräkningen `EncodeTypes.DatabarOmniDirectional` talar om för biblioteket att använda Databar‑symbologi, medan strängen `"(01)12345678901231"` följer GS1 Application Identifier‑formatet för ett 14‑siffrigt GTIN.

---

## Steg 3: Definiera vanliga parametrar – X‑dimension och bashöjd

De flesta streckkodsläsare förväntar sig en minsta X‑dimension (bredden på den smalaste stapeln). Att sätta den till 2 pixlar ger en kompakt men läsbar bild.

```csharp
// Step 3: Set a 2‑pixel X‑dimension (common for most scanners)
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Du kan senare justera stapelhöjden utan att återskapa generatorn — detta är kärnan i **how to set barcode**‑attribut efter instansiering.

---

## Steg 4: Ställ in första stapelhöjden och spara bilden (generate barcode image C#)

Nu demonstrerar vi den första delen av **how to set barcode**‑höjd. Stapelhöjden styr den visuella längden på varje stapel; ett värde på 30 pixlar ger en kort streckkod, medan 60 pixlar skapar en högre version.

```csharp
// Step 4a: 30‑pixel bar height
generator.Parameters.Barcode.BarHeight.Pixels = 30;

// Save the first PNG image
generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Efter körning innehåller `DatabarBarHeight30Pixels.png` en Databar‑streckkod med en 30‑pixlar hög stapel. Öppna filen i någon bildvisare för att verifiera resultatet.

---

## Steg 5: Ändra stapelhöjden och spara en andra bild

För att illustrera att **how to set barcode**‑värden kan ändras i farten, ändrar vi stapelhöjden till 60 pixlar och skriver en andra fil.

```csharp
// Step 5a: 60‑pixel bar height
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second PNG image
generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Nu har du två PNG‑filer som visar samma Databar‑data men med olika visuella höjder. Detta är användbart när du behöver en större streckkod för tryckta etiketter eller en mindre för visning på skärm.

---

## Steg 6: Fullt, körbart exempel

När vi sätter ihop allt, här är ett fristående konsolprogram som utför alla stegen som beskrivits ovan. Kopiera koden till en ny `Program.cs`‑fil, ersätt `YOUR_DIRECTORY` med en faktisk sökväg och kör den.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the generator for a Databar Omnidirectional barcode
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // Common parameters
        generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2‑pixel narrow bar

        // First image: 30‑pixel height
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save(@"C:\Barcodes\DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode.");

        // Second image: 60‑pixel height
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save(@"C:\Barcodes\DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode.");

        // Dispose the generator to free native resources
        generator.Dispose();
    }
}
```

**Förväntat resultat**

När du kör programmet skriver konsolen ut:

```
Saved 30-pixel barcode.
Saved 60-pixel barcode.
```

Och mappen `C:\Barcodes` (eller den sökväg du angav) innehåller de två PNG‑filerna. Båda bilderna visar en giltig Databar Omnidirectional‑streckkod som kan läsas av standard‑GS1‑läsare.

---

## Vanliga frågor

**Fungerar detta med andra bildformat?**  
Ja. Ersätt `BarCodeImageFormat.Png` med `Jpeg`, `Bmp`, `Gif` eller `Tiff` för att generera motsvarande filtyp.

**Kan jag ändra förgrundsfärgen?**  
Sätt `generator.Parameters.Barcode.ForeColor` till vilket `System.Drawing.Color`‑värde som helst, t.ex. `Color.Blue`.

**Vad händer om jag behöver en annan symbologi?**  
Skicka ett annat `EncodeTypes`‑värde till konstruktorn, till exempel `EncodeTypes.Code128` för en linjär streckkod eller `EncodeTypes.QR` för en matris‑kod.

**Finns det ett sätt att bädda in streckkoden i en PDF?**  
Aspose.Barcode tillhandahåller en `PdfGenerator`‑klass. Efter att ha genererat bilden kan du lägga till den på en PDF‑sida med hjälp av Aspose.PDF.

---

## Bästa praxis för streckkodsgenerering i C#

* **Återanvänd `BarcodeGenerator`‑instansen** när du bara behöver justera dimensioner — detta undviker onödiga minnesallokeringar.  
* **Dispose generatorn** (`generator.Dispose()`) när du är klar för att snabbt frigöra inhemska resurser.  
* **Validera indata** (t.ex. GTIN‑längd) innan du skapar streckkoden för att förhindra körningsfel.  
* **Testa med en fysisk scanner** efter att du ändrat X‑dimension eller stapelhöjd; extrema värden kan påverka läsbarheten.  
* **Se till att utskriftsmappen är skrivbar** för det körande kontot; annars kommer `Save` att kasta ett `UnauthorizedAccessException`.

---

## Slutsats

Du vet nu **how to set barcode**‑egenskaper såsom X‑dimension och stapelhöjd, **how to generate barcode**‑bilder i C#, och de exakta stegen för att **create Databar barcode**‑filer med Aspose.Barcode. Genom att följa det kompletta exemplet kan du generera flera PNG‑filer med olika visuella egenskaper, vilket uppfyller kravet **generate barcode image C#** för vilken .NET‑applikation som helst.

Nästa steg är att utforska relaterade ämnen såsom **how to generate barcode** i bulk, inbäddning av streckkoder i PDF‑filer, eller byte till andra symbologier som QR eller Code 128. Experimentera med parametrarna som visas här för att finjustera streckkodens utseende för din specifika skannermiljö. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar DataMatrix‑streckkoder (ECC 200) med Aspose.BarCode för .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Hur man genererar Aztec‑streckkod med anpassat bildförhållande med Aspose.BarCode för .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Hur man genererar streckkod – Code 39‑konfiguration med Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
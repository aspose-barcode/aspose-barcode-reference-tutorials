---
category: general
date: 2026-11-17
description: Skapa streckkod‑PNG i C# snabbt – en steg‑för‑steg‑guide som visar hur
  du genererar en Planet‑streckkod, anpassar dess storlek och sparar bilden.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to create barcode
- barcode generator example
- generate planet barcode
- customize barcode size
language: sv
lastmod: 2026-11-17
og_description: Skapa streckkod PNG i C# med Aspose.Barcode. Lär dig hur du genererar
  en Planet‑streckkod, anpassar dess storlek och sparar en högkvalitativ PNG‑bild.
og_image_alt: C# code snippet that creates a barcode PNG file
og_title: Skapa streckkod PNG i C# – komplett guide
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Create barcode PNG in C# quickly – a step‑by‑step guide that shows
    how to generate a Planet barcode, customize its size, and save the image.
  headline: How to create barcode PNG in C# using Aspose.Barcode
  type: TechArticle
- description: Create barcode PNG in C# quickly – a step‑by‑step guide that shows
    how to generate a Planet barcode, customize its size, and save the image.
  name: How to create barcode PNG in C# using Aspose.Barcode
  steps:
  - name: '**Instantiate** the generator with the desired symbology and data.'
    text: '**Instantiate** the generator with the desired symbology and data.'
  - name: '**Adjust parameters** such as size and bar style.'
    text: '**Adjust parameters** such as size and bar style.'
  - name: '**Save** the image in the format you need.'
    text: '**Save** the image in the format you need.'
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
title: Hur man skapar streckkod PNG i C# med Aspose.Barcode
url: /sv/python-java/general/how-to-create-barcode-png-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar barcode PNG i C# med Aspose.Barcode

Om du behöver **skapa barcode PNG**-filer från C#-kod visar den här guiden exakt hur du gör det. Oavsett om du bygger ett system för postetiketter eller en point‑of‑sale‑app, kommer du att lära dig ett komplett **barcode generator‑exempel** som genererar en Planet‑streckkod, låter dig **anpassa barcode storlek**, och sparar resultatet som en PNG‑bild.

Du avslutar tutorialen med ett färdigt program som du kan lägga in i vilket .NET‑projekt som helst. Inga externa tjänster krävs—bara Aspose.Barcode‑biblioteket och några rader kod.

## Förutsättningar

| Krav | Orsak |
|------|-------|
| .NET 6.0 SDK or later | Tillhandahåller runtime för C#‑konsolappen |
| Visual Studio 2022 (or any IDE) | Låter dig kompilera och felsöka koden |
| Aspose.Barcode for .NET NuGet package | Innehåller `BarcodeGenerator`‑klassen som används i exemplet |

Installera NuGet‑paketet från kommandoraden:

```bash
dotnet add package Aspose.Barcode
```

> **Pro tip:** Om du föredrar Package Manager Console i Visual Studio, kör `Install-Package Aspose.Barcode`.

## Steg 1: Skapa ett nytt konsolprojekt

Öppna en terminal och kör:

```bash
dotnet new console -n BarcodePngDemo
cd BarcodePngDemo
```

Det här skapar en minimal C#‑konsolapplikation med namnet **BarcodePngDemo**.

## Steg 2: Skapa barcode PNG i C# (kärnan i lösningen)

Kärnan i tutorialen är `BarcodeGenerator`‑objektet. I detta steg **skapar vi barcode PNG** genom att instansiera generatorn med *Planet*-symbologi och den data du vill koda.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2.1: Initialize the generator for the Planet barcode type
        // "123456" is the data that will be encoded.
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Step 2.2: Set the module (X‑dimension) size – 4 pixels per bar gives a clear image.
        generator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 2.3: Choose the empty‑bars style (unfilled bars) for a postal‑friendly look.
        generator.Parameters.Barcode.FilledBars = false;

        // Step 2.4: Save the generated barcode as a PNG file.
        // Adjust the path as needed for your environment.
        generator.Save("postal_planet_empty_bars.png", BarCodeImageFormat.Png);

        System.Console.WriteLine("Barcode PNG created successfully.");
    }
}
```

### Varför dessa inställningar är viktiga

* **EncodeTypes.Planet** – *Planet*-symbologin är avsedd för postapplikationer; den kodar numerisk data effektivt.  
* **XDimension.Pixels = 4** – Denna **customize barcode size**‑inställning styr bredden på varje stapel. Ett värde på 4 pixlar balanserar läsbarhet och filstorlek för de flesta skrivare.  
* **FilledBars = false** – Stilen med tomma staplar producerar en vit‑på‑svart bild som skannas bra på högkontrast‑papper, ett vanligt krav för postetiketter.  
* **BarCodeImageFormat.Png** – PNG bevarar skarpa kanter utan förlustkomprimering, vilket säkerställer att streckkoden förblir skannbar.

## Steg 3: Så skapar du barcode – grundläggande sammanfattning

Om du är ny på barcode‑generering kapslar de tre raderna ovan in hela **how to create barcode**‑arbetsflödet:

1. **Instantiate** generatorn med önskad symbologi och data.  
2. **Adjust parameters** såsom storlek och stapelstil.  
3. **Save** bilden i det format du behöver.

Du kan ersätta `EncodeTypes.Planet` med någon annan stödd typ (t.ex. `EncodeTypes.Code128`) utan att ändra den omgivande koden.

## Steg 4: Barcode generator‑exempel – lägg till mer anpassning

Utöver storlek och tomma staplar låter Aspose.Barcode dig justera färger, marginaler och text. Nedan är en snabb utökning som lägger till en röd förgrund och en vit bakgrund, och sedan sparar samma streckkod under ett annat namn.

```csharp
// Change colors (optional)
generator.Parameters.Barcode.BarColor = System.Drawing.Color.Red;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;

// Save a second version
generator.Save("postal_planet_red.png", BarCodeImageFormat.Png);
```

> **Watch out for:** Att använda färger med låg kontrast kan göra streckkoden oläslig för vissa skannrar. Testa alltid med din mål‑hardware.

## Steg 5: Generera Planet‑streckkod med tomma staplar (fullständigt exempel)

När allt sätts ihop, här är det kompletta programmet som du kan kopiera‑och‑klistra in i `Program.cs`:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodePngDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for a Planet barcode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // Customize size – 4 pixels per module.
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // Use empty‑bars style for postal friendliness.
            generator.Parameters.Barcode.FilledBars = false;

            // Save the primary PNG.
            generator.Save("postal_planet_empty_bars.png", BarCodeImageFormat.Png);

            // Optional: change colors and save a second version.
            generator.Parameters.Barcode.BarColor = System.Drawing.Color.Red;
            generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
            generator.Save("postal_planet_red.png", BarCodeImageFormat.Png);

            Console.WriteLine("Both barcode PNG files have been generated.");
        }
    }
}
```

Kör programmet:

```bash
dotnet run
```

Du bör se två PNG‑filer i projektmappen:

* `postal_planet_empty_bars.png` – en klassisk svart‑på‑vit streckkod med tomma staplar.  
* `postal_planet_red.png` – en färgad variant som demonstrerar ytterligare **customize barcode size**‑alternativ.

Öppna någon av filerna i en bildvisare; du kommer att se en ren, skannbar streckkod redo för utskrift.

## Vanliga fallgropar och felsökning

| Symptom | Trolig orsak | Åtgärd |
|---------|--------------|-------|
| Streckkoden blir suddig | X‑dimension för låg (t.ex. 1 pixel) | Öka `XDimension.Pixels` till minst 3‑4 pixlar. |
| Skannern kan inte läsa bilden | Färger har otillräcklig kontrast | Använd mörk stapelfärg på en ljus bakgrund, eller återgå till standard svart/vitt‑schema. |
| `Save` kastar `ArgumentException` | Ogiltig filsökväg eller saknad skrivbehörighet | Verifiera att katalogen finns och att ditt program har skrivbehörighet. |
| Fel symbologi skriven | Fel `EncodeTypes`‑enum‑värde | Dubbelkolla att du har valt `EncodeTypes.Planet` (eller den avsedda typen). |

## Bästa praxis för produktionsanvändning

* **Validate input data** innan du skickar den till `BarcodeGenerator`. Planet‑streckkoder accepterar endast numeriska strängar av specifika längder.  
* **Cache the generator** om du behöver skapa många streckkoder med identiska inställningar; återanvändning av objektet förbättrar prestanda.  
* **Use PNG for on‑screen rendering** och **PDF eller TIFF för högupplöst utskrift**—båda stöds av Aspose.Barcode.  
* **Test with the actual scanner** du planerar att använda. Olika enheter har varierande tolerans för stapelbredd och kontrast.

## Slutsats

Du vet nu hur du **skapar barcode PNG**‑filer i C# med ett koncist **barcode generator‑exempel**. Tutorialen täckte:

* Instansiering av en `BarcodeGenerator` för **Planet**‑symbologin.  
* **Customize barcode size** med X‑dimension‑egenskapen.  
* Tillämpning av en tom‑staplar‑stil för postvänligt resultat.  
* Sparar resultatet som en PNG‑bild och eventuellt justerar färger.

Härifrån kan du utforska andra symbologier, lägga till mänskligt läsbar text, eller integrera koden i ett webb‑API som returnerar barcode PNG‑filer på begäran. Lycka till med kodningen, och må dina skanningar alltid vara perfekta!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger på teknikerna som demonstrerats i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar barcode PNG i C# – steg‑för‑steg‑guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-barcode-png-in-c-step-by-step-guide/)
- [Hur man skapar barcode PNG med ett anpassat bildförhållande i C#](/barcode/english/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/)
- [Hur man använder en C# barcode‑generator för att skapa en Planet‑streckkod](/barcode/english/python-java/general/how-to-use-a-c-barcode-generator-to-create-a-planet-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
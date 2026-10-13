---
category: general
date: 2026-10-04
description: Skapa PDF417‑streckkod i C# snabbt. Lär dig hur du genererar PDF417‑streckkod
  och hur du sparar streckkodsbild som PNG med Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode c#
- barcode for mobile scanning
- aspose barcode png generation
lastmod: 2026-10-04
og_description: Skapa PDF417‑streckkod i C# med Aspose.Barcode. Denna handledning
  visar hur du genererar en kompakt PDF417‑streckkod, konfigurerar dess utseende och
  sparar den som en PNG‑bild för mobilskanning eller etikettutskrift.
og_image_alt: 'Developer guide: Create PDF417 barcode in C# and save as PNG using
  Aspose.Barcode'
og_title: Skapa PDF417‑streckkod i C# – fullständig steg‑för‑steg‑guide
schemas:
- author: Aspose
  dateModified: '2026-10-04'
  description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  headline: Create PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  name: Create PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: Why this matters
    text: '* **EncodeTypes.Pdf417** tells the library to use the PDF417 standard,
      which supports large data payloads and error correction. * Providing Unicode
      characters proves the generator handles non‑ASCII input without extra configuration.'
  - name: Practical tip
    text: If you need a taller barcode for limited horizontal space, increase `Columns`.
      Setting `Truncate` to `true` reduces the overall height by removing quiet zones,
      which is ideal for mobile screens.
  - name: Expected result
    text: Running the program creates `CompactPdf417.png` in the project folder. Opening
      the file shows a compact PDF417 barcode that encodes the string *Åspóse.Barcóde©*.
      The image can be embedded in HTML, PDF reports, or printed on labels.
  - name: Verifying the output
    text: 'After the program finishes, you can verify the file exists with a quick
      command:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
- Aspose.Barcode
title: Skapa PDF417‑streckkod i C# – steg‑för‑steg‑guide
url: /sv/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa PDF417-streckkod i C# – steg‑för‑steg‑guide

Om du behöver **skapa PDF417-streckkod** i en .NET-applikation, visar den här guiden exakt hur du genererar en PDF417-streckkod och hur du sparar streckkodens bild som en PNG‑fil. Du får en kompakt bild som fungerar utmärkt för mobilsökning, biljettsystem eller etikettprinter.

## Snabba svar
- **Vilket bibliotek hanterar PDF417-generering?** Aspose.Barcode for .NET.  
- **I vilket format sparar exemplet?** PNG, using `BarCodeImageFormat.Png`.  
- **Hur många kodrader krävs?** Ungefär 10 rader efter projektuppsättning.  
- **Kan jag anpassa storlek och trunkering?** Ja – `Columns`, `Rows` och `Truncate`-egenskaper.  
- **Är koden kompatibel med .NET‑6?** Fullt, och den fungerar också med .NET Framework 4.7+.

## Vad du behöver för att skapa en PDF417-streckkod i C#?
För att börja behöver du ett aktuellt .NET SDK, en IDE som Visual Studio 2022 och **Aspose.Barcode for .NET** NuGet-paketet. Dessa verktyg låter exemplet kompileras och köras utan extra konfiguration.

- .NET 6.0 SDK eller senare (fungerar också med .NET Framework 4.7+)
- Visual Studio 2022 eller någon C#‑kompatibel redigerare
- Internetåtkomst för att ladda ner Aspose.Barcode NuGet-paketet

## Hur ställer du in ett .NET-projekt för PDF417-streckkodsgenerering?
Skapa ett nytt konsolprojekt, lägg till Aspose.Barcode-paketet och öppna den genererade `Program.cs`. Detta förbereder en ren arbetsyta där du kan instansiera streckkodsgeneratorn och skriva utdatafilen.

```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

## Hur kan du generera en PDF417-streckkod med Aspose.Barcode?
`BarcodeGenerator` är Aspose.Barcode-klassen som skapar streckkods­bilder från angivna data och symbolik. Du specificerar PDF417‑symboliken, anger texten som ska kodas och kan valfritt justera storlek eller felkorrigeringsinställningar.

```bash
   dotnet add package Aspose.Barcode
   ```

### Varför detta är viktigt
* **EncodeTypes.Pdf417** talar om för biblioteket att använda PDF417‑standarden, som stödjer stora datamängder och felkorrigering.
* Att tillhandahålla Unicode‑tecken visar att generatorn hanterar icke‑ASCII‑inmatning utan extra konfiguration.

## Hur konfigurerar du utseendet på en PDF417-streckkod?
Du kan kontrollera modulstorlek, kolumnantal och om streckkoden använder kompakt (trunkerat) läge. Dessa inställningar påverkar direkt läsbarheten på små skärmar och den totala filstorleken för PNG‑bilden.

`generator.Parameters.Barcode.XDimension` sätter bredden på en enskild modul, medan `Columns` och `Rows` definierar matrisens dimensioner. Att sätta `Truncate` till `true` tar bort tysta zoner för en mer kompakt bild.

```csharp
   using System;
   using Aspose.Barcode.Generation;
   using Aspose.Barcode;
   ```

### Praktiskt tips
Om du behöver en högre streckkod för begränsat horisontellt utrymme, öka `Columns`. Att sätta `Truncate` till `true` minskar den totala höjden genom att ta bort tysta zoner, vilket är idealiskt för mobila skärmar.

## Hur sparar du streckkodsbilden som PNG?
`Save` är en metod i `BarcodeGenerator` som skriver den genererade bilden till en fil. Ange en filsökväg och `BarCodeImageFormat.Png` för att skapa en PNG‑bild i ett enda steg.

```csharp
// Step 1: Initialise the generator with PDF417 symbology and sample text.
// The text includes Unicode characters to demonstrate full‑range support.
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

### Förväntat resultat
När programmet körs skapas `CompactPdf417.png` i projektmappen. När du öppnar filen visas en kompakt PDF417‑streckkod som kodar strängen *Åspóse.Barcóde©*. Bilden kan bäddas in i HTML, PDF‑rapporter eller skrivas ut på etiketter.

## Hur kan du verifiera den genererade streckkodsfilen?
När programmet är klart kan du verifiera att filen finns med ett snabbt kommando. Denna enkla kontroll bekräftar att genererings- och sparstegen slutfördes utan fel.

```csharp
// Step 2: Set the module (X) dimension – each barcode element will be 2 pixels wide.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Configure PDF417‑specific options.
generator.Parameters.Barcode.Pdf417.Columns = 3;      // Number of columns (affects height)
generator.Parameters.Barcode.Pdf417.Truncate = true; // Enable compact mode
```

Om filen visas, har processen **create PDF417 barcode** lyckats.

## Vilka vanliga variationer och kantfall finns vid generering av PDF417-streckkoder?
Olika scenarier kan kräva justeringar av generatorinställningarna. Nedan finns en snabb referenstabell som visar hur man hanterar typiska variationer.

| Situation | Justering |
|-----------|------------|
| **Längre datasträng** | Öka `Columns` eller sätt `Rows` för att rymma fler kodord. |
| **Annat bildformat** | Byt ut `BarCodeImageFormat.Png` mot `Jpeg`, `Bmp` eller `Gif`. |
| **Högre upplösning** | Sätt `generator.Parameters.ImageResolution` innan `Save`. |
| **Bakgrundsfärg** | Använd `generator.Parameters.Barcode.ImageBackgroundColor = Color.White;`. |
| **Undantagshantering** | Omslut `generator.Save` med ett `try/catch`-block för att fånga I/O‑fel. |

Dessa variationer låter dig anpassa streckkoden för specifika enheter eller varumärkeskrav.

## Vad är nästa steg efter att ha skapat streckkoden?
Nu när du kan generera och spara en PDF417‑streckkod kan du utforska relaterade funktioner som att generera QR‑koder, bädda in streckkoder i PDF‑dokument eller anpassa färger för varumärkesanpassning. Alla dessa använder samma `BarcodeGenerator`‑API, så du kan utöka exemplet med minimal ansträngning.

## Relaterade guider
- [Hur man skapar streckkod – kompakt PDF417 med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hur man genererar DataMatrix‑streckkoder (ECC 200) med Aspose.BarCode för .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Hur man genererar Aztec‑streckkod med anpassat bildförhållande med Aspose.BarCode för .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

## Vanliga frågor

**Q: Kan jag använda den här koden i en webbapplikation?**  
A: Ja. Samma `BarcodeGenerator`‑klass fungerar i ASP.NET, MVC eller Blazor‑projekt; se bara till att servern har skrivrättigheter för utdatamappen.

**Q: Stöder Aspose.Barcode andra 2‑D‑symboler?**  
A: Absolut. Över 30 typer av 2‑D‑streckkoder stöds, inklusive QR, DataMatrix och Aztec.

**Q: Hur stor streckkod kan jag skapa?**  
A: PDF417 kan koda upp till 1 850 tecken i en enda symbol; du kan också dela upp data över flera rader genom att justera `Rows` och `Columns`.

**Q: Krävs en licens för produktionsanvändning?**  
A: Ja. En gratis provperiod finns för utvärdering, men en kommersiell licens behövs för distribution.

**Q: Vilka .NET‑versioner är kompatibla?**  
A: Aspose.Barcode stöder .NET Framework 4.5+, .NET Core 3.1+ och .NET 5/6/7.

---

**Senast uppdaterad:** 2026-10-04  
**Testat med:** Aspose.Barcode 24.11 for .NET  
**Författare:** Aspose  

```csharp
// Step 4: Save the generated barcode as a PNG image.
string outputPath = @"./CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```
```csharp
using System;
using Aspose.Barcode.Generation;
using Aspose.Barcode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with PDF417 symbology and sample text.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Åspóse.Barcóde©");

            // Set the module width to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Configure PDF417‑specific options.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Define the output file path.
            string outputPath = @"./CompactPdf417.png";

            // Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```
```bash
dotnet run && ls -l CompactPdf417.png
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
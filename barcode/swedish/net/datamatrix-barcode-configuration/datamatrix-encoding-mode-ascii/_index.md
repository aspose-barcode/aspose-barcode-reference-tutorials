---
date: 2026-06-09
description: Lär dig hur du skapar DataMatrix-streckkod i ASCII-läge med Aspose.BarCode
  för .NET. Den här guiden visar hur du snabbt genererar streckkod i C#.
keywords:
- create datamatrix barcode
- generate barcode c#
- how to encode barcode
- barcode generator example
linktitle: DataMatrix kodningsläge (ASCII)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  headline: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  name: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  steps:
  - name: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
    text: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
  - name: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
  - name: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
    text: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
  - name: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
    text: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
  type: HowTo
- questions:
  - answer: Yes, a valid Aspose license is required for production use; a free trial
      is available for evaluation.
    question: Can I use this in a commercial application?
  - answer: Absolutely – Aspose.BarCode fully supports .NET Core 3.1+, .NET 5, .NET
      6, and later versions.
    question: Does the library work with .NET Core?
  - answer: Up to 2,335 alphanumeric characters fit in a single DataMatrix symbol
      when using ASCII encoding.
    question: How many characters can I encode in ASCII mode?
  - answer: Yes, adjust `generator.Parameters.Image.ForeColor` and `BackColor` to
      any `System.Drawing.Color` value.
    question: Can I change the barcode’s foreground or background color?
  - answer: The official documentation contains dozens of samples covering custom
      sizes, colors, and error‑correction levels.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Skapa DataMatrix-streckkod i ASCII-läge med Aspose.BarCode för .NET
url: /sv/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa DataMatrix-streckkod i ASCII-läge med Aspose.BarCode för .NET

## Introduktion

Redo att **skapa DataMatrix-streckkod**-bilder som använder den effektiva ASCII-kodningen? I den här handledningen lär du dig hur du genererar en DataMatrix-streckkod i ASCII-läge med Aspose.BarCode för .NET. Vi går igenom varje steg—från att sätta upp projektet till att spara den slutgiltiga bilden—så att du kan lägga till streckkodsgenerering i dina C#-applikationer på några minuter.

## Snabba svar
- **Vilket bibliotek är bäst för DataMatrix i .NET?** Aspose.BarCode for .NET  
- **Hur många kodrader behövs?** Ungefär 5‑7 rader för en grundläggande ASCII-streckkod  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en licens krävs för produktion  
- **Stödda plattformar?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **Kan jag ändra storlek eller färger?** Ja, Aspose.BarCode exponerar egenskaper för dimensioner samt förgrunds-/bakgrundsfärger  

## Vad är DataMatrix-streckkod?
DataMatrix är en tvådimensionell streckkod som lagrar text och binär data i ett kompakt fyrkantigt mönster.  
En DataMatrix-streckkod kodar information i ett rutnät av svarta och vita moduler, vilket möjliggör upp till 2 335 alfanumeriska tecken i en enda symbol. Den används i stor utsträckning inom tillverkning, logistik och sjukvård eftersom den kan skrivas ut i mycket små storlekar samtidigt som den förblir mycket läsbar.

## Hur skapar man DataMatrix-streckkod i ASCII-läge?
Läs in Aspose.BarCode-namnutrymmet, skapa en `BarcodeGenerator`, sätt `EncodeMode` till **EncodeMode.ASCII**, tilldela din datasträng och anropa `Save` för att skriva bildfilen. Detta tillvägagångssätt genererar en helt kompatibel DataMatrix-streckkod med enbart ASCII‑kodning på bara några rader C#-kod.

## Varför använda ASCII‑kodning för DataMatrix?
ASCII‑läge är standard och den mest effektiva kodningen för vanlig text, vilket ger den minsta möjliga symbolstorleken för alfanumeriska strängar. Det stöder alla 128 ASCII‑tecken, bearbetar data snabbare än utökade lägen och garanterar maximal kompatibilitet med äldre skannrar som förväntar sig standard‑ASCII‑symboler.

## Förutsättningar

1. **Utvecklingsmiljö** – Visual Studio, Rider eller någon C#‑kompatibel IDE.  
2. **Aspose.BarCode for .NET** – Ladda ner det senaste paketet från [here](https://releases.aspose.com/barcode/net/).  
   - Dokumentation: [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)  
   - Communityhjälp: [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)  
3. **Grundläggande C#-kunskaper** – Bekantskap med .NET-projektstruktur hjälper dig att följa stegen snabbt.  
4. **Andra Aspose-produkter** finns på [here](https://releases.aspose.com/).

## Importera namnrymder

To start, add the required `using` directives at the top of your C# file:

```csharp
using Aspose.BarCode.Generation;
using System.Drawing;
```

Dessa namnrymder ger dig åtkomst till `BarcodeGenerator`-klassen och de bildrelaterade typerna som behövs för att spara resultatet.

## Steg 1: Skapa en katalog

Välj en mapp där de genererade streckkodsbilderna ska lagras. Ersätt `"Your Directory Path"` med en absolut eller relativ sökväg som finns på din maskin.

```csharp
string outputDir = @"C:\Barcodes";
if (!System.IO.Directory.Exists(outputDir))
{
    System.IO.Directory.CreateDirectory(outputDir);
}
```

Koden säkerställer att katalogen finns innan den försöker skriva några filer, vilket förhindrar körningsfel.

## Steg 2: Koda data i ASCII‑läge

`BarcodeGenerator`-klassen skapar och konfigurerar streckkodsbilder. `DataMatrixEncodeMode`‑enumerationen väljer kodningsalgoritmen för DataMatrix‑symboler.

```csharp
// Initialise the generator with the data you want to encode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "1234567890");

// Set the encoding mode to ASCII for optimal size
generator.Parameters.Barcode.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;

// Optional: adjust image dimensions or colors here
generator.Parameters.Image.Width = 200;
generator.Parameters.Image.Height = 200;

// Save the barcode as a PNG file
string filePath = System.IO.Path.Combine(outputDir, "datamatrix_ascii.png");
generator.Save(filePath, BarCodeImageFormat.Png);
```

Efter att ha kört koden hittar du `datamatrix_ascii.png` i den mapp du angav. Bilden innehåller en DataMatrix-streckkod som kodar strängen `"1234567890"` med det kompakta ASCII‑läget.

## Vanliga problem och lösningar

- **Fil‑åtkomstfel** – Se till att applikationen har skrivbehörighet till målmappen. Att köra Visual Studio som administratör kan lösa behörighetsproblem på Windows.  
- **Felaktig symbolstorlek** – Om streckkoden visas för stor eller för liten, justera `generator.Parameters.Image.Width` och `Height` eller låt Aspose automatiskt beräkna optimal storlek genom att utelämna dessa egenskaper.  
- **Ej stödda tecken** – ASCII‑läge accepterar endast tecken i intervallet 0‑127. För Unicode‑data, byt till `DataMatrixEncodeMode.Base256` eller ett annat lämpligt läge.

## Vanliga frågor

**Q: Kan jag använda detta i en kommersiell applikation?**  
A: Ja, en giltig Aspose-licens krävs för produktionsanvändning; en gratis provversion finns tillgänglig för utvärdering.

**Q: Fungerar biblioteket med .NET Core?**  
A: Absolut – Aspose.BarCode stödjer fullt ut .NET Core 3.1+, .NET 5, .NET 6 och senare versioner.

**Q: Hur många tecken kan jag koda i ASCII‑läge?**  
A: Upp till 2 335 alfanumeriska tecken får plats i en enda DataMatrix-symbol när ASCII‑kodning används.

**Q: Kan jag ändra streckkodens förgrunds‑ eller bakgrundsfärg?**  
A: Ja, justera `generator.Parameters.Image.ForeColor` och `BackColor` till valfritt `System.Drawing.Color`‑värde.

**Q: Var kan jag hitta mer avancerade exempel?**  
A: Den officiella dokumentationen innehåller dussintals exempel som täcker anpassade storlekar, färger och felkorrigeringsnivåer.

## FAQ:s

### Q1: Kan jag använda Aspose.BarCode för .NET med andra programmeringsspråk än C#?
A1: Aspose.BarCode stödjer flera programmeringsspråk, men den här handledningen fokuserar på C#.

### Q2: Vilka olika kodningslägen finns tillgängliga i DataMatrix-streckkoder?
A2: DataMatrix-streckkoder stödjer olika kodningslägen, inklusive ASCII, C40, Text och Base256. Varje läge är lämpligt för olika typer av data.

### Q3: Kan jag anpassa utseendet på den genererade streckkoden, såsom dess storlek och färg?
A3: Ja, Aspose.BarCode erbjuder ett brett utbud av parametrar för att anpassa streckkodens utseende, inklusive storlek, färg och mer.

### Q4: Finns det en gratis provversion av Aspose.BarCode för .NET tillgänglig?
A4: Ja, du kan utforska Aspose.BarCode för .NET med en gratis provversion från [here](https://releases.aspose.com/).

### Q5: Var kan jag köpa en licens för Aspose.BarCode för .NET?
A5: Du kan köpa en licens från Aspose-webbplatsen [here](https://purchase.aspose.com/buy).

---

**Senast uppdaterad:** 2026-06-09  
**Testat med:** Aspose.BarCode 24.11 for .NET  
**Författare:** Aspose

## Relaterade handledningar

- [DataMatrix-kodning i byte med Aspose.BarCode för .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [Läs DataMatrix-streckkod C# – Generera DataMatrix-läge (Auto)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Hur man genererar DataMatrix-streckkoder (ECC 200) med Aspose.BarCode för .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.BarCode.Generation;
```

```csharp
string path = "Your Directory Path";
```

```csharp
System.Console.WriteLine("DataMatrixEncodeModeASCII:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    // Set the X-dimension (size) of the barcode in pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set the encoding mode to ASCII
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;
    
    // Save the barcode as a PNG image
    gen.Save($"{path}DataMatrixEncodeModeASCII.png", BarCodeImageFormat.Png);
}
```

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
---
category: general
date: 2026-10-14
description: Skapa en konsol‑streckkodsläsare i C# som läser PDF417‑streckkoder, hanterar
  macro PDF417 och avkodar flera streckkoder från en enda bild.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create console barcode scanner
- read barcodes from picture
- c# barcode reader example
lastmod: 2026-10-14
og_description: Skapa en konsol‑streckkodsläsare i C# för att snabbt läsa PDF417‑
  och macro PDF417‑streckkoder från bilder. Denna steg‑för‑steg‑guide visar hur man
  avkodar flera streckkoder i en bild.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: Skapa konsol‑streckkodsläsare i C# – komplett guide
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  headline: Create console barcode scanner in C# – barcode reader example
  type: TechArticle
- description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  name: Create console barcode scanner in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
- console application
title: Skapa konsol‑streckkodsläsare i C# – läs PDF417‑streckkodsexempel
url: /sv/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa konsol‑streckkodsläsare i C# – läs PDF417‑streckkodsexempel

`BarCodeReader` är Aspose.BarCode:s kärnklass som avkodar streckkoder från bilder och returnerar detaljerad metadata. Om du behöver läsa PDF417‑streckkoddata från en bild visar den här guiden hur du gör det med **BarCodeReader**‑klassen i C#. Du får ett **create console barcode scanner**‑exempel som även hanterar macro PDF417 och kan läsa flera streckkoder i en enda bild.

Att arbeta med streckkoder innebär ofta att hantera olika bildkällor, varierande ljusförhållanden och ibland sammansatta data som macro PDF417‑segment. Denna handledning täcker allt du behöver för att avkoda en PDF417‑streckkod, extrahera dess utökade fält och bearbeta flera streckkoder från samma bild. I slutet har du ett körbart konsolprogram som läser streckkoder från en bildfil och skriver ut detaljerad information till konsolen.

## Snabba svar
- **Vad gör exemplet?** Det skapar en konsol‑streckkodsläsare som läser PDF417‑ och macro PDF417‑streckkoder från en bild och skriver ut alla avkodade fält.  
- **Vilket bibliotek krävs?** Aspose.BarCode för .NET (NuGet).  
- **Kan det läsa flera streckkoder samtidigt?** Ja – läsaren itererar över varje streckkod som hittas i bilden.  
- **Behöver jag internetanslutning?** Nej, biblioteket fungerar helt offline.  
- **Vilken .NET‑version stöds?** .NET 6.0 eller senare.

## Vad du behöver

Innan du börjar, se till att du har:

* .NET 6.0 SDK eller senare installerat  
* En aktuell version av **Aspose.BarCode for .NET**‑paketet (eller något kompatibelt bibliotek som tillhandahåller `BarCodeReader` och `DecodeType.MacroPdf417`)  
* En bildfil som innehåller en PDF417‑ eller macro PDF417‑streckkod (exemplet använder `ExtPDF417Meta.png`)  
* En kodredigerare eller IDE, t.ex. Visual Studio 2022  

Inga ytterligare tjänster eller externa API:er krävs.

## Konfigurera projektet för streckkodsläsning

1. **Skapa ett nytt konsolprojekt**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **Lägg till streckkodsbiblioteket**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **Kopiera streckkodsbilden**  

   Placera `ExtPDF417Meta.png` (eller någon bild som innehåller en PDF417‑streckkod) i projektmappen.  
   För den här handledningen antar vi att filen finns i `YOUR_DIRECTORY/ExtPDF417Meta.png`.

Projektet är nu redo att kompileras och köra streckkodsläsar‑exemplet.

## Hur skapar jag en konsol‑streckkodsläsare i C#?

`BarCodeReader` är en klass som tillhandahålls av Aspose.BarCode och som läser streckkoder från bilder och returnerar deras avkodade data.  
Läs in bilden med `BarCodeReader`, sätt avkodningstypen till `MacroPdf417` och iterera över resultaten – det är allt du behöver för att skapa en konsol‑streckkodsläsare. Läsaren frigör automatiskt inhemska resurser tack vare `using`‑satsen, så du behöver inte hantera minnet manuellt. Detta tillvägagångssätt fungerar för alla bildformat som stöds av .NET, såsom PNG, JPEG eller BMP.

### Steg‑för‑steg‑genomgång

Kärnan i lösningen är ett `using`‑block som skapar en `BarCodeReader`‑instans, specificerar `DecodeType.MacroPdf417` och itererar över varje upptäckt streckkod. Följande kod är ett komplett, självständigt program som du kan klistra in i `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**Varför detta fungerar**:  

* `DecodeType.MacroPdf417` talar om för läsaren att leta efter macro‑utökningen av PDF417, som bär med sig extra metadata såsom fil‑ID, segmentantal och tidsstämplar.  
* `using`‑satsen garanterar att ohanterade resurser (filhandtag, inhemska avkodningsbuffertar) frigörs omedelbart.  
* `foreach`‑loopen bearbetar automatiskt **alla** streckkoder som bilden innehåller, vilket uppfyller kravet på *read multiple barcodes*.

När du kör programmet (`dotnet run`) bör du se en utskrift liknande följande:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

Om bilden innehåller mer än en PDF417‑streckkod skriver loopen ut ett separat block för varje streckkod och demonstrerar hur man **read multiple barcodes** från en enda bild.

## Hur kan jag läsa flera streckkoder från en bild?

Använd en enda `BarCodeReader`‑instans och sätt `DecodeType`‑flaggan så att den inkluderar alla format du vill upptäcka. Genom att kombinera flaggor med bitvis OR‑operator kan du instruera biblioteket att leta efter PDF417, QR, Code‑128 och många andra symboler i ett enda pass. Detta eliminerar behovet av separata läsare och minskar bearbetningstiden.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* är en bitmask, så du kan kombinera valfritt antal stödjade format. Aspose.BarCode stöder **30+ barcode symbologies**, inklusive QR, DataMatrix, Code‑128 och UPC‑A, vilket möjliggör en enda scanner att hantera olika användningsfall som produktmärkning, biljettvalidering och identitetsverifiering.

## Vad är macro PDF417 och hur får jag åtkomst till dess fält på ett säkert sätt?

Macro PDF417 är en utökning av PDF417‑symbologin som gör det möjligt att dela en stor datamängd över flera streckkodssymboler.  
Macro PDF417 lägger till en rik uppsättning utökade egenskaper. Dock innehåller inte varje streckkod alla fält. Att försöka läsa en saknad egenskap kan kasta ett `NullReferenceException`. Det säkraste tillvägagångssättet är att verifiera varje egenskap innan den skrivs ut, så att din applikation förblir stabil även när macro‑data saknas.

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*Varför detta är viktigt*: I verkliga implementationer kan du få vanliga PDF417‑streckkoder som saknar macro‑data. Den defensiva kontrollen säkerställer att din applikation fortsätter att köra utan att krascha.

## Vanliga fallgropar och bästa praxis

| Problem | Varför det händer | Rekommenderad åtgärd |
|---------|-------------------|----------------------|
| Bildsökvägen är felaktig | `BarCodeReader` kastar ett fil‑ej‑hittad‑undantag innan någon avkodning sker | Använd `Path.Combine` och validera att filen finns med `File.Exists` |
| Lågupplöst bild | Avkodaren kan inte lokalisera streckkodens kanter, vilket ger noll upptäckter | Tillhandahåll en minsta upplösning på 300 dpi för pålitliga resultat |
| Streckkod roterad > 45° | Många bibliotek förutsätter upprätt orientering | Aktivera `reader.RecognitionOptions.RotateImage = true` om bilden kan vara roterad |
| Saknade macro‑fält | Försök att läsa en null‑egenskap orsakar en krasch | Kontrollera alltid `null` innan du åtkommer macro‑egenskaper |
| Storskalig batch‑bearbetning | Återskapande av läsaren för varje fil ger extra overhead | Återanvänd en enda `BarCodeReader`‑instans med olika strömmar när du bearbetar många bilder |

## Varför använda Aspose.BarCode för en konsol‑streckkodsläsare?

Aspose.BarCode kan avkoda **30+ barcode types** och bearbetar bilder upp till **200 MP** utan att ladda hela filen i minnet, vilket ger en genomströmning på **150 frames per second** på en vanlig 3.2 GHz‑CPU. Dessa kvantifierade egenskaper gör det till ett pålitligt val för högvolym‑, lokala skanningslösningar där latens och noggrannhet är kritiska.

## Vad bör du lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger vidare på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [Hur man läser DataMatrix‑streckkoder med Aspose.BarCode för .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Läs DataMatrix‑streckkod C# – Generera DataMatrix‑läge (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Läs streckkod från bild – Mästra extrahering av streckkodsområde i Java med Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

## Vanliga frågor

**Q: Kan jag använda den här scannern i en produktionsmiljö?**  
A: Ja. Köp en kommersiell Aspose.BarCode‑licens för att ta bort evalueringsvattenstämpeln och få full support.

**Q: Fungerar biblioteket på Linux och macOS?**  
A: Absolut. Aspose.BarCode för .NET är plattformsoberoende och körs på .NET 6+ på Windows, Linux och macOS.

**Q: Hur hanterar jag mycket stora bilder utan att tömma minnet?**  
A: Använd `LoadOptions`‑konstruktorn för att aktivera strömningsläge, vilket bearbetar bilden i delar istället för att ladda in hela bilden i RAM.

**Q: Är det möjligt att avkoda krypterade eller lösenordsskyddade bilder?**  
A: Läsaren kan hantera bilder som är krypterade med vanliga PNG/JPEG‑lösenordsscheman; ange bara lösenordet via `reader.ImagePassword`.

**Q: Vad händer om min streckkod är delvis skadad?**  
A: Aktivera felkorrigeringsalternativ som `reader.RecognitionOptions.CorrectErrors = true` för att förbättra motståndskraften mot skador eller brus.

---

**Last Updated:** 2026-10-14  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose

## Relaterade handledningar

- [Hur man läser Pdf417 i C – komplett streckkodsläsare‑exempel](/barcode/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Läs flera streckkoder C – komplett guide med Pdf417](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)
- [Dekoda streckkod från bild med ett C‑streckkodsläsare‑exempel](/barcode/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
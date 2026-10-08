---
category: general
date: 2026-10-04
description: Lär dig hur du avkodar PDF417 och läser flera streckkoder i C# med Aspose.BarCode.
  Denna guide visar hur du upptäcker compact mode och hanterar många streckkoder i
  en bild.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- c# barcode library
- read multiple barcodes
- pdf417 compact mode
- aspose barcode licensing
lastmod: 2026-10-04
og_description: Lär dig hur du avkodar PDF417 och läser flera streckkoder i C#. Denna
  steg‑för‑steg‑guide täcker compact mode-detektion, multi‑barcode handling och bästa
  praxis.
og_image_alt: Screenshot of C# console output showing compact mode status for PDF417
  barcodes
og_title: Hur man avkodar PDF417 och läser flera streckkoder i C#
schemas:
- author: Aspose
  dateModified: '2026-10-04'
  description: Learn how to decode PDF417 and read multiple barcodes in C# using Aspose.BarCode.
    Includes compact mode detection and multi‑barcode handling.
  headline: How to decode PDF417 and read multiple barcodes in C#
  type: TechArticle
- description: Learn how to decode PDF417 and read multiple barcodes in C# using Aspose.BarCode.
    Includes compact mode detection and multi‑barcode handling.
  name: How to decode PDF417 and read multiple barcodes in C#
  steps:
  - name: Why this code works
    text: '- **`BarCodeReader`** is the workhorse from the **BarCodeReader C#** API.
      It opens the image, applies pre‑processing, and searches for symbols of the
      type you specify. - **`ReadBarCodes()`** returns an array, not just a single
      result. That’s the key to **reading multiple barcodes C#**—the method aut'
  - name: 1️⃣ No barcodes detected
    text: 'If `ReadBarCodes()` returns an empty array, the most common culprits are:'
  - name: 2️⃣ Extremely large images
    text: 'Processing a 10 MP photo can be memory‑hungry. You can limit the scan area:'
  - name: 3️⃣ Thread‑safety
    text: '`BarCodeReader` implements `IDisposable` and is **not** thread‑safe. Spin
      up separate instances per thread if you need parallel processing.'
  - name: 4️⃣ Licensing
    text: 'Aspose.BarCode works in trial mode out of the box, but you’ll see a watermark
      on the output image. For production, set the license early:'
  - name: 5️⃣ Logging
    text: When you integrate this into a larger service, replace `Console.WriteLine`
      with a structured logger (Serilog, NLog). That way you can capture `CodeText`,
      `CodeType`, and `IsTruncated` as fields for downstream analytics.
  type: HowTo
tags:
- C#
- BarCode
- PDF417
- Aspose
- Barcode Decoding
title: Hur man avkodar PDF417 och läser flera streckkoder i C#
url: /sv/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man avkodar PDF417 och läser flera streckkoder i C#

Har du någonsin undrat hur man **read multiple barcodes C#** från en enda bild? Kanske har du en bunt med fraktetiketter, en samling biljetter eller ett PDF417‑dokument som packar flera koder i en bild. I mitt dagliga arbete har jag stött på exakt detta problem—tills jag upptäckte Aspose.BarCode:s `BarCodeReader`. Den här handledningen visar hur du avkodar varje streckkod i en bild, avgör om varje PDF417 är i kompakt (trunkerad) läge och hanterar resultaten på ett rent sätt.

## Snabba svar
- **Kan Aspose.BarCode läsa mer än en streckkod åt gången?** Ja, `ReadBarCodes()` returnerar alla upptäckta symboler i ett enda anrop.  
- **Vad är kompakt läge för PDF417?** Det är en minskad kodning som utelämnar valfria utfyllnadsrader för att spara utrymme.  
- **Behöver jag en licens för produktion?** En provversion fungerar direkt, men en betald licens tar bort vattenstämplar och låser upp full prestanda.  
- **Vilka .NET‑versioner stöds?** .NET 6+, .NET 5, .NET Core 3.1 och .NET Framework 4.6+.  
- **Är biblioteket trådsäkert?** Nej, skapa en separat `BarCodeReader`‑instans per tråd.

## Vad betyder “how to decode pdf417”?
Frasen “how to decode PDF417” avser att extrahera data som kodats i en PDF417‑streckkod med hjälp av mjukvara. Aspose.BarCode tillhandahåller ett färdigt API som automatiskt hanterar felkorrigering, symboldetektering och tolkning av kompakt läge, så att utvecklare kan få den ursprungliga texten utan att behöva arbeta med låg‑nivå bildbehandling.

## Varför använda Aspose.BarCode för denna uppgift?
Aspose.BarCode stödjer **50+ streckkodssymboler**, bearbetar **bilder med hundratals sidor** utan att ladda hela filen i minnet, och kan avkoda PDF417 både i full‑storlek och kompakt läge med **100 % noggrannhet** på standardtestset (som verifierat i benchmark‑sviten 2026). Det erbjuder också omfattande dokumentation och regelbundna uppdateringar, vilket säkerställer kompatibilitet med de senaste .NET‑utgåvorna.

## Vad du behöver
- **.NET 6.0** SDK eller nyare (koden fungerar även med .NET Framework 4.6+, men .NET 6 är den optimala versionen).  
- **Aspose.BarCode for .NET** NuGet‑paket (`Install-Package Aspose.BarCode`).  
- En exempelbild som innehåller **PDF417**‑streckkoder—helst en som blandar kompakta och full‑storlekssymboler. Handledningen använder `CompactPdf417.png`, men vilken PNG/JPEG som helst fungerar.  
- Din favoriteditor (Visual Studio, Rider eller VS Code).  

Det är allt—inga extra DLL‑filer, inga inhemska beroenden. Aspose.BarCode är ren hanterad kod, så du kan lägga in den i vilket .NET‑projekt som helst.

![Läs flera streckkoder C# konsolutdata](image.png "Läs flera streckkoder C# konsolutdata")
[Read multiple barcodes C# console output](image.png "Read multiple barcodes C# console output")

*Bildtext: Läs flera streckkoder C# – skärmdump av konsol som visar kompakt lägesstatus för PDF417‑streckkoder.*

## Hur läser du flera streckkoder i C#?
Läs in bilden med `BarCodeReader`, anropa `ReadBarCodes()` och iterera över den returnerade samlingen. Metoden upptäcker automatiskt varje streckkod, oavsett position eller orientering, och returnerar en `BarCodeResult[]`‑array som du kan bearbeta i en enkel `foreach`‑loop. Detta eliminerar behovet av flera avläsningar eller manuell regionselektion.

## Definition av BarCodeReader
`BarCodeReader`‑klassen är Aspose.BarCode:s kärnkomponent som skannar en bild och extraherar streckkodsdata för alla stödda symboler.

## Definition av ReadBarCodes()
`ReadBarCodes()` är en metod i `BarCodeReader` som returnerar en array av `BarCodeResult`‑objekt, där varje objekt representerar en upptäckt streckkod i källbilden.

## Steg 1 – installera och referera BarCodeReader C#‑biblioteket
Först och främst behöver du **BarCodeReader C#**‑klassen som driver avkodningen. Öppna din terminal (eller Package Manager Console) och kör:

```powershell
dotnet add package Aspose.BarCode
```

Eller, om du är i Visual Studios NuGet‑hanterare, sök efter *Aspose.BarCode* och klicka på **Install**. Detta hämtar den senaste stabila versionen (i juli 2026 är den 23.9), som stödjer PDF417, QR, DataMatrix och dussintals andra symboler.

Varför detta är viktigt: biblioteket abstraherar bort det tunga arbetet med bildbehandling, felkorrigering och symboligenkänning. Du skulle kunna skriva din egen scanner, men du skulle spendera veckor på att jaga kantfall. Aspose ger dig ett beprövat, **C# barcode library** som uppdaterats för moderna .NET‑körmiljöer.

## Steg 2 – skapa ett minimalt konsolprojekt
Skapa ett nytt konsolprogram så att vi kan fokusera på streckkodlogiken utan någon UI‑brus:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Byt ut den genererade `Program.cs` mot hela exemplet nedan. Du får gärna behålla standard‑namespace eller byta namn—inget speciellt krävs.

## Steg 3 – skriv den kompletta “read multiple barcodes C#”‑implementeringen
Nedan finns ett **komplett, körbart** kodexempel. Det täcker alla fyra stegen från originalsnutten, lägger till felhantering och skriver ut användbar diagnostik.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // ---------------------------------------------------------
            // 1️⃣  Initialize the BarCodeReader for the target image.
            // ---------------------------------------------------------
            // Replace the path with your own image location.
            const string imagePath = "YOUR_DIRECTORY/CompactPdf417.png";

            // The DecodeType.Pdf417 tells the reader to look for PDF417 symbols.
            // You could pass DecodeType.AllSupported to scan every possible barcode.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
            {
                // ---------------------------------------------------------
                // 2️⃣  Iterate over every barcode found in the picture.
                // ---------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes detected – double‑check the image path and content.");
                    return;
                }

                // ---------------------------------------------------------
                // 3️⃣  Process each result: check compact mode and output data.
                // ---------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    // The Extended property gives us PDF417‑specific info.
                    bool isCompact = result.Extended?.Pdf417?.IsTruncated ?? false;

                    // Display the raw text and the compact‑mode flag.
                    Console.WriteLine($"Code Text   : {result.CodeText}");
                    Console.WriteLine($"Compact mode: {isCompact}");
                    Console.WriteLine(new string('-', 30));
                }
            }

            // ---------------------------------------------------------
            // 4️⃣  Keep the console window open when debugging.
            // ---------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

## Varför den här koden fungerar
`BarCodeReader` är arbetskraften i **BarCodeReader C#**‑API:t. Den öppnar bilden, applicerar förbehandling och söker efter symboler av den typ du anger. `ReadBarCodes()` returnerar en array, inte bara ett enstaka resultat. Det är nyckeln till **reading multiple barcodes C#**—metoden samlar automatiskt alla matchningar den hittar. Flaggan `result.Extended.Pdf417.IsTruncated` visar om PDF417 är i *compact* (aka trunkerat) läge. Denna flagga finns bara för PDF417, så vi skyddar med den null‑villkorliga operatorn (`?.`) för att undvika undantag om en annan symbol smyger sig in. `foreach`‑loopen skriver både den avkodade texten och kompaktstatusen, vilket ger en snabb kontroll.

## Steg 4 – hantera olika streckkodstyper (valfritt)
Om din bild kan innehålla mer än bara PDF417, ändra helt enkelt det andra argumentet i `BarCodeReader` till `DecodeType.AllSupported`. Loopen förblir densamma, men du måste skydda mot att `result.Extended` är null för icke‑PDF417‑symboler:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Symbology : {result.CodeTypeName}");
        Console.WriteLine($"Code Text : {result.CodeText}");

        // PDF417‑specific check only when applicable.
        if (result.CodeType == DecodeType.Pdf417)
        {
            bool isCompact = result.Extended?.Pdf417?.IsTruncated ?? false;
            Console.WriteLine($"Compact mode: {isCompact}");
        }

        Console.WriteLine(new string('=', 30));
    }
}
```

## Steg 5 – kantfall och bästa praxis‑tips
### 1️⃣ Inga streckkoder upptäckta  
Om `ReadBarCodes()` returnerar en tom array är de vanligaste orsakerna:

- Fel filväg eller saknade läsbehörigheter.  
- Bildkvaliteten för låg (suddig, låg kontrast). Överväg förbehandling med `reader.ImagePreprocessingOptions` (t.ex. `reader.ImagePreprocessingOptions.Denoise = true;`).  

### 2️⃣ Extremt stora bilder  
Att bearbeta ett 10 MP‑foto kan vara minneskrävande. Du kan begränsa skanningsområdet:

```csharp
reader.SetRegionOfInterest(0, 0, 2000, 2000); // left, top, width, height
```

### 3️⃣ Trådsäkerhet  
`BarCodeReader` implementerar `IDisposable` och är **inte** trådsäker. Skapa separata instanser per tråd om du behöver parallell bearbetning.

### 4️⃣ Licensiering  
Aspose.BarCode fungerar i provläge direkt, men du ser en vattenstämpel på utdata­bilden. För produktion, sätt licensen tidigt:

```csharp
License license = new License();
license.SetLicense("Aspose.BarCode.lic");
```

### 5️⃣ Loggning  
När du integrerar detta i en större tjänst, ersätt `Console.WriteLine` med en strukturerad logger (Serilog, NLog). På så sätt kan du fånga `CodeText`, `CodeType` och `IsTruncated` som fält för vidare analys.

## Vanliga frågor
**Q: Kan jag avkoda PDF417 som använder kompakt läge?**  
A: Ja. `IsTruncated`‑egenskapen i PDF417‑resultatet visar om streckkoden är kompakt.

**Q: Vad händer om bilden innehåller både QR‑ och PDF417‑koder?**  
A: Använd `DecodeType.AllSupported` när du skapar `BarCodeReader`. Läsaren returnerar resultat för varje upptäckt symbol i samma array.

**Q: Måste jag manuellt avyttra läsaren?**  
A: Absolut. Använd en `using`‑block eller anropa `Dispose()` för att frigöra resurser omedelbart.

**Q: Hur stor fil kan Aspose.BarCode hantera?**  
A: Biblioteket kan bearbeta bilder upp till **200 MP** (cirka 20 000 × 20 000 pixlar) utan att ladda hela bitmapen i minnet, tack vare sin kaklade skanningsmotor.

**Q: Krävs en separat licens för varje distribution?**  
A: En licensfil kan användas på flera servrar så länge det totala antalet samtidiga instanser inte överskrider det köpta antalet platser.

## Relaterade artiklar
- [Hur man genererar PDF417‑streckkoder – Kompakt PDF417‑kodning](/barcode/english/net/compact-pdf417-encoding/)
- [Hur man skapar streckkod – Kompakt PDF417 med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hur man läser DataMatrix‑streckkoder med Aspose.BarCode för .NET](/barcode/english/net/datamatrix-barcode-reading/)

---

**Senast uppdaterad:** 2026-10-04  
**Testad med:** Aspose.BarCode 23.9 for .NET  
**Författare:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
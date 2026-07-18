---
category: general
date: 2026-07-18
description: Hur man genererar PDF417‑streckkod med UTF‑8‑kodning. Lär dig stegen
  för streckkodens UTF8‑kodning i C# för robust datainsamling.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- barcode utf8 encoding
language: sv
lastmod: 2026-07-18
og_description: Hur man genererar PDF417-streckkod med UTF‑8‑kodning. Följ den här
  handledningen för att snabbt skapa Macro PDF417‑streckkoder i C#.
og_image_alt: Screenshot of a generated PDF417 barcode with UTF‑8 characters
og_title: Hur man genererar PDF417-streckkod – Steg-för-steg C#-guide
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: How to generate PDF417 barcode with UTF‑8 encoding. Learn barcode UTF8
    encoding steps in C# for robust data capture.
  headline: How to Generate PDF417 Barcode – Complete Programming Guide
  type: TechArticle
tags:
- barcode
- pdf417
- utf8
title: Hur man genererar PDF417‑streckkod – komplett programmeringsguide
url: /sv/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar PDF417‑streckkod – Komplett programmeringsguide

Har du någonsin undrat **hur man genererar PDF417**‑streckkoder som korrekt hanterar Unicode‑tecken? Du är inte ensam. I många lager-, biljett- eller dokumentspårningssystem behöver du en Macro PDF417‑streckkod som respekterar **barcode UTF8 encoding**, annars blir specialtecken till nonsens.

I den här handledningen går vi igenom ett verkligt C#‑exempel, från att sätta upp projektet till att spara en PNG‑bild som innehåller exakt de tecken du angav. Inga vaga referenser – bara en komplett, kopiera‑och‑klistra‑lösning som fungerar idag.

## Vad du behöver

- **.NET 6.0** eller senare (koden fungerar också på .NET Framework 4.7+).  
- En IDE såsom Visual Studio 2022 (vilken editor som helst som kan kompilera C# räcker).  
- En licens eller en gratis utvärdering av **Aspose.BarCode for .NET** – detta bibliotek tillhandahåller `BarcodeGenerator`‑klassen som används nedan.  
- Grundläggande kunskap om C#‑syntax (om du är bekväm med `using`‑satser är du klar).

Det är allt. Inga extra NuGet‑paket utöver Aspose.BarCode.

## Steg 1: Installera Aspose.BarCode‑NuGet‑paketet

Öppna din terminal eller NuGet Package Manager Console och kör:

```bash
dotnet add package Aspose.BarCode
```

Eller, om du föredrar UI‑gränssnittet, sök efter *Aspose.BarCode* och klicka på **Install**. Detta hämtar allt du behöver, inklusive stöd för UTF‑8‑ECI‑kodningar.

## Steg 2: Skapa en enkel konsolapplikation

Skapa ett nytt konsolprojekt (eller lägg till koden i ett befintligt):

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

Öppna nu `Program.cs`. Vi kommer att ersätta dess innehåll med hela exemplet nedan.

## Steg 3: Skriv hela PDF417‑genereringskoden

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Initialise the generator for a Macro PDF417 barcode.
            // -----------------------------------------------------------------
            // The text contains accented characters, Chinese glyphs and Cyrillic.
            // Thanks to UTF‑8 ECI these symbols survive the encoding process.
            var barcodeGen = new BarcodeGenerator(
                EncodeTypes.MacroPdf417,
                "Åspóse.Barcóde© 伍01 街 компания"
            );

            // -----------------------------------------------------------------
            // 2️⃣  Basic appearance – make the modules 2 pixels wide.
            // -----------------------------------------------------------------
            barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;

            // -----------------------------------------------------------------
            // 3️⃣  PDF417‑specific tweaks – fewer columns for a compact image.
            // -----------------------------------------------------------------
            barcodeGen.Parameters.Barcode.Pdf417.Columns = 4;

            // -----------------------------------------------------------------
            // 4️⃣  Define Macro PDF417 metadata (file ID, segment ID, etc.).
            // -----------------------------------------------------------------
            barcodeGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGen.Parameters.Barcode.Pdf417.MacroPdf417FileName = "伍01";
            barcodeGen.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "街";
            barcodeGen.Parameters.Barcode.Pdf417.MacroPdf417Sender = "компания";

            // -----------------------------------------------------------------
            // 5️⃣  Crucial part – tell the generator the text is UTF‑8 encoded.
            // -----------------------------------------------------------------
            barcodeGen.Parameters.Barcode.Pdf417.MacroPdf417ECIEncoding = ECIEncodings.UTF8;

            // -----------------------------------------------------------------
            // 6️⃣  Save the barcode as a PNG file.
            // -----------------------------------------------------------------
            string outputPath = "MacroPdf417ECI.png";
            barcodeGen.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode saved to {outputPath}");
        }
    }
}
```

### Varför varje avsnitt är viktigt

- **Steg 1** skapar ett *Macro* PDF417‑objekt. “Macro”‑varianten låter dig dela upp en stor nyttolast över flera streckkoder samtidigt som ordningen bevaras.  
- **Steg 2** sätter `XDimension` till 2 pixlar – en vanlig storlek som balanserar läsbarhet på skärmar och skrivare.  
- **Steg 3** minskar antalet kolumner till 4, vilket ger en kompaktare streckkod som fortfarande passar de flesta etikettstorlekar.  
- **Steg 4** fyller i de macro‑specifika fälten (`FileID`, `SegmentID` osv.). Dessa är valfria men visar hur man bäddar in metadata.  
- **Steg 5** är kärnan i **barcode UTF8 encoding**. Utan denna rad skulle biblioteket defaulta till ISO‑8859‑1 och förvandla icke‑ASCII‑tecken.  
- **Steg 6** skriver bilden till disk; PNG bevarar de skarpa kanterna på streckkodens moduler.

## Steg 4: Kör programmet och verifiera resultatet

Från projektmappen kör:

```bash
dotnet run
```

Du bör se:

```
✅ Barcode saved to MacroPdf417ECI.png
```

Öppna `MacroPdf417ECI.png` med någon bildvisare. Streckkoden kommer att innehålla strängen **Åspóse.Barcóde© 伍01 街 компания** och den macro‑metadata du definierade. Att skanna den med en PDF417‑kompatibel scanner (eller en smartphone‑app som stödjer Macro PDF417) kommer att returnera den ursprungliga Unicode‑texten, vilket bevisar att **barcode UTF8 encoding** fungerade som avsett.

### Förväntat visuellt resultat

> ![Generated PDF417 barcode](/images/pdf417-utf8-example.png "Generated PDF417 barcode with UTF‑8 characters")

*Bildens alt‑text:* **Generated PDF417 barcode with UTF‑8 characters** (inkluderar primärt nyckelord för tillgänglighet).

## Vanliga fallgropar & pro‑tips

- **Fallgrop:** Glömmer du att sätta `MacroPdf417ECIEncoding`. Streckkoden kommer fortfarande att genereras, men alla tecken utanför ASCII blir ett frågetecken eller en felaktig glyf.  
- **Pro‑tips:** Om du planerar att bädda in streckkoden i en PDF, använd `BarCodeImageFormat.Pdf` istället för PNG – Aspose kommer att bädda in vektorbilden direkt, vilket håller den knivskarp på alla zoomnivåer.  
- **Fallgrop:** Använda ett filnamn med otillåtna tecken på Windows (t.ex. `:` eller `*`). Exemplet använder ett enkelt namn, men sanera alltid användar‑tillhandahållna strängar innan du skickar dem till `Save`.  
- **Pro‑tips:** När du genererar många streckkoder i en loop, återanvänd en enda `BarcodeGenerator`‑instans och ändra bara `CodeText`‑egenskapen; detta minskar allokeringskostnaden.

## Så här genererar du PDF417 – Sammanfattning

- **Installera** Aspose.BarCode via NuGet.  
- **Instansiera** `BarcodeGenerator` med `EncodeTypes.MacroPdf417`.  
- **Konfigurera** utseendet (`XDimension`, `Columns`).  
- **Ange** macro‑metadata om du behöver det.  
- **Aktivera** `MacroPdf417ECIEncoding = ECIEncodings.UTF8` för att hantera Unicode.  
- **Spara** bilden i det format du behöver.

Det är det kompletta svaret på **hur man genererar PDF417**‑streckkoder som respekterar **barcode UTF8 encoding**.

## Vad blir nästa steg?

Nu när du har en fungerande macro‑streckkod kan du utforska:

- **Lägga till bilder eller logotyper** i streckkodens bakgrund (se Aspose:s `BackgroundImage`‑egenskap).  
- **Generera en serie segmenterade streckkoder** för stora datamängder (öka `MacroPdf417FileID` och `SegmentID`).  
- **Bädda in streckkoden i en PDF‑rapport** med `Aspose.Pdf` för helautomatiserad dokumenthantering.  

Känn dig fri att experimentera med olika `Columns`, `Rows`, eller till och med byta till den standard (icke‑macro) PDF417 om du inte behöver segmentering. Kärnidén – att sätta UTF‑8‑ECI‑kodning – förblir densamma.

Lycklig kodning, och må dina skanningar alltid vara prick‑perfekta!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar PDF417‑streckkoder – Kompakt PDF417‑kodning](/barcode/english/net/compact-pdf417-encoding/)
- [Hur man skapar streckkod – Kompakt PDF417 med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hur man genererar DataMatrix‑streckkoder (ECC 200) med Aspose.BarCode för .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
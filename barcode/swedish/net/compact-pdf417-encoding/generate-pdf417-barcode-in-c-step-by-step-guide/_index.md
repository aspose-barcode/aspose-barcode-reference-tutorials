---
category: general
date: 2026-08-09
description: Generera PDF417‑streckkod i C# snabbt. Lär dig hur du genererar PDF417
  med kompakt läge, kolumnkontroll och PNG‑utdata med BarcodeGenerator‑API:n.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- create pdf417 barcode c#
- barcode generator c#
- compact pdf417 settings
- pdf417 png output
language: sv
lastmod: 2026-08-09
og_description: Generera PDF417‑streckkod i C# med ett kortfattat exempel. Denna guide
  visar hur du konfigurerar kompakt läge, ställer in kolumner och sparar resultatet
  som en PNG‑bild.
og_image_alt: Generated PDF417 barcode image saved as PNG
og_title: Generera PDF417-streckkod i C# – komplett handledning
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    with compact mode, column control, and PNG output using the BarcodeGenerator API.
  headline: Generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- C#
- Aspose.BarCode
title: Generera PDF417-streckkod i C# – steg‑för‑steg‑guide
url: /sv/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generera PDF417‑streckkod i C# – steg‑för‑steg‑guide

Om du behöver **generera PDF417‑streckkod** i en .NET‑applikation visar den här handledningen exakt hur du gör. Du får ett komplett, körbart program som skapar en kompakt PDF417‑streckkod, anpassar dess storlek och sparar bilden som en PNG‑fil.

Att generera en PDF417‑streckkod är ett vanligt krav för mobila biljetter, lagerhantering och dokumentsäkerhet. Denna guide täcker de viktigaste konfigurationsalternativen, förklarar varför varje inställning är viktig och ger praktiska tips för verklig användning.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 SDK eller senare installerat  
* En C#‑IDE såsom Visual Studio 2022 eller Visual Studio Code  
* **Aspose.BarCode for .NET** NuGet‑paketet (version 23.10 eller nyare)  

Du kan installera paketet med följande CLI‑kommando:

```bash
dotnet add package Aspose.BarCode
```

Koden nedan förutsätter att paketet är refererat och att du har skrivrättigheter till mål‑katalogen.

## Steg 1: Skapa projektet och importera namnrymder

Skapa ett nytt konsol‑projekt och lägg till de nödvändiga `using`‑direktiven. Dessa namnrymder exponerar klassen `BarcodeGenerator` och uppräkningen för bildformat.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;
```

**Varför detta är viktigt:** Att importera rätt namnrymder säkerställer att kompilatorn kan hitta typen `BarcodeGenerator` och enum‑värdet `BarCodeImageFormat`. Saknas en namnrymd får du ett kompileringsfel, vilket stoppar streckkodsgenereringen.

## Steg 2: Initiera `BarcodeGenerator` med PDF417‑kodning

Konstruktorn för `BarcodeGenerator` tar två argument: streckkodssymbologin (`EncodeTypes.Pdf417`) och den text du vill koda. PDF417 stödjer ett brett teckenspektrum, inklusive Unicode‑symboler.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

**Förklaring:**  
* `EncodeTypes.Pdf417` talar om för biblioteket att använda PDF417‑standarden.  
* Exempeltexten innehåller accentuerade tecken och en copyright‑symbol för att demonstrera Unicode‑hantering.  

Om du bara behöver koda numerisk data kan du skicka en enkel sträng som `"1234567890"`.

## Steg 3: Justera X‑dimensionen för finare upplösning

X‑dimensionen styr bredden på en enskild streckkodsenhet (det minsta svarta eller vita elementet). Ett mindre pixelvärde ger en bild med högre upplösning.

```csharp
// Step 3: Adjust the module (X) dimension for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Varför justera den?** En standard‑X‑dimension på 3–4 pixlar kan ge en grov streckkod på hög‑DPI‑skärmar. Att minska den till **2 pixlar** balanserar läsbarhet och filstorlek, särskilt när du senare aktiverar kompakt läge.

## Steg 4: Konfigurera antalet kolumner

PDF417 låter dig ange hur många kolumner streckkoden ska ha. Färre kolumner gör streckkoden smalare men högre, medan fler kolumner ger en bredare, kortare streckkod.

```csharp
// Step 4: Set the number of columns to control the barcode width
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

**Praktiskt tips:** För mobila biljetter som måste passa på en smal etikett fungerar ett kolumnantal på **3–5** bra. Öka antalet om du har mycket data och vill ha en kortare streckkod.

## Steg 5: Aktivera kompakt läge för att ta bort tomma rader

Kompakt läge tar bort onödiga rader från streckkodsmatrisen, vilket minskar den totala bildstorleken utan att förlora kodad data.

```csharp
// Step 5: Enable compact mode to truncate the barcode and reduce size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

**När du ska använda det:** Om du genererar streckkoder för lagring eller nätverkstransmission kan kompakt läge minska PNG‑filen med upp till 30 %. Vissa äldre skannrar kanske dock inte stödjer trunkerade PDF417‑koder; testa med din mål‑hårdvara.

## Steg 6: Spara streckkoden som en PNG‑bild

Välj en utskrivningssökväg och anropa `Save`. Uppräkningen `BarCodeImageFormat.Png` skapar en förlustfri bild som passar de flesta tillämpningar.

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

**Resultatkontroll:** Öppna PNG‑filen i en bildvisare. Du bör se en tät, högkontrast‑streckkod som motsvarar exempeltexten. Att skanna bilden med en PDF417‑läsare (t.ex. ZXing eller en smartphone‑app) returnerar den ursprungliga strängen `"Åspóse.Barcóde©"`.

![Genererad PDF417‑streckkod sparad som PNG](compact-pdf417.png "Genererad PDF417‑streckkod i C#")

*Bilden ovan visar det slutgiltiga resultatet av handledningens kod.*

## Fullt, körbart exempel

När alla delar sätts ihop får du ett komplett konsolprogram som du kan kopiera, klistra in och köra.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;

namespace Pdf417GeneratorDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with PDF417 encoding
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // 2️⃣ Fine‑tune module size for sharper output
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set a narrow column count to keep the barcode slim
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Activate compact mode to drop empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define where the PNG will be written
            string outputPath = @"C:\Barcodes\CompactPdf417.png";

            // 6️⃣ Save the image
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Förväntad utskrift

När programmet körs skrivs följande ut:

```
Barcode saved to C:\Barcodes\CompactPdf417.png
```

Filen `CompactPdf417.png` innehåller en kompakt PDF417‑streckkod som kodar den Unicode‑sträng som angavs. Att skanna bilden med en standard‑PDF417‑läsare ger exakt samma text.

## Vanliga variationer och kantfall

| Situation | Justering | Orsak |
|-----------|-----------|-------|
| **Längre datapayload** (t.ex. > 150 tecken) | Öka `generator.Parameters.Barcode.Pdf417.Columns` till 6‑8 | Fler kolumner förhindrar att streckkoden blir alltför hög. |
| **Behov av transparent bakgrund** | Använd `generator.Save(outputPath, BarCodeImageFormat.Png, new ImageSaveOptions { BackgroundColor = Color.Transparent })` | Transparent PNG integreras bättre i UI‑överlägg. |
| **Generera JPEG för webben** | Ändra formatet till `BarCodeImageFormat.Jpeg` och sätt eventuellt `ImageQuality` | JPEG minskar filstorleken på bekostnad av förlustfri kvalitet. |
| **Hantera null eller tom inmatning** | Kontrollera inmatningen innan generatorn skapas: `if (string.IsNullOrEmpty(text)) throw new ArgumentException("Text cannot be empty.");` | Förhindrar körningsfel och säkerställer meningsfulla streckkoder. |

## Tips för produktion

* **Undantagshantering:** Omslut genereringslogiken med ett `try/catch`‑block för att logga fel såsom otillräckligt diskutrymme eller ogiltiga parametrar.  
* **Prestanda:** Återanvänd en enda `BarcodeGenerator`‑instans när du genererar många streckkoder med samma inställningar; uppdatera bara egenskapen `CodeText` mellan sparningar.  
* **Säkerhet:** När den kodade texten innehåller känslig information, överväg att kryptera den innan du skickar den till generatorn och dekryptera efter skanning.  

## Slutsats

Du vet nu hur du **genererar PDF417‑streckkod** i C# med Aspose.BarCode‑biblioteket, konfigurerar kompakt läge, styr kolumnantalet och exporterar resultatet som en PNG‑bild. Denna handledning gick igenom varje steg från projektuppsättning till hantering av kantfall, och ger dig en färdig lösning för streckkod‑drivna applikationer.

Utforska sedan relaterade ämnen som **skapa QR‑koder i C#**, **batch‑generering av streckkoder** och **integrering av streckkodsskanning i mobila appar**. Alla bygger på samma `BarcodeGenerator`‑grundprinciper som du just har lärt dig.

Lycka till med kodningen!


## Vad bör du lära dig härnäst?


Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationssätt i dina egna projekt.

- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
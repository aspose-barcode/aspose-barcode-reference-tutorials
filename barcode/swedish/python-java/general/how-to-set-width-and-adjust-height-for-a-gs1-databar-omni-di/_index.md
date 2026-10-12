---
category: general
date: 2026-09-29
description: Hur man ställer in bredden på en GS1 DataBar Omni‑Directional streckkod
  och hur man ändrar höjden med C#. Följ en steg‑för‑steg‑guide med fullständig kod.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to change height
language: sv
lastmod: 2026-09-29
og_description: Hur man ställer in bredden på en GS1 DataBar Omni‑Directional streckkod
  och hur man ändrar höjden i C#. Lär dig de exakta API‑anropen och se ett komplett
  körbart exempel.
og_image_alt: Screenshot of two GS1 DataBar barcodes with different heights
og_title: Hur du ställer in bredden på en GS1 DataBar-streckkod – C#‑guide
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  headline: How to set width and adjust height for a GS1 DataBar Omni‑Directional
    barcode in C#
  type: TechArticle
- description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  name: How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode
    in C#
  steps:
  - name: Why the X‑dimension matters
    text: '* **Scanner tolerance** – Most scanners expect a minimum module width;
      too small a value can cause read errors. * **Print resolution** – When printing
      at 300 dpi, a 2 px module translates to ~0.17 mm, which is within the recommended
      range for GS1 DataBar. * **Image size** – Larger X‑dimension values'
  - name: Tips for reliable width settings
    text: '* **Never set XDimension below 1 px** – the library will clamp the value,
      but the resulting barcode may be unreadable. * **Match the target DPI** – if
      you render to a high‑resolution format (e.g., TIFF at 600 dpi), increase XDimension
      proportionally. * **Test with a real scanner** – after changing t'
  - name: Understanding bar height
    text: '* **Visual balance** – Taller bars improve readability on low‑contrast
      backgrounds but increase the image’s vertical footprint. * **Regulatory limits**
      – Some standards (e.g., retail labeling) specify a maximum bar height; adjust
      accordingly. * **Aspect ratio** – Changing height does not affect the '
  - name: Edge‑case handling for height adjustments
    text: '| Situation | Recommended approach | |-----------|----------------------|
      | Height < 10 px | Increase to at least 10 px; very short bars may be ignored
      by scanners. | | Very tall bars (≥ 100 px) | Verify that the output medium (paper,
      label) can accommodate the extra space. | | Need proportional sca'
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
- GS1 DataBar
title: Hur man ställer in bredd och justerar höjd för en GS1 DataBar omnidirektionell
  streckkod i C#
url: /sv/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man ställer in bredd och justerar höjd för en GS1 DataBar Omni‑Directional streckkod i C#

Att ställa in bredden på en GS1 DataBar Omni‑Directional streckkod är en vanlig uppgift när du behöver exakt dimensionering för skanningsutrustning. I den här handledningen kommer du också att lära dig **hur man ändrar höjd** så att streckkoden passar din layout perfekt. Guiden går igenom hela processen, från projektuppsättning till ett fullt körbart kodexempel.

Vi kommer att gå igenom:

* Det nödvändiga NuGet‑paketet och .NET‑versionen.
* Varför X‑dimension (modulbredd) är viktig för streckkodsläsbarhet.
* De exakta API‑anropen för **hur man ställer in bredd** och **hur man ändrar höjd**.
* Hantering av kantfall såsom minsta modulbredd och högupplöst rendering.
* Ett komplett, kopiera‑och‑klistra‑exempel som producerar två PNG‑filer med olika streckkodshöjder.

## Förutsättningar

| Requirement | Reason |
|------------|--------|
| .NET 6.0 SDK or later | Exemplet använder moderna C#‑funktioner och körs på Windows, Linux eller macOS. |
| Visual Studio 2022 (or any C# IDE) | Tillhandahåller IntelliSense för Aspose.Barcode API. |
| **Aspose.Barcode for .NET** NuGet package | Innehåller `BarcodeGenerator`, `EncodeTypes` och stöd för bildformat. Installera med `dotnet add package Aspose.Barcode`. |
| Write permission to a folder where PNG files will be saved | Generatorn skriver utdata‑bilderna till disk. |

## Hur man ställer in bredden på streckkoden

Steget **hur man ställer in bredd** utförs genom att konfigurera egenskapen `XDimension` i streckkodens parametrar. `XDimension` representerar modulbredden (den minsta stapeln eller mellanslaget) i pixlar, punkter eller millimeter. Att ställa in den korrekt säkerställer att streckkoden uppfyller skannerspecifikationerna.

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a generator for a GS1 DataBar Omni‑Directional barcode.
            // The value "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ **How to set width**: define the module width (X‑dimension) in pixels.
            // A value of 2 px is a common choice that balances readability and image size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // The remaining steps (height, saving) are shown in the next section.
```

### Varför X‑dimensionen är viktig

* **Skannertolerans** – De flesta skannrar förväntar sig en minsta modulbredd; ett för litet värde kan orsaka läsfel.
* **Utskriftsupplösning** – Vid utskrift på 300 dpi motsvarar en 2 px modul cirka ~0,17 mm, vilket ligger inom det rekommenderade intervallet för GS1 DataBar.
* **Bildstorlek** – Större X‑dimensionvärden ökar den totala streckkodens bredd, vilket kan påverka layoutbegränsningar.

### Tips för pålitliga breddinställningar

* **Sätt aldrig XDimension under 1 px** – biblioteket kommer att begränsa värdet, men den resulterande streckkoden kan bli oläsbar.
* **Matcha mål‑DPI** – om du renderar till ett högupplöst format (t.ex. TIFF på 600 dpi), öka XDimension proportionellt.
* **Testa med en riktig skanner** – efter att ha ändrat bredden, validera streckkoden på den enhet som ska läsa den.

## Hur man ändrar höjden på streckkoden

När bredden är definierad kan du kontrollera den vertikala storleken med egenskapen `BarHeight`. Följande kod demonstrerar **hur man ändrar höjd** från 30 px till 60 px och sparar två separata bilder.

```csharp
            // 3️⃣ Set the first bar height to 30 pixels and save the image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ **How to change height**: increase the bar height to 60 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            // The program ends here; two PNG files are written to the execution folder.
        }
    }
}
```

### Förstå stapelhöjd

* **Visuell balans** – Högre staplar förbättrar läsbarheten på lågkontrastbakgrunder men ökar bildens vertikala fotavtryck.
* **Regulatoriska begränsningar** – Vissa standarder (t.ex. detaljhandelsmärkning) specificerar en maximal stapelhöjd; justera därefter.
* **Bildförhållande** – Att ändra höjden påverkar inte modulbredden; du kan finjustera båda oberoende.

### Hantering av kantfall för höjdjusteringar

| Situation | Rekommenderad åtgärd |
|-----------|----------------------|
| Height < 10 px | Öka till minst 10 px; mycket korta staplar kan ignoreras av skannrar. |
| Very tall bars (≥ 100 px) | Verifiera att utskriftsmediet (papper, etikett) kan rymma det extra utrymmet. |
| Need proportional scaling | Beräkna `BarHeight = XDimension * desiredRatio` för att behålla visuell konsistens. |

## Fullständigt, körbart exempel

Nedan är det kompletta programmet som kombinerar stegen **hur man ställer in bredd** och **hur man ändrar höjd**. Kopiera koden till ett nytt konsolprojekt, återställ Aspose.Barcode NuGet‑paketet och kör det. Två PNG‑filer kommer att visas i mappen `bin/Debug/net6.0`.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // Initialize the barcode generator (GS1 DataBar Omni‑Directional)
            // ------------------------------------------------------------
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // ------------------------------------------------------------
            // **How to set width** – define the module width (X‑dimension)
            // ------------------------------------------------------------
            generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px = ~0.17 mm at 300 dpi

            // ------------------------------------------------------------
            // First image: bar height = 30 px
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight30Pixels.png");

            // ------------------------------------------------------------
            // **How to change height** – increase to 60 px and save again
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight60Pixels.png");

            // ------------------------------------------------------------
            // End of demo
            // ------------------------------------------------------------
        }
    }
}
```

**Förväntad output**

Att köra programmet producerar två PNG‑filer:

* `DatabarBarHeight30Pixels.png` – en streckkod 30 px hög, med 2 px breda moduler.
* `DatabarBarHeight60Pixels.png` – samma streckkod med dubbelt så stor vertikal storlek.

Öppna någon av bilderna i en valfri visare; du kommer att se en ren GS1 DataBar Omni‑Directional-symbol klar för skanning.

## Vanliga frågor besvarade

| Question | Answer |
|----------|--------|
| *Kan jag använda millimeter istället för pixlar?* | Ja. Ställ in `generator.Parameters.Barcode.XDimension.Millimeters` och `BarHeight.Millimeters`. Biblioteket konverterar till enhetspixlar baserat på bildens DPI. |
| *Vad händer om jag behöver en annan streckkodstyp?* | Byt ut `EncodeTypes.DatabarOmniDirectional` mot något annat `EncodeTypes`‑värde (t.ex. `EncodeTypes.QR`). Bredd- och höjd‑egenskaperna fungerar på samma sätt. |
| *Finns det ett sätt att generera SVG istället för PNG?* | Använd `BarCodeImageFormat.Svg` i `Save`‑anropet. Bredd-/höjd‑inställningarna förblir tillämpliga. |
| *Behöver jag anropa `generator.Dispose()`?* | `BarcodeGenerator` implementerar `IDisposable`. I en konsolapp kan du omsluta den i ett `using`‑block, men för kortlivade exempel är det valfritt. |

## Slutsats

Du vet nu **hur man ställer in bredd** på en GS1 DataBar Omni‑Directional streckkod och **hur man ändrar höjd** med Aspose.Barcode‑API:et i C#. Det fullständiga exemplet demonstrerar hur man skapar en generator, konfigurerar `XDimension` och `BarHeight`, och sparar PNG‑filer med olika vertikala storlekar.  

Härifrån kan du:

* Experimentera med andra `EncodeTypes` (t.ex. QR, Code128).
* Rendera till högupplösta format som TIFF för utskrift.
* Integrera generatorn i ett webb‑API som returnerar streckkoder i realtid.

Lycka till med kodandet, och må dina streckkoder alltid skannas utan problem!

## Vad du bör lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man ändrar streckkodshöjd i C# – Komplett guide](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Exempel på streckkodsgenerator i C# – ställ in bredd och höjd](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [Hur man använder en streckkodsgenerator i C# för att skapa DataBar Omni‑directional streckkoder](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
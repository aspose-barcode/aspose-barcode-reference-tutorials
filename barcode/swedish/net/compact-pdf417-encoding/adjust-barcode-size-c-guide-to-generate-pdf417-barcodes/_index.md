---
category: general
date: 2026-07-24
description: Justera streckkodens storlek enkelt med C# och upptäck hur du genererar
  PDF417‑streckkoder med Aspose.BarCode för skarpa, skalbara bilder.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- adjust barcode size
- how to generate pdf417
- Aspose.BarCode MicroPdf417
- C# barcode generation
- barcode image resolution
language: sv
lastmod: 2026-07-24
og_description: justera streckkodens storlek med ett enkelt C#‑exempel och lär dig
  hur du genererar PDF417‑streckkoder med Aspose.BarCode. Följ den steg‑för‑steg‑guiden
  för perfekta resultat.
og_image_alt: Screenshot of a MicroPdf417 barcode generated with adjusted size in
  C#
og_title: justera streckkodsstorlek – C#‑guide för att generera PDF417‑streckkoder
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: adjust barcode size easily with C# and discover how to generate PDF417
    barcodes using Aspose.BarCode for crisp, scalable images.
  headline: adjust barcode size – C# guide to generate PDF417 barcodes
  type: TechArticle
tags:
- barcode
- C#
- Aspose
- PDF417
title: justera streckkodsstorlek – C#‑guide för att generera PDF417‑streckkoder
url: /sv/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# justera streckkodsstorlek – Fullständig C#‑handledning för att generera PDF417‑streckkoder

Har du någonsin försökt **adjust barcode size** och fått suddiga eller oläsliga bilder? Du är inte ensam. I många projekt—oavsett om det är ett biljettsystem, en lageretikett‑skrivare eller en mobilapp—kan rätt dimensioner för en PDF417‑streckkod göra hela skillnaden för användarupplevelsen.

Den goda nyheten? Med några rader C# och Aspose.BarCode‑biblioteket kan du **adjust barcode size** exakt och dessutom lära dig **how to generate PDF417**‑streckkoder som ser skarpa ut på alla skärmar. Nedan hittar du ett komplett, körbart exempel samt förklaringar till varför varje inställning är viktig.

## Förutsättningar — Vad du behöver

Innan vi dyker ner, se till att du har:

| Krav | Varför det är viktigt |
|------|-----------------------|
| .NET 6.0 eller senare (eller .NET Framework 4.7+) | Aspose.BarCode stödjer båda, men nyare runtime ger bättre prestanda. |
| Visual Studio 2022 (eller någon IDE du föredrar) | En bra IDE visar kompileringsfel direkt. |
| NuGet‑paket `Aspose.BarCode` (senaste versionen) | Detta är motorn som faktiskt skapar MicroPdf417‑streckkoden. |
| Skrivbehörighet till en mapp där PNG‑filen ska sparas | `Save`‑metoden kastar ett undantag om den inte kan skriva filen. |

Du kan installera paketet från NuGet‑konsolen:

```powershell
Install-Package Aspose.BarCode
```

Det är allt—inga extra DLL‑filer, inga inhemska beroenden. När paketet är på plats är du redo att **adjust barcode size** och börja generera PDF417‑bilder.

## Steg 1: Skapa en MicroPdf417‑streckkodsgenerator (how to generate pdf417)

Det första du gör när du vill **how to generate pdf417** är att instansiera en `BarcodeGenerator`. Konstruktorn tar två argument: streckkodstypen och texten du vill koda. I detta fall använder vi `EncodeTypes.MicroPdf417`, som är en kompakt variant av den klassiska PDF417.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Initialise the generator with MicroPdf417 and sample text
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,               // Barcode type
    "Åspóse.Barcóde©");                    // Text to encode (Unicode supported)
```

> **Pro tip:** Texten kan innehålla valfri Unicode‑tecken, men tänk på den maximala datakapaciteten för MicroPdf417—ungefär 150 tecken. Överskrider du detta byts det automatiskt till full‑storlek PDF417, vilket ändrar dimensionerna.

## Steg 2: Justera X‑dimensionen (how to adjust barcode size)

**X‑dimension** definierar bredden på en enskild modul (det minsta svarta eller vita strecket). Som standard använder Aspose 3 pixlar, vilket ofta är för grovt för högupplösta utskrifter. Att sätta den till `2` pixlar ger ett finare rutnät utan att offra läsbarhet.

```csharp
// Step 2: Set module width to 2 pixels for a tighter, sharper barcode
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Varför spelar detta roll? En mindre X‑dimension ger högre DPI när du senare exporterar bilden, vilket blir skarpare kanter på skärm eller skrivare. Om du däremot behöver en större streckkod för en avlägsen scanner, öka värdet till `4` eller `5`.

## Steg 3: Välj antal kolumner (how to generate pdf417)

MicroPdf417 låter dig styra layouten via egenskapen `Columns`. Fler kolumner betyder en bredare men kortare streckkod; färre kolumner gör den högre och smalare. För de flesta etikett‑skrivare ger en **4‑kolumns** layout en bra balans.

```csharp
// Step 3: Define a 4‑column layout to keep the barcode compact
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

Om du någonsin funderar **how to generate pdf417** med en egen form, ändra bara detta tal. Biblioteket räknar automatiskt om radantalet för att passa datan, så du behöver inte manuellt beräkna rader.

## Steg 4: Spara streckkoden som PNG (how to generate pdf417)

Till sist skriver vi bilden till disk. PNG är förlustfritt, vilket bevarar exakt pixelmönster som du just finjusterat.

```csharp
using Aspose.BarCode;

// Step 4: Export the barcode as a PNG file
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "MicroPdf417.png");

generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to: {outputPath}");
```

När du öppnar `MicroPdf417.png` bör du se en ren, högupplöst streckkod som matchar 2‑pixel X‑dimensionen och 4‑kolumns layouten du konfigurerade. De flesta moderna scanners läser den omedelbart, även från en skärmbild.

![justera streckkodsstorlek – exempel på MicroPdf417‑streckkod](MicroPdf417.png "justera streckkodsstorlek – exempel på MicroPdf417‑streckkod")

*Bildbeskrivning (alt‑text):* **justera streckkodsstorlek – exempel på MicroPdf417‑streckkod genererad med C#**.

## Fullt fungerande exempel (Alla steg kombinerade)

Nedan är det kompletta programmet som du kan kopiera‑klistra in i ett nytt Console‑App‑projekt. Det inkluderar `using`‑direktiv, felhantering och kommentarer som förklarar varje rad.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // 1️⃣ Initialise the generator with MicroPdf417 and Unicode text
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.MicroPdf417,
                    "Åspóse.Barcóde©");

                // 2️⃣ Adjust the X‑dimension for finer resolution (2 px)
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // 3️⃣ Set columns to 4 for a compact layout
                generator.Parameters.Barcode.Pdf417.Columns = 4;

                // 4️⃣ Choose where to save the PNG image
                string desktop = Environment.GetFolderPath(Environment.SpecialFolder.Desktop);
                string filePath = Path.Combine(desktop, "MicroPdf417.png");

                // 5️⃣ Save the image
                generator.Save(filePath, BarCodeImageFormat.Png);

                Console.WriteLine($"✅ Barcode generated and saved to: {filePath}");
            }
            catch (Exception ex)
            {
                // In production code you’d log this instead of writing to console
                Console.WriteLine($"❌ An error occurred: {ex.Message}");
            }
        }
    }
}
```

### Förväntad utskrift

När programmet körs skrivs något liknande ut:

```
✅ Barcode generated and saved to: C:\Users\YourName\Desktop\MicroPdf417.png
```

Att öppna PNG‑filen visar en skarp MicroPdf417‑streckkod med exakt de dimensioner du angav. Skanna den med någon PDF417‑läsare (mobilappar, Zebra‑scanners osv.) så får du tillbaka den ursprungliga strängen `"Åspóse.Barcóde©"`.

## Vanliga frågor & kantfall

| Fråga | Svar |
|-------|------|
| **Vad gör jag om jag behöver en större bild?** | Öka `XDimension.Pixels` (t.ex. till `4`) eller exportera som ett högre upplöst format som `BarCodeImageFormat.Tiff`. |
| **Kan jag generera full‑storlek PDF417 istället för MicroPdf417?** | Absolut—byt bara `EncodeTypes.MicroPdf417` mot `EncodeTypes.Pdf417`. Samma `Columns`‑ och `XDimension`‑egenskaper gäller fortfarande. |
| **Är Unicode‑stöd pålitligt?** | Ja. Aspose.BarCode kodar Unicode‑tecken med UTF‑8 internt, men kom ihåg datakapacitetsgränsen för MicroPdf417. |
| **Vad händer om mål‑mappen inte finns?** | `Save`‑metoden kastar `DirectoryNotFoundException`. Omslut anropet med ett `try/catch`‑block (som visas) eller skapa mappen med `Directory.CreateDirectory`. |
| **Behöver jag sätta streckkodshöjden manuellt?** | Nej. Höjden beräknas automatiskt baserat på antal rader som krävs för data och kolumnantalet. |

## Tips för perfekt justerade streckkoder

- **Pro tip:** Vid utskrift på termiska etiketter, sätt skrivardpi till 300 dpi och håll `XDimension.Pixels` på `2`. Detta ger en fysisk modulbredd på ≈0,17 mm, vilket de flesta scanners gillar.
- **Se upp för:** Överkomprimering av PNG (med låg kvalitet) kan göra kanterna suddiga och undergräva syftet med en fin X‑dimension.
- **Typisk fallgrop:** Att glömma `using Aspose.BarCode;` leder till kompileringsfel på `BarCodeImageFormat`‑enum.

## Nästa steg — Bortom grunderna

Nu när du kan **adjust barcode size** och **how to generate PDF417**, kanske du vill utforska:

- Lägga till **färg** på streckkoden (`generator.Parameters.Barcode.Color = Color.Blue;`).
- Bädda in streckkoden direkt i en PDF med `Aspose.Pdf`.
- Generera **flera streckkoder** i en batch‑operation för massetikett‑utskrift.
- Använda **felkorrigeringsnivå**‑inställningar för att förbättra läsbarheten i bullriga miljöer.

Alla dessa ämnen bygger på de grundläggande koncepten som behandlats här, och samma mönster—skapa en generator, justera parametrar, spara—gäller över hela linjen.

---

### TL;DR

Du har precis lärt dig hur du **adjust barcode size** i C# genom att sätta X‑dimensionen och kolumnantalet, och du förstår nu **how to generate PDF417** (specifikt MicroPdf417) med Aspose.BarCode. Det fullständiga, körbara exemplet ovan producerar en skarp PNG‑bild klar för alla efterföljande arbetsflöden. Känn dig fri att experimentera med parametrarna, byta till full‑storlek PDF417, eller integrera koden i en större applikation. Lycka till med kodandet!

## Vad bör du lära dig härnäst?

De följande handledningarna täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i denna guide. Varje resurs innehåller kompletta kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringssätt i dina egna projekt.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
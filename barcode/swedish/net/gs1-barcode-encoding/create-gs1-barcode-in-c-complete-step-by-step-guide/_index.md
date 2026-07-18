---
category: general
date: 2026-07-18
description: Skapa GS1‑streckkod i C# och lär dig hur du genererar streckkodsbilder,
  ställer in kolumner och använder Barcode Generator C# för felfria resultat.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create gs1 barcode
- how to generate barcode
- how to set columns
- barcode generator c#
- create barcode image
language: sv
lastmod: 2026-07-18
og_description: Skapa GS1-streckkod i C# snabbt. Lär dig hur du genererar streckkods­bilder,
  konfigurerar kolumner och master Barcode Generator C# på några minuter.
og_image_alt: Screenshot showing a generated GS1 Micro PDF417 barcode image
og_title: Skapa GS1-streckkod i C# – Fullständig programmeringsgenomgång
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create GS1 barcode in C# and learn how to generate barcode images,
    set columns, and use Barcode Generator C# for flawless results.
  headline: Create GS1 Barcode in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: Create GS1 barcode in C# and learn how to generate barcode images,
    set columns, and use Barcode Generator C# for flawless results.
  name: Create GS1 Barcode in C# – Complete Step‑by‑Step Guide
  steps:
  - name: What if I need a different image format?
    text: Just replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`, `Bmp`,
      or `Gif`. The library handles the conversion automatically.
  - name: Can I generate multiple barcodes in a loop?
    text: Absolutely. Wrap the generator creation and `Save` call inside a `foreach`
      that iterates over your data set. Remember to reset or create a fresh `BarcodeGenerator`
      instance for each unique data string to avoid parameter bleed‑over.
  - name: How does error handling work?
    text: 'If the data string violates GS1 rules (e.g., missing mandatory AI), the
      library throws a `BarcodeException`. Catch it and log the problematic input:'
  - name: What about DPI settings for printing?
    text: 'You can control the output resolution via `barcodeGenerator.Parameters.ImageResolution`.
      For high‑quality printouts, set it to 300 dpi:'
  type: HowTo
tags:
- barcode
- C#
- GS1
title: Skapa GS1-streckkod i C# – Komplett steg‑för‑steg‑guide
url: /sv/net/gs1-barcode-encoding/create-gs1-barcode-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa GS1-streckkod i C# – Komplett steg‑för‑steg‑guide

Har du någonsin funderat på hur man **skapar GS1-streckkod** med C# utan att rycka ur håret? Du är inte ensam. Oavsett om du bygger ett lageravläsningssystem eller behöver bädda in produktdata i en mobilapp, är det en solid färdighet för varje .NET‑utvecklare att behärska skapandet av en GS1‑streckkod.

I den här handledningen går vi igenom de exakta stegen för att **skapa GS1-streckkod**‑bilder, förklarar **hur man genererar streckkod**‑filer med finjusterade inställningar, och visar dig de små knepen som gör hela processen smärtfri. I slutet har du en färdig PNG‑fil och en klar förståelse för det underliggande API‑et.

## Förutsättningar

- .NET 6.0 eller senare installerat (koden fungerar även med .NET Framework 4.7+).
- En referens till **Barcode Generator C#**‑biblioteket (t.ex. Aspose.BarCode för .NET eller något kompatibelt NuGet‑paket).
- En mapp på disken där du kan skriva utdata‑bilden (exemplet använder `YOUR_DIRECTORY` – ersätt den med en faktisk sökväg).

Inga andra externa verktyg krävs.

## Så skapar du GS1-streckkod i C# – Översikt

Vi delar upp lösningen i fyra logiska delar:

1. **Instansiera streckkodsgeneratorn** med GS1 Micro PDF417‑symbologi och den råa datatsträngen.
2. **Konfigurera visuella parametrar** som X‑dimensionen (modulbredd) för skarpare rendering.
3. **Ställ in kolumnantalet** för att kontrollera matrislayouten – här blir **how to set columns** avgörande.
4. **Spara resultatet** som en PNG‑fil, vilket slutför steget **create barcode image**.

Varje del motsvarar ett litet, testbart kodsnutt, så att du kan kopiera‑klistra och köra direkt.

---

## Steg 1: Instansiera streckkodsgeneratorn (Skapa GS1-streckkod)

Det första du behöver göra är att skapa en instans av `BarcodeGenerator`. Detta objekt kommer att hålla alla inställningar och data som behövs för att **skapa GS1-streckkod**‑utdata.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for GS1 Micro PDF417 with the required data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.GS1MicroPdf417,
    "(01)12345678901231(240)ABCD123456789012345");
```

> **Varför detta är viktigt:** Enum‑värdet `EncodeTypes.GS1MicroPdf417` talar om för biblioteket att du vill ha en GS1‑kompatibel Micro PDF417‑symbol, och datasträngen följer GS1 Application Identifier (AI)‑syntaxen. Att få AI‑formatet rätt är grunden för en giltig **create GS1 barcode**‑operation.

---

## Steg 2: Finjustera X‑dimensionen (Hur man genererar streckkod med bättre detaljrikedom)

En streckkods läsbarhet beror ofta på modulbredden, känd som X‑dimensionen. Att sätta den till ett lägre antal pixlar ger finare detaljer, vilket kan vara viktigt för små etiketter.

```csharp
// Step 2: Set the X‑dimension (module width) to 2 pixels for finer detail
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Proffstips:** Om du planerar att skriva ut streckkoden på en högupplöst skrivare är 2 pixlar ett säkert standardvärde. För lågupplösta skärmar kan du öka det till 3 eller 4 pixlar för att undvika sudda kanter.

---

## Steg 3: How to Set Columns – Kontroll av PDF417‑matrisen

PDF417‑familjen låter dig ange antalet kolumner i dess matris. Detta påverkar både den fysiska storleken och skanningsprestandan. Här är kodsnutten som svarar på **how to set columns** för en GS1 Micro PDF417‑streckkod.

```csharp
// Step 3: Define the number of columns in the PDF417 matrix (4 columns)
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

> **När du ska ändra det:** Om ditt etikettutrymme är begränsat horisontellt, minska kolumnantalet. Omvänt, öka kolumnerna för ett mer kompakt vertikalt fotavtryck. Biblioteket justerar automatiskt radantalet för att rymma data.

---

## Steg 4: Spara streckkoden – Skapa streckkodsbild

Nu när generatorn är fullt konfigurerad kan du äntligen **create barcode image** genom att spara den till disk. Följande rad skriver en PNG‑fil, men du kan också välja JPEG, BMP eller GIF.

```csharp
// Step 4: Save the generated barcode as a PNG image
barcodeGenerator.Save("YOUR_DIRECTORY/GS1MicroPdf417_903to905.png", BarCodeImageFormat.Png);
```

> **Förväntat resultat:** Efter att programmet körts kommer `GS1MicroPdf417_903to905.png` att visas i mål‑mappen. Öppna den med någon bildvisare så bör du se en ren, läsbar GS1 Micro PDF417‑symbol.

---

## Fullt fungerande exempel

Nedan är det kompletta, körbara programmet som binder ihop alla fyra stegen. Kopiera det till ett nytt konsolprojekt och tryck **F5**.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Gs1BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Create a barcode generator for GS1 Micro PDF417 with the required data
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.GS1MicroPdf417,
                "(01)12345678901231(240)ABCD123456789012345");

            // 2️⃣ Set the X‑dimension (module width) to 2 pixels for finer detail
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Define the number of columns in the PDF417 matrix (4 columns)
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;

            // 4️⃣ Save the generated barcode as a PNG image
            const string outputPath = @"C:\Temp\GS1MicroPdf417_903to905.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"GS1 barcode created successfully at: {outputPath}");
        }
    }
}
```

**Kör du denna kod** kommer den att producera en PNG‑fil som du kan bädda in i rapporter, skriva ut på produktförpackningar eller skicka till en mobilskanningsapp. Konsolmeddelandet bekräftar platsen, vilket är praktiskt för snabb felsökning.

---

## Vanliga frågor & specialfall

### Vad händer om jag behöver ett annat bildformat?

Byt bara ut `BarCodeImageFormat.Png` mot `BarCodeImageFormat.Jpeg`, `Bmp` eller `Gif`. Biblioteket hanterar konverteringen automatiskt.

### Kan jag generera flera streckkoder i en loop?

Absolut. Lägg in generatorns skapande och `Save`‑anropet i en `foreach` som itererar över din datamängd. Kom ihåg att återställa eller skapa en ny `BarcodeGenerator`‑instans för varje unik datasträng för att undvika att parametrar läcker över.

### Hur fungerar felhantering?

Om datasträngen bryter mot GS1‑reglerna (t.ex. saknar obligatorisk AI) kastar biblioteket ett `BarcodeException`. Fånga det och logga den problematiska inmatningen:

```csharp
try
{
    // generator code here
}
catch (BarcodeException ex)
{
    Console.Error.WriteLine($"Invalid GS1 data: {ex.Message}");
}
```

### Vad gäller DPI‑inställningar för utskrift?

Du kan kontrollera utdataupplösningen via `barcodeGenerator.Parameters.ImageResolution`. För högkvalitativa utskrifter, sätt den till 300 dpi:

```csharp
barcodeGenerator.Parameters.ImageResolution = 300;
```

---

## Visuellt resultat

Nedan är en platshållarbild som illustrerar hur den slutgiltiga **create GS1 barcode**‑utdata ser ut. Ersätt URL:en med den faktiska sökvägen till din genererade PNG när du publicerar handledningen.

![GS1 Micro PDF417 barcode generated by C# code – create barcode image](https://example.com/gs1-micro-pdf417-sample.png)

*Alt‑text:* **GS1 Micro PDF417 barcode generated by C# code – create barcode image**

---

## Sammanfattning: Vad vi uppnådde

- **Create GS1 barcode** med Aspose.BarCode‑biblioteket.
- Lärde oss **how to generate barcode** med anpassad X‑dimension för skarp rendering.
- Behärskade **how to set columns** för att passa dina etikettbegränsningar.
- Använde **barcode generator c#** för att konfigurera och exportera en **create barcode image** i PNG‑format.

---

## Nästa steg & relaterade ämnen

Nu när du kan **create GS1 barcode**‑bilder, överväg att utforska:

- **Embedding barcodes in PDF reports** (sök efter “barcode generator c# PDF export”).
- **Dynamic data binding** för real‑time streckkodsgenerering i ASP.NET Core‑webbappar.
- **Scanning verification** med ett mobilt SDK för att säkerställa att den genererade streckkoden uppfyller branschstandarder.

Om du stöter på problem, tveka inte att lämna en kommentar—lycka till med kodningen!

---

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Skapa streckkodsbild c# – Konfigurera Codablock F rader & kolumner](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Skapa DotCode streckkodsbild – rader & kolumner (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Hur man skapar tyst zon för ITF-14‑streckkod med Aspose.BarCode för .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
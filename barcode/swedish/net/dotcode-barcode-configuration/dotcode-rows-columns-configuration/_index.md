---
date: 2026-08-22
description: Lär dig hur du skapar dotcode-streckkods bilder och konfigurerar rader
  och kolumner med Aspose.BarCode för .NET.
keywords:
- create dotcode barcode
- dotcode rows columns
- Aspose.BarCode .NET
- barcode generation
lastmod: 2026-08-22
linktitle: Konfiguration av DotCode rader och kolumner
og_description: Lär dig hur du skapar dotcode-streckkods bilder och konfigurerar rader
  och kolumner med Aspose.BarCode för .NET. Steg‑för‑steg‑guide med praktiska tips.
og_image_alt: Screenshot of a DotCode barcode generated with Aspose.BarCode in .NET
og_title: Skapa dotcode-streckkod rader & kolumner med Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to create dotcode barcode images and configure rows and columns
    using Aspose.BarCode for .NET.
  headline: Create dotcode barcode rows & columns with Aspose.BarCode
  type: TechArticle
- description: Learn how to create dotcode barcode images and configure rows and columns
    using Aspose.BarCode for .NET.
  name: Create dotcode barcode rows & columns with Aspose.BarCode
  steps:
  - name: set up your directory path
    text: First, decide where the generated images will be saved. Replace the placeholder
      with an actual folder on your machine. > **Pro tip:** Use `Path.Combine(Environment.CurrentDirectory,
      "Barcodes")` to build a path that works across platforms.
  - name: initialize the dotcode generator
    text: Create a `BarcodeGenerator` instance, specify the `EncodeTypes.DotCode`
      symbology, and provide the data you want to encode (e.g., “Aspose”). > **Definition
      anchor:** `EncodeTypes.DotCode` is the enumeration value that tells the generator
      to produce a DotCode barcode.
  - name: configure dotcode columns
    text: If you want a fixed number of columns, set the `Columns` property. Here
      we choose **18 columns** and store the result as a PNG file. > **Why XDimension?**
      Adjusting the pixel size changes the visual density of each dot without affecting
      the encoded data.
  - name: configure dotcode rows
    text: You can also fix the number of rows while letting the library decide the
      column count (by setting `Columns = -1`). The example below creates a barcode
      with **12 rows**. > **Common pitfall:** Setting both rows and columns to values
      that are too high can produce an image that exceeds typical label dim
  - name: configure rows and columns simultaneously
    text: When you need full control, set both properties. The following snippet produces
      a barcode with **29 columns** and **26 rows**.
  type: HowTo
- questions:
  - answer: It depends on the number of rows and columns you configure. More cells
      increase capacity; a 30 × 30 matrix can hold up to 2 KB of text.
    question: What is the maximum amount of data I can store in a DotCode barcode?
  - answer: Yes. Use `gen.Parameters.Barcode.ForeColor` and `BackColor` to set custom
      colors before saving.
    question: Can I change the barcode’s colors?
  - answer: Aspose.BarCode for .NET works on .NET Framework, .NET Core, and .NET 5/6+,
      so you can generate images on Windows, Linux, or macOS.
    question: Is the DotCode symbology supported on all platforms?
  - answer: The official API reference provides detailed documentation – see the [Aspose.BarCode
      documentation](https://reference.aspose.com/barcode/net/).
    question: Where can I find a complete list of all DotCode parameters?
  - answer: Call `gen.Save(Stream, BarCodeImageFormat.Png)` and return the stream
      as a file result.
    question: How do I generate a barcode in a web API without writing to disk?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- dotcode barcode
- Aspose.BarCode
- .NET barcode library
title: Skapa dotcode-streckkod rader & kolumner med Aspose.BarCode
url: /sv/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa DotCode streckkod rader & kolumner med Aspose.BarCode

## Introduktion

I den här handledningen kommer du att lära dig hur du **skapa DotCode‑streckkod**‑bilder och exakt justerar deras rader och kolumner med Aspose.BarCode för .NET. Oavsett om du bygger ett system för märkning inom sjukvården, en logistikspårningslösning eller bara experimenterar med 2‑D‑symbologier, gör kontroll av dessa dimensioner att du kan anpassa streckkoden till vilken etikettstorlek som helst samtidigt som du maximerar datakapaciteten.

## Snabba svar
- **Vad betyder “skapa DotCode‑streckkod bild”?** Det betyder att generera en visuell PNG/JPEG/etc.-fil som kodar dina data med DotCode 2‑D‑symbologi.  
- **Vilket bibliotek hanterar genereringen?** Aspose.BarCode för .NET tillhandahåller ett enkelt API för att producera högkvalitativa DotCode‑bilder.  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktionsanvändning.  
- **Kan jag anpassa rader och kolumner oberoende?** Ja – du kan sätta rader, kolumner, eller låta biblioteket automatiskt bestämma storleken.  
- **Vilka utdataformat stöds?** PNG, JPEG, BMP, GIF, TIFF och fler via `BarCodeImageFormat`.

## Vad är en DotCode‑streckkod bild?

En DotCode‑streckkod bild är en rasterrepresentation av DotCode‑2‑dimensionella symbologi som lagrar data i en matris av prickar. Den är allmänt använd inom **healthcare** och **pharmaceutical** sektorerna för spårning av produkter och kodning av patientinformation. Genom att konfigurera rader och kolumner påverkar du direkt streckkodens fysiska storlek och mängden data den kan innehålla.

## Varför konfigurera rader och kolumner?

Att sätta rader och kolumner ger dig deterministisk kontroll över streckkodens fotavtryck och läsbarhet. Fler rader eller kolumner ökar datakapaciteten med ungefär 12 tecken per extra cell och lägger till cirka 0,5 mm till den totala bildstorleken. Detta låter dig balansera etikettutrymmesbegränsningar med skanningspålitlighet för specifika skrivare eller skannrar.

## Förutsättningar

1. **.NET‑utvecklingsmiljö** – Visual Studio, Rider eller VS Code med .NET SDK installerat.  
2. **Aspose.BarCode för .NET** – ladda ner det från den officiella webbplatsen **[download Aspose.BarCode for .NET](https://releases.aspose.com/barcode/net/)**.  
3. **En giltig licens** (eller en tillfällig provlicens) för produktion‑klassad generering.  
4. **Grundläggande C#‑kunskap** – kodsnuttarna är korta, men förståelse för variabeltilldelning och objektinstansiering hjälper.

## Importera namnrymder

Den enda namnrymden som krävs för exemplen är:

`Aspose.BarCode.Generation`

> **Definition anchor:** `BarcodeGenerator` är kärnklassen i Aspose.BarCode som skapar streckkods‑bilder från angivna data och konfigurationsinställningar.

## Steg‑för‑steg‑guide för att skapa DotCode‑streckkod bild

### Steg 1: konfigurera din katalogsökväg

Först, bestäm var de genererade bilderna ska sparas. Ersätt platshållaren med en faktisk mapp på din dator.

> **Pro tip:** Använd `Path.Combine(Environment.CurrentDirectory, "Barcodes")` för att bygga en sökväg som fungerar på alla plattformar.

### Steg 2: initiera DotCode‑generatorn

Skapa en `BarcodeGenerator`‑instans, ange symbologin `EncodeTypes.DotCode` och tillhandahåll de data du vill koda (t.ex. “Aspose”).

> **Definition anchor:** `EncodeTypes.DotCode` är enum‑värdet som talar om för generatorn att producera en DotCode‑streckkod.

### Steg 3: konfigurera DotCode‑kolumner

Om du vill ha ett fast antal kolumner, sätt `Columns`‑egenskapen. Här väljer vi **18 kolumner** och sparar resultatet som en PNG‑fil.

> **Varför XDimension?** Justering av pixelstorleken ändrar den visuella densiteten för varje prick utan att påverka de kodade data.

### Steg 4: konfigurera DotCode‑rader

Du kan också fixera antalet rader medan du låter biblioteket bestämma kolumnantalet (genom att sätta `Columns = -1`). Exemplet nedan skapar en streckkod med **12 rader**.

> **Vanligt fallgropp:** Att sätta både rader och kolumner till värden som är för höga kan producera en bild som överskrider vanliga etikettmått. Testa med en förhandsgranskning innan utskrift.

### Steg 5: konfigurera rader och kolumner samtidigt

När du behöver full kontroll, sätt båda egenskaperna. Följande kodsnutt producerar en streckkod med **29 kolumner** och **26 rader**.

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|---------|-------|---------|
| Streckkoden blir suddig | XDimension för låg | Öka `XDimension.Pixels` (t.ex. 12‑15). |
| Skannern kan inte läsa streckkoden | Rader/Kolumner för täta för skrivaren | Minska rader/kolumner eller använd en skrivare med högre upplösning. |
| Bilden sparas inte | Ogiltig `path`‑sträng | Säkerställ att katalogen finns eller anropa `Directory.CreateDirectory(path)`. |

## Vanliga frågor

**Q: Vad är den maximala mängden data jag kan lagra i en DotCode‑streckkod?**  
A: Det beror på antalet rader och kolumner du konfigurerar. Fler celler ökar kapaciteten; en 30 × 30‑matris kan hålla upp till 2 KB text.

**Q: Kan jag ändra streckkodens färger?**  
A: Ja. Använd `gen.Parameters.Barcode.ForeColor` och `BackColor` för att ange egna färger innan du sparar.

**Q: Stöds DotCode‑symbologin på alla plattformar?**  
A: Aspose.BarCode för .NET fungerar på .NET Framework, .NET Core och .NET 5/6+, så du kan generera bilder på Windows, Linux eller macOS.

**Q: Var kan jag hitta en komplett lista över alla DotCode‑parametrar?**  
A: Den officiella API‑referensen ger detaljerad dokumentation – se [Aspose.BarCode documentation](https://reference.aspose.com/barcode/net/).

**Q: Hur genererar jag en streckkod i ett webb‑API utan att skriva till disk?**  
A: Anropa `gen.Save(Stream, BarCodeImageFormat.Png)` och returnera strömmen som ett filresultat.

## Slutsats

Du vet nu hur du **skapar DotCode‑streckkod**‑filer och exakt styr deras rader och kolumner med Aspose.BarCode för .NET. Genom att justera egenskaperna `Rows` och `Columns` kan du anpassa streckkodens storlek för vilken etikett‑ eller förpackningssituation som helst. Experimentera med olika dimensioner, färger och utdataformat för att passa ditt projekts behov, och utforska det bredare Aspose.BarCode‑funktionspaketet för ännu mer anpassning.

Om du stöter på problem eller vill gå djupare, kolla in de officiella resurserna:

* [Aspose.BarCode documentation](https://reference.aspose.com/barcode/net/)  
* [Aspose.BarCode community support](https://forum.aspose.com/c/barcode/13)

---

**Senast uppdaterad:** 2026-08-22  
**Testad med:** Aspose.BarCode för .NET 24.11 (senaste vid skrivande)  
**Författare:** Aspose  







```csharp
using Aspose.BarCode.Generation;
```

```csharp
string path = "Your Directory Path";
```

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, "Aspose"))
{
    // All configuration and saving will happen inside this block.
}
```

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 10;
gen.Parameters.Barcode.DotCode.Columns = 18;
gen.Save($"{path}DotCodeColumns18.png", BarCodeImageFormat.Png);
```

```csharp
gen.Parameters.Barcode.DotCode.Columns = -1;
gen.Parameters.Barcode.DotCode.Rows = 12;
gen.Save($"{path}DotCodeRows12.png", BarCodeImageFormat.Png);
```

```csharp
gen.Parameters.Barcode.DotCode.Columns = 29;
gen.Parameters.Barcode.DotCode.Rows = 26;
gen.Save($"{path}DotCodeRows26Columns29.png", BarCodeImageFormat.Png);
```

## Relaterade handledningar

- [Skapa DotCode‑streckkod .NET (Auto‑läge) med Aspose.BarCode](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)
- [Hur man skapar DotCode‑utökad kodtext med Aspose.BarCode för .NET](/barcode/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Skapa DotCode‑streckkod .NET – Structured Append med Aspose](/barcode/net/dotcode-barcode-configuration/dotcode-structured-append-mode-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
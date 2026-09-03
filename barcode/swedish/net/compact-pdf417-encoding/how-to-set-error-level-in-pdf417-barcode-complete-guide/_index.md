---
category: general
date: 2026-07-18
description: hur man anger felnivå i PDF417‑streckkod med Aspose.BarCode. Lär dig
  att generera PDF417‑streckkod med anpassad text och justera felkorrigeringen på
  några minuter.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set error
- generate pdf417 barcode
- how to generate pdf417
- barcode with custom text
language: sv
lastmod: 2026-07-18
og_description: hur man snabbt ställer in felnivå i PDF417‑streckkod. Den här handledningen
  guidar dig genom att generera en PDF417‑streckkod med anpassad text och olika felkorrigeringsnivåer.
og_image_alt: how to set error level in PDF417 barcode example
og_title: Hur man ställer in felnivå i PDF417‑streckkod – steg‑för‑steg‑guide
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: how to set error level in PDF417 barcode using Aspose.BarCode. Learn
    to generate PDF417 barcode with custom text and tweak error correction in minutes.
  headline: How to Set Error Level in PDF417 Barcode – Complete Guide
  type: TechArticle
- description: how to set error level in PDF417 barcode using Aspose.BarCode. Learn
    to generate PDF417 barcode with custom text and tweak error correction in minutes.
  name: How to Set Error Level in PDF417 Barcode – Complete Guide
  steps:
  - name: What if my text contains line breaks?
    text: 'PDF417 automatically encodes line‑feed (`

      `) characters. Just include them in the string:'
  - name: Can I use a different image format?
    text: Absolutely. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Svg`
      depending on your downstream workflow.
  - name: Does changing the X‑dimension affect error correction?
    text: Indirectly, yes. A larger X‑dimension yields bigger modules, which can improve
      scanning reliability but does **not** alter the logical error‑correction level.
      Adjust both parameters independently for best results.
  - name: How to generate PDF417 barcode in a web API?
    text: Wrap the same code in an ASP.NET Core controller and stream the PNG back
      as a `FileResult`. The core logic stays unchanged, which means **how to generate
      PDF417** remains consistent across desktop and web environments.
  type: HowTo
tags:
- PDF417
- barcode
- error correction
title: Hur man ställer in felnivå i PDF417‑streckkod – Komplett guide
url: /sv/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man ställer in felnivå i PDF417‑streckkod – Komplett guide

Har du någonsin undrat **hur man ställer in fel** när du genererar en PDF417‑streckkod? Du är inte ensam – de flesta utvecklare stöter på detta när de behöver en mer robust streckkod för skanning i tuffa miljöer. Den goda nyheten? Att justera felkorrigeringsnivån är enkelt med Aspose.BarCode, och du får även lära dig **hur man genererar PDF417** med egen anpassad text medan du är igång.

I den här handledningen går vi igenom varje steg, från att skapa en streckkodsgenerator med specialtecken till att spara två PNG‑filer som visar olika felkorrigeringsnivåer. När du är klar kommer du att känna dig säker på **generering av PDF417‑streckkod**, justering av dess X‑dimension, kolumnantal och, viktigast av allt, **inställning av fel**‑nivåer som passar ditt användningsfall.

## Förutsättningar

- .NET 6.0 eller senare (koden fungerar även med .NET Framework)
- Aspose.BarCode för .NET installerat (`Install-Package Aspose.BarCode` via NuGet)
- En mapp på disken där bilderna kan skrivas (ersätt `YOUR_DIRECTORY/` i exemplet)
- Grundläggande C#‑kunskaper – om du har skrivit ett `Console.WriteLine` tidigare är du redo

> **Proffstips:** Om du riktar dig mot mobilsökning, sikta på en högre felnivå (Nivå 5) för att klara smuts, repor eller svagt ljus.

## Steg 1: Skapa en streckkodsgenerator med anpassad text

Det första du behöver är en `BarcodeGenerator`‑instans som vet att den ska producera en **PDF417‑streckkod** och som bär exakt den text du vill koda. Lägg märke till användningen av accentuerade tecken och en copyright‑symbol – detta visar att generatorn kan hantera Unicode direkt.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

*Varför detta är viktigt:* Flaggan `EncodeTypes.Pdf417` talar om för Aspose att du arbetar med en 2‑D staplad streckkod, medan strängargumentet blir databelastningen. Om du hoppar över detta steg får du en standard‑Code128‑streckkod istället för den högkapacitets‑PDF417 du behöver.

## Steg 2: Finjustera visuella parametrar

En PDF417‑streckkod är inte bara data; den är också ett visuellt mönster. Genom att justera **X‑dimensionen** (bredden på den minsta stapeln) och antalet **kolumner** kan du kontrollera streckkodens fysiska storlek och läsbarhet.

```csharp
// Step 2: Adjust visual parameters – set the X‑dimension and number of columns
generator.Parameters.Barcode.XDimension.Pixels = 2;   // each module is 2 pixels wide
generator.Parameters.Barcode.Pdf417.Columns = 3;    // three columns across the page
```

*Varför detta är viktigt:* En mindre X‑dimension ger en mer kompakt bild men kan bli oläslig på skannrar med låg upplösning. Tre kolumner ger ett balanserat bildförhållande för de flesta etikettstorlekar.

## Steg 3: Ställ in felkorrigeringsnivå till 2 och spara

Felkorrigering är kärnan i **hur man ställer in fel** för PDF417. `Pdf417ErrorLevel`‑enumen sträcker sig från `Level0` (ingen extra data) upp till `Level5` (maximal redundans). Här börjar vi med **Nivå 2**, vilket lägger till en måttlig mängd felresistens utan att bilden blir för stor.

```csharp
// Define the output folder (replace with your actual path)
string outputFolder = "YOUR_DIRECTORY/";

// Step 3: Set error correction level to 2 and save the image
generator.Parameters.Barcode.Pdf417.ErrorLevel = Pdf417ErrorLevel.Level2;
generator.Save($"{outputFolder}Pdf417ErrorLevel2.png", BarCodeImageFormat.Png);
```

Efter att ha kört detta kodsnutt hittar du `Pdf417ErrorLevel2.png` i din mapp. Öppna den, så bör du se en ren, tre‑kolumnig streckkod som fortfarande innehåller en rimlig mängd redundans.

## Steg 4: Öka felkorrigeringen till Nivå 5 och spara igen

Ibland måste streckkoden klara av mer aggressiv skada – tänk dig ett lagergolv där etiketter repas. Att byta till **Nivå 5** maximerar felkorrigeringen på bekostnad av en något större bild.

```csharp
// Step 4: Change error correction level to 5 and save the second image
generator.Parameters.Barcode.Pdf417.ErrorLevel = Pdf417ErrorLevel.Level5;
generator.Save($"{outputFolder}Pdf417ErrorLevel5.png", BarCodeImageFormat.Png);
```

Nu har du två PNG‑filer sida vid sida: en med måttlig felkorrigering, en med maximal. Jämför dem; versionen med Nivå 5 har fler mörka moduler, vilket exakt är vad algoritmen lägger till för att skydda data.

![hur man ställer in felnivå i PDF417‑streckkod exempel](image.png)

*Bildbeskrivning (alt‑text): hur man ställer in felnivå i PDF417‑streckkod exempel – visar två PNG‑filer med olika felkorrigeringsnivåer.*

## Förväntad utdata

| Filnamn                        | Felnivå | Ungefärliga dimensioner (px) |
|--------------------------------|---------|------------------------------|
| `Pdf417ErrorLevel2.png`        | Nivå 2  | 150 × 80                     |
| `Pdf417ErrorLevel5.png`        | Nivå 5  | 180 × 95                     |

Båda bilderna kodar strängen **“Åspóse.Barcóde©”** och kan skannas med vilken standard‑PDF417‑läsare som helst (t.ex. ZXing, Scandit). Bilden med Nivå 5 tål upp till ~30 % skada, medan Nivå 2 tål omkring ~15 %.

## Vanliga frågor & kantfall

### Vad händer om min text innehåller radbrytningar?
PDF417 kodar automatiskt radmatning (`\n`). Inkludera dem bara i strängen:

```csharp
new BarcodeGenerator(EncodeTypes.Pdf417, "Line1\nLine2\nLine3");
```

### Kan jag använda ett annat bildformat?
Absolut. Byt ut `BarCodeImageFormat.Png` mot `Jpeg`, `Bmp` eller `Svg` beroende på ditt efterföljande arbetsflöde.

### Påverkar förändring av X‑dimensionen felkorrigeringen?
Indirekt, ja. En större X‑dimension ger större moduler, vilket kan förbättra skanningspålitligheten men **ändrar inte** den logiska felkorrigeringsnivån. Justera båda parametrarna oberoende för bästa resultat.

### Hur genererar man PDF417‑streckkod i ett webb‑API?
Packa in samma kod i en ASP.NET Core‑controller och streama PNG‑filen tillbaka som ett `FileResult`. Kärnlogiken förblir oförändrad, vilket betyder att **hur man genererar PDF417** förblir konsekvent i både skrivbords‑ och webbmiljöer.

## Sammanfattning

Vi har gått igenom **hur man ställer in fel** för en PDF417‑streckkod, demonstrerat **hur man genererar PDF417** med anpassad Unicode‑text, och visat hur du finjusterar visuella inställningar som X‑dimension och kolumnantal. Genom att byta `Pdf417ErrorLevel.Level2` mot `Level5` kan du kontrollera avvägningen mellan bildstorlek och motståndskraft.

## Nästa steg

- Experimentera med **streckkod med anpassad text** som inkluderar URL:er eller produkt‑ID:n.
- Prova olika kolumnantal (`generator.Parameters.Barcode.Pdf417.Columns = 5`) för att se hur formen förändras.
- Kombinera PDF417 med andra streckkodstyper i samma dokument för multimodala skanningslösningar.
- Fördjupa dig i Asposes [officiella dokumentation](https://docs.aspose.com/barcode/net/) för avancerade funktioner som macro PDF417 eller kompakt läge.

Känn dig fri att lämna en kommentar om du stöter på problem, eller dela dina egna skannade resultat. Lycka till med streckkodsskapandet!


## Vad bör du lära dig härnäst?


Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to create Aztec barcode with error correction in .NET](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
---
category: general
date: 2026-09-16
description: Naučte se, jak nastavit šířku, jak vytvořit prázdné pruhy a jak vyplnit
  pruhy při generování Planet čárového kódu pomocí Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to make empty
- how to fill bars
- generate planet barcode
language: cs
lastmod: 2026-09-16
og_description: Jak nastavit šířku, vytvořit prázdné pruhy a vyplnit pruhy při generování
  Planet čárového kódu pomocí Aspose.BarCode – kompletní krok‑za‑krokem průvodce.
og_image_alt: Screenshot showing how to set width for a Planet barcode in C#
og_title: Jak nastavit šířku a vygenerovat čárový kód Planet v C#
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set width, how to make empty bars, and how to fill bars
    when you generate Planet barcode using Aspose.BarCode.
  headline: How to set width and generate a Planet barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak nastavit šířku a vygenerovat Planet čárový kód v C#
url: /cs/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak nastavit šířku a vygenerovat Planet čárový kód v C#

Pokud potřebujete **jak nastavit šířku** pro Planet čárový kód, tento průvodce ukazuje celý proces. Také uvidíte **jak vytvořit prázdné** pruhy, **jak vyplnit pruhy** a přesné kroky k **vygenerování Planet čárového kódu** pomocí Aspose.BarCode pro .NET.

Generování poštovního stylu Planet čárového kódu je běžné při tvorbě aplikací pro štítky nebo integrací poštovních služeb. Na konci tohoto tutoriálu budete mít připravený spustitelný konzolový program, který vytvoří jak obrázek s vyplněnými pruhy, tak obrázek s prázdnými pruhy, oba používající stejný datový řetězec.

## Požadavky

- .NET 6.0 SDK nebo novější (kód také funguje s .NET Framework 4.7+)
- Visual Studio 2022 nebo jakékoli IDE kompatibilní s C#
- NuGet balíček Aspose.BarCode pro .NET (`Aspose.BarCode`)  
  Instalace pomocí:

```bash
dotnet add package Aspose.BarCode
```

Žádná další konfigurace není vyžadována; knihovna interně zpracovává kódování obrázku.

## Krok 1: Vytvořte konzolový projekt a přidejte knihovnu

Otevřete terminál a spusťte:

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
dotnet add package Aspose.BarCode
```

Tím se vytvoří soubor `Program.cs`, ve kterém napíšeme logiku čárového kódu.

## Krok 2: Napište kód – jak nastavit šířku a vygenerovat Planet čárový kód

Otevřete `Program.cs` a nahraďte jeho obsah následujícím kompletním příkladem:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Data to encode – the same value is used for both images
        const string data = "123456";

        // -----------------------------------------------------------------
        // Part A: Filled‑bars version (default style)
        // -----------------------------------------------------------------
        // Step 2.1: Create a Planet barcode generator
        var filledGenerator = new BarcodeGenerator(EncodeTypes.Planet, data);

        // Step 2.2: How to set width – define the width of a single bar in pixels
        // The XDimension controls bar width; 4 pixels yields a clear, printable image
        filledGenerator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 2.3: Save the filled‑bars image (default is FilledBars = true)
        string filledPath = "PostalPlanetFilledBars.png";
        filledGenerator.Save(filledPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Filled‑bars barcode saved to {filledPath}");

        // -----------------------------------------------------------------
        // Part B: Empty‑bars version (unfilled style)
        // -----------------------------------------------------------------
        // Step 3.1: Re‑instantiate the generator for the same data
        var emptyGenerator = new BarcodeGenerator(EncodeTypes.Planet, data);

        // Step 3.2: How to set width again – required after re‑instantiation
        emptyGenerator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 3.3: How to make empty – disable the filled‑bars flag
        emptyGenerator.Parameters.Barcode.FilledBars = false;

        // Step 3.4: Save the empty‑bars image
        string emptyPath = "PostalPlanetEmptyBars.png";
        emptyGenerator.Save(emptyPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Empty‑bars barcode saved to {emptyPath}");

        // -----------------------------------------------------------------
        // Verification output
        // -----------------------------------------------------------------
        Console.WriteLine("Both barcodes generated successfully.");
    }
}
```

### Proč je každý krok důležitý

- **How to set width**: Vlastnost `XDimension.Pixels` přímo ovlivňuje fyzickou velikost každého pruhu. Volba hodnoty mezi 2 a 6 pixely vyvažuje čitelnost na obrazovce a kvalitu tisku.
- **How to make empty**: Nastavení `FilledBars = false` říká generátoru, aby kreslil pouze obrysy pruhů. Tento styl je užitečný pro tisk „světlo‑na‑tmavém“ nebo když chcete, aby se prosvítala textura papíru pod ním.
- **How to fill bars**: Výchozí `FilledBars = true` vytváří plné černé pruhy, což je standard pro většinu poštovních skenerů.
- **Generate Planet barcode**: Použití `EncodeTypes.Planet` vybírá konkrétní kódování požadované United States Postal Service (USPS) pro Planet čárové kódy.

## Krok 3: Sestavte a spusťte program

Z adresáře projektu spusťte:

```bash
dotnet run
```

Měli byste vidět výstup v konzoli podobný tomuto:

```
Filled‑bars barcode saved to PostalPlanetFilledBars.png
Empty‑bars barcode saved to PostalPlanetEmptyBars.png
Both barcodes generated successfully.
```

V projektovém adresáři se objeví dva soubory PNG:

- `PostalPlanetFilledBars.png` – plné černé pruhy (výchozí styl)
- `PostalPlanetEmptyBars.png` – obrysové pruhy (prázdný styl)

Otevřete je v libovolném prohlížeči obrázků a ověřte, že šířka pruhu odpovídá nastavení 4 pixelů a že prázdná verze zobrazuje nevyplněné pruhy.

## Časté otázky a okrajové případy

| Question | Answer |
|----------|--------|
| *Mohu použít jiný formát obrázku?* | Ano. Nahraďte `BarCodeImageFormat.Png` za `Jpeg`, `Bmp` nebo `Gif` podle potřeby. |
| *Co když se čárový kód stane příliš širokým pro můj štítek?* | Snižte `XDimension.Pixels` (např. na `2`) nebo zvýšte šířku modulu tiskárny štítků. |
| *Musím nastavit `Height` ručně?* | Knihovna automaticky vypočítá výšku na základě kódování. Můžete ji přepsat pomocí `Parameters.Barcode.BarHeight`. |
| *Je styl prázdných pruhů podporován na všech tiskárnách?* | Většina moderních termotiskáren podporuje jak plné, tak prázdné styly, ale ověřte to testovacím výtiskem, pokud používáte starší zařízení. |
| *Jak přidat čitelný popisek pod čárový kód?* | Použijte `Parameters.Caption` pro povolení a stylizaci popisku; nastavte `CaptionAbove` na `false`, aby se umístil pod čárový kód. |

## Profesionální tipy

- **Znovu použijte stejný generátor** pouze pokud zachováte všechny parametry identické. Změna `FilledBars` po uložení neovlivní již uložený obrázek, takže opětovná inicializace (jak je ukázáno) zaručuje čistý start.
- **Dávkové generování**: Zabalte kód do smyčky a měňte `data` v každé iteraci, abyste vytvořili sérii Planet čárových kódů pro hromadnou poštu.
- **Výkon**: Pro tisíce čárových kódů vytvořte jedinou instanci `BarcodeGenerator`, upravte `XDimension` a `FilledBars` podle potřeby a znovu použijte objekt, aby se snížily alokace paměti.

## Závěr

Nyní víte **jak nastavit šířku**, **jak vytvořit prázdné**, **jak vyplnit pruhy** a přesné kroky k **vygenerování Planet čárového kódu** pomocí Aspose.BarCode v C#. Kompletní, spustitelný příklad vytváří jak PNG soubory s plnými pruhy, tak s prázdnými pruhy, připravené k integraci do jakéhokoli workflow pro poštovní štítky.

Dále prozkoumejte související témata, jako je **jak přidat QR kódy na stejný štítek**, **přizpůsobení barev čárových kódů** nebo **vložení čárového kódu do PDF dokumentu**. Každé z nich staví na stejných základech, které jsou zde popsány. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Vytvořit Planet čárový kód jako obrázek v C# – Jak generovat poštovní čárový kód](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Jak vytvořit Code128 čárový kód s prázdnými pruhy v Javě](/barcode/english/java/image-manipulation/generating-barcode-empty-bars/)
- [Jak generovat obrázek čárového kódu v Javě s Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
---
category: general
date: 2026-08-19
description: Naučte se, jak v C# vytvořit soubor PNG s čárovým kódem a upravit jeho
  výšku, včetně toho, jak snadno generovat obrázky čárových kódů a měnit výšku čárového
  kódu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode png file
- how to generate barcode
- adjust barcode height
- change barcode height
language: cs
lastmod: 2026-08-19
og_description: Vytvořte PNG soubor s čárovým kódem v C# a naučte se, jak generovat
  obrázky čárových kódů, upravovat výšku čárového kódu a měnit výšku čárového kódu
  pro optimální skenování.
og_image_alt: barcode PNG file showing Databar OmniDirectional barcode at two heights
og_title: Vytvořte soubor PNG s čárovým kódem v C# – průvodce krok za krokem
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Learn how to generate a barcode PNG file in C# and adjust its height,
    covering how to generate barcode images and change barcode height easily.
  headline: How to create a barcode PNG file with adjustable height in C#
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`,
      `BarCodeImageFormat.Bmp`, etc.
    question: Can I generate other image formats (JPEG, BMP)?
  - answer: Serve the generated PNG via an HTTP endpoint or convert it to a Base64
      string and place it in an `<img>` tag’s `src` attribute.
    question: How do I embed the PNG in a web page?
  - answer: 'Use `generator.Parameters.Image.BackgroundColor = Color.White;` (or any
      `System.Drawing.Color`). ## Conclusion You now know how to **generate a barcode
      PNG file** in C# and precisely **adjust barcode height** to meet scanning or
      design requirements. By changing the `BarHeight.Pixels` property you ca'
    question: Is there a way to set the background color?
  type: FAQPage
tags:
- barcode
- C#
- image generation
title: Jak vytvořit PNG soubor s čárovým kódem s nastavitelnou výškou v C#
url: /cs/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit soubor PNG s čárovým kódem s nastavitelnou výškou v C#

Pokud potřebujete v C# vytvořit **soubor PNG s čárovým kódem**, tento návod vám přesně ukáže, jak na to. Uvidíte kompletní, spustitelný příklad, který demonstruje **jak generovat čárový kód** obrázky a jak **upravit výšku čárového kódu** pro různé případy použití.

Generování souboru PNG s čárovým kódem je běžná potřeba pro inventární systémy, pokladní terminály a jakoukoli aplikaci, která musí tisknout nebo zobrazovat strojově čitelná data. Na konci tohoto tutoriálu budete schopni změnit výšku čárového kódu, uložit více PNG souborů a pochopit vliv výšky na spolehlivost skenování.

## Požadavky

* .NET 6.0 SDK nebo novější nainstalováno  
* Visual Studio 2022 (nebo jakékoli IDE podporující .NET)  
* NuGet balíček **Aspose.BarCode for .NET** (ukázkový kód používá tuto knihovnu)  

Balíček můžete přidat z příkazové řádky:

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Bezplatná evaluační verze Aspose.BarCode funguje pro vývoj a testování. Pro produkci získejte licencovaný klíč.

## Instalace knihovny pro čárový kód

Prvním krokem je odkaz na knihovnu ve vašem projektu. Přidejte následující `using` direktivy na začátek vašeho C# souboru:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Tyto jmenné prostory vám poskytují přístup k `BarcodeGenerator`, `EncodeTypes` a `BarCodeImageFormat`.

## Vytvoření souboru PNG s čárovým kódem

Nyní vytvoříme instanci `BarcodeGenerator`, která vygeneruje **soubor PNG s čárovým kódem**. Příklad používá symbologii Databar OmniDirectional, ale můžete nahradit `EncodeTypes.DatabarOmniDirectional` libovolným podporovaným typem.

```csharp
// Step 1: Create a DataBar Omnidirectional generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Řetězec `"(01)12345678901231"` odpovídá formátu GS1 Application Identifier pro 14‑ciferný GTIN. Upravit data tak, aby odpovídala vašim vlastním identifikátorům produktu.

## Nastavení X‑dimenze (volitelné)

X‑dimenze určuje šířku jednoho modulu čárového kódu. Hodnota založená na pixelech vám poskytuje přesnou kontrolu nad velikostí obrázku.

```csharp
// Optional: Set the pixel size of the X‑dimension (module width)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Hodnota `2` pixely funguje dobře pro většinu displejů. Zvyšte ji, pokud potřebujete větší čárový kód při tisku.

## Úprava výšky čárového kódu a uložení souboru PNG s čárovým kódem

Vlastnost **BarHeight** řídí vertikální velikost čar. Změna této hodnoty vám umožní **upravit výšku čárového kódu** bez ovlivnění zakódovaných dat.

```csharp
// Step 2: Generate a 30‑pixel‑high barcode and save it as PNG
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Soubor `DatabarBarHeight30Pixels.png` je nyní **soubor PNG s čárovým kódem**, který má výšku 30 pixelů.  

Pro **změnu výšky čárového kódu** a vytvoření druhého obrázku stačí přiřadit novou hodnotu a znovu zavolat `Save`:

```csharp
// Step 3: Change the height to 60 pixels and save the new image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
barcodeGenerator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Nyní máte dva PNG soubory — jeden o výšce 30 px a druhý o výšce 60 px — což demonstruje, jak **upravit výšku čárového kódu** za běhu.

### Proč výška čárového kódu záleží

* **Čitelnost:** Skenery očekávají minimální výšku pro spolehlivé rozpoznání. Příliš krátký čárový kód může být přehlédnut, zejména na nízkokvalitních kamerách.
* **Estetika:** Přizpůsobení výšky čárového kódu okolním designovým prvkům vytváří čistší UI.
* **Tisková omezení:** Některé tiskárny štítků mají pevně dané výškové sloty; úprava výšky čárového kódu zajišťuje, že se vejde.

**Nejlepší praxe:** Udržujte výšku jako násobek X‑dimenze (např. 30 px při X‑dimenzi 2 px), aby byl zachován poměr a nedošlo k deformaci.

## Kompletní příklad

Níže je kompletní, samostatný program, který můžete vložit do konzolové aplikace a okamžitě spustit.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator with Databar OmniDirectional data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set a reasonable X‑dimension (module width)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First height: 30 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode as DatabarBarHeight30Pixels.png");

        // 4️⃣ Second height: 60 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode as DatabarBarHeight60Pixels.png");
    }
}
```

**Očekávaný výstup**

Spuštění programu vytvoří dva soubory v pracovním adresáři spustitelného souboru:

* `DatabarBarHeight30Pixels.png` – 30‑pixelový soubor PNG s čárovým kódem  
* `DatabarBarHeight60Pixels.png` – 60‑pixelový soubor PNG s čárovým kódem  

Otevřete kterýkoli PNG v libovolném prohlížeči obrázků; uvidíte jasný čárový kód Databar OmniDirectional připravený ke skenování.

## Okrajové případy a řešení problémů

| Situace | Co zkontrolovat | Doporučené řešení |
|-----------|---------------|-----------------|
| Čárový kód je rozmazaný | X‑dimenze je příliš nízká pro zvolenou výšku | Zvyšte `XDimension.Pixels` (např. z 2 na 3) |
| Skenování selže u nízkého čárového kódu | Výška pod minimem skeneru | Nastavte `BarHeight.Pixels` na alespoň 30 px (nebo dle specifikací skeneru) |
| Soubor PNG je prázdný nebo poškozený | Neplatná výstupní cesta nebo chybí oprávnění k zápisu | Použijte absolutní cestu nebo zajistěte, aby aplikace měla přístup k zápisu |
| Potřeba jiné symbologie | Aktuální `EncodeTypes` není vhodný | Nahraďte `EncodeTypes.DatabarOmniDirectional` jinou hodnotou enumu (např. `EncodeTypes.Code128`) |

## Často kladené otázky

**Q: Mohu generovat jiné formáty obrázků (JPEG, BMP)?**  
A: Ano. Nahraďte `BarCodeImageFormat.Png` za `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp` atd.

**Q: Jak vložit PNG do webové stránky?**  
A: Poskytněte vygenerovaný PNG přes HTTP endpoint nebo jej převeďte na Base64 řetězec a umístěte do atributu `src` značky `<img>`.

**Q: Existuje způsob, jak nastavit barvu pozadí?**  
A: Použijte `generator.Parameters.Image.BackgroundColor = Color.White;` (nebo libovolnou `System.Drawing.Color`).

## Závěr

Nyní víte, jak **vygenerovat soubor PNG s čárovým kódem** v C# a přesně **upravit výšku čárového kódu**, aby vyhovovala požadavkům na skenování nebo design. Změnou vlastnosti `BarHeight.Pixels` můžete **měnit výšku čárového kódu** za běhu a vytvořit více PNG souborů z jedné základny kódu.

Dále prozkoumejte další možnosti přizpůsobení, jako je barva popředí, okraje a přidání lidsky čitelného textu. Můžete také experimentovat s různými symbologiemi (`EncodeTypes.Code128`, `EncodeTypes.QR`) a rozšířit tak rozsah dat, která můžete kódovat.

Šťastné programování a ať vaše čárové kódy vždy skenují na první pokus!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto návodu. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak generovat a upravit výšku čárového kódu pro jednorozměrný Databar pomocí Aspose.BarCode pro .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Jak generovat čárový kód – jednorozměrné typy čárových kódů](/barcode/english/net/one-dimensional-barcode-types/)
- [Jak generovat Aztec čárový kód s vlastním poměrem stran pomocí Aspose.BarCode pro .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
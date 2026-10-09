---
category: general
date: 2026-10-08
description: Naučte se, jak vytvořit obrázek čárového kódu v C#, a zjistěte, jak upravit
  poměr stran pro DataBar stacked omni‑directional čárové kódy.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust aspect ratio
- Aspose.BarCode C#
- DataBar stacked omni‑directional
- barcode X‑dimension
language: cs
lastmod: 2026-10-08
og_description: Vytvořte obrázek čárového kódu v C# a naučte se, jak upravit poměr
  stran pro DataBar stacked omni‑directional čárové kódy s kompletním ukázkovým kódem.
og_image_alt: Result of create barcode image with aspect ratio 15 using Aspose.BarCode
og_title: Vytvořte obrázek čárového kódu v C# – průvodce krok za krokem
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  headline: How to create barcode image and adjust its aspect ratio in C#
  type: TechArticle
- description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  name: How to create barcode image and adjust its aspect ratio in C#
  steps:
  - name: Expected output
    text: 'After running the program you will find two PNG files in the execution
      directory:'
  - name: What if I need a different X‑dimension?
    text: You can change `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` to
      any integer greater than zero. For very high‑resolution output (e.g., 300 dpi),
      a value of 3‑4 pixels often yields clearer results.
  - name: How do I choose the right aspect ratio?
    text: 'The optimal ratio depends on the scanning environment: * **Low‑profile
      labels** – use a smaller ratio (e.g., 10‑15) to keep the barcode compact. *
      **Large shipping containers** – a higher ratio (e.g., 25‑35) improves readability
      from a distance. * **Regulatory requirements** – some standards mandate'
  - name: Can I generate other barcode formats with the same code?
    text: Yes. Replace `EncodeTypes.DatabarStackedOmniDirectional` with any other
      `EncodeTypes` value (e.g., `EncodeTypes.Code128`). The rest of the code—X‑dimension,
      aspect ratio (if applicable), and saving—remains the same.
  - name: What if I need to create the image in a different format?
    text: '`BarCodeImageFormat` supports PNG, JPEG, BMP, GIF, and TIFF. Just change
      the second argument of `Save`, for example:'
  - name: Next steps
    text: '* Explore other symbologies such as **Code128** or **QR Code** by swapping
      the `EncodeTypes` value. * Combine the barcode generation with PDF creation
      (e.g., using Aspose.PDF) to embed barcodes directly into invoices. * Experiment
      with dynamic aspect‑ratio selection based on label size—this extends '
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak vytvořit obrázek čárového kódu a upravit jeho poměr stran v C#
url: /cs/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit obrázek čárového kódu a upravit jeho poměr stran v C#

Pokud potřebujete **vytvořit obrázek čárového kódu** programově, tento průvodce vám ukáže kompletní, připravené řešení. Uvidíte přesně **jak upravit poměr stran** pro DataBar stacked omni‑directional čárový kód, požadavek, který se často objevuje v maloobchodě a logistických aplikacích.

V tomto tutoriálu se naučíte:
* Inicializovat Aspose.BarCode `BarcodeGenerator` pro symbologii DataBar stacked omni‑directional.  
* Nastavit X‑dimenzi (šířku modulu) v pixelech pro kontrolu tloušťky čáry.  
* Použít dva různé poměry stran a uložit každý výsledek jako PNG soubor.  
* Ověřit výstup a pochopit, proč je poměr stran důležitý.

Nejsou vyžadovány žádné externí nástroje – stačí knihovna Aspose.BarCode pro .NET a vývojové prostředí .NET 6 (nebo novější).

## Jak vytvořit obrázek čárového kódu pomocí Aspose.BarCode

Prvním krokem je vytvořit instanci generátoru s požadovanou symbologií a řetězcem dat. Výčtový typ `EncodeTypes.DatabarStackedOmniDirectional` říká Aspose.BarCode, aby vytvořil DataBar stacked omni‑directional čárový kód, který se široce používá pro aplikace GS1‑128.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a BarcodeGenerator for DataBar stacked omni‑directional.
        // The data string "(01)12345678901231" follows the GS1 Application Identifier format.
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Proč je to důležité:** Objekt `BarcodeGenerator` je vstupním bodem pro všechny úlohy tvorby čárových kódů. Tím, že předem určíte symbologii a surová data, zajistíte, že vygenerovaný obrázek bude vyhovovat standardu GS1.

## Nastavení X‑dimenze (šířka modulu)

X‑dimenze určuje šířku nejtenčí čáry (modulu). Větší X‑dimenze vede k silnějšímu čárovému kódu, což může být užitečné pro tiskárny s nízkým rozlišením.

```csharp
        // 2️⃣ Define the X‑dimension in pixels.
        // A value of 2 pixels provides a good balance between readability and file size.
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Proč je to důležité:** Úprava X‑dimenze je součástí procesu vizuálního ladění. Nemá vliv na kódovaná data, ale ovlivňuje spolehlivost skenování na různých zařízeních.

## Jak upravit poměr stran – první verze (15)

Poměr stran řídí vztah výšky k šířce DataBar čárového kódu. Vlastnost `DataBar.AspectRatio` přijímá celočíselné hodnoty; vyšší čísla vytvářejí vyšší čáry.

```csharp
        // 3️⃣ Set the aspect ratio to 15 and save the first image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Proč je to důležité:** Poměr stran 15 je běžná výchozí hodnota pro maloobchodní skenery. Výsledný PNG (`DatabarAspectRatio15.png`) bude mít vyšší vzhled, což může zlepšit úspěšnost skenování na přenosných zařízeních.

## Jak upravit poměr stran – druhá verze (30)

Možná budete potřebovat vyšší čárový kód pro konkrétní formáty štítků. Změna poměru stran je tak jednoduchá, jako přiřadit novou celočíselnou hodnotu před opětovným voláním `Save`.

```csharp
        // 4️⃣ Change the aspect ratio to 30 and save a second image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Proč je to důležité:** Demonstrací **jak upravit poměr stran** můžete generovat více obrázků čárových kódů ze stejného zdroje dat, aniž byste museli znovu vytvářet generátor. To snižuje spotřebu paměti a urychluje dávkové zpracování.

### Očekávaný výstup

Po spuštění programu najdete ve výkonném adresáři dva PNG soubory:

| Název souboru                  | Poměr stran | Popis vzhledu |
|-------------------------------|-------------|----------------|
| `DatabarAspectRatio15.png`    | 15          | Standardní výška, vhodná pro většinu pokladen. |
| `DatabarAspectRatio30.png`    | 30          | Vyšší čáry, užitečné pro velké štítky nebo tiskárny s nízkým rozlišením. |

Oba obrázky obsahují stejný kódovaný GTIN `(01)12345678901231`, ale vizuální proporce se liší podle nastaveného poměru stran.

## Časté otázky a řešení okrajových případů

### Co když potřebuji jinou X‑dimenzi?

Můžete změnit `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` na libovolné celé číslo větší než nula. Pro výstup s velmi vysokým rozlišením (např. 300 dpi) hodnota 3‑4 pixely často poskytuje jasnější výsledky.

### Jak si vybrat správný poměr stran?

Optimální poměr závisí na prostředí skenování:

* **Nízkoprofilové štítky** – použijte menší poměr (např. 10‑15), aby byl čárový kód kompaktní.
* **Velké přepravní kontejnery** – vyšší poměr (např. 25‑35) zlepšuje čitelnost z dálky.
* **Regulační požadavky** – některé standardy vyžadují minimální výšku; konzultujte specifikaci GS1 pro přesná čísla.

### Mohu generovat jiné formáty čárových kódů stejným kódem?

Ano. Nahraďte `EncodeTypes.DatabarStackedOmniDirectional` libovolnou jinou hodnotou `EncodeTypes` (např. `EncodeTypes.Code128`). Zbytek kódu – X‑dimenze, poměr stran (pokud je relevantní) a ukládání – zůstává stejný.

### Co když potřebuji vytvořit obrázek v jiném formátu?

`BarCodeImageFormat` podporuje PNG, JPEG, BMP, GIF a TIFF. Stačí změnit druhý argument metody `Save`, například:

```csharp
barcodeGenerator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
```

## Pro tip: opakované použití generátoru pro dávkové zpracování

Když musíte vytvořit desítky čárových kódů se stejným vizuálním nastavením, vytvořte generátor jednou, aktualizujte pouze vlastnost `CodeText` a opakovaně volajte `Save`. Tím se vyhnete režii spojené s opakovaným alokováním interních bufferů.

```csharp
// Example of batch creation
string[] gtins = { "(01)12345678901231", "(01)98765432109876", "(01)55555555555555" };
foreach (var gtin in gtins)
{
    barcodeGenerator.CodeText = gtin;
    barcodeGenerator.Save($"Barcode_{gtin.Substring(4, 6)}.png", BarCodeImageFormat.Png);
}
```

## Závěr

Nyní víte, jak **vytvořit obrázek čárového kódu** v C# pomocí Aspose.BarCode a přesně **jak upravit poměr stran** pro DataBar stacked omni‑directional symboly. Ovládáním X‑dimenze a poměru stran můžete vytvářet čárové kódy, které splňují jakékoli požadavky na skenování nebo rozvržení, a přitom zůstává implementace jednoduchá a udržovatelná.

### Další kroky

* Prozkoumejte další symbologie, jako jsou **Code128** nebo **QR Code**, výměnou hodnoty `EncodeTypes`.  
* Kombinujte generování čárových kódů s tvorbou PDF (např. pomocí Aspose.PDF) a vložte čárové kódy přímo do faktur.  
* Experimentujte s dynamickým výběrem poměru stran na základě velikosti štítku – to rozšiřuje vzor **jak upravit poměr stran** na plnohodnotný nástroj pro návrh štítků.

Neváhejte upravit ukázkový kód, sdílet své výsledky nebo klást doplňující otázky v komentářích. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vytvořit databar stacked čárový kód v C# s Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [Jak vytvořit obrázek čárového kódu s Aspose.Barcode v C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [Jak upravit velikost čárového kódu – poměr stran Codablock F s Aspose.BarCode pro .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
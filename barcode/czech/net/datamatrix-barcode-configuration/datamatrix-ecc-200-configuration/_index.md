---
date: 2026-08-02
description: Naučte se, jak vytvořit DataMatrix čárový kód, generovat datamatrix a
  prozkoumat high density barcode generation s Aspose.BarCode pro .NET projekty.
keywords:
- create datamatrix barcode
- high density barcode
- generate datamatrix barcode
- barcode generation asp.net
- temporary aspose license
lastmod: 2026-08-02
linktitle: Konfigurace DataMatrix ECC 200
og_description: Vytvořte DataMatrix čárový kód pomocí Aspose.BarCode pro .NET. Tento
  tutoriál ukazuje high density barcode generation, temporary Aspose license setup
  a step‑by‑step C# code.
og_image_alt: Guide showing C# code to create a DataMatrix barcode using Aspose.BarCode
og_title: Vytvořte DataMatrix čárový kód – Aspose.BarCode .NET průvodce
schemas:
- author: Aspose
  dateModified: '2026-08-02'
  description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  headline: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  name: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  steps:
  - name: Initialize the Barcode Generator
    text: '`BarcodeGenerator` is Aspose.BarCode''s core class that creates and renders
      barcodes. It accepts the symbology type and the text to encode. Replace `"Your
      Directory Path"` with the folder where you’d like the image saved.'
  - name: Set XDimension and ECC Type
    text: '`XDimension` defines the pixel size of each DataMatrix module, while `DataMatrixEcc`
      selects the error‑correction level. ECC 200 provides the highest correction
      capability for this symbology. Adjust the pixel value if you need larger or
      smaller modules; typical values are 4‑6 px for on‑screen displa'
  - name: Generate and Save the Barcode Image
    text: The `Save` method writes the barcode to a file. You can choose PNG, JPEG,
      or TIFF by passing the corresponding `BarCodeImageFormat` enum value. Switch
      `BarCodeImageFormat.Png` to `BarCodeImageFormat.Jpeg` or `BarCodeImageFormat.Tiff`
      if your workflow requires a different format.
  type: HowTo
- questions:
  - answer: Yes, the same API works in .NET Core, .NET 5, and .NET 6 projects.
    question: Can I use this code in a .NET Core console application?
  - answer: Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg` in the
      `Save` call.
    question: How do I change the output format to JPEG?
  - answer: Yes – generate the image first, then add it to a PDF using Aspose.PDF
      or any PDF library.
    question: Is it possible to embed the barcode directly into a PDF?
  - answer: DataMatrix supports UTF‑8; simply pass the Unicode string to the generator
      as shown.
    question: What if I need to encode Unicode characters?
  - answer: Absolutely – place the generation code inside a loop and change the data/value
      for each iteration.
    question: Does the library support batch generation of multiple barcodes?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- .NET barcode generation
- C# barcode tutorial
title: Jak vytvořit DataMatrix čárový kód (ECC 200) pomocí Aspose.BarCode pro .NET
url: /cs/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit DataMatrix čárový kód (ECC 200) pomocí Aspose.BarCode pro .NET

## Úvod

V tomto průvodci **vytvoříte DataMatrix čárový kód** (ECC 200) pomocí Aspose.BarCode pro .NET. Ať už vytváříte sledovač zásob, pokladní systém nebo automatizujete pracovní postupy s dokumenty, vysoce hustý čárový kód může uložit spoustu dat v malém prostoru. Provedeme vás každým konfiguračním krokem, vysvětlíme, proč je každé nastavení důležité, a poskytneme připravené úryvky kódu v C#.

## Rychlé odpovědi
- **Jaká knihovna je nejlepší pro DataMatrix v .NET?** Aspose.BarCode for .NET  
- **Jakou úroveň ECC poskytuje ECC 200?** Vysoce hustá korekce chyb pro spolehlivé skenování.  
- **Potřebuji licenci pro spuštění ukázky?** Dočasná licence stačí pro hodnocení; plná licence je vyžadována pro produkci.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Mohu výstupně generovat PNG, JPEG nebo TIFF?** Ano – metoda `Save` podporuje více formátů obrázků.

## Co je DataMatrix ECC 200?

DataMatrix ECC 200 je vysoce hustý dvourozměrný čárový kód, který může uložit až 2 335 alfanumerických znaků nebo 1 556 bajtů binárních dat v kompaktním čtvercovém nebo obdélníkovém vzoru. Používá Reed‑Solomon korekci chyb k obnovení ztracených nebo poškozených modulů, což ho činí ideálním pro aplikace jako označování součástí letectví, farmaceutické značení a logistiku, kde je spolehlivost kritická.

## Proč použít generování čárových kódů Aspose?

Aspose.BarCode podporuje **30+ symbologií**, může vykreslovat obrázky až do 10 000 × 10 000 px bez načítání celého souboru do paměti a poskytuje deterministický výstup napříč Windows, Linux a macOS. Jeho API vám umožňuje řídit každý parametr vykreslování, což z něj dělá nejflexibilnější volbu pro **generování čárových kódů ASP.NET** scénáře.

## Požadavky

1. **Vývojové prostředí** – Visual Studio s nainstalovaným odpovídajícím .NET frameworkem.  
2. **Aspose.BarCode pro .NET** – Stáhněte a nainstalujte z webu, [zde](https://releases.aspose.com/barcode/net/).  
3. **Licence** – Získejte dočasnou licenci pro testování [zde](https://purchase.aspose.com/temporary-license/).  
4. **Základy C#** – Znalost syntaxe C# a struktury projektu.

Nyní, když máme základy pokryté, přejděme k nastavení DataMatrix ECC 200.

## Importování jmenných prostorů

`Aspose.BarCode.Generation` jmenný prostor obsahuje všechny třídy potřebné pro tvorbu čárových kódů. Importujte jej na začátku souboru:

```csharp
using Aspose.BarCode.Generation;
```

## Jak vytvořit DataMatrix čárový kód (ECC 200) krok za krokem

Pro vytvoření DataMatrix ECC 200 čárového kódu stačí načíst data, která chcete kódovat, nastavit několik klíčových parametrů na `BarcodeGenerator` a poté zavolat `Save` pro zápis souboru obrázku. Tento tříkrokový proces zajišťuje kódování, korekci chyb a výběr výstupního formátu, což vám umožní integrovat tvorbu čárových kódů do jakékoli .NET aplikace s minimálním kódem.

### Krok 1: Inicializace generátoru čárových kódů

`BarcodeGenerator` je hlavní třída Aspose.BarCode, která vytváří a vykresluje čárové kódy. Přijímá typ symbologie a text k zakódování.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixEcc200:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Your code goes here
}
```

Nahraďte `"Your Directory Path"` složkou, kam chcete obrázek uložit.

### Krok 2: Nastavení XDimension a typu ECC

`XDimension` určuje velikost pixelu každého modulu DataMatrix, zatímco `DataMatrixEcc` vybírá úroveň korekce chyb. ECC 200 poskytuje nejvyšší schopnost korekce pro tuto symbologii.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 4;
gen.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

Upravte hodnotu pixelu, pokud potřebujete větší nebo menší moduly; typické hodnoty jsou 4‑6 px pro zobrazení na obrazovce a 8‑10 px pro tištěné štítky.

### Krok 3: Generování a uložení obrázku čárového kódu

Metoda `Save` zapíše čárový kód do souboru. Můžete zvolit PNG, JPEG nebo TIFF předáním odpovídající hodnoty výčtu `BarCodeImageFormat`.

```csharp
gen.Save($"{path}DataMatrixEcc200.png", BarCodeImageFormat.Png);
```

Změňte `BarCodeImageFormat.Png` na `BarCodeImageFormat.Jpeg` nebo `BarCodeImageFormat.Tiff`, pokud váš pracovní postup vyžaduje jiný formát.

## Časté problémy a řešení

| Příznak | Pravděpodobná příčina | Oprava |
|---------|-----------------------|--------|
| Čárový kód je rozmazaný | XDimension je příliš nízký | Zvyšte `XDimension.Pixels` na 6‑8 |
| Skenování selhává na mobilu | Špatná úroveň ECC | Ujistěte se, že `DataMatrixEcc = DataMatrixEccType.Ecc200` |
| Soubor nebyl vytvořen | Neplatný řetězec cesty | Použijte absolutní cestu nebo zajistěte, že složka existuje |

## Často kladené otázky

**Q: Můžu použít tento kód v .NET Core konzolové aplikaci?**  
A: Ano, stejné API funguje v projektech .NET Core, .NET 5 a .NET 6.

**Q: Jak změním výstupní formát na JPEG?**  
A: Nahraďte `BarCodeImageFormat.Png` za `BarCodeImageFormat.Jpeg` v volání `Save`.

**Q: Je možné vložit čárový kód přímo do PDF?**  
A: Ano – nejprve vygenerujte obrázek a poté jej přidejte do PDF pomocí Aspose.PDF nebo jakékoli PDF knihovny.

**Q: Co když potřebuji kódovat Unicode znaky?**  
A: DataMatrix podporuje UTF‑8; stačí předat Unicode řetězec generátoru, jak je ukázáno.

**Q: Podporuje knihovna hromadné generování více čárových kódů?**  
A: Rozhodně – umístěte kód generování do smyčky a pro každou iteraci změňte data/hodnotu.

## Závěr

Probrali jsme vše, co potřebujete k **vytvoření DataMatrix čárového kódu** (ECC 200) s Aspose.BarCode pro .NET: od požadavků a importu jmenných prostorů po nastavení X‑dimenze, výběr úrovně ECC a uložení obrázku v preferovaném formátu. Experimentujte s mnoha dalšími vlastnostmi – jako jsou okraj, barva pozadí a rotace – abyste doladili výstup pro váš konkrétní případ použití.

Pokud narazíte na jakékoli potíže, komunita je připravena pomoci na [fóru Aspose.BarCode](https://forum.aspose.com/c/barcode/13). Šťastné programování!

---

**Poslední aktualizace:** 2026-08-02  
**Testováno s:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Jak generovat DataMatrix ECC 000-140 čárové kódy s Aspose.BarCode pro .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-000-140-configuration/)
- [Jak číst DataMatrix čárové kódy s Aspose.BarCode pro .NET](/barcode/net/datamatrix-barcode-reading/)
- [Vytvořit čárový kód PNG – Poměr stran DataMatrix – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
---
category: general
date: 2026-09-07
description: Vygenerujte čárový kód PDF417 v C# a naučte se, jak nastavit rozměry
  čárového kódu pro přesné řízení. Postupujte podle tohoto průvodce krok za krokem
  a vytvořte PNG obrázek.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- how to set barcode dimensions
language: cs
lastmod: 2026-09-07
og_description: Vygenerujte čárový kód PDF417 v C# a naučte se, jak nastavit rozměry
  čárového kódu. Tento tutoriál ukazuje kompletní, spustitelný příklad.
og_image_alt: Generated PDF417 barcode image with custom dimensions
og_title: Vytvořte čárový kód PDF417 v C# – kompletní průvodce s rozměry
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  headline: How to generate PDF417 barcode in C# with custom dimensions
  type: TechArticle
- description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  name: How to generate PDF417 barcode in C# with custom dimensions
  steps:
  - name: Expected output
    text: '- **File:** `Pdf417Layout.png` (PNG, lossless) - **Dimensions:** Determined
      by `XDimension` (2 px) × (columns × rows) matrix - **Content:** A scannable
      PDF417 barcode encoding the Unicode string `Åspóse.Barcóde©`'
  - name: What if I need a larger image for printing?
    text: Increase `XDimension.Pixels` to 4 or 5. Larger values produce a higher‑resolution
      barcode but also increase file size.
  - name: Can I encode more data than the example string?
    text: Yes. PDF417 can hold up to 1,850 characters. Just replace the text argument
      in the `BarcodeGenerator` constructor. If the data exceeds the matrix capacity,
      the library automatically adds extra rows.
  - name: How does error correction work?
    text: 'PDF417 includes built‑in error correction. You can adjust its level via:'
  - name: What if the barcode appears blurry on screen?
    text: 'Make sure the output image’s DPI matches the display environment. You can
      set DPI when saving:'
  - name: Next steps
    text: '- Explore **how to generate PDF417 barcode** with different image formats
      (JPEG, BMP). - Learn **how to set barcode dimensions** dynamically based on
      user input or device DPI. - Integrate the barcode generation into an ASP.NET
      Core API to serve barcodes on demand.'
  type: HowTo
tags:
- barcode generation
- PDF417
- C#
title: Jak vygenerovat čárový kód PDF417 v C# s vlastními rozměry
url: /cs/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generovat PDF417 čárový kód v C# s vlastními rozměry

Pokud potřebujete **generovat PDF417 čárový kód** v .NET aplikaci, tento návod vám ukáže přesně, jak na to. Uvidíte kompletní, spustitelný příklad, který vytvoří PNG obrázek a umožní vám nastavit rozměry čárového kódu.

Generování PDF417 čárového kódu je běžná potřeba pro inventární systémy, palubní vstupenky a zabezpečené dokumenty. V tomto tutoriálu se také naučíte **jak nastavit rozměry čárového kódu**, aby výstup odpovídal vašim požadavkům na rozvržení.

## Předpoklady

Než začnete, ujistěte se, že máte:

- .NET 6.0 SDK nebo novější nainstalovaný  
- Visual Studio 2022 (nebo jakékoli IDE kompatibilní s C#)  
- NuGet balíček **Aspose.BarCode for .NET** (nebo jakoukoli kompatibilní knihovnu podporující PDF417)  

Balíček můžete přidat následujícím příkazem:

```bash
dotnet add package Aspose.BarCode
```

## Krok 1: Vytvoření generátoru PDF417 čárového kódu

Prvním krokem je vytvořit instanci `BarcodeGenerator` s typem `EncodeTypes.Pdf417` a textem, který chcete zakódovat. Objekt generátoru obsahuje všechna nastavení pro čárový kód.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");
```

**Proč je to důležité:** Výčtový typ `EncodeTypes.Pdf417` říká knihovně, aby použila symbologii PDF417, která podporuje velké objemy dat a korekci chyb. Textový řetězec může obsahovat Unicode znaky, takže můžete zakódovat mezinárodní symboly bez dalšího úsilí.

## Krok 2: Jak nastavit rozměry čárového kódu

Ovládání velikosti jednotlivých modulů (nejmenší černobílý čtvereček) určuje celkové rozlišení obrázku. Vlastnost `XDimension.Pixels` nastavuje šířku jednoho modulu v pixelech.

```csharp
        // Step 2: Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Proč je to důležité:** Větší `XDimension` vede k obrázku s vyšším rozlišením, což je užitečné pro tisk nebo skenování z větší vzdálenosti. Naopak menší hodnota snižuje velikost souboru pro použití na webu.

## Krok 3: Definování rozvržení PDF417 (sloupce a řádky)

PDF417 vám umožňuje ovlivnit tvar matice zadáním počtu sloupců a řádků. To může ovlivnit čitelnost a fyzickou velikost čárového kódu.

```csharp
        // Step 3: Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

**Proč je to důležité:** Úpravou sloupců a řádků můžete čárový kód umístit do konkrétního prostoru nebo splnit požadavky skeneru na poměr stran. Knihovna automaticky přidá odsazení, pokud data nevyplní matici úplně.

## Krok 4: Uložení čárového kódu jako PNG obrázek

Nakonec zapíšete vygenerovaný čárový kód do souboru. PNG zachovává bezztrátovou kvalitu, což je ideální pro další zpracování.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

Po spuštění programu se v výstupní složce projektu objeví soubor `Pdf417Layout.png`. Obrázek vypadá takto:

![Generated PDF417 barcode image with custom dimensions](og_image_placeholder.png)

*Alt text obrázku: Vygenerovaný obrázek čárového kódu PDF417 s vlastními rozměry*  

**Proč je to důležité:** Uložení jako PNG zajišťuje, že přesně nastavené rozměry modulů zůstanou zachovány, což je klíčové pro následné skenovací aplikace.

## Kompletní příklad v jednom bloku

Níže je celý program, který můžete zkopírovat, vložit a spustit bez úprav (kromě výstupní cesty, pokud chcete).

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

### Očekávaný výstup

- **Soubor:** `Pdf417Layout.png` (PNG, bezztrátový)  
- **Rozměry:** Určeny pomocí `XDimension` (2 px) × (sloupce × řádky) matice  
- **Obsah:** Skenovatelný PDF417 čárový kód kódující Unicode řetězec `Åspóse.Barcóde©`

## Časté otázky a okrajové případy

### Co když potřebuji větší obrázek pro tisk?

Zvyšte `XDimension.Pixels` na 4 nebo 5. Větší hodnoty vytvoří čárový kód s vyšším rozlišením, ale také zvětší velikost souboru.

### Můžu zakódovat více dat než v ukázkovém řetězci?

Ano. PDF417 pojme až 1 850 znaků. Stačí nahradit argument textu v konstruktoru `BarcodeGenerator`. Pokud data přesáhnou kapacitu matice, knihovna automaticky přidá další řádky.

### Jak funguje korekce chyb?

PDF417 obsahuje vestavěnou korekci chyb. Její úroveň můžete upravit pomocí:

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // 0‑8, higher = more correction
```

Vyšší úrovně zvyšují odolnost, ale zvětšují velikost čárového kódu.

### Co když se čárový kód na obrazovce jeví rozmazaný?

Ujistěte se, že DPI výstupního obrázku odpovídá prostředí, ve kterém je zobrazován. DPI můžete nastavit při ukládání:

```csharp
barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png, 300);
```

## Profesionální tipy

- **Pro tip:** Vždy testujte vygenerovaný čárový kód na skutečném skeneru, který hodláte používat. Různá zařízení mají odlišnou toleranci pro velikost modulů a klidové zóny.  
- **Dejte pozor na:** Velmi malé hodnoty `XDimension` (< 1 px) se mohou na obrazovkách s vysokým DPI zobrazit jako neviditelné čáry.  
- **Tip pro webové aplikace:** Podávejte PNG s hlavičkou `Cache-Control: public, max-age=86400`, aby se snížila zátěž opakovaného generování.

## Závěr

Nyní víte, jak **generovat PDF417 čárový kód** v C# a přesně **nastavit rozměry čárového kódu**, aby vyhovoval jakémukoli požadavku. Kompletní, spustitelný příklad ukazuje vytvoření PNG obrázku s vlastním rozvržením sloupců/řádků a velikostí modulů, připraveného k tisku nebo digitální distribuci.

### Další kroky

- Prozkoumejte **jak generovat PDF417 čárový kód** v různých formátech obrázků (JPEG, BMP).  
- Naučte se **jak dynamicky nastavit rozměry čárového kódu** na základě vstupu uživatele nebo DPI zařízení.  
- Integrovat generování čárového kódu do ASP.NET Core API pro poskytování čárových kódů na vyžádání.

Neváhejte experimentovat s dalšími nastaveními PDF417, jako jsou korekce chyb, okraje a barvy. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy ve vlastních projektech.

- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Generate PDF417 Barcode in C# – Complete Guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
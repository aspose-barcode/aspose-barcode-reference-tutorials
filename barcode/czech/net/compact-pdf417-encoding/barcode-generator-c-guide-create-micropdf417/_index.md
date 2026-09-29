---
category: general
date: 2026-09-29
description: Průvodce generátorem čárových kódů v C# ukazuje, jak vytvořit čárový
  kód MicroPdf417, změnit rozměry, nastavit sloupce a přizpůsobit velikost čárového
  kódu pomocí několika řádků.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- how to generate barcode
- how to change dimensions
- how to set columns
- customize barcode size
language: cs
lastmod: 2026-09-29
og_description: Průvodce generátorem čárových kódů v C# ukazuje, jak vygenerovat čárový
  kód MicroPdf417, změnit rozměry, nastavit sloupce a přizpůsobit velikost čárového
  kódu během několika řádků.
og_image_alt: Screenshot of a MicroPdf417 barcode generated with a C# barcode generator
og_title: Průvodce generátorem čárových kódů v C# – vytvořte a přizpůsobte MicroPdf417
schemas:
- author: GroupDocs
  dateModified: '2026-09-29'
  description: Barcode generator C# guide shows how to generate a MicroPdf417 barcode,
    change dimensions, set columns, and customize barcode size in just a few lines.
  headline: 'Barcode generator C# guide: create MicroPdf417'
  type: TechArticle
tags:
- barcode
- C#
- MicroPdf417
- barcode generation
title: 'Průvodce generátorem čárových kódů v C#: vytvořte MicroPdf417'
url: /cs/net/compact-pdf417-encoding/barcode-generator-c-guide-create-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Průvodce generátorem čárových kódů C#: vytvoření MicroPdf417

Pokud potřebujete **barcode generator C#** pro váš .NET projekt, tento tutoriál vás provede vytvořením čárového kódu MicroPdf417 od nuly. Naučíte se **jak generovat čárový kód**, měnit rozměry, nastavit sloupce a **přizpůsobit velikost čárového kódu** bez námahy.

MicroPdf417 je kompaktní 2‑D symbologie, která se dobře hodí pro označování malých součástí, vstupenek nebo inventárních štítků. Na konci tohoto průvodce budete mít kompletní spustitelnou konzolovou aplikaci, která vytvoří PNG obrázek čárového kódu, a pochopíte, jak každý parametr ovlivňuje konečnou velikost.

## Požadavky

Než začnete, ujistěte se, že máte:

* .NET 6.0 SDK nebo novější (kód také funguje s .NET Framework 4.7+)
* IDE kompatibilní s C# (Visual Studio, VS Code, Rider, atd.)
* Balíček **GroupDocs.Barcode** NuGet – nainstalujte jej pomocí  

  ```bash
  dotnet add package GroupDocs.Barcode
  ```

Nejsou vyžadovány žádné další externí nástroje; knihovna se postará o kódování, vykreslování a ukládání souborů.

## Barcode generator C#: inicializace generátoru

Prvním krokem je vytvořit instanci `BarcodeGenerator` a specifikovat symbologii (`EncodeTypes.MicroPdf417`) spolu s daty, která chcete kódovat.

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1 – create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // Subsequent configuration steps go here...

            // Save the final image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

**Proč je to důležité:**  
`BarcodeGenerator` je vstupním bodem pro všechny operace s čárovými kódy. Konstruktor sváže zvolený **EncodeTypes** (MicroPdf417) s řetězcem surových dat. Knihovna automaticky zpracovává Unicode znaky jako “Å” a “©”, takže není potřeba žádná další logika kódování.

## Jak změnit rozměry čárového kódu

Čitelnost čárového kódu silně závisí na šířce modulu (X‑rozměr). Nastavení na vyšší počet pixelů způsobí širší pruhy a obrázek bude snáze skenovatelný, zejména na nízkorozlišovacích displejích.

```csharp
// Step 2 – adjust the X‑dimension (module width) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Vysvětlení:**  
`XDimension.Pixels` řídí šířku jednoho modulu čárového kódu. Výchozí hodnota je 1 pixel, což může na monitorech s vysokým DPI vypadat tence. Zvýšením na 2 pixely se celková šířka zdvojnásobí, aniž by to ovlivnilo kódovaná data.

**Tip:** Pokud plánujete tisk čárového kódu při 300 dpi, hodnota 3 nebo 4 pixely často poskytuje nejlepší rovnováhu mezi velikostí a spolehlivostí skenování.

## Jak nastavit sloupce pro kontrolu velikosti

MicroPdf417 vám umožňuje určit počet sloupců (až 4). Méně sloupců vede k vyššímu čárovému kódu; více sloupců jej rozšiřuje, ale zkracuje. Úprava této hodnoty je hlavním způsobem, jak **přizpůsobit velikost čárového kódu**.

```csharp
// Step 3 – set the maximum number of columns (4 is the limit for MicroPdf417)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Proč to funguje:**  
Vlastnost `Pdf417.Columns` je sdílena napříč všemi symbologiemi založenými na PDF417, včetně MicroPdf417. Nastavením na maximum (4) se data rozprostřou po nejširším možném rozložení, čímž se sníží celková výška. Pokud potřebujete kompaktnější výšku, snižte počet sloupců na 2 nebo 3.

**Hraniční případ:** Když je řetězec dat dlouhý, knihovna může automaticky zvýšit počet řádků, aby obsah pojmula, bez ohledu na počet sloupců. Pro předvídatelnou velikost udržujte payload pod 50 znaky.

## Přizpůsobení velikosti čárového kódu pro různé výstupy

Kromě X‑rozměru a sloupců můžete ovlivnit konečnou velikost obrázku výběrem vhodného formátu a DPI. PNG je bezztrátový, ideální pro webové zobrazení, zatímco BMP nebo TIFF mohou být vhodnější pro vysoce kvalitní tisk.

```csharp
// Step 4 – save as PNG (lossless) with default 96 dpi
generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
```

Pokud potřebujete vyšší DPI, můžete jej nastavit explicitně:

```csharp
generator.Parameters.Image.DpiX = 300;
generator.Parameters.Image.DpiY = 300;
generator.Save("MicroPdf417_300dpi.png", BarCodeImageFormat.Png);
```

**Výsledek:** Uložený PNG soubor obsahuje ostrý MicroPdf417 čárový kód, který respektuje nastavené rozměry. Otevřete soubor v libovolném prohlížeči obrázků a ověřte vizuální velikost.

### Očekávaný výstup

Spuštěním programu se vytvoří soubor pojmenovaný **MicroPdf417.png** (nebo **MicroPdf417_300dpi.png**, pokud jste nastavili DPI). Čárový kód bude vypadat podobně jako ilustrace níže:

![Barcode generator C# output showing a MicroPdf417 PNG](barcode-micro-pdf417.png)

*Alt text:* *Výstup Barcode generator C# zobrazující MicroPdf417 PNG*

Naskenováním obrázku standardním 2‑D čtečkou čárových kódů získáte původní řetězec `Åspóse.Barcóde©`.

## Úplný zdrojový kód pro rychlé kopírování

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // 2️⃣ Change dimensions – make modules 2 pixels wide
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set columns – use the maximum of 4 for a wider, shorter barcode
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // (Optional) Increase DPI for high‑resolution output
            // generator.Parameters.Image.DpiX = 300;
            // generator.Parameters.Image.DpiY = 300;

            // 4️⃣ Save the barcode as a PNG image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

Zkopírujte kód do nového konzolového projektu, obnovte NuGet balíčky a spusťte `dotnet run`. Konzole potvrdí umístění obrázku a v adresáři projektu uvidíte vygenerovaný čárový kód.

## Časté otázky a řešení problémů

| Otázka | Odpověď |
|----------|--------|
| **Co když čárový kód vypadá rozmazaně?** | Zvyšte `XDimension.Pixels` nebo DPI (`Parameters.Image.DpiX/Y`). Obě možnosti zvětší moduly a zlepší vizuální věrnost. |
| **Mohu použít jiný formát obrázku?** | Ano. Nahraďte `BarCodeImageFormat.Png` za `Jpeg`, `Bmp` nebo `Tiff`. PNG zůstává nejbezpečnější volbou pro bezztrátovou kvalitu. |
| **Moje data obsahují emoji—budou zakódována?** | MicroPdf417 podporuje UTF‑8, takže většina emoji se zakóduje správně. Pokud narazíte na chyby, ověřte, že řetězec je správně normalizován (`System.Text.Encoding.UTF8`). |
| **Jak mohu generovat jiné symbologie?** | Změňte `EncodeTypes.MicroPdf417` na jakoukoli jinou hodnotu z `EncodeTypes` (


## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak generovat obrázek čárového kódu v C# – Průvodce MicroPdf417](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/)
- [Jak generovat PDF417 čárový kód v C# s vlastními rozměry](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
---
category: general
date: 2026-09-16
description: Vytvořte poštovní čárový kód v C# a naučte se nastavit šířku a změnit
  výšku čárového kódu pro dokonalé skenování.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode
- how to set width
- change barcode height
- barcode generator C#
- postal barcode image
language: cs
lastmod: 2026-09-16
og_description: Vytvořte poštovní čárový kód v C# pomocí tohoto krok‑za‑krokem průvodce,
  který ukazuje, jak nastavit šířku a změnit výšku čárového kódu pro spolehlivé poštovní
  skenování.
og_image_alt: C# generated postal barcode image with custom width and height
og_title: Vytvořte poštovní čárový kód s vlastní šířkou a výškou v C#
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Create postal barcode in C# and learn how to set width and change barcode
    height for perfect scanning.
  headline: Create postal barcode with custom width and height in C#
  type: TechArticle
tags:
- barcode
- C#
- postal
title: Vytvořte poštovní čárový kód s vlastní šířkou a výškou v C#
url: /cs/python-java/general/create-postal-barcode-with-custom-width-and-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořte poštovní čárový kód s vlastní šířkou a výškou v C#

Pokud potřebujete **vytvořit poštovní čárový kód** v C#, tento návod vám ukáže, jak generovat čárové kódy Planet a RM4SCC s přesnými rozměry. Po přečtení prvních dvou vět budete znát přesná volání API pro **nastavení šířky** a **změnu výšky čárového kódu**, takže můžete vytvářet skenovatelné kódy, které odpovídají specifikacím poštovních služeb.

Dozvíte se:
* Jak vytvořit generátor čárových kódů pro formáty Planet a RM4SCC.  
* Jaká je přesná vlastnost pro **nastavení šířky** (X‑dimension) v pixelech.  
* Jak **změnit výšku čárového kódu** pro konkrétní typ kódu.  
* Kde jsou uložené vygenerované PNG soubory a jak vypadají.

Jedinou podmínkou je odkaz na knihovnu `Aspose.BarCode` (nebo podobnou), která poskytuje třídu `BarcodeGenerator`. Žádné další NuGet balíčky nejsou potřeba nad rámec samotného SDK pro čárové kódy.

---

## Vytvořte poštovní čárový kód s vlastními rozměry

Nejprve přidejte požadované `using` direktivy a vytvořte jednoduchý konzolový program. Kompletní, spustitelný příklad je uveden po podrobném vysvětlení.

```csharp
using System;
using Aspose.BarCode.Generation;   // Namespace for BarcodeGenerator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Generate a Planet barcode (height auto‑determined)
            var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            // Step 2: Set the module width (X‑dimension) to 4 px
            planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            // Step 3: Save the Planet barcode image
            planetGenerator.Save("PostalPlanetBarWidth4.png", BarCodeImageFormat.Png);

            // Step 4: Generate an RM4SCC barcode (requires explicit height)
            var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            // Step 5: Apply the same X‑dimension (width) of 4 px
            rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            // Step 6: Fix the barcode height to 100 px
            rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
            // Step 7: Save the RM4SCC barcode image
            rm4sccGenerator.Save("PostalRM4SCCHeight100.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcodes generated successfully.");
        }
    }
}
```

**Proč to funguje:**  
* `EncodeTypes.Planet` a `EncodeTypes.RM4SCC` říkají generátoru, podle jakého poštovního standardu má pracovat.  
* `XDimension.Pixels` řídí **šířku** každého modulu čárového kódu (nejmenší černý/bílý prvek).  
* `BarHeight.Pixels` vám umožňuje **změnit výšku čárového kódu** u formátů, které výšku nepočítají automaticky, například u RM4SCC.

Po spuštění programu se vytvoří dva PNG soubory v pracovním adresáři spustitelného souboru:
* `PostalPlanetBarWidth4.png` – čárový kód Planet s šířkou modulu 4 px.  
* `PostalRM4SCCHeight100.png` – čárový kód RM4SCC s šířkou 4 px a pevnou výškou 100 px.

---

## Jak nastavit šířku poštovního čárového kódu

Krok **nastavení šířky** je stejný pro každý podporovaný poštovní formát:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = desiredWidth;
```

* `desiredWidth` je celé číslo představující velikost jednoho modulu v pixelech.  
* Typická hodnota pro poštovní čárové kódy je **4 px**, ale můžete ji zvýšit pro tisk ve vyšším rozlišení.  

**Tip:** Při tisku na tiskárně s řízeným DPI vynásobte šířku v pixelech DPI faktorem tiskárny, abyste zachovali fyzické rozměry.

---

## Změna výšky čárového kódu pro poštovní kód RM4SCC

Pouze podmnožina poštovních symbologií (např. RM4SCC) vyžaduje explicitní výšku. Použijte vlastnost **změna výšky čárového kódu**:

```csharp
generator.Parameters.Barcode.BarHeight.Pixels = desiredHeight;
```

* `desiredHeight` je celková výška obrázku čárového kódu, nikoli výška jednoho modulu.  
* Nastavením `BarHeight` na **100 px** získáte vysoký, snadno čitelný kód, který splňuje mnoho směrnic poštovních služeb.

**Hraniční případ:** Pokud nastavíte výšku příliš malou, čárový kód může být nečitelné skenery. Vždy to otestujte na fyzickém výtisku před hromadným nasazením.

---

## Kompletní zdrojový soubor pro rychlé zkopírování

Níže je celý program, který můžete zkopírovat do nového konzolového projektu. Žádný další kód není potřeba.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Planet barcode – auto height, custom width
            var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            planetGenerator.Save("PostalPlanetBarWidth4.png", BarCodeImageFormat.Png);

            // RM4SCC barcode – custom width and explicit height
            var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
            rm4sccGenerator.Save("PostalRM4SCCHeight100.png", BarCodeImageFormat.Png);

            Console.WriteLine("Both postal barcodes have been saved.");
        }
    }
}
```

**Očekávaný výstup** (konzole):

```
Both postal barcodes have been saved.
```

A ve výstupní složce se objeví dva PNG soubory, každý zobrazující čistý poštovní čárový kód připravený k tisku nebo vložení.

---

## Časté otázky a řešení problémů

| Otázka | Odpověď |
|----------|--------|
| *Co když potřebuji jinou X‑dimenzi pro každý čárový kód?* | Vytvořte samostatné instance `BarcodeGenerator` a přiřaďte odlišnou hodnotu `XDimension.Pixels` před voláním `Save`. |
| *Proč formát Planet ignoruje `BarHeight`?* | Formát Planet automaticky vypočítá výšku z X‑dimenze, takže nastavení `BarHeight` nemá žádný efekt. |
| *Mohu místo PNG generovat SVG?* | Ano. Nahraďte `BarCodeImageFormat.Png` za `BarCodeImageFormat.Svg`. |
| *Co když je obrázek po tisku rozmazaný?* | Zvyšte X‑dimenzi (např. na 6 px) a generujte obrázek s vyšším DPI pomocí nastavení `Resolution` na generátoru. |

---

## Závěr

Nyní víte, jak **vytvořit poštovní čárový kód** v C# a přesně **nastavit šířku** a **změnit výšku** pomocí API `BarcodeGenerator`. Příklad pokrývá jak automaticky dimenzované (Planet), tak manuálně dimenzované (RM4SCC) formáty, což vám poskytuje pevný základ pro jakýkoli projekt automatizace pošty.

Dále můžete zkusit:
* Přidat čitelný text pod čárový kód (`CodeTextParameters`).  
* Exportovat do dalších formátů, jako je SVG nebo PDF, pro vektorový tisk.  
* Integrovat generátor do webového API, které bude na požádání poskytovat čárové kódy.

Neváhejte experimentovat s různými rozměry, kódováními a výstupními formáty, aby vyhovovaly vašemu konkrétnímu poštovnímu workflow. Šťastné kódování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobným krok‑za‑krokem vysvětlením, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vlastních projektech.

- [Create Postal Barcode Image in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-postal-barcode-image-in-c-full-step-by-step-guide/)
- [Create Postal Barcode in C# – Full Generator Example](/barcode/english/python-java/general/create-postal-barcode-in-c-full-generator-example/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
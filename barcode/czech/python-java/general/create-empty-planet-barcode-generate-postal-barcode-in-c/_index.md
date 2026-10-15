---
category: general
date: 2026-10-08
description: Vytvořte prázdný planetární čárový kód pomocí C# a naučte se, jak generovat
  poštovní čárový kód pomocí Aspose.BarCode. Kód krok po kroku a tipy jsou zahrnuty.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create empty planet barcode
- how to generate postal barcode
- Aspose.BarCode C#
- postal barcode example
- barcode XDimension setting
language: cs
lastmod: 2026-10-08
og_description: Vytvořte prázdný planetární čárový kód pomocí Aspose.BarCode v C#
  a zjistěte, jak generovat obrázky poštovních čárových kódů pro poštovní aplikace.
og_image_alt: Screenshot of generated empty Planet barcode and filled RM4SCC barcode
og_title: Vytvořte prázdný planetární čárový kód – průvodce poštovním čárovým kódem
  v C#
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Create empty planet barcode with C# and learn how to generate postal
    barcode using Aspose.BarCode. Step‑by‑step code and tips included.
  headline: Create empty planet barcode, generate postal barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- postal
title: Vytvořit prázdný planetární čárový kód, generovat poštovní čárový kód v C#
url: /cs/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořit prázdný planet barcode, generovat poštovní barcode v C#

Pokud potřebujete **vytvořit prázdný planet barcode** pro poštovní systém, tento průvodce vám přesně ukáže, jak to provést pomocí Aspose.BarCode pro .NET. Také se naučíte **jak generovat poštovní barcode** obrázky, jako jsou Planet a RM4SCC, přizpůsobit šířku čáry a ovládat možnost vyplněných čar.

Generování poštovních čárových kódů nevyžaduje samostatnou grafickou knihovnu. Aspose.BarCode SDK poskytuje jednotné API, které zajišťuje kódování, vykreslování obrázku a výběr formátu obrázku. Na konci tohoto tutoriálu budete mít tři připravené PNG soubory:

* `PostalPlanetEmptyBars.png` – prázdné‑čárový Planet barcode  
* `PostalPlanetFilledBars.png` – výchozí vyplněný‑čárový Planet barcode  
* `PostalRM4SCCFilledBars.png` – vyplněný‑čárový RM4SCC barcode  

Můžete tyto soubory vložit do libovolné šablony poštovní etikety, vytisknout je na obálky nebo předat třetí straně.

## Požadavky

* .NET 6.0 nebo novější (kód také funguje s .NET Framework 4.7+).  
* Visual Studio 2022 nebo jakékoli C# IDE.  
* Aspose.BarCode for .NET – instalace přes NuGet:

```bash
dotnet add package Aspose.BarCode
```

Žádné další závislosti nejsou vyžadovány.

## Vytvořit prázdný planet barcode pomocí Aspose.BarCode

Symbologie Planet je součástí rodiny čárových kódů United States Postal Service (USPS). Ve výchozím nastavení SDK kreslí **vyplněné** čáry. Pro **vytvoření prázdného planet barcode** zakážete příznak `FilledBars`.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 1 – instantiate a Planet barcode generator with the data to encode.
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Step 2 – set the width of a single bar. XDimension defines the pixel size of one bar.
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Step 3 – disable the FilledBars option to get empty (hollow) bars.
planetEmpty.Parameters.Barcode.FilledBars = false;

// Step 4 – save the image. The PNG format is widely supported by printers and browsers.
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**Proč to funguje:**  
`EncodeTypes.Planet` říká generátoru, aby použil symbologii Planet. `XDimension.Pixels` řídí fyzickou šířku každé čáry, což je klíčové pro poštovní skenery, které očekávají konkrétní velikost modulu. Nastavením `FilledBars` na `false` renderer nakreslí pouze obrys každé čáry, čímž vytvoří *prázdný* vzhled požadovaný některými poštovními standardy.

### Očekávaný výstup

Soubor `PostalPlanetEmptyBars.png` najdete v cílové složce. Obrázek zobrazuje Planet barcode, kde je každá čára obrysem místo plného obdélníku.

![Empty Planet barcode example](empty-planet.png){: .align-center alt="Vytvořit prázdný planet barcode – příklad planet barcode s prázdnými čarami"}

## Jak generovat poštovní barcode obrázky (vyplněná verze)

Většina poštovních pracovních postupů používá výchozí verzi s vyplněnými čarami. Stejné API může vygenerovat vyplněný Planet barcode a RM4SCC barcode pomocí jen několika řádků kódu.

```csharp
// Filled Planet barcode (default behavior)
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// RM4SCC barcode – another USPS format that always uses filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
```

**Proč můžete potřebovat RM4SCC:**  
RM4SCC je novější USPS barcode, který kóduje stejná data jako Planet, ale s vyšší hustotou. Někteří dopravci vyžadují RM4SCC pro slevy při hromadném zasílání. Výše uvedený kód ukazuje, jak **generovat poštovní barcode** pro oba standardy bez změny celkového pracovního postupu.

### Očekávaný výstup

* `PostalPlanetFilledBars.png` – klasický vyplněný‑čárový Planet barcode.  
* `PostalRM4SCCFilledBars.png` – vyplněný‑čárový RM4SCC barcode, vizuálně podobný, ale s těsnějším rozestupem.

Oba soubory lze otevřít v libovolném prohlížeči obrázků a ověřit vzory čar.

## Úprava šířky čáry pro různé rozlišení tisku

Poštovní skenery často uvádějí minimální šířku modulu (např. 0.013 palců). Pokud vaše tiskárna pracuje na 300 dpi, 4‑pixelový modul odpovídá 0.013 palcům. Upravit hodnotu `XDimension.Pixels` tak, aby odpovídala vašemu hardware:

| Požadovaný modul (palce) | DPI | Požadovaný počet pixelů (`XDimension`) |
|--------------------------|-----|------------------------------------------|
| 0.013                    | 300 | 4                                        |
| 0.013                    | 600 | 8                                        |
| 0.015                    | 300 | 5                                        |

**Tip:** Vždy testujte

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vytvořit planet barcode PNG v C# – krok za krokem průvodce](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/)
- [Generování poštovního čárového kódu v C# – kompletní průvodce s Planet barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)
- [Jak generovat poštovní čárový kód v C# s Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
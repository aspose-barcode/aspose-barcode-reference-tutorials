---
date: 2026-09-03
description: Naučte se, jak generovat čárový kód ze řetězce pomocí Aspose.BarCode
  pro .NET. Tento tutoriál generování čárových kódů v C# ukazuje krok za krokem vytvoření
  GS1 Coupon UPC‑A Code 128.
keywords:
- generate barcode from string
- how to generate barcode
- convert text to barcode
- generate code 128 barcode
- barcode generation tutorial c#
lastmod: 2026-09-03
linktitle: Generovat čárový kód ze řetězce – GS1 Coupon UPC-A Code 128
og_description: Generujte čárový kód ze řetězce pomocí Aspose.BarCode pro .NET. Tento
  průvodce ukazuje krok za krokem příklad v C# pro rychlé vytvoření čárového kódu
  GS1 Coupon UPC‑A Code 128.
og_image_alt: Tutorial showing how to generate a GS1 Coupon UPC‑A Code 128 barcode
  from a string in C# using Aspose.BarCode
og_title: Generovat čárový kód ze řetězce – GS1 Coupon UPC-A Code 128
schemas:
- author: Aspose
  dateModified: '2026-09-03'
  description: Learn how to generate barcode from string using Aspose.BarCode for
    .NET. This barcode generation tutorial C# example shows step‑by‑step creation
    of a GS1 Coupon UPC‑A Code 128.
  headline: Generate barcode from string – GS1 Coupon UPC-A Code 128
  type: TechArticle
- description: Learn how to generate barcode from string using Aspose.BarCode for
    .NET. This barcode generation tutorial C# example shows step‑by‑step creation
    of a GS1 Coupon UPC‑A Code 128.
  name: Generate barcode from string – GS1 Coupon UPC-A Code 128
  steps:
  - name: set the directory path
    text: Begin by defining the directory path where you want to save the generated
      barcode image. Replace `"Your Directory Path"` with the actual path on your
      system.
  - name: create a barcode generator
    text: '`BarcodeGenerator` is Aspose.BarCode''s core class that creates barcode
      images from supplied data. Initialize a `BarcodeGenerator` object with the desired
      encoding type and data to encode. You can replace the data with your own if
      needed.'
  - name: customize barcode parameters
    text: You can fine‑tune various parameters for your barcode, such as the X‑Dimension
      (size of the smallest bar), image format, and more. In this example, we set
      the X‑Dimension to 2 pixels. Feel free to adjust these parameters according
      to your project requirements.
  - name: save the barcode image
    text: Now, save the generated barcode as an image in your specified directory.
      We are saving it in PNG format. You can change the filename and image format
      as needed. By following these four simple steps, you've successfully generated
      a GS1 Coupon UPC‑A Code 128 barcode using Aspose.BarCode for .NET.
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode for .NET fully supports .NET Core 3.1 and later, as
      well as .NET 5/6.
    question: Does the library support .NET Core?
  - answer: Absolutely. Use `BarCodeImageFormat.Svg` or `Pdf` when calling `gen.Save()`.
    question: Can I generate barcodes in vector formats?
  - answer: Set `gen.Parameters.Barcode.CodeTextParameters.ShowCodeText = true;` and
      adjust font settings via `CodeTextParameters`.
    question: How do I add a human‑readable caption below the barcode?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- barcode generation
- Aspose.BarCode
- .NET barcode
title: Generovat čárový kód ze řetězce – GS1 Coupon UPC-A Code 128
url: /cs/net/gs1-barcode-encoding/gs1-coupon-upc-a-code-128-encoding/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GS1 kupón UPC-A Code 128 kódování

## Úvod

Čárové kódy jsou tichými pracovníky v pozadí regálů v maloobchodě, skladů a dokonce i mobilních kupónů. Pokud jste někdy potřebovali **generate barcode from string** data v .NET aplikaci, Aspose.BarCode pro .NET vám poskytne čistý, spolehlivý způsob, jak to provést. V tomto **barcode generation tutorial C#** uvidíte kompletní **barcode generator C# example**, který vytváří GS1 kupón UPC‑A Code 128 čárový kód z jednoduchého textového řetězce. Na konci tohoto průvodce budete schopni vložit čárové kódy přímo do svých projektů bez boje s nízkoúrovňovou logikou kódování.

## Rychlé odpovědi
- **Co dělá primární API?** Převádí prostý řetězec na plně kompatibilní GS1 kupón UPC‑A Code 128 čárový kód.  
- **Která knihovna je vyžadována?** Aspose.BarCode for .NET (k dispozici jako bezplatná zkušební verze).  
- **Potřebuji licenci pro vývoj?** Ne, zkušební verze funguje pro vývoj a testování.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Jak dlouho trvá implementace?** Přibližně 5‑10 minut k získání funkčního obrázku.

## Předpoklady

Než se ponoříte do světa generování čárových kódů s Aspose.BarCode pro .NET, je nezbytné zajistit, že máte potřebné nástroje a znalosti k dispozici.

1. **Vývojové prostředí:** Ujistěte se, že máte nastavené funkční vývojové prostředí. To zahrnuje Visual Studio nebo jakékoli jiné IDE dle vašeho výběru pro psaní a kompilaci vašeho .NET kódu.

2. **Knihovna Aspose.BarCode pro .NET:** Musíte mít Aspose.BarCode pro .NET nainstalovaný ve vašem systému. Pokud jste tak ještě neučinili, můžete jej stáhnout z [Aspose.BarCode for .NET download page](https://releases.aspose.com/barcode/net/).

3. **Základní znalost C#:** Znalost programovacího jazyka C# je nutná, protože budete psát kód pro generování čárových kódů.

## Importování jmenných prostorů

Nyní, když jste prošli předpoklady, je čas pochopit potřebné jmenné prostory pro práci s Aspose.BarCode pro .NET.

1. **Zahrnutí jmenného prostoru Aspose.BarCode:** Začněte zahrnutím jmenného prostoru Aspose.BarCode do vašeho projektu. Zde se nachází veškerá funkčnost generování čárových kódů.

   ```csharp
   using Aspose.BarCode;
   ```

2. **Další jmenné prostory:** V závislosti na vašich konkrétních požadavcích můžete potřebovat zahrnout další jmenné prostory pro manipulaci s obrázky nebo soubory. Například:

   ```csharp
   using System;
   using System.IO;
   ```

S těmito jmennými prostory přidanými do vašeho projektu jste nyní připraveni vytvářet a přizpůsobovat čárové kódy.

## Co je GS1 kupón UPC‑A Code 128?

Čárový kód GS1 kupón UPC‑A Code 128 kóduje standardní 12‑ciferná číselná data UPC‑A spolu s identifikátory aplikací GS1, které nesou informace specifické pro kupón, jako je hodnota slevy nebo datum expirace. Formát vychází ze specifikací GS1 a používá symbologii Code 128 k reprezentaci jak číselného kódu produktu, tak dat s předponou AI v jednom lineárním čárovém kódu.

## Proč použít Aspose.BarCode pro tento úkol?

Protože Aspose.BarCode implementuje kompletní specifikaci GS1, automaticky provádí výpočet kontrolního součtu, formátování AI a vykreslování ve vysokém rozlišení, což vám umožní generovat kompatibilní UPC‑A Code 128 kupóny jedním voláním API. Knihovna také podporuje více než 50 výstupních formátů, dávkové zpracování a jemné vizuální přizpůsobení bez externích závislostí.

## Průvodce krok za krokem pro generování čárového kódu z řetězce – GS1 kupón UPC‑A Code 128

Prozkoumejme krok za krokem proces generování čárového kódu GS1 kupón UPC‑A Code 128 pomocí Aspose.BarCode pro .NET. V tomto příkladu rozdělíme kód na zvládnutelné kroky pro jasné pochopení.

### Krok 1: nastavení cesty k adresáři

Začněte definováním cesty k adresáři, kam chcete uložit vygenerovaný obrázek čárového kódu.

```csharp
string path = "Your Directory Path";
```

Nahraďte `"Your Directory Path"` skutečnou cestou ve vašem systému.

### Krok 2: vytvoření generátoru čárového kódu

`BarcodeGenerator` je hlavní třída Aspose.BarCode, která vytváří obrázky čárových kódů z poskytnutých dat. Inicializujte objekt `BarcodeGenerator` s požadovaným typem kódování a daty k zakódování.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.UpcaGs1Code128Coupon, "123456789012(8110)ASPOSE");
```

Data můžete v případě potřeby nahradit vlastními.

### Krok 3: přizpůsobení parametrů čárového kódu

Můžete jemně doladit různé parametry vašeho čárového kódu, jako je X‑Dimension (velikost nejmenšího pruhu), formát obrázku a další. V tomto příkladu jsme nastavili X‑Dimension na 2 pixely.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

Neváhejte tyto parametry upravit podle požadavků vašeho projektu.

### Krok 4: uložení obrázku čárového kódu

Nyní uložte vygenerovaný čárový kód jako obrázek do zvoleného adresáře. Ukládáme jej ve formátu PNG.

```csharp
gen.Save($"{path}Gs1CouponUpcaCode128.png", BarCodeImageFormat.Png);
```

Název souboru a formát obrázku můžete změnit podle potřeby.

Podle těchto čtyř jednoduchých kroků jste úspěšně vygenerovali čárový kód GS1 kupón UPC‑A Code 128 pomocí Aspose.BarCode pro .NET.

## Běžné případy použití

- **Maloobchodní kupóny** – vložte informace o slevě přímo na obal produktu.  
- **Označování ve skladech** – kombinujte ID produktů s údaji o šarži nebo expiraci.  
- **Mobilní propagační akce** – generujte tisknutelné čárové kódy pro uplatnění kupónu bez QR.

## Řešení problémů a tipy

- **Problémy s cestou** – ujistěte se, že adresář existuje a aplikace má oprávnění k zápisu.  
- **Neplatný formát dat** – řetězec musí odpovídat syntaxi GS1 (`(AI)Data`).  
- **Kvalita obrázku** – zvyšte `XDimension` pro vyšší rozlišení tisku.  

## Závěr

V tomto tutoriálu jsme se podrobně zabývali generováním čárových kódů pomocí Aspose.BarCode pro .NET. Prošli jsme předpoklady, importovali potřebné jmenné prostory a krok za krokem prošli praktickým **barcode generator C# example**. S těmito znalostmi nyní můžete **generate barcode from string** data pro jakýkoli scénář kompatibilní s GS1, ať už jde o kupón, štítek zásob nebo vlastní propagaci.

Aspose.BarCode pro .NET poskytuje všestranné a uživatelsky přívětivé řešení pro všechny vaše potřeby generování čárových kódů. Ať už spravujete zásoby, sledujete produkty nebo kódujete data, tato knihovna proces zjednodušuje.

Pokud máte jakékoli otázky nebo potřebujete další pomoc, neváhejte navštívit [Aspose.BarCode documentation](https://reference.aspose.com/barcode/net/) nebo požádat o podporu na [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13).

## Často kladené otázky

### Q: Mohu používat Aspose.BarCode pro .NET pro komerční projekty?
A: Ano, Aspose.BarCode pro .NET je vhodný jak pro osobní, tak pro komerční projekty. Licence může být zakoupena na [Aspose.BarCode license purchase page](https://purchase.aspose.com/buy).

### Q: Je k dispozici bezplatná zkušební verze Aspose.BarCode pro .NET?
A: Ano, můžete získat bezplatnou zkušební verzi [Aspose.BarCode free trial download](https://releases.aspose.com/). Umožní vám vyzkoušet funkce knihovny před zakoupením.

### Q: Jak mohu získat dočasnou licenci pro Aspose.BarCode pro .NET?
A: Pokud potřebujete dočasnou licenci pro vyhodnocení nebo testování, můžete ji získat na [temporary license request page](https://purchase.aspose.com/temporary-license/).

### Q: Mohu dále přizpůsobit vzhled vygenerovaných čárových kódů?
A: Rozhodně. Aspose.BarCode pro .NET poskytuje různé parametry a nastavení pro přizpůsobení vzhledu a chování vašich čárových kódů. Více podrobností najdete v dokumentaci.

### Q: Existují i jiné typy kódování podporované Aspose.BarCode pro .NET?
A: Ano, Aspose.BarCode pro .NET podporuje širokou škálu typů kódování, včetně UPC‑A, Code 128, QR kódů a mnoha dalších. Kompletní seznam najdete v dokumentaci.

## Další často kladené otázky

**Q: Podporuje knihovna .NET Core?**  
A: Ano, Aspose.BarCode pro .NET plně podporuje .NET Core 3.1 a novější, stejně jako .NET 5/6.

**Q: Mohu generovat čárové kódy ve vektorových formátech?**  
A: Rozhodně. Použijte `BarCodeImageFormat.Svg` nebo `Pdf` při volání `gen.Save()`.

**Q: Jak přidám lidsky čitelný popisek pod čárový kód?**  
A: Nastavte `gen.Parameters.Barcode.CodeTextParameters.ShowCodeText = true;` a upravte nastavení písma pomocí `CodeTextParameters`.

---

**Last Updated:** 2026-09-03  
**Tested With:** Aspose.BarCode for .NET 24.11  
**Author:** Aspose

## Související tutoriály

- [Generovat Aztec čárový kód s textovým kódováním pomocí Aspose.BarCode pro .NET](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)
- [Jak generovat DataMatrix čárové kódy pomocí Aspose.BarCode pro .NET – Průvodce krok za krokem](/barcode/net/datamatrix-barcode-configuration/)
- [Generovat jednorozměrné Databar 2D čárové kódy pomocí Aspose.BarCode .NET API](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
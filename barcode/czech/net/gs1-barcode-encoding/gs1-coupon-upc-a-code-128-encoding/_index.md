---
date: 2026-02-15
description: Naučte se, jak generovat čárový kód ze řetězce pomocí Aspose.BarCode
  pro .NET. Tento tutoriál generování čárových kódů s příkladem v C# ukazuje krok
  po kroku vytvoření GS1 Coupon UPC‑A Code 128.
linktitle: Generate barcode from string – GS1 Coupon UPC-A Code 128
second_title: Aspose.BarCode .NET API
title: Generovat čárový kód ze řetězce – GS1 kupón UPC‑A Code 128
url: /cs/net/gs1-barcode-encoding/gs1-coupon-upc-a-code-128-encoding/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kódování GS1 Coupon UPC-A Code 128

## Úvod

Čárové kódy jsou tichými pracovníky za regály v maloobchodu, sklady i mobilními kupóny. Pokud jste někdy potřebovali **vygenerovat čárový kód z řetězce** v .NET aplikaci, Aspose.BarCode pro .NET vám poskytne čistý a spolehlivý způsob, jak to udělat. V tomto **návodu na generování čárových kódů C#** uvidíte kompletní **příklad generátoru čárových kódů C#**, který vytvoří GS1 Coupon UPC‑A Code 128 čárový kód z jednoduchého textového řetězce. Na konci tohoto průvodce budete schopni vložit čárové kódy přímo do svých projektů, aniž byste se museli zabývat nízkoúrovňovou logikou kódování.

## Rychlé odpovědi
- **Co dělá primární API?** Převádí prostý řetězec na plně kompatibilní GS1 Coupon UPC‑A Code 128 čárový kód.  
- **Která knihovna je vyžadována?** Aspose.BarCode pro .NET (k dispozici jako bezplatná zkušební verze).  
- **Potřebuji licenci pro vývoj?** Ne, zkušební verze funguje pro vývoj a testování.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Jak dlouho trvá implementace?** Přibližně 5‑10 minut na získání funkčního obrázku.

## Požadavky

Než se ponoříte do světa generování čárových kódů s Aspose.BarCode pro .NET, je nezbytné zajistit, že máte potřebné nástroje a znalosti k dispozici.

1. Vývojové prostředí: Ujistěte se, že máte nastavené funkční vývojové prostředí. To zahrnuje Visual Studio nebo jakékoli jiné IDE dle vašeho výběru pro psaní a kompilaci .NET kódu.

2. Knihovna Aspose.BarCode pro .NET: Musíte mít Aspose.BarCode pro .NET nainstalovanou ve vašem systému. Pokud jste tak ještě neučinili, můžete ji stáhnout [zde](https://releases.aspose.com/barcode/net/).

3. Základní znalost C#: Znalost programovacího jazyka C# je nutná, protože budete psát kód pro generování čárových kódů.

## Importování jmenných prostorů

Nyní, když jste prošli požadavky, je čas pochopit potřebné jmenné prostory pro práci s Aspose.BarCode pro .NET.

1. Zahrňte jmenný prostor Aspose.BarCode: Začněte zahrnutím jmenného prostoru Aspose.BarCode do vašeho projektu. Zde se nachází veškerá funkčnost generování čárových kódů.

   ```csharp
   using Aspose.BarCode;
   ```

2. Další jmenné prostory: V závislosti na vašich konkrétních požadavcích můžete potřebovat zahrnout další jmenné prostory pro manipulaci s obrázky nebo práci se soubory. Například:

   ```csharp
   using System;
   using System.IO;
   ```

S těmito jmennými prostory přidanými do projektu jste nyní připraveni vytvářet a přizpůsobovat čárové kódy.

## Co je GS1 Coupon UPC‑A Code 128?

Čárový kód GS1 Coupon UPC‑A Code 128 kombinuje tradiční číselný formát UPC‑A s dalšími identifikátory aplikací GS1 (AI), které nesou data specifická pro kupóny, jako jsou výše slev nebo datum expirace. Kódování těchto informací jako **řetězec** a nechat Aspose provést konverzi vás ušetří od ručních výpočtů kontrolního součtu a zvláštností formátu.

## Proč použít Aspose.BarCode pro tento úkol?

- **Kódování bez závislostí** – knihovna zná přesná pravidla GS1.  
- **Výstup vysoké kvality** – generujte PNG, JPEG, SVG nebo PDF jedním voláním.  
- **Plná kontrola** – upravujte rozměry, barvy a tiché zóny bez opuštění C#.  

## Průvodce krok za krokem pro generování čárového kódu z řetězce – GGS1 Coupon UPC‑A Code 128

Prozkoumejme krok‑za‑krokem proces generování čárového kódu GGS1 Coupon UPC‑A Code 128 pomocí Aspose.BarCode pro .NET. V tomto příkladu rozdělíme kód na zvládnutelné kroky pro jasné pochopení.

### Krok 1: Nastavte cestu ke složce

Začněte definováním cesty ke složce, kam chcete uložit vygenerovaný obrázek čárového kódu.

```csharp
string path = "Your Directory Path";
```

Nahraďte `"Your Directory Path"` skutečnou cestou ve vašem systému.

### Krok 2: Vytvořte generátor čárových kódů

Inicializujte objekt `BarcodeGenerator` s požadovaným typem kódování a daty k zakódování. V tomto případě vytváříme čárový kód GGS1 Coupon UPC‑A Code 128 s daty `"123456789012(8110)ASPOSE"`.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.UpcaGs1Code128Coupon, "123456789012(8110)ASPOSE");
```

Můžete nahradit data svými vlastními, pokud je to potřeba.

### Krok 3: Přizpůsobte parametry čárového kódu

Můžete jemně doladit různé parametry vašeho čárového kódu, jako je X‑Dimension (velikost nejmenšího pruhu), formát obrázku a další. V tomto příkladu nastavíme X‑Dimension na 2 pixely.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

Neváhejte upravit tyto parametry podle požadavků vašeho projektu.

### Krok 4: Uložte obrázek čárového kódu

Nyní uložte vygenerovaný čárový kód jako obrázek do určené složky. Ukládáme jej ve formátu PNG.

```csharp
gen.Save($"{path}Gs1CouponUpcaCode128.png", BarCodeImageFormat.Png);
```

Můžete změnit název souboru a formát obrázku podle potřeby.

Dodržením těchto čtyř jednoduchých kroků jste úspěšně vygenerovali čárový kód GGS1 Coupon UPC‑A Code 128 pomocí Aspose.BarCode pro .NET.

## Běžné případy použití

- **Maloobchodní kupóny** – vložte informace o slevě přímo na obal produktu.  
- **Označování ve skladu** – kombinujte ID produktů s údaji o šarži nebo expiraci.  
- **Mobilní propagace** – generujte tisknutelné čárové kódy pro uplatnění kupónu bez QR.  

## Řešení problémů a tipy

- **Problémy s cestou** – ujistěte se, že složka existuje a aplikace má oprávnění k zápisu.  
- **Neplatný formát dat** – řetězec musí dodržovat syntaxi GS1 (`(AI)Data`).  
- **Kvalita obrázku** – zvýšte `XDimension` pro vyšší rozlišení tisku.  

## Závěr

V tomto tutoriálu jsme se podrobně zabývali generováním čárových kódů pomocí Aspose.BarCode pro .NET. Probrali jsme požadavky, importovali potřebné jmenné prostory a krok za krokem prošli praktickým **příkladem generátoru čárových kódů C#**. S těmito znalostmi nyní můžete **vygenerovat čárový kód z řetězce** pro jakýkoli scénář splňující GS1, ať už jde o kupón, štítek zásob nebo vlastní propagaci.

Aspose.BarCode pro .NET poskytuje univerzální a uživatelsky přívětivé řešení pro všechny vaše potřeby generování čárových kódů. Ať už spravujete zásoby, sledujete produkty nebo kódujete data, tato knihovna proces zjednodušuje.

Pokud máte jakékoli otázky nebo potřebujete další pomoc, neváhejte navštívit [dokumentaci Aspose.BarCode](https://reference.aspose.com/barcode/net/) nebo požádat o podporu na [fóru Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

## Často kladené otázky

### Otázka: Mohu použít Aspose.BarCode pro .NET pro komerční projekty?
Ano, Aspose.BarCode pro .NET je vhodný jak pro osobní, tak pro komerční projekty. Licenci si můžete zakoupit [zde](https://purchase.aspose.com/buy).

### Otázka: Je k dispozici bezplatná zkušební verze Aspose.BarCode pro .NET?
Ano, můžete získat bezplatnou zkušební verzi [zde](https://releases.aspose.com/). Umožní vám vyzkoušet funkce knihovny před zakoupením.

### Otázka: Jak mohu získat dočasnou licenci pro Aspose.BarCode pro .NET?
Pokud potřebujete dočasnou licenci pro hodnocení nebo testování, můžete ji získat [zde](https://purchase.aspose.com/temporary-license/).

### Otázka: Mohu dále přizpůsobit vzhled vygenerovaných čárových kódů?
Rozhodně. Aspose.BarCode pro .NET poskytuje různé parametry a nastavení pro přizpůsobení vzhledu a chování vašich čárových kódů. Další podrobnosti najdete v dokumentaci.

### Otázka: Existují i jiné typy kódování podporované Aspose.BarCode pro .NET?
Ano, Aspose.BarCode pro .NET podporuje širokou škálu typů kódování, včetně UPC‑A, Code 128, QR kódů a mnoha dalších. Kompletní seznam najdete v dokumentaci.

## Další často kladené otázky

**Otázka: Podporuje knihovna .NET Core?**  
**Odpověď:** Ano, Aspose.BarCode pro .NET plně podporuje .NET Core 3.1 a novější, stejně jako .NET 5/6.

**Otázka: Mohu generovat čárové kódy ve vektorových formátech?**  
**Odpověď:** Rozhodně. Použijte `BarCodeImageFormat.Svg` nebo `Pdf` při volání `gen.Save()`.

**Otázka: Jak přidám čitelný popisek pod čárový kód?**  
**Odpověď:** Nastavte `gen.Parameters.Barcode.CodeTextParameters.ShowCodeText = true;` a upravte nastavení písma pomocí `CodeTextParameters`.

---

**Poslední aktualizace:** 2026-02-15  
**Testováno s:** Aspose.BarCode pro .NET 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
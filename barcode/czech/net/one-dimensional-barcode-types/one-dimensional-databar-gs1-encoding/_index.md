---
date: 2026-03-07
description: Naučte se, jak v .NET pomocí Aspose.BarCode vytvářet jednorozměrné databar
  kódy GS1. Tento průvodce ukazuje, jak nastavit GS1, nakonfigurovat generátor čárových
  kódů a rychle generovat čárové kódy.
linktitle: One-Dimensional Databar GS1 Encoding
second_title: Aspose.BarCode .NET API
title: Vytvořte jednorozměrné kódování Databar GS1 pomocí Aspose.BarCode
url: /cs/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření jednorozměrného Databar GS1 kódování s Aspose.BarCode

V tomto tutoriálu **vytvoříte jednorozměrné databar** čárové kódy, které vyhovují standardu GS1, pomocí knihovny Aspose.BarCode pro .NET. Ať už potřebujete přísnou validaci GS1 nebo flexibilnější čárový kód, provedeme vás každým krokem – od instalace knihovny po zpracování výjimek při kódování – abyste mohli generovat spolehlivé čárové kódy ve svých aplikacích.

## Rychlé odpovědi
- **Co znamená „vytvořit jednorozměrný databar“?** Znamená to generování lineárního (1‑D) čárového kódu rodiny Databar, často používaného v maloobchodě a logistice.  
- **Jak nastavit validaci GS1?** Nastavte `IsAllowOnlyGS1Encoding` na `true` v parametrech `DataBar`.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Které verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Odkud si mohu stáhnout knihovnu?** Z oficiální stránky vydání Aspose (viz předpoklady).

## Co je „vytvořit jednorozměrný databar“?
Jednorozměrný Databar (také známý jako RSS) je kompaktní lineární čárový kód, který může kódovat číselná data, data nebo řetězce AI (Application Identifier). V kombinaci s kódováním GS1 čárový kód používá celosvětově uznávanou datovou strukturu, což jej činí ideálním pro maloobchod, zdravotnictví a scénáře dodavatelského řetězce.

## Proč použít Aspose.BarCode pro .NET?
Aspose.BarCode poskytuje plynulé API, plnou podporu GS1 a možnost jemně doladit každý vizuální aspekt čárového kódu. Odstraňuje hádání při nízkoúrovňovém kódování a umožňuje se soustředit na obchodní logiku.

## Předpoklady

1. **Aspose.BarCode pro .NET** – stáhněte a nainstalujte jej z [zde](https://releases.aspose.com/barcode/net/).  
2. **Cesta k vašemu adresáři** – nahraďte `"Your Directory Path"` ve vzorcích složkou, do které máte oprávnění zápisu.

## Importování jmenných prostorů

Přidejte požadované `using` příkazy na začátek vašeho souboru C#:

```csharp
using Aspose.BarCode;
using System;
```

## Krok 1: Inicializace generátoru čárových kódů

Vytvořte instanci `BarcodeGenerator` a specifikujte symbologii Databar Expanded:

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## Krok 2: Jak nastavit GS1 – Vygenerovat čárový kód s přísnou validací GS1

Povolte kódování pouze GS1, přiřaďte GS1‑kompatibilní text kódu a uložte obrázek:

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## Krok 3: Generování čárových kódů s Aspose – Proměnné kódování (bez kontroly GS1)

Pokud potřebujete čárový kód, který **ne**vynucuje pravidla GS1, vypněte kontrolu:

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## Krok 4: Kontrola GS1 v generátoru čárových kódů – Zpracování výjimky

Když je `IsAllowOnlyGS1Encoding` nastaveno na `true`, ale text kódu není GS1‑kompatibilní, Aspose vyhodí výjimku. Následující vzor ukazuje, jak ji zachytit a zaznamenat:

```csharp
try
{
    gen.CodeText = "ASPOSE";
    gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

### Časté úskalí a tipy
- **Úskalí:** Poskytnutí řetězce, který není GS1, při zapnuté kontrole GS1 způsobí přerušení generování čárového kódu.  
- **Profesionální tip:** Ověřte své AI řetězce před přiřazením k `CodeText`, abyste předešli chybám za běhu.  
- **Tip:** Používejte absolutní cesty nebo `Path.Combine` pro bezpečnou tvorbu názvů souborů napříč platformami.

## Závěr

Nyní víte, jak **vytvořit jednorozměrné databar** čárové kódy s GS1 kódováním, jak přepínat kontrolu GS1 a jak zpracovávat související výjimky – vše pomocí Aspose.BarCode pro .NET. Klidně prozkoumejte další možnosti stylování, jako je velikost čárového kódu, barva a okraje pomocí objektu `Parameters.Barcode`.

Pokud narazíte na jakékoli problémy, oficiální dokumentace a komunitní fórum jsou vynikajícími zdroji:

- [Dokumentace Aspose.BarCode](https://reference.aspose.com/barcode/net/)  
- [Fórum podpory Aspose.BarCode](https://forum.aspose.com/c/barcode/13)

## Často kladené otázky

### 1. Co je GS1 kódování v čárových kódech?
GS1 kódování je standardizovaný způsob strukturování dat (např. identifikátorů produktů) v čárovém kódu, který zajišťuje interoperabilitu mezi maloobchodníky, výrobci a poskytovateli logistiky.

### 2. Mohu přizpůsobit vzhled vygenerovaných čárových kódů?
Ano. Aspose.BarCode vám umožní upravit velikost, barvy, okraje a dokonce přidat text čitelný pro člověka pomocí nastavení `Parameters.Barcode`.

### 3. Kde najdu další zdroje a dokumentaci pro Aspose.BarCode?
Komplexní dokumentaci a příklady najdete na [Aspose.BarCode documentation](https://reference.aspose.com/barcode/net/). Jedná se o cenný zdroj pro učení a řešení problémů.

### 4. Je k dispozici zkušební verze Aspose.BarCode?
Ano, můžete získat bezplatnou zkušební verzi Aspose.BarCode pro .NET z [zde](https://releases.aspose.com/).

### 5. Jak mohu zakoupit licenci pro Aspose.BarCode pro .NET?
Pro zakoupení licence pro Aspose.BarCode pro .NET navštivte [stránku nákupu](https://purchase.aspose.com/buy) na webu Aspose.

---

**Poslední aktualizace:** 2026-03-07  
**Testováno s:** Aspose.BarCode 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
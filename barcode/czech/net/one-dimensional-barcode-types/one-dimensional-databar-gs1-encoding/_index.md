---
title: Kódování jednorozměrné datové lišty GS1
linktitle: Kódování jednorozměrné datové lišty GS1
second_title: Aspose.BarCode .NET API
description: Naučte se vytvářet kódované čárové kódy Databar GS1 v .NET pomocí Aspose.BarCode. Snadno generujte čárové kódy. Postupujte podle našeho podrobného průvodce.
weight: 18
url: /cs/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kódování jednorozměrné datové lišty GS1


V tomto tutoriálu vás provedeme procesem vytváření jednorozměrných kódovaných čárových kódů Databar GS1 pomocí knihovny Aspose.BarCode for .NET. Ať už chcete generovat čárové kódy s kódováním GS1 nebo bez něj, máme pro vás vše. Tento podrobný průvodce vám pomůže porozumět předpokladům, importovat jmenné prostory a předvést každý příklad, jak snadno vytvořit čárové kódy Databar GS1.

## Předpoklady

Než se ponoříme do kódu, ujistěte se, že máte splněny následující předpoklady:

1.  Aspose.BarCode for .NET: Měli byste mít nainstalovaný Aspose.BarCode for .NET. Pokud jste tak ještě neučinili, můžete si jej stáhnout z[tady](https://releases.aspose.com/barcode/net/).

2.  Cesta k vašemu adresáři: Nahradit`"Your Directory Path"` v příkladech kódu se skutečnou cestou, kam chcete uložit vygenerované obrázky čárových kódů.

Nyní, když máte připravené potřebné předpoklady, přistoupíme k části kódování.

## Import jmenných prostorů

Chcete-li začít, musíte importovat příslušné jmenné prostory pro Aspose.BarCode. Na začátek projektu .NET přidejte následující řádky kódu:

```csharp
using Aspose.BarCode;
using System;
```

## Krok 1: Inicializujte generátor čárových kódů

Prvním krokem je inicializace objektu BarcodeGenerator s požadovaným typem kódování. V tomto případě používáme kódování Databar Expanded. 

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## Krok 2: Vygenerujte čárový kód s kódováním GS1

Nyní nastavíme kódový text pomocí kontroly GS1Encoding a uložíme vygenerovaný obrázek čárového kódu. 

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## Krok 3: Vygenerujte čárový kód s variabilním kódováním

V tomto kroku vygenerujeme čárový kód s proměnným kódovým textem bez kontroly GS1Encoding.

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## Krok 4: Zvládněte výjimku pro kontrolu kódování GS1

Pokud se pokusíte vygenerovat čárový kód s proměnným kódovým textem se zapnutou kontrolou GS1Encoding, vyvolá výjimku. Můžete to zvládnout takto:

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

Nyní jste úspěšně vytvořili jednorozměrné čárové kódy Databar GS1 zakódované pomocí Aspose.BarCode pro .NET. Generování čárových kódů můžete dále prozkoumat a přizpůsobit na základě svých specifických požadavků.

## Závěr

tomto tutoriálu jsme se zabývali procesem generování jednorozměrných čárových kódů kódovaných Databar GS1 pomocí Aspose.BarCode for .NET. Diskutovali jsme o nezbytných předpokladech, importovali potřebné jmenné prostory a poskytli podrobné pokyny pro vytváření čárových kódů s kódováním GS1 i s variabilním kódováním.

 S Aspose.BarCode for .NET se generování čárových kódů stává bezproblémovým úkolem, který nabízí flexibilitu a kontrolu nad vašimi potřebami při vytváření čárových kódů. Pokud narazíte na nějaké problémy nebo máte dotazy, neváhejte navštívit[Dokumentace Aspose.BarCode](https://reference.aspose.com/barcode/net/) nebo vyhledejte pomoc na[Fórum podpory Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

## Často kladené otázky

### 1. Co je kódování GS1 v čárových kódech?
Kódování GS1 je standard používaný v čárových kódech k zajištění správné struktury dat a identifikace. Běžně se používá pro položky v maloobchodě, zdravotnictví a logistice, aby se usnadnilo přesné sledování a výměna informací.

### 2. Mohu upravit vzhled generovaných čárových kódů?
Ano, vzhled čárových kódů generovaných pomocí Aspose.BarCode for .NET si můžete přizpůsobit. Máte kontrolu nad různými parametry, jako je velikost, barva a styl.

### 3. Kde najdu další zdroje a dokumentaci k Aspose.BarCode?
 Kompletní dokumentaci a příklady naleznete na[Dokumentace Aspose.BarCode](https://reference.aspose.com/barcode/net/). Je to cenný zdroj pro učení a řešení problémů.

### 4. Je k dispozici zkušební verze pro Aspose.BarCode?
 Ano, můžete získat bezplatnou zkušební verzi Aspose.BarCode pro .NET od[tady](https://releases.aspose.com/).

### 5. Jak si mohu zakoupit licenci pro Aspose.BarCode pro .NET?
 Chcete-li zakoupit licenci pro Aspose.BarCode pro .NET, navštivte stránku[nákupní stránku](https://purchase.aspose.com/buy) na webu Aspose.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

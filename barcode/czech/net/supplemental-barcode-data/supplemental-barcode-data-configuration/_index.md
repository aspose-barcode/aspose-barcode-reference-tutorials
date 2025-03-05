---
title: Vytváření doplňkových dat čárových kódů pomocí Aspose.BarCode pro .NET
linktitle: Konfigurace doplňkových dat čárového kódu
second_title: Aspose.BarCode .NET API
description: Generujte doplňková data čárových kódů pomocí Aspose.BarCode pro .NET. Přizpůsobte si čárové kódy EAN-2 a EAN-5 bez námahy. Podrobný průvodce pro vývojáře .NET.
type: docs
weight: 10
url: /cs/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
---

Ve světě generování a přizpůsobení čárových kódů Aspose.BarCode for .NET vyniká jako výkonný a všestranný nástroj. Ať už jste zkušený vývojář nebo teprve začínáte, tento podrobný průvodce vás provede procesem konfigurace doplňkových dat čárových kódů pomocí Aspose.BarCode for .NET. 

## Předpoklady

Než se ponoříme do světa doplňkových dat čárových kódů, ujistěte se, že máte splněny následující předpoklady:

- Vývojové prostředí nastavené pomocí sady Visual Studio nebo jakéhokoli jiného vývojového nástroje .NET.
-  Kopie Aspose.BarCode pro .NET. Pokud jste to ještě neudělali, můžete si ji stáhnout[tady](https://releases.aspose.com/barcode/net/).
- Základní znalost programování v C#.
- Adresář, kam můžete uložit vygenerované obrázky čárových kódů.

## Import jmenných prostorů

Nejprve se ujistěte, že máte v kódu C# zahrnuty potřebné jmenné prostory pro práci s Aspose.BarCode for .NET. Importujte požadované jmenné prostory na začátek vašeho souboru C#:

```csharp
using Aspose.BarCode.Generation;
```

Nyní si rozdělme proces konfigurace doplňkových dat čárových kódů do několika kroků.

## Krok 1: Nastavení cesty k adresáři

 V kódu C# definujte cestu k adresáři, kam chcete uložit vygenerované obrázky čárových kódů. Nahradit`"Your Directory Path"` s vaší skutečnou cestou k adresáři.

```csharp
string path = "Your Directory Path";
```

## Krok 2: Vytvoření generátoru čárových kódů

 Vytvořte instanci`BarcodeGenerator` zadáním typu čárového kódu a dat, která chcete kódovat. V tomto příkladu používáme čárový kód EAN-13 s údaji „1234567890128“.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

## Krok 3: Přizpůsobení rozměrů čárového kódu

Nastavte rozměry čárového kódu, jako je rozměr X (šířka nejmenšího prvku v čárovém kódu) a doplňková mezera. V tomto příkladu nastavíme rozměr X na 2 pixely a doplňkový prostor na 20 pixelů.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

## Krok 4: Konfigurace doplňku EAN-2

Chcete-li nakonfigurovat doplňkový čárový kód EAN-2, nastavte doplňková data na požadovanou hodnotu. V tomto případě ji nastavíme na „12“. 

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

## Krok 5: Uložení obrázku čárového kódu

Uložte vygenerovaný obrázek čárového kódu do zadaného adresáře se smysluplným názvem. V tomto příkladu uložíme doplňkový čárový kód EAN-2 jako "SupplementEAN2.png".

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

## Krok 6: Konfigurace doplňku EAN-5

 Chcete-li nakonfigurovat doplňkový čárový kód EAN-5, jednoduše změňte`SupplementData` na vámi požadovanou hodnotu. Zde jsme jej nastavili na „12345“.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

## Krok 7: Uložení obrázku čárového kódu (EAN-5)

Nakonec uložte obrázek doplňkového čárového kódu EAN-5 do vámi určeného adresáře. V tomto případě jej uložíme jako „SupplementEAN5.png“.

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

Nyní jste úspěšně nakonfigurovali a vygenerovali doplňková data čárových kódů pomocí Aspose.BarCode for .NET. Tento přístup můžete použít k vytvoření široké škály typů čárových kódů s různými doplňkovými daty.

## Závěr

Aspose.BarCode for .NET je výkonný nástroj pro generování a přizpůsobení čárových kódů. V této příručce jsme krok za krokem prošli procesem konfigurace a generování doplňkových dat čárových kódů. Se správnými předpoklady a trochou kódování můžete efektivně pracovat s daty čárových kódů a vyhovět vašim specifickým potřebám.

 Další informace a pokročilé použití naleznete v části[Aspose.BarCode pro dokumentaci .NET](https://reference.aspose.com/barcode/net/).

## Často kladené otázky

### Mohu použít Aspose.BarCode pro .NET ve svém projektu .NET Core?
Ano, Aspose.BarCode for .NET je kompatibilní s .NET Core.

### Je k dispozici bezplatná zkušební verze pro Aspose.BarCode pro .NET?
 Ano, můžete si to vyzkoušet zdarma při návštěvě[tento odkaz](https://releases.aspose.com/).

### Kde mohu získat dočasnou licenci pro Aspose.BarCode pro .NET?
 Dočasnou licenci můžete získat od[tento odkaz](https://purchase.aspose.com/temporary-license/).

### Podporuje Aspose.BarCode širokou škálu typů čárových kódů?
Ano, podporuje různé typy čárových kódů, včetně EAN-13, QR Code, Code 128 a dalších.

### Mohu upravit vzhled generovaných čárových kódů?
Rozhodně si můžete přizpůsobit rozměry, barvy a další aspekty čárových kódů tak, aby vyhovovaly vašim požadavkům.

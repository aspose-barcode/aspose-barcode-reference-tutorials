---
title: Generování čárových kódů DataMatrix pomocí Aspose.BarCode pro .NET
linktitle: Verze DataMatrix
second_title: Aspose.BarCode .NET API
description: Naučte se generovat čárové kódy DataMatrix v .NET pomocí Aspose.BarCode for .NET. Vlastní rozměry, podpora ECC a další.
weight: 12
url: /cs/net/datamatrix-barcode-reading/datamatrix-versions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generování čárových kódů DataMatrix pomocí Aspose.BarCode pro .NET

Pokud hledáte spolehlivé řešení pro generování čárových kódů DataMatrix ve vašich aplikacích .NET, Aspose.BarCode for .NET je tou správnou cestou. V tomto podrobném průvodci vás provedeme procesem použití Aspose.BarCode for .NET k vytvoření čárových kódů DataMatrix. Každý příklad rozdělíme do několika kroků, abyste je mohli snadno sledovat.

## Předpoklady

Než se ponoříme do kódu, ujistěte se, že máte splněny následující předpoklady:
- Vývojové prostředí s podporou .NET.
-  Kopie Aspose.BarCode pro .NET, kterou si můžete stáhnout[tento odkaz](https://releases.aspose.com/barcode/net/).
- Základní znalost C# a .NET frameworku.

Nyní se podívejme na verze DataMatrix a na to, jak je generovat pomocí Aspose.BarCode for .NET.

## Importovat jmenné prostory

V každém projektu C# je nezbytné importovat potřebné jmenné prostory. V případě Aspose.BarCode budete muset zahrnout následující:

```csharp
using Aspose.BarCode.Generation;
```

 Tento jmenný prostor poskytuje přístup k`BarcodeGenerator` třídy, která je klíčová pro generování čárových kódů.

Nyní si příklad rozdělíme do několika kroků.

## Krok 1: Nastavte cestu k adresáři

Začněte definováním cesty k adresáři, kam chcete uložit vygenerované čárové kódy DataMatrix.

```csharp
string path = "Your Directory Path";
```

 Nahradit`"Your Directory Path"` se skutečnou cestou, kam chcete uložit obrázky čárových kódů.

## Krok 2: Inicializujte generátor čárových kódů

 Vytvořte instanci souboru`BarcodeGenerator` třídy a zadejte typ čárového kódu jako`DataMatrix`. Můžete také zadat data, která chcete zakódovat do čárového kódu.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Kód pro generování čárových kódů je zde
}
```

## Krok 3: Konfigurace vlastností čárového kódu

Můžete přizpůsobit různé vlastnosti čárového kódu DataMatrix, jako jsou jeho rozměry a typ ECC (Error Correction Code). Zde je příklad nastavení rozměru X na 4 pixely a výběru ECC200:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4;
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

## Krok 4: Nastavte verzi DataMatrix a uložte

Verzi DataMatrix můžete určit nastavením počtu řádků a sloupců. Po konfiguraci verze uložte obrázek čárového kódu.

Chcete-li například vytvořit čárový kód DataMatrix s 22 řádky a 22 sloupci pomocí ECC200:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC200_22x22;
generator.Save($"{path}DataMatrixRows22Columns22Ecc200.png", BarCodeImageFormat.Png);
```

Podobně můžete vygenerovat čárový kód s různými parametry změnou verze a typu ECC podle potřeby.

## Krok 5: Opakujte pro další verze

Krok 4 můžete opakovat pro další verze DataMatrix. Chcete-li například vytvořit čárový kód s 12 řádky a 64 sloupci pomocí ECC200:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.DMRE_12x64;
generator.Save($"{path}DataMatrixRows12Columns64Ecc200.png", BarCodeImageFormat.Png);
```

## Krok 6: Přepněte typy ECC

Pokud chcete změnit typ ECC na Ecc140, můžete tak učinit aktualizací vlastnosti ECC:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;
```

## Krok 7: Generujte čárové kódy s různými verzemi a ECC

Opakujte krok 4 pro další verze DataMatrix a typy ECC a uložte každý čárový kód s jedinečným názvem souboru.

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC000_140_29x29;
generator.Save($"{path}DataMatrixRows29Columns29Ecc140.png", BarCodeImageFormat.Png);
```

Nyní, když jste se naučili generovat čárové kódy DataMatrix pomocí Aspose.BarCode pro .NET, můžete tuto funkci snadno integrovat do svých aplikací .NET.

## Závěr

Aspose.BarCode for .NET zjednodušuje proces generování čárových kódů DataMatrix ve vašich aplikacích .NET. Pomocí tohoto podrobného průvodce můžete vytvářet čárové kódy s různými verzemi a typy ECC, které nabízejí flexibilitu a přizpůsobení vašim specifickým potřebám.

 Pokud máte nějaké dotazy nebo potřebujete pomoc, neváhejte navštívit[Aspose.BarCode pro dokumentaci .NET](https://reference.aspose.com/barcode/net/) nebo se podívejte na[Fórum Aspose.BarCode](https://forum.aspose.com/c/barcode/13) pro podporu.

## FAQ

### Q1: Co je ECC v čárových kódech DataMatrix?

A1: ECC (Error Correction Code) je důležitou součástí čárových kódů DataMatrix, která pomáhá zajistit integritu dat. Různé úrovně ECC poskytují různé stupně opravy chyb.

### Q2: Mohu generovat čárové kódy DataMatrix s vlastními rozměry pomocí Aspose.BarCode for .NET?

Odpověď 2: Ano, můžete přizpůsobit rozměry čárových kódů DataMatrix nastavením počtu řádků a sloupců, jak je ukázáno v kurzu.

### Q3: Kde mohu stáhnout Aspose.BarCode pro .NET?

 A3: Aspose.BarCode pro .NET si můžete stáhnout z[tento odkaz](https://releases.aspose.com/barcode/net/).

### Q4: Je k dispozici bezplatná zkušební verze pro Aspose.BarCode pro .NET?

 A4: Ano, máte přístup k bezplatné zkušební verzi Aspose.BarCode pro .NET[tady](https://releases.aspose.com/).

### Q5: Jak mohu získat dočasnou licenci pro Aspose.BarCode pro .NET?

 A5: Chcete-li získat dočasnou licenci pro Aspose.BarCode pro .NET, navštivte[tento odkaz](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

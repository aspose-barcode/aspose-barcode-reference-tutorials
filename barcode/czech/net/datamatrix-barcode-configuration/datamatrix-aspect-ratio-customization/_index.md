---
date: 2026-01-12
description: Naučte se, jak vytvořit PNG čárový kód s vlastním poměrem stran DataMatrix
  pomocí Aspose.BarCode pro .NET. Podrobný návod krok za krokem pro generování čárových
  kódů a přizpůsobení velikosti.
linktitle: DataMatrix Aspect Ratio Customization
second_title: Aspose.BarCode .NET API
title: Vytvořit čárový kód PNG – Poměr stran DataMatrix – Aspose.BarCode
url: /cs/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření PNG čárového kódu – poměr stran DataMatrix – Aspose.BarCode

Generování **PNG čárového kódu** s vlastním poměrem stran DataMatrix je častý požadavek, když potřebujete, aby čárový kód zapadl do konkrétních rozvržení. V tomto tutoriálu projdeme přesné kroky k **vytvoření PNG souborů** čárových kódů pomocí Aspose.BarCode pro .NET, vysvětlíme, proč můžete chtít upravit poměr stran, a ukážeme, jak jemně doladit výstup pro vaši aplikaci.

## Rychlé odpovědi
- **Co řídí „poměr stran“?** Definuje poměr šířky k výšce modulů DataMatrix.  
- **Mohu výstup v PNG, JPEG nebo SVG?** Ano – metoda `Save` podporuje PNG, JPEG, BMP, GIF a další.  
- **Potřebuji licenci pro tuto funkci?** Bezplatná zkušební verze funguje pro vývoj; plná licence je vyžadována pro produkci.  
- **Které verze .NET jsou podporovány?** .NET Framework 4.x, .NET Core 3.1+, .NET 5/6/7.  
- **Kolik hodnot poměru stran je platných?** Jakékoli kladné desetinné číslo; typické hodnoty jsou 0,5 – 2,0.

## Co je DataMatrix čárový kód a proč upravovat jeho poměr stran?
DataMatrix je dvourozměrný maticový čárový kód, který ukládá velké množství dat v malém prostoru. Úprava **poměru stran** vám umožní vodorovně roztáhnout nebo zkomprimovat moduly, což může být užitečné pro umístění čárového kódu do úzkých sloupců nebo širokých štítků bez ztráty čitelnosti.

## Předpoklady

Než začneme upravovat poměry stran DataMatrix, ujistěte se, že máte následující předpoklady:

1. **Visual Studio** – jakákoli aktuální verze postačí.  
2. **Aspose.BarCode pro .NET** – stáhněte si jej [zde](https://releases.aspose.com/barcode/net/).  
3. **.NET Framework / .NET Core** – váš projekt musí cílit na podporovanou verzi.

## Import jmenných prostorů

Nejprve musíte importovat potřebný jmenný prostor ve vašem C# projektu:

```csharp
using Aspose.BarCode.Generation;
```

> **Tip:** Umístěte tento `using` příkaz na začátek souboru, aby třída `BarcodeGenerator` byla vždy k dispozici.

## Průvodce krok za krokem

### Krok 1: Nastavení projektu
Vytvořte nový konzolový nebo Windows Forms projekt ve Visual Studiu a přidejte odkaz na Aspose.BarCode DLL.

### Krok 2: Inicializace generátoru čárových kódů
Vytvořte instanci `BarcodeGenerator` s typem DataMatrix a daty, která chcete kódovat:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> Tento řádek vytvoří generátor připravený vytvořit DataMatrix čárový kód obsahující ukázkový text.

### Krok 3: Přizpůsobení poměru stran a uložení PNG souborů
Nyní můžete změnit **poměr stran** a uložit každou verzi jako PNG obrázek:

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- První volání vytvoří čtvercový čárový kód (`AspectRatio = 1`).  
- Druhé volání komprimuje čárový kód vodorovně (`AspectRatio = 0.5`), čímž získá širší vzhled.

Nyní máte dva **PNG soubory čárových kódů** s různými poměry stran připravené k použití v reportech, štítcích nebo UI prvcích.

## Časté problémy a řešení
| Problém | Řešení |
|---------|--------|
| **Vygenerovaný obrázek je rozmazaný** | Zvyšte parametr `Resolution` před uložením (`gen.Parameters.ImageResolution = 300`). |
| **Čárový kód se nedaří načíst** | Ujistěte se, že poměr stran zůstává v rozmezí 0,5 – 2,0 a zachovejte dostatečnou klidovou zónu (`gen.Parameters.Barcode.CodeTextParameters.Margin`). |
| **Chyby v cestě k souboru** | Použijte `Path.Combine` pro vytvoření výstupní cesty a ověřte, že složka existuje. |

## Často kladené otázky

**Q: Mohu upravit poměr stran i u jiných typů čárových kódů pomocí Aspose.BarCode pro .NET?**  
A: Ano, mnoho 2‑D čárových kódů (např. QR, PDF417) podporuje úpravy poměru stran prostřednictvím jejich specifických objektů parametrů.

**Q: Je k dispozici bezplatná zkušební verze Aspose.BarCode pro .NET?**  
A: Ano, bezplatnou zkušební verzi získáte [zde](https://releases.aspose.com/).

**Q: Kde mohu zakoupit licenci pro Aspose.BarCode pro .NET?**  
A: Licenci můžete zakoupit na webu Aspose [zde](https://purchase.aspose.com/buy).

**Q: Je Aspose.BarCode pro .NET kompatibilní s různými verzemi .NET Framework?**  
A: Ano, funguje s .NET Framework 4.x, .NET Core 3.1+ a nejnovějšími verzemi .NET.

**Q: Mohu generovat čárové kódy v různých formátech pomocí Aspose.BarCode pro .NET?**  
A: Rozhodně – PNG, JPEG, BMP, GIF, TIFF, SVG a PDF jsou všechny podporovány přímo z krabice.

## Závěr

Přizpůsobení **poměru stran** DataMatrix čárového kódu a **vytvoření PNG souborů** čárových kódů je s Aspose.BarCode pro .NET jednoduché. Dodržením výše uvedených kroků můžete generovat perfektně dimenzované čárové kódy, které splňují přesné požadavky vašeho rozvržení. Prozkoumejte další parametry jako `Resolution`, `Margin` a `Color` pro další úpravy výstupu.

Pro podrobnější informace navštivte oficiální [dokumentaci](https://reference.aspose.com/barcode/net/) nebo se připojte ke komunitě na [fóru Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**Poslední aktualizace:** 2026-01-12  
**Testováno s:** Aspose.BarCode 24.12 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-05-30
description: Naučte se, jak vytvořit PNG čárového kódu s vlastním poměrem stran DataMatrix
  pomocí Aspose.BarCode pro .NET. Praktický návod krok za krokem pro generování čárových
  kódů a přizpůsobení velikosti.
keywords:
- create barcode png
- generate datamatrix barcode
- asp.net barcode generation
- barcode generation visual studio
linktitle: Přizpůsobení poměru stran DataMatrix
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  headline: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  name: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  steps:
  - name: Set Up Your Project
    text: Create a new console or Windows Forms project in Visual Studio and add a
      reference to the Aspose.BarCode DLL.
  - name: Initialize a Barcode Generator
    text: 'Instantiate it with the DataMatrix symbology and the data you want to encode:
      `BarcodeGenerator` creates a barcode image from the specified symbology and
      data. > This line creates a generator ready to produce a DataMatrix barcode
      that contains the sample text.'
  - name: Customize Aspect Ratio and Save PNG Files
    text: 'Now you can change the **aspect ratio** and save each version as a PNG
      image: `AspectRatio` sets the width‑to‑height proportion of the DataMatrix modules.
      `Save` writes the generated barcode image to a file in the chosen format. -
      The first call creates a square‑proportioned barcode (`AspectRatio = '
  type: HowTo
- questions:
  - answer: Yes, many 2‑D barcodes (e.g., QR, PDF417) support aspect‑ratio adjustments
      through their specific parameter objects.
    question: Can I customize the aspect ratio of other barcode types using Aspose.BarCode
      for .NET?
  - answer: Yes, you can access a free trial of Aspose.BarCode for .NET [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: You can purchase a license on the Aspose website [here](https://purchase.aspose.com/buy).
    question: Where can I purchase a license for Aspose.BarCode for .NET?
  - answer: Yes, it works with .NET Framework 4.x, .NET Core 3.1+, and the latest
      .NET releases.
    question: Is Aspose.BarCode for .NET compatible with different .NET Framework
      versions?
  - answer: Absolutely – PNG, JPEG, BMP, GIF, TIFF, SVG, and PDF are all supported
      out of the box.
    question: Can I generate barcodes in different formats with Aspose.BarCode for
      .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Vytvořit PNG čárového kódu – Poměr stran DataMatrix – Aspose.BarCode
url: /cs/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření PNG čárového kódu – poměr stran DataMatrix – Aspose.BarCode

Generování **barcode PNG** s vlastním poměrem stran DataMatrix je běžný požadavek, když potřebujete **vytvořit barcode PNG** soubory, které odpovídají konkrétním rozložení. V tomto tutoriálu projdeme přesné kroky k **vytvoření barcode PNG** souborů pomocí Aspose.BarCode pro .NET, vysvětlíme, proč můžete chtít upravit poměr stran, a ukážeme, jak jemně doladit výstup pro vaši aplikaci.

## Rychlé odpovědi
- **Co řídí „poměr stran“?** Definuje poměr šířky k výšce modulů DataMatrix.  
- **Mohu výstupně získat PNG, JPEG nebo SVG?** Ano – metoda `Save` podporuje PNG, JPEG, BMP, GIF, TIFF, SVG a PDF.  
- **Potřebuji licenci pro tuto funkci?** Bezplatná zkušební verze funguje pro vývoj; plná licence je vyžadována pro produkci.  
- **Které verze .NET jsou podporovány?** .NET Framework 4.x, .NET Core 3.1+, .NET 5/6/7.  
- **Kolik hodnot poměru stran je platných?** Jakékoli kladné desetinné číslo; typické hodnoty jsou 0.5 – 2.0.

## Co je čárový kód DataMatrix a proč upravovat jeho poměr stran?
DataMatrix čárový kód je dvourozměrný maticový kód, který ukládá velké množství dat do kompaktního čtverce. Úprava **aspect ratio** vám umožní vodorovně roztáhnout nebo zkomprimovat moduly, což je užitečné, když potřebujete čárový kód umístit do úzkých sloupců nebo širokých štítků, aniž byste ohrozili spolehlivost skenování.

## Proč použít Aspose.BarCode k vytvoření barcode PNG?
Aspose.BarCode podporuje **7 formátů obrázků** — PNG, JPEG, BMP, GIF, TIFF, SVG a PDF — a může zpracovávat **více než 50 vstupních a výstupních formátů** v paměti, zvládá dokumenty s několika stovkami stránek, aniž by načítal celý soubor. Knihovna poskytuje plynulé API, které vám umožní vygenerovat DataMatrix čárový kód v jediném řádku kódu, zaručující pixel‑dokonalé vykreslení a plnou kompatibilitu s .NET.

## Předpoklady

Než začneme přizpůsobovat poměry stran DataMatrix, ujistěte se, že máte následující předpoklady:

1. **Visual Studio** – jakákoli nedávná verze bude stačit.  
2. **Aspose.BarCode for .NET** – stáhněte jej [zde](https://releases.aspose.com/barcode/net/).  
3. Další vydání produktů Aspose můžete prozkoumat [zde](https://releases.aspose.com/).  
4. **.NET Framework / .NET Core** – váš projekt musí cílit na podporovanou verzi.

## Importování jmenných prostorů

Nejprve musíte ve svém C# projektu importovat potřebný jmenný prostor: `using Aspose.BarCode.Generation;` importuje jmenný prostor, který obsahuje třídy pro generování čárových kódů.  

```csharp
using Aspose.BarCode.Generation;
```

> **Tip:** Uchovávejte tento `using` příkaz na začátku souboru, aby třída `BarcodeGenerator` byla vždy k dispozici.

## Jak vytvořit barcode PNG s vlastním poměrem stran?

Načtěte `BarcodeGenerator`, nastavte typ DataMatrix, upravte vlastnost `AspectRatio` a zavolejte `Save`. Tento jednorázový vzor vytvoří barcode PNG, který respektuje zadaný poměr, a knihovna automaticky zpracuje škálování modulů a tiché zóny.  
`BarcodeGenerator` vytváří obrázek čárového kódu ze zadané symbologie a dat.  

### Krok 1: Nastavte svůj projekt
Vytvořte nový konzolový nebo Windows Forms projekt ve Visual Studiu a přidejte odkaz na Aspose.BarCode DLL.

### Krok 2: Inicializujte generátor čárových kódů
Vytvořte jeho instanci s DataMatrix symbologií a daty, která chcete kódovat: `BarcodeGenerator` vytváří obrázek čárového kódu ze zadané symbologie a dat.  

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> Tento řádek vytvoří generátor připravený vytvořit DataMatrix čárový kód, který obsahuje ukázkový text.

### Krok 3: Přizpůsobte poměr stran a uložte PNG soubory
Nyní můžete změnit **aspect ratio** a uložit každou verzi jako PNG obrázek: `AspectRatio` nastavuje poměr šířky k výšce modulů DataMatrix. `Save` zapíše vygenerovaný obrázek čárového kódu do souboru ve zvoleném formátu.  

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- První volání vytvoří čtvercový čárový kód (`AspectRatio = 1`).  
- Druhé volání komprimuje čárový kód vodorovně (`AspectRatio = 0.5`), což vytváří širší vzhled.

Nyní máte dva **barcode PNG** soubory s různými poměry stran připravené k použití v reportech, štítcích nebo UI prvcích.

## Časté problémy a řešení

| Problém | Řešení |
|-------|----------|
| **Vygenerovaný obrázek je rozmazaný** | Zvyšte parametr `Resolution` před uložením (`gen.Parameters.ImageResolution = 300`). |
| **Čárový kód se nedaří načíst** | Ujistěte se, že poměr stran zůstává v rozmezí 0.5 – 2.0 a zachovejte dostatečnou tichou zónu (`gen.Parameters.Barcode.CodeTextParameters.Margin`). |
| **Chyby cesty k souboru** | Použijte `Path.Combine` pro vytvoření výstupní cesty a ověřte, že složka existuje. |

## Často kladené otázky

**Q: Mohu přizpůsobit poměr stran jiných typů čárových kódů pomocí Aspose.BarCode pro .NET?**  
A: Ano, mnoho 2‑D čárových kódů (např. QR, PDF417) podporuje úpravy poměru stran prostřednictvím jejich specifických objektů parametrů.

**Q: Je k dispozici bezplatná zkušební verze Aspose.BarCode pro .NET?**  
A: Ano, bezplatnou zkušební verzi Aspose.BarCode pro .NET můžete získat [zde](https://releases.aspose.com/).

**Q: Kde mohu zakoupit licenci pro Aspose.BarCode pro .NET?**  
A: Licenci můžete zakoupit na webu Aspose [zde](https://purchase.aspose.com/buy).

**Q: Je Aspose.BarCode pro .NET kompatibilní s různými verzemi .NET Framework?**  
A: Ano, funguje s .NET Framework 4.x, .NET Core 3.1+ a nejnovějšími verzemi .NET.

**Q: Mohu generovat čárové kódy v různých formátech pomocí Aspose.BarCode pro .NET?**  
A: Rozhodně – PNG, JPEG, BMP, GIF, TIFF, SVG a PDF jsou všechny podporovány přímo.

## Závěr

Přizpůsobení **aspect ratio** DataMatrix čárového kódu a **vytvoření barcode PNG** souborů je s Aspose.BarCode pro .NET jednoduché. Dodržením výše uvedených kroků můžete generovat dokonale velikostní čárové kódy, které splňují přesné požadavky na rozvržení vašeho projektu. Prozkoumejte další parametry jako `Resolution`, `Margin` a `Color`, abyste dále upravili výstup, a zvažte možnosti `generate datamatrix barcode` při tvorbě aplikací přátelských ke skenování ve Visual Studiu.

Pro podrobnější průzkum si prohlédněte oficiální [dokumentaci](https://reference.aspose.com/barcode/net/) nebo se připojte ke komunitě na [fóru Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**Poslední aktualizace:** 2026-05-30  
**Testováno s:** Aspose.BarCode 24.12 pro .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Generovat DataMatrix čárový kód – profesionální průvodce s Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/)
- [Jak generovat DataMatrix čárové kódy (ECC 200) s Aspose.BarCode pro .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Mistrovské kódování DataMatrix v ASCII s Aspose.BarCode pro .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
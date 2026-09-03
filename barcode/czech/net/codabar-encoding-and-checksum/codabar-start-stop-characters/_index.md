---
date: 2026-05-24
description: Naučte se, jak vytvořit čárový kód Codabar s start a stop znaky pomocí
  Aspose.BarCode pro .NET. Podrobný návod na generování čárových kódů krok za krokem
  pro vývojáře.
keywords:
- create codabar barcode
- codabar start stop characters
- aspose barcode example
- barcode generation .net core
linktitle: Codabar – znaky Start/Stop
schemas:
- author: Aspose
  dateModified: '2026-05-24'
  description: Learn how to create codabar barcode with start and stop characters
    using Aspose.BarCode for .NET. Step‑by‑step barcode generation tutorial for developers.
  headline: Create Codabar Barcode with Start/Stop Characters in Aspose.BarCode for
    .NET
  type: TechArticle
- description: Learn how to create codabar barcode with start and stop characters
    using Aspose.BarCode for .NET. Step‑by‑step barcode generation tutorial for developers.
  name: Create Codabar Barcode with Start/Stop Characters in Aspose.BarCode for .NET
  steps:
  - name: Initialize the Barcode Generator
    text: '`BarcodeGenerator` is the core class that creates barcode images. It takes
      the symbology type and the data string as constructor arguments. > **Pro tip:**
      The dash (`-`) is one of the valid start/stop symbols for Codabar. You can also
      use `A`, `B`, `C`, or `D` depending on your application’s require'
  - name: Set the X‑Dimension (barcode element width)
    text: '`XDimension` controls the width of the narrowest bar. Larger values improve
      readability on low‑resolution printers, while smaller values conserve space
      on high‑density labels. > **Why it matters:** Adjusting `XDimension` helps you
      meet scanner specifications that often require a minimum bar width of'
  - name: Define Start and Stop Characters
    text: Codabar supports four start/stop symbols (A, B, C, D). Below are examples
      for each option. Choose the one that matches the specification of the system
      you’re integrating with.
  - name: Save the Generated Barcode Images (PNG)
    text: '`Save` writes the barcode to a file. Using `BarCodeImageFormat.Png` produces
      lossless PNG images that are ideal for web and print use cases. Each file now
      contains a **codabar barcode example** with the corresponding start/stop symbols.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET
    question: What library do I need?
  - answer: PNG (`BarCodeImageFormat.Png`)
    question: Which format can I save the barcode in?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license for development?
  - answer: Yes – use `CodabarSymbol.A`, `B`, `C`, or `D`.
    question: Can I change the start/stop symbols?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Vytvoření čárového kódu Codabar s Start/Stop znaky v Aspose.BarCode pro .NET
url: /cs/net/codabar-encoding-and-checksum/codabar-start-stop-characters/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořte čárový kód Codabar se start/stop znaky v Aspose.BarCode pro .NET

## Úvod

V tomto tutoriálu **vytvoříte obrázky čárových kódů codabar**, které obsahují explicitní start/stop znaky pomocí Aspose.BarCode pro .NET. Ať už budujete systém inventarizace v maloobchodě, sledování laboratorních vzorků nebo řešení pro lékařské záznamy, numerická symbologie Codabar se spoléhá na tyto ohraničující symboly, aby zajistila spolehlivé skenování. V následujících několika minutách pokryjeme vše od nastavení prostředí po ukládání PNG souborů, takže můžete okamžitě začít generovat čárové kódy Codabar.

## Rychlé odpovědi
- **Jaká knihovna potřebuji?** Aspose.BarCode pro .NET  
- **Do jakého formátu mohu čárový kód uložit?** PNG (`BarCodeImageFormat.Png`)  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro testování; pro produkci je vyžadována komerční licence.  
- **Mohu změnit start/stop symboly?** Ano – použijte `CodabarSymbol.A`, `B`, `C` nebo `D`.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Co je Codabar a proč jsou start/stop znaky nezbytné?

Codabar je numerická symbologie čárových kódů široce používaná v knihovnách, zdravotnictví a řízení zásob. Start a stop znaky (A‑D nebo pomlčka) definují hranice čárového kódu, což umožňuje skenerům zjistit, kde data začínají a končí, s 99,9 % přesností čtení.

## Proč použít Aspose.BarCode pro .NET?

Aspose.BarCode podporuje **více než 30 symbologií čárových kódů** a může generovat obrázky až do **10 000 × 10 000 px** bez načítání celého dokumentu do paměti. Funguje na Windows, Linuxu i macOS a je kompatibilní s .NET Framework, .NET Core a .NET 5+ — poskytuje vám flexibilitu napříč všemi moderními platformami.

## Požadavky

1. **Nastavení prostředí** – Zajistěte funkční .NET vývojové prostředí. Pokud potřebujete návod, podívejte se na [dokumentaci](https://reference.aspose.com/barcode/net/).  
2. **Aspose.BarCode pro .NET knihovna** – Stáhněte a nainstalujte knihovnu z oficiálního [zdroje](https://releases.aspose.com/barcode/net/).  
3. **Základní znalosti .NET** – Znalost C# a IDE jako Visual Studio, Rider nebo VS Code.  
4. **IDE** – Visual Studio, Rider nebo Visual Studio Code jsou všechny v pořádku.

Nyní, když jsme prošli požadavky, pojďme se ponořit do samotného kódu.

## Jak vygenerovat čárový kód Codabar se start/stop znaky?

Načtěte `BarcodeGenerator`, nastavte typ kódování na **Codabar** a předávejte řetězec dat, který již obsahuje požadované start/stop symboly (například “-12345-”). Pak nakonfigurujte X‑Dimension, volitelně vyberte jiný start/stop symbol a nakonec uložte obrázek jako PNG. Tento end‑to‑end tok vytvoří připravený čárový kód během několika řádků C#.

### Importovat jmenné prostory

`BarcodeGenerator` a související typy se nacházejí v jmenném prostoru `Aspose.BarCode.Generation`.

```csharp
using Aspose.BarCode.Generation;
```

### Krok 1: Inicializace generátoru čárových kódů

`BarcodeGenerator` je hlavní třída, která vytváří obrázky čárových kódů. Přijímá typ symbologie a řetězec dat jako argumenty konstruktoru.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarStartStop:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

> **Tip:** Pomlčka (`-`) je jedním z platných start/stop symbolů pro Codabar. Můžete také použít `A`, `B`, `C` nebo `D` podle požadavků vaší aplikace.

### Krok 2: Nastavení X‑Dimension (šířka elementu čárového kódu)

`XDimension` řídí šířku nejúzkého pruhu. Větší hodnoty zlepšují čitelnost na nízkorizolucních tiskárnách, zatímco menší hodnoty šetří místo na vysoce hustých štítcích.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Proč je to důležité:** Úprava `XDimension` vám pomůže splnit specifikace skenerů, které často vyžadují minimální šířku pruhu 0,25 mm.

### Krok 3: Definice start a stop znaků

Codabar podporuje čtyři start/stop symboly (A, B, C, D). Níže jsou příklady pro každou možnost. Vyberte tu, která odpovídá specifikaci systému, do kterého integrujete.

#### Nastavení Start A a Stop A

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.A;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.A;
```

#### Nastavení Start B a Stop B

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.B;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.B;
```

#### Nastavení Start C a Stop C

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.C;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.C;
```

#### Nastavení Start D a Stop D

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.D;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.D;
```

Můžete opakovat konfiguraci pro každý symbol, který potřebujete vygenerovat; níže uvedený příklad uloží čtyři samostatné obrázky — jeden pro každý start/stop pár.

### Krok 4: Uložení vygenerovaných obrázků čárových kódů (PNG)

`Save` zapíše čárový kód do souboru. Použití `BarCodeImageFormat.Png` vytváří bezztrátové PNG obrázky, které jsou ideální pro web i tisk.

```csharp
gen.Save($"{path}CodabarStartAStopA.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartBStopB.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartCStopC.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartDStopD.png", BarCodeImageFormat.Png);
```

Každý soubor nyní obsahuje **příklad čárového kódu codabar** s odpovídajícími start/stop symboly.

## Časté problémy a řešení

| Příznak | Pravděpodobná příčina | Oprava |
|---------|-----------------------|--------|
| Čárový kód vypadá zkresleně | X‑Dimension příliš nízká pro zvolenou rozlišení tiskárny | Zvyšte `XDimension.Pixels` (např. na 3 nebo 4) |
| Scanner nedokáže přečíst start/stop | Špatný start/stop symbol pro cílový systém | Ověřte požadovaný symbol (A‑D) a nastavte jej podle toho |
| Soubor PNG je prázdný nebo poškozený | Neplatná výstupní cesta nebo nedostatečná oprávnění k zápisu | Ujistěte se, že `path` ukazuje na existující složku a aplikace má oprávnění k zápisu |

## Často kladené otázky

**Q1: Co je Codabar a proč jsou start a stop znaky důležité?**  
A: Codabar je numerická symbologie čárových kódů používaná v inventáři, knihovnách a zdravotnictví. Start/stop znaky definují hranice čárového kódu, což zajišťuje, že skenery vědí, kde data začínají a končí.

**Q2: Mohu přizpůsobit vzhled čárových kódů Codabar pomocí Aspose.BarCode pro .NET?**  
A: Ano. Kromě X‑Dimension můžete měnit barvy, přidávat okraje a exportovat do PDF nebo SVG pomocí stejného API.

**Q3: Existují omezení čárových kódů Codabar z hlediska kódování dat?**  
A: Codabar primárně podporuje číselná data (0‑9) a omezenou sadu speciálních znaků. Není vhodný pro plně alfanumerické řetězce.

**Q4: Je Aspose.BarCode pro .NET vhodný pro komerční použití a jak získám licenci?**  
A: Ano, je připravený pro produkci. Licenci si můžete zakoupit na [stránce nákupu Aspose](https://purchase.aspose.com/buy).

**Q5: Kde mohu získat pomoc nebo diskutovat o problémech souvisejících s Aspose.BarCode pro .NET?**  
A: Připojte se ke komunitě na [fóru podpory Aspose.BarCode pro .NET](https://forum.aspose.com/c/barcode/13), kde vám pomohou jak inženýři Aspose, tak ostatní vývojáři.

---

**Poslední aktualizace:** 2026-05-24  
**Testováno s:** Aspose.BarCode 24.11 pro .NET  
**Autor:** Aspose

## Související tutoriály

- [Codabar Start Stop znaky a kontrolní součet](/barcode/net/codabar-encoding-and-checksum/)
- [Jak přidat kontrolní součet k čárovým kódům Codabar pomocí Aspose.BarCode pro .NET](/barcode/net/codabar-encoding-and-checksum/codabar-checksum-calculation/)
- [Komplexní tutoriály a příklady Aspose.BarCode pro .NET](/barcode/net/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
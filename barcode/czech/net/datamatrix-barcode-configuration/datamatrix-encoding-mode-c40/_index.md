---
date: 2026-06-09
description: Naučte se, jak generovat DataMatrix čárové kódy a uložit PNG pomocí kódování
  C40 s Aspose.BarCode – kompletní průvodce generováním čárových kódů pro .NET Core.
keywords:
- how to generate datamatrix
- barcode generation .net core
- datamatrix c40 png
linktitle: Režim kódování DataMatrix (C40)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  headline: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  type: TechArticle
- description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  name: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  steps:
  - name: Define the Directory Path
    text: Set the folder where the PNG image will be stored. Replace the placeholder
      with an actual path on your machine.
  - name: Set Up Barcode Generation
    text: Create a `BarcodeGenerator` instance, specify `EncodeTypes.DataMatrix`,
      and provide the data you want to encode.
  - name: Customize Barcode
    text: Configure the X‑dimension (pixel width of the modules) and switch the encoding
      mode to C40.
  - name: Save the Barcode Image
    text: Finally, save the generated barcode as a PNG file. This is the concrete
      answer to **how to save png** with Aspose.BarCode. When you run the program,
      you’ll find `DataMatrixEncodeModeC40.png` in the folder you specified, ready
      to be used in reports, labels, or web pages.
  type: HowTo
- questions:
  - answer: C40 is a compact alphanumeric encoding scheme for DataMatrix symbols,
      ideal for text that includes letters, numbers, and a limited set of special
      characters.
    question: What is DataMatrix Encoding Mode (C40)?
  - answer: You can find the documentation [here](https://reference.aspose.com/barcode/net/).
      It provides detailed guidance on all barcode types and encoding options.
    question: Where can I find the Aspose.BarCode for .NET documentation?
  - answer: Yes, the library supports a wide range of .NET versions, from .NET Framework
      4.5+ to .NET 6 and later.
    question: Is Aspose.BarCode for .NET compatible with all .NET versions?
  - answer: Yes, you can explore a free trial of Aspose.BarCode for .NET by visiting
      [this link](https://releases.aspose.com/). It allows you to test the library’s
      features and capabilities.
    question: Can I try Aspose.BarCode for .NET before purchasing?
  - answer: You can find a supportive community and access support for Aspose.BarCode
      for .NET on the [Aspose forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Jak generovat DataMatrix PNG s C40 pomocí Aspose.BarCode
url: /cs/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hlavní režim kódování DataMatrix (C40) s Aspose.BarCode pro .NET

## Úvod

V tomto tutoriálu se naučíte **jak generovat datamatrix** čárové kódy a uložit je jako soubory PNG pomocí režimu kódování C40 s Aspose.BarCode pro .NET. Ať už vytváříte systém inventarizace, generátor přepravních štítků nebo jakékoli řešení vyžadující kompaktní, vysoce husté symboly, zvládnutí C40 vám poskytne menší symboly bez ztráty čitelnosti. Provedeme vás každým krokem – od nastavení prostředí až po vytvoření finálního PNG – abyste mohli kód okamžitě integrovat do svého projektu.

## Rychlé odpovědi
- **Co znamená „how to generate datamatrix“?** Vytvoření obrázku DataMatrix čárového kódu programově.  
- **Který režim kódování je pokryt?** DataMatrix C40, efektivní alfanumerické schéma.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro testování; pro produkční nasazení je vyžadována komerční licence.  
- **Mohu to spustit na .NET Core?** Ano, Aspose.BarCode plně podporuje .NET Core, .NET 5, .NET 6 a novější.  
- **Jaký formát souboru je vytvořen?** PNG – bezztrátový, webově přátelský formát obrázku.

## Jak generovat DataMatrix s kódováním C40

Načtěte svá data, nakonfigurujte generátor a zavolejte `Save` – to je kompletní pracovní postup ve třech stručných krocích. Třída `BarcodeGenerator` zajišťuje vytvoření symbolu, zatímco výčet `BarCodeImageFormat.Png` říká Aspose.BarCode, aby výsledek zapsal jako soubor PNG. `Save` zapíše vygenerovaný obrázek čárového kódu na zadanou cestu v zvoleném formátu. Tento přímý odstavcový odpověď vám poskytuje kompletní řešení, než se ponoříme do jednotlivých řádků kódu.

## Co je režim kódování DataMatrix (C40)?

`DataMatrixEncodeMode` je výčet, který určuje, jaké schéma kódování má Aspose.BarCode použít pro symboly DataMatrix. Volba `DataMatrixEncodeMode.C40` vybírá alfanumerické kódování C40, které komprimuje písmena, číslice a omezenou sadu interpunkčních znaků do méně modulů, čímž snižuje celkovou velikost symbolu při zachování čitelnosti typického textu inventáře. Toto efektivní schéma je ideální, když potřebujete kódovat alfanumerická data v kompaktní podobě.

## Proč použít Aspose.BarCode pro .NET?

Aspose.BarCode poskytuje **30+ konfigurovatelných parametrů** pro rozměry, úrovně korekce chyb a režimy kódování a podporuje **50+ formátů obrázků a čárových kódů**. Knihovna běží na **.NET Framework 4.5+, .NET Core 2.0+, .NET 5/6+**, což umožňuje generování bez závislostí, které funguje na serverech, desktopových a mobilních zařízeních.

## Předpoklady

1. **.NET vývojové prostředí** – Visual Studio, Rider nebo jakékoli IDE podporující C#.  
2. **Aspose.BarCode pro .NET** – nainstalováno přes NuGet nebo oficiální instalátor. Podrobnosti najdete v [dokumentaci](https://reference.aspose.com/barcode/net/).  
3. **Základní znalost C#** – měli byste být obeznámeni s jmennými prostory, třídami a using direktivami.  
4. **Složka s právy zápisu** – adresář ve vašem počítači, kam bude PNG uložen.

## Importování potřebných jmenných prostorů

Třída `BarcodeGenerator` je vstupním bodem pro vytváření jakéhokoli čárového kódu. Přidejte požadovaný jmenný prostor na začátek vašeho C# zdrojového souboru, abyste mohli přistupovat k API generování:

```csharp
using Aspose.BarCode.Generation;
```

## Postupná generace čárového kódu krok za krokem

Níže je **krok‑za‑krokem průvodce generováním čárového kódu**. Každý krok je vysvětlen srozumitelně a původní zástupné symboly jsou ponechány beze změny pro pohodlné kopírování.

### Krok 1: Definujte cestu ke složce
Nastavte složku, kde bude uložen obrázek PNG. Nahraďte zástupný symbol skutečnou cestou ve vašem počítači.

```csharp
string path = "Your Directory Path";
```

### Krok 2: Nastavte generování čárového kódu
Vytvořte instanci `BarcodeGenerator`, specifikujte `EncodeTypes.DataMatrix` a poskytněte data, která chcete kódovat.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE.BARCODE"))
{
    // Additional steps go here
}
```

### Krok 3: Přizpůsobte čárový kód
Nakonfigurujte X‑dimenzi (šířku pixelu modulů) a přepněte režim kódování na C40.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 6;
gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.C40;
```

### Krok 4: Uložte obrázek čárového kódu
Nakonec uložte vygenerovaný čárový kód jako soubor PNG. Toto je konkrétní odpověď na **jak uložit png** s Aspose.BarCode.

```csharp
gen.Save($"{path}DataMatrixEncodeModeC40.png", BarCodeImageFormat.Png);
```

Po spuštění programu najdete `DataMatrixEncodeModeC40.png` ve složce, kterou jste určili, připravený k použití ve zprávách, štítcích nebo webových stránkách.

## Časté problémy a tipy

- **Neplatná cesta** – Ujistěte se, že složka existuje a máte oprávnění k zápisu; jinak `gen.Save` vyhodí výjimku.  
- **Nesprávný režim kódování** – Pokud potřebujete kódovat znaky mimo sadu C40, přepněte na `DataMatrixEncodeMode.Auto` nebo jiný vhodný režim.  
- **Velikost obrázku** – Upravte `XDimension.Pixels` pro zvětšení nebo zmenšení celkové velikosti čárového kódu bez ovlivnění čitelnosti.

## Často kladené otázky

**Q: Co je režim kódování DataMatrix (C40)?**  
A: C40 je kompaktní alfanumerické kódovací schéma pro symboly DataMatrix, ideální pro text obsahující písmena, číslice a omezenou sadu speciálních znaků.

**Q: Kde mohu najít dokumentaci k Aspose.BarCode pro .NET?**  
A: Dokumentaci najdete [zde](https://reference.aspose.com/barcode/net/). Poskytuje podrobné pokyny ke všem typům čárových kódů a možnostem kódování.

**Q: Je Aspose.BarCode pro .NET kompatibilní se všemi verzemi .NET?**  
A: Ano, knihovna podporuje širokou škálu verzí .NET, od .NET Framework 4.5+ po .NET 6 a novější.

**Q: Můžu vyzkoušet Aspose.BarCode pro .NET před zakoupením?**  
A: Ano, můžete si vyzkoušet bezplatnou zkušební verzi Aspose.BarCode pro .NET na [této stránce](https://releases.aspose.com/). Umožní vám otestovat funkce a možnosti knihovny.

**Q: Kde mohu získat podporu pro Aspose.BarCode pro .NET?**  
A: Podporu a komunitu najdete na [fóru Aspose](https://forum.aspose.com/c/barcode/13).

## Závěr

Podle tohoto **průvodce krok‑za‑krokem** nyní přesně víte **jak generovat datamatrix** čárové kódy a uložit je jako soubory PNG pomocí režimu kódování C40 s Aspose.BarCode pro .NET. Tento přístup vám poskytuje plnou kontrolu nad vzhledem, velikostí a reprezentací dat čárového kódu, což usnadňuje vložení vysoce kvalitních čárových kódů do jakékoli .NET aplikace.

---

**Last Updated:** 2026-06-09  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Kódování DataMatrix v bajtech s Aspose.BarCode pro .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [Hlavní kódování DataMatrix v ASCII s Aspose.BarCode pro .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Jak generovat DataMatrix čárové kódy (ECC 200) s Aspose.BarCode pro .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
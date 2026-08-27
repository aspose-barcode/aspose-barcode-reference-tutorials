---
date: 2026-06-09
description: Naučte se, jak vytvořit DataMatrix čárový kód v režimu ASCII pomocí Aspose.BarCode
  pro .NET. Tento průvodce ukazuje, jak rychle vygenerovat čárový kód v C#.
keywords:
- create datamatrix barcode
- generate barcode c#
- how to encode barcode
- barcode generator example
linktitle: Režim kódování DataMatrix (ASCII)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  headline: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  name: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  steps:
  - name: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
    text: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
  - name: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
  - name: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
    text: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
  - name: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
    text: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
  type: HowTo
- questions:
  - answer: Yes, a valid Aspose license is required for production use; a free trial
      is available for evaluation.
    question: Can I use this in a commercial application?
  - answer: Absolutely – Aspose.BarCode fully supports .NET Core 3.1+, .NET 5, .NET
      6, and later versions.
    question: Does the library work with .NET Core?
  - answer: Up to 2,335 alphanumeric characters fit in a single DataMatrix symbol
      when using ASCII encoding.
    question: How many characters can I encode in ASCII mode?
  - answer: Yes, adjust `generator.Parameters.Image.ForeColor` and `BackColor` to
      any `System.Drawing.Color` value.
    question: Can I change the barcode’s foreground or background color?
  - answer: The official documentation contains dozens of samples covering custom
      sizes, colors, and error‑correction levels.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Vytvořte DataMatrix čárový kód v režimu ASCII s Aspose.BarCode pro .NET
url: /cs/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/
weight: 13
---

{{< blocks/products/pf/main-container >}}
{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořte DataMatrix čárový kód v ASCII režimu pomocí Aspose.BarCode pro .NET

## Úvod

Připraveni **vytvořit DataMatrix čárový kód** obrázky, které využívají efektivní ASCII kódování? V tomto tutoriálu se naučíte, jak vygenerovat DataMatrix čárový kód v ASCII režimu pomocí Aspose.BarCode pro .NET. Provedeme vás každým krokem – od nastavení projektu až po uložení finálního obrázku – abyste mohli přidat generování čárových kódů do svých C# aplikací během několika minut.

## Rychlé odpovědi
- **Jaká knihovna je nejlepší pro DataMatrix v .NET?** Aspose.BarCode for .NET  
- **Kolik řádků kódu je potřeba?** Přibližně 5‑7 řádků pro základní ASCII čárový kód  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; licence je vyžadována pro produkci  
- **Podporované platformy?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **Mohu změnit velikost nebo barvy?** Ano, Aspose.BarCode poskytuje vlastnosti pro rozměry a barvy popředí/pozadí  

## Co je DataMatrix čárový kód?
DataMatrix je dvourozměrný čárový kód, který ukládá text a binární data v kompaktním čtvercovém vzoru.  
DataMatrix čárový kód kóduje informace v mřížce černých a bílých modulů a umožňuje až 2 335 alfanumerických znaků v jednom symbolu. Je široce používán ve výrobě, logistice a zdravotnictví, protože může být tištěn v velmi malých rozměrech a přitom zůstává snadno čitelný.

## Jak vytvořit DataMatrix čárový kód v ASCII režimu?
Načtěte jmenný prostor Aspose.BarCode, vytvořte instanci `BarcodeGenerator`, nastavte `EncodeMode` na **EncodeMode.ASCII**, přiřaďte svůj datový řetězec a zavolejte `Save` pro zápis souboru obrázku. Tento přístup vytvoří zcela kompatibilní DataMatrix čárový kód s čistě ASCII kódováním během několika řádků C# kódu.

## Proč používat ASCII kódování pro DataMatrix?
ASCII režim je výchozí a nejefektivnější kódování pro prostý text, poskytuje nejmenší možnou velikost symbolu pro alfanumerické řetězce. Podporuje všech 128 ASCII znaků, zpracovává data rychleji než rozšířené režimy a zaručuje maximální kompatibilitu se staršími skenery, které očekávají standardní ASCII symboly.

## Předpoklady

1. **Vývojové prostředí** – Visual Studio, Rider nebo jakékoli IDE kompatibilní s C#.  
2. **Aspose.BarCode for .NET** – Stáhněte nejnovější balíček z [zde](https://releases.aspose.com/barcode/net/).  
   - Dokumentace: [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)  
   - Komunitní pomoc: [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)  
3. **Základní znalost C#** – Znalost struktury .NET projektu vám pomůže rychle sledovat kroky.  
4. **Další produkty Aspose** najdete [zde](https://releases.aspose.com/).

## Importovat jmenné prostory

Pro začátek přidejte požadované `using` direktivy na začátek svého C# souboru:

```csharp
using Aspose.BarCode.Generation;
using System.Drawing;
```

Tyto jmenné prostory vám poskytují přístup ke třídě `BarcodeGenerator` a typům souvisejícím s obrázky, které jsou potřebné pro uložení výstupu.

## Krok 1: Vytvořit adresář

Vyberte složku, kde budou uloženy vygenerované obrázky čárových kódů. Nahraďte `"Your Directory Path"` absolutní nebo relativní cestou, která na vašem počítači existuje.

```csharp
string outputDir = @"C:\Barcodes";
if (!System.IO.Directory.Exists(outputDir))
{
    System.IO.Directory.CreateDirectory(outputDir);
}
```

Kód zajistí, že adresář existuje před pokusem o zápis souborů, čímž předchází chybám za běhu.

## Krok 2: Kódování dat v ASCII režimu

Třída `BarcodeGenerator` vytváří a konfiguruje obrázky čárových kódů. Výčtový typ `DataMatrixEncodeMode` vybírá algoritmus kódování pro DataMatrix symboly.

```csharp
// Initialise the generator with the data you want to encode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "1234567890");

// Set the encoding mode to ASCII for optimal size
generator.Parameters.Barcode.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;

// Optional: adjust image dimensions or colors here
generator.Parameters.Image.Width = 200;
generator.Parameters.Image.Height = 200;

// Save the barcode as a PNG file
string filePath = System.IO.Path.Combine(outputDir, "datamatrix_ascii.png");
generator.Save(filePath, BarCodeImageFormat.Png);
```

Po spuštění kódu najdete soubor `datamatrix_ascii.png` ve složce, kterou jste určili. Obrázek obsahuje DataMatrix čárový kód, který kóduje řetězec `"1234567890"` pomocí kompaktního ASCII režimu.

## Časté problémy a řešení

- **Chyby přístupu k souboru** – Ujistěte se, že aplikace má oprávnění k zápisu do cílové složky. Spuštění Visual Studia jako administrátor může vyřešit problémy s oprávněními ve Windows.  
- **Nesprávná velikost symbolu** – Pokud se čárový kód zdá příliš velký nebo malý, upravte `generator.Parameters.Image.Width` a `Height` nebo nechte Aspose automaticky vypočítat optimální velikost vynecháním těchto vlastností.  
- **Není podporované znaky** – ASCII režim přijímá pouze znaky v rozsahu 0‑127. Pro Unicode data přepněte na `DataMatrixEncodeMode.Base256` nebo jiný vhodný režim.

## Často kladené otázky

**Q: Mohu to použít v komerční aplikaci?**  
A: Ano, pro produkční použití je vyžadována platná licence Aspose; bezplatná zkušební verze je k dispozici pro hodnocení.

**Q: Funguje knihovna s .NET Core?**  
A: Rozhodně – Aspose.BarCode plně podporuje .NET Core 3.1+, .NET 5, .NET 6 a novější verze.

**Q: Kolik znaků mohu zakódovat v ASCII režimu?**  
A: Až 2 335 alfanumerických znaků se vejde do jednoho DataMatrix symbolu při použití ASCII kódování.

**Q: Mohu změnit barvu popředí nebo pozadí čárového kódu?**  
A: Ano, upravte `generator.Parameters.Image.ForeColor` a `BackColor` na libovolnou hodnotu `System.Drawing.Color`.

**Q: Kde najdu pokročilejší příklady?**  
A: Oficiální dokumentace obsahuje desítky vzorků pokrývajících vlastní velikosti, barvy a úrovně opravy chyb.

## Často kladené otázky

### Q1: Mohu použít Aspose.BarCode pro .NET s jinými programovacími jazyky než C#?

A1: Aspose.BarCode podporuje více programovacích jazyků, ale tento tutoriál se zaměřuje na C#.

### Q2: Jaké jsou různé režimy kódování dostupné v DataMatrix čárových kódech?

A2: DataMatrix čárové kódy podporují různé režimy kódování, včetně ASCII, C40, Text a Base256. Každý režim je vhodný pro jiný typ dat.

### Q3: Mohu přizpůsobit vzhled generovaného čárového kódu, například jeho velikost a barvu?

A3: Ano, Aspose.BarCode poskytuje širokou škálu parametrů pro přizpůsobení vzhledu čárového kódu, včetně velikosti, barvy a dalších.

### Q4: Je k dispozici bezplatná zkušební verze Aspose.BarCode pro .NET?

A4: Ano, můžete si vyzkoušet Aspose.BarCode pro .NET zdarma z [zde](https://releases.aspose.com/).

### Q5: Kde mohu zakoupit licenci pro Aspose.BarCode pro .NET?

A5: Licenci můžete zakoupit na webu Aspose [zde](https://purchase.aspose.com/buy).

---

**Poslední aktualizace:** 2026-06-09  
**Testováno s:** Aspose.BarCode 24.11 pro .NET  
**Autor:** Aspose

## Související tutoriály

- [DataMatrix kódování v bajtech s Aspose.BarCode pro .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [Čtení DataMatrix čárového kódu C# – Generování DataMatrix režimu (Auto)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Jak generovat DataMatrix čárové kódy (ECC 200) s Aspose.BarCode pro .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.BarCode.Generation;
```

```csharp
string path = "Your Directory Path";
```

```csharp
System.Console.WriteLine("DataMatrixEncodeModeASCII:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    // Set the X-dimension (size) of the barcode in pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set the encoding mode to ASCII
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;
    
    // Save the barcode as a PNG image
    gen.Save($"{path}DataMatrixEncodeModeASCII.png", BarCodeImageFormat.Png);
}
```

{{< /blocks/products/pf/main-container >}}
{{< blocks/products/pf/main-wrap-class >}}
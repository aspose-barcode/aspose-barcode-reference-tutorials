---
category: general
date: 2026-08-03
description: Návod na generování čárových kódů v C# ukazující, jak vytvořit Planet
  čárový kód pomocí Aspose.BarCode, nastavit X‑rozměr a uložit jako PNG obrázky.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- create planet barcode
language: cs
lastmod: 2026-08-03
og_description: Návod na generátor čárových kódů v C# vás provede vytvořením Planet
  čárového kódu, úpravou X‑dimenze a uložením jako PNG pomocí Aspose.BarCode.
og_image_alt: Screenshot of generated Planet and RM4SCC barcodes in PNG format
og_title: Generátor čárových kódů C# – vytvořte čárový kód Planet krok za krokem
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Barcode generator C# tutorial showing how to create Planet barcode
    with Aspose.BarCode, set X‑dimension, and save as PNG images.
  headline: Barcode generator C# – create Planet barcode and RM4SCC example
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Generátor čárových kódů C# – vytvořte příklad čárového kódu Planet a RM4SCC
url: /cs/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generátor čárových kódů C# – vytvoření Planet čárového kódu a příklad RM4SCC

Pokud potřebujete **barcode generator C#**, který dokáže vytvářet poštovní specifické symboly, tento návod vám ukáže, jak **vytvořit Planet čárový kód** pomocí Aspose.BarCode. Uvidíte, jak nastavit X‑dimenzi, vygenerovat odpovídající RM4SCC čárový kód a uložit oba jako PNG soubory – vše během několika stručných kroků.

Návod pokrývá vše, co potřebujete ke spuštění kódu na .NET 6 nebo novějším, vysvětluje, proč je každé nastavení důležité, a upozorňuje na běžné úskalí, jako je nesprávná šířka modulu nebo chybějící oprávnění ke složce. Na konci budete mít dva připravené obrázky čárových kódů, které splňují standardy Planet a RM4SCC.

## Požadavky

Než začnete, ujistěte se, že máte:

* .NET 6 SDK (nebo jakoukoli verzi .NET podporovanou Aspose.BarCode)
* Visual Studio 2022 nebo libovolné C# IDE dle vašeho výběru
* NuGet odkaz na **Aspose.BarCode** (`Install-Package Aspose.BarCode`)
* Oprávnění k zápisu do složky, kam budete ukládat PNG soubory

Žádné další externí služby nejsou potřeba; knihovna provádí veškeré kódování lokálně.

## Krok 1: Inicializace objektu barcode generator C#

Prvním úkolem je vytvořit instanci `BarcodeGenerator`. Konstruktor přijímá symbologii čárového kódu (`EncodeTypes.Planet`) a data, která mají být zakódována.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*Proč tento krok?*  
`BarcodeGenerator` je vstupním bodem pro každý čárový kód, který generujete. Výběrem `EncodeTypes.Planet` říkáte knihovně, aby se řídila specifikací ISO/IEC 24723 používanou mnoha poštovními službami.

## Krok 2: Nastavení X‑dimenze (šířka modulu) pro Planet čárový kód

X‑dimenze určuje šířku jednoho modulu čárového kódu (nejmenšího pruhu nebo mezery). Hodnota **4 pixely** funguje dobře pro většinu štítkových tiskáren.

```csharp
// Step 2: Define the X‑dimension (module width) in pixels
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Proč je to důležité*  
Pokud je modul příliš úzký, čárový kód může být nečitelný; pokud je příliš široký, velikost štítku zbytečně roste. Úpravou `Pixels` můžete jemně doladit čárový kód pro konkrétní rozlišení tiskárny.

## Krok 3: Uložení Planet čárového kódu jako PNG obrázku

Aspose.BarCode automaticky vypočítá výšku čárového kódu na základě zvolené symbologie, takže stačí zadat cestu k souboru a formát.

```csharp
// Step 3: Save the Planet barcode as a PNG image (height is calculated automatically)
planetGenerator.Save("YOUR_DIRECTORY/PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

*Tip*  
Nahraďte `YOUR_DIRECTORY` absolutní nebo relativní cestou, která na vašem počítači existuje. Pokud složka neexistuje, metoda `Save` vyhodí `DirectoryNotFoundException`.

**Očekávaný výstup** – PNG soubor, který vypadá podobně jako ilustrace níže (skutečný obrázek zde není zobrazen, ale uvidíte klasický Planet čárový kód s číselnou částí `123456`).

## Krok 4: Inicializace druhého generátoru pro RM4SCC čárový kód

Mnoho poštovních systémů vyžaduje na jednom dopise jak Planet, tak RM4SCC symboly. Vytvořte novou instanci `BarcodeGenerator` pro symbologii RM4SCC.

```csharp
// Step 4: Create an RM4SCC barcode generator with the same data
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
```

*Proč samostatná instance?*  
Každá symbologie má vlastní sadu parametrů. Použití stejného generátoru by mohlo neúmyslně přenést nastavení (např. X‑dimenzi), která nejsou pro druhý čárový kód optimální.

## Krok 5: Konfigurace X‑dimenze pro RM4SCC čárový kód

RM4SCC také respektuje nastavení X‑dimenze, takže použijeme stejnou šířku v pixelech pro vizuální konzistenci.

```csharp
// Step 5: Set the X‑dimension for the RM4SCC barcode
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Pro tip*  
Pokud potřebujete vyšší čárový kód (např. pro větší štítky), můžete také nastavit `Height.Pixels`. Pokud tuto hodnotu nenastavíte, knihovna automaticky vypočítá ideální výšku.

## Krok 6: Uložení RM4SCC čárového kódu jako PNG obrázku

Nakonec uložíme RM4SCC čárový kód na disk.

```csharp
// Step 6: Save the RM4SCC barcode as a PNG image (height is calculated automatically)
rm4sccGenerator.Save("YOUR_DIRECTORY/PostalRM4SCCBarHeightNone.png", BarCodeImageFormat.Png);
```

Nyní máte dva PNG soubory – `PostalPlanetBarHeightNone.png` a `PostalRM4SCCBarHeightNone.png` – které můžete vložit do poštovních štítků, vytisknout na obálky nebo poslat třetí straně pro tisk.

## Volitelné: Úprava výšky nebo použití jiných formátů obrázků

Pokud váš workflow vyžaduje konkrétní výšku čárového kódu nebo jiný formát obrázku (např. JPEG nebo BMP), můžete parametry upravit před voláním `Save`:

```csharp
// Example: set a fixed height of 100 pixels and save as JPEG
planetGenerator.Parameters.Barcode.Height.Pixels = 100;
planetGenerator.Save("PostalPlanet.jpg", BarCodeImageFormat.Jpeg);
```

**Hraniční případ** – Když nastavíte vlastní výšku, ujistěte se, že hodnota splňuje minimální výšku požadovanou ISO standardem; jinak může čárový kód selhat při validaci.

## Časté úskalí a jak se jim vyhnout

| Úskalí | Proč se to stane | Řešení |
|---------|----------------|-----|
| `DirectoryNotFoundException` | Cílová složka neexistuje nebo je špatně napsaná. | Nejprve vytvořte složku nebo použijte `Path.Combine` s `Environment.CurrentDirectory`. |
| Čárový kód nečitelný na tiskárnách s nízkým rozlišením | X‑dimenze je příliš malá pro DPI tiskárny. | Zvyšte `XDimension.Pixels` na 5 – 6 pro 203 dpi tiskárny, nebo otestujte na vzorovém štítku. |
| Špatná symbologie použita | Předání `EncodeTypes.Code128` místo `EncodeTypes.Planet`. | Zkontrolujte, že hodnota enumu `EncodeTypes` odpovídá požadovanému poštovnímu standardu. |
| Null reference na `Parameters` | Použití starší verze Aspose.BarCode, kde se API liší. | Aktualizujte na nejnovější NuGet balíček (v. 23.12 nebo novější). |

## Kompletní spustitelný příklad

Níže je celý program, který můžete zkopírovat, vložit a spustit. Obsahuje `using` direktivy, ošetření chyb a komentáře vysvětlující každý řádek.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define the output directory (change as needed)
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // -------- Planet barcode ----------
        var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string planetPath = Path.Combine(outputDir, "PostalPlanetBarHeightNone.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Planet barcode saved to: {planetPath}");

        // -------- RM4SCC barcode ----------
        var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string rm4sccPath = Path.Combine(outputDir, "PostalRM4SCCBarHeightNone.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);
        Console.WriteLine($"RM4SCC barcode saved to: {rm4sccPath}");
    }
}
```

Po spuštění program vytvoří složku `Barcodes` vedle spustitelného souboru a umístí do ní oba PNG soubory. Otevřete je libovolným prohlížečem obrázků a ověřte výstup.

## Závěr

Nyní máte **barcode generator C#** řešení, které dokáže **vytvořit Planet čárový kód**, nastavit X‑dimenzi pro optimální tisk a vygenerovat odpovídající RM4SCC čárový kód – vše během několika řádků kódu. Přístup funguje s .NET 6+, vyžaduje pouze NuGet balíček Aspose.BarCode a lze jej rozšířit na další symbologie jako Code128, QR nebo DataMatrix změnou hodnoty `EncodeTypes`.

### Co dál?

* Experimentujte s různými hodnotami `XDimension.Pixels`, aby odpovídaly DPI vaší tiskárny.  
* Generujte čárové kódy v jiných formátech (PDF, SVG) změnou enumu `BarCodeImageFormat`.  
* Spojte oba PNG soubory do jednoho štítku pomocí grafické knihovny jako **SkiaSharp**.  
* Prozkoumejte kompletní Aspose.BarCode API pro pokročilé funkce, jako je validace kontrolního součtu nebo vlastní písma.

Neváhejte kód přizpůsobit pro hromadné zpracování nebo jej integrovat do ASP.NET Core webové služby, která na vyžádání vrací obrázky čárových kódů. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vašich projektech.

- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [How to Save PNG using DataMatrix C40 with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [barcode generator tutorial c# – Customize Code 16K Barcode Aspect Ratios with Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
---
category: general
date: 2026-10-02
description: Vytvořte obrázek čárového kódu v C# pomocí generátoru čárových kódů,
  kontrolujte velikost pixelu čárového kódu a upravte výšku čárového kódu pro vlastní
  rozměry.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- barcode pixel size
- adjust barcode height
- custom barcode dimensions
language: cs
lastmod: 2026-10-02
og_description: Vytvořte obrázek čárového kódu v C# pomocí generátoru čárových kódů.
  Naučte se nastavit velikost pixelu čárového kódu, upravit výšku čárového kódu a
  definovat vlastní rozměry čárového kódu.
og_image_alt: Sample DataBar Omnidirectional barcode saved at 30 px height and 60 px
  height
og_title: Vytvořte obrázek čárového kódu v C# – průvodce generátorem čárových kódů
  a vlastními rozměry
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create barcode image in C# using a barcode generator, control barcode
    pixel size and adjust barcode height for custom barcode dimensions.
  headline: How to create barcode image in C# with a barcode generator
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: Jak vytvořit obrázek čárového kódu v C# pomocí generátoru čárových kódů
url: /cs/python-java/general/how-to-create-barcode-image-in-c-with-a-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit obrázek čárového kódu v C# pomocí generátoru čárových kódů

Pokud potřebujete **vytvořit obrázek čárového kódu** soubory programově, tento průvodce vám ukáže kompletní, připravené řešení v C#. Pomocí generátoru čárových kódů můžete řídit **velikost pixelu čárového kódu**, **upravit výšku čárového kódu** a definovat **vlastní rozměry čárového kódu** bez opuštění IDE.

Naučíte se, jak vygenerovat dva PNG soubory — jeden s výškou čáry 30 px a druhý s 60 px — při zachování konstantní šířky modulu. Kroky fungují s libovolným typem čárového kódu podporovaným knihovnou, takže je můžete přizpůsobit QR kódům, Code 128 nebo jiným symbologiím.

## Co budete potřebovat

- .NET 6.0 nebo novější (kód také kompiluje s .NET Framework 4.8)
- Odkaz na knihovnu čárových kódů (např. Aspose.BarCode pro .NET nebo jakoukoliv kompatibilní třídu `BarcodeGenerator`)
- Základní znalost C#
- Oprávnění k zápisu do složky, kam budou PNG soubory uloženy

## Krok 1: Inicializujte generátor čárových kódů pro **vytvoření obrázku čárového kódu**

Nejprve importujte požadované jmenné prostory a vytvořte instanci `BarcodeGenerator`. Konstruktor přijímá typ čárového kódu (`EncodeTypes.DatabarOmniDirectional`) a datový řetězec, který chcete zakódovat.

```csharp
using Aspose.BarCode.Generation;   // or the namespace of your barcode library
using Aspose.BarCode;               // for BarCodeImageFormat
using System.IO;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator to create barcode image
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Vytvoření generátoru je základem pro jakýkoli **barcode generator c#** workflow. Alokuje interní kreslicí plátno a připraví data pro vykreslení.

## Krok 2: Definujte **velikost pixelu čárového kódu** a počáteční výšku čáry

Vizální kvalita výsledného obrázku závisí na dvou parametrech:

| Parametr | Význam |
|----------|--------|
| `XDimension.Pixels` | Šířka jednoho modulu (nejmenší černý/bílý prvek). |
| `BarHeight.Pixels` | Výška čar pro aktuální obrázek. |

```csharp
        // Step 2: Set common visual parameters – module size and initial bar height
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // barcode pixel size (module width)
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first image height in pixels
```

Udržení **velikosti pixelu čárového kódu** konstantní při změně výšky vám umožní vytvořit **vlastní rozměry čárového kódu**, které odpovídají směrnicím značky nebo požadavkům na skenování.

## Krok 3: Uložte první PNG soubor (výška 30 px)

Nyní zapište obrázek na disk. Metoda `Save` přijímá cestu k souboru a požadovaný formát obrázku.

```csharp
        // Step 3: Save the first barcode image (30 px height)
        string outputFolder = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputFolder); // ensure the folder exists

        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);
```

Výsledný soubor je **obrázek čárového kódu** s výškou čáry 30 px a šířkou modulu 2 px, ideální pro kompaktní štítky.

## Krok 4: **Upravit výšku čárového kódu** pro větší verzi

Pro vygenerování druhého obrázku s jinou vizuální velikostí stačí změnit pouze vlastnost `BarHeight.Pixels`. To ukazuje, jak snadné je **upravit výšku čárového kódu** bez opětovného vytvoření generátoru.

```csharp
        // Step 4: Change the bar height to 60 px for a larger barcode
        barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

Změna výšky při zachování **velikosti pixelu čárového kódu** zajišťuje, že čáry zůstávají ostré a celkový poměr stran zůstává konzistentní.

## Krok 5: Uložte druhý PNG soubor (výška 60 px)

Nakonec uložte větší verzi.

```csharp
        // Step 5: Save the second barcode image (60 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);
    }
}
```

Nyní máte uloženy dva **vlastní rozměry čárového kódu** vedle sebe:

- `DatabarBarHeight30Pixels.png` – výška čáry 30 px
- `DatabarBarHeight60Pixels.png` – výška čáry 60 px

Oba obrázky mají stejnou **velikost pixelu čárového kódu** 2 px, což zaručuje vizuální konzistenci napříč různými velikostmi.

## Proč jsou tato nastavení důležitá

- **Velikost pixelu čárového kódu** (`XDimension`) ovlivňuje čitelnost skeneru. Šířka 2 px je běžná výchozí hodnota, která vyvažuje velikost souboru a spolehlivost skenování.
- **Výška čáry** určuje, jak vysoký čárový kód bude na štítku. Některé maloobchodní skenery vyžadují minimální výšku; jiné umožňují vyšší čáry z estetických důvodů.
- Udržení instance generátoru při pouhém ladění `BarHeight` snižuje alokace paměti a zrychluje dávkové zpracování.

## Okrajové případy a tipy pro nejlepší praxi

| Situace | Doporučený přístup |
|---------|--------------------|
| **Různé formáty obrázků** (JPEG, BMP) | Změňte `BarCodeImageFormat.Jpeg` nebo `.Bmp` v volání `Save`. JPEG je menší, ale může zavést kompresní artefakty. |
| **Výstup ve vysokém rozlišení** (např. 300 DPI) | Zvyšte `XDimension.Pixels` úměrně (např. 4 px) a upravte `BarHeight.Pixels` pro zachování stejné fyzické velikosti. |
| **Dynamické datové řetězce** | Zabalte vytvoření generátoru do metody, která přijímá datový řetězec jako parametr, a poté znovu použijte stejnou instanci `barcode` pro více uložení. |
| **Bezpečná dávková generace v několika vláknech** | Vytvořte samostatný `BarcodeGenerator` pro každé vlákno nebo použijte pool lokální pro vlákno, aby se předešlo závodním podmínkám. |
| **Chyby oprávnění souborového systému** | Ověřte, že `outputFolder` existuje a proces má právo zápisu; ošetřete `IOException` elegantně. |

## Kompletní výpis zdrojového kódu

Níže je kompletní, samostatný program, který můžete zkopírovat, vložit a spustit.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.IO;

class Program
{
    static void Main()
    {
        // Create a barcode generator – this is the core of the create barcode image workflow
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // Define barcode pixel size (module width) and initial height
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // barcode pixel size
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first image height

        // Prepare output folder
        string outputFolder = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputFolder);

        // Save first image (30 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);

        // Adjust height for the second image
        barcode.Parameters.Barcode.BarHeight.Pixels = 60; // adjust barcode height

        // Save second image (60 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);
    }
}
```

### Očekávaný výstup

Po spuštění programu složka `YOUR_DIRECTORY` obsahuje dva PNG soubory:

- **DatabarBarHeight30Pixels.png** – kompaktní čárový kód vhodný pro malé štítky.
- **DatabarBarHeight60Pixels.png** – větší verze ideální pro aplikace s vysokou viditelností.

Oba soubory lze otevřít v libovolném prohlížeči obrázků, vytisknout nebo vložit do PDF.

## Závěr

Nyní víte, jak **vytvořit obrázek čárového kódu** soubory v C# pomocí **barcode generator c#**, řídit **velikost pixelu čárového kódu**, **upravit výšku čárového kódu** a vytvořit **vlastní rozměry čárového kódu**, které splňují konkrétní požadavky na skenování nebo značku. Příklad ukazuje čistý, opakovatelný vzor, který lze škálovat na dávkové zpracování nebo různé symbologie.

### Co zkusit dál

- Vyměňte `EncodeTypes.DatabarOmniDirectional` za jiné typy, jako jsou `EncodeTypes.Code128` nebo `EncodeTypes.QR`.
- Použijte barvy popředí/pozadí pomocí `barcode.Parameters.Barcode.ForeColor` a `BackColor`.
- Generujte výstupy SVG nebo PDF pro vektorové tisknutí.
- Kombinujte více čárových kódů do jednoho obrázku pomocí `Graphics` pro kompozitní štítky.

Neváhejte experimentovat s parametry a integrovat tento vzor do vašeho inventáře, ticketingu nebo jakéhokoli systému, který potřebuje programové vytváření čárových kódů. Šťastné kódování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vytvořit obrázek čárového kódu v C# s nastavitelnou výškou](/barcode/english/python-java/general/how-to-create-barcode-image-in-c-with-adjustable-height/)
- [Jak vygenerovat sadu čárových kódů s vlastní velikostí a uložit obrázek v C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [Vytvořit obrázek čárového kódu v C# s příkladem generátoru čárových kódů](/barcode/english/python-java/general/create-barcode-image-c-with-barcode-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
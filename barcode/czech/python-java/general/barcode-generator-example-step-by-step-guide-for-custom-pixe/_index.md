---
category: general
date: 2026-08-12
description: Příklad generátoru čárových kódů, který ukazuje, jak generovat čárový
  kód s přesnou velikostí pixelu. Naučte se nastavit šířku modulu, výšku čáry a vytvořit
  Planet čárové kódy.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to generate barcode
- barcode pixel size
- generate planet barcode
- barcode height setting
language: cs
lastmod: 2026-08-12
og_description: Ukázka generátoru čárových kódů demonstruje, jak vytvořit čárový kód
  s přesnými rozměry v pixelech. Postupujte podle tohoto návodu, abyste ovládali šířku
  modulu a výšku čáry pro kódy Planet a RM4SCC.
og_image_alt: Screenshot of a barcode generator example showing a Planet barcode with
  custom pixel size
og_title: příklad generátoru čárových kódů – přizpůsobení velikosti pixelu v C#
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: barcode generator example that shows how to generate barcode with precise
    pixel size. Learn to set module width, bar height and create Planet barcodes.
  headline: barcode generator example – step‑by‑step guide for custom pixel sizes
  type: TechArticle
- description: barcode generator example that shows how to generate barcode with precise
    pixel size. Learn to set module width, bar height and create Planet barcodes.
  name: barcode generator example – step‑by‑step guide for custom pixel sizes
  steps:
  - name: Install the Aspose.BarCode package
    text: 'Open a terminal in your project folder and run:'
  - name: Add the necessary `using` directives
    text: '```csharp using Aspose.BarCode.Generation; using Aspose.BarCode.BarCodeImageFormat;
      ```'
  - name: – generate a Planet barcode with automatically calculated height
    text: '```csharp // Step 1: Generate a Planet barcode with automatically calculated
      height BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet,
      "123456");'
  - name: – generate a Planet barcode with an explicit 100‑pixel height
    text: '```csharp // Step 2: Generate a Planet barcode with an explicit 100‑pixel
      height BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet,
      "123456");'
  - name: – generate an RM4SCC barcode with the same explicit height
    text: '```csharp // Step 3: Generate an RM4SCC barcode with the same explicit
      height BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC,
      "123456");'
  - name: What is **barcode pixel size**?
    text: '*Pixel size* refers to the physical number of screen or printer pixels
      that represent a single module (`XDimension`). A larger pixel size yields a
      bigger barcode, which can be easier for low‑resolution scanners but consumes
      more label real‑estate.'
  - name: How does `BarHeight` affect readability?
    text: The `BarHeight` property controls the vertical length of the bars. Standards
      for most 1‑D barcodes (including Planet and RM4SCC) recommend a minimum height
      of 10 mm when printed at 300 dpi, which translates to roughly 118 pixels. Setting
      a height below that can cause read errors, especially on mobil
  - name: When should you let the library calculate height automatically?
    text: If you’re generating barcodes for on‑screen display only, the automatic
      calculation keeps the aspect ratio consistent and reduces the amount of manual
      tweaking needed. For printed labels that must meet strict ISO specifications,
      you should **explicitly set the bar height**.
  - name: Pro tip on performance
    text: When generating thousands of barcodes in a batch job, reuse a single `BarcodeGenerator`
      instance and only change the `CodeText` and size parameters between saves. This
      avoids repeated allocation of internal rendering objects and can cut execution
      time by up to 30 %.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Příklad generátoru čárových kódů – krok za krokem průvodce pro vlastní velikosti
  pixelů
url: /cs/python-java/general/barcode-generator-example-step-by-step-guide-for-custom-pixe/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# příklad generátoru čárových kódů – krok za krokem průvodce pro vlastní velikosti pixelů

Pokud potřebujete **příklad generátoru čárových kódů**, který vám umožní ovládat každý pixel, tento průvodce vám přesně ukáže, jak na to. Naučíte se nastavit šířku modulu, definovat pevnou výšku pruhu a generovat jak čárové kódy Planet, tak RM4SCC s předvídatelnými rozměry.

Většina vývojářů má potíže s tím, „jak generovat obrázky čárových kódů“, které vypadají stejně na každé obrazovce nebo tiskárně. Níže uvedené úryvky kódu tento problém řeší tím, že odhalí parametry na úrovni pixelů knihovny Aspose.BarCode pro .NET, takže můžete vytvářet konzistentní výstup bez hádání.

## Co se naučíte

* Jak nainstalovat požadovaný NuGet balíček.  
* Jak vygenerovat Planet čárový kód s automaticky vypočtenou výškou.  
* Jak vygenerovat Planet čárový kód s explicitní výškou 100 pixelů.  
* Jak vygenerovat RM4SCC čárový kód pomocí stejné explicitní výšky.  
* Proč **velikost pixelu čárového kódu** ovlivňuje spolehlivost skenování.  
* Tipy pro řešení běžných problémů při generování obrázků Planet čárových kódů.

Stačí vám .NET 6 nebo novější, základní vývojové prostředí C# a internetové připojení pro stažení NuGet balíčku.

---

## barcode generator example – nastavení vývojového prostředí

Než napíšete jakýkoli kód, ujistěte se, že knihovna Aspose.BarCode je ve vašem projektu dostupná.

### Instalace balíčku Aspose.BarCode

Otevřete terminál ve složce projektu a spusťte:

```bash
dotnet add package Aspose.BarCode
```

Příkaz přidá nejnovější stabilní verzi **Aspose.BarCode** do vašeho `csproj`. Po dokončení obnovení můžete začít používat třídu `BarcodeGenerator`.

> **Pro tip:** Cílová platforma .NET 6 nebo .NET 7 vám poskytne nejnovější vylepšení výkonu a výchozí zpracování UTF‑8.

### Přidejte potřebné `using` direktivy

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;
```

Tyto jmenné prostory zpřístupňují třídu `BarcodeGenerator` a výčet `BarCodeImageFormat`, které budou později v tutoriálu použity.

---

## Jak generovat čárový kód s vlastní velikostí pixelů

Následující tři kroky ukazují kompletní **příklad generátoru čárových kódů**. Každý krok navazuje na předchozí, takže můžete celý blok zkopírovat do konzolové aplikace a spustit beze změn.

### Krok 1 – vygenerovat Planet čárový kód s automaticky vypočtenou výškou

```csharp
// Step 1: Generate a Planet barcode with automatically calculated height
BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set module width (x‑dimension) to 4 pixels
planetAuto.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG
planetAuto.Save("PlanetAuto.png", BarCodeImageFormat.Png);
```

**Proč to funguje:**  
*Vlastnost `XDimension` určuje šířku jednoho modulu čárového kódu (nejmenšího černého nebo bílého prvku). Když vynecháte `BarHeight`, knihovna vypočítá výšku, která zachová standardní poměr stran pro kódy Planet.*

**Očekávaný výstup:** PNG soubor pojmenovaný `PlanetAuto.png` obsahující čistý Planet čárový kód. Jeho výška se přizpůsobí šířce 4‑pixelového modulu, typicky kolem 60 pixelů pro šestimístný payload.

### Krok 2 – vygenerovat Planet čárový kód s explicitní výškou 100 pixelů

```csharp
// Step 2: Generate a Planet barcode with an explicit 100‑pixel height
BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same module width
planetFixed.Parameters.Barcode.XDimension.Pixels = 4;

// Force the bar height to 100 pixels
planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the image
planetFixed.Save("PlanetHeight100.png", BarCodeImageFormat.Png);
```

**Proč byste to mohli potřebovat:**  
Některé skenovací zařízení vyžaduje minimální výšku pruhu pro spolehlivé rozpoznání. Nastavením `BarHeight.Pixels` zajistíte, že každý vygenerovaný obrázek splní tento požadavek, bez ohledu na délku kódovaných dat.

**Očekávaný výstup:** `PlanetHeight100.png` zobrazuje stejná data jako předtím, ale pruhy mají přesně 100 pixelů na výšku, což vám dává plnou kontrolu nad vizuální velikostí.

### Krok 3 – vygenerovat RM4SCC čárový kód se stejnou explicitní výškou

```csharp
// Step 3: Generate an RM4SCC barcode with the same explicit height
BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Use the same module width for consistency
rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;

// Apply the 100‑pixel bar height
rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the image
rm4sccFixed.Save("RM4SCCHeight100.png", BarCodeImageFormat.Png);
```

**Proč je to důležité:**  
`EncodeTypes.RM4SCC` je vrstvený lineární čárový kód používaný v logistice. Zarovnání výšky pruhu s Planet čárovým kódem usnadňuje dávkové zpracování, když se na stejné etiketě objeví oba symbology.

**Očekávaný výstup:** `RM4SCCHeight100.png` zobrazuje perfektně dimenzovaný RM4SCC čárový kód, který odpovídá výšce 100 pixelů nastavené pro Planet kód.

> **Ověření výsledku:** Otevřete každý PNG v prohlížeči obrázků a potvrďte, že černé pruhy jsou přesně 4 pixely široké a tam, kde jste zadali, 100 pixelů vysoké. Můžete také soubory nahrát do aplikace pro skenování čárových kódů a ověřit, že dekódují „123456“.

---

## Porozumění velikosti pixelu čárového kódu a výšce pruhu

### Co je **velikost pixelu čárového kódu**?

*Velikost pixelu* označuje fyzický počet pixelů na obrazovce nebo tiskárně, které představují jeden modul (`XDimension`). Větší velikost pixelu vede k většímu čárovému kódu, který může být snazší pro nízkorozlišovací skenery, ale zabírá více místa na štítku.

### Jak `BarHeight` ovlivňuje čitelnost?

Vlastnost `BarHeight` řídí vertikální délku pruhů. Standardy pro většinu 1‑D čárových kódů (včetně Planet a RM4SCC) doporučují minimální výšku 10 mm při tisku 300 dpi, což odpovídá přibližně 118 pixelům. Nastavení výšky pod tuto hodnotu může způsobit chyby čtení, zejména u mobilních kamer.

### Kdy nechat knihovnu automaticky vypočítat výšku?

Pokud generujete čárové kódy pouze pro zobrazení na obrazovce, automatický výpočet udrží poměr stran konzistentní a sníží množství ručního ladění. Pro tištěné štítky, které musí splňovat přísné ISO specifikace, byste měli **explicitně nastavit výšku pruhu**.

---

## Běžné úskalí a osvědčené postupy při generování Planet čárového kódu

| Problém | Proč k tomu dochází | Řešení |
|---------|----------------------|--------|
| Pruhy se jeví příliš tenké nebo tlusté | `XDimension` zůstala na výchozí hodnotě (1 pixel) na displejích s vysokým rozlišením | Nastavte `XDimension.Pixels` alespoň na 3‑4 pro vizuální jasnost |
| Skenner nedokáže kód přečíst | `BarHeight` je příliš malá pro ohniskovou vzdálenost skeneru | Použijte `BarHeight.Pixels` ≥ 100 pro většinu mobilních skenerů |
| Obrázek je po škálování rozmazaný | Ukládání jako JPEG zavádí kompresní artefakty | Ukládejte jako PNG (`BarCodeImageFormat.Png`) pro bezztrátový výstup |
| Neočekávaný typ čárového kódu | Nesprávná hodnota v enumu `EncodeTypes` | Zkontrolujte, že používáte `EncodeTypes.Planet` pro symbologii Planet |

### Pro tip na výkon

Při generování tisíců čárových kódů v dávkovém úkolu opakovaně používejte jedinou instanci `BarcodeGenerator` a mezi ukládáními měňte pouze `CodeText` a parametry velikosti. Tím se vyhnete opakovanému alokování interních renderovacích objektů a můžete zkrátit dobu běhu až o 30 %.

---

## Kompletní funkční příklad – spojte vše dohromady

Vytvořte nový konzolový projekt (`dotnet new console -n BarcodeDemo`) a nahraďte obsah souboru `Program.cs` následujícím kódem:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Directory where PNG files will be saved
            string outputDir = Environment.CurrentDirectory;

            // ---------- Planet barcode – automatic height ----------
            var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
            planetAuto.Save($"{outputDir}/PlanetAuto.png", BarCodeImageFormat.Png);
            Console.WriteLine("PlanetAuto.png generated.");

            // ---------- Planet barcode – fixed 100‑pixel height ----------
            var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
            planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            planetFixed.Save($"{outputDir}/PlanetHeight100.png", BarCodeImageFormat.Png);
            Console.WriteLine("PlanetHeight100.png generated.");

            // ---------- RM4SCC barcode – same fixed height ----------
            var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            rm4sccFixed.Save($"{outputDir}/RM4SCCHeight100.png", BarCodeImageFormat.Png);
            Console.WriteLine("RM4SCCHeight100.png generated.");

            Console.WriteLine("All barcodes created successfully.");
        }
    }
}
```

Spusťte program pomocí `dotnet run`. Po dokončení najdete ve složce projektu tři PNG soubory, z nichž každý ilustruje jiný scénář **příkladu generátoru čárových kódů**.

---

## Další kroky a související témata

* **Jak generovat čárový kód v jiných formátech** – prozkoumejte `EncodeTypes.Code128`, `EncodeTypes.QR` a `EncodeTypes.DataMatrix` pro potřeby 2‑D.  
* **Vkládání čárových kódů do PDF** – kombinujte Aspose.BarCode s Aspose.PDF pro umístění čárových kódů přímo na šablony faktur.  
* **Dynamická velikost čárového kódu na základě vstupu uživatele** – vypočítejte  

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vlastních projektech.

- [How to generate barcode java: Create an Exact Barcode Image](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)
- [How to Generate Barcode in Java Create and Set Size for Whole Picture](/barcode/english/java/barcode-basics/creating-setting-size-whole-picture-barcode/)
- [How to create code128 barcode Java and set bar height](/barcode/english/java/barcode-configuration/setting-bars-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
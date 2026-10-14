---
category: general
date: 2026-09-29
description: Vytvořte planetární čárový kód v C# s plnými i prázdnými pruhy – krok
  za krokem průvodce s využitím Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode XDimension
- filled bars
- empty bars
- Aspose.Barcode C#
language: cs
lastmod: 2026-09-29
og_description: Rychle vytvořte planetární čárový kód v C#. Naučte se, jak vykreslovat
  vyplněné pruhy, přepínat na prázdné pruhy a upravovat X‑rozměr pomocí Aspose.Barcode.
og_image_alt: 'Screenshot of two Planet barcodes: one with filled bars, one with empty
  bars'
og_title: Vytvořte planetární čárový kód s vyplněnými a prázdnými pruhy – C# tutoriál
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  headline: How to create planet barcode with filled and empty bars
  type: TechArticle
- description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  name: How to create planet barcode with filled and empty bars
  steps:
  - name: Changing the bar width
    text: If your label printer expects a different bar width, modify the `XDimension.Pixels`
      value. For high‑resolution printers, a value of **2** or **3** pixels may be
      preferable; for low‑resolution printers, **5** or **6** pixels can improve scan
      reliability.
  - name: Using a different image format
    text: Aspose.Barcode supports PNG, JPEG, BMP, GIF, and TIFF. Swap `BarCodeImageFormat.Png`
      with another enum value to match your downstream workflow.
  - name: Generating multiple barcodes in a loop
    text: When you need a batch of Planet barcodes (e.g., for a mailing list), wrap
      the generator logic in a `foreach` loop and change the data string each iteration.
  - name: Handling invalid input
    text: The Planet symbology accepts only numeric strings of **5‑8** digits. Supplying
      an invalid value throws an `ArgumentException`. Guard against this with a simple
      validation method.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Jak vytvořit planetární čárový kód s vyplněnými a prázdnými pruhy
url: /cs/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit planet barcode s vyplněnými a prázdnými pruhy

Pokud potřebujete **vytvořit planet barcode** obrázky v C#, tento návod vám přesně ukáže, jak vygenerovat jak verze s vyplněnými pruhy, tak s prázdnými pruhy. Uvidíte, jak nastavit šířku pruhu (X‑dimension), přepnout vlastnost `FilledBars` a uložit výsledky jako PNG soubory — vše pomocí knihovny Aspose.Barcode.

Generování poštovních čárových kódů je běžnou požadavkem pro přepravní systémy, aplikace pro poštovní seznamy a logistické dashboardy. Na konci tohoto tutoriálu budete mít dva připravené PNG soubory, které můžete vložit do reportů, e‑mailů nebo výtisků.

## Požadavky

| Požadavek | Proč je důležitý |
|-------------|----------------|
| .NET 6.0 nebo novější | Poskytuje runtime pro C# příklad. |
| Visual Studio 2022 (nebo jakékoli C# IDE) | Umožňuje kompilovat a spustit kód. |
| **Aspose.Barcode for .NET** NuGet balíček | Poskytuje třídu `BarcodeGenerator` a `EncodeTypes.Planet`. Nainstalujte jej pomocí `dotnet add package Aspose.Barcode`. |
| Oprávnění k zápisu do složky na disku | Metoda `Save` zapisuje PNG soubory na zadanou cestu. |

## Krok 1: Nastavte projekt a importujte jmenné prostory

Vytvořte nový konzolový projekt (nebo přidejte kód do existujícího) a odkažte na jmenný prostor Aspose.Barcode.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;
```

Tyto `using` direktivy vám poskytují přístup k `BarcodeGenerator`, `EncodeTypes` a výčtům formátů obrázků potřebných pro tutoriál.

## Krok 2: Vytvořte Planet čárový kód s výchozími (vyplněnými) pruhy

První čárový kód používá výchozí vykreslování knihovny, které vyplňuje pruhy.

```csharp
// Initialise a generator for the Planet (postal) barcode with sample data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Optional: adjust the bar width (X dimension) to 4 pixels for clearer printing.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image with filled bars.
string filledPath = @"C:\Barcodes\PlanetFilledBars.png";
barcodeGenerator.Save(filledPath, BarCodeImageFormat.Png);

Console.WriteLine($"Filled Planet barcode saved to: {filledPath}");
```

**Proč to funguje:**  
`EncodeTypes.Planet` říká Aspose.Barcode, aby použil symbologii **Planet**, což je poštovní čárový kód používaný United States Postal Service. Vlastnost `XDimension` řídí šířku každého pruhu; nastavení na 4 pixely vytvoří čárový kód, který se dobře tiskne na standardních štítcových tiskárnách. Ve výchozím nastavení je `FilledBars` `true`, takže pruhy jsou plné.

## Krok 3: Vytvořte Planet čárový kód s prázdnými pruhy

Pro vygenerování stejných dat s *prázdnými* pruhy stačí přepnout příznak `FilledBars`, zatímco ostatní nastavení zůstane stejné.

```csharp
// Re‑use the same variable for clarity.
barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for visual consistency.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Render empty bars instead of filled ones.
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the image with empty bars.
string emptyPath = @"C:\Barcodes\PlanetEmptyBars.png";
barcodeGenerator.Save(emptyPath, BarCodeImageFormat.Png);

Console.WriteLine($"Empty Planet barcode saved to: {emptyPath}");
```

**Proč je to důležité:**  
Některé poštovní systémy vyžadují styl **empty‑bars** pro zlepšení čitelnosti, když je čárový kód tištěn na tmavém pozadí nebo je použita kontrastní barevná schéma. Nastavením `FilledBars = false` generátor vykreslí pouze obrysy pruhů a vnitřek zůstane průhledný.

## Očekávaný výstup

Po spuštění programu složka `C:\Barcodes` (nebo vámi zvolená cesta) obsahuje dva PNG soubory:

| Soubor | Vizuální popis |
|------|---------------------|
| `PlanetFilledBars.png` | Pruhy jsou pevné černé obdélníky na bílém pozadí. |
| `PlanetEmptyBars.png`  | Pruhy jsou černé obrysy; vnitřek každého pruhu je průhledný (zobrazuje pozadí). |

Oba obrázky kódují stejný číselný řetězec `"123456"` a mají šířku pruhu 4 pixely, což zajišťuje, že vypadají konzistentně, až na styl výplně.

## Běžné varianty a okrajové případy

### Změna šířky pruhu

Pokud vaše štítková tiskárna očekává jinou šířku pruhu, upravte hodnotu `XDimension.Pixels`. Pro vysoce rozlišené tiskárny může být vhodná hodnota **2** nebo **3** pixely; pro nízko rozlišené tiskárny mohou **5** nebo **6** pixelů zlepšit spolehlivost skenování.

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 5; // example for coarse printers
```

### Použití jiného formátu obrázku

Aspose.Barcode podporuje PNG, JPEG, BMP, GIF a TIFF. Vyměňte `BarCodeImageFormat.Png` za jinou hodnotu výčtu, aby odpovídala vašemu následnému workflow.

```csharp
barcodeGenerator.Save("Planet.tiff", BarCodeImageFormat.Tiff);
```

### Generování více čárových kódů ve smyčce

Když potřebujete dávku Planet čárových kódů (např. pro poštovní seznam), zabalte logiku generátoru do `foreach` smyčky a měňte datový řetězec v každé iteraci.

```csharp
string[] postalCodes = { "123456", "654321", "112233" };
int index = 1;
foreach (var code in postalCodes)
{
    var gen = new BarcodeGenerator(EncodeTypes.Planet, code);
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    gen.Save($@"C:\Barcodes\Planet_{index}_filled.png", BarCodeImageFormat.Png);
    gen.Parameters.Barcode.FilledBars = false;
    gen.Save($@"C:\Barcodes\Planet_{index}_empty.png", BarCodeImageFormat.Png);
    index++;
}
```

### Zpracování neplatného vstupu

Symbologie Planet přijímá pouze číselné řetězce o **5‑8** číslicích. Poskytnutí neplatné hodnoty vyvolá `ArgumentException`. Ochráníte se před tím jednoduchou validační metodou.

```csharp
bool IsValidPlanet(string value) => System.Text.RegularExpressions.Regex.IsMatch(value, @"^\d{5,8}$");

string data = "ABC123";
if (!IsValidPlanet(data))
{
    Console.WriteLine("Invalid Planet data – must be 5 to 8 digits.");
    return;
}
```

## Tip: Ověřte čárový kód pomocí emulátoru skeneru

Aspose.Barcode obsahuje třídu `BarcodeReader`, kterou můžete použít k potvrzení, že vygenerovaný obrázek dekóduje zpět na původní data.

```csharp
using Aspose.Barcode.Reader;

// Verify filled barcode
using (BarCodeReader reader = new BarCodeReader(filledPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from filled image: {reader.GetCodeText()}");
}

// Verify empty barcode
using (BarCodeReader reader = new BarCodeReader(emptyPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from empty image: {reader.GetCodeText()}");
}
```

Pokud výstup ukazuje `"123456"` pro oba soubory, čárový kód byl vygenerován správně.

## Závěr

Nyní víte, jak **vytvořit planet barcode** obrázky v C# s oběma styly vyplněných i prázdných pruhů, ovládat **Planet barcode XDimension** a uložit výsledky ve formátu PNG pomocí knihovny **Aspose.Barcode**. Přizpůsobte šířku pruhu, změňte formát obrázku nebo provádějte smyčku přes kolekci hodnot, aby vyhovovaly jakémukoli workflow poštovních kódů.

Dále můžete prozkoumat:

* **Přidání lidsky čitelného textu** pod čárový kód (`barcodeGenerator.Parameters.Caption.Show = true`).
* **Vkládání čárových kódů do PDF dokumentů** pomocí Aspose.PDF.
* **Generování dalších poštovních symbologií** jako **USPS POSTNET** nebo **Intelligent Mail**.

Neváhejte experimentovat s parametry a integrovat kód do vašeho přepravního nebo poštovního systému. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto návodu. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Create Planet Barcode in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Create planet barcode in C# – complete programming guide](/barcode/english/python-java/general/create-planet-barcode-in-c-complete-programming-guide/)
- [Barcode generator C# – create Planet barcode and RM4SCC example](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
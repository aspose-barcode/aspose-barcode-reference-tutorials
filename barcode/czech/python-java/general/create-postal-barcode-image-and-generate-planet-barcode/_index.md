---
category: general
date: 2026-11-20
description: Rychle vytvořte obrázek poštovního čárového kódu v C#. Naučte se generovat
  planetové čárové kódy a RM4SCC čárové kódy s přizpůsobitelnými styly čar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- postal barcode C#
- Aspose.BarCode example
- barcode image generation
language: cs
lastmod: 2026-11-20
og_description: Vytvořte obrázek poštovního čárového kódu v C# s Aspose.BarCode. Tento
  tutoriál ukazuje, jak generovat planetární čárový kód, přizpůsobit styly čar a vytvořit
  obrázky RM4SCC.
og_image_alt: Create postal barcode image example showing filled and empty bars
og_title: Vytvořte obrázek poštovního čárového kódu v C# – průvodce krok za krokem
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Create postal barcode image in C# quickly. Learn how to generate planet
    barcode and RM4SCC barcodes with customizable bar styles.
  headline: Create postal barcode image and generate planet barcode
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Vytvořte obrázek poštovního čárového kódu a vygenerujte planetární čárový kód
url: /cs/python-java/general/create-postal-barcode-image-and-generate-planet-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření obrázku poštovního čárového kódu a generování planet barcode

Vytvořte obrázek poštovního čárového kódu v C# pomocí knihovny Aspose.BarCode. Pokud potřebujete generovat planet barcode nebo čárové kódy RM4SCC pro poštovní aplikace, tento tutoriál poskytuje kompletní, připravené řešení.

Generování čárových kódů pro poštovní služby často vyžaduje přesné rozměry a možnost přepínání mezi vyplněnými a prázdnými pruhy. Tento průvodce vás provede nastavením výstupní složky, vytvořením jak vyplněných, tak prázdných Planet čárových kódů a vytvořením RM4SCC čárového kódu se stejným vizuálním nastavením. Na konci budete mít čtyři soubory PNG, které můžete použít přímo ve svém poštovním workflow.

## Požadavky

Než začnete, ujistěte se, že máte:

* .NET 6.0 nebo novější nainstalovaný  
* Visual Studio 2022 (nebo jakékoli jiné C# IDE, které preferujete)  
* NuGet balíček **Aspose.BarCode** (`Install-Package Aspose.BarCode`)  

Žádná další konfigurace není vyžadována; kód používá pouze výchozí font a PNG enkodér.

## Přehled vytvoření obrázku poštovního čárového kódu

Jádrem procesu je třída `BarcodeGenerator`. Přijímá hodnotu `EncodeTypes`, která určuje symbologii čárového kódu (například `EncodeTypes.Planet` pro Planet čárový kód). Po nastavení generátoru zavoláte `Save`, aby se soubor obrázku zapsal.

![Create postal barcode image example](/images/postal_barcode_example.png)

*Alt text: Příklad vytvoření obrázku poštovního čárového kódu zobrazujícího vyplněné a prázdné pruhy.*

## Krok 1: Nastavení výstupní složky

Nejprve definujte složku, kam budou soubory PNG uloženy. Použití absolutní nebo relativní cesty funguje stejným způsobem; stačí zajistit, aby složka existovala, nebo nechte kód, aby ji vytvořil.

```csharp
using System.IO;
using Aspose.BarCode.Generation;

// Define the output folder (change to your own path)
string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
```

Programové vytvoření složky zabraňuje výjimce `DirectoryNotFoundException`, když se tutoriál spustí na novém počítači.

## Krok 2: Generování planet barcode s vyplněnými pruhy

Vyplněný Planet čárový kód je výchozí vizuální styl. Následující kód vytvoří čárový kód, nastaví X‑dimenzi na 4 pixely (běžná velikost pro poštovní aplikace) a uloží obrázek.

```csharp
// Step 2: Generate a Planet barcode with filled bars
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save as PNG
string planetFilledPath = Path.Combine(outputFolder, "PostalPlanetFilledBars.png");
planetFilled.Save(planetFilledPath, BarCodeImageFormat.Png);
```

**Proč to funguje:**  
* `EncodeTypes.Planet` říká generátoru, aby použil symbologii Planet, která je požadována mnoha poštovními službami.  
* `XDimension.Pixels` řídí šířku každého pruhu; 4 px poskytuje jasný, čitelný obrázek bez nadměrné velikosti souboru.  
* Metoda `Save` automaticky vybere PNG enkodér na základě výčtu `BarCodeImageFormat`.

## Krok 3: Generování planet barcode s prázdnými pruhy

Některé poštovní specifikace upřednostňují prázdné (bílé) pruhy na tmavém pozadí. To můžete dosáhnout nastavením `FilledBars` na `false`.

```csharp
// Step 3: Generate a Planet barcode with empty bars
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for consistency
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars – the bars become transparent (empty)
planetEmpty.Parameters.Barcode.FilledBars = false;

// Save the result
string planetEmptyPath = Path.Combine(outputFolder, "PostalPlanetEmptyBars.png");
planetEmpty.Save(planetEmptyPath, BarCodeImageFormat.Png);
```

**Tip:** Když je `FilledBars` nastaveno na `false`, generátor vykreslí pruhy barvou pozadí (standardně bílou) a mezery barvou popředí (černou). Pokud potřebujete jinou barevnou kombinaci, upravte `Parameters.Barcode.ForeColor` a `BackColor`.

## Krok 4: Generování RM4SCC barcode s vyplněnými pruhy

RM4SCC je další poštovní symbologie používaná ve Spojeném království. Kroky tvorby jsou podobné jako u Planet příkladu; mění se pouze hodnota `EncodeTypes`.

```csharp
// Step 4: Generate an RM4SCC barcode with filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Reuse the same X‑dimension for a uniform look
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save the PNG file
string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png");
rm4sccFilled.Save(rm4sccPath, BarCodeImageFormat.Png);
```

**Co očekávat:** Výsledný PNG zobrazuje kompaktní RM4SCC čárový kód, který splňuje britské poštovní směrnice. Velikost obrázku bude podobná jako u Planet čárových kódů, protože X‑dimenze je stejná.

## Krok 5: Ověření vygenerovaných obrázků

Po spuštění programu otevřete čtyři soubory ve složce `Barcodes`. Měli byste vidět:

* `PostalPlanetFilledBars.png` – tmavé pruhy na světlém pozadí  
* `PostalPlanetEmptyBars.png` – světlé pruhy na tmavém pozadí (inverzní)  
* `PostalRM4SCCFilledBars.png` – standardní vzor RM4SCC  

Pokud některý obrázek vypadá poškozeně, zkontrolujte následující:

* **X‑dimenze** – příliš malá (< 2 px) může způsobit rozmazání; příliš velká (> 10 px) může překročit limity velikosti štítku.  
* **Datový řetězec** – hodnota `"123456"` musí splňovat délkové požadavky zvolené symbologie (Planet vyžaduje 6 číslic, RM4SCC také 6 číslic).  
* **Oprávnění složky** – ujistěte se, že aplikace má právo zápisu do výstupního adresáře.

## Běžné varianty a okrajové případy

| Scénář | Úprava |
|----------|------------|
| **Různé data čárového kódu** | Nahraďte `"123456"` libovolným platným číselným řetězcem. Pro Planet musí mít délku přesně 6 číslic; RM4SCC také vyžaduje 6 číslic. |
| **Vlastní barvy** | Nastavte `planetFilled.Parameters.Barcode.ForeColor = System.Drawing.Color.DarkBlue;` a `BackColor = System.Drawing.Color.LightYellow;`. |
| **Vyšší rozlišení** | Zvyšte `XDimension.Pixels` na 6 nebo 8 pro větší výtisky. |
| **Jiné formáty obrázků** | Použijte `BarCodeImageFormat.Jpeg` nebo `BarCodeImageFormat.Bmp` v volání `Save`. |
| **Dávkové generování** | Procházejte kolekci řetězců a volajte stejnou logiku generátoru uvnitř smyčky, přičemž znovu použijete cestu `outputFolder`. |

## Kompletní, spustitelný příklad

Zkopírujte níže uvedený kód do nového C# konzolového projektu. Kompiluje se s .NET 6.0 a automaticky vytvoří všechny čtyři obrázky čárových kódů.



## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, která vám pomohou zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vlastních projektech.

- [Jak vytvořit obrázek poštovního čárového kódu s vlastní výškou v C#](/barcode/english/python-java/general/how-to-create-postal-barcode-image-with-custom-heights-in-c/)
- [Jak vytvořit RM4SCC čárový kód a generovat planet barcode v C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-generate-planet-barcode-in/)
- [Vytvoření obrázku poštovního čárového kódu v C# – krok za krokem](/barcode/english/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
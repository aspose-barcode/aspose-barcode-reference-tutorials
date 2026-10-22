---
category: general
date: 2026-10-21
description: Naučte se, jak v C# pomocí Aspose.BarCode vytvářet obrázky poštovních
  čárových kódů – generovat kódy Planet a RM4SCC, řídit vyplněné čáry a ukládat soubory
  PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode
- generate planet barcode
- how to generate barcode c#
language: cs
lastmod: 2026-10-21
og_description: Vytvořte obrázky poštovních čárových kódů v C# pomocí Aspose.BarCode.
  Tento tutoriál ukazuje, jak generovat čárové kódy Planet a RM4SCC, přepínat vyplněné
  čáry a ukládat soubory PNG.
og_image_alt: Screenshot of a generated Planet postal barcode with filled bars
og_title: Vytvořte obrázky poštovních čárových kódů v C# – průvodce krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Learn how to create postal barcode images in C# with Aspose.BarCode
    – generate Planet and RM4SCC barcodes, control filled bars, and save PNG files.
  headline: How to create postal barcode images in C# using Aspose.BarCode
  type: TechArticle
- description: Learn how to create postal barcode images in C# with Aspose.BarCode
    – generate Planet and RM4SCC barcodes, control filled bars, and save PNG files.
  name: How to create postal barcode images in C# using Aspose.BarCode
  steps:
  - name: 1. Prepare the output folder
    text: The barcode images need a writable directory. The code creates the folder
      if it does not exist, preventing a runtime `DirectoryNotFoundException`.
  - name: 2. Generate a Planet barcode with filled bars
    text: Planet barcodes are used by many postal services for domestic mail. The
      default `FilledBars` setting renders solid bars, which is the most common visual
      style.
  - name: 3. Generate a Planet barcode with empty bars
    text: Some postal specifications require **empty** (hollow) bars. You can toggle
      this behavior via the `FilledBars` property.
  - name: 4. Generate an RM4SCC barcode with filled bars
    text: RM4SCC (Royal Mail 4‑State Customer Code) is the UK postal barcode. Like
      Planet, the default appearance uses solid bars.
  - name: Full source code in one block
    text: Copy the following snippet into a new C# console project. It compiles with
      .NET 6.0 and produces three PNG files in the `Barcodes` subfolder.
  - name: Next steps
    text: '* **Generate other postal barcodes** – try `EncodeTypes.Postnet` or `EncodeTypes.USPSIntelligentMail`.
      * **Customize appearance** – experiment with `BarHeight`, `ForeColor`, and `BackColor`
      to match your branding. * **Integrate into a web service** – expose the generation
      logic via ASP.NET Core endp'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak vytvořit obrázky poštovních čárových kódů v C# pomocí Aspose.BarCode
url: /cs/python-java/general/how-to-create-postal-barcode-images-in-c-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit obrázky poštovních čárových kódů v C# pomocí Aspose.BarCode

Pokud potřebujete **vytvořit poštovní čárový kód** obrázky v .NET projektu, tento průvodce ukazuje kompletní, připravené‑k‑spuštění řešení. Uvidíte, jak generovat čárové kódy Planet a RM4SCC, přepínat mezi plnými a prázdnými pruhy a ukládat výsledky jako PNG soubory — vše pomocí několika řádků C# kódu.

Generování spolehlivých poštovních čárových kódů je nezbytné pro automatizaci pošty, hromadný tisk štítků a integraci s logistickými platformami. Na konci tohoto tutoriálu budete mít znovupoužitelný úryvek kódu, který můžete zkopírovat do libovolné C# konzolové nebo webové aplikace.

## Požadavky

* .NET 6.0 SDK nebo novější nainstalovaný  
* Visual Studio 2022 (nebo jakékoli IDE podporující .NET)  
* Aktivní **Aspose.BarCode** NuGet balíček (`Install-Package Aspose.BarCode`)  

Tyto nástroje jsou dostačující pro zkompilování a spuštění příkladu bez dalších závislostí.

## Krok‑za‑krokem průvodce k **vytvoření poštovního čárového kódu** obrázků

Proces se skládá ze čtyř logických kroků:

1. Připravte výstupní složku.  
2. Vygenerujte Planet čárový kód s vyplněnými pruhy (výchozí vzhled).  
3. Vygenerujte Planet čárový kód s prázdnými pruhy.  
4. Vygenerujte RM4SCC čárový kód s vyplněnými pruhy.

Každý krok je vysvětlen níže a kompletní zdrojový kód se objeví po vysvětleních.

### 1. Připravte výstupní složku

Obrázky čárových kódů potřebují zapisovatelný adresář. Kód vytvoří složku, pokud neexistuje, čímž zabrání výjimce `DirectoryNotFoundException` během běhu.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // Define the output folder (adjust the path to your environment)
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

        // Ensure the folder exists
        Directory.CreateDirectory(outputFolder);
```

*Proč je to důležité*: Chybějící adresář zastaví program před vygenerováním jakéhokoli čárového kódu. Použití `Directory.CreateDirectory` je bezpečné, protože pokud složka již existuje, nic neudělá.

### 2. Vygenerujte Planet čárový kód s vyplněnými pruhy

Planet čárové kódy používá mnoho poštovních služeb pro domácí poštu. Výchozí nastavení `FilledBars` vykresluje plné pruhy, což je nejběžnější vizuální styl.

```csharp
        // Step 2: Generate a Planet barcode with filled bars (default)
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        // XDimension controls the width of a single bar; 4 pixels works well for screen display
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
        planetFilled.Save(Path.Combine(outputFolder, "PostalPlanetFilledBars.png"),
                          BarCodeImageFormat.Png);
```

*Vysvětlení*:
* `EncodeTypes.Planet` říká Aspose.BarCode, aby použil standard Planet.  
* Řetězec dat `"123456"` je platná Planet data (6 číselných znaků).  
* `XDimension.Pixels = 4` dává šířku pruhu 4 px, což vyvažuje čitelnost a velikost souboru.  
* `Save` zapíše obrázek jako PNG, bezztrátový formát vhodný pro další zpracování.

### 3. Vygenerujte Planet čárový kód s prázdnými pruhy

Některé poštovní specifikace vyžadují **prázdné** (průsvitné) pruhy. Toto chování můžete přepnout pomocí vlastnosti `FilledBars`.

```csharp
        // Step 3: Generate a Planet barcode with empty bars
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        // Setting FilledBars to false creates hollow bars
        planetEmpty.Parameters.Barcode.FilledBars = false;
        planetEmpty.Save(Path.Combine(outputFolder, "PostalPlanetEmptyBars.png"),
                         BarCodeImageFormat.Png);
```

*Tip*: Při přepínání mezi plnými a prázdnými pruhy nechte hodnotu `XDimension` nezměněnou, aby se zachovala konzistentní velikost napříč obrázky.

### 4. Vygenerujte RM4SCC čárový kód s vyplněnými pruhy

RM4SCC (Royal Mail 4‑State Customer Code) je britský poštovní čárový kód. Stejně jako Planet, výchozí vzhled používá plné pruhy.

```csharp
        // Step 4: Generate an RM4SCC barcode with filled bars (default)
        BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFilled.Save(Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png"),
                          BarCodeImageFormat.Png);
    }
}
```

*Proč RM4SCC*: Formát RM4SCC kóduje 6‑číslicový číselný řetězec plus kontrolní součet, což jej činí ideálním pro britské poštovní služby.

### Kompletní zdrojový kód v jednom bloku

Zkopírujte následující úryvek do nového C# konzolového projektu. Kompiluje se s .NET 6.0 a vytvoří tři PNG soubory ve složce `Barcodes`.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // -------------------------------------------------
        // 1. Prepare the output folder
        // -------------------------------------------------
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // -------------------------------------------------
        // 2. Planet barcode – filled bars (default)
        // -------------------------------------------------
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
        planetFilled.Save(Path.Combine(outputFolder, "PostalPlanetFilledBars.png"),
                          BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 3. Planet barcode – empty bars
        // -------------------------------------------------
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        planetEmpty.Parameters.Barcode.FilledBars = false;
        planetEmpty.Save(Path.Combine(outputFolder, "PostalPlanetEmptyBars.png"),
                         BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 4. RM4SCC barcode – filled bars (default)
        // -------------------------------------------------
        BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFilled.Save(Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png"),
                          BarCodeImageFormat.Png);

        Console.WriteLine("All barcode images have been saved to: " + outputFolder);
    }
}
```

#### Očekávaný výstup

Spuštěním programu se vypíše potvrzovací řádek a vytvoří se tři soubory:

* `PostalPlanetFilledBars.png` – Planet čárový kód s plnými pruhy  
* `PostalPlanetEmptyBars.png` – Planet čárový kód s prázdnými (průsvitnými) pruhy  
* `PostalRM4SCCFilledBars.png` – RM4SCC čárový kód s plnými pruhy  

Každý obrázek má šířku 4 px na pruh, vhodný pro náhled na obrazovce nebo pro vložení do PDF připraveného k tisku.

## Často kladené otázky a řešení okrajových případů

| Otázka | Odpověď |
|----------|--------|
| **Co když je řetězec dat neplatný?** | Aspose.BarCode vyhodí `ArgumentException`. Před vytvořením generátoru ověřte délku vstupu (Planet = 6 čísel, RM4SCC = 6 čísel). |
| **Mohu změnit formát obrázku?** | Ano. Nahraďte `BarCodeImageFormat.Png` za `Jpeg`, `Gif`, `Bmp` nebo `Tiff` podle potřeby. |
| **Jak upravit výšku pruhu?** | Použijte `planetFilled.Parameters.Barcode.BarHeight` (výchozí je 50 px). |
| **Je bezpečné použít tento kód ve webovém API?** | Rozhodně. Generátor je thread‑safe pro operace jen ke čtení, ale vytvořte nový `BarcodeGenerator` pro každý požadavek, aby nedošlo ke sdílenému stavu. |
| **Co s ostatními poštovními standardy?** | Aspose.BarCode také podporuje `EncodeTypes.Postnet`, `EncodeTypes.USPSIntelligentMail` atd. Stejný vzor platí — stačí změnit hodnotu `EncodeTypes`. |

## Závěr

Nyní víte, jak **vytvořit poštovní čárový kód** obrázky v C# pomocí Aspose.BarCode, zahrnující jak formáty Planet, tak RM4SCC a ukazující, jak přepínat mezi plnými a prázdnými pruhy. Kompletní, spustitelný příklad můžete vložit do libovolného .NET projektu a získat okamžitý vizuální výstup.

### Další kroky

* **Generujte další poštovní čárové kódy** — vyzkoušejte `EncodeTypes.Postnet` nebo `EncodeTypes.USPSIntelligentMail`.  
* **Přizpůsobte vzhled** — experimentujte s `BarHeight`, `ForeColor` a `BackColor`, aby odpovídaly vaší značce.  
* **Integrujte do webové služby** — zveřejněte logiku generování přes ASP.NET Core endpointy pro tvorbu čárových kódů na požádání.  

Ovládnutím těchto technik budete schopni **generovat planet čárové kódy** obrázky a s jistotou odpovídat na dotazy „**jak generovat čárový kód v C#**“, ať už vytváříte desktopový nástroj pro poštu nebo cloudové API pro dopravu. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s krok‑za‑krokem vysvětleními, která vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vlastních projektech.

- [Jak vytvořit planet čárový kód s vyplněnými a prázdnými pruhy](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [Jak vytvořit RM4SCC čárový kód a generovat planet čárový kód v C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-generate-planet-barcode-in/)
- [Generovat poštovní čárový kód v C# – Kompletní průvodce s Planet čárovým kódem](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
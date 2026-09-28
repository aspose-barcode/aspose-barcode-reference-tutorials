---
category: general
date: 2026-08-15
description: Obrázek čárového kódu PNG v C# – naučte se generovat poštovní čárové
  kódy, vytvořit Planet čárový kód a změnit výšku čárového kódu pomocí jednoduchého
  generátoru.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode image png
- barcode generator c#
- generate postal barcode
- create planet barcode
- change barcode height
language: cs
lastmod: 2026-08-15
og_description: Návod Barcode image PNG v C# ukazuje, jak generovat poštovní čárové
  kódy, vytvořit čárový kód Planet a změnit výšku čárového kódu pomocí API BarcodeGenerator.
og_image_alt: Screenshot of generated PNG barcode with custom height using C# BarcodeGenerator
og_title: Obrázek čárového kódu PNG v C# – generování a úprava čárových kódů
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Barcode image PNG in C# – learn how to generate postal barcodes, create
    a Planet barcode, and change barcode height with a simple generator.
  headline: Barcode image PNG in C# generate barcodes, change height
  type: TechArticle
tags:
- barcode
- C#
- PNG
- postal
- generator
title: PNG obrázek čárového kódu v C# – generovat čárové kódy, změnit výšku
url: /cs/python-java/general/barcode-image-png-in-c-generate-barcodes-change-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode image PNG in C# – generování čárových kódů, změna výšky

Pokud potřebujete **barcode image PNG** v C#, tento návod vás provede kompletním procesem. Naučíte se generovat poštovní čárové kódy, vytvořit Planet čárový kód a změnit výšku čárového kódu, aniž byste opustili své IDE.

Generování spolehlivých PNG čárových kódů je běžnou potřebou pro přepravní štítky, inventární systémy a automatizovaná poštovní řešení. Na konci tohoto tutoriálu budete mít znovupoužitelný úryvek kódu, který vytváří vysoce kvalitní PNG soubory pro formáty Planet i RM4SCC, a pochopíte, jak upravit výšku čárového kódu tak, aby splňovala poštovní specifikace.

## Co budete potřebovat

- .NET 6+ nebo .NET Framework 4.7.2 (API BarcodeGenerator funguje s jakýmkoli moderním .NET runtime)  
- Odkaz na NuGet balíček **Aspose.BarCode for .NET** (nebo jakoukoli kompatibilní knihovnu, která poskytuje `BarcodeGenerator`, `EncodeTypes` a `BarCodeImageFormat`)  
- Základní znalost syntaxe C# a práce se soubory (I/O)  

Žádné další nástroje nejsou potřeba; kód běží ve Visual Studio, Rider nebo v `dotnet` CLI.

## Barcode image PNG – základní generování

Prvním krokem je vytvořit **barcode image PNG** s výchozími rozměry. Tím se vytvoří výchozí soubor, který můžete později přizpůsobit.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Define the output folder (replace with your own path)
string outputFolder = @"C:\Barcodes";

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);

// 1️⃣ Create a Planet barcode generator with default height
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width (X‑dimension) to 4 pixels – this defines the thin bar size
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG; this is the first **barcode image PNG** you’ll produce
planetGenerator.Save(Path.Combine(outputFolder, "PlanetBarHeightDefault.png"),
                     BarCodeImageFormat.Png);
```

**Proč to funguje:**  
- `EncodeTypes.Planet` říká generátoru, aby použil symbologii Planet, která je vyžadována mnoha poštovními službami.  
- `XDimension.Pixels` řídí šířku nejmenšího pruhu; hodnota 4 px poskytuje čitelný čárový kód při typických velikostech štítků.  
- Metoda `Save` zapíše **barcode image PNG** soubor na disk a zachová veškeré vektorové informace jako rastrové pixely.

## Změna výšky čárového kódu – přizpůsobení vizuální hmotnosti

Poštovní směrnice často vyžadují konkrétní výšku pruhu. Následující úryvek ukazuje, jak nastavit vlastní výšku 100 pixelů pro stejný Planet čárový kód.

```csharp
// 2️⃣ Apply a custom 100‑pixel bar height
planetGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Overwrite or save as a new file to keep both versions
planetGenerator.Save(Path.Combine(outputFolder, "PlanetBarHeight100.png"),
                     BarCodeImageFormat.Png);
```

**Proč měníte výšku:**  
Vyšší pruh zlepšuje spolehlivost skenování na tiskárnách s nízkým rozlišením, zatímco nižší pruh šetří místo na štítku. Vlastnost `BarHeight.Pixels` vám umožní jemně doladit tento atribut, aniž by to ovlivnilo X‑dimenzi.

## Generování poštovního čárového kódu – vytvoření příkladu RM4SCC

Formát RM4SCC je další běžný poštovní čárový kód používaný ve Spojeném království. Kroky generování jsou podobné příkladu Planet, což posiluje vzor **barcode generator c#**.

```csharp
// 3️⃣ Create an RM4SCC barcode generator with default height
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Keep the same module width for consistency
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the default‑height PNG
rm4sccGenerator.Save(Path.Combine(outputFolder, "RM4SCCBarHeightDefault.png"),
                     BarCodeImageFormat.Png);
```

## Změna výšky čárového kódu – varianta RM4SCC

Stejně jako u Planet čárového kódu můžete upravit výšku pruhu RM4SCC. Níže uvedený kód nastaví výšku na 100 px a vytvoří druhý **barcode image PNG** pro stejný datový řetězec.

```csharp
// 4️⃣ Set a custom 100‑pixel bar height for RM4SCC
rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the customized PNG
rm4sccGenerator.Save(Path.Combine(outputFolder, "RM4SCCBarHeight100.png"),
                     BarCodeImageFormat.Png);
```

## Kompletní, spustitelný příklad

Spojením všech kroků dohromady získáte jeden samostatný program, který vytvoří čtyři PNG soubory:

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        string outputFolder = @"C:\Barcodes";
        Directory.CreateDirectory(outputFolder);

        // Planet barcode – default height
        var planet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planet.Parameters.Barcode.XDimension.Pixels = 4;
        planet.Save(Path.Combine(outputFolder, "PlanetBarHeightDefault.png"),
                    BarCodeImageFormat.Png);

        // Planet barcode – custom 100‑pixel height
        planet.Parameters.Barcode.BarHeight.Pixels = 100;
        planet.Save(Path.Combine(outputFolder, "PlanetBarHeight100.png"),
                    BarCodeImageFormat.Png);

        // RM4SCC barcode – default height
        var rm4scc = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4scc.Parameters.Barcode.XDimension.Pixels = 4;
        rm4scc.Save(Path.Combine(outputFolder, "RM4SCCBarHeightDefault.png"),
                    BarCodeImageFormat.Png);

        // RM4SCC barcode – custom 100‑pixel height
        rm4scc.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4scc.Save(Path.Combine(outputFolder, "RM4SCCBarHeight100.png"),
                    BarCodeImageFormat.Png);

        Console.WriteLine("All barcode PNG files have been generated in " +


## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto návodu. Každý zdroj obsahuje kompletní funkční příklady kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Vytvořit čárový kód s vlastní výškou – jednorozměrné čárové kódy](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [Vytvořit čárový kód PNG – poměr stran DataMatrix – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [Vytvořit obrázek čárového kódu C# – příklad GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
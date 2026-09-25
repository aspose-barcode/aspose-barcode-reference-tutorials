---
category: general
date: 2026-08-22
description: Vytvořte čárový kód FCC 11 v C# pomocí Aspose.BarCode. Naučte se krok
  za krokem kód, nastavte rozměry a generujte PNG obrázky pro Australia Post.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create fcc 11 barcode
- Australia Post barcode
- Aspose.BarCode C#
- FCC 59 barcode
- FCC 62 barcode
- N‑Table encoding
- C‑Table encoding
language: cs
lastmod: 2026-08-22
og_description: Vytvořte čárový kód FCC 11 v C# pomocí Aspose.BarCode. Postupujte
  podle tohoto stručného tutoriálu a generujte PNG čárové kódy pro Australia Post,
  včetně variant FCC 59 a FCC 62.
og_image_alt: Screenshot showing a generated FCC 11 barcode image
og_title: Vytvořte čárový kód FCC 11 v C# – kompletní průvodce Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  headline: How to create FCC 11 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  name: How to create FCC 11 barcode in C# with Aspose.BarCode
  steps:
  - name: 4.1 FCC 59 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)'
  - name: 4.2 FCC 62 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)'
  - name: 4.3 FCC 62 with C‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix'
  - name: 4.4 FCC 62 with Other encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567321032103210"); // Long payload for "Other" table'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- AustraliaPost
title: Jak vytvořit čárový kód FCC 11 v C# s Aspose.BarCode
url: /cs/python-java/general/how-to-create-fcc-11-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit FCC 11 čárový kód v C# s Aspose.BarCode

Pokud potřebujete **vytvořit FCC 11 čárový kód** v .NET aplikaci, tento návod vám ukáže přesný potřebný kód. Uvidíte, jak nastavit rozměry čárového kódu, vybrat správnou kódovací tabulku a uložit výsledek jako PNG soubor.

Generování čárových kódů Australia Post je běžnou požadavkem pro logistiku, poštovní systémy a sledování zásob. Tento tutoriál pokrývá formát FCC 11 a také ukazuje, jak vytvořit čárové kódy FCC 59 a FCC 62 s různými kódovacími tabulkami, takže můžete stejný vzor použít i pro jiné poštovní služby.

## Co budete potřebovat

* .NET 6.0 SDK nebo novější nainstalováno  
* Visual Studio 2022 (nebo jakékoli C#‑kompatibilní IDE)  
* Platná licence pro **Aspose.BarCode for .NET** – komunitní edice funguje pro hodnocení  
* Oprávnění k zápisu do složky, kde budou PNG soubory ukládány  

Tyto předpoklady zajišťují, že kód se zkompiluje a spustí bez další konfigurace.

## Krok 1: Nainstalujte NuGet balíček Aspose.BarCode

Otevřete terminál ve složce projektu a spusťte:

```bash
dotnet add package Aspose.BarCode
```

Příkaz přidá nejnovější stabilní verzi knihovny do vašeho souboru projektu. Balíček obsahuje třídu `BarcodeGenerator`, která je používána v celém tomto tutoriálu.

## Krok 2: Definujte výstupní složku

Vytvořte složku, kde budou ukládány vygenerované obrázky. Cesta může být absolutní nebo relativní k spustitelnému souboru.

```csharp
// Step 2: Define the output folder
string outputPath = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputPath);
```

`Directory.CreateDirectory` zajistí, že složka existuje, čímž zabrání chybám za běhu při zápisu souboru metodou `Save`.

## Krok 3: Vygenerujte FCC 11 čárový kód

Formát FCC 11 je výchozí kódování pro poštovní čárové kódy Australia Post. Následující kód vytvoří čárový kód, který kóduje číselný řetězec `1101234567`.

```csharp
// Step 3: Create a BarcodeGenerator for FCC 11
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,      // Use the Australia Post symbology
    "1101234567");                  // Data for FCC 11

// Configure visual appearance
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;   // Width of a single module
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50; // Height of the barcode

// Save as PNG
string fcc11Path = Path.Combine(outputPath, "PostalAustraliaPostFCC11.png");
barcodeGenerator.Save(fcc11Path, BarCodeImageFormat.Png);
```

**Proč to funguje:**  
* `EncodeTypes.AustraliaPost` říká knihovně, aby použila pravidla kódování Australia Post.  
* Datový řetězec `1101234567` odpovídá specifikaci FCC 11: první dvě číslice (`11`) určují formát, následované 7‑ciferným zákaznickým odkazem.  
* `XDimension` a `BarHeight` řídí velikost tištěného čárového kódu, což je důležité pro čitelnost skenerem.  

Po spuštění programu najdete `PostalAustraliaPostFCC11.png` ve složce `Barcodes`. Obrázek vypadá takto:

![create fcc 11 barcode example](https://example.com/fcc11.png "FCC 11 barcode generated by Aspose.BarCode")

## Krok 4: Vytvořte další čárové kódy Australia Post (volitelné)

Zatímco hlavním cílem je **vytvořit FCC 11 čárový kód**, často potřebujete čárové kódy FCC 59 nebo FCC 62 pro různé poštovní třídy. Níže uvedený kód znovu používá stejnou instanci `BarcodeGenerator`, mění pouze datový řetězec a volitelnou kódovací tabulku.

### 4.1 FCC 59 s kódováním N‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;

// Use N‑Table for customer information interpretation
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc59Path = Path.Combine(outputPath, "PostalAustraliaPostFCC59NTable.png");
barcodeGenerator.Save(fcc59Path, BarCodeImageFormat.Png);
```

### 4.2 FCC 62 s kódováním N‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc62NPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62NTable.png");
barcodeGenerator.Save(fcc62NPath, BarCodeImageFormat.Png);
```

### 4.3 FCC 62 s kódováním C‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.CTable;

string fcc62CPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62CTable.png");
barcodeGenerator.Save(fcc62CPath, BarCodeImageFormat.Png);
```

### 4.4 FCC 62 s jiným kódováním

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567321032103210"); // Long payload for "Other" table

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.Other;

string fcc62OtherPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62OtherTable.png");
barcodeGenerator.Save(fcc62OtherPath, BarCodeImageFormat.Png);
```

Všechny čtyři obrázky jsou uloženy vedle sebe ve stejné složce, což usnadňuje vizuální porovnání rozdílů.

## Krok 5: Pochopte kódovací tabulky

Australia Post definuje tři kódovací tabulky:

* **N‑Table** – interpretuje číselné zákaznické informace. Použijte ji, když data obsahují pouze číslice.  
* **C‑Table** – podporuje alfanumerické znaky, užitečné pro referenční čísla, která obsahují písmena.  
* **Other** – záložní možnost pro vlastní nebo rozšířené datové formáty.  

Výběr správné tabulky zajišťuje, že skener čárových kódů dekóduje informace přesně tak, jak je zamýšleno. Pokud vynecháte vlastnost `AustralianPostEncodingTable`, knihovna použije výchozí N‑Table, což může oříznout nečíselné znaky.

## Tipy, okrajové případy a běžné úskalí

| Situace | Doporučený postup |
|-----------|----------------------|
| Délka datového řetězce je kratší než požadováno | Doplňte číselnou část úvodními nulami, aby splňovala specifikaci FCC. |
| Čárový kód se při tisku jeví rozmazaný | Zvyšte `XDimension` na 5 nebo 6 pixelů a ověřte nastavení DPI tiskárny. |
| Skener vrací „neplatný formát“ | Ověřte, že správná kódovací tabulka (N‑Table, C‑Table, Other) odpovídá datovému payloadu. |
| Spuštění na Linuxu bez GUI | Ujistěte se, že je odkazován balíček `System.Drawing.Common`, nebo použijte metodu `Save` s `BarCodeImageFormat.Png`, která nevyžaduje grafický kontext. |
| Potřebujete jiný formát obrázku | Nahraďte `BarCodeImageFormat.Png` za `BarCodeImageFormat.Jpeg` nebo `BarCodeImageFormat.Tiff` podle potřeby. |

Tyto praktické tipy vycházejí z reálných nasazení poštovních čárových kódů.

## Kompletní spustitelný příklad

Níže je samostatný program, který můžete zkopírovat do nového konzolového projektu (`dotnet new console`) a spustit bez úprav.



## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak generovat čárový kód v Java – Australia Post Barcode s Aspose](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)
- [Vytvořit jednorozměrný Databar GS1 kódování s Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Jak vytvořit tichou zónu čárového kódu .NET pro Code 16K pomocí Aspose.BarCode](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
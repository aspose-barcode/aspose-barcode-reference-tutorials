---
category: general
date: 2026-07-18
description: Vytvořte obrázky GS1 čárových kódů v C# pomocí tohoto krok‑za‑krokem
  průvodce, jak generovat čárový kód v C# s využitím Aspose.BarCode – bez zbytečného
  textu, jen funkční kód.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create gs1 barcode images
- how to generate barcode c#
language: cs
lastmod: 2026-07-18
og_description: Vytvořte obrázky GS1 čárových kódů v C# pomocí tohoto stručného tutoriálu.
  Naučte se, jak generovat čárový kód v C# pomocí Aspose.BarCode a během několika
  sekund uložit soubory PNG.
og_image_alt: Screenshot of a generated GS1‑MicroPDF417 barcode saved as a PNG file
og_title: Vytvořte obrázky GS1 čárových kódů v C# – Kompletní návod
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create GS1 barcode images in C# with this step‑by‑step guide on how
    to generate barcode C# using Aspose.BarCode – no fluff, just working code.
  headline: Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly
  type: TechArticle
tags:
- barcode
- csharp
- gs1
- aspose
title: Vytvořte GS1 obrázky čárových kódů v C# – Jak rychle generovat čárový kód v
  C#
url: /cs/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořte obrázky GS1 čárových kódů v C# – Jak generovat čárový kód v C#

Už jste někdy potřebovali **vytvořit obrázky gs1 čárových kódů** pro balící štítek, ale nevedeli jste, kde začít? Nejste v tom sami. V tomto tutoriálu uvidíte přesně **jak generovat čárový kód v c#** kód, který během několika minut vytvoří obrázky GS1‑MicroPDF417.

Provedeme vás celým procesem – instalací knihovny, konfigurací generátoru, výměnou dat AI (Application Identifier) a nakonec uložením sady PNG souborů. Na konci budete mít připravenou konzolovou aplikaci, která vygeneruje několik obrázků GS1 čárových kódů, z nichž každý odráží jinou kombinaci AI.

---

## Co budete potřebovat

- **.NET 6+** (nebo .NET Framework 4.6+). Nejnovější runtime funguje nejlépe s Aspose.BarCode.
- **Aspose.BarCode for .NET** – nainstalujte pomocí NuGet (`Install-Package Aspose.BarCode`).
- Složka na disku, kam budou ukládány PNG soubory (nazveme ji `YOUR_DIRECTORY`).
- Základní znalost syntaxe C# – nic složitého není potřeba.

Pokud už to máte, skvělé. Pokud ne, nejprve si stáhněte NuGet balíček; jde o jediný řádek v Package Manager Console a postará se o všechny závislosti.

---

## Krok 1: Nastavte minimální konzolový projekt

Open your favorite IDE (Visual Studio, Rider, or VS Code) and create a new console project:

```bash
dotnet new console -n Gs1BarcodeDemo
cd Gs1BarcodeDemo
dotnet add package Aspose.BarCode
```

Nahraďte automaticky vygenerovaný soubor `Program.cs` kódem uvedeným v následujících krocích. Tento kostra nám poskytuje čistý základ pro **vytvoření obrázků gs1 čárových kódů** bez zbytečného nepořádku.

---

## Krok 2: Jak vytvořit obrázky gs1 čárových kódů – Inicializace generátoru

Jádrem operace je `BarcodeGenerator`. Spustíme jej s počáteční hodnotou GS1‑MicroPDF417, například `(17)991231(10)ABCD`. Tento řetězec kóduje dva AI: datum expirace (17) a šarže/lot (10).

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with a GS1‑MicroPDF417 barcode type
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.GS1MicroPdf417,
            "(17)991231(10)ABCD");
```

**Proč je to důležité:** `EncodeTypes.GS1MicroPdf417` říká Aspose, že pracujeme s kompaktním, vysoce hustým formátem GS1. Začátek s platným AI řetězcem zajišťuje, že první PNG, který uložíme, již splňuje standardy GS1.

---

## Krok 3: Úprava vizuálních parametrů – jemné doladění velikosti a rozložení

Čárový kód, který je příliš malý nebo podivně tvarovaný, se nenačte. Zde nastavíme X‑dimenzi (šířku modulu) na 2 pixely, omezíme počet sloupců, aby byl obrázek úzký, a povolíme propojení, aby bylo možné později spojit více čárových kódů, pokud bude potřeba.

```csharp
        // Set visual parameters for a crisp, scannable image
        barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;      // module width
        barcodeGen.Parameters.Barcode.Pdf417.Columns = 2;        // column count
        barcodeGen.Parameters.Barcode.Pdf417.IsLinked = true;   // enable linking
```

**Tip:** Pokud potřebujete vyšší čárový kód, zvyšte `Rows` místo sloupců. Hrajte si s `XDimension`, aby vyhovoval minimální velikosti modulu 0,33 mm požadované většinou skenerů.

---

## Krok 4: Uložení prvního čárového kódu – AI 17 + AI 10

Nyní skutečně zapíšeme obrázek na disk. Název souboru odráží použité AI, což usnadňuje pozdější vyhledání.

```csharp
        // Save the first image (AI 17 + AI 10)
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_17_10.png",
                        BarCodeImageFormat.Png);
```

Po spuštění programu byste měli v `YOUR_DIRECTORY` vidět ostrý PNG. Otevřete jej – uvidíte drobné čáry a pod nimi lidsky čitelný text. To je první z mnoha **gs1 obrázků čárových kódů**, které vygenerujeme.

---

## Krok 5: Změna kódovaných dat – opětovné použití stejného generátoru

Místo vytváření nového `BarcodeGenerator` pro každou dvojici AI jednoduše vyměníme vlastnost `CodeText` a znovu zavoláme `Save`. Tento přístup je nejefektivnější způsob, jak **vytvořit gs1 obrázky čárových kódů** hromadně.

```csharp
        // AI 15 (best before) + AI 10 (batch)
        barcodeGen.CodeText = "(15)991231(10)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_15_10.png",
                        BarCodeImageFormat.Png);

        // AI 13 (production date) + AI 21 (serial)
        barcodeGen.CodeText = "(13)991231(21)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_13_21.png",
                        BarCodeImageFormat.Png);

        // AI 11 (manufacture date) + AI 21 (serial)
        barcodeGen.CodeText = "(11)991231(21)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_11_21.png",
                        BarCodeImageFormat.Png);

        // Only AI 17 (expiration) – no batch number
        barcodeGen.CodeText = "(17)991231";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_17.png",
                        BarCodeImageFormat.Png);
```

**Proč znovu použít?** Změna `CodeText` eliminuje režii znovu vytvoření generátoru a zaručuje konzistentní vizuální nastavení napříč všemi obrázky.

---

## Krok 6: Spusťte, ověřte a dolaďte

Compile and run:

```bash
dotnet run
```

Měli byste nyní mít pět PNG souborů, z nichž každý je pojmenován podle AI dvojice, kterou obsahuje. Otevřete kterýkoli z nich v prohlížeči obrázků; uvidíte čárový kód a kódovaný text pod ním. Pro dvojitou kontrolu správnosti dat použijte bezplatnou aplikaci GS1 scanner na vašem telefonu – nasměrujte ji na PNG na obrazovce a sledujte, jak se zobrazí hodnoty AI.

**Časté problémy a jak se jim vyhnout**

| Problém | Příčina | Řešení |
|---------|---------|--------|
| Čárový kód nečitelný | `XDimension` příliš nízká (např. 1 pixel) | Zvýšit na 2 nebo 3 pixely |
| Chybějící závorky AI | Nesprávný formát `CodeText` | Vždy obalte každý AI v závorkách |
| Obrázek příliš velký | Příliš mnoho sloupců/řádků | Snižte `Columns` nebo nechte Aspose automaticky nastavit velikost |
| Runtime error `EncodeTypes` not found | Chybějící `using Aspose.BarCode.Generation` | Přidejte chybějící direktivu `using` |

---

## Krok 7: Rozšíření příkladu – generování dalších kombinací AI

Pokud potřebujete **vytvořit gs1 obrázky čárových kódů** pro desítky variant produktů, zvažte načtení dvojic AI z CSV souboru:

```csharp
using System.IO;

string[] lines = File.ReadAllLines(@"ai_pairs.csv"); // format: "(17)991231,(10)ABCD"
foreach (var line in lines)
{
    barcodeGen.CodeText = line.Replace(',', ' ');
    string fileName = $"GS1MicroPdf417_{line.Replace("(", "").Replace(")", "").Replace(",", "_")}.png";
    barcodeGen.Save(Path.Combine(@"YOUR_DIRECTORY", fileName), BarCodeImageFormat.Png);
}
```

Tato malá smyčka načte každý řádek, vymění data a uloží PNG s popisným názvem – ideální pro velké tiskové linky štítků.

---

## Závěr

Nyní máte kompletní, připravený C# program, který **vytváří gs1 obrázky čárových kódů** pro různé scénáře AI, a ukazuje nejužší cestu, jak **generovat čárový kód v c#** pomocí Aspose.BarCode. Opětovným použitím jedné instance `BarcodeGenerator`, laděním vizuálních parametrů a výměnou `CodeText` můžete vytvořit tolik GS1‑MicroPDF417 PNG, kolik váš projekt vyžaduje.

Co dál? Zkuste přidat barvy (`barcodeGen.Parameters.Barcode.ForeColor`), vložit čárový kód do PDF, nebo přejít na jinou GS1 symbologii, jako je DataMatrix. Stejný postup platí – inicializovat, konfigurovat, nastavit `CodeText` a uložit.

Neváhejte zanechat komentář, pokud narazíte na potíže, nebo sdílet své vlastní varianty. Šťastné programování a ať jsou vaše skeny vždy čisté!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vlastních projektech.

- [Jak vytvořit tichou zónu čárového kódu pro Code 16K pomocí Aspose.BarCode pro .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Jak vytvořit tichou zónu čárového kódu pro ITF-14 pomocí Aspose.BarCode pro .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Jak generovat čárový kód – konfigurace Code 39 s Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
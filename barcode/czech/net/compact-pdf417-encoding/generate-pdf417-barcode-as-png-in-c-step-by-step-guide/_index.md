---
category: general
date: 2026-10-28
description: Vygenerujte čárový kód PDF417 v C# a exportujte jej jako PNG obrázek.
  Naučte se, jak nastavit rozložení, sloupce a řádky, a soubor uložit.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- barcode generator PNG
- how to set PDF417
- how to generate PNG barcode
- how to configure PDF417 barcode
language: cs
lastmod: 2026-10-28
og_description: Vygenerujte čárový kód PDF417 v C# a uložte jej jako PNG obrázek.
  Postupujte podle tohoto kompletního návodu, jak nastavit rozvržení, sloupce a řádky
  a vytvořit soubor čárového kódu vysoké kvality.
og_image_alt: Screenshot of a generated PDF417 barcode saved as a PNG file
og_title: Generujte čárový kód PDF417 jako PNG – C# tutoriál
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Generate PDF417 barcode in C# and export it as a PNG image. Learn how
    to configure layout, set columns and rows, and save the file.
  headline: Generate PDF417 barcode as PNG in C# – step‑by‑step guide
  type: TechArticle
tags:
- C#
- PDF417
- barcode
- image generation
title: Generování PDF417 čárového kódu jako PNG v C# – krok za krokem průvodce
url: /cs/net/compact-pdf417-encoding/generate-pdf417-barcode-as-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření čárového kódu PDF417 jako PNG v C# – krok za krokem

Pokud potřebujete **vytvořit čárový kód PDF417** v .NET aplikaci, tento průvodce vám přesně ukáže, jak vytvořit čárový kód a uložit jej jako PNG obrázek. Naučíte se, jak nakonfigurovat rozložení čárového kódu, nastavit počet sloupců a řádků a vytvořit soubor, který lze použít ve skladovém, ticketingovém nebo mobilním skenovacím scénáři.

Tutoriál pokrývá vše od instalace požadované knihovny až po zpracování okrajových případů, jako jsou neplatné hodnoty rozložení. Není potřeba žádná externí dokumentace – stačí zkopírovat kód, spustit jej a získáte připravený obrázek čárového kódu.

## Požadavky

* .NET 6.0 SDK nebo novější nainstalovaný  
* Vývojové prostředí pro C# (Visual Studio, VS Code nebo Rider)  
* Přístup k internetu pro stažení NuGet balíčku **Aspose.BarCode for .NET** (knihovna použita v příkladech)  

Tyto požadavky zajišťují, že kód se zkompiluje a spustí bez další konfigurace.

## Krok 1: Instalace knihovny pro čárový kód

Nejjednodušší způsob, jak získat schopnost **generovat čárový kód PNG**, je použít oficiální balíček Aspose.BarCode. Otevřete terminál ve složce projektu a spusťte:

```bash
dotnet add package Aspose.BarCode
```

Příkaz přidá knihovnu a její závislosti do souboru projektu. Po úspěšné instalaci můžete odkazovat na třídy ve vašich C# zdrojových souborech.

## Krok 2: Vytvoření generátoru čárového kódu PDF417

Vytvoření objektu čárového kódu je základem procesu. Následující úryvek vytvoří generátor, který kóduje text `"Sample"` pomocí symbologie PDF417.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for PDF417
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");
```

*Proč je tento krok důležitý* – Třída `BarcodeGenerator` zapouzdřuje všechna nastavení potřebná pro vykreslení. Zadáním `EncodeTypes.Pdf417` říkáte knihovně, aby vytvořila **čárový kód PDF417**, což je vrstvený lineární kód ideální pro ukládání velkého množství dat.

## Krok 3: Jak nastavit sloupce a řádky PDF417

Čárový kód PDF417 lze přizpůsobit úpravou jeho matice. Dvě nejčastější parametry jsou **sloupce** (horizontální moduly) a **řádky** (vertikální moduly). Ovládání těchto hodnot ovlivňuje velikost a čitelnost čárového kódu.

```csharp
        // Step 3: Configure a custom layout – set columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4; // allowed range: 2‑30
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // allowed range: 1‑90
```

### Jak nakonfigurovat čárový kód PDF417 pro konkrétní rozměry

* Používejte hodnoty v dokumentovaných rozsazích; čísla mimo rozsah vyvolají výjimku.  
* Vyšší počet sloupců komprimuje čárový kód horizontálně, zatímco více řádků zvyšuje vertikální výšku.  
* Přizpůsobte rozložení cílové tiskové ploše nebo vzdálenosti skenování.  

Pokud potřebujete jiný tvar, změňte čísla podle potřeby. Knihovna automaticky přepočítá velikost modulů, aby čárový kód zůstal skenovatelný.

## Krok 4: Jak vygenerovat PNG čárový kód

Uložení čárového kódu jako PNG souboru je jednorázová operace, jakmile je generátor plně nakonfigurován. PNG poskytuje bezztrátovou kompresi, což je ideální pro ostré obrázky čárových kódů.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        generator.Save("CustomLayout.png", BarCodeImageFormat.Png);
    }
}
```

*Proč PNG* – Výčtový typ `BarCodeImageFormat.Png` říká knihovně, aby vykreslila čárový kód ve formátu PNG. Tento formát zachovává ostré hrany, což je nezbytné pro skenery čárových kódů, které spoléhají na vysoký kontrast hran.

### Očekávaný výstup

Spuštěním programu se vytvoří soubor s názvem **CustomLayout.png** v pracovním adresáři aplikace. Otevřením souboru uvidíte obdélníkový čárový kód PDF417 se čtyřmi sloupci a devíti řádky, který kóduje řetězec `"Sample"`.

![Vytvořit PDF417 čárový kód jako PNG](https://example.com/images/pdf417-custom.png "Vytvořit PDF417 čárový kód jako PNG")

*Text alternativy obrázku*: **Vytvořit PDF417 čárový kód jako PNG** – obrázek čárového kódu vytvořený kódem z tutoriálu.

## Krok 5: Ověření čárového kódu a řešení běžných problémů

Po vygenerování obrázku byste měli ověřit, že skener nebo validační nástroj jej dokáže přečíst. Zde je několik rychlých kontrol:

| Problém | Příčina | Řešení |
|-------|-------|-----|
| Čárový kód je rozmazaný | Obrázek byl po vygenerování změněn velikost | Zachovejte původní velikost PNG; vyhněte se škálování v UI ovládacích prvcích |
| Skener hlásí „neplatná data“ | Sloupce/řádky mimo rozsah nebo data příliš dlouhá pro zvolené rozložení | Snižte množství kódovaného textu nebo zvyšte počet řádků/sloupců |
| PNG soubor je prázdný | Cesta `generator.Save` ukazuje na neexistující adresář | Ujistěte se, že adresář existuje, nebo použijte absolutní cestu |

**Tip:** Když potřebujete průhledné pozadí (např. překrytí čárového kódu na UI prvek), nastavte `generator.Parameters.Image.TransparentBackground = true;` před voláním `Save`.

## Úplný funkční příklad

Níže je kompletní program, který můžete zkopírovat, vložit a spustit bez úprav (kromě výstupní cesty, pokud chcete).

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the generator for PDF417 with sample data
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");

        // Configure custom layout – set columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4; // 2‑30
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // 1‑90

        // Optional: make background transparent
        generator.Parameters.Image.TransparentBackground = true;

        // Save the barcode as a PNG file
        string outputPath = "CustomLayout.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode saved to {outputPath}");
    }
}
```

Spuštěním programu se vypíše potvrzovací zpráva a vytvoří se `CustomLayout.png` ve stejné složce jako spustitelný soubor.

## Závěr

Nyní víte, jak **vytvořit čárový kód PDF417** v C#, nakonfigurovat jeho rozložení s konkrétními sloupci a řádky a exportovat výsledek jako obrázek **PNG čárového kódu**. Kroky zahrnovaly instalaci knihovny Aspose.BarCode, inicializaci generátoru, použití vlastních rozměrů, uložení souboru a ověření výstupu.

Odtud můžete prozkoumat další nastavení, jako je úroveň opravy chyb, okraje čárového kódu nebo vložení obrázku přímo do PDF zprávy. Každé z těchto témat staví na základním vzoru předvedeném v tomto průvodci, takže jste připraveni přizpůsobit řešení jakémukoli .NET scénáři generování čárových kódů.

---

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s krok‑za‑krokem vysvětlením, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vygenerovat PDF417 čárový kód – kompletní programovací průvodce](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)
- [Jak vygenerovat PDF417 čárový kód v C# a nastavit velikost čárového kódu](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/)
- [Jak vygenerovat PDF417 čárový kód s Aspose – kompletní průvodce](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
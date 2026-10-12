---
category: general
date: 2026-09-22
description: Vytvořte makro PDF417 čárový kód pomocí Aspose.BarCode v C#. Naučte se
  krok za krokem, jak generovat čárový kód s Aspose, konfigurovat metadata a uložit
  jako PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- generate barcode with Aspose
- Aspose.BarCode PDF417
- C# barcode generation
- barcode metadata configuration
language: cs
lastmod: 2026-09-22
og_description: Vytvořte makro PDF417 čárový kód pomocí Aspose.BarCode v C#. Tento
  průvodce vám ukáže, jak generovat čárový kód s Aspose, nastavit metadata makra a
  exportovat obrázek.
og_image_alt: Screenshot of a created macro PDF417 barcode using Aspose.BarCode in
  C#
og_title: Vytvořte makro PDF417 čárový kód pomocí Aspose.BarCode (C#) – průvodce krok
  za krokem
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Create macro PDF417 barcode using Aspose.BarCode in C#. Learn step‑by‑step
    how to generate barcode with Aspose, configure metadata, and save as PNG.
  headline: Create macro PDF417 barcode with Aspose.BarCode (C#)
  type: TechArticle
tags:
- Aspose
- PDF417
- C#
- Barcode
title: Vytvořte makro PDF417 čárový kód pomocí Aspose.BarCode (C#)
url: /cs/net/compact-pdf417-encoding/create-macro-pdf417-barcode-with-aspose-barcode-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořte makro PDF417 čárový kód s Aspose.BarCode (C#)

Pokud potřebujete **vytvořit makro PDF417 čárový kód** v .NET aplikaci, tento tutoriál vám přesně ukáže, jak to provést pomocí Aspose.BarCode. Uvidíte kompletní, spustitelný příklad, který **generuje čárový kód s Aspose**, nastavuje všechna makro‑specifická pole a uloží výsledek jako PNG obrázek.

Čárové kódy se často používají pro inventarizaci, přepravu nebo sledování dokumentů a varianta Macro PDF417 vám umožňuje vložit další metadata na úrovni souboru přímo do čárového kódu. Na konci tohoto průvodce budete schopni vygenerovat plně vybavený makro PDF417 čárový kód, který splňuje standard ISO/IEC 15438.

## Co budete potřebovat

* .NET 6.0 SDK nebo novější (kód funguje s .NET Core a .NET Framework)
* Visual Studio 2022 (nebo jakékoli C# IDE)
* Internetové připojení kompatibilní s NuGet pro stažení balíčku Aspose.BarCode
* Základní znalost syntaxe C#

Tyto předpoklady zajišťují, že kód se zkompiluje bez další konfigurace.

## Krok 1: Instalace NuGet balíčku Aspose.BarCode

Knihovna Aspose.BarCode poskytuje třídu `BarcodeGenerator`, která je používána v celém tomto tutoriálu.

```bash
dotnet add package Aspose.BarCode
```

Spuštěním příkazu se přidá nejnovější stabilní verze do souboru projektu (`*.csproj`). Balíček obsahuje podporu pro PDF417, Macro PDF417 a mnoho dalších symbologií.

## Krok 2: Vytvořte nový konzolový projekt (volitelné)

Pokud dáváte přednost čistému startu, vygenerujte konzolovou aplikaci:

```bash
dotnet new console -n MacroPdf417Demo
cd MacroPdf417Demo
```

Vygenerovaný soubor `Program.cs` bude obsahovat kód pro generování čárového kódu.

## Krok 3: Inicializace generátoru čárového kódu

Generátor je vytvořen s hodnotou výčtu `EncodeTypes.MacroPdf417` a textem, který chcete zakódovat. Aspose.BarCode automaticky zpracovává Unicode znaky, takže můžete přímo zahrnout diakritické znaky nebo symboly.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

class Program
{
    static void Main()
    {
        // Step 3: Create a Macro PDF417 barcode generator with the desired text
        using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // The rest of the configuration follows...
```

### Proč je to důležité
`EncodeTypes.MacroPdf417` říká knihovně, aby použila makro verzi PDF417, která přidává možnost vložit metadata na úrovni souboru (ID souboru, počet segmentů atd.). Text `"Åspóse.Barcóde©"` ukazuje, že generátor správně kóduje UTF‑8 znaky.

## Krok 4: Nastavení základních rozměrů čárového kódu

PDF417 vám umožňuje řídit počet sloupců a X‑dimenzi (šířku jednoho modulu). Úprava těchto hodnot ovlivňuje fyzickou velikost čárového kódu a spolehlivost skenování.

```csharp
            // Step 4: Set basic barcode dimensions
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // module width in pixels
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

* **XDimension** – Menší hodnoty vytvářejí hustší čárový kód; větší hodnoty usnadňují skenování nízkým rozlišením.
* **Columns** – Řídí počet datových sloupců; typické hodnoty jsou od 1 do 30.

## Krok 5: Konfigurace metadat Macro PDF417

Macro PDF417 obsahuje další pole, která popisují soubor, který čárový kód představuje. Každé pole je volitelné, ale jejich nastavení zlepšuje interoperabilitu se skenery, které rozumí makro formátu.

```csharp
            // Step 5: Configure Macro PDF417 metadata
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // demo checksum
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // bytes
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### Vysvětlení jednotlivých polí

| Vlastnost | Účel | Typický rozsah |
|----------|------|----------------|
| **MacroPdf417FileID** | Jedinečný identifikátor logického souboru, který může být rozdělen do několika čárových kódů. | 0‑2³²‑1 |
| **MacroPdf417SegmentID** | Index aktuálního segmentu (začíná od 0). | 0‑(SegmentsCount‑1) |
| **MacroPdf417SegmentsCount** | Celkový počet segmentů, které tvoří celý soubor. | 1‑99 |
| **MacroPdf417FileName** | Čitelné jméno souboru. | Do 255 znaků |
| **MacroPdf417Checksum** | Volitelný kontrolní součet pro detekci chyb. | 0‑65535 |
| **MacroPdf417FileSize** | Velikost původního souboru v bajtech. | 0‑2³²‑1 |
| **MacroPdf417TimeStamp** | Časové razítko vytvoření nebo úpravy souboru. | Jakýkoli `DateTime` |
| **MacroPdf417Addressee** | Identifikátor příjemce (např. oddělení nebo stroj). | Volný řetězec |
| **MacroPdf417Sender** | Identifikátor odesílatele (např. název společnosti). | Volný řetězec |
| **MacroPdf417Terminator** | Určuje, zda je tento segment poslední. | `Set` nebo `Unset` |

**Tip:** Pokud rozdělíte velký soubor na více čárových kódů, ujistěte se, že `SegmentID` každého segmentu je sekvenční a že `SegmentsCount` zůstává konstantní ve všech segmentech. Skenery se na tyto hodnoty spoléhají při rekonstrukci původního souboru.

## Krok 6: Uložení obrázku čárového kódu

Aspose.BarCode podporuje mnoho výstupních formátů (PNG, JPEG, BMP, SVG atd.). PNG poskytuje bezztrátovou kvalitu, což je ideální pro testování a dokumentaci.

```csharp
            // Step 6: Save the barcode image as PNG
            barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }
    }
}
```

Spuštěním programu se vytvoří soubor s názvem `ExtPDF417Meta.png` ve výstupním adresáři projektu (`bin/Debug/net6.0/`). Otevřete obrázek v libovolném prohlížeči a ověřte, že čárový kód se vykresluje správně.

## Krok 7: Ověření vygenerovaného čárového kódu (volitelné)

Pokud máte aplikaci pro skenování PDF417 (mobilní nebo desktopovou), naskenujte uložený PNG. Skener by měl vrátit:

* Zakódovaný text `"Åspóse.Barcóde©"`
* Všechna makro pole, která jste nastavili (ID souboru, ID segmentu atd.)

Pro automatické ověření Aspose.BarCode také nabízí třídu `BarCodeReader`:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

using (var reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Text: {result.CodeText}");
        Console.WriteLine($"Macro File ID: {result.GetMacroPdf417FileID()}");
        // Access other macro properties similarly
    }
}
```

Tento úryvek ukazuje, jak programově načíst zpět makro metadata, což potvrzuje, že **generování čárového kódu s Aspose** funguje od začátku do konce.

## Okrajové případy a osvědčené postupy

| Situace | Doporučené řešení |
|-----------|----------------------|
| **Unicode znaky** | Ujistěte se, že zdrojový řetězec je UTF‑8 (výchozí v .NET). Aspose.BarCode automaticky kóduje Unicode, ale ověřte znakovou sadu skeneru. |
| **Velikost souboru** | Macro PDF417 rozděluje soubory na až 99 segmentů. Pokud soubor přesáhne 400 KB, zvyšte `SegmentsCount` a vygenerujte více čárových kódů, každý se sekvenčním `SegmentID`. |
| **Přesnost časového razítka** | Použijte `DateTime.UtcNow` pro univerzální čas; některé skenery očekávají UTC. |
| **Validace kontrolního součtu** | Poskytněte správný kontrolní součet, pokud plánujete ověřovat integritu na přijímací straně. |
| **Různé formáty obrázků** | Použijte `BarCodeImageFormat.Svg` pro vektorovou grafiku, když potřebujete nekonečně škálovatelné čárové kódy. |
| **Výkon** | Znovu použijte jedinou instanci `BarcodeGenerator` při generování mnoha čárových kódů; mezi iteracemi měňte pouze `Parameters`. |

## Kompletní, spustitelný příklad

Níže je kompletní program, který můžete zkopírovat, vložit a spustit bez úprav (za předpokladu, že je nainstalován NuGet balíček).



## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vašich projektech.

- [Příklad Aspose čárového kódu: generování Macro PDF417 v C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [Vytvoření metadat PDF417 čárového kódu v C# – Kompletní krok‑za‑krokem průvodce](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [Jak vygenerovat obrázek PDF417 čárového kódu v C# s Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
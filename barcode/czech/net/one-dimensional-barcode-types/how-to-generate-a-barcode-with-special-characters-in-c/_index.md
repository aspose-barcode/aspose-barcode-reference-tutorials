---
category: general
date: 2026-10-02
description: čárový kód se speciálními znaky v C# – naučte se, jak vygenerovat čárový
  kód se speciálními znaky pomocí Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode with special characters
- how to generate barcode c#
language: cs
lastmod: 2026-10-02
og_description: Čárový kód se speciálními znaky v C# – tento tutoriál ukazuje, jak
  vygenerovat čárový kód v C#, který obsahuje diakritické a ochranné známky, včetně
  kódu a vysvětlení.
og_image_alt: barcode with special characters example output
og_title: Vytvořte čárový kód se speciálními znaky v C# – krok za krokem
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: barcode with special characters in C# – learn how to generate a barcode
    with special characters using Aspose.BarCode.
  headline: How to generate a barcode with special characters in C#
  type: TechArticle
- description: barcode with special characters in C# – learn how to generate a barcode
    with special characters using Aspose.BarCode.
  name: How to generate a barcode with special characters in C#
  steps:
  - name: Why this works
    text: '* **Unicode support** – `BarcodeGenerator` accepts a `string` containing
      any Unicode glyph, so characters like **Å**, **ó**, and **©** are encoded without
      extra steps. * **MacroPdf417** – This format allows you to attach file‑level
      metadata (file ID, segment ID, checksum, etc.) that many enterprise '
  - name: Pro tip
    text: If you target a high‑density label printer, increase `XDimension.Pixels`
      to `3` or `4` to avoid pixel‑level distortion.
  - name: Edge case handling
    text: '* **Large file IDs** – The `FileID` property accepts a 32‑bit integer.
      If your system uses GUIDs, hash the GUID into a 32‑bit value before assignment.
      * **Timestamp precision** – The property stores a `DateTime`. If you need sub‑second
      precision, include it in the filename instead, as the standard d'
  - name: Expected output
    text: '* A PNG file approximately 300 × 150 pixels (size varies with column count).
      * When scanned with a PDF417‑compatible reader, the decoded text displays exactly
      **Åspóse.Barcóde©** and the scanner can reconstruct the original file using
      the macro fields.'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak vygenerovat čárový kód se speciálními znaky v C#
url: /cs/net/one-dimensional-barcode-types/how-to-generate-a-barcode-with-special-characters-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generovat čárový kód se speciálními znaky v C#

Pokud potřebujete v C# vygenerovat čárový kód se speciálními znaky, tento návod vám poskytne kompletní, připravené řešení. Ať už kódujete diakritické písmena jako **Å** nebo symboly jako **©**, níže uvedené kroky vám umožní vytvořit čárový kód MacroPdf417, který zachová každý znak přesně tak, jak jste jej zadali.

Naučíte se, jak generovat čárový kód v C# pomocí knihovny Aspose.BarCode, nakonfigurovat specifická metadata pro MacroPdf417 a uložit výsledek jako PNG obrázek. Nepotřebujete žádné externí nástroje – stačí .NET vývojové prostředí a NuGet balíček Aspose.BarCode.

## Požadavky

* .NET 6.0 SDK nebo novější nainstalovaný  
* Visual Studio 2022 (nebo jakékoli IDE podporující C#)  
* Aspose.BarCode pro .NET přidaný do vašeho projektu (`dotnet add package Aspose.BarCode`)  

Tyto požadavky zajišťují, že kód se zkompiluje bez dalších závislostí.

## Vytvoření čárového kódu se speciálními znaky v C#

Jádrem řešení je vytvoření instance `BarcodeGenerator`, která používá formát `EncodeTypes.MacroPdf417`. Generátor přijímá libovolný Unicode řetězec, takže můžete přímo vložit speciální znaky.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for MacroPdf417 with special characters
        using (BarcodeGenerator barcodeGenerator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // Step 2: Set basic barcode appearance
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Step 3: Configure MacroPdf417 specific metadata
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 checksum
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Step 4: Save the generated barcode as a PNG image
            barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }

        Console.WriteLine("Barcode with special characters generated successfully.");
    }
}
```

### Proč to funguje

* **Unicode podpora** – `BarcodeGenerator` přijímá `string` obsahující jakýkoli Unicode znak, takže znaky jako **Å**, **ó** a **©** jsou zakódovány bez dalších kroků.  
* **MacroPdf417** – Tento formát umožňuje připojit metadata na úrovni souboru (file ID, segment ID, checksum atd.), která očekává mnoho podnikově nasazených skenovacích systémů.  
* **Pixel‑úroveň řízení** – Nastavení `XDimension.Pixels` řídí šířku modulu, což ovlivňuje čitelnost na tiskárnách s nízkým rozlišením.

## Nastavení základního vzhledu čárového kódu

Úprava `XDimension` a počtu sloupců ovlivňuje jak vizuální velikost, tak množství dat, která se vejdou do jednoho řádku. Hodnota `2` pixely poskytuje kompaktní, ale čitelný čárový kód, zatímco `Columns = 5` udržuje symbol dostatečně úzký pro většinu štítků.

### Profesionální tip

Pokud cílíte na tiskárnu štítků s vysokou hustotou, zvyšte `XDimension.Pixels` na `3` nebo `4`, abyste se vyhnuli pixelové deformaci.

## Konfigurace metadat MacroPdf417

MacroPdf417 rozšiřuje standardní specifikaci PDF417 o pole, která popisují, jak má být rekonstruován soubor s více segmenty. Vlastnosti, které nastavujete v příkladu, odpovídají typickému scénáři použití:

| Vlastnost | Účel |
|----------|------|
| `MacroPdf417FileID` | Jedinečný identifikátor celého souboru |
| `MacroPdf417SegmentID` | Index aktuálního segmentu (začíná na 1) |
| `MacroPdf417SegmentsCount` | Celkový počet segmentů v souboru |
| `MacroPdf417FileName` | Logický název souboru (používá některé skenery) |
| `MacroPdf417Checksum` | Kontrolní součet CCITT‑16 pro integritu dat |
| `MacroPdf417FileSize` | Očekávaná velikost v bytech – pomáhá skenerům ověřit úplnost |
| `MacroPdf417TimeStamp` | Časové razítko vytvoření pro auditní záznamy |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Volitelná informace o směrování |
| `MacroPdf417Terminator` | Indikuje, zda se jedná o poslední segment (`Set`) nebo o mezilehlý (`Unset`) |

### Zvládání okrajových případů

* **Velké ID souborů** – Vlastnost `FileID` přijímá 32‑bitové celé číslo. Pokud váš systém používá GUIDy, vytvořte hash GUIDu na 32‑bitovou hodnotu před přiřazením.  
* **Přesnost časového razítka** – Vlastnost ukládá `DateTime`. Pokud potřebujete podsekundovou přesnost, zahrňte ji do názvu souboru, protože standard nepodporuje milisekundy.

## Uložení obrázku čárového kódu

Metoda `Save` zapíše vykreslený čárový kód do souborového systému. Můžete zvolit jiné formáty (`Jpeg`, `Bmp`, `Svg`) změnou `BarCodeImageFormat.Png`. PNG je bezztrátový, což ho činí ideálním pro další zpracování nebo vkládání do PDF souborů.

```csharp
barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
```

Po spuštění programu najdete soubor `ExtPDF417Meta.png` ve výstupním adresáři. Otevřením obrázku uvidíte hustý, víceřádkový čárový kód, který obsahuje text **Åspóse.Barcóde©** spolu s makro metadaty, která jste nakonfigurovali.

### Očekávaný výstup

* PNG soubor o rozměrech přibližně 300 × 150 pixelů (velikost se mění podle počtu sloupců).  
* Při skenování čtečkou kompatibilní s PDF417 se dekódovaný text zobrazí přesně **Åspóse.Barcóde©** a skener může rekonstruovat původní soubor pomocí makro polí.

## Jak generovat čárový kód v C# – běžné úskalí

I když je kód jednoduchý, vývojáři často narazí na následující problémy:

1. **Chybějící NuGet balíček** – Zapomenutí nainstalovat `Aspose.BarCode` vede k chybám při kompilaci. Ověřte odkaz na balíček ve vašem `.csproj`.  
2. **Neplatné znaky pro zvolenou symbologii** – Některé typy čárových kódů (např. Code 128) odmítají určité Unicode rozsahy. MacroPdf417 přijímá celý Unicode soubor, což je nejbezpečnější volba pro speciální znaky.  
3. **Nesprávná cesta k souboru** – Použití relativní cesty bez odpovídajících oprávnění může způsobit výjimku `UnauthorizedAccessException` během běhu. Poskytněte absolutní cestu nebo zajistěte, aby aplikace měla právo zápisu do cílové složky.  

Řešením těchto bodů zajistíte, že generování čárového kódu v C# bude plynulý proces.

## Kompletní funkční příklad

Zkopírujte kompletní program níže do nového konzolového projektu a spusťte jej. Kromě NuGet balíčku není vyžadována žádná další konfigurace.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeSpecialCharsDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator with special characters in the payload
            using (BarcodeGenerator generator =
                   new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Appearance settings
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // MacroPdf417 metadata


## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto návodu. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Čárový kód se speciálními znaky – Kompletní průvodce generováním PDF417 pomocí](/barcode/english/net/compact-pdf417-encoding/barcode-with-special-characters-complete-guide-to-generating/)
- [Jak vygenerovat obrázek čárového kódu s Aspose.BarCode v C#](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)
- [Jak vygenerovat obrázek PDF417 čárového kódu v C# s Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
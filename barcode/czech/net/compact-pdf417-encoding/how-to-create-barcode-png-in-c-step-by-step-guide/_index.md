---
category: general
date: 2026-10-15
description: Vytvořte PNG čárový kód v C# s kompaktním příkladem PDF417 – naučte se
  nastavit sloupce, upravit rozměry a vygenerovat obrázek.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to create barcode
- how to set columns
- c# barcode example
language: cs
lastmod: 2026-10-15
og_description: Vytvořte PNG čárový kód v C# s kompaktním příkladem PDF417. Tento
  návod ukazuje, jak nastavit sloupce, upravit rozměry a uložit obrázek.
og_image_alt: Screenshot showing a generated barcode PNG created with C#
og_title: Vytvořte PNG čárový kód v C# – kompletní programovací tutoriál
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  headline: How to create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  name: How to create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: Initialise the barcode generator with the desired text
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: Set the module (X) dimension in pixels
    text: '```csharp // Set the width of the smallest bar (module) to 2 pixels generator.Parameters.Barcode.XDimension.Pixels
      = 2; ```'
  - name: Define the number of columns for the PDF417 barcode
    text: '```csharp // Specify that the barcode should use 3 columns generator.Parameters.Barcode.Pdf417.Columns
      = 3; ```'
  - name: Enable the compact layout by truncating the barcode
    text: '```csharp // Truncate removes unnecessary empty rows, making the barcode
      shorter generator.Parameters.Barcode.Pdf417.Truncate = true; ```'
  - name: Save the barcode image as PNG
    text: '```csharp // Choose the output folder and file name string outputPath =
      Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");'
  - name: Full, runnable example
    text: 'Putting everything together, here is a self‑contained program you can copy,
      paste, and run:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: Jak vytvořit PNG čárový kód v C# – krok za krokem průvodce
url: /cs/net/compact-pdf417-encoding/how-to-create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit barcode PNG v C# – krok za krokem

Pokud potřebujete **vytvořit barcode PNG** soubory z C# kódu, tento tutoriál vám ukáže kompletní řešení během několika řádků. Uvidíte, jak nastavit sloupce, upravit velikost modulu a uložit kompaktní PDF417 čárový kód jako PNG obrázek – vše v jednom snadno čitelném příkladu.

Programové generování čárových kódů odstraňuje ruční krok používání grafického editoru a umožňuje vložit čárové kódy přímo do faktur, vstupenek nebo štítků zásob. V následujících sekcích pokryjeme vše, co potřebujete vědět o **vytvoření barcode** obrázků, proč každé nastavení má význam a jak přizpůsobit kód pro různé scénáře.

## Požadavky

Než začnete, ujistěte se, že máte:

* .NET 6.0 nebo novější (kód funguje také s .NET Framework 4.7+)
* Odkaz na knihovnu pro čárové kódy, která podporuje PDF417, například **Aspose.BarCode for .NET** nebo **IronBarcode**. Příklad používá Aspose.BarCode, kterou můžete nainstalovat přes NuGet:

```bash
dotnet add package Aspose.BarCode
```

* Základní znalost syntaxe C# a Visual Studio (nebo libovolného IDE, které preferujete).

> **Tip:** Pokud hledáte bezplatnou alternativu, open‑source knihovna **ZXing.Net** také podporuje PDF417, ale názvy vlastností se mírně liší. Koncepty zde zůstávají stejné.

## Jak vytvořit barcode PNG v C# (hlavní krok)

Jádrem řešení je objekt `BarcodeGenerator` nakonfigurovaný pro kódování PDF417. Následující sekce rozebírají každý řádek kódu, vysvětlují **jak nastavit sloupce** a ukazují, proč nastavení ovlivňuje konečnou velikost PNG.

### Krok 1: Inicializace generátoru čárového kódu s požadovaným textem

```csharp
using Aspose.BarCode.Generation;

// The text you want to encode in the barcode
string barcodeText = "Compact example";

// Create a generator for PDF417 barcodes
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
{
    // Subsequent configuration goes here
}
```

*Proč je to důležité*: Výčtový typ `EncodeTypes.Pdf417` říká knihovně, aby vytvořila dvourozměrný vrstvený čárový kód. Konstruktor také přijímá data, která chcete kódovat, takže není potřeba samostatné volání `SetData`.

### Krok 2: Nastavení rozměru modulu (X) v pixelech

```csharp
// Set the width of the smallest bar (module) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**X rozměr** řídí vizuální hustotu čárového kódu. Menší hodnota vytváří kompaktnější obrázek, což je užitečné, když potřebujete úsporný PNG pro mobilní obrazovky nebo omezený tiskový prostor.

### Krok 3: Definování počtu sloupců pro PDF417 čárový kód

```csharp
// Specify that the barcode should use 3 columns
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

Tento řádek ukazuje **jak nastavit sloupce**. PDF417 může automaticky zvolit optimální počet sloupců, ale explicitní nastavení vám dává předvídatelnou šířku, zejména když vkládáte PNG do rozvržení s pevnou velikostí.

### Krok 4: Aktivace kompaktního rozvržení oříznutím čárového kódu

```csharp
// Truncate removes unnecessary empty rows, making the barcode shorter
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

Když je `Truncate` nastaveno na true, knihovna odstraní koncové řádky, které neobsahují data, čímž sníží celkovou výšku obrázku bez ztráty informací.

### Krok 5: Uložení obrázku čárového kódu jako PNG

```csharp
// Choose the output folder and file name
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");

// Save the generated barcode as a PNG file
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Metoda `Save` zapíše čárový kód na disk ve formátu, který specifikujete. PNG je bezztrátový, což ho činí ideálním pro skenovací aplikace vyžadující přesnou detekci hran.

### Kompletní, spustitelný příklad

Sestavením všeho dohromady získáte samostatný program, který můžete zkopírovat, vložit a spustit:

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise the generator with the data to encode
        string barcodeText = "Compact example";

        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
        {
            // 2️⃣ Set module width to 2 pixels for a tighter image
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Explicitly set the number of columns (how to set columns)
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Enable compact layout by truncating empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define the output path and save as PNG (create barcode PNG)
            string outputPath = Path.Combine(Directory.GetCurrentDirectory(), "CompactPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode PNG saved to: {outputPath}");
        }
    }
}
```

**Očekávaný výstup** – Po spuštění programu najdete `CompactPdf417.png` ve složce s výstupem. Obrázek obsahuje třísloupcový PDF417 čárový kód, který je dostatečně kompaktní, aby se vešel na standardní štítek 2 × 2 cm a přitom byl plně čitelný.

![Create barcode PNG example](placeholder.png){alt="Vytvořit barcode PNG pomocí C#"}

## Jak nastavit sloupce pro různou velikost dat (sekundární klíčové slovo)

Počet sloupců ovlivňuje jak šířku, tak čitelnost čárového kódu:

| Sloupce | Přibližná šířka (px) | Typické použití |
|--------|----------------------|-----------------|
| 1‑2    | Úzký, vysoký         | Malé štítky, tisky podobné RFID |
| 3‑5    | Vyvážený             | Univerzální štítky |
| 6‑9    | Široký, nízký        | Velké plakáty nebo balení |

Pokud se řetězec dat prodlouží, knihovna může automaticky zvýšit počet řádků, aby čárový kód zůstal v rámci limitu sloupců. Naopak vynucení příliš nízkého počtu sloupců může způsobit, že čárový kód bude nadměrně vysoký a nemusí se vejít na tiskárnu pokladen. Přizpůsobte počet sloupců fyzickým omezením výstupního média.

## Jak vytvořit barcode obrázky v jiných formátech (sekundární klíčové slovo)

Zatímco PNG je nejčastější formát pro web a mobil, můžete potřebovat **vytvořit barcode** obrázky ve formátech JPEG, BMP nebo SVG pro specializované workflow:

```csharp
// Save as JPEG with 90 % quality
generator.Save("CompactPdf417.jpg", BarCodeImageFormat.Jpeg, 90);

// Save as SVG (vector, infinite scaling)
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

Volba správného formátu závisí na následném spotřebiteli:

* **PNG** – bezztrátový, ideální pro skenery.
* **JPEG** – menší velikost souboru, přijatelné, pokud jsou drobné kompresní artefakty tolerovatelné.
* **SVG** – perfektní pro vysoce rozlišený tisk nebo škálování UI.

## Příklad C# čárového kódu: ošetření chyb a okrajových případů

Robustní **c# barcode example** by měl předvídat runtime problémy:

```csharp
try
{
    // All configuration steps as shown earlier
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode parameter: {ex.Message}");
}
catch (IOException ex)
{
    Console.Error.WriteLine($"Failed to write file: {ex.Message}");
}
```

*Proč obalit do `try/catch`?* Neplatné znaky v textu, nepodporované rozměry nebo problémy s oprávněním zápisu vyvolají výjimky. Jejich elegantní ošetření zabrání zhroucení aplikace během hromadného zpracování.

## Rozšíření příkladu: přidání loga nebo pozadí

Mnoho reálných scénářů vyžaduje překrytí loga nebo barevné pozadí. API Aspose.BarCode vám umožní kombinovat čárový kód s bitmapou:

```csharp
// Load a logo image
using (Bitmap logo = (Bitmap)Image.FromFile("logo.png"))
{
    generator.Parameters.Barcode.ImageFormat = BarCodeImageFormat.Png;
    generator.Parameters.Barcode.Pdf417.EnablePdf417CodewordCount = true; // optional

    // Merge the logo with the barcode (centered)
    generator.Save("BarcodeWithLogo.png", BarCodeImageFormat.Png, logo);
}
```

Tato technika zachovává workflow **create barcode PNG** a zároveň obohacuje vizuální branding finálního obrázku.

## Shrnutí

V tomto průvodci jsme ukázali, jak **vytvořit barcode PNG** soubory v C# pomocí kompaktní konfigurace PDF417. Naučili jste se:

* Přesný kód potřebný k inicializaci `BarcodeGenerator`.
* **Jak nastavit sloupce** a proč je počet sloupců důležitý pro velikost a čitelnost.
* Jak upravit X‑rozměr a povolit oříznutí pro těsnější PNG.
* Způsoby uložení obrázku v PNG, JPEG nebo SVG.
* Vzory ošetření chyb pro produkčně připravený **c# barcode example**.
* Volitelné rozšíření jako překrytí loga a úprava pozadí.

Nyní máte připravený útržek kódu, který můžete integrovat do generátorů faktur, ticketovacích systémů nebo nástrojů pro správu zásob. Experimentujte s různými hodnotami sloupců, velikostmi modulů nebo typy čárových kódů (např. QR, Code128) a sledujte, jak se obrázek mění.

## Další kroky

* Prozkoumejte další typy kódování (`EncodeTypes.QR`, `EncodeTypes.Code128`) pro pokrytí širšího spektra případů.
* Kombinujte generování čárových kódů s knihovnami pro tvorbu PDF (např. **iTextSharp**) a vkládejte PNG přímo do dokumentů.
* Zkoumejte dynamické dimenzování: vypočítejte optimální počet sloupců na základě délky vstupního řetězce a cílových rozměrů štítku.

Šťastné programování a užijte si jednoduchost programového generování ostrých barcode PNG v C#!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, abyste si osvojili další funkce API a prozkoumali alternativní implementační přístupy ve svých projektech.

- [Jak vytvořit PDF417 čárový kód a uložit jej jako PNG v C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)
- [Jak vytvořit PDF417 čárový kód a nastavit jeho velikost v C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/)
- [Jak vytvořit PDF417 čárový kód v C# s kompaktním režimem](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
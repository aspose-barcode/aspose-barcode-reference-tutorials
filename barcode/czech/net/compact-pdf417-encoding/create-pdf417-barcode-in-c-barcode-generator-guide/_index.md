---
category: general
date: 2026-07-18
description: Vytvořte čárový kód PDF417 v C# pomocí generátoru čárových kódů PDF417
  pro C#. Postupujte podle krok‑za‑krokem tutoriálu, jak vytvořit rozšířený kódový
  text, nastavit vzhled a uložit obrázek.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- c# pdf417 barcode generator
language: cs
lastmod: 2026-07-18
og_description: Vytvořte PDF417 čárový kód v C# okamžitě. Tento průvodce ukazuje,
  jak použít generátor PDF417 čárových kódů v C#, nastavit rozšířený režim a exportovat
  PNG.
og_image_alt: Generated PDF417 barcode image created with C# PDF417 barcode generator
og_title: Vytvořte čárový kód PDF417 v C# – Kompletní průvodce generátorem
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create PDF417 barcode in C# using the C# PDF417 barcode generator.
    Follow a step‑by‑step tutorial to build extended codetext, set appearance, and
    save the image.
  headline: Create PDF417 Barcode in C# – Barcode Generator Guide
  type: TechArticle
- description: Create PDF417 barcode in C# using the C# PDF417 barcode generator.
    Follow a step‑by‑step tutorial to build extended codetext, set appearance, and
    save the image.
  name: Create PDF417 Barcode in C# – Barcode Generator Guide
  steps:
  - name: 1. Install the barcode library
    text: 'Open your terminal in the project folder and run:'
  - name: 2. Build the extended codetext
    text: 'PDF417 supports **extended encoding**, allowing you to mix different character
      sets in a single barcode. Below we create three segments:'
  - name: 3. Initialise the **C# PDF417 barcode generator**
    text: Now that we have a valid codetext string, we hand it to the generator. The
      `using` statement ensures the underlying resources are released automatically.
  - name: 4. Configure appearance and encoding mode
    text: 'The default settings give you a tiny barcode that might be hard to read.
      Let’s tweak a few parameters:'
  - name: 5. Save the barcode image
    text: Finally, write the image to disk. The library supports PNG, JPEG, BMP, and
      several vector formats—PNG is a safe default because it preserves crisp edges.
  - name: Handling Unicode and special characters
    text: When you feed Unicode symbols directly into a plain‑text barcode, the generator
      may fall back to a fallback encoding, resulting in garbled output. By using
      `AddECICodetext` you explicitly tell the encoder which character set to apply,
      eliminating guesswork. If you ever need to support **Arabic**, **
  - name: Adjusting error correction level
    text: 'PDF417 offers four error‑correction levels (0‑8). Higher levels increase
      resilience but also enlarge the barcode. Adjust it via:'
  - name: Scaling for print vs. screen
    text: 'For on‑screen display you might keep the default 96 dpi. For high‑resolution
      printing (300 dpi or more), set:'
  - name: Common pitfalls
    text: '- **Missing `using` directive** – Forgetting `using Aspose.BarCode.Encoding;`
      will cause `ECIEncodings` to be undefined. - **Directory not found** – The `Save`
      method won’t create intermediate folders; create them beforehand or use `Path.Combine`
      with `Environment.CurrentDirectory`. - **Wrong encode'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Vytvořte čárový kód PDF417 v C# – Průvodce generátorem čárových kódů
url: /cs/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-barcode-generator-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření PDF417 čárového kódu v C# – Průvodce generátorem čárových kódů

Už jste někdy potřebovali **vytvořit PDF417 čárový kód** v aplikaci C#, ale nebyli jste si jisti, kde začít? Nejste v tom sami — mnoho vývojářů narazí na stejnou překážku, když poprvé řeší dvourozměrné čárové kódy. Dobrá zpráva? S vestavěným **C# PDF417 barcode generator** můžete během několika řádků vytvořit plně funkční čárový kód.

V tomto tutoriálu projdeme celý proces: vytvoříme rozšířený kód textu, který míchá různé znakové sady, nakonfigurujeme generátor pro správný vizuální styl a nakonec uložíme čárový kód jako PNG soubor. Na konci budete mít připravený úryvek kódu, který můžete vložit do libovolného .NET projektu, plus tipy pro práci s okrajovými případy jako jsou Unicode znaky nebo vlastní šířky modulů.

---

## Co budete potřebovat

- **.NET 6.0** nebo novější (příklad funguje také s .NET Framework 4.6+)
- **Aspose.BarCode for .NET** (nebo jakákoli kompatibilní knihovna, která poskytuje `BarcodeGenerator`, `EncodeTypes.Pdf417` atd.)
- Editor kódu — Visual Studio, Rider nebo i VS Code bude stačit
- Složka, do které můžete zapisovat, protože generátor uloží PNG tam

To je vše — žádné další NuGet balíčky kromě samotné knihovny pro čárové kódy.

---

## Průvodce krok za krokem k **vytvoření PDF417 čárového kódu**

### 1. Instalace knihovny pro čárové kódy

Otevřete terminál ve složce projektu a spusťte:

```bash
dotnet add package Aspose.BarCode
```

Balíček přidá jmenný prostor `Aspose.BarCode`, který obsahuje třídu `BarcodeGenerator`, kterou budeme během celého tutoriálu používat.

### 2. Vytvoření rozšířeného kódu textu

PDF417 podporuje **rozšířené kódování**, které vám umožní kombinovat různé znakové sady v jednom čárovém kódu. Níže vytvoříme tři segmenty:

- Segment Windows‑1251 (cyrilice)
- Segment UTF‑8 obsahující Unicode znaky (japonské kanji pro „pes“ a „pravý“)
- Segment prostého textu

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;

// Step 1: Build the extended codetext for the PDF417 barcode
Pdf417ExtCodetextBuilder builder = new Pdf417ExtCodetextBuilder();

// Add a Win1251‑encoded segment
builder.AddECICodetext(ECIEncodings.Win1251, "Will");

// Add a UTF‑8 segment with Unicode characters
builder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");

// Add a plain‑text segment
builder.AddPlainCodetext("Plain text");

// Retrieve the combined codetext string
string extendedCodetext = builder.GetExtendedCodetext();
```

**Proč je to důležité:**  
Pokud použijete jen prostý text, jste omezeni na výchozí podmnožinu ASCII. Explicitním deklarováním ECI (Extended Channel Interpretation) segmentů zajistíte, že skenery každou část interpretují správně, bez ohledu na jazyk nebo použité symboly.

### 3. Inicializace **C# PDF417 barcode generator**

Nyní, když máme platný řetězec kódu textu, předáme jej generátoru. Příkaz `using` zajistí automatické uvolnění podkladových prostředků.

```csharp
// Step 2: Create a PDF417 barcode generator using the extended codetext
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, extendedCodetext))
{
    // Configuration goes here (see next step)
}
```

### 4. Nastavení vzhledu a režimu kódování

Výchozí nastavení vám vytvoří malý čárový kód, který může být těžko čitelný. Upravme několik parametrů:

- **X‑Dimension** — řídí šířku každého modulu (velikost pixelu)
- **EncodeMode** — říká enginu, aby vstup zpracoval jako rozšířený režim
- **TwoDDisplayText** — volitelný lidsky čitelný text zobrazený pod čárovým kódem

```csharp
    // Step 3: Configure barcode appearance and encoding mode
    generator.Parameters.Barcode.XDimension.Pixels = 15; // Wider modules for better scannability
    generator.Parameters.Barcode.Pdf417.EncodeMode = Pdf417EncodeMode.Extended; // Activate extended encoding
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended mode"; // Display text under the symbol
```

**Tip:** Pokud tisknete čárový kód na štítkový tiskárně, zvyšte `XDimension` na 20 px nebo více; většina scannerů ocení trochu větší mezery.

### 5. Uložení obrázku čárového kódu

Nakonec zapíšeme obrázek na disk. Knihovna podporuje PNG, JPEG, BMP a několik vektorových formátů — PNG je bezpečná výchozí volba, protože zachovává ostré hrany.

```csharp
    // Step 4: Save the generated barcode image
    generator.Save("YOUR_DIRECTORY/Pdf417Extended.png", BarCodeImageFormat.Png);
}
```

Ujistěte se, že `YOUR_DIRECTORY` existuje a je zapisovatelný. Po spuštění programu byste měli vidět soubor podobný snímku obrazovky níže.

![Generated PDF417 barcode created with C# PDF417 barcode generator](https://example.com/images/pdf417-extended.png "Generated PDF417 barcode created with C# PDF417 barcode generator")

---

## Použití **C# PDF417 barcode generator** — hlubší pohled

### Zpracování Unicode a speciálních znaků

Když vložíte Unicode symboly přímo do čárového kódu s prostým textem, generátor může přejít na záložní kódování, což vede k poškozenému výstupu. Použitím `AddECICodetext` explicitně řeknete enkodéru, kterou znakovou sadu použít, čímž odstraníte hádání. Pokud potřebujete podporovat **arabštinu**, **hebrejštinu** nebo **emoji**, stačí vybrat odpovídající hodnotu `ECIEncodings`.

### Nastavení úrovně opravy chyb

PDF417 nabízí čtyři úrovně opravy chyb (0‑8). Vyšší úrovně zvyšují odolnost, ale také zvětšují čárový kód. Nastavte ji pomocí:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // Balanced level
```

### Škálování pro tisk vs. obrazovku

Pro zobrazení na obrazovce můžete ponechat výchozí 96 dpi. Pro vysoké rozlišení tisku (300 dpi a více) nastavte:

```csharp
generator.Parameters.ImageResolution = 300;
```

To zajistí, že uložené PNG zachová dostatek detailů pro laserové tiskárny.

### Časté úskalí

- **Chybějící `using` direktiva** — Zapomenutí `using Aspose.BarCode.Encoding;` způsobí, že `ECIEncodings` bude nedefinováno.
- **Adresář nenalezen** — Metoda `Save` nevytvoří mezilehlé složky; vytvořte je předem nebo použijte `Path.Combine` s `Environment.CurrentDirectory`.
- **Špatný režim kódování** — Pokud ponecháte `EncodeMode` na `Pdf417EncodeMode.Auto`, knihovna může váš rozšířený kód textu považovat za prostý text a odstranit ECI značky.

---

## Kompletní, připravený příklad

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;

class Program
{
    static void Main()
    {
        // 1️⃣ Build extended codetext
        Pdf417ExtCodetextBuilder builder = new Pdf417ExtCodetextBuilder();
        builder.AddECICodetext(ECIEncodings.Win1251, "Will");
        builder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
        builder.AddPlainCodetext("Plain text");
        string extendedCodetext = builder.GetExtendedCodetext();

        // 2️⃣ Initialise generator with the extended codetext
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, extendedCodetext))
        {
            // 3️⃣ Configure appearance
            generator.Parameters.Barcode.XDimension.Pixels = 15;
            generator.Parameters.Barcode.Pdf417.EncodeMode = Pdf417EncodeMode.Extended;
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;
            generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended mode";

            // 4️⃣ Save to PNG (ensure the folder exists)
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "Pdf417Extended.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }

        Console.WriteLine("PDF417 barcode generated successfully!");
    }
}
```

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vašich projektech.

- [Jak vytvořit čárový kód – Kompaktní PDF417 s Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak vytvořit rozšířený kód textu pro dotcode s Aspose.BarCode pro .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Vytvořit obrázek čárového kódu c# – Konfigurace řádků a sloupců Codablock F](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
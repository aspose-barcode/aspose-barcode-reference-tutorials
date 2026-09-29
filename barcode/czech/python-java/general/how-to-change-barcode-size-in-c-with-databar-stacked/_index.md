---
category: general
date: 2026-08-22
description: Jak změnit velikost čárového kódu v C# pomocí generátoru DataBar Stacked
  Omni‑Directional. Naučte se nastavit X‑rozměr a poměr stran pro výstup PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to change barcode size
- DataBar Stacked Omni‑Directional barcode
- C# barcode generator
- barcode aspect ratio
- X‑dimension pixels
- BarCodeImageFormat PNG
language: cs
lastmod: 2026-08-22
og_description: Jak změnit velikost čárového kódu v C# pomocí generátoru DataBar Stacked
  Omni‑Directional. Postupujte podle návodu krok za krokem a upravte X‑rozměr a poměr
  stran.
og_image_alt: Screenshot showing how to change barcode size in C#
og_title: Jak změnit velikost čárového kódu v C# – kompletní průvodce
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to change barcode size in C# using the DataBar Stacked Omni‑Directional
    generator. Learn to set X‑dimension and aspect ratio for PNG output.
  headline: How to change barcode size in C# with DataBar Stacked
  type: TechArticle
- description: How to change barcode size in C# using the DataBar Stacked Omni‑Directional
    generator. Learn to set X‑dimension and aspect ratio for PNG output.
  name: How to change barcode size in C# with DataBar Stacked
  steps:
  - name: Create a DataBar Stacked Omni‑Directional barcode generator
    text: The generator object holds all barcode settings. By passing `EncodeTypes.DatabarStackedOmniDirectional`
      and sample data, you create a valid barcode ready for further customization.
  - name: Set the basic module size (X‑dimension) in pixels
    text: The X‑dimension defines the width of a single barcode module. Adjusting
      it changes the overall width and height proportionally.
  - name: Change the barcode aspect ratio to 15 and save the image
    text: The **barcode aspect ratio** controls the height‑to‑width relationship.
      An aspect ratio of 15 yields a relatively tall barcode.
  - name: Change the barcode aspect ratio to 30 and save the new image
    text: Increasing the aspect ratio to 30 makes the barcode even taller, illustrating
      the flexibility of size adjustments.
  - name: Verify the generated images
    text: Open the PNG files in any image viewer. You should see two barcodes with
      identical width (controlled by the X‑dimension) but different heights (controlled
      by the aspect ratio). If the images appear blurry, increase the X‑dimension
      pixels; if they are too tall, lower the aspect ratio.
  - name: What to explore next
    text: '* **Custom colors** – experiment with `barcodeGenerator.Parameters.Barcode.ForeColor`
      and `BackColor` to match brand guidelines. * **Different barcode types** – replace
      `EncodeTypes.DatabarStackedOmniDirectional` with `EncodeTypes.QR` or `EncodeTypes.Code128`
      to see how size parameters differ across'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak změnit velikost čárového kódu v C# pomocí DataBar Stacked
url: /cs/python-java/general/how-to-change-barcode-size-in-c-with-databar-stacked/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak změnit velikost čárového kódu v C# pomocí DataBar Stacked

Pokud potřebujete **jak změnit velikost čárového kódu** v .NET aplikaci, tento průvodce ukazuje přesné kroky pomocí generátoru čárových kódů DataBar Stacked Omni‑Directional. Uvidíte, jak ovládat X‑dimenzi v pixelech, upravit poměr stran čárového kódu a uložit výsledek jako PNG soubor.

Změna velikosti čárového kódu je často vyžadována, když je prostor pro tištěný štítek omezený nebo když je potřeba obrázek s vyšším rozlišením pro digitální kanály. Tento tutoriál pokrývá vše, co potřebujete, od inicializace generátoru až po vytvoření dvou obrázků s různými velikostmi.

## Požadavky

Než začnete, ujistěte se, že máte:

* .NET 6.0 SDK nebo novější nainstalováno  
* Odkaz na NuGet balíček **Aspose.BarCode for .NET**  
* Základní znalost syntaxe C#  

Žádná další konfigurace není vyžadována; kód běží na Windows, Linuxu i macOS.

## Jak změnit velikost čárového kódu v C# – krok za krokem

Následující sekce rozdělují proces na jednotlivé, znovupoužitelné kroky. Každý krok vysvětluje **proč** je kód potřeba, nejen **co** dělá.

### Krok 1: Vytvořte generátor čárových kódů DataBar Stacked Omni‑Directional

Objekt generátoru obsahuje všechna nastavení čárového kódu. Předáním `EncodeTypes.DatabarStackedOmniDirectional` a ukázkových dat vytvoříte platný čárový kód připravený k dalším úpravám.

```csharp
// Step 1: Create a DataBar Stacked Omni‑Directional barcode generator with sample data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

*Proč je to důležité* – Třída **C# barcode generator** zapouzdřuje algoritmus kódování. Začátek s platným generátorem zajišťuje, že následné změny velikosti ovlivní správný typ čárového kódu.

### Krok 2: Nastavte základní velikost modulu (X‑dimenzi) v pixelech

X‑dimenze určuje šířku jednoho modulu čárového kódu. Úprava této hodnoty mění celkovou šířku a výšku úměrně.

```csharp
// Step 2: Define the basic module size (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Proč je to důležité* – Větší X‑dimenze vytváří větší čárový kód, což je užitečné pro tiskárny s nízkým rozlišením. Naopak menší hodnota vytvoří kompaktní čárový kód vhodný pro malé štítky.

### Krok 3: Změňte poměr stran čárového kódu na 15 a uložte obrázek

**Poměr stran čárového kódu** řídí vztah výšky k šířce. Poměr 15 dává relativně vysoký čárový kód.

```csharp
// Step 3: Set the DataBar aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

*Proč je to důležité* – Různá skenovací zařízení mají optimální požadavky na poměr stran. Nastavení poměru na 15 ukazuje, jak **jak změnit velikost čárového kódu** úpravou výšky při zachování šířky definované X‑dimenzí.

#### Očekávaný výstup

Soubor `DatabarAspectRatio15.png` zobrazuje DataBar Stacked Omni‑Directional čárový kód, který je vyšší než výchozí. Šířka čárového kódu odráží 2‑pixelovou X‑dimenzi a výška následuje poměr 15.

### Krok 4: Změňte poměr stran čárového kódu na 30 a uložte nový obrázek

Zvýšení poměru stran na 30 udělá čárový kód ještě vyšším, což ilustruje flexibilitu úprav velikosti.

```csharp
// Step 4: Change the DataBar aspect ratio to 30 and save the new image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

*Proč je to důležité* – Výměnou hodnoty **poměru stran čárového kódu** okamžitě vidíte, jak **jak změnit velikost čárového kódu** bez nutnosti znovu vytvářet generátor. To šetří čas při dávkovém zpracování.

#### Očekávaný výstup

Soubor `DatabarAspectRatio30.png` je viditelně vyšší než předchozí obrázek, což potvrzuje, že poměr stran přímo ovlivňuje výšku čárového kódu.

### Krok 5: Ověřte vygenerované obrázky

Otevřete PNG soubory v libovolném prohlížeči obrázků. Měli byste vidět dva čárové kódy se stejnou šířkou (řízenou X‑dimenzí), ale různou výškou (řízenou poměrem stran). Pokud jsou obrázky rozmazané, zvyšte počet pixelů X‑dimenze; pokud jsou příliš vysoké, snižte poměr stran.

```csharp
// Optional verification code – load images and print dimensions
using (var img15 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio15.png"))
using (var img30 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio30.png"))
{
    Console.WriteLine($"15‑ratio size: {img15.Width}×{img15.Height}");
    Console.WriteLine($"30‑ratio size: {img30.Width}×{img30.Height}");
}
```

*Proč je to důležité* – Programová verifikace zajišťuje, že změny velikosti byly aplikovány správně, což je klíčové pro automatizované build pipeline.

## Běžné varianty a okrajové případy

| Situace | Úprava | Důvod |
|-----------|------------|--------|
| **Velmi malé štítky** | Nastavte `XDimension.Pixels = 1` a `AspectRatio = 10` | Snižuje celkovou stopu při zachování čitelnosti |
| **Tisk ve vysokém rozlišení** | Nastavte `XDimension.Pixels = 4` a `AspectRatio = 20` | Zvyšuje hustotu pixelů pro ostrý výstup |
| **Jiný formát obrázku** | Nahraďte `BarCodeImageFormat.Png` za `BarCodeImageFormat.Jpeg` | Užitečné, když je podpora PNG omezená |
| **Dynamická data** | Předávejte proměnný řetězec do konstruktoru `BarcodeGenerator` | Automaticky generuje čárové kódy pro každý produkt |

Když potřebujete generovat mnoho čárových kódů s různými velikostmi, zabalte kroky do metody:

```csharp
void GenerateDatabar(string data, int xDim, int aspectRatio, string filePath)
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
    generator.Parameters.Barcode.XDimension.Pixels = xDim;
    generator.Parameters.Barcode.DataBar.AspectRatio = aspectRatio;
    generator.Save(filePath, BarCodeImageFormat.Png);
}
```

Volání `GenerateDatabar("(01)98765432109876", 3, 25, "output.png")` vytvoří čárový kód s vlastní velikostí v jediném řádku kódu.

## Profesionální tipy pro spolehlivé změny velikosti

* **Vždy nastavujte X‑dimenzi před poměrem stran.** Změna poměru stran jako první může vést k neočekávanému škálování, pokud X‑dimenze má výchozí neideální hodnotu.  
* **Používejte konzistentní výstupní složku.** Hard‑coding `"YOUR_DIRECTORY"` funguje pro ukázky, ale v produkci raději použijte `Path.Combine(Environment.CurrentDirectory, "Barcodes")`.  
* **Ověřujte velikost vygenerovaného obrázku.** Malé změny v X‑dimenzi nemusí být na obrazovce patrné; kontrola pixelových rozměrů zaručuje, že změna byla aplikována.

## Závěr

Nyní víte **jak změnit velikost čárového kódu** v C# pomocí generátoru DataBar Stacked Omni‑Directional. Úpravou **pixelů X‑dimenze** a **poměru stran čárového kódu** můžete vytvářet PNG obrázky, které vyhovují jakémukoli požadavku na velikost štítku nebo rozlišení. Kompletní, spustitelný příklad výše demonstruje celý workflow od vytvoření generátoru až po ověření velikosti.

### Co prozkoumat dál

* **Vlastní barvy** – experimentujte s `barcodeGenerator.Parameters.Barcode.ForeColor` a `BackColor`, abyste ladili vzhled podle firemních směrnic.  
* **Různé typy čárových kódů** – nahraďte `EncodeTypes.DatabarStackedOmniDirectional` za `EncodeTypes.QR` nebo `EncodeTypes.Code128`, abyste viděli, jak se parametry velikosti liší mezi symbologiemi.  
* **Dávkové zpracování** – kombinujte metodu `GenerateDatabar` s importem CSV pro automatické vytvoření tisíců čárových kódů.

Klidně přizpůsobte úryvky kódu architektuře svého projektu a nechte úpravy velikosti čárových kódů zlepšit spolehlivost skenování i vizuální design. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vašich projektech.

- [Jak upravit velikost čárového kódu – poměr stran Codablock F s Aspose.BarCode pro .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [Jak generovat Aztec čárový kód s vlastním poměrem stran pomocí Aspose.BarCode pro .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Jak generovat a upravit výšku čárového kódu pro jednorozměrný Databar pomocí Aspose.BarCode pro .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
---
category: general
date: 2026-09-23
description: Naučte se, jak v C# vytvořit obrázky čárových kódů Postal Planet s vyplněnými
  a prázdnými pruhy. Postupujte podle tohoto kompletního příkladu s využitím BarcodeGenerator
  a nastavení X‑dimenze.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal planet barcode
- Planet barcode generator C#
- barcode X‑dimension pixels
- filled bars vs empty bars
- BarCodeImageFormat PNG
language: cs
lastmod: 2026-09-23
og_description: Vytvořte planetový poštovní čárový kód v C# s tímto podrobným návodem.
  Generujte jak plné, tak prázdné typy čar pomocí BarcodeGenerator a nastavení X‑dimenze.
og_image_alt: Screenshot showing a created postal planet barcode with filled bars
og_title: Vytvořte čárový kód Postal Planet v C# – kompletní programovací průvodce
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to create postal planet barcode images in C# with filled
    and empty bars. Follow this complete example using BarcodeGenerator and X‑dimension
    settings.
  headline: How to create postal planet barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: Jak vytvořit čárový kód Postal Planet v C# – krok za krokem
url: /cs/python-java/general/how-to-create-postal-planet-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit poštovní planet barcode v C# – krok za krokem

Pokud potřebujete **vytvořit poštovní planet barcode** obrázky v .NET aplikaci, tento tutoriál vám poskytne připravené řešení. Ať už budujete systém štítků pro poštu nebo nástroj pro ověřování adres, uvidíte přesně, jak generovat varianty s **vyplněnými pruhy** i **prázdnými pruhy** pomocí třídy Aspose.Barcode `BarcodeGenerator`.

Naučíte se, jak nakonfigurovat **generátor Planet barcode**, nastavit **X‑dimenzi** (šířku každého pruhu) v pixelech a uložit výsledek jako PNG soubor. Průvodce také vysvětluje, proč můžete zvolit vyplněné pruhy oproti prázdným a jak mezi nimi přepnout jediným řádkem kódu.

## Co budete potřebovat

Než začnete, ujistěte se, že máte:

* .NET 6.0 SDK nebo novější (kód funguje také s .NET Core a .NET Framework)
* Visual Studio 2022 (nebo jakékoli IDE podporující C#)
* NuGet balíček Aspose.Barcode pro .NET (`Aspose.Barcode`) nainstalovaný ve vašem projektu
* Oprávnění k zápisu do složky, kam budou ukládány generované PNG soubory

Tyto předpoklady zajišťují, že příklad se zkompiluje bez další konfigurace.

## Krok 1: Nastavte výstupní složku

Prvním krokem je definovat, kam budou obrázky čárových kódů zapisovány. Funguje absolutní i relativní cesta; jen se ujistěte, že složka existuje, nebo ji vytvořte programově.

```csharp
// Step 1: Define the output folder
string outputFolder = "C:/Barcodes/";

// Ensure the folder exists
if (!Directory.Exists(outputFolder))
{
    Directory.CreateDirectory(outputFolder);
}
```

*Proč je to důležité*: Pokud složka neexistuje, `BarcodeGenerator.Save` vyhodí výjimku. Vytvoření složky předem činí kód odolným v nasazovacích prostředích.

## Krok 2: Inicializujte generátor Planet barcode

**Generátor Planet barcode** (EncodeTypes.Planet) je konkrétní symbologie používaná mnoha poštovními službami. Inicializujete jej s daty, která chcete kódovat – v tomto případě s číselným řetězcem `"123456"`.

```csharp
// Step 2: Create a Planet barcode generator with the data "123456"
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*Proč je to důležité*: `EncodeTypes.Planet` říká Aspose.Barcode, aby použil symbologii Planet, která má pevný vzor pruhů a mezer vhodný pro poštovní směrování.

## Krok 3: Nakonfigurujte X‑dimenzi čárového kódu

**X‑dimenze čárového kódu** určuje šířku každého jednotlivého pruhu. Nastavení na 4 pixely poskytuje čistý, čitelný kód, který se dobře tiskne na standardních tiskárnách štítků.

```csharp
// Step 3: Set the X‑dimension (width of each bar) to 4 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Proč je to důležité*: Příliš malá X‑dimenze může kód učinit nečitelným, zatímco příliš velká hodnota plýtvá prostorem na štítku. Čtyři pixely jsou běžně optimální pro tiskárny s rozlišením 300 dpi.

## Krok 4: Vygenerujte Planet barcode s vyplněnými pruhy

Výchozí režim vykreslování používá **vyplněné pruhy** (černé pruhy na bílém pozadí). Uložte obrázek jako PNG, aby se zachovala bezztrátová kvalita.

```csharp
// Step 4: Save the barcode using the default setting (filled bars)
barcodeGenerator.Save($"{outputFolder}PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

**Očekávaný výstup**: `PostalPlanetFilledBars.png` zobrazuje klasický Planet barcode, kde je každý pruh vyplněný.  

![Příklad vytvořeného poštovního planet barcode s vyplněnými pruhy](https://example.com/filled-bars.png "Příklad vytvořeného poštovního planet barcode s vyplněnými pruhy")

*Proč je to důležité*: Vyplněné pruhy jsou průmyslovým standardem pro většinu poštovních skenerů. Použití PNG zajišťuje, že obrázek zůstane ostrý při tisku.

## Krok 5: Vytvořte druhý generátor pro prázdné pruhy

Abychom ilustrovali srovnání **vyplněných pruhů vs. prázdných pruhů**, vytvoříme další instanci `BarcodeGenerator` se stejnými daty. Opětovné použití stejných dat zaručuje, že oba obrázky budou vizuálně srovnatelné.

```csharp
// Step 5: Create another Planet barcode generator for the same data
BarcodeGenerator emptyBarGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

## Krok 6: Použijte stejnou X‑dimenzi a přepněte na prázdné pruhy

Vlastnost `FilledBars` přepíná režim vykreslování. Nastavením na `false` získáte **prázdné pruhy** (bílé pruhy na černém pozadí). X‑dimenze zůstává stejná, aby byl rozměr konzistentní.

```csharp
// Step 6: Apply the same X‑dimension and configure the barcode to use empty bars
emptyBarGenerator.Parameters.Barcode.XDimension.Pixels = 4;
emptyBarGenerator.Parameters.Barcode.FilledBars = false;
```

*Proč je to důležité*: Některé poštovní služby nebo vlastní pracovní postupy vyžadují inverzní barevné schéma pro lepší kontrast na tmavých médiích. Příznak `FilledBars` vám poskytuje tuto flexibilitu jediným řádkem kódu.

## Krok 7: Vygenerujte Planet barcode s prázdnými pruhy

Nakonec uložte verzi s prázdnými pruhy do stejné výstupní složky.

```csharp
// Step 7: Save the barcode with empty bars
emptyBarGenerator.Save($"{outputFolder}PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**Očekávaný výstup**: `PostalPlanetEmptyBars.png` zobrazuje stejný Planet vzor, ale pruhy jsou prázdné (bílé) a pozadí černé.

![Příklad vytvořeného poštovního planet barcode s prázdnými pruhy](https://example.com/empty-bars.png "Příklad vytvořeného poštovního planet barcode s prázdnými pruhy")

## Ověřte výsledky

Otevřete oba PNG soubory v libovolném prohlížeči obrázků. Měli byste vidět dva vizuálně identické čárové kódy, lišící se jen inverzí barev. Pro potvrzení, že kódy jsou čitelné, můžete použít aplikaci pro čtení čárových kódů na chytrém telefonu, která podporuje symbologii Planet.

Pokud se obrázky jeví jako zkreslené, zkontrolujte hodnotu **X‑dimenze** a ujistěte se, že cesta výstupní složky neobsahuje nelegální znaky.

## Časté problémy a tipy pro nejlepší praxi

| Problém | Proč k tomu dochází | Řešení |
|---------|---------------------|--------|
| **Složka nenalezena** | `Save` vyhodí `DirectoryNotFoundException`, když cesta chybí. | Vytvořte složku pomocí `Directory.CreateDirectory` před uložením. |
| **Nesprávná velikost čárového kódu** | Použití necelé X‑dimenze nebo hodnoty < 2 pixelů vede k nečitelnosti. | Udržujte X‑dimenzi ≥ 2 pixelů; 4 pixely fungují pro většinu tiskáren. |
| **Inverze barev nebyla aplikována** | Zapomenutí nastavit `FilledBars = false`. | Explicitně nastavte `FilledBars` po konfiguraci X‑dimenze. |
| **Špatný formát obrázku** | Ukládání jako JPEG může zavést kompresní artefakty. | Použijte `BarCodeImageFormat.Png` pro bezztrátový výstup. |

## Rozšíření příkladu

* **Změna dat** – Nahraďte `"123456"` libovolným číselným řetězcem až do 12 znaků (Planet podporuje až 12 číslic).  
* **Úprava velikosti obrázku** – Modifikujte `XDimension.Pixels` nebo nastavte `Height`/`Width` přes `barcodeGenerator.Parameters.Image`.  
* **Přidání okraje** – Použijte `barcodeGenerator.Parameters.Barcode.BorderWidth` k vykreslení tenkého obrysu kolem čárového kódu.  
* **Export do jiných formátů** – Změňte `BarCodeImageFormat.Png` na `Jpeg`, `Bmp` nebo `Tiff`, pokud to váš pracovní postup vyžaduje.

## Závěr

Nyní víte, jak **vytvořit poštovní planet barcode** obrázky v C# pomocí Aspose.Barcode `BarcodeGenerator`. Tutoriál pokryl inicializaci **generátoru Planet barcode**, nastavení **X‑dimenze čárového kódu** a vytvoření PNG souborů s **vyplněnými** i **prázdnými** pruhy. S těmito základy můžete integrovat generování poštovních čárových kódů do jakékoli .NET aplikace, přizpůsobit vzhled a zajistit spolehlivé skenování v reálných poštovních systémech.

Chcete se dozvědět víc? Vyzkoušejte generování dalších poštovních symbologií (např. **Postnet** nebo **Intelligent Mail**) nebo kombinujte čárový kód s PDF štítkem pomocí Aspose.PDF. Šťastné programování!

## Co se naučíte dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vašich projektech.

- [Create Planet Barcode Image in C# – How to Generate Postal Barcode](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Barcode generator C# – create Planet barcode and RM4SCC example](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)
- [Create Planet Barcode in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
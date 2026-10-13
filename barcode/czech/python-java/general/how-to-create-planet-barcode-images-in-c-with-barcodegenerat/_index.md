---
category: general
date: 2026-09-26
description: Naučte se rychle vytvářet planetové čárové kódy v C#. Tento průvodce
  zahrnuje plné i prázdné planetové čárové kódy, nastavení X‑rozměru a export obrázku.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode C#
- filled planet barcode
- empty planet barcode
- barcode generator parameters
language: cs
lastmod: 2026-09-26
og_description: Vytvořte planetový čárový kód v C# s kompletním příkladem kódu. Generujte
  jak plné, tak prázdné planetové čárové kódy, nastavte šířku čáry a uložte jako PNG.
og_image_alt: Screenshot showing generated filled and empty planet barcode PNG files
og_title: Vytvořte obrázky planetárních čárových kódů v C# – průvodce krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create planet barcode in C# quickly. This guide covers
    filled and empty Planet barcodes, X‑dimension settings, and image export.
  headline: How to create planet barcode images in C# with BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak vytvořit obrázky planetárních čárových kódů v C# pomocí BarcodeGenerator
url: /cs/python-java/general/how-to-create-planet-barcode-images-in-c-with-barcodegenerat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit obrázky planetových čárových kódů v C# s BarcodeGenerator

Pokud potřebujete **vytvořit planet barcode** jako obrázky v .NET aplikaci, tento tutoriál vám ukáže přesné kroky. Naučíte se, jak vygenerovat jak vyplněný, tak prázdný Planet čárový kód, upravit šířku čáry a exportovat výsledky jako PNG soubory—vše pomocí knihovny Aspose.BarCode pro .NET.

Vytvoření **Planet barcode C#** řešení je jednoduché, jakmile pochopíte klíčové **barcode generator parameters**. V následujících sekcích projdeme kompletní spustitelný kód, vysvětlíme, proč je každé nastavení důležité, a poukážeme na běžné úskalí, abyste se jim vyhnuli hned na první pokus.

## Požadavky

* .NET 6.0 SDK nebo novější nainstalováno.
* Visual Studio 2022 (nebo jakékoli C# IDE, které preferujete).
* NuGet balíček **Aspose.BarCode for .NET** (`Aspose.BarCode`) přidán do vašeho projektu.

Balíček můžete přidat pomocí konzole NuGet Package Manager:

```bash
dotnet add package Aspose.BarCode
```

## Krok 1: Nastavení BarcodeGenerator

Třída `BarcodeGenerator` je vstupním bodem pro všechny úlohy tvorby čárových kódů. Vyžaduje dva argumenty: typ čárového kódu (`EncodeTypes.Planet`) a data, která mají být zakódována.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PlanetBarcodeDemo
{
    static void Main()
    {
        // Create a generator for a filled Planet barcode
        BarcodeGenerator filledPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*Proč je to důležité:* Instanciace generátoru s `EncodeTypes.Planet` říká knihovně, aby použila symboliku **Planet barcode**, která je běžně používána pro poštovní služby v některých zemích. Řetězec `"123456"` je náklad, který se objeví v čárovém kódu.

## Krok 2: Nastavení X‑dimenze (šířka čáry)

X‑dimenze řídí fyzickou šířku každé čáry. Typická hodnota pro vykreslování na obrazovce je 4 pixely, ale můžete ji upravit podle požadavků tisku.

```csharp
        // Define the bar width (X dimension) in pixels
        filledPlanet.Parameters.Barcode.XDimension.Pixels = 4;
```

*Proč je to důležité:* Nastavení `XDimension.Pixels` zajišťuje, že vygenerovaný čárový kód není ani příliš tenký (což způsobuje selhání skenování), ani příliš tlustý (což plýtvá prostorem). Toto nastavení bude znovu použito pro prázdný čárový kód.

## Krok 3: Uložení vyplněného Planet čárového kódu

Exportujte čárový kód do PNG souboru pomocí metody `Save`. Výčtový typ `BarCodeImageFormat.Png` říká knihovně, aby vytvořila bezztrátový obrázek vhodný pro další zpracování.

```csharp
        // Save the filled barcode as a PNG image
        filledPlanet.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

Po spuštění programu najdete `PostalPlanetFilledBars.png` ve výstupní složce. Otevřete jej a ověřte, že čáry jsou plné (vyplněné).

## Krok 4: Vytvoření generátoru pro prázdný Planet čárový kód

**Prázdný planet barcode** zobrazuje stejná data, ale s nevyplněnými (bílými) čarami. To je užitečné pro vizuální návrhy, které překrývají čárový kód na barevných pozadích.

```csharp
        // Create a generator for an empty Planet barcode (unfilled bars)
        BarcodeGenerator emptyPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

Volání konstruktoru je identické jako u vyplněné verze; rozdíl spočívá v parametru, který změníme v dalším kroku.

## Krok 5: Znovupoužití stejné X‑dimenze

Aby byl vizuální rozměr konzistentní, použijte stejnou šířku čáry i pro prázdný čárový kód.

```csharp
        // Use the same bar width as before
        emptyPlanet.Parameters.Barcode.XDimension.Pixels = 4;
```

Znovupoužití **barcode generator parameters** zaručuje, že oba obrázky budou dokonale zarovnány při umístění vedle sebe.

## Krok 6: Přepnutí na nevyplněné čáry

Příznak `FilledBars` určuje, zda jsou čáry vykresleny jako plná černá (výchozí) nebo průhledná bílá.

```csharp
        // Configure the generator to produce empty (unfilled) bars
        emptyPlanet.Parameters.Barcode.FilledBars = false;
```

*Proč je to důležité:* Nastavení `FilledBars = false` obrátí režim vykreslování, což je klíčový rozdíl mezi vyplněným a prázdným Planet čárovým kódem.

## Krok 7: Uložení prázdného Planet čárového kódu

Nakonec exportujte prázdnou verzi do PNG.

```csharp
        // Save the empty barcode as a PNG image
        emptyPlanet.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

Když spustíte program, objeví se dva soubory:

* `PostalPlanetFilledBars.png` – plné černé čáry.
* `PostalPlanetEmptyBars.png` – průhledné (nevyplněné) čáry.

Oba obrázky obsahují stejná data (`123456`) a sdílejí stejnou X‑dimenzi, což je činí zaměnitelnými ve většině UI scénářů.

## Kompletní, spustitelný příklad

Když spojíme vše dohromady, zde je kompletní zdrojový soubor, který můžete zkopírovat a vložit do nového konzolového projektu:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PlanetBarcodeDemo
{
    static void Main()
    {
        // ----------- Filled Planet barcode -----------
        BarcodeGenerator filledPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        filledPlanet.Parameters.Barcode.XDimension.Pixels = 4;
        filledPlanet.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // ----------- Empty Planet barcode ------------
        BarcodeGenerator emptyPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        emptyPlanet.Parameters.Barcode.XDimension.Pixels = 4;
        emptyPlanet.Parameters.Barcode.FilledBars = false;
        emptyPlanet.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

**Očekávaný výstup**

Spuštěním programu se vytvoří dva PNG soubory v pracovním adresáři spustitelného souboru. Otevřete je v libovolném prohlížeči obrázků:

* **Vyplněná verze** – tmavé, plné čáry, které jsou snadno čitelné standardními skenery.
* **Prázdná verze** – čáry se objevují jako bílé mezery na černém pozadí, užitečné pro překryvné efekty.

## Časté úskalí a tipy pro profesionály

| Problém | Proč se to děje | Jak to opravit |
|-------|----------------|---------------|
| Čáry vypadají příliš tenké | X‑dimenze ponechána na výchozí hodnotě (1 pixel) | Nastavte `XDimension.Pixels` na 3‑5 pixelů pro použití na obrazovce; zvýšte pro vysoce rozlišený tisk. |
| Prázdný čárový kód se zobrazuje úplně černě | `FilledBars` není nastaven na `false` | Ujistěte se, že `emptyPlanet.Parameters.Barcode.FilledBars = false;` je provedeno **po** nastavení X‑dimenze. |
| PNG soubor chybí | Cesta k výstupu je nesprávná nebo adresář neexistuje | Zadejte úplnou cestu (`@"C:\Barcodes\PostalPlanetFilledBars.png"`) nebo vytvořte adresář předem pomocí `Directory.CreateDirectory`. |
| Čárový kód selhává při skenování | Řetězec dat obsahuje nelegální znaky pro symboliku Planet | Planet čárové kódy akceptují pouze číselné náklady; ověřte vstup pomocí `int.TryParse`. |

**Tip pro profesionály:** Pokud potřebujete vložit čárový kód do PDF, můžete načíst vygenerovaný PNG do `PdfDocument` pomocí Aspose.PDF, nebo přímo přidat čárový kód jako obrazový stream bez zápisu na disk.

## Další kroky

Nyní, když můžete **vytvořit planet barcode** obrázky, zvažte prozkoumání těchto souvisejících témat:

- **Planet barcode C#** – přizpůsobení barev, přidání lidsky čitelného textu nebo vložení čárového kódu do PDF.
- **Barcode generator parameters** – ladění úrovně opravy chyb, tiché zóny nebo rotace.
- **Batch generation** – iterovat přes seznam poštovních kódů a vytvořit zip soubor s PNG.
- **Alternative formats** – export do SVG nebo JPEG pro webové doručení.

Experimentujte s různými hodnotami `XDimension` a příznakem `FilledBars`, abyste viděli, jak ovlivňují spolehlivost skenování a vizuální styl. Až budete připraveni, integrujte kód generování do svého webového API nebo desktopové aplikace, aby se automaticky vytvářely poštovní čárové kódy za běhu.

---

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Vytvořit Planet Barcode v C# – Kompletní krok‑za‑krokem průvodce](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Barcode generator C# – vytvořit Planet barcode a RM4SCC příklad](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)
- [Generovat poštovní čárový kód v C# – Kompletní průvodce s Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
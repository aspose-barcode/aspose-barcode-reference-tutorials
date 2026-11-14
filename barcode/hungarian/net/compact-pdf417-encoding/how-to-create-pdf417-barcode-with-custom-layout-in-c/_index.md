---
category: general
date: 2026-11-14
description: Tanulja meg, hogyan hozhat létre PDF417 vonalkódot C#-ban gyorsan. Ez
  az útmutató azt is bemutatja, hogyan generáljon PDF417-et, és hogyan testreszabja
  a PDF417 beállításait a pontos vezérlés érdekében.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417
- how to customize pdf417
language: hu
lastmod: 2026-11-14
og_description: Készíts PDF417 vonalkódot C#-ban lépésről‑lépésre útmutatóval. Tanulja
  meg, hogyan generáljon PDF417-et, és hogyan testre szabja a PDF417 paramétereit
  a pontos eredményekért.
og_image_alt: Screenshot showing a generated PDF417 barcode created with C# code
og_title: PDF417 vonalkód létrehozása C#-ban – teljes útmutató egyedi elrendezéssel
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  headline: How to create PDF417 barcode with custom layout in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  name: How to create PDF417 barcode with custom layout in C#
  steps:
  - name: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
    text: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
  - name: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
    text: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
  - name: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
    text: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
  type: HowTo
tags:
- barcode
- pdf417
- C#
title: Hogyan készítsünk PDF417 vonalkódot egyedi elrendezéssel C#-ban
url: /hu/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-custom-layout-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PDF417 vonalkód létrehozása egyedi elrendezéssel C#-ban

Ha **pdf417 barcode létrehozása** egy jegyrendszerhez, készletcímkéhez vagy mobil‑app szkenneléshez szükséges, ez a bemutató a teljes folyamatot mutatja be. Megtudja, hogyan generálhat PDF417‑et gyorsan, és hogyan testreszabhatja a PDF417 beállításait, például az oszlopokat és sorokat, hogy a vonalkód illeszkedjen a tervezési korlátokhoz.

Vonalkód generálásához nem szükséges összetett grafikai könyvtár – elég az Aspose.BarCode for .NET (vagy bármely kompatibilis API). A útmutató végére egy kész‑használatra készült PNG fájlt kap, amelyet beágyazhat PDF‑ekbe, weboldalakba, vagy közvetlenül nyomtathat az alkalmazásából.

## Előfeltételek

- .NET 6.0 vagy újabb (a kód .NET Framework 4.7+‑vel is működik)
- Aspose.BarCode for .NET (NuGet csomag `Aspose.BarCode`)
- Alapvető ismeretek C#‑ban és a Visual Studio‑ban (vagy bármely IDE)

> **Pro tipp:** Ha CI/CD csővezetékben dolgozik, adja hozzá a NuGet csomag hivatkozást a projektfájlhoz, hogy a buildek reprodukálhatók maradjanak.

## 1. lépés: A vonalkód könyvtár telepítése

Nyissa meg a projekt mappáját egy terminálban, és futtassa:

```bash
dotnet add package Aspose.BarCode
```

A csomag tartalmazza a `BarcodeGenerator` osztályt, amelyet a teljes bemutató során használunk. További natív függőségek nem szükségesek.

## 2. lépés: Alap PDF417 vonalkód létrehozása

Az első cél a **pdf417 barcode létrehozása** alapértelmezett beállításokkal. A következő program beállítja a generátort, kódol egy mintaszöveget, és PNG képként menti az eredményt.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417Demo
{
    static void Main()
    {
        // Step 2.1: Initialise the generator for PDF417 with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample text for PDF417");

        // Step 2.2: Save the barcode as PNG
        string outputPath = "Pdf417Default.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

**Miért működik ez:**  
`EncodeTypes.Pdf417` azt mondja a könyvtárnak, hogy a PDF417 szimbólumot használja. A konstruktor automatikusan létrehoz egy `Barcode` objektumot alapértelmezett oszlop/sor értékekkel, amelyek a legtöbb esetben biztosítják a beolvashatóságot.

Futtassa a programot (`dotnet run`). A `Pdf417Default.png` fájlt a projekt mappájában találja. A kép megnyitása egy szabványos PDF417 vonalkódot mutat, amely készen áll a beolvasásra.

![Create PDF417 barcode example](https://example.com/images/pdf417-default.png){:alt="PDF417 vonalkód létrehozása példa, alapértelmezett elrendezés megjelenítése"}

## 3. lépés: PDF417 generálása egyedi méretekkel

Néha egy fix méretű címke vagy UI komponens speciális vonalkód lábnyomot igényel. Itt válik elengedhetetlenné a **pdf417 egyedi oszlopokkal és sorokkal való generálása**.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417CustomDemo
{
    static void Main()
    {
        // Initialise generator with the same text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Custom layout text");

        // ---- Customization begins here ----
        // Set the number of columns (2‑30). Fewer columns make the barcode taller.
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // Set the number of rows (1‑90). More rows make the barcode wider.
        generator.Parameters.Barcode.Pdf417.Rows = 9;
        // ------------------------------------

        // Save the customized barcode
        string outputPath = "Pdf417CustomLayout.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Custom barcode saved to {outputPath}");
    }
}
```

**Miért lehet erre szükség:**  
- **Korlátozott szélesség:** Az oszlopok csökkentése és a sorok növelése szélesebb, de rövidebb vonalkódot eredményez, ami tökéletes szűk címkékhez.  
- **Korlátozott magasság:** Az oszlopok növelése és a sorok csökkentése magasabb, keskenyebb vonalkódot ad, ami hasznos, ha függőleges hely áll rendelkezésre.

Mind a `Columns`, mind a `Rows` csak a dokumentált tartományon belüli értékeket fogadja (oszlopok: 2‑30, sorok: 1‑90). Ha tartományon kívüli értéket ad meg, `ArgumentOutOfRangeException` kivételt dob, ezért mindig ellenőrizze a felhasználói bemenetet, ha ezeket a beállításokat UI‑ban teszi elérhetővé.

## 4. lépés: PDF417 további testreszabása

Az oszlopok és sorok mellett a PDF417 szimbólum számos opcionális paramétert kínál:

| Property | Purpose | Typical values |
|----------|---------|----------------|
| `ErrorLevel` | A hibajavítási képességet szabályozza | 0‑8 (magasabb = robusztusabb) |
| `MacroPdf417` | Engedélyezi a macro PDF417‑t több szegmens adat esetén | `true`/`false` |
| `CompactPdf417` | Kompaktabb vonalkódot hoz létre a hibajavítás csökkenése árán | `true`/`false` |
| `SecurityLevel` | Biztonsági ellenőrző számjegyet ad hozzá | 0‑2 |

Itt egy gyors példa, amely a hibaszintet a maximálisra (8) állítja egy zajos környezethez:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 8;
generator.Parameters.Barcode.Pdf417.CompactPdf417 = true;
```

**Miért fontos:**  
A magasabb hibajavítás lehetővé teszi a szkennereknek, hogy adatot helyreállítsanak még akkor is, ha a vonalkód egy része sérült. Ugyanakkor növeli a vonalkód méretét, ezért egyensúlyozni kell a beállítást a tervezési korlátokkal.

## 5. lépés: A vonalkód működésének ellenőrzése

A PNG generálása után tesztelje bármely vonalkód‑olvasó alkalmazással (a legtöbb okostelefon ingyenes PDF417 olvasóval rendelkezik). Ha a szkenner visszaadja az eredeti szöveget (`Custom layout text`), a vonalkód érvényes.

Ha beolvasási problémákat tapasztal:

1. **Ellenőrizze a méreteket:** Győződjön meg róla, hogy az oszlopok/sorok az engedélyezett tartományon belül vannak.  
2. **Állítsa be a hibaszintet:** Növelje az `ErrorLevel`‑t sérült adathordozón.  
3. **Ellenőrizze a képminőséget:** Mentse magasabb DPI‑vel (`generator.Save(outputPath, BarCodeImageFormat.Png, 300)`) ha nyomtatni szeretné.

## Teljes forráskód újrahasználható segédfüggvényhez

Az alábbi egy kompakt, újrahasználható osztály, amelyet bármely .NET projektbe beilleszthet. Egyetlen metódusban foglalja össze a **pdf417 generálását** és a **pdf417 testreszabását**.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

public static class Pdf417Helper
{
    /// <summary>
    /// Creates a PDF417 barcode image with optional layout parameters.
    /// </summary>
    /// <param name="text">The data to encode.</param>
    /// <param name="outputPath">Full file path for the PNG output.</param>
    /// <param name="columns">Number of columns (2‑30). Pass null to use default.</param>
    /// <param name="rows">Number of rows (1‑90). Pass null to use default.</param>
    /// <param name="errorLevel">Error correction level (0‑8). Null = default.</param>
    public static void CreatePdf417(string text, string outputPath,
                                    int? columns = null,
                                    int? rows = null,
                                    int? errorLevel = null)
    {
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, text);

        // Apply optional customizations
        if (columns.HasValue) generator.Parameters.Barcode.Pdf417.Columns = columns.Value;
        if (rows.HasValue)    generator.Parameters.Barcode.Pdf417.Rows    = rows.Value;
        if (errorLevel.HasValue) generator.Parameters.Barcode.Pdf417.ErrorLevel = errorLevel.Value;

        // Save as high‑resolution PNG (300 DPI) for printing scenarios
        generator.Save(outputPath, BarCodeImageFormat.Png, 300);
    }
}
```

Ezt a segédfüggvényt így hívhatja meg:

```csharp
Pdf417Helper.CreatePdf417(
    text: "Order #12345",
    outputPath: "OrderBarcode.png",
    columns: 5,
    rows: 12,
    errorLevel: 6);
```

A metódus elrejti az ismétlődő boiler‑plate kódot, így az üzleti logikára koncentrálhat.

## Gyakori buktatók és elkerülésük módja

- **Tartományon kívüli értékek:** Mindig ellenőrizze a `columns` és `rows` értékeket, mielőtt hozzárendeli őket.  
- **Helytelen képformátum:** Egyes régi szkennerek csak BMP vagy JPEG formátumot fogadnak el. Szükség esetén használja a `BarCodeImageFormat.Bmp`‑et.  
- **Alacsony DPI nyomtatáshoz:** Az alapértelmezett DPI 96. Magas minőségű nyomtatáshoz állítson be kifejezetten magasabb DPI‑t (pl. 300) a `Save` hívásakor.  
- **Hiányzó betűtípus‑támogatás:** A PDF417 bináris adatot kódol, így általában nem szükséges betűtípust megadni. Ha azonban szöveget helyez a kép fölé, győződjön meg róla, hogy a betűtípus telepítve van a célgépen.

## Összegzés

Most már tudja, hogyan **pdf417 barcode létrehozását** végezze el a kezdetektől a végéig, hogyan **pdf417 generálását** egyedi oszlop/sor beállításokkal, és hogyan **pdf417 testreszabását** hibajavításra és kompaktosságra. Az újrahasználható segédfüggvény minta követésével igény szerint generálhat vonalkódokat, bármilyen elrendezési korláthoz igazíthatja őket, és garantálhatja a megbízható beolvasást a termelési környezetben.

**Következő lépések**

- Fedezze fel a többi szimbólumot, például a QR‑t vagy a Code128‑at ugyanazzal a `BarcodeGenerator` osztállyal.  
- Kombinálja a PNG kimenetet egy PDF generáló könyvtárral (pl. iText7), hogy vonalkódokat ágyazzon be számlákba.  
- Kísérletezzen a `MacroPdf417`‑val több szegmens adatátvitelhez, amely funkció hasznos a logisztikai és szállítási alkalmazásokban.

Boldog kódolást, és legyenek a vonalkódjai mindig első próbálkozásra beolvasva!

## Mit érdemes még megtanulni?

A következő bemutatók szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljesen működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsen elsajátítani további API‑funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeiben.

- [Hogyan generáljunk PDF417 vonalkódot C#‑ban – lépésről‑lépésre útmutató](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [Hogyan generáljunk vonalkódot és testreszabjuk a PDF417 vonalkódot C#‑ban](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/)
- [Hogyan hozzunk létre PDF417 vonalkódot és exportáljunk PNG‑t C#‑ban](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
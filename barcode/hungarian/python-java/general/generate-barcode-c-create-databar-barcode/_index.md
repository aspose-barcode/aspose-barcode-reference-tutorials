---
category: general
date: 2026-07-21
description: Generálj gyorsan vonalkódot C#-ban az Aspose.BarCode segítségével. Tanulj
  meg DataBar vonalkódot létrehozni, testre szabni a vonalkód méretét, és néhány lépésben
  exportálni a vonalkód képét.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode c#
- create databar barcode
- customize barcode size
- change barcode dimensions
- export barcode image
language: hu
lastmod: 2026-07-21
og_description: Generáljon vonalkódot C#-ban az Aspose.BarCode segítségével. Hozzon
  létre DataBar vonalkódot, testreszabja annak méretét, és azonnal exportálja a képet.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode saved as PNG
og_title: Vonalkód generálása C#-ban – DataBar vonalkódok egyedi mérettel
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: Generate barcode C# quickly with Aspose.BarCode. Learn to create DataBar
    barcode, customize barcode size, and export barcode image in just a few steps.
  headline: Generate barcode C# – Create DataBar barcode
  type: TechArticle
- questions:
  - answer: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, `Gif`, or `Svg`.
      The API handles the conversion automatically.
    question: What if I need a different image format?
  - answer: Technically you can set both, but Aspose will prioritize the last property
      you modify. It's safer to set *one* dimension and let the library compute the
      other for a valid DataBar.
    question: Can I change both rows and columns simultaneously?
  - answer: 'Use `barcodeGen.Parameters.Barcode.ForegroundColor` and `BackgroundColor`.
      Example:'
    question: How do I apply a foreground/background color?
  - answer: DataBar Expanded Stacked supports up to 74 numeric characters (or 30 alphanumeric).
      Exceeding that throws an exception.
    question: Is there a size limit for the encoded data?
  type: FAQPage
tags:
- barcode
- csharp
- databar
- image-export
- aspnet
title: Vonalkód generálása C# – DataBar vonalkód létrehozása
url: /hu/python-java/general/generate-barcode-c-create-databar-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vonalkód generálása C# – DataBar vonalkód létrehozása

Szeretne **vonalkód generálása C#**-t anélkül, hogy végtelen dokumentációban merülne el? Jó helyen jár. Ebben az útmutatóban végigvezetjük a **DataBar vonalkód** létrehozását, a méretek finomhangolását, és végül a **vonalkód kép exportálását**—mindössze néhány C# sorral.

Képzelje el, hogy egy kompakt termékcímkékre van szüksége, amely egy apró polcrakorra illeszkedik. A DataBar Expanded Stacked szimbólum megoldja a feladatot, és az Aspose.BarCode segítségével pontosan szabályozhatja, hány oszlopot vagy sort használ. Készen áll? Merüljünk el benne.

## Amit el fogsz érni

- **DataBar vonalkód létrehozása** (a „expanded stacked” változat) a semmiből.  
- **A vonalkód méretének testreszabása** oszlopok vagy sorok közvetlen beállításával.  
- **A vonalkód méreteinek módosítása** menet közben anélkül, hogy újraépítené a generátort.  
- **A vonalkód kép exportálása** PNG formátumba (vagy bármely Aspose által támogatott formátumba).  

## Előfeltételek

- .NET 6.0 vagy újabb (a kód .NET Framework 4.7+‑on is működik).  
- Érvényes Aspose.BarCode for .NET licenc (vagy próbaverzióban futtathatja).  
- A választott IDE – a Visual Studio, Rider vagy VS Code megfelel.  

Ha még nem telepítette a NuGet csomagot, futtassa:

```bash
dotnet add package Aspose.BarCode
```

Ennyi—más függőség nincs.

## 1. lépés: A vonalkód generátor beállítása (Hogyan **vonalkód generálása C#**)

Először is szükségünk van egy `BarcodeGenerator` példányra, amely a **DataBar Expanded Stacked** szimbólumra mutat. Ez az objektum a motor, amely később létrehozza a képet.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Initialize the generator with the desired symbology and data
BarcodeGenerator barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // Symbology
    "Databar Expanded Stacked long");    // Human‑readable text (optional)
```

*Miért fontos*: Az `EncodeTypes.DatabarExpandedStacked` enum azt jelzi az Aspose-nak, hogy a stacked változatot szeretnénk, ami ideális szűk helyeken. A megadott szöveg lesz a kódolt érték; bármilyen numerikus karakterláncra cserélheti, amelyet az alkalmazása igényel.

## 2. lépés: **A vonalkód méretének testreszabása** – oszlopok beállítása

A DataBar vonalkódok lehetővé teszik a vizuális sűrűség befolyásolását a **oszlopok** *vagy* **sorok** számának megadásával. Kezdjük az oszlopokkal. A sorok száma automatikusan lesz kiszámítva, hogy a vonalkód érvényes maradjon.

```csharp
// Set the number of columns; rows are computed automatically
barcodeGen.Parameters.Barcode.DataBar.Columns = 4;
```

*Pro tipp*: Az oszlopok a vonalkód szélességét befolyásolják. Több oszlop → szélesebb vonalkód, ami javíthatja a beolvasás megbízhatóságát alacsony felbontású nyomtatókon.

## 3. lépés: **A vonalkód kép exportálása** az oszlopbeállítással

Most a képet a lemezre írjuk. Választhat PNG, JPEG, BMP vagy akár SVG formátumot is. Itt a PNG a tiszta, veszteségmentes kimenethez.

```csharp
// Save the barcode image using the current column configuration
barcodeGen.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

> **Várható eredmény** – Nyissa meg a `DatabarCols4.png` fájlt, és egy szép, négy oszlopos DataBar-t kell látnia. Sűrű függőleges sávokból álló halom, ami tökéletes egy kis címkéhez.

## 4. lépés: **A vonalkód méreteinek módosítása** – sorok beállítása helyette

Néha egy magasabb vonalkódra van szükség, mint egy szélesebbre. Váltson sorvezérlésre; az Aspose automatikusan újraszámolja az oszlopokat.

```csharp
// Switch to row control – columns will be derived automatically
barcodeGen.Parameters.Barcode.DataBar.Rows = 3;
```

*Miért váltás?* A sorok a vonalkód magasságát befolyásolják. Több sor magasabb szimbólumot eredményez, ami hasznos lehet, ha függőleges helye van, de a szélesség korlátozott.

## 5. lépés: **A vonalkód kép exportálása** a sorbeállítással

Mentse el a második változatot. Figyelje meg, hogy a fájlnév tükrözi a változást; mindkét képet megtarthatja összehasonlítás céljából.

```csharp
// Save the barcode image using the new row configuration
barcodeGen.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

> **Eredmény** – a `DatabarRows3.png` most egy magasabb verziót mutat ugyanabból az adathoz, továbbra is tökéletesen beolvasható.

## Teljes működő példa

Összegezve, itt egy önálló konzolos alkalmazás, amelyet egyszerűen másolhat és azonnal futtathat:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator for DataBar Expanded Stacked
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Customize size – set columns (width)
        barcodeGen.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Export image with column setting
        string colPath = @"C:\Barcodes\DatabarCols4.png";
        barcodeGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column‑based barcode to {colPath}");

        // 4️⃣ Change dimensions – set rows (height)
        barcodeGen.Parameters.Barcode.DataBar.Rows = 3;

        // 5️⃣ Export image with row setting
        string rowPath = @"C:\Barcodes\DatabarRows3.png";
        barcodeGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row‑based barcode to {rowPath}");
    }
}
```

Futtassa a programot, majd nyissa meg a két PNG fájlt. Most már **vonalkód generálása C#**, **a vonalkód méretének testreszabása**, **a vonalkód méreteinek módosítása**, és **a vonalkód kép exportálása** megtörtént—mind mindössze egy perc alatt.

## Gyakori kérdések és szélhelyzetek

- **Mi van, ha más képformátumra van szükségem?**  
  Cserélje le a `BarCodeImageFormat.Png`-t `Jpeg`, `Bmp`, `Gif` vagy `Svg`-re. Az API automatikusan kezeli a konverziót.

- **Beállíthatom egyszerre a sorokat és az oszlopokat?**  
  Technikai szempontból mindkettőt beállíthatja, de az Aspose az utoljára módosított tulajdonságot részesíti előnyben. Biztonságosabb egy dimenziót beállítani, és a könyvtár számolja ki a másikat egy érvényes DataBar-hoz.

- **Hogyan alkalmazhatok előtér/háttér színt?**  
  Használja a `barcodeGen.Parameters.Barcode.ForegroundColor` és `BackgroundColor` beállításokat. Példa:  
  ```csharp
  barcodeGen.Parameters.Barcode.ForegroundColor = Color.DarkBlue;
  barcodeGen.Parameters.Barcode.BackgroundColor = Color.White;
  ```

- **Van méretkorlát a kódolt adatokra?**  
  A DataBar Expanded Stacked legfeljebb 74 numerikus (vagy 30 alfanumerikus) karaktert támogat. Ennek túllépése kivételt eredményez.

## Következő lépések

Miután elsajátította a **create databar barcode** alapjait, fontolja meg a következőket:

- **Szöveges megjegyzések** hozzáadása a vonalkód alá (`barcodeGen.Parameters.CaptionAbove.Text`).
- A PNG közvetlen beágyazása PDF-be az Aspose.PDF segítségével.
- Vonalkódok tömeges generálása CSV-ben szereplő termékazonosítók ciklusával.

Ezek a témák mind ugyanazon a `BarcodeGenerator` objektumon alapulnak, így nem kell a semmiből kezdenie.

---

**Összefoglalás**: most már tudja, hogyan **vonalkód generálása C#**, **a vonalkód méretének testreszabása**, **a vonalkód méreteinek módosítása**, és **a vonalkód kép exportálása** az Aspose.BarCode segítségével. Kísérletezzen az oszlop/sor értékekkel, cserélje ki a képformátumokat, és integrálja a kódot a készlet- vagy POS-rendszerébe. Jó kódolást!

## Mit érdemes még megtanulni?

A következő útmutatók szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljesen működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsen elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket saját projektjeiben.

- [Vonalkód kép generálása – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Hogyan generáljunk Aztec vonalkódot egyedi képaránnyal az Aspose.BarCode for .NET használatával](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [DataMatrix vonalkód generálása – Pro útmutató az Aspose.BarCode segítségével](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
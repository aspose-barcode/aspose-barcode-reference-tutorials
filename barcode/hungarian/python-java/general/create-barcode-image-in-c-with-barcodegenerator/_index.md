---
category: general
date: 2026-08-12
description: Készítsen vonalkód képet C#-ban a BarCodeGenerator használatával. Tanulja
  meg, hogyan generáljon DataBar-t, szabályozza a vonalkód kép méretét, és hatékonyan
  hozzon létre több vonalkódot.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- create multiple barcodes
- how to generate databar
- barcode image size
language: hu
lastmod: 2026-08-12
og_description: C#-ban készítsen vonalkód képet a BarCodeGenerator segítségével. Ez
  az útmutató lépésről lépésre bemutatja, hogyan generáljon DataBar kódokat, állítsa
  be a vonalkód kép méretét, és készítsen több vonalkódot.
og_image_alt: Screenshot of a generated DataBar barcode image saved as PNG
og_title: Vonalkód kép létrehozása C#-ban – teljes BarCodeGenerator útmutató
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  headline: Create barcode image in C# with BarCodeGenerator
  type: TechArticle
- description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  name: Create barcode image in C# with BarCodeGenerator
  steps:
  - name: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
    text: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
  - name: Adjusting **barcode image size** by changing X‑dimension and bar height.
    text: Adjusting **barcode image size** by changing X‑dimension and bar height.
  - name: Using a loop to **create multiple barcodes** with different heights.
    text: Using a loop to **create multiple barcodes** with different heights.
  - name: Saving the images as PNG files and verifying the output.
    text: Saving the images as PNG files and verifying the output.
  type: HowTo
tags:
- barcode
- csharp
- barcodegenerator
- databar
- image-processing
title: Vonalkód kép létrehozása C#‑ban a BarCodeGenerator‑rel
url: /hu/python-java/general/create-barcode-image-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vonalkód kép létrehozása C#-ban a BarCodeGenerator segítségével

Ha .NET alkalmazásban **vonalkód képet** kell létrehoznod, ez az útmutató pontosan megmutatja, hogyan teheted ezt meg a `BarCodeGenerator` osztállyal. Akár kiskereskedelmi POS rendszert, akár készletkövető eszközt építesz, megtanulod, hogyan generálj DataBar szimbólumokat, szabályozd a vonalkód kép méretét, és több vonalkódot állíts elő egy futtatás során.

Felfedezheted, hogyan teszi lehetővé a **barcode generator c#** API a méretek finomhangolását, a kimeneti formátumok váltását, és a szélhelyzetek kezelését, például az érvénytelen adatkarakterláncokat. A tutorial végére magabiztosan **több vonalkódot hozhatsz létre** anélkül, hogy ismétlődő kódot írnál.

## Előkövetelmények

- .NET 6.0 vagy újabb telepítve  
- Fejlesztői környezet (Visual Studio, Rider vagy VS Code)  
- Az Aspose.BarCode for .NET NuGet csomag (vagy bármely kompatibilis könyvtár, amely biztosítja a `BarCodeGenerator`-t)  

A csomagot a következővel adhatod hozzá:

```bash
dotnet add package Aspose.BarCode
```

## A tutorial tartalma

1. **barcode generator c#** példány beállítása DataBar Omni‑directional kódoláshoz.  
2. **barcode image size** módosítása X‑dimenzió és sávmagasság változtatásával.  
3. Ciklus használata **multiple barcodes** létrehozásához különböző magasságokkal.  
4. A képek PNG fájlként mentése és a kimenet ellenőrzése.  

Minden kódrészlet teljes és készen áll a másolásra‑beillesztésre egy új konzol projektbe.

![Vonalkód kép példa](barcode-example.png){alt="Vonalkód kép példa"}

## 1. lépés: Inicializáld a generátort – vonalkód kép alapjai

Az első lépés a `BarCodeGenerator` példányosítása a kívánt szimbólummal. DataBar Omni‑directional szimbólumhoz a `EncodeTypes.DatabarOmniDirectional` értéket használod.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for DataBar Omni‑directional.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarCodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // The rest of the steps are performed below.
        }
    }
}
```

**Miért fontos:** A generátor példányosítása meghatározza a kódolási szabályokat és az adatpayloadot. Ha kihagyod a megfelelő `EncodeTypes` értéket, a könyvtár nem támogatott vonalkódot generál, vagy kivételt dob.

## 2. lépés: X‑dimenzió és sávmagasság beállítása – a vonalkód kép méretének szabályozása

A vonalkód vizuális méretét két paraméter határozza meg:

| Paraméter | Mit szabályoz | Tipikus tartomány |
|-----------|----------------|-------------------|
| `x_dimension.pixels` | A legkisebb modul (a „pont”) szélessége | 1 – 4 px |
| `bar_height.pixels`  | A függőleges sávok magassága | 30 – 150 px |

```csharp
// Set the module width to 2 px for a crisp, readable image.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set an initial bar height of 30 px.
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

**Pro tipp:** A kisebb X‑dimenzió nagyobb felbontású képet eredményez, de alacsony minőségű nyomtatókon nehezebb lehet beolvasni. Állítsd az értéket a célbeolvasó eszközödnek megfelelően.

## 3. lépés: Az első vonalkód mentése – vonalkód kép 30 px magassággal

Most már generálhatod a képet és írhatod a lemezre. A `Save` metódus egy fájlútvonalat és egy képformátum enumot fogad.

```csharp
// Save the 30 px high barcode as a PNG file.
string outputFolder = @"C:\Barcodes";
generator.Save($"{outputFolder}\\Databar30.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar30.png (30 px height)");
```

**Várható eredmény:** Egy `Databar30.png` nevű PNG fájl jelenik meg a `C:\Barcodes` mappában. A fájl megnyitása egy DataBar Omni‑directional szimbólumot mutat tiszta, nagy kontrasztú mintával.

## 4. lépés: Magasság módosítása és további képek generálása – több vonalkód létrehozása

A **több vonalkód** különböző méretekkel való létrehozásához csak módosítanod kell a `BarHeight` tulajdonságot, és újra meghívni a `Save`-et. Ez elkerüli a generátor újra‑példányosítását, ami memóriát és CPU‑időt takarít meg.

```csharp
// Increase the bar height to 60 px for a larger barcode.
generator.Parameters.Barcode.BarHeight.Pixels = 60;
generator.Save($"{outputFolder}\\Databar60.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar60.png (60 px height)");

// You can repeat the process for any height you need.
int[] heights = { 90, 120 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputFolder}\\Databar{h}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved Databar{h}.png ({h} px height)");
}
```

**Miért működik:** A `BarCodeGenerator` objektum tárolja az összes konfigurációs állapotot. Egyetlen tulajdonság módosítása frissíti a renderelő motorját a következő `Save` hívásra, lehetővé téve, hogy hatékonyan **több vonalkódot hozz létre**.

## 5. lépés: Haladó – hogyan generáljunk DataBar-t egyedi adatokkal

A fenti példa egy statikus GS1 payload-ot használ. Valós környezetben gyakran kell változó termékazonosítókat beágyazni. A könyvtár bármely, a DataBar specifikációnak megfelelő karakterláncot elfogad.

```csharp
string[] gtins = { "01234567890123", "98765432109876", "12345678901234" };
foreach (var gtin in gtins)
{
    // GS1 Application Identifier (01) + GTIN
    generator.CodeText = $"(01){gtin}";
    generator.Parameters.Barcode.BarHeight.Pixels = 50; // uniform height
    generator.Save($"{outputFolder}\\Databar_{gtin}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode for GTIN {gtin}");
}
```

**Kulcspont:** A `generator.CodeText` beállítása frissíti a kódolt adatot az objektum újra‑létrehozása nélkül. Ez a javasolt **how to generate databar** minta nagy adathalmazok kezelésekor.

## 6. lépés: Ellenőrzés és hibaelhárítás – a megfelelő vonalkód kép méretének biztosítása

A képek generálása után programozottan is ellenőrizheted, hogy a méretek megfelelnek-e az elvárásoknak. A `System.Drawing`-ből származó `Image` osztály képes beolvasni a fájlt és jelenteni a méretét.

```csharp
using System.Drawing;

// Verify image dimensions
string[] files = { "Databar30.png", "Databar60.png", "Databar90.png" };
foreach (var file in files)
{
    using var img = Image.FromFile($"{outputFolder}\\{file}");
    Console.WriteLine($"{file}: {img.Width}px × {img.Height}px");
}
```

Ha a magasság nem egyezik a beállított értékkel, ellenőrizd:

- **X‑dimension**: Egy nagyon kis érték miatt a renderelő lekerekítheti a magasságot.  
- **Image format**: Néhány formátum (pl. JPEG) tömörítést alkalmaz, ami a mentéskor megváltoztathatja a pixelméreteket. A PNG pontos méreteket őriz.

## 7. lépés: Legjobb gyakorlatok a vonalkód kép méretéhez és teljesítményhez

| Ajánlás | Ok |
|----------------|--------|
| Tartsd a `x_dimension.pixels` értékét 2‑3 px között a legtöbb szkennerhez. | Kiegyensúlyozza az olvashatóságot és a fájlméretet. |
| Használj PNG-t veszteségmentes kimenethez, ha a képet nyomtatni fogod. | Biztosítja a pontos méreteket és a tiszta éleket. |
| Használd újra egyetlen `BarCodeGenerator` példányt sok vonalkód generálásakor. | Csökkenti az objektum‑allokáció terhelését. |
| Érvényesítsd a bemeneti karakterláncot a GS1 szabvány szerint, mielőtt a `CodeText`-hez rendelnéd. | Megakadályozza a futásidejű kivételeket és az érvénytelen beolvasásokat. |
| Tárold a generált képeket egy dedikált mappában, egyértelmű elnevezési konvencióval (pl. `Databar_{GTIN}.png`). | Egyszerűsíti a későbbi feldolgozást és az audit nyomvonalakat. |

## Teljes működő példa

Az alábbiakban a teljes program látható, amely magában foglalja az összes lépést az inicializálástól az ellenőrzésig. Másold a kódot egy új konzol projektbe és futtasd.



## Mit érdemes következőként megtanulni?

A következő tutorialok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás tartalmaz teljes működő kódrészleteket lépésről‑lépésre magyarázatokkal, hogy segítsenek elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [Vonalkód kép generálása – GS1 Kupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [DotCode vonalkód kép létrehozása – sorok és oszlopok (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Hogyan hozzunk létre vonalkód csendes zónát ITF-14-hez az Aspose.BarCode for .NET használatával](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
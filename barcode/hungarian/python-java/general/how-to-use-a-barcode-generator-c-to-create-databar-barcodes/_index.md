---
category: general
date: 2026-09-07
description: C# vonalkódgenerátor oktatóanyag, amely megmutatja, hogyan lehet PNG
  formátumú vonalkódfájlokat generálni, és testreszabható sorokkal és oszlopokkal
  DataBar vonalkódokat létrehozni.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- generate barcode PNG
- create DataBar barcode
language: hu
lastmod: 2026-09-07
og_description: 'Vonalkód-generátor C# oktatóanyag: tanulja meg, hogyan generáljon
  vonalkód PNG fájlokat, és hozzon létre DataBar vonalkódokat egyedi sorokkal és oszlopokkal
  csupán percek alatt'
og_image_alt: Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator
  C#
og_title: C# vonalkód generátor – DataBar vonalkódok és PNG képek létrehozása
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: barcode generator C# tutorial that shows you how to generate barcode
    PNG files and create DataBar barcodes with customizable rows and columns
  headline: How to use a barcode generator C# to create DataBar barcodes
  type: TechArticle
tags:
- barcode
- C#
- DataBar
title: Hogyan használjunk C#-os vonalkódgenerátort DataBar vonalkódok létrehozásához
url: /hu/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan használjunk C# vonalkódgenerátort DataBar vonalkódok létrehozásához

Ha **barcode generator C#**‑re van szüksége magas minőségű vonalkódok létrehozásához, ez az útmutató megmutatja, hogyan **generate barcode PNG** fájlokat készíthet, és **create DataBar barcodes**‑t egyedi sorokkal és oszlopokkal. Akár kiskereskedelmi készletkezelő rendszert, akár jegykezelő platformot épít, az alábbi lépések lehetővé teszik egy DataBar Expanded Stacked vonalkód előállítását egyetlen, önálló példában.

Ebben az útmutatóban megtanulja:

* Hogyan példányosítsa a `BarcodeGenerator`‑t a DataBar Expanded Stacked szimbólumhoz.  
* Hogyan állítsa be az oszlop- és sorbeállításokat az ISO / GS1 specifikációknak megfelelően.  
* Hogyan mentse a kimenetet PNG képként, amely beágyazható weboldalakba vagy nyomtatható címkékre.  

Nem szükséges külső szolgáltatás – csak az Aspose.BarCode for .NET könyvtár (vagy bármely kompatibilis könyvtár, amely ugyanazt az API‑t követi). A kód .NET 6+ környezetben fut, és működik a Visual Studio, Rider vagy bármely C#‑t támogató IDE‑ben.

## Előkövetelmények

Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik:

* .NET 6 SDK vagy újabb telepítve.  
* `Aspose.BarCode` NuGet csomagra való hivatkozás (vagy egy ekvivalens könyvtár, amely biztosítja a `BarcodeGenerator`, `EncodeTypes` és `BarCodeImageFormat` elemeket).  
* Alapvető ismeretek a C# szintaxisról és a projekt struktúrájáról.  

A csomagot a parancssorból adhatja hozzá:

```bash
dotnet add package Aspose.BarCode
```

## 1. lépés: A barcode generator C# inicializálása a DataBar Expanded Stacked-hez

Az első lépés egy `BarcodeGenerator` példány létrehozása, amely a **DataBar Expanded Stacked** szimbólumra irányul. Ez az objektum tartalmazza az összes megjelenítési paramétert, beleértve a kódolandó szöveget.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,          // Symbology
    "Databar Expanded Stacked long");            // Data to encode
```

**Miért fontos:** A `EncodeTypes.DatabarExpandedStacked` enum érték megmondja a könyvtárnak, melyik vonalkód szabványt kell alkalmazni. A megfelelő enum használata biztosítja, hogy a generált kép megfeleljen a GS1 DataBar specifikációknak.

## 2. lépés: Az oszlopok számának beállítása (alapértelmezett sorok használata)

A DataBar Expanded Stacked több oszlopra osztható. Az oszlopszám módosítása megváltoztatja a vizuális sűrűséget, és segíthet a hosszabb adatkarakterláncok korlátozott helyre való illesztésében.

```csharp
// Step 2: Set the number of columns (default rows are used)
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

**Pro tip:** Az alapértelmezett oszlopszám 1. 4‑re állítva négy egymásra helyezett oszlop jön létre, ami ideális a hosszabb numerikus karakterláncokhoz, miközben a vonalkód magassága kezelhető marad.

## 3. lépés: Vonalkód PNG generálása az oszlopbeállítással

Most mentse a vonalkódot PNG képként. A PNG megőrzi a szkennerekhez szükséges éles éleket, és jól működik mind web, mind nyomtatott médiában.

```csharp
// Step 3: Save the barcode image with the column setting applied
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

A `DatabarCols4.png` fájl egy **barcode PNG**‑t tartalmaz, amelyet közvetlenül beágyazhat HTML‑be:

```html
<img src="DatabarCols4.png" alt="Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#">
```

## 4. lépés: Külön generátor példány létrehozása a sorbeállításhoz

Ha a sorok számát szeretné vezérelni az oszlopok helyett, példányosítson egy új `BarcodeGenerator`‑t. Egy dimenzió módosítása után ugyanazon példány újrafelhasználása váratlan elrendezési hibákhoz vezethet, ezért egy új objektum a legbiztonságosabb megoldás.

```csharp
// Step 4: Create a new generator instance for the same barcode type
BarcodeGenerator rowBarcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## 5. lépés: A sorok számának beállítása (alapértelmezett oszlopok használata)

A sorok befolyásolják a vonalkód moduljainak függőleges elrendezését. A sorok növelése magasabb vonalkódot eredményez, ami bizonyos címkeméretekhez szükséges lehet.

```csharp
// Step 5: Set the number of rows (default columns are used)
rowBarcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

**Miért sorok vs. oszlopok:** Az oszlopok a vonalkódot vízszintesen osztják, míg a sorok függőlegesen nyújtják. Válassza ki azt az orientációt, amely a legjobban illeszkedik a címke elrendezéséhez.

## 6. lépés: Vonalkód PNG generálása a sorbeállítással

Végül mentse a sorral módosított vonalkódot PNG fájlként.

```csharp
// Step 6: Save the barcode image with the row setting applied
rowBarcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

Most két különálló PNG fájlja van:

* `DatabarCols4.png` – 4 oszlop, 1 sor.  
* `DatabarRows3.png` – 1 oszlop, 3 sor.

Mindkét kép azonnal használatra készen áll alkalmazásokban, jelentésekben vagy nyomtatott címkéken.

## Hogyan generáljunk barcode PNG fájlokat C#‑ban egyedi méretekkel

A fenti minta bármely DataBar változathoz vagy a könyvtár által támogatott egyéb szimbólumokhoz újra felhasználható. Íme egy kompakt sablon, amelyet bemásolhat egy segédosztályba:

```csharp
public static void GenerateDatabar(string data, int columns = 1, int rows = 1, string outputPath = "output.png")
{
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, data);
    generator.Parameters.Barcode.DataBar.Columns = columns;
    generator.Parameters.Barcode.DataBar.Rows = rows;
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

A metódust így hívhatja meg:

```csharp
GenerateDatabar("1234567890123", columns: 4, outputPath: "DatabarCols4.png");
GenerateDatabar("1234567890123", rows: 3, outputPath: "DatabarRows3.png");
```

**Figyelembe veendő szélhelyzetek**

* **Data length** – A DataBar Expanded Stacked legfeljebb 74 numerikus karaktert kódolhat. Ennek a határnak a túllépése kivételt dob. Ellenőrizze a bemeneti hosszúságot a generátor meghívása előtt.  
* **Invalid dimensions** – A könyvtár az oszlopokat 1‑4, a sorokat 1‑3 közé korlátozza ennél a szimbólumnál. A tartományon kívüli értékek figyelmen kívül maradnak vagy hibát okoznak.  
* **Image DPI** – Ha nyomtatáshoz magasabb felbontásra van szüksége, állítsa be a `generator.Parameters.ImageResolution` értékét a mentés előtt.

## Várható kimenet

Amikor megnyitja a `DatabarCols4.png` vagy `DatabarRows3.png` fájlt, egy tiszta, nagy kontrasztú DataBar vonalkódot kell látnia. A képet GS1‑kompatibilis szkennerrel beolvasva visszakapja az eredeti szöveget: "Databar Expanded Stacked long".

![Minta DataBar Expanded Stacked vonalkód PNG‑ként mentve a barcode generator C# használatával](image.png)

*Alt text: Minta DataBar Expanded Stacked vonalkód PNG‑ként mentve a barcode generator C# használatával*

## Következtetés

Ez az útmutató bemutatta, hogyan használható egy **barcode generator C#** a **DataBar vonalkódok** létrehozására és **barcode PNG** fájlok generálására egyedi sor- és oszlopbeállításokkal. A hat lépés – a generátor inicializálása, oszlopok vagy sorok konfigurálása, és PNG‑ként mentés – követésével olyan gyártásra kész képeket kap, amelyek alkalmasak készletkezelő rendszerekhez, jegykezeléshez vagy bármely olyan helyzethez, ahol megbízható vonalkód-megjelenítésre van szükség.

Ezután érdemes felfedezni:

* Szín vagy háttérkép hozzáadása a PNG‑hez (még mindig kompatibilis a legtöbb szkennerrel).  
* Más szimbólumok, például QR, Code 128 vagy PDF417 használata ugyanazon `BarcodeGenerator` API‑val.  
* A generált PNG közvetlen beágyazása ASP.NET Core MVC nézetekbe vagy Blazor komponensekbe.

Nyugodtan kísérletezzen különböző adatkarakterláncokkal, méretekkel és képformátumokkal (pl. JPEG, BMP). Ugyanaz a minta alkalmazható, így a **barcode generator C#** sokoldalú eszköz minden .NET fejlesztő eszköztárában. Boldog kódolást!

## Mit érdemes legközelebb megtanulni?

A következő útmutatók szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsen elsajátítani további API‑funkciókat és alternatív megvalósítási megközelítéseket saját projektjeiben.

- [C# vonalkód generálása – DataBar vonalkód létrehozása](/barcode/english/python-java/general/generate-barcode-c-create-databar-barcode/)
- [Barcode Generator példa – DataBar kép építése C#‑ban](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [Barcode Generator példa C#‑ban – Oszlopok, sorok beállítása és kép exportálása](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
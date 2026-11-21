---
category: general
date: 2026-11-20
description: Készítsen postai vonalkód képet C#-ban gyorsan. Tanulja meg, hogyan generáljon
  planet vonalkódot és RM4SCC vonalkódokat testreszabható vonalstílusokkal.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- postal barcode C#
- Aspose.BarCode example
- barcode image generation
language: hu
lastmod: 2026-11-20
og_description: Készítsen postai vonalkód képet C#-ban az Aspose.BarCode segítségével.
  Ez az útmutató bemutatja, hogyan lehet generálni a planet vonalkódot, testreszabni
  a vonalstílusokat, és RM4SCC képeket előállítani.
og_image_alt: Create postal barcode image example showing filled and empty bars
og_title: Postai vonalkód kép létrehozása C#‑ban – lépésről lépésre útmutató
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Create postal barcode image in C# quickly. Learn how to generate planet
    barcode and RM4SCC barcodes with customizable bar styles.
  headline: Create postal barcode image and generate planet barcode
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Postai vonalkód kép létrehozása és bolygó vonalkód generálása
url: /hu/python-java/general/create-postal-barcode-image-and-generate-planet-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Postai vonalkód kép létrehozása és planet vonalkód generálása

Postai vonalkód képet hozunk létre C#-ban az Aspose.BarCode könyvtár segítségével. Ha planet vonalkódot vagy RM4SCC vonalkódokat kell generálnia levelezési alkalmazásokhoz, ez a bemutató egy teljes, azonnal futtatható megoldást nyújt.

A postai szolgáltatások számára vonalkódok generálása gyakran pontos méreteket és a kitöltött illetve üres sávstílusok közötti váltás lehetőségét igényli. Ez az útmutató végigvezeti a kimeneti mappa beállításán, a kitöltött és üres Planet vonalkódok létrehozásán, valamint egy RM4SCC vonalkód előállításán azonos vizuális beállításokkal. A végére négy PNG fájlt kap, amelyet közvetlenül felhasználhat a postai munkafolyamatában.

## Előfeltételek

Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik:

* .NET 6.0 vagy újabb telepítve  
* Visual Studio 2022 (vagy bármelyik kedvelt C# IDE)  
* A **Aspose.BarCode** NuGet csomag (`Install-Package Aspose.BarCode`)  

További konfiguráció nem szükséges; a kód csak az alapértelmezett betűtípust és PNG enkódert használ.

## Postai vonalkód kép létrehozása – áttekintés

A folyamat központja a `BarcodeGenerator` osztály. Egy `EncodeTypes` értéket fogad, amely meghatározza a vonalkód szimbólumát (például `EncodeTypes.Planet` a Planet vonalkódhoz). A generátor konfigurálása után a `Save` metódussal írja ki a képfájlt.

![Create postal barcode image example](/images/postal_barcode_example.png)

*Alt text: Postai vonalkód kép példája, amely kitöltött és üres sávokat mutat.*

## 1. lépés: Kimeneti mappa beállítása

Először határozzon meg egy mappát, ahová a PNG fájlok mentésre kerülnek. Az abszolút vagy relatív útvonal egyformán működik; csak győződjön meg róla, hogy a mappa létezik, vagy hagyja, hogy a kód létrehozza azt.

```csharp
using System.IO;
using Aspose.BarCode.Generation;

// Define the output folder (change to your own path)
string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
```

A mappa programozott létrehozása megakadályozza a `DirectoryNotFoundException` hibát, amikor a bemutató egy friss gépen fut.

## 2. lépés: Planet vonalkód generálása kitöltött sávokkal

A kitöltött sávú Planet vonalkód az alapértelmezett vizuális stílus. Az alábbi kód létrehozza a vonalkódot, a X‑dimenziót 4 pixelre állítja (a postai alkalmazásoknál gyakori méret), és elmenti a képet.

```csharp
// Step 2: Generate a Planet barcode with filled bars
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save as PNG
string planetFilledPath = Path.Combine(outputFolder, "PostalPlanetFilledBars.png");
planetFilled.Save(planetFilledPath, BarCodeImageFormat.Png);
```

**Miért működik ez:**  
* `EncodeTypes.Planet` azt mondja a generátornak, hogy a Planet szimbólumot használja, amelyet sok postai szolgáltatás megkövetel.  
* `XDimension.Pixels` szabályozza minden egyes sáv szélességét; 4 px tiszta, beolvasható képet eredményez túl nagy fájlméret nélkül.  
* A `Save` metódus automatikusan a PNG enkódert választja a `BarCodeImageFormat` enum alapján.

## 3. lépés: Planet vonalkód generálása üres sávokkal

Néhány postai specifikáció üres (fehér) sávokat preferál sötét háttéren. Ezt úgy érheti el, hogy a `FilledBars` értékét `false`‑ra állítja.

```csharp
// Step 3: Generate a Planet barcode with empty bars
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for consistency
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars – the bars become transparent (empty)
planetEmpty.Parameters.Barcode.FilledBars = false;

// Save the result
string planetEmptyPath = Path.Combine(outputFolder, "PostalPlanetEmptyBars.png");
planetEmpty.Save(planetEmptyPath, BarCodeImageFormat.Png);
```

**Tipp:** Ha a `FilledBars` `false`, a generátor a sávokat a háttérszínnel (alapértelmezés szerint fehér) festi, a szóközöket pedig az előtérszínnel (fekete). Ha más színsémára van szüksége, állítsa be a `Parameters.Barcode.ForeColor` és `BackColor` értékeket.

## 4. lépés: RM4SCC vonalkód generálása kitöltött sávokkal

Az RM4SCC egy másik postai szimbólum, amelyet az Egyesült Királyságban használnak. A létrehozási lépések a Planet példához hasonlóak; csak az `EncodeTypes` értéke változik.

```csharp
// Step 4: Generate an RM4SCC barcode with filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Reuse the same X‑dimension for a uniform look
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save the PNG file
string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png");
rm4sccFilled.Save(rm4sccPath, BarCodeImageFormat.Png);
```

**Mi várható:** A keletkezett PNG egy kompakt RM4SCC vonalkódot mutat, amely megfelel az UK postai irányelveknek. A képméret hasonló lesz a Planet vonalkódokhoz, mivel az X‑dimenzió azonos.

## 5. lépés: A generált képek ellenőrzése

A program futtatása után nyissa meg a négy fájlt a `Barcodes` mappában. A következőket kell látnia:

* `PostalPlanetFilledBars.png` – sötét sávok világos háttéren  
* `PostalPlanetEmptyBars.png` – világos sávok sötét háttéren (inverz)  
* `PostalRM4SCCFilledBars.png` – standard RM4SCC minta  

Ha bármelyik kép torzultnak tűnik, ellenőrizze a következőket:

* **X‑dimenzió** – túl kicsi (< 2 px) elmosódáshoz vezethet; túl nagy (> 10 px) meghaladhatja a címke méretkorlátait.  
* **Adatsor** – a `"123456"` értéknek meg kell felelnie a választott szimbólum hosszkövetelményeinek (Planet esetén 6 számjegy, RM4SCC esetén szintén 6 számjegy).  
* **Mappa jogosultságok** – győződjön meg róla, hogy az alkalmazásnak írási joga van a kimeneti könyvtárhoz.

## Gyakori variációk és szélsőséges esetek

| Forgatókönyv | Módosítás |
|--------------|-----------|
| **Eltérő vonalkód adat** | Cserélje a `"123456"` értéket bármely érvényes numerikus karakterláncra. Planet esetén a hossznak pontosan 6 számjegynek kell lennie; az RM4SCC is 6 számjegyet igényel. |
| **Egyedi színek** | `planetFilled.Parameters.Barcode.ForeColor = System.Drawing.Color.DarkBlue;` és `BackColor = System.Drawing.Color.LightYellow;`. |
| **Magasabb felbontás** | Növelje a `XDimension.Pixels` értékét 6-ra vagy 8-ra a nagyobb nyomatokhoz. |
| **Egyéb képformátumok** | Használja a `BarCodeImageFormat.Jpeg` vagy `BarCodeImageFormat.Bmp` értéket a `Save` hívásban. |
| **Kötegelt generálás** | Iteráljon egy karakterlánc-gyűjteményen, és hívja meg ugyanazt a generátorlogikát a cikluson belül, újra felhasználva az `outputFolder` útvonalat. |

## Teljes, futtatható példa

Másolja az alábbi kódot egy új C# konzolprojektbe. .NET 6.0-val fordítható, és automatikusan előállítja mind a négy vonalkód képet.



## Mit érdemes legközelebb megtanulni?

Az alábbi bemutatók szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsen elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeiben.

- [Hogyan hozzunk létre postai vonalkód képet egyedi magasságokkal C#-ban](/barcode/english/python-java/general/how-to-create-postal-barcode-image-with-custom-heights-in-c/)
- [Hogyan hozzunk létre RM4SCC vonalkódot és generáljunk planet vonalkódot C#-ban](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-generate-planet-barcode-in/)
- [Postai vonalkód kép létrehozása C#-ban – lépésről‑lépésre útmutató](/barcode/english/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
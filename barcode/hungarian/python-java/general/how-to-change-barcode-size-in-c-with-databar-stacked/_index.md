---
category: general
date: 2026-08-22
description: Hogyan változtassuk meg a vonalkód méretét C#-ban a DataBar Stacked Omni‑Directional
  generátor használatával. Tanulja meg beállítani az X‑dimenziót és az arányt a PNG
  kimenethez.
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
language: hu
lastmod: 2026-08-22
og_description: Hogyan változtathatja meg a vonalkód méretét C#‑ban a DataBar Stacked
  Omni‑Directional generátorral. Kövesse a lépésről‑lépésre útmutatót az X‑dimenzió
  és az oldalarány beállításához.
og_image_alt: Screenshot showing how to change barcode size in C#
og_title: Hogyan változtassuk meg a vonalkód méretét C#-ban – teljes útmutató
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
title: Hogyan változtassuk meg a vonalkód méretét C#‑ban a DataBar Stacked használatával
url: /hu/python-java/general/how-to-change-barcode-size-in-c-with-databar-stacked/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan változtassuk meg a vonalkód méretét C#‑ban a DataBar Stacked használatával

Ha .NET alkalmazásban **hogyan változtassuk meg a vonalkód méretét**‑re van szüksége, ez az útmutató bemutatja a pontos lépéseket a DataBar Stacked Omni‑Directional vonalkód generátor használatával. Megmutatjuk, hogyan szabályozhatja az X‑dimenziót pixelben, állíthatja a vonalkód képarányát, és mentheti az eredményt PNG fájlként.

A vonalkód méretének módosítása gyakran szükséges, ha a nyomtatott címke helye korlátozott, vagy ha digitális csatornákhoz nagy felbontású képre van szükség. Ez a tutorial mindent lefed, ami szükséges, az inicializálástól a két különböző méretű kép előállításáig.

## Előfeltételek

Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik:

* .NET 6.0 SDK vagy újabb telepítve  
* Hivatkozás a **Aspose.BarCode for .NET** NuGet csomagra  
* Alapvető C# szintaxis ismeretekkel  

Nem szükséges további konfiguráció; a kód Windows, Linux vagy macOS rendszeren is fut.

## Hogyan változtassuk meg a vonalkód méretét C#‑ban – lépésről lépésre

Az alábbi szakaszok a folyamatot önálló, újrahasználható lépésekre bontják. Minden lépés elmagyarázza, **miért** szükséges a kód, nem csak **mit** csinál.

### 1. lépés: DataBar Stacked Omni‑Directional vonalkód generátor létrehozása

A generátor objektum tárolja az összes vonalkód beállítást. Az `EncodeTypes.DatabarStackedOmniDirectional` és egy minta adat átadásával egy érvényes vonalkódot hoz létre, amely későbbi testreszabásra készen áll.

```csharp
// Step 1: Create a DataBar Stacked Omni‑Directional barcode generator with sample data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

*Miért fontos* – A **C# barcode generator** osztály magába foglalja a kódolási algoritmust. Egy érvényes generátorral kezdve biztosítható, hogy a későbbi méretváltoztatások a megfelelő vonalkódtípusra hatnak.

### 2. lépés: Az alapmodul méretének (X‑dimenzió) beállítása pixelben

Az X‑dimenzió egyetlen vonalkód modul szélességét határozza meg. Ennek módosítása arányosan változtatja a teljes szélességet és magasságot.

```csharp
// Step 2: Define the basic module size (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Miért fontos* – A nagyobb X‑dimenzió nagyobb vonalkódot eredményez, ami alacsony felbontású nyomtatók esetén hasznos. Ezzel szemben egy kisebb érték kompakt vonalkódot hoz létre, amely kis címkékre alkalmas.

### 3. lépés: A vonalkód képarányának 15‑re állítása és a kép mentése

A **barcode aspect ratio** szabályozza a magasság‑szélesség arányt. A 15‑ös képarány viszonylag magas vonalkódot eredményez.

```csharp
// Step 3: Set the DataBar aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

*Miért fontos* – Különböző olvasóeszközöknek optimális képarány‑követelményeik vannak. A 15‑ös arány beállítása bemutatja, hogyan **hogyan változtassuk meg a vonalkód méretét** a magasság módosításával, miközben a szélesség az X‑dimenzió által van meghatározva.

#### Várt kimenet

A `DatabarAspectRatio15.png` fájl egy DataBar Stacked Omni‑Directional vonalkódot mutat, amely magasabb az alapértelmezettnél. A vonalkód szélessége a 2‑pixel X‑dimenziót tükrözi, a magasság pedig a 15‑ös arányt követi.

### 4. lépés: A vonalkód képarányának 30‑ra állítása és az új kép mentése

A képarány 30‑ra növelése még magasabb vonalkódot eredményez, bemutatva a méretállítás rugalmasságát.

```csharp
// Step 4: Change the DataBar aspect ratio to 30 and save the new image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

*Miért fontos* – A **barcode aspect ratio** értékének cseréjével azonnal látható, hogyan **hogyan változtassuk meg a vonalkód méretét** anélkül, hogy újra kellene hozni a generátort. Ez időt takarít meg kötegelt feldolgozás esetén.

#### Várt kimenet

A `DatabarAspectRatio30.png` fájl nyilvánvalóan magasabb, mint az előző kép, ami megerősíti, hogy a képarány közvetlenül befolyásolja a vonalkód magasságát.

### 5. lépés: A generált képek ellenőrzése

Nyissa meg a PNG fájlokat bármely képmegjelenítőben. Két vonalkódot kell látnia azonos szélességgel (az X‑dimenzió által vezérelve), de különböző magasságokkal (a képarány által). Ha a képek elmosódottak, növelje az X‑dimenzió pixel értékét; ha túl magasak, csökkentse a képarányt.

```csharp
// Optional verification code – load images and print dimensions
using (var img15 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio15.png"))
using (var img30 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio30.png"))
{
    Console.WriteLine($"15‑ratio size: {img15.Width}×{img15.Height}");
    Console.WriteLine($"30‑ratio size: {img30.Width}×{img30.Height}");
}
```

*Miért fontos* – A programozott ellenőrzés biztosítja, hogy a méretváltoztatások helyesen alkalmazásra kerültek, ami elengedhetetlen az automatizált build folyamatokban.

## Gyakori variációk és szélhelyzetek

| Szituáció | Módosítás | Ok |
|-----------|------------|--------|
| **Nagyon kis címkék** | Állítsa be `XDimension.Pixels = 1` és `AspectRatio = 10` | Csökkenti az összméretet, miközben megőrzi az olvashatóságot |
| **Nagy felbontású nyomtatás** | Állítsa be `XDimension.Pixels = 4` és `AspectRatio = 20` | Növeli a pixel sűrűséget a tiszta kimenethez |
| **Eltérő képformátum** | Cserélje le `BarCodeImageFormat.Png`‑t `BarCodeImageFormat.Jpeg`‑re | Hasznos, ha a PNG támogatás korlátozott |
| **Dinamikus adatok** | Adjon át egy változó stringet a `BarcodeGenerator` konstruktorának | Automatikusan generál vonalkódot minden termékhez |

Amikor sok vonalkódot kell előállítani változó méretekkel, csomagolja a lépéseket egy metódusba:

```csharp
void GenerateDatabar(string data, int xDim, int aspectRatio, string filePath)
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
    generator.Parameters.Barcode.XDimension.Pixels = xDim;
    generator.Parameters.Barcode.DataBar.AspectRatio = aspectRatio;
    generator.Save(filePath, BarCodeImageFormat.Png);
}
```

A `GenerateDatabar("(01)98765432109876", 3, 25, "output.png")` hívás egy egyedi méretű vonalkódot hoz létre egyetlen kódsorban.

## Pro tippek a megbízható méretváltoztatáshoz

* **Mindig az X‑dimenziót állítsa be a képarány előtt.** A képarány előbb történő módosítása váratlan skálázáshoz vezethet, ha az X‑dimenzió alapértelmezett értéke nem ideális.  
* **Használjon konzisztens kimeneti mappát.** A `"YOUR_DIRECTORY"` keménykódolása demókhoz működik, de éles környezetben inkább a `Path.Combine(Environment.CurrentDirectory, "Barcodes")` megoldást javasoljuk.  
* **Ellenőrizze a generált kép méretét.** Az X‑dimenzióban bekövetkező kis változások a képernyőn nem feltétlenül láthatók; a pixelméretek ellenőrzése garantálja, hogy a változtatás életbe lépett.  

## Összegzés

Most már tudja, **hogyan változtassuk meg a vonalkód méretét** C#‑ban a DataBar Stacked Omni‑Directional vonalkód generátor használatával. Az **X‑dimension pixel** és a **barcode aspect ratio** beállításával PNG képeket hozhat létre, amelyek bármilyen címkemérethez vagy felbontási követelményhez illeszkednek. A fenti, teljesen futtatható példa bemutatja a teljes munkafolyamatot a generátor létrehozásától a méretellenőrzésig.

### Mit érdemes még felfedezni

* **Egyedi színek** – kísérletezzen a `barcodeGenerator.Parameters.Barcode.ForeColor` és `BackColor` beállításokkal a márka irányelveinek megfelelően.  
* **Eltérő vonalkódtípusok** – cserélje le az `EncodeTypes.DatabarStackedOmniDirectional`‑t `EncodeTypes.QR` vagy `EncodeTypes.Code128`‑ra, hogy lássa, hogyan különböznek a méretparaméterek a szimbólumok között.  
* **Kötegelt feldolgozás** – kombinálja a `GenerateDatabar` metódust egy CSV importtal, hogy automatikusan több ezer vonalkódot hozzon létre.

Nyugodtan igazítsa a kódrészleteket saját projektjének architektúrájához, és engedje, hogy a vonalkód méretállítások javítsák a beolvasási megbízhatóságot és a vizuális megjelenést. Boldog kódolást!

## Mit érdemes legközelebb megtanulni?

Az alábbi tutorialok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódrészletet tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsen elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket saját projektjeiben.

- [How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
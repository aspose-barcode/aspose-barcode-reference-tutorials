---
title: Kiegészítő vonalkód adatok létrehozása az Aspose.BarCode segítségével .NET-hez
linktitle: Kiegészítő vonalkód adatkonfiguráció
second_title: Aspose.BarCode .NET API
description: Hozzon létre kiegészítő vonalkód adatokat az Aspose.BarCode for .NET segítségével. Az EAN-2 és EAN-5 vonalkódok könnyedén testreszabhatók. Lépésről lépésre útmutató .NET fejlesztőknek.
type: docs
weight: 10
url: /hu/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
---

A vonalkód generálás és testreszabás világában az Aspose.BarCode for .NET hatékony és sokoldalú eszközként tűnik ki. Akár tapasztalt fejlesztő, akár csak most kezdi, ez a lépésről lépésre végigvezeti Önt a kiegészítő vonalkódadatok konfigurálásán az Aspose.BarCode for .NET használatával. 

## Előfeltételek

Mielőtt belevetnénk magunkat a kiegészítő vonalkódadatok világába, győződjön meg arról, hogy a következő előfeltételeket teljesíti:

- Visual Studióval vagy bármely más .NET fejlesztőeszközzel beállított fejlesztői környezet.
-  Az Aspose.BarCode másolata .NET-hez. Ha még nem tette meg, letöltheti[itt](https://releases.aspose.com/barcode/net/).
- C# programozási alapismeretek.
- Egy könyvtár, ahová elmentheti a generált vonalkód képeket.

## Névterek importálása

Először is győződjön meg arról, hogy a C# kódban szerepelnek a szükséges névterek az Aspose.BarCode for .NET használatához. Importálja a szükséges névtereket a C# fájl elejére:

```csharp
using Aspose.BarCode.Generation;
```

Most bontsuk le több lépésre a kiegészítő vonalkódadatok konfigurálásának folyamatát.

## 1. lépés: A címtár elérési útjának beállítása

 A C# kódban adja meg annak a könyvtárnak az elérési útját, ahová menteni szeretné a generált vonalkód képeket. Cserélje ki`"Your Directory Path"` a tényleges könyvtár elérési útjával.

```csharp
string path = "Your Directory Path";
```

## 2. lépés: Vonalkód-generátor létrehozása

 Hozzon létre egy példányt a`BarcodeGenerator` a vonalkód típusának és a kódolni kívánt adatok megadásával. Ebben a példában egy EAN-13 vonalkódot használunk „1234567890128” adattal.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

## 3. lépés: A vonalkód méreteinek testreszabása

Állítsa be a vonalkód méreteit, például az X méretet (a vonalkód legkisebb elemének szélessége) és a kiegészítő helyet. Ebben a példában az X dimenziót 2 képpontra, a kiegészítő teret pedig 20 képpontra állítjuk be.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

## 4. lépés: Az EAN-2 kiegészítés konfigurálása

Az EAN-2 kiegészítő vonalkód konfigurálásához állítsa be a kiegészítő adatokat a kívánt értékre. Ebben az esetben "12"-re állítjuk. 

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

## 5. lépés: A vonalkód kép mentése

Mentse el a generált vonalkód képet a megadott könyvtárba értelmes névvel. Ebben a példában az EAN-2 kiegészítő vonalkódot "SupplementEAN2.png" néven mentjük el.

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

## 6. lépés: Az EAN-5 kiegészítés konfigurálása

 Az EAN-5 kiegészítő vonalkód konfigurálásához egyszerűen módosítsa a`SupplementData` a kívánt értékre. Itt „12345”-re állítottuk.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

## 7. lépés: A vonalkód kép mentése (EAN-5)

Végül mentse el az EAN-5 kiegészítő vonalkódképet a megadott könyvtárba. Ebben az esetben "SupplementEAN5.png" néven mentjük el.

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

Sikeresen konfigurálta és létrehozta a kiegészítő vonalkódadatokat az Aspose.BarCode for .NET használatával. Ezzel a megközelítéssel számos vonalkódtípust hozhat létre változó kiegészítő adatokkal.

## Következtetés

Az Aspose.BarCode for .NET egy hatékony eszköz a vonalkód generálására és testreszabására. Ebben az útmutatóban lépésről lépésre végigjártuk a kiegészítő vonalkód adatok konfigurálásának és generálásának folyamatát. A megfelelő előfeltételekkel és egy kis kódolással hatékonyan dolgozhat vonalkódadatokkal, és megfelelhet egyedi igényeinek.

 További információkért és a speciális használatért tekintse meg a[Aspose.BarCode a .NET dokumentációhoz](https://reference.aspose.com/barcode/net/).

## Gyakran Ismételt Kérdések

### Használhatom az Aspose.BarCode for .NET fájlt a .NET Core projektemben?
Igen, az Aspose.BarCode for .NET kompatibilis a .NET Core-al.

### Létezik ingyenes próbaverzió az Aspose.BarCode for .NET számára?
 Igen, ingyenesen kipróbálhatja, ha ellátogat[ez a link](https://releases.aspose.com/).

### Hol szerezhetek ideiglenes licencet az Aspose.BarCode .NET-hez?
 Ideiglenes jogosítványt szerezhet be[ez a link](https://purchase.aspose.com/temporary-license/).

### Támogatja az Aspose.BarCode a vonalkódtípusok széles skáláját?
Igen, különféle vonalkód-típusokat támogat, beleértve az EAN-13-at, a QR-kódot, a 128-as kódot stb.

### Testreszabhatom a generált vonalkódok megjelenését?
Természetesen testreszabhatja a vonalkódok méreteit, színeit és egyéb jellemzőit, hogy megfeleljen az Ön igényeinek.

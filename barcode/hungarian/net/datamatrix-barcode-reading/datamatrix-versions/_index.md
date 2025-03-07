---
title: Generáljon DataMatrix vonalkódokat az Aspose.BarCode segítségével .NET-hez
linktitle: DataMatrix verziók
second_title: Aspose.BarCode .NET API
description: Ismerje meg, hogyan hozhat létre DataMatrix vonalkódokat .NET-ben az Aspose.BarCode for .NET használatával. Egyéni méretek, ECC-támogatás és még sok más.
weight: 12
url: /hu/net/datamatrix-barcode-reading/datamatrix-versions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generáljon DataMatrix vonalkódokat az Aspose.BarCode segítségével .NET-hez

Ha megbízható megoldást keres DataMatrix vonalkódok generálására .NET-alkalmazásaiban, az Aspose.BarCode for .NET a megfelelő út. Ebben a lépésenkénti útmutatóban végigvezetjük az Aspose.BarCode for .NET használatán DataMatrix vonalkódok létrehozásához. Az egyes példákat több lépésre bontjuk, így biztosítva, hogy Ön könnyedén követhesse.

## Előfeltételek

Mielőtt belemerülnénk a kódba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
- Fejlesztői környezet .NET támogatással.
-  A .NET-hez készült Aspose.BarCode másolata, amelyről letölthető[ez a link](https://releases.aspose.com/barcode/net/).
- C# és .NET keretrendszer alapismeretei.

Most pedig nézzük meg a DataMatrix verzióit, és azt, hogyan hozhatjuk létre azokat az Aspose.BarCode for .NET használatával.

## Névterek importálása

Minden C# projektben elengedhetetlen a szükséges névterek importálása. Az Aspose.BarCode esetében a következőket kell megadnia:

```csharp
using Aspose.BarCode.Generation;
```

 Ez a névtér hozzáférést biztosít a`BarcodeGenerator` osztály, ami döntő fontosságú a vonalkódok generálásához.

Most bontsuk fel a példát több lépésre.

## 1. lépés: Állítsa be a címtár elérési útját

Kezdje a könyvtár elérési útjának meghatározásával, ahová menteni szeretné a generált DataMatrix vonalkódokat.

```csharp
string path = "Your Directory Path";
```

 Cserélje ki`"Your Directory Path"` azzal a tényleges elérési úttal, ahová a vonalkód képeket menteni szeretné.

## 2. lépés: Inicializálja a Vonalkód-generátort

 Hozzon létre egy példányt a`BarcodeGenerator` osztályt, és adja meg a vonalkód típusát mint`DataMatrix`. A kódolni kívánt adatokat a vonalkódon belül is megadhatja.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // A vonalkód generálására szolgáló kód itt található
}
```

## 3. lépés: Állítsa be a vonalkód tulajdonságait

Testreszabhatja a DataMatrix vonalkód különféle tulajdonságait, például a méreteit és az ECC (Error Correction Code) típusát. Íme egy példa az X-dimenzió 4 pixeles beállítására és az ECC200 kiválasztására:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4;
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

## 4. lépés: Állítsa be a DataMatrix verziót és Mentse

A DataMatrix verzióját a sorok és oszlopok számának beállításával adhatja meg. A verzió konfigurálása után mentse el a vonalkód képet.

Például 22 sorból és 22 oszlopból álló DataMatrix vonalkód létrehozásához az ECC200 használatával:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC200_22x22;
generator.Save($"{path}DataMatrixRows22Columns22Ecc200.png", BarCodeImageFormat.Png);
```

Hasonlóképpen, a verzió és az ECC típus igény szerinti módosításával különböző paraméterekkel állíthat elő vonalkódot.

## 5. lépés: Ismételje meg a többi verzióhoz is

A 4. lépést megismételheti más DataMatrix verziókhoz is. Például 12 sorból és 64 oszlopból álló vonalkód létrehozásához az ECC200 használatával:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.DMRE_12x64;
generator.Save($"{path}DataMatrixRows12Columns64Ecc200.png", BarCodeImageFormat.Png);
```

## 6. lépés: ECC típusok váltása

Ha az ECC típusát Ecc140-re szeretné módosítani, ezt az ECC tulajdonság frissítésével teheti meg:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;
```

## 7. lépés: Vonalkódok létrehozása különböző verziókkal és ECC-vel

Ismételje meg a 4. lépést a többi DataMatrix verzióhoz és ECC-típushoz, és minden vonalkódot egyedi fájlnévvel ment el.

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC000_140_29x29;
generator.Save($"{path}DataMatrixRows29Columns29Ecc140.png", BarCodeImageFormat.Png);
```

Most, hogy megtanulta, hogyan hozhat létre DataMatrix vonalkódokat az Aspose.BarCode for .NET használatával, könnyen integrálhatja ezt a funkciót .NET-alkalmazásaiba.

## Következtetés

Az Aspose.BarCode for .NET leegyszerűsíti a DataMatrix vonalkódok létrehozásának folyamatát a .NET-alkalmazásokban. Ezzel a lépésenkénti útmutatóval különböző verziójú és ECC-típusú vonalkódokat hozhat létre, amelyek rugalmasságot és testreszabást kínálnak az Ön egyedi igényeinek megfelelően.

 Ha bármilyen kérdése van, vagy segítségre van szüksége, ne habozzon felkeresni a[Aspose.BarCode a .NET dokumentációhoz](https://reference.aspose.com/barcode/net/) vagy nézd meg a[Aspose.BarCode fórum](https://forum.aspose.com/c/barcode/13) támogatásért.

## GYIK

### 1. kérdés: Mi az ECC a DataMatrix vonalkódokban?

1. válasz: Az ECC (Error Correction Code) a DataMatrix vonalkódok létfontosságú összetevője, amely segít biztosítani az adatok integritását. A különböző ECC szintek különböző mértékű hibajavítást tesznek lehetővé.

### 2. kérdés: Létrehozhatok-e DataMatrix vonalkódokat egyéni méretekkel az Aspose.BarCode for .NET használatával?

2. válasz: Igen, testreszabhatja a DataMatrix vonalkódok méreteit a sorok és oszlopok számának beállításával az oktatóanyagban bemutatott módon.

### 3. kérdés: Honnan tölthetem le az Aspose.BarCode-ot .NET-hez?

 3. válasz: Az Aspose.BarCode for .NET innen letölthető[ez a link](https://releases.aspose.com/barcode/net/).

### 4. kérdés: Elérhető ingyenes próbaverzió az Aspose.BarCode for .NET számára?

 4. válasz: Igen, hozzáférhet az Aspose.BarCode ingyenes próbaverziójához a .NET-hez[itt](https://releases.aspose.com/).

### 5. kérdés: Hogyan szerezhetek ideiglenes licencet az Aspose.BarCode for .NET számára?

 5. válasz: A .NET Aspose.BarCode ideiglenes licencének beszerzéséhez látogasson el a következő oldalra[ez a link](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

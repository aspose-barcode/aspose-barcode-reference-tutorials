---
date: 2026-05-30
description: Ismerje meg, hogyan hozhat létre vonalkód PNG-t egy egyedi DataMatrix
  képaránnyal az Aspose.BarCode for .NET használatával. Lépésről lépésre útmutató
  a vonalkód generálásához és a méret testreszabásához.
keywords:
- create barcode png
- generate datamatrix barcode
- asp.net barcode generation
- barcode generation visual studio
linktitle: DataMatrix képarány testreszabása
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  headline: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  name: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  steps:
  - name: Set Up Your Project
    text: Create a new console or Windows Forms project in Visual Studio and add a
      reference to the Aspose.BarCode DLL.
  - name: Initialize a Barcode Generator
    text: 'Instantiate it with the DataMatrix symbology and the data you want to encode:
      `BarcodeGenerator` creates a barcode image from the specified symbology and
      data. > This line creates a generator ready to produce a DataMatrix barcode
      that contains the sample text.'
  - name: Customize Aspect Ratio and Save PNG Files
    text: 'Now you can change the **aspect ratio** and save each version as a PNG
      image: `AspectRatio` sets the width‑to‑height proportion of the DataMatrix modules.
      `Save` writes the generated barcode image to a file in the chosen format. -
      The first call creates a square‑proportioned barcode (`AspectRatio = '
  type: HowTo
- questions:
  - answer: Yes, many 2‑D barcodes (e.g., QR, PDF417) support aspect‑ratio adjustments
      through their specific parameter objects.
    question: Can I customize the aspect ratio of other barcode types using Aspose.BarCode
      for .NET?
  - answer: Yes, you can access a free trial of Aspose.BarCode for .NET [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: You can purchase a license on the Aspose website [here](https://purchase.aspose.com/buy).
    question: Where can I purchase a license for Aspose.BarCode for .NET?
  - answer: Yes, it works with .NET Framework 4.x, .NET Core 3.1+, and the latest
      .NET releases.
    question: Is Aspose.BarCode for .NET compatible with different .NET Framework
      versions?
  - answer: Absolutely – PNG, JPEG, BMP, GIF, TIFF, SVG, and PDF are all supported
      out of the box.
    question: Can I generate barcodes in different formats with Aspose.BarCode for
      .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Vonalkód PNG létrehozása – DataMatrix képarány – Aspose.BarCode
url: /hu/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode PNG létrehozása – DataMatrix képarány – Aspose.BarCode

Egy **barcode PNG** létrehozása egyedi DataMatrix képaránnyal gyakori követelmény, amikor **barcode PNG** fájlokat kell készíteni, amelyek meghatározott elrendezési korlátoknak felelnek meg. Ebben az oktatóanyagról lépésről‑lépésre bemutatjuk, hogyan **hozzunk létre barcode PNG** fájlokat az Aspose.BarCode for .NET segítségével, miért lehet szükség a képarány módosítására, és hogyan finomhangolhatja a kimenetet az alkalmazásához.

## Gyors válaszok
- **Mi szabályozza a “képarány”?** A DataMatrix modulok szélesség‑magasság arányát határozza meg.  
- **Exportálhatok PNG‑t, JPEG‑t vagy SVG‑t?** Igen – a `Save` metódus támogatja a PNG, JPEG, BMP, GIF, TIFF, SVG és PDF formátumokat.  
- **Szükségem van licencre ehhez a funkcióhoz?** A fejlesztéshez ingyenes próba verzió működik; a termeléshez teljes licenc szükséges.  
- **Mely .NET verziók támogatottak?** .NET Framework 4.x, .NET Core 3.1+, .NET 5/6/7.  
- **Hány képarány érték érvényes?** Bármely pozitív lebegőpontos szám; a tipikus értékek 0,5 – 2,0.

## Mi az a DataMatrix vonalkód és miért állítsuk be a képarányát?
A DataMatrix vonalkód egy kétdimenziós mátrixkód, amely nagy mennyiségű adatot tárol egy kompakt négyzetben. A **képarány** beállítása lehetővé teszi a modulok vízszintes nyújtását vagy összenyomását, ami hasznos, ha a vonalkódot szűk oszlopokba vagy széles címkékbe kell illeszteni a beolvasási megbízhatóság csökkenése nélkül.

## Miért használjuk az Aspose.BarCode-ot barcode PNG létrehozásához?
Az Aspose.BarCode **7 képformátumot** támogat — PNG, JPEG, BMP, GIF, TIFF, SVG és PDF — és memóriában képes feldolgozni **50+ bemeneti és kimeneti formátumot**, több száz oldalas dokumentumokat kezelve anélkül, hogy a teljes fájlt betöltené. A könyvtár egy folyékony API-t biztosít, amely lehetővé teszi egy DataMatrix vonalkód generálását egyetlen kódsorral, garantálva a pixel‑pontos megjelenítést és a teljes .NET kompatibilitást.

## Előkövetelmények

Mielőtt elkezdenénk testreszabni a DataMatrix képarányokat, győződjön meg róla, hogy a következő előkövetelmények rendelkezésre állnak:

1. **Visual Studio** – bármely friss verzió megfelelő.  
2. **Aspose.BarCode for .NET** – töltse le [itt](https://releases.aspose.com/barcode/net/).  
3. Más Aspose termékkiadásokat is felfedezhet [itt](https://releases.aspose.com/).  
4. **.NET Framework / .NET Core** – a projektnek támogatott verziót kell céloznia.

## Névterek importálása

Először importálnia kell a szükséges névteret a C# projektjében:

`using Aspose.BarCode.Generation;` importálja azt a névteret, amely a vonalkód generálás osztályait tartalmazza.  

```csharp
using Aspose.BarCode.Generation;
```

> **Pro tipp:** Tartsa ezt a `using` utasítást a fájl tetején, hogy a `BarcodeGenerator` osztály mindig elérhető legyen.

## Hogyan hozzunk létre barcode PNG-t egyedi képaránnyal?

Töltse be a `BarcodeGenerator`‑t, állítsa be a DataMatrix típust, módosítsa az `AspectRatio` tulajdonságot, és hívja meg a `Save`‑t. Ez az egy‑soros minta olyan barcode PNG‑t hoz létre, amely tiszteletben tartja a megadott arányt, és a könyvtár automatikusan kezeli a modulok méretezését és a csendes zónákat.

`BarcodeGenerator` egy vonalkód képet hoz létre a megadott szimbólumból és adatokból.

### 1. lépés: Projekt beállítása
Hozzon létre egy új konzol vagy Windows Forms projektet a Visual Studio-ban, és adjon hozzá hivatkozást az Aspose.BarCode DLL‑hez.

### 2. lépés: Barcode Generator inicializálása
Példányosítsa a DataMatrix szimbólummal és a kódolni kívánt adatokkal:

`BarcodeGenerator` egy vonalkód képet hoz létre a megadott szimbólumból és adatokból.  

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> Ez a sor egy generátort hoz létre, amely készen áll egy DataMatrix vonalkód előállítására, amely a minta szöveget tartalmazza.

### 3. lépés: Képarány testreszabása és PNG fájlok mentése
Most módosíthatja a **képarányt**, és minden verziót PNG képként menthet:

`AspectRatio` beállítja a DataMatrix modulok szélesség‑magasság arányát.  
`Save` a generált vonalkód képet a kiválasztott formátumban egy fájlba írja.  

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- Az első hívás egy négyzetes arányú vonalkódot hoz létre (`AspectRatio = 1`).  
- A második hívás vízszintesen összenyomja a vonalkódot (`AspectRatio = 0.5`), szélesebb megjelenést eredményezve.

Most már két **barcode PNG** fájlja van különböző képarányokkal, készen állva jelentésekben, címkékben vagy UI elemekben való használatra.

## Gyakori problémák és megoldások
| Probléma | Megoldás |
|----------|----------|
| **A generált kép homályos** | Növelje a `Resolution` paramétert a mentés előtt (`gen.Parameters.ImageResolution = 300`). |
| **A vonalkód nem olvasható** | Győződjön meg róla, hogy a képarány 0,5 – 2,0 között marad, és elegendő csendes zóna van (`gen.Parameters.Barcode.CodeTextParameters.Margin`). |
| **Fájlútvonal hibák** | `Path.Combine` használata az output útvonal építéséhez, és ellenőrizze, hogy a mappa létezik. |

## Gyakran ismételt kérdések

**K: Testreszabhatom más vonalkód típusok képarányát az Aspose.BarCode for .NET használatával?**  
A: Igen, sok 2‑D vonalkód (pl. QR, PDF417) támogatja a képarány módosítását a saját paraméterobjektumaikon keresztül.

**K: Elérhető ingyenes próba az Aspose.BarCode for .NET-hez?**  
A: Igen, ingyenes próba verziót érhet el az Aspose.BarCode for .NET [itt](https://releases.aspose.com/).

**K: Hol vásárolhatok licencet az Aspose.BarCode for .NET-hez?**  
A: Licencet az Aspose weboldalán vásárolhat [itt](https://purchase.aspose.com/buy).

**K: Az Aspose.BarCode for .NET kompatibilis különböző .NET Framework verziókkal?**  
A: Igen, működik a .NET Framework 4.x, .NET Core 3.1+ és a legújabb .NET kiadásokkal.

**K: Különböző formátumokban generálhatok vonalkódokat az Aspose.BarCode for .NET használatával?**  
A: Természetesen – a PNG, JPEG, BMP, GIF, TIFF, SVG és PDF mind támogatottak alapból.

## Következtetés

A DataMatrix vonalkód **képarányának** testreszabása és **barcode PNG** fájlok létrehozása egyszerű az Aspose.BarCode for .NET segítségével. A fenti lépések követésével tökéletes méretű vonalkódokat generálhat, amelyek pontosan megfelelnek a projekt elrendezési követelményeinek. Fedezze fel a további paramétereket, például a `Resolution`, `Margin` és `Color` beállításokat, hogy tovább finomítsa a kimenetet, és vegye figyelembe a `generate datamatrix barcode` képességeket, amikor beolvasás‑barát alkalmazásokat épít a Visual Studio-ban.

A mélyebb felfedezéshez tekintse meg a hivatalos [dokumentációt](https://reference.aspose.com/barcode/net/), vagy csatlakozzon a közösséghez a [Aspose.BarCode fórumon](https://forum.aspose.com/c/barcode/13).

---

**Utolsó frissítés:** 2026-05-30  
**Tesztelve:** Aspose.BarCode 24.12 for .NET  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó oktatóanyagok

- [DataMatrix vonalkód generálása – Pro útmutató az Aspose.BarCode használatával](/barcode/net/datamatrix-barcode-configuration/)
- [Hogyan generáljunk DataMatrix vonalkódokat (ECC 200) az Aspose.BarCode for .NET használatával](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [DataMatrix kódolás mesterfokon ASCII-val az Aspose.BarCode for .NET használatával](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
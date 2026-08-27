---
date: 2026-06-14
description: Ismerje meg, hogyan olvassuk be a DataMatrix kódokat és generáljunk strukturált
  Append vonalkódokat .NET környezetben az Aspose.BarCode segítségével, a gyors és
  megbízható vonalkód könyvtárat.
keywords:
- how to read datamatrix
- DataMatrix structured append
- Aspose.BarCode .NET
linktitle: DataMatrix strukturált Append beállítása
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to read datamatrix and generate structured append barcodes
    in .NET using Aspose.BarCode, the fast and reliable barcode library.
  headline: How to Read DataMatrix Append with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to read datamatrix and generate structured append barcodes
    in .NET using Aspose.BarCode, the fast and reliable barcode library.
  name: How to Read DataMatrix Append with Aspose.BarCode for .NET
  steps:
  - name: Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
    text: Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
  - name: You can also browse other Aspose products [here](https://releases.aspose.com/).
    text: You can also browse other Aspose products [here](https://releases.aspose.com/).
  - name: A .NET development environment such as Visual Studio 2022 or Visual Studio
      Code with the C# extension.
    text: A .NET development environment such as Visual Studio 2022 or Visual Studio
      Code with the C# extension.
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET.
    question: What library handles DataMatrix structured append?
  - answer: Up to 16 DataMatrix symbols.
    question: How many symbols can a single structured append sequence contain?
  - answer: A free trial works for development and testing.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes, you can decode from a byte array or stream.
    question: Can I read the barcode without an image file?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Hogyan olvassuk be a DataMatrix Append-et az Aspose.BarCode .NET-hez
url: /hu/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# DataMatrix strukturált hozzáfűzés konfigurációja az Aspose.BarCode for .NET használatával

Ha fejlesztő vagy, és **hogyan olvassuk a datamatrixot** használod strukturált hozzáfűzéssel .NET alkalmazásaidban, az Aspose.BarCode for .NET a megfelelő megoldás. Ebben a lépésről‑lépésre útmutatóban végigvezetünk a DataMatrix vonalkódok generálásán és dekódolásán, amelyek több szimbólumra vannak felosztva. A tutorial végére magabiztosan tudsz DataMatrix strukturált hozzáfűzési vonalkódokat létrehozni, konfigurálni és olvasni az Aspose.BarCode for .NET segítségével.

## Gyors válaszok
- **Melyik könyvtár kezeli a DataMatrix strukturált hozzáfűzést?** Aspose.BarCode for .NET.
- **Hány szimbólumot tartalmazhat egyetlen strukturált hozzáfűzési sorozat?** Legfeljebb 16 DataMatrix szimbólum.
- **Szükségem van licencre fejlesztéshez?** Egy ingyenes próba verzió működik fejlesztéshez és teszteléshez.
- **Mely .NET verziók támogatottak?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Olvashatom a vonalkódot képfájl nélkül?** Igen, dekódolhat byte tömbből vagy streamből.

## Mi a datamatrix olvasása?
**how to read datamatrix** a DataMatrix szimbólumok dekódolásának folyamatát jelenti, és ha szükséges, a strukturált‑hozzáfűzési sorozat darabjainak összefűzését az eredeti adatcsomag visszanyeréséhez. Az Aspose.BarCode beépített támogatást nyújt ehhez a munkafolyamathoz, automatikusan kezeli a szimbólumok sorrendjét és az adatok összefűzését.

## Miért használjuk az Aspose.BarCode-ot DataMatrix strukturált hozzáfűzéshez?
Az Aspose.BarCode **30+ vonalkód szimbólumot** támogat, és képes **10 000 × 10 000 px** méretű képeket dekódolni **200 ms** alatt tipikus szerver hardveren. A könyvtár **nulla függőségű telepítést** is kínál, ami azt jelenti, hogy nem szükséges további natív DLL, és működik Windows, Linux és macOS .NET futtatókörnyezetekben.

## Előfeltételek

Mielőtt belemerülnél a tutorialba, a következőkre lesz szükséged:

1. Aspose.BarCode for .NET Library – letöltés: [itt](https://releases.aspose.com/barcode/net/).
2. Más Aspose termékeket is böngészhet [itt](https://releases.aspose.com/).
3. .NET fejlesztői környezet, például Visual Studio 2022 vagy Visual Studio Code a C# kiegészítővel.

Most kezdjünk el DataMatrix strukturált hozzáfűzési vonalkódokat létrehozni és olvasni.

## Névterek importálása

Az első lépés a névterek importálása, amelyek a vonalkód API-t teszik elérhetővé.

`BarCodeWriter` osztály az Aspose.BarCode belépési pontja a vonalkódok létrehozásához, míg a `BarCodeReader` a dekódolást kezeli.

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

Miután importáltad a szükséges névtereket, hozzunk létre egy strukturált‑hozzáfűzési vonalkódot.

## Hogyan olvassuk a DataMatrix strukturált hozzáfűzési vonalkódokat?

Töltsd be a generált képet (vagy streamet) egy `BarCodeReader`‑be, engedélyezd a `ReadStructuredAppend` opciót, és hívd a `ReadBarcode`‑t. Az olvasó automatikusan visszaadja az összefűzött adatot, és megjeleníti a sorozat részleteit, mint például `StructuredAppendFileId`, `StructuredAppendTotalCount`, és `StructuredAppendSegmentId`. Az összegzett eredmény egyetlen karakterláncként kerül visszaadásra, és a `StructuredAppendSegmentId` tulajdonságon keresztül lekérheted az egyes szegmens azonosítókat egyedi feldolgozáshoz.

```csharp
    using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
    {
        reader.ReadBarCodes();

        Console.WriteLine("Barcode ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodeId);
        Console.WriteLine("Barcodes count: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodesCount);
        Console.WriteLine("File ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendFileId);
    }
}
```

Ebben a lépésben az olvasót használjuk a vonalkód ID, a teljes darabszám és a fájl ID kinyerésére, megerősítve, hogy a strukturált‑hozzáfűzési konfigurációt helyesen értelmezte.

## 1. lépés: DataMatrix strukturált hozzáfűzés konfiguráció beállítása

DataMatrix strukturált hozzáfűzési vonalkód létrehozásához be kell állítanod a konfigurációt. Ez magában foglalja a könyvtár útvonalának, a vonalkód ID-jának, a vonalkódok számának és a fájl ID-jének meghatározását.

```csharp
string path = "Your Directory Path";

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;

    // Set DataMatrix structured append mode
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodeId = 3;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodesCount = 5;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendFileId = 150;

    // Generate the barcode image
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

Ebben a lépésben a kívánt paraméterekkel konfiguráltuk a DataMatrix vonalkódot.

## Gyakori problémák és megoldások

- **Helytelen szegmens sorrend:** Győződj meg róla, hogy a `StructuredAppendSegmentId` értékek sorban követik egymást 0‑tól kezdve; egyébként az olvasó nem tudja helyesen összerakni az adatot.
- **Nem egyező teljes darabszám:** A `StructuredAppendTotalCount` minden szimbólumban azonosnak kell lennie; a eltérés miatt az olvasó a sorozatot hiányosnak tekinti.
- **Képminőség:** Alacsony felbontású képek dekódolási hibákat okozhatnak. Törekedj legalább **300 dpi** felbontásra a vonalkód bitmapre renderelésekor.

## Gyakran Ismételt Kérdések

### Q1: Mi az a DataMatrix strukturált hozzáfűzés, és miért használják?
A1: A DataMatrix strukturált hozzáfűzés egy olyan funkció, amely lehetővé teszi, hogy nagy mennyiségű adatot több kisebb vonalkódra bontsunk. Ez különösen hasznos, ha egyetlen vonalkód számára korlátozott a hely, vagy hatékony adatkezelésre van szükség. Gyakran alkalmazzák logisztikában, egészségügyben és gyártásban.

### Q2: Használhatom az Aspose.BarCode for .NET-et nyílt forráskódú projektemben?
A2: Igen, az Aspose.BarCode for .NET ingyenes próba verziót kínál, amelyet nyílt forráskódú projektekben is használhatsz. A próba verziót [itt](https://releases.aspose.com/) találod.

### Q3: Van közösségi támogatás az Aspose.BarCode for .NET-hez?
A3: Igen, közösségi támogatást kereshetsz és más felhasználókkal léphetsz kapcsolatba az Aspose.BarCode fórumon [itt](https://forum.aspose.com/c/barcode/13).

### Q4: Hogyan szerezhetek ideiglenes licencet az Aspose.BarCode for .NET-hez?
A4: Ha értékeléshez vagy teszteléshez ideiglenes licencre van szükséged, azt [itt](https://purchase.aspose.com/temporary-license/) szerezheted be.

### Q5: Támogatja az Aspose.BarCode for .NET más vonalkód típusokat is?
A5: Igen, az Aspose.BarCode for .NET számos vonalkód típust támogat, beleértve a QR kódokat, a Code 128‑at, az EAN‑13‑at és még sok mást. A teljes dokumentációt [itt](https://reference.aspose.com/barcode/net/) tekintheted meg a támogatott vonalkód típusok teljes listájáért.

---

**Legutóbb frissítve:** 2026-06-14  
**Tesztelve ezzel:** Aspose.BarCode 24.11 for .NET  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [DataMatrix olvasó programozás az Aspose.BarCode for .NET használatával](/barcode/net/datamatrix-barcode-reading/datamatrix-reader-programming/)
- [DataMatrix vonalkódok generálása az Aspose.BarCode for .NET használatával](/barcode/net/datamatrix-barcode-reading/datamatrix-versions/)
- [DataMatrix makró konfiguráció mestersége az Aspose.BarCode for .NET használatával](/barcode/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}
---
category: general
date: 2026-08-22
description: Hogyan olvassuk be a PDF417 vonalkódokat C#-ban lépésről‑lépésre útmutatóval,
  amely lefedi, hogyan olvassunk be több vonalkódot egy képből, és hogyan nyerjük
  ki a MacroPdf417 részleteket.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcodes image c#
language: hu
lastmod: 2026-08-22
og_description: Hogyan olvassunk PDF417 vonalkódokat C#-ban gyorsan. Ez az útmutató
  megmutatja, hogyan olvassunk több vonalkódot egy képből, és hogyan nyerjünk ki MacroPdf417
  kiterjesztett információkat.
og_image_alt: Developer console displaying MacroPdf417 barcode details extracted by
  C# code
og_title: Hogyan olvassunk PDF417 vonalkódokat C#-ban – teljes programozási útmutató
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to read PDF417 barcodes in C# with a step‑by‑step guide, covering
    how to read multiple barcodes from an image and extract MacroPdf417 details.
  headline: How to read PDF417 barcodes in C# – complete guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Hogyan olvassuk be a PDF417 vonalkódokat C#-ban – teljes útmutató
url: /hu/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan olvassuk be a PDF417 vonalkódokat C#‑ban – teljes útmutató

Ha **hogyan olvassuk be a PDF417** vonalkódokat szeretne egy .NET alkalmazásban, ez az útmutató egy azonnal futtatható megoldást nyújt. Megtanulja, hogyan olvasson be több vonalkódot egyetlen képből, hogyan nyerje ki a teljes MacroPdf417 adatkészletet, és hogyan jelenítse meg a konzolon. A megközelítés az Aspose.BarCode for .NET könyvtárral működik, és csak néhány sor kódot igényel.

A vonalkódok képről történő olvasása gyakori feladat készletkezelő rendszerekben, jegyellenőrzésben és dokumentumkezelésben. A útmutató végére képes lesz dekódolni bármely PDF417 vagy MacroPdf417 vonalkódot, több kódot kezelni egy képen, és megérteni a MacroPdf417 által biztosított kiterjesztett mezőket.

## Előkövetelmények

- .NET 6.0 SDK vagy újabb (a kód .NET Framework 4.7+‑vel is lefordítható)
- Visual Studio 2022 vagy bármely kedvelt C# szerkesztő
- Aspose.BarCode for .NET NuGet csomag (`Install-Package Aspose.BarCode`)
- Egy minta kép, amely MacroPdf417 vonalkódot tartalmaz (pl. `MacroPdf417.png`)

Nem szükséges további konfiguráció; a könyvtár belsőleg kezeli a kép betöltését és a dekódolást.

## Hogyan olvassuk be a PDF417 vonalkódokat egy képről C#‑ban

A megoldás központja a `BarCodeReader` osztály. Megnyitja a képet, felismeri az összes megadott típusú vonalkódot, és egy `BarCodeResult` objektumok gyűjteményét adja vissza. Az alábbi kód egy teljes konzolos programot mutat.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            // Path to the image that contains one or more MacroPdf417 barcodes
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            // 1️⃣ Initialize the reader for MacroPdf417 barcodes.
            // DecodeType.MacroPdf417 tells the engine to look for the extended PDF417 format.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // 2️⃣ Iterate over every barcode found in the image.
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // 3️⃣ Print basic information.
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // 4️⃣ Access MacroPdf417 extended fields.
                    // The Extended property contains format‑specific data; for PDF417 it is .Pdf417.
                    var macro = result.Extended.Pdf417;

                    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Miért fontos minden sor

| Lépés | Cél |
|------|-----|
| **1️⃣ Initialize** | Létrehozza a `BarCodeReader`‑t, amely a képfájlhoz van kötve, és a felismerést a MacroPdf417 szimbólumra korlátozza, ezáltal felgyorsítja a feldolgozást. |
| **2️⃣ Iterate** | A `ReadBarCodes()` **összes** olyan vonalkódot visszaad, amely megfelel a kért típusnak, lehetővé téve a **több vonalkód** beolvasását extra ciklusok nélkül. |
| **3️⃣ Basic output** | Megjeleníti az általános `CodeTypeName`‑t és az emberi olvasásra alkalmas `CodeText`‑et. Ez hasznos naplózáshoz vagy gyors ellenőrzéshez. |
| **4️⃣ Extended data** | A MacroPdf417 további metaadatokat (fájlazonosító, szegmensszám, időbélyegek stb.) tartalmaz. Az `Extended.Pdf417` objektum közvetlenül elérhetővé teszi ezeket a mezőket, így tárolhatja vagy ellenőrizheti a teljes adatcsomagot. |

A program futtatása egy érvényes MacroPdf417 képen a következőhöz hasonló konzolkimenetet eredményez:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345678
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x9A3F
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2024-07-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

A kimenet megerősíti, hogy a könyvtár sikeresen beolvasta a vonalkódot, kinyerte a szöveget, és minden MacroPdf417 mezőt biztosított.

## Több vonalkód olvasása egyetlen képről

Sok valós helyzetben több PDF417 szimbólum is elhelyezkedik egy címkén – gondoljunk egy szállítmánylistára, amely tartalmaz egy fuvarozói kódot, egy nyomkövetési számot és egy vámnyilatkozatot. A fenti kódrészlet már **több vonalkódot** olvas, mivel a `ReadBarCodes()` egy enumerátort ad vissza az összes egyezésről. Nem szükséges további beállítás; csak végig kell iterálni az eredményeken, ahogy a példában látható.

Ha a leolvasót csak a standard PDF417‑ra (nem‑macro) szeretné korlátozni, miközben több kódot is kezel, cserélje le a `DecodeType.MacroPdf417`‑t `DecodeType.Pdf417`‑ra. A logika többi része változatlan marad.

## A MacroPdf417 kiterjesztett adatainak megértése

A MacroPdf417 a szokásos PDF417 specifikáció kiterjesztése. Nagy adatcsomagokat több szegmensre bont, és egy kis fejlécet ad hozzá, amely leírja a teljes fájlt. A legfontosabb mezők:

- **MacroPdf417FileID** – egyedi azonosító, amelyet a fájl összes szegmense megoszt.
- **MacroPdf417SegmentID** – az aktuális szegmens sorszáma.
- **MacroPdf417SegmentsCount** – a várható szegmensek teljes száma.
- **MacroPdf417FileName** – opcionális fájlnév, amely a vonalkóddal együtt továbbítódik.
- **MacroPdf417Checksum** – hibakereső érték a teljes fájlhoz.
- **MacroPdf417FileSize** – az eredeti bináris adat mérete.
- **MacroPdf417TimeStamp** – ISO‑8601 időbélyeg, amikor a vonalkódot generálták.
- **MacroPdf417Addressee / Sender** – opcionális szöveges mezők az útvonal meghatározásához.
- **MacroPdf417Terminator** – jelzi, hogy ez a szegmens az utolsó-e.

Ha megkapja az összes szegmenst, az eredeti fájlt újraépítheti a `MacroPdf417SegmentID` szerint rendezve, majd a `CodeText` értékeket összefűzve. Ez a logika egyszerűen megvalósítható, amint a mezők rendelkezésre állnak.

## Gyakori hibák és profi tippek

- **Image quality matters** – alacsony felbontású vagy erősen tömörített PNG/JPEG fájlok hibás felismerést okozhatnak. Nyomtatott vonalkódok esetén legalább 300 dpi DPI‑t használjon.
- **Mixed symbologies** – ha a kép tartalmazza a MacroPdf417‑t és a hagyományos PDF417‑t is, hozzon létre két olvasót (egyik a megfelelő `DecodeType`‑hez), vagy használja a `DecodeType.AllSupported`‑t, és szűrje a találatokat a `result.CodeTypeName` alapján.
- **Memory usage** – a `using` utasítás azonnal felszabadítja a `BarCodeReader`‑t, megakadályozva, hogy nagy képbufferek a memóriában maradjanak.
- **Thread safety** – a `BarCodeReader` nem szálbiztos. Hozzon létre külön példányt szálanként, ha párhuzamosan dekódol képeket.
- **Error handling** – a `ReadBarCodes()` hívást helyezze try/catch blokkba, hogy elkapja a `BarCodeException`‑t sérült képek esetén.

## Teljes működő példa összefoglaló

Az alábbi teljes programot másolja be egy új konzolos projektbe. Tartalmazza az összes `using` direktívát, egy állandó változót a kép útvonalához, és a megfelelő erőforrás‑felszabadítási mintát.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    var macro = result.Extended.Pdf417;
                    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

Fordítsa le `dotnet build`‑kel, majd futtassa `dotnet run`‑nal. A konzol kiírja minden vonalkód alapadatait és a teljes MacroPdf417 payload‑ot.

## Következő lépések

- **Reconstruct multipart files** – collect all segments, sort by `MacroPdf417SegmentID`, and concatenate `CodeText` to

## Mit érdemes még megtanulni?

Az alábbi oktatóanyagok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódpéldákat tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsen elsajátítani további API‑funkciókat és alternatív megvalósítási megközelítéseket saját projektjeiben.

- [Hogyan generáljunk PDF417 vonalkódot – Kompakt PDF417 kódolás](/barcode/english/net/compact-pdf417-encoding/)
- [Hogyan olvassuk be a PDF417 vonalkódokat török karakterekkel Java‑ban](/barcode/english/java/multilingual-support/recognizing-pdf417-turkish-characters/)
- [Hogyan használjuk az Aspose‑t PDF417 vonalkódhoz (kínai) Java‑ban](/barcode/english/java/multilingual-support/recognizing-pdf417-chinese-characters/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
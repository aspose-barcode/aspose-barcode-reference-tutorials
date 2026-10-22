---
category: general
date: 2026-10-21
description: Generálj pdf417 vonalkódot gyorsan C#-ban. Tanulj meg pdf417 vonalkódot
  generálni egyedi elrendezéssel, oszlopokkal, sorokkal és PNG kimenettel.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- pdf417 barcode layout
- barcode generator C#
- save barcode as PNG
language: hu
lastmod: 2026-10-21
og_description: PDF417 vonalkód generálása C#-ban. Kövesd ezt az útmutatót, hogy megtanuld,
  hogyan generálj PDF417 vonalkódot egyéni oszlopokkal, sorokkal és PNG kimenettel.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: PDF417 vonalkód generálása C#‑ban – teljes lépésről‑lépésre útmutató
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  headline: Generate pdf417 barcode in C# with custom columns and rows
  type: TechArticle
- description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  name: Generate pdf417 barcode in C# with custom columns and rows
  steps:
  - name: Open the PNG file in any image viewer.
    text: Open the PNG file in any image viewer.
  - name: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
    text: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
  - name: Confirm that the decoded text matches the original input.
    text: Confirm that the decoded text matches the original input.
  type: HowTo
tags:
- barcode
- pdf417
- C#
- image generation
title: PDF417 vonalkód generálása C#-ban egyedi oszlopokkal és sorokkal
url: /hu/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-with-custom-columns-and-rows/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# pdf417 vonalkód generálása C#-ban – teljes programozási útmutató

Ha **pdf417 vonalkódot** kell generálnia egy .NET alkalmazásban, ez az útmutató megmutatja, hogyan teheti ezt néhány kódsorral. Egy gyakorlati példát láthat, amely beállítja az oszlopok és sorok számát, majd PNG képként menti az eredményt. Ugyanaz a megközelítés bármilyen kódolni kívánt szövegre alkalmazható, így számlákhoz, jegyekhez vagy személyi igazolványokhoz is adaptálható.

A **pdf417 vonalkód** generálása gyakran úgy tűnik, mintha a kódbázis többi részétől külön feladat lenne. A tutorial végére megérti, miért fontosak a layout paraméterek, hogyan szabályozhatja a képminőséget, és mely könyvtári hívások szükségesek a **pdf417 vonalkód** megbízható generálásához.

## Amire szüksége lesz

* .NET 6.0 SDK vagy újabb telepítve  
* C#‑kompatibilis IDE (Visual Studio, VS Code, Rider, stb.)  
* A **Aspose.BarCode for .NET** NuGet csomag (vagy bármely kompatibilis vonalkód könyvtár)  

You can add the library with the following command:

```bash
dotnet add package Aspose.BarCode
```

A könyvtár biztosítja a `BarcodeGenerator` osztályt, amelyet a tutorial során használunk.

## 1. lépés: Barcode generátor példány létrehozása

Az első sor egy olyan objektumot hoz létre, amely tud **pdf417 vonalkódot** generálni. Meg kell adnia a kódolás típusát (`EncodeTypes.Pdf417`) és a kódolni kívánt szöveget.

```csharp
using Aspose.BarCode.Generation;

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample Text");
```

*Miért fontos ez a lépés* – A `BarcodeGenerator` tartalmazza a vonalkód összes beállítását. A megfelelő `EncodeTypes` értékkel történő példányosítás azt mondja a motornak, hogy a PDF417 szimbólumot használja a QR, Code128 vagy más formátumok helyett.

## 2. lépés: PDF417 elrendezés beállítása

A PDF417 lehetővé teszi az oszlopok és sorok számának szabályozását, ami közvetlenül befolyásolja a vonalkód méretét és sűrűségét. Ezeknek az értékeknek a módosítása a **pdf417 vonalkód egyedi elrendezéssel történő generálásának** központja.

```csharp
// Set the number of data columns (valid range: 2‑30)
generator.Parameters.Barcode.Pdf417.Columns = 4;

// Set the number of rows (up to 90 rows)
generator.Parameters.Barcode.Pdf417.Rows = 9;
```

*Miért módosíthatja ezeket az értékeket* – Több oszlop csökkenti a vonalkód magasságát, míg több sor növeli a szélességet. Válasszon olyan értékeket, amelyek illeszkednek a célzott szkennerhez és a rendelkezésre álló nyomtatási területhez.

> **Pro tipp:** Ha kihagyja a sorokat, a könyvtár automatikusan kiszámítja az optimális számot az adat hosszának alapján. A sorok explicit megadása akkor hasznos, ha rögzített képméretre van szükség UI elrendezésekhez.

## 3. lépés: Képkép formátum kiválasztása és fájl mentése

Az elrendezés beállítása után a vonalkódot képként renderelheti. Az alábbi példa PNG fájlként menti a vonalkódot, de választhat JPEG, BMP vagy TIFF formátumot is.

```csharp
using Aspose.BarCode;
using System.IO;

// Define the output path – replace with your actual directory
string outputPath = Path.Combine("C:\\Barcodes", "CustomLayout.png");

// Save the barcode image as PNG
generator.Save(outputPath, BarCodeImageFormat.Png);
```

A kód futtatásakor a `CustomLayout.png` egy tiszta **pdf417 vonalkódot** tartalmaz majd, amely megfelel a megadott oszlop/sor beállításoknak.

### Várt kimenet

A `CustomLayout.png` megnyitása egy négyszögletes vonalkódot mutat négy adatoszloppal és kilenc sorral. A kép bármely PDF417 olvasóval történő beolvasása visszaadja az eredeti **„Sample Text”** szöveget.

![Generated PDF417 barcode example](generated-pdf417.png){: .center-image alt="Generált pdf417 vonalkód PNG fájlként mentve"}

## 4. lépés: Teljes, futtatható példa

Az alábbi önálló konzolalkalmazás összeállítja az összes részt. Másolja a kódot egy új `.csproj` projektbe, és futtassa – nincs szükség további fájlokra.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample Text for PDF417 barcode");

            // 2️⃣ Configure layout – custom columns and rows
            generator.Parameters.Barcode.Pdf417.Columns = 4; // 2‑30
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // up to 90

            // Optional: increase image resolution for sharper output
            generator.Parameters.ImageResolution = 300; // DPI

            // 3️⃣ Define the output location
            string folder = Path.Combine(Environment.CurrentDirectory, "output");
            Directory.CreateDirectory(folder);
            string filePath = Path.Combine(folder, "CustomLayout.png");

            // 4️⃣ Save as PNG
            generator.Save(filePath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode generated at: {filePath}");
        }
    }
}
```

A program futtatása egy megerősítő sort ír ki, és létrehozza a PNG fájlt egy `output` almappában. A kép beágyazható jelentésekbe, nyomtatható címkékre, vagy elküldhető mobil eszközre beolvasás céljából.

## Gyakori variációk és szélsőséges esetek

| Forgatókönyv | Mit kell módosítani | Miért fontos |
|----------|----------------|----------------|
| **Hosszú karakterlánc kódolása** | Növelje a `Rows` értékét, vagy hagyja, hogy a könyvtár automatikusan kiszámítsa a `Rows` hozzárendelés elhagyásával | A PDF417 akár 1 850 karaktert is tárolhat; a sorok hiánya csonkításhoz vezet |
| **Magasabb vizuális minőség** | Állítsa a `generator.Parameters.ImageResolution` értékét 600 DPI-re | Hasznos nagy felbontású nyomtatókhoz |
| **Eltérő képfájl formátum** | Cserélje a `BarCodeImageFormat.Png`-t `Jpeg` vagy `Tiff`-re | A JPEG csökkenti a fájlméretet; a TIFF veszteségmentes adatot őriz archiváláshoz |
| **Csendes zóna hozzáadása** | `generator.Parameters.Barcode.XDimension = 2;` (vagy állítsa be a `Margins`-t) | A csendes zónák javítják a szkenner megbízhatóságát zajos környezetben |
| **Dinamikus szöveg felhasználói bemenetről** | Cserélje a keménykódolt stringet `Console.ReadLine()`-re | Lehetővé teszi a futásidőben történő generálást felhasználói adatok alapján |

### Hogyan generáljunk pdf417 vonalkódot web API-ban

Ha a vonalkód generálást ASP.NET Core végponton keresztül szeretné elérhetővé tenni, adja vissza a képet bájt tömbként:

```csharp
[HttpGet("api/barcode/pdf417")]
public IActionResult GetPdf417([FromQuery] string data)
{
    var generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
    generator.Parameters.Barcode.Pdf417.Columns = 5;
    generator.Parameters.Barcode.Pdf417.Rows = 10;

    using var ms = new MemoryStream();
    generator.Save(ms, BarCodeImageFormat.Png);
    return File(ms.ToArray(), "image/png");
}
```

Ez a kódrészlet megválaszolja, hogyan **pdf417 vonalkódot** generálhatunk futás közben lemezre írás nélkül, ami ideális mikro-szolgáltatások vagy mobil háttéralkalmazások számára.

## A generált vonalkód tesztelése

A vonalkód helyes létrehozásának ellenőrzéséhez:

1. Nyissa meg a PNG fájlt bármely képnézőben.  
2. Használjon ingyenes PDF417 szkenner alkalmazást (pl. ZXing, PDF417 Decoder) a kép beolvasásához.  
3. Ellenőrizze, hogy a dekódolt szöveg megegyezik az eredeti bemenettel.

Ha a szkenner hibákat jelent, ellenőrizze újra az oszlop/sor értékeket, és győződjön meg róla, hogy a képfelbontás elég magas a készülékéhez.

## Következtetés

Most már tudja, hogyan **pdf417 vonalkódot** generáljon C#-ban, teljes kontrollal az oszlopok, sorok és a kimeneti formátum felett. A teljes példa bemutatja az egész munkafolyamatot – a `BarcodeGenerator` létrehozásától a PNG fájl mentéséig – így beépítheti a vonalkód létrehozását bármely .NET projektbe.

Ezután fedezze fel a kapcsolódó témákat, például a **pdf417 vonalkód elrendezés** optimalizálását, vonalkódok beágyazását PDF jelentésekbe, vagy a vonalkódok dekódolását mobil eszközökön. A hibajavítási szintek beállítása és a különböző képfelbontások kipróbálása segít finomhangolni a megoldást az Ön konkrét felhasználási esetére. Jó kódolást!

## Mit érdemes legközelebb megtanulni?

Az alábbi tutorialok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódpéldákat tartalmaz lépésről‑lépésre magyarázatokkal, hogy elsajátíthassa a további API funkciókat és alternatív megvalósítási megközelítéseket saját projektjeiben.

- [Hogyan generáljunk PDF417 vonalkódot C#‑ban – lépésről‑lépésre útmutató](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [Hogyan mentsünk vonalkódot C#‑ban – PDF417 vonalkódok generálása](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Hogyan generáljunk PDF417 vonalkódot – teljes programozási útmutató](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
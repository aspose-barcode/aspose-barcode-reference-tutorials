---
category: general
date: 2026-10-15
description: Készítsen vonalkód PNG-t C#-ban egy kompakt PDF417 példával – tanulja
  meg, hogyan állíthatja be az oszlopokat, módosíthatja a méreteket, és generálhatja
  a képet.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to create barcode
- how to set columns
- c# barcode example
language: hu
lastmod: 2026-10-15
og_description: Készítsen vonalkód PNG-t C#-ban egy kompakt PDF417 példával. Ez az
  útmutató bemutatja, hogyan állíthatja be az oszlopokat, módosíthatja a méreteket,
  és mentheti a képet.
og_image_alt: Screenshot showing a generated barcode PNG created with C#
og_title: Barcode PNG létrehozása C#‑ban – teljes programozási útmutató
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  headline: How to create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  name: How to create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: Initialise the barcode generator with the desired text
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: Set the module (X) dimension in pixels
    text: '```csharp // Set the width of the smallest bar (module) to 2 pixels generator.Parameters.Barcode.XDimension.Pixels
      = 2; ```'
  - name: Define the number of columns for the PDF417 barcode
    text: '```csharp // Specify that the barcode should use 3 columns generator.Parameters.Barcode.Pdf417.Columns
      = 3; ```'
  - name: Enable the compact layout by truncating the barcode
    text: '```csharp // Truncate removes unnecessary empty rows, making the barcode
      shorter generator.Parameters.Barcode.Pdf417.Truncate = true; ```'
  - name: Save the barcode image as PNG
    text: '```csharp // Choose the output folder and file name string outputPath =
      Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");'
  - name: Full, runnable example
    text: 'Putting everything together, here is a self‑contained program you can copy,
      paste, and run:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: Hogyan készítsünk vonalkód PNG-t C#-ban – lépésről lépésre útmutató
url: /hu/net/compact-pdf417-encoding/how-to-create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan készítsünk vonalkód PNG-t C#‑ban – lépésről‑lépésre útmutató

Ha **vonalkód PNG** fájlokat kell létrehoznod C# kódból, ez a tutorial néhány sorban bemutat egy teljes megoldást. Megmutatjuk, hogyan állítsd be az oszlopokat, módosítsd a modulméretet, és ments egy kompakt PDF417 vonalkódot PNG képként – mindezt egyetlen, könnyen érthető példával.

Programozott vonalkód-generálás eltávolítja a grafikus szerkesztő kézi használatát, és lehetővé teszi, hogy a vonalkódokat közvetlenül számlákba, jegyekbe vagy készletcímkékbe ágyazd. Az alábbi szakaszokban mindent lefedünk, amit a **vonalkód képek létrehozásához** tudnod kell, miért fontos minden beállítás, és hogyan igazíthatod a kódot különböző felhasználási esetekhez.

## Előkövetelmények

* .NET 6.0 vagy újabb (a kód .NET Framework 4.7+‑vel is működik)
* Egy hivatkozás egy PDF417-et támogató vonalkód könyvtárra, például **Aspose.BarCode for .NET** vagy **IronBarcode**. A példa az Aspose.BarCode‑ot használja, amelyet a NuGet‑en keresztül telepíthetsz:

```bash
dotnet add package Aspose.BarCode
```

* Alapvető ismeretek a C# szintaxisról és a Visual Studio‑ról (vagy bármely általad preferált IDE‑ról).

> **Pro tipp:** Ha ingyenes alternatívát részesítesz előnyben, a nyílt forráskódú **ZXing.Net** könyvtár is támogatja a PDF417‑et, bár a tulajdonságnevek kissé eltérnek. Az itt bemutatott koncepciók ugyanazok maradnak.

## Hogyan készítsünk vonalkód PNG-t C#‑ban (elsődleges lépés)

A megoldás központja egy `BarcodeGenerator` objektum, amely PDF417 kódolásra van konfigurálva. Az alábbi szakaszok részletezik a kód minden sorát, elmagyarázzák, **hogyan állítsuk be az oszlopokat**, és megmutatják, miért befolyásolják a beállítások a végső PNG méretét.

### 1. lépés: A vonalkódgenerátor inicializálása a kívánt szöveggel

```csharp
using Aspose.BarCode.Generation;

// The text you want to encode in the barcode
string barcodeText = "Compact example";

// Create a generator for PDF417 barcodes
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
{
    // Subsequent configuration goes here
}
```

*Miért fontos*: Az `EncodeTypes.Pdf417` enum azt mondja a könyvtárnak, hogy egy kétdimenziós, egymásra rakott vonalkódot állítson elő. A konstruktor egyben elfogadja a kódolni kívánt adatot, így nincs szükség külön `SetData` hívásra.

### 2. lépés: A modul (X) dimenzió beállítása pixelben

```csharp
// Set the width of the smallest bar (module) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Az **X dimenzió** szabályozza a vonalkód vizuális sűrűségét. A kisebb érték szorosabb képet eredményez, ami akkor hasznos, ha mobil képernyőkhöz vagy korlátozott nyomtatási helyhez kell egy kompakt PNG‑t.

### 3. lépés: A PDF417 vonalkód oszlopainak számának meghatározása

```csharp
// Specify that the barcode should use 3 columns
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

Ez a sor bemutatja, **hogyan állítsuk be az oszlopokat**. A PDF417 automatikusan kiválaszthatja az optimális oszlopszámot, de a kézi beállítás előre meghatározható szélességet biztosít, különösen, ha a PNG‑t rögzített méretű elrendezésbe ágyazod.

### 4. lépés: A kompakt elrendezés engedélyezése a vonalkód csonkításával

```csharp
// Truncate removes unnecessary empty rows, making the barcode shorter
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

Ha a `Truncate` igaz, a könyvtár eltávolítja az adatot nem tartalmazó sorokat, ezáltal csökkentve a kép teljes magasságát információvesztés nélkül.

### 5. lépés: A vonalkód kép mentése PNG‑ként

```csharp
// Choose the output folder and file name
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");

// Save the generated barcode as a PNG file
generator.Save(outputPath, BarCodeImageFormat.Png);
```

A `Save` metódus a megadott formátumban írja a vonalkódot a lemezre. A PNG veszteségmentes, így ideális a pontos élkiemelést igénylő szkennelési alkalmazásokhoz.

### Teljes, futtatható példa

Mindent összevonva, itt egy önálló program, amelyet másolhatsz, beilleszthetsz és futtathatsz:

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise the generator with the data to encode
        string barcodeText = "Compact example";

        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
        {
            // 2️⃣ Set module width to 2 pixels for a tighter image
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Explicitly set the number of columns (how to set columns)
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Enable compact layout by truncating empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define the output path and save as PNG (create barcode PNG)
            string outputPath = Path.Combine(Directory.GetCurrentDirectory(), "CompactPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode PNG saved to: {outputPath}");
        }
    }
}
```

**Várható kimenet** – A program futtatása után a `CompactPdf417.png` fájlt megtalálod a végrehajtási mappában. A kép egy háromoszlopos PDF417 vonalkódot tartalmaz, amely elég kompakt ahhoz, hogy egy szabványos 2 × 2 cm-es címkén elférjen, miközben teljesen beolvasható marad.

![Vonalkód PNG létrehozása példa](placeholder.png){alt="Vonalkód PNG létrehozása C#‑ban"}

## Hogyan állítsuk be az oszlopokat különböző adatméretekhez (másodlagos kulcsszó)

Az oszlopok száma befolyásolja a vonalkód szélességét és olvashatóságát is:

| Oszlopok | Kb. szélesség (px) | Tipikus felhasználás |
|----------|-------------------|----------------------|
| 1‑2      | Keskeny, magas    | Kis címkék, RFID‑szerű nyomatok |
| 3‑5      | Kiegyensúlyozott  | Általános célú címkék |
| 6‑9      | Széles, alacsony  | Nagy poszterek vagy csomagolás |

Ha az adatkarakterlánc hosszabb lesz, a könyvtár automatikusan növelheti a sorok számát, hogy a vonalkód a megadott oszlopszámon belül maradjon. Azonban ha túl alacsony oszlopszámot kényszerítesz, a vonalkód túl magas lesz, ami nem fér el egy nyugtanyomtatón. Az oszlopszámot a kimeneti közeg fizikai korlátaihoz igazítsd.

## Hogyan készítsünk vonalkód képeket más formátumokban (másodlagos kulcsszó)

Míg a PNG a leggyakoribb formátum a weben és mobilon, előfordulhat, hogy **vonalkód képeket kell létrehoznod** JPEG, BMP vagy SVG formátumban speciális munkafolyamatokhoz:

```csharp
// Save as JPEG with 90 % quality
generator.Save("CompactPdf417.jpg", BarCodeImageFormat.Jpeg, 90);

// Save as SVG (vector, infinite scaling)
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

A megfelelő formátum kiválasztása a downstream fogyasztótól függ:

* **PNG** – veszteségmentes, ideális a szkennerek számára.
* **JPEG** – kisebb fájlméret, elfogadható, ha enyhe tömörítési hibák tolerálhatók.
* **SVG** – tökéletes nagy felbontású nyomtatáshoz vagy UI skálázáshoz.

## C# vonalkód példa: hibakezelés és szélsőséges esetek

Egy robusztus **c# vonalkód példa** előre fel kell, hogy lássa a futásidejű problémákat:

```csharp
try
{
    // All configuration steps as shown earlier
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode parameter: {ex.Message}");
}
catch (IOException ex)
{
    Console.Error.WriteLine($"Failed to write file: {ex.Message}");
}
```

*Miért csomagold `try/catch`‑be?* Érvénytelen karakterek a szövegben, nem támogatott dimenziók vagy írási jogosultsági problémák kivételt dobnak. Ezeknek a megfelelő kezelése megakadályozza, hogy az alkalmazás összeomoljon kötegelt feldolgozás során.

## A példa kiterjesztése: logó vagy háttér hozzáadása

Sok valós helyzetben logó átfedés vagy színes háttér szükséges. Az Aspose.BarCode API lehetővé teszi, hogy a vonalkódot egy bitmap‑tel kombináld:

```csharp
// Load a logo image
using (Bitmap logo = (Bitmap)Image.FromFile("logo.png"))
{
    generator.Parameters.Barcode.ImageFormat = BarCodeImageFormat.Png;
    generator.Parameters.Barcode.Pdf417.EnablePdf417CodewordCount = true; // optional

    // Merge the logo with the barcode (centered)
    generator.Save("BarcodeWithLogo.png", BarCodeImageFormat.Png, logo);
}
```

Ez a technika megőrzi a **vonalkód PNG létrehozása** munkafolyamatot, miközben gazdagítja a végső kép vizuális márkázását.

## Összefoglalás

Ebben az útmutatóban bemutattuk, hogyan **hozzunk létre vonalkód PNG** fájlokat C#‑ban egy kompakt PDF417 konfigurációval. Megtanultad:

* A pontos kód, amely a `BarcodeGenerator` inicializálásához szükséges.
* **Hogyan állítsuk be az oszlopokat**, és miért fontos az oszlopszám a méret és olvashatóság szempontjából.
* Hogyan állítsd be az X‑dimenziót és engedélyezd a csonkítást egy szorosabb PNG‑hez.
* Módszerek a kép mentésére PNG, JPEG vagy SVG formátumban.
* Hibakezelési minták egy termelés‑kész **c# vonalkód példához**.
* Opcionális kiterjesztések, mint a logó átfedés és a háttér testreszabása.

Most már van egy futtatható kódrészlet, amelyet beépíthetsz számlagenerátorokba, jegyrendszerekbe vagy készletkezelő eszközökbe. Kísérletezz különböző oszlopszámokkal, modulméretekkel vagy vonalkód típusokkal (pl. QR, Code128), hogy lásd, hogyan változik a kép.

## Következő lépések

* Fedezz fel más kódolási típusokat (`EncodeTypes.QR`, `EncodeTypes.Code128`), hogy több felhasználási esetet lefedj.
* Kombináld a vonalkód-generálást PDF‑készítő könyvtárakkal (pl. **iTextSharp**) a PNG közvetlen beágyazásához dokumentumokba.
* Vizsgáld meg a dinamikus méretezést: számold ki az optimális oszlopszámot a bemeneti karakterlánc hossza és a célcímke méretei alapján.

Boldog kódolást, és élvezd a programozott módon generált, éles vonalkód PNG‑k egyszerűségét C#‑ban!

## Mit érdemes legközelebb megtanulni?

A következő tutorialok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódpéldákat tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsenek elsajátítani további API‑funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [Hogyan készítsünk PDF417 vonalkódot és mentsük PNG‑ként C#‑ban](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)
- [Hogyan készítsünk PDF417 vonalkódot és állítsuk be a méretét C#‑ban](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/)
- [Hogyan készítsünk PDF417 vonalkódot C#‑ban kompakt móddal](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
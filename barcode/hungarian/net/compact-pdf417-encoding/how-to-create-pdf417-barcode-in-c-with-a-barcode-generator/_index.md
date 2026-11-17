---
category: general
date: 2026-11-17
description: Tanulja meg, hogyan hozhat létre PDF417 vonalkódot C#-ban – egy teljes
  útmutató arról, hogyan generáljon vonalkódot karakterláncból C#-os vonalkód-generátorral.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to generate barcode
- c# barcode generator
- generate barcode from string
- create gs1 barcode
language: hu
lastmod: 2026-11-17
og_description: PDF417 vonalkód létrehozása C#-ban gyorsan. Ez az útmutató megmutatja,
  hogyan generáljunk vonalkódot karakterláncból egy C#-os vonalkód-generátorral, és
  tartalmazza a teljes forráskódot.
og_image_alt: Screenshot of a generated PDF417 barcode created with a C# barcode generator
og_title: PDF417 vonalkód létrehozása C#‑ban – lépésről‑lépésre útmutató
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  headline: How to create PDF417 barcode in C# with a barcode generator
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  name: How to create PDF417 barcode in C# with a barcode generator
  steps:
  - name: Expected output
    text: '![Generated PDF417 barcode showing the GTIN (01)12345678901234](/images/pdf417-sample.png){:
      .center-image alt="Generated PDF417 barcode created with a C# barcode generator"}'
  - name: Changing the image format
    text: If you prefer JPEG or BMP, just replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`
      or `BarCodeImageFormat.Bmp`. The rest of the code stays identical.
  - name: Adjusting error correction level
    text: PDF417 supports error correction levels 0‑8. Higher levels increase redundancy
      but also enlarge the barcode.
  - name: Generating other GS1 barcodes
    text: 'The same `BarcodeGenerator` can produce **create GS1 barcode** for other
      symbologies, such as `EncodeTypes.Gs1DataMatrix` or `EncodeTypes.Gs1Qr`. Just
      swap the enum value:'
  - name: Handling empty or null data
    text: 'When you **generate barcode from string**, always validate the input:'
  type: HowTo
- questions:
  - answer: Yes. The Aspose.BarCode library targets .NET Standard 2.0, which is compatible
      with .NET Framework 4.6 and later.
    question: Can I use this code on .NET Framework 4.6?
  - answer: 'Set the `Resolution` property before saving: ```csharp generator.Parameters.ImageResolution.DpiX
      = 300; generator.Parameters.ImageResolution.DpiY = 300; ```'
    question: What if I need a higher‑resolution image?
  - answer: 'It will be a standard PDF417 barcode, but it won’t be recognized as a
      GS1‑compliant symbol. Include the `(01)` prefix when you need **create GS1 barcode**
      compliance. ## Conclusion You now know how to **create PDF417 barcode** in C#
      using a robust **c# barcode generator**. The tutorial covered: * In'
    question: Is the barcode still valid without the GS1 Application Identifier?
  type: FAQPage
tags:
- barcode
- C#
- PDF417
- GS1
- code generation
title: Hogyan hozhatunk létre PDF417 vonalkódot C#-ban egy vonalkódgenerátorral
url: /hu/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-a-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan hozzunk létre PDF417 vonalkódot C#-ban egy vonalkódgenerátorral

Ha .NET alkalmazásban **PDF417 vonalkódot szeretne létrehozni**, ez az útmutató pontosan megmutatja, hogyan teheti meg. Megtanulja, hogyan **generáljon vonalkódot** egy egyszerű karakterláncból, hogyan állítsa be a szimbólum méretét, és hogyan mentse az eredményt PNG fájlként – mindezt egy megbízható C# vonalkódgenerátor segítségével.

A vonalkódok programozott generálása eltávolítja a manuális lépéseket és garantálja a következetes minőséget. Ebben az oktatóanyagról mindent lefedünk a projekt beállításától a végső képig, így már ma beépítheti a vonalkód létrehozását bármely C# megoldásba.

## Előfeltételek

* .NET 6.0 SDK vagy újabb (a kód működik .NET Core és .NET Framework esetén is)
* Visual Studio 2022 (vagy bármely C#-t támogató IDE)
* **Aspose.BarCode for .NET** licenc vagy ingyenes próba – a példákban használt könyvtár
* Alapvető ismeretek a C# szintaxisról

További csomagok nem szükségesek; a `Aspose.BarCode` NuGet csomag tartalmazza az összes szükséges osztályt.

## 1. lépés – A C# vonalkódgenerátor beállítása

Az első dolog, amit a **PDF417 vonalkód létrehozásakor** tesz, egy `BarcodeGenerator` objektum példányosítása. Ez az objektum a **c# vonalkódgenerátort** képviseli, amely a kódolást, megjelenítést és mentést kezeli.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for PDF417 with the data to encode
        // The data string follows the GS1 Application Identifier (01) for a GTIN
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417, "(01)12345678901234");
```

*Miért fontos*: Az `EncodeTypes.Pdf417` enum azt mondja a könyvtárnak, hogy a PDF417 szimbólumot használja, amely ugyanaz a szabvány, amit személyazonosító kártyák és szállítási címkék esetén alkalmaznak. A `"(01)12345678901234"` karakterlánc egy **vonalkód generálása karakterláncból** példát mutat, amely azt is demonstrálja, hogyan **GS1 vonalkód létrehozása** adatot hozhatunk létre.

## 2. lépés – Az X‑dimenzió (modul szélesség) beállítása

Az X‑dimenzió szabályozza a legkisebb vonal (modul) szélességét. A képernyőn történő megjelenítéshez gyakori érték 2 pixel.

```csharp
        // Step 2: Set the X‑dimension (module width) to 2 pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Az X‑dimenzió explicit beállítása megakadályozza, hogy a generátor az alapértelmezettet használja, ami egyes szkennerek számára túl kicsi vonalkódot eredményezhet.

## 3. lépés – Az oszlopok számának meghatározása

A PDF417 lehetővé teszi az oszlopok számának módosítását, ami a vonalkód alakját és adatkapacitását egyaránt befolyásolja. Egy kompakt címkéhez négy oszlop jól működik.

```csharp
        // Step 3: Define the number of columns (e.g., 4) for a compact barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

Ha magasabb vonalkódra van szüksége, növelje az oszlopszámot; a könyvtár automatikusan kiszámítja a szükséges sorok számát.

## 4. lépés – A vonalkód mentése képként

Végül exportálja a vonalkódot PNG fájlba. A PNG megőrzi a tiszta éleket és támogatja az átlátszóságot.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("output/Gs1Pdf417.png", BarCodeImageFormat.Png);
    }
}
```

A program futtatása létrehozza a `output/Gs1Pdf417.png` fájlt. Nyissa meg a fájlt bármely képnézőben – egy tiszta **PDF417 vonalkódot** fog látni, amely a megadott GS1 adatot kódolja.

### Várható kimenet

![C# vonalkódgenerátorral létrehozott PDF417 vonalkód, amely a GTIN (01)12345678901234 értéket mutat](/images/pdf417-sample.png){: .center-image alt="C# vonalkódgenerátorral létrehozott PDF417 vonalkód"}

*A fenti kép bemutatja a teljes kódminta eredményét. A vonalkódot bármely PDF417‑kompatibilis olvasó beolvashatja.*

## További lehetőségek és gyakori variációk

### Képformátum módosítása

Ha JPEG vagy BMP formátumot kedvel, egyszerűen cserélje le a `BarCodeImageFormat.Png`-t `BarCodeImageFormat.Jpeg` vagy `BarCodeImageFormat.Bmp` értékre. A kód többi része változatlan marad.

### Hibajavítási szint beállítása

A PDF417 támogatja a 0‑8 közötti hibajavítási szinteket. A magasabb szintek növelik a redundanciát, de a vonalkód méretét is nagyobbá teszik.

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // medium redundancy
```

### Más GS1 vonalkódok generálása

Ugyanaz a `BarcodeGenerator` képes **GS1 vonalkód létrehozására** más szimbólumokhoz, például `EncodeTypes.Gs1DataMatrix` vagy `EncodeTypes.Gs1Qr`. Csak cserélje ki az enum értékét:

```csharp
BarcodeGenerator gs1Generator = new BarcodeGenerator(
    EncodeTypes.Gs1DataMatrix, "(01)12345678901234");
```

### Üres vagy null adat kezelése

Amikor **vonalkód generálása karakterláncból** történik, mindig ellenőrizze a bemenetet:

```csharp
string data = GetUserInput();
if (string.IsNullOrWhiteSpace(data))
{
    throw new ArgumentException("Data to encode cannot be null or empty.");
}
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
```

Ez megakadályozza a futásidejű kivételeket, és biztosítja, hogy a vonalkód megfeleljen a GS1 formázási szabályoknak.

## Teljes, futtatható példa

Az alábbiakban a teljes program látható, amelyet beilleszthet egy új konzolprojektbe. Tartalmazza az összes szükséges `using` direktívát, mappalétrehozást és hibakezelést.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Input data – GS1 GTIN with Application Identifier (01)
        const string gs1Data = "(01)12345678901234";

        // Validate input
        if (string.IsNullOrWhiteSpace(gs1Data))
        {
            Console.WriteLine("Error: Barcode data cannot be empty.");
            return;
        }

        // Ensure output directory exists
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);

        // Create the generator for PDF417 (GS1 optional)
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417, gs1Data);

        // Configure appearance
        generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
        generator.Parameters.Barcode.Pdf417.Columns = 4;    // compact layout
        generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // optional

        // Save as PNG
        string outputPath = Path.Combine(outputDir, "Gs1Pdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

**Futtassa a programot** (`dotnet run`), és megtalálja a `Gs1Pdf417.png` fájlt az *output* mappában. Olvassa be bármely PDF417 olvasóval, hogy ellenőrizze, a GTIN `(01)12345678901234` helyesen van kódolva.

## Gyakran ismételt kérdések

**K: Használhatom ezt a kódot .NET Framework 4.6-on?**  
V: Igen. Az Aspose.BarCode könyvtár a .NET Standard 2.0-ra céloz, amely kompatibilis a .NET Framework 4.6-tal és újabb verziókkal.

**K: Mi van, ha nagyobb felbontású képre van szükségem?**  
V: Állítsa be a `Resolution` tulajdonságot a mentés előtt:

```csharp
generator.Parameters.ImageResolution.DpiX = 300;
generator.Parameters.ImageResolution.DpiY = 300;
```

**K: Érvényes marad a vonalkód a GS1 Alkalmazásazonosító nélkül?**  
V: Ez egy standard PDF417 vonalkód lesz, de nem lesz felismerhető GS1‑kompatibilis szimbólumként. Tartalmazza a `(01)` előtagot, ha **GS1 vonalkód létrehozása** megfelelőséget igényel.

## Következtetés

Most már tudja, hogyan **hozzon létre PDF417 vonalkódot** C#-ban egy robusztus **c# vonalkódgenerátor** segítségével. Az oktatóanyag lefedte:

* `BarcodeGenerator` példányosítása GS1 adatokkal  
* X‑dimenzió és oszlopszám beállítása  
* Az eredmény PNG képként való mentése  
* A megoldás kiterjesztése hibajavítással, különböző formátumokkal és bemeneti ellenőrzéssel  

Ezzel az alapokkal bármilyen PDF417 vagy GS1 vonalkódot generálhat közvetlenül egy karakterláncból, beágyazhatja jelentésekbe, vagy elküldheti nyomtatóknak. Fedezze fel az Aspose.BarCode API-t, hogy színeket, margókat adjon hozzá, vagy több vonalkódot egyetlen képpé kombináljon.

**Következő lépések**: próbáljon meg **GS1 vonalkód létrehozása** DataMatrix-hez, kísérletezzen dinamikus oszlopszám számításokkal, vagy integrálja a generátort egy ASP.NET Core webszolgáltatásba, amely igény szerint visszaad vonalkód képeket.

Boldog kódolást!

## Mit érdemes még megtanulni?

A következő oktatóanyagok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás tartalmaz teljes, működő kódpéldákat lépésről‑lépésre magyarázatokkal, hogy segítsenek elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket saját projektjeiben.

- [Hogyan generáljunk PDF417 vonalkódot C#‑ban – teljes útmutató](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-complete-guide/)
- [Hogyan hozzunk létre micro PDF417 vonalkódot és generáljunk PNG‑t C#‑ban](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-generate-png-in-c/)
- [Hogyan hozzunk létre macro PDF417 vonalkódot C#‑ban az Aspose.BarCode használatával](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
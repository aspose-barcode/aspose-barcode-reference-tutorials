---
date: 2026-06-09
description: Ismerje meg, hogyan hozhat létre DataMatrix vonalkódot ASCII módban az
  Aspose.BarCode for .NET használatával. Ez az útmutató gyorsan bemutatja, hogyan
  generáljon vonalkódot C#-ban.
keywords:
- create datamatrix barcode
- generate barcode c#
- how to encode barcode
- barcode generator example
linktitle: DataMatrix kódolási mód (ASCII)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  headline: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  name: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  steps:
  - name: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
    text: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
  - name: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
  - name: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
    text: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
  - name: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
    text: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
  type: HowTo
- questions:
  - answer: Yes, a valid Aspose license is required for production use; a free trial
      is available for evaluation.
    question: Can I use this in a commercial application?
  - answer: Absolutely – Aspose.BarCode fully supports .NET Core 3.1+, .NET 5, .NET
      6, and later versions.
    question: Does the library work with .NET Core?
  - answer: Up to 2,335 alphanumeric characters fit in a single DataMatrix symbol
      when using ASCII encoding.
    question: How many characters can I encode in ASCII mode?
  - answer: Yes, adjust `generator.Parameters.Image.ForeColor` and `BackColor` to
      any `System.Drawing.Color` value.
    question: Can I change the barcode’s foreground or background color?
  - answer: The official documentation contains dozens of samples covering custom
      sizes, colors, and error‑correction levels.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: DataMatrix vonalkód létrehozása ASCII módban az Aspose.BarCode for .NET segítségével
url: /hu/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# DataMatrix vonalkód létrehozása ASCII módban az Aspose.BarCode for .NET segítségével

## Bevezetés

Ready to **create DataMatrix barcode** images that use the efficient ASCII encoding? In this tutorial you’ll learn how to generate a DataMatrix barcode in ASCII mode using Aspose.BarCode for .NET. We’ll walk through every step—from setting up the project to saving the final image—so you can add barcode generation to your C# applications in minutes.

## Gyors válaszok
- **Melyik könyvtár a legjobb DataMatrix-hez .NET-ben?** Aspose.BarCode for .NET  
- **Hány sor kódsorra van szükség?** Körülbelül 5‑7 sor egy alap ASCII vonalkódhoz  
- **Szükségem van licencre?** Egy ingyenes próba verzió fejlesztéshez működik; licenc szükséges a termeléshez  
- **Támogatott platformok?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **Módosíthatom a méretet vagy a színeket?** Igen, az Aspose.BarCode tulajdonságokkal teszi lehetővé a méretek és az előtér/háttér színek beállítását  

## Mi az a DataMatrix vonalkód?
DataMatrix is a two‑dimensional barcode that stores text and binary data in a compact square pattern.  
A DataMatrix egy kétdimenziós vonalkód, amely szöveget és bináris adatot tárol egy kompakt négyzetes mintában.  
A DataMatrix vonalkód információt kódol egy fekete-fehér modulokból álló rácsban, egyetlen szimbólumban akár 2 335 alfanumerikus karaktert is elhelyezve. Széles körben használják a gyártásban, logisztikában és egészségügyben, mivel nagyon kis méretben is nyomtatható, miközben rendkívül könnyen beolvasható marad.

## Hogyan hozhatunk létre DataMatrix vonalkódot ASCII módban?
Load the Aspose.BarCode namespace, instantiate a `BarcodeGenerator`, set the `EncodeMode` to **EncodeMode.ASCII**, assign your data string, and call `Save` to write the image file. This approach produces a perfectly compliant DataMatrix barcode with ASCII‑only encoding in just a few lines of C# code.

## Miért használjuk az ASCII kódolást DataMatrix esetén?
ASCII mode is the default and most efficient encoding for plain‑text data, delivering the smallest possible symbol size for alphanumeric strings. It supports all 128 ASCII characters, processes data faster than extended modes, and guarantees maximum compatibility with legacy scanners that expect standard ASCII symbols.

## Előfeltételek

1. **Fejlesztői környezet** – Visual Studio, Rider vagy bármely C#‑kompatibilis IDE.  
2. **Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).  
   - Documentation: [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)  
   - Community help: [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)  
3. **Alap C# ismeretek** – Familiarity with .NET project structure will help you follow the steps quickly.  
4. **Más Aspose termékek** can be found [here](https://releases.aspose.com/).

## Névterek importálása

To start, add the required `using` directives at the top of your C# file:

```csharp
using Aspose.BarCode.Generation;
using System.Drawing;
```

These namespaces give you access to the `BarcodeGenerator` class and the image‑related types needed for saving the output.

## 1. lépés: Könyvtár létrehozása

Choose a folder where the generated barcode images will be stored. Replace `"Your Directory Path"` with an absolute or relative path that exists on your machine.

```csharp
string outputDir = @"C:\Barcodes";
if (!System.IO.Directory.Exists(outputDir))
{
    System.IO.Directory.CreateDirectory(outputDir);
}
```

The code ensures the directory exists before attempting to write any files, preventing runtime errors.

## 2. lépés: Adatok kódolása ASCII módban

The `BarcodeGenerator` class creates and configures barcode images. The `DataMatrixEncodeMode` enumeration selects the encoding algorithm for DataMatrix symbols.

```csharp
// Initialise the generator with the data you want to encode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "1234567890");

// Set the encoding mode to ASCII for optimal size
generator.Parameters.Barcode.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;

// Optional: adjust image dimensions or colors here
generator.Parameters.Image.Width = 200;
generator.Parameters.Image.Height = 200;

// Save the barcode as a PNG file
string filePath = System.IO.Path.Combine(outputDir, "datamatrix_ascii.png");
generator.Save(filePath, BarCodeImageFormat.Png);
```

After running the code, you’ll find `datamatrix_ascii.png` in the folder you specified. The image contains a DataMatrix barcode that encodes the string `"1234567890"` using the compact ASCII mode.

## Gyakori problémák és megoldások

- **Fájlhozzáférési hibák** – Ensure the application has write permissions to the target folder. Running Visual Studio as Administrator can resolve permission issues on Windows.  
- **Helytelen szimbólum méret** – If the barcode appears too large or too small, tweak `generator.Parameters.Image.Width` and `Height` or let Aspose automatically calculate the optimal size by omitting those properties.  
- **Nem támogatott karakterek** – ASCII mode only accepts characters in the 0‑127 range. For Unicode data, switch to `DataMatrixEncodeMode.Base256` or another suitable mode.

## Gyakran Ismételt Kérdések

**Q: Használhatom ezt kereskedelmi alkalmazásban?**  
A: Igen, a termeléshez érvényes Aspose licenc szükséges; ingyenes próba verzió elérhető értékeléshez.

**Q: A könyvtár működik .NET Core‑al?**  
A: Teljes mértékben – az Aspose.BarCode teljesen támogatja a .NET Core 3.1+, .NET 5, .NET 6 és későbbi verziókat.

**Q: Hány karaktert kódolhatok ASCII módban?**  
A: Akár 2 335 alfanumerikus karakter fér el egyetlen DataMatrix szimbólumban ASCII kódolás használatával.

**Q: Módosíthatom a vonalkód előtér vagy háttér színét?**  
A: Igen, állítsa be a `generator.Parameters.Image.ForeColor` és `BackColor` értékeket bármely `System.Drawing.Color` értékre.

**Q: Hol találok fejlettebb példákat?**  
A: A hivatalos dokumentáció több tucat példát tartalmaz, amelyek egyedi méreteket, színeket és hibajavítási szinteket mutatnak be.

## GyIK

### Q1: Használhatom az Aspose.BarCode for .NET-et más programozási nyelvekkel C#-on kívül?
A1: Az Aspose.BarCode több programozási nyelvet támogat, de ez az oktatóanyag C#‑ra fókuszál.

### Q2: Melyek a DataMatrix vonalkódokban elérhető különböző kódolási módok?
A2: A DataMatrix vonalkódok különböző kódolási módokat támogatnak, többek között ASCII, C40, Text és Base256. Minden mód más típusú adat számára alkalmas.

### Q3: Testreszabhatom a generált vonalkód megjelenését, például a méretét és színét?
A3: Igen, az Aspose.BarCode számos paramétert biztosít a vonalkód megjelenésének testreszabásához, beleértve a méretet, a színt és egyebeket.

### Q4: Van ingyenes próba verziója az Aspose.BarCode for .NET‑nek?
A4: Igen, az Aspose.BarCode for .NET ingyenes próba verziója elérhető [here](https://releases.aspose.com/).

### Q5: Hol vásárolhatok licencet az Aspose.BarCode for .NET‑hez?
A5: Licencet az Aspose weboldalán vásárolhat [here](https://purchase.aspose.com/buy).

---

**Utolsó frissítés:** 2026-06-09  
**Tesztelve:** Aspose.BarCode 24.11 for .NET  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [DataMatrix kódolás bájtokban az Aspose.BarCode for .NET‑el](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [DataMatrix vonalkód olvasása C# – DataMatrix mód generálása (Auto)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Hogyan generáljunk DataMatrix vonalkódokat (ECC 200) az Aspose.BarCode for .NET‑el](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.BarCode.Generation;
```

```csharp
string path = "Your Directory Path";
```

```csharp
System.Console.WriteLine("DataMatrixEncodeModeASCII:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    // Set the X-dimension (size) of the barcode in pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set the encoding mode to ASCII
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;
    
    // Save the barcode as a PNG image
    gen.Save($"{path}DataMatrixEncodeModeASCII.png", BarCodeImageFormat.Png);
}
```

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
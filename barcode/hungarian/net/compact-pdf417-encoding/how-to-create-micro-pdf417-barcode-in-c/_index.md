---
category: general
date: 2026-11-14
description: Micro PDF417 vonalkód létrehozása C#-ban az Aspose.BarCode segítségével
  – lépésről‑lépésre útmutató a generátor beállításáról, X‑dimenzióról, oszlopokról
  és a PNG exportálásról.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- micro pdf417 barcode generator
- set XDimension pixels
- define barcode columns
- save barcode as PNG
- Aspose.BarCode C# example
language: hu
lastmod: 2026-11-14
og_description: Készítsen micro PDF417 vonalkódot C#-ban az Aspose.BarCode használatával.
  Tanulja meg a generátor beállítását, az XDimension megadását, az oszlopok kiválasztását,
  és a PNG formátumba exportálást.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Micro PDF417 vonalkód létrehozása C#‑ban – teljes programozási útmutató
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  headline: How to create micro PDF417 barcode in C#
  type: TechArticle
- description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  name: How to create micro PDF417 barcode in C#
  steps:
  - name: Open the PNG in an image viewer.
    text: Open the PNG in an image viewer.
  - name: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
    text: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
  - name: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
    text: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
- image generation
title: Hogyan készítsünk micro PDF417 vonalkódot C#-ban
url: /hu/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan hozhatunk létre micro PDF417 vonalkódot C#‑ban  

Ha gyorsan **micro PDF417 vonalkód létrehozása** kell, ez az útmutató egy komplett, azonnal futtatható megoldást mutat be. Megmutatja, hogyan hozhatod létre a vonalkód‑generátort, állíthatod be az X‑dimenziót, választhatod ki az oszlopok számát, és végül mentheted az eredményt PNG képként – mindezt az Aspose.BarCode .NET könyvtár segítségével.

A micro PDF417 vonalkód generálásához nem szükséges összetett build pipeline. A tutorial végére egyetlen C# fájlod lesz, amely magas minőségű vonalkód képet állít elő, amelyet beágyazhatsz jelentésekbe, címkékbe vagy mobilalkalmazásokba.

## Előfeltételek  

* .NET 6.0 SDK vagy újabb (a kód .NET Framework 4.7+‑vel is működik).  
* Fejlesztői környezet, például Visual Studio 2022, VS Code vagy Rider.  
* Aspose.BarCode for .NET licenc (vagy ingyenes értékelő kulcs). Letöltheted a [Aspose weboldalról](https://purchase.aspose.com/barcode/net).  

> **Pro tipp:** Ha az értékelő verziót használod, a generált PNG egy kis „Evaluation” vízjelet tartalmaz. A licencelt verzió automatikusan eltávolítja.

## 1. lépés: A projekt beállítása  

Hozz létre egy új konzolos projektet, és add hozzá az Aspose.BarCode NuGet csomagot.

```bash
dotnet new console -n MicroPdf417Demo
cd MicroPdf417Demo
dotnet add package Aspose.BarCode --version 24.9.0
```

A `dotnet add package` parancs letölti az **Aspose.BarCode C# példa** függőségeit, így nem kell manuálisan kezelni a DLL‑eket.

## 2. lépés: Írd meg a teljes kódot  

Cseréld le az automatikusan generált `Program.cs`‑t a következő kóddal. Bemutatja, hogyan **hozhatsz létre micro pdf417 vonalkódot** a kezdetektől a végéig.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text.
            // The text can contain Unicode characters; here we use a sample string.
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Åspóse.Barcóde©");

            // 2️⃣ Set the X‑dimension (module width) in pixels.
            // This determines the width of the smallest element (a bar or a space).
            generator.Parameters.Barcode.XDimension.Pixels = 2; // secondary keyword: set XDimension pixels

            // 3️⃣ Define the number of columns (allowed values: 1‑4 for MicroPDF417).
            // More columns mean a wider barcode but fewer rows, which can improve readability.
            generator.Parameters.Barcode.Pdf417.Columns = 4; // secondary keyword: define barcode columns

            // 4️⃣ Choose the output format and save the barcode as a PNG image.
            // PNG preserves the sharp edges of the barcode, which is ideal for scanning.
            string outputPath = "MicroPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png); // secondary keyword: save barcode as PNG

            Console.WriteLine($"Micro PDF417 barcode saved to {outputPath}");
        }
    }
}
```

### Miért fontos minden sor  

* **BarcodeGenerator constructor** – Létrehozza a **micro pdf417 vonalkód generátort** a kódolni kívánt szöveggel.  
* **XDimension.Pixels** – A modul szélességét szabályozza; `2` pixelre állítva sűrű, nagy felbontású vonalkódot eredményez, amely a legtöbb szkennerhez megfelelő.  
* **Pdf417.Columns** – A MicroPDF417 csak 1‑4 oszlopot támogat. A `4` választása csökkenti a vonalkód magasságát, ami hasznos, ha korlátozott a függőleges hely.  
* **Save method** – PNG fájlba írja a vonalkódot. A PNG veszteségmentes, így a szkenner pontosan a generált mintát olvassa.

## 3. lépés: Build és futtatás  

Fordítsd le és futtasd a programot:

```bash
dotnet run
```

A konzolon a következő kimenetet kell látnod:

```
Micro PDF417 barcode saved to MicroPdf417.png
```

A projekt mappájában megjelenik egy **MicroPdf417.png** nevű fájl. Nyisd meg bármely képnézegetővel; egy tiszta micro PDF417 vonalkódot látsz, amely a `"Åspóse.Barcóde©"` karakterláncot kódolja.

![Létrehozott micro PDF417 vonalkód példa](MicroPdf417.png "Létrehozott micro PDF417 vonalkód példa"){.center-image width=400 alt="Létrehozott micro PDF417 vonalkód kép példa"}

*A fenti kép a 2. lépésben bemutatott kód eredménye.*

## 4. lépés: Gyakori variációk és szélhelyzetek  

| Helyzet | Hogyan módosítsd a kódot |
|-----------|----------------------|
| **Különböző adat hossza** | A MicroPDF417 legfeljebb 1 200 karaktert kódolhat. Csak módosítsd a `BarcodeGenerator` második argumentumát. |
| **Magasabb felbontás** | Növeld az `XDimension.Pixels` értékét `3`‑ra vagy `4`‑re. A nagyobb modulok javítják az olvashatóságot alacsony felbontású szkennereknél, de növelik a kép méretét. |
| **Egyedi színek** | A generátor létrehozása után állítsd be `generator.Parameters.Barcode.BarcodeColor = Color.Blue;` és `generator.Parameters.Barcode.BackgroundColor = Color.White;`. |
| **Más formátumok mentése** | Cseréld le a `BarCodeImageFormat.Png`‑t `Jpeg`‑re, `Bmp`‑re vagy `Gif`‑re a downstream követelményeknek megfelelően. |
| **Beágyazás PDF‑be** | Használd a `generator.Save("barcode.pdf", BarCodeImageFormat.Pdf);`‑t, majd egyesítsd a PDF‑et más dokumentumokkal az Aspose.PDF segítségével. |

> **Figyelj:** Az `XDimension.Pixels` értékének `1`‑nél alacsonyabbra állítása `ArgumentOutOfRangeException`‑t dob. Mindig tartsd `1` vagy nagyobb értéken.

## 5. lépés: A vonalkód ellenőrzése  

A vonalkód helyes beolvasásának biztosításához:

1. Nyisd meg a PNG‑t egy képnézegetőben.  
2. Használj bármely okostelefonos vonalkód‑olvasó alkalmazást, amely támogatja a PDF417‑et (a legtöbb „QR‑kód olvasó” app tartalmazza).  
3. Olvasd be a képet; az alkalmazásnak meg kell jelenítenie az eredeti szöveget `"Åspóse.Barcóde©"`.

Ha a beolvasás sikertelen, ellenőrizd újra az **X‑dimenzió** és **oszlop** beállításokat – a túl kicsi modul szélesség vagy egy nem támogatott oszlopszám olvashatatlanná teheti a mintát.

## Összegzés  

Most már tudod, hogyan **hozhatsz létre micro pdf417 vonalkódot** C#‑ban az Aspose.BarCode használatával. A tutorial a következőket fedte le:

* **micro pdf417 vonalkód generátor** példányosítása.  
* **XDimension pixelek beállítása** a modul szélesség szabályozásához.  
* **Vonalkód oszlopok meghatározása** a forma beállításához.  
* **Vonalkód mentése PNG‑ként** a veszteségmentes kép kimenethez.  

Innen tovább felfedezheted a további funkciókat, például a szín testreszabását, a vonalkód PDF‑be ágyazását, vagy a vonalkódok valós időben történő generálását ASP.NET Core web‑API‑kban. Boldog kódolást!

## Mit érdemes még megtanulni?

A következő tutorialok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsenek elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [Vonalkód PNG létrehozása C#‑ban – teljes útmutató a GS1 Micro PDF417‑hez](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [Hogyan hozhatsz létre macro PDF417 vonalkódot C#‑ban az Aspose.BarCode használatával](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [PDF417 vonalkód létrehozása C#‑ban az Aspose.BarCode használatával – lépésről‑lépésre útmutató](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
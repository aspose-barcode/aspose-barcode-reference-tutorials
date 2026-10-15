---
category: general
date: 2026-10-15
description: Tanulja meg, hogyan generáljon PDF417 vonalkódot C#-ban Macro‑PDF417
  paraméterek használatával, állítsa be a vonalkód méreteit, és mentse PNG formátumban.
  Teljes kódrészlet is mellékelve.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417 barcode
- C# PDF417 barcode
- Macro PDF417 parameters
- set barcode dimensions
- barcode image format
- barcode checksum
language: hu
lastmod: 2026-10-15
og_description: Hogyan generáljunk PDF417 vonalkódot C#-ban teljes Macro‑PDF417 konfigurációval,
  méretvezérléssel és PNG kimenettel. Kövesse a teljes példát.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: PDF417 vonalkód generálása C#-ban – lépésről lépésre útmutató
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to generate PDF417 barcode in C# using Macro‑PDF417 parameters,
    set barcode dimensions, and save as PNG. Complete code example included.
  headline: How to generate PDF417 barcode in C# with Macro‑PDF417 settings
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- Aspose.Barcode
title: Hogyan generáljunk PDF417 vonalkódot C#‑ban Macro‑PDF417 beállításokkal
url: /hu/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-macro-pdf417-settin/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan generáljunk PDF417 vonalkódot C#-ban Macro‑PDF417 beállításokkal

Ha **hogyan generáljunk PDF417 vonalkódot** egy dokumentumfolyamhoz, ez az útmutató pontos lépéseket mutat. Megmutatjuk, hogyan konfiguráljuk a Macro‑PDF417 paramétereket, állítsuk be a vonalkód méreteit, és exportáljuk az eredményt PNG képként – mindezt egyetlen, futtatható C# programban.

A PDF417 vonalkód generálásához nem szükséges több könyvtár vagy összetett utófeldolgozás. Az Aspose.Barcode for .NET használatával minden vonalkód‑aspektust vezérelhetünk, a modul szélességétől a checksum-ig, és magas minőségű képet hozhatunk létre, amely készen áll a nyomtatásra vagy beolvasásra.

## Előfeltételek

Mielőtt elkezdené, győződjön meg róla, hogy rendelkezik:

* .NET 6.0 (vagy újabb) SDK‑val  
* Visual Studio 2022‑vel vagy a kedvenc C# IDE‑jével  
* Aspose.Barcode for .NET NuGet csomaggal (`Install-Package Aspose.Barcode`)  

Ezek az előfeltételek biztosítják, hogy a kód további konfiguráció nélkül leforduljon.

## 1. lépés: BarcodeGenerator létrehozása Macro‑PDF417 vonalkódhoz

Az első művelet egy `BarcodeGenerator` példányt hoz létre, amely a `EncodeTypes.MacroPdf417` formátumra céloz. A konstruktor megkapja a kódolni kívánt adatot – ebben az esetben a `"Sample text"` karakterláncot.

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

// Step 1: Initialize the generator with Macro‑PDF417 and data to encode
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent steps configure the barcode
```

A generátor létrehozása beállítja a belső `Parameters` objektumot, amelyet a **C# PDF417 vonalkód** tulajdonságainak módosítására használhat.

## 2. lépés: Alapvető vonalkód megjelenés beállítása – vonalkód méretek

A vonalkód vizuális méretének szabályozása javítja a beolvasási megbízhatóságot. Az `XDimension.Pixels` tulajdonság határozza meg a modul (pont) szélességét, míg a `Pdf417.Columns` meghatározza, hány oszlopot tartalmaz a vonalkód.

```csharp
    // Step 2: Define module width and column count
    generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width in pixels
    generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

Ezeknek a méreteknek a beállítása biztosítja, hogy a vonalkód a tipikus címkelméretekbe illeszkedjen, és megfeleljen a szkenner specifikációinak.

## 3. lépés: Macro‑PDF417 fájlazonosítás megadása

A Macro‑PDF417 a szabványos PDF417 vonalkódot fájlszintű metaadatokkal egészíti ki. Egyedi fájl‑azonosítót, szegmens‑azonosítót, a szegmensek teljes számát és egy ember által olvasható fájlnevet kell megadni.

```csharp
    // Step 3: Assign macro file identification
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";
```

Ezek a **Macro PDF417 paraméterek** lehetővé teszik, hogy a downstream rendszerek a több vonalkódszegmensből rekonstruálják az eredeti fájlt.

## 4. lépés: További macro metaadatok hozzáadása – vonalkód checksum‑beágyazása

Az azonosításon túl a Macro‑PDF417 tárolhat checksum‑ot, fájlméretet, időbélyeget, címzettet, feladót és egy terminátor jelzőt. A checksum megadása javítja az adat integritás ellenőrzését a dekódolás során.

```csharp
    // Step 4: Populate extra macro metadata
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;               // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 850_000;             // file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = DateTime.UtcNow;   // UTC timestamp
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "Acme Corp";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "John Doe";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

Egy **vonalkód checksum** és egyéb metaadatok beágyazása önmagát leíró vonalkódot eredményez, ami értékes az automatizált dokumentumfeldolgozó csővezetékekben.

## 5. lépés: Generált vonalkód mentése PNG képként – vonalkód képformátum kiválasztása

Az utolsó lépés a vonalkód fájlba írása. A `Save` metódus egy fájlútvonalat és egy `BarCodeImageFormat` enum‑ot vár. A PNG veszteségmentes tömörítést biztosít, megőrizve a éles éleket a megbízható beolvasáshoz.

```csharp
    // Step 5: Export the barcode to PNG
    generator.Save("C:/Barcodes/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

A futtatás után a `MacroPdf417.png` fájl egy tiszta PDF417 vonalkódot tartalmaz, amely beágyazható PDF‑ekbe, nyomtatható címkékre vagy megjeleníthető képernyőkön.

## Várt kimenet

A `C:/Barcodes/MacroPdf417.png` megnyitása egy téglalap alakú vonalkódot mutat, amely a „Sample text” szöveget kódolja. A vonalkód tartalmazza a beállított macro metaadatokat, amelyeket bármely PDF417 szkennerrel ellenőrizhet, amely támogatja a Macro‑PDF417‑t. A kép méretei a modul szélességét (2 px) és az oszlopszámot (5) tükrözik, így egy kompakt, de jól olvasható vonalkódot kapunk.

## Gyakori variációk és szélső esetek

| Helyzet | Módosítás |
|-----------|------------|
| **Eltérő adat hossza** | Cserélje le a `"Sample text"`‑et bármely UTF‑8 karakterláncra; a generátor automatikusan beállítja a vonalkód méretét. |
| **Magasabb felbontás** | Növelje az `XDimension.Pixels` értékét 3‑ra vagy 4‑re a nagyobb modulokhoz, ami alacsony felbontású nyomtatók esetén hasznos. |
| **Több szegmens** | Állítsa be a `MacroPdf417SegmentsCount`‑t a generálni kívánt vonalkódrészek teljes számának megfelelően. |
| **Alternatív képformátum** | Használja a `BarCodeImageFormat.Jpeg`‑et vagy a `BarCodeImageFormat.Bmp`‑et, ha downstream rendszere ezeket a formátumokat részesíti előnyben. |
| **Egyedi hibajavítás** | Módosítsa a `generator.Parameters.Barcode.Pdf417.ErrorLevel`‑t (0‑8 tartomány) az adat sűrűségének és a hibatűrő képességnek a kiegyensúlyozásához. |

**Pro tipp:** Mindig ellenőrizze a generált vonalkódot fizikai szkennerrel, mielőtt éles környezetbe helyezné. A szkennerek firmware‑specifikus korlátokkal rendelkezhetnek a modul szélességre vagy az oszlopszámra vonatkozóan.

## Teljes forráskód

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace Pdf417MacroDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator for Macro‑PDF417 with sample data
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
            {
                // Set visual dimensions
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // column count

                // Provide macro file identification
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";

                // Add macro metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;               // CCITT‑16 checksum
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 850_000;             // file size in bytes
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = DateTime.UtcNow;   // timestamp
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "Acme Corp";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "John Doe";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Export as PNG
                generator.Save("C:/Barcodes/MacroPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("PDF417 barcode generated successfully.");
        }
    }
}
```

A program futtatása létrehozza a `MacroPdf417.png` fájlt a `C:/Barcodes` mappában. A konzol jelzi a sikeres generálást.

## Összegzés

Most már tudja, **hogyan generáljunk PDF417 vonalkódot** C#‑ban teljes Macro‑PDF417 vezérléssel, hogyan **állítsa be a vonalkód méreteit**, hogyan ágyazza be a **vonalkód checksum‑ot** és egyéb macro metaadatokat, valamint hogyan exportálja az eredményt a kívánt **vonalkód képformátummal**. A teljes példát bármely .NET projektbe be lehet másolni, különböző adatpayloadokhoz módosítani, és nagyobb dokumentum‑automatizálási csővezetékekbe integrálni.

### Következő lépések

* Fedezze fel a **C# PDF417 vonalkód** hibajavítási szinteket a beolvasási megbízhatóság növeléséhez.  
* Kombináljon több Macro‑PDF417 szegmenst nagy fájlok, például PDF‑ek vagy képek kódolásához.  
* Cserélje le a **vonalkód képformátumot** SVG‑re, hogy skálázható vektorgrafikát kapjon webalkalmazásokhoz.  

Kísérletezzen a paraméterekkel, és ossza meg eredményeit a kommentekben vagy a közösségi fórumokon. Boldog kódolást!

## Mit érdemes még megtanulni?

Az alábbi oktatóanyagok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes, működő kódrészleteket és lépésről‑lépésre magyarázatokat tartalmaz, hogy segítsen elsajátítani további API‑funkciókat és alternatív megvalósítási megközelítéseket saját projektjeiben.

- [Generate barcode C# with Macro PDF417 – full example](/barcode/english/net/compact-pdf417-encoding/generate-barcode-c-with-macro-pdf417-full-example/)
- [How to Generate PDF417 Barcode – Complete Programming Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)
- [How to generate PDF417 barcode in C# with custom dimensions](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
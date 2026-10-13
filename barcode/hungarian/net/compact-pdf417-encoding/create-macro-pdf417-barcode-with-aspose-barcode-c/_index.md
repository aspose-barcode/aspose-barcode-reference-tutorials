---
category: general
date: 2026-09-22
description: Macro PDF417 vonalkód létrehozása Aspose.BarCode használatával C#-ban.
  Tanulja meg lépésről lépésre, hogyan generáljon vonalkódot az Aspose segítségével,
  konfigurálja a metaadatokat, és mentse PNG formátumban.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- generate barcode with Aspose
- Aspose.BarCode PDF417
- C# barcode generation
- barcode metadata configuration
language: hu
lastmod: 2026-09-22
og_description: Készíts macro PDF417 vonalkódot az Aspose.BarCode használatával C#-ban.
  Ez az útmutató megmutatja, hogyan generálj vonalkódot az Aspose-szal, állíts be
  macro metaadatokat, és exportáld a képet.
og_image_alt: Screenshot of a created macro PDF417 barcode using Aspose.BarCode in
  C#
og_title: Makró PDF417 vonalkód létrehozása az Aspose.BarCode (C#) segítségével –
  lépésről‑lépésre útmutató
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Create macro PDF417 barcode using Aspose.BarCode in C#. Learn step‑by‑step
    how to generate barcode with Aspose, configure metadata, and save as PNG.
  headline: Create macro PDF417 barcode with Aspose.BarCode (C#)
  type: TechArticle
tags:
- Aspose
- PDF417
- C#
- Barcode
title: Makró PDF417 vonalkód létrehozása az Aspose.BarCode (C#) segítségével
url: /hu/net/compact-pdf417-encoding/create-macro-pdf417-barcode-with-aspose-barcode-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Macro PDF417 vonalkód létrehozása az Aspose.BarCode segítségével (C#)

Ha .NET alkalmazásban **macro PDF417 vonalkódot** kell létrehoznod, ez a tutorial pontosan megmutatja, hogyan teheted ezt az Aspose.BarCode segítségével. Egy teljes, futtatható példát láthatsz, amely **vonalkódot generál az Aspose-dal**, beállítja az összes makró‑specifikus mezőt, és PNG képként menti az eredményt.

A vonalkódokat gyakran használják készletnyilvántartásra, szállításra vagy dokumentumkövetésre, és a Macro PDF417 változat lehetővé teszi további fájlszintű metaadatok beágyazását a vonalkódba. A útmutató végére képes leszel egy teljes funkcionalitású macro PDF417 vonalkódot generálni, amely megfelel az ISO/IEC 15438 szabványnak.

## Amire szükséged lesz

Mielőtt elkezdenéd, győződj meg róla, hogy rendelkezel:

* .NET 6.0 SDK vagy újabb (a kód működik .NET Core és .NET Framework alatt)
* Visual Studio 2022 (vagy bármely C# IDE)
* NuGet‑kompatibilis internetkapcsolat az Aspose.BarCode csomag letöltéséhez
* Alapvető ismeretek a C# szintaxisról

Ezek a feltételek biztosítják, hogy a kód további konfiguráció nélkül leforduljon.

## 1. lépés: Az Aspose.BarCode NuGet csomag telepítése

Az Aspose.BarCode könyvtár biztosítja a `BarcodeGenerator` osztályt, amelyet a tutorial során használunk.

```bash
dotnet add package Aspose.BarCode
```

A parancs futtatása hozzáadja a legújabb stabil verziót a projektfájlodhoz (`*.csproj`). A csomag támogatja a PDF417, Macro PDF417 és számos más szimbólumkészletet.

## 2. lépés: Új konzolos projekt létrehozása (opcionális)

Ha egy tiszta kezdést szeretnél, generálj egy konzolos alkalmazást:

```bash
dotnet new console -n MacroPdf417Demo
cd MacroPdf417Demo
```

A generált `Program.cs` fogja tartalmazni a vonalkód‑generálás kódját.

## 3. lépés: A vonalkódgenerátor inicializálása

A generátort a `EncodeTypes.MacroPdf417` enum értékkel és a kódolni kívánt szöveggel hozzuk létre. Az Aspose.BarCode automatikusan kezeli a Unicode karaktereket, így közvetlenül beilleszthetsz ékezetes betűket vagy szimbólumokat.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

class Program
{
    static void Main()
    {
        // Step 3: Create a Macro PDF417 barcode generator with the desired text
        using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // The rest of the configuration follows...
```

### Miért fontos ez
`EncodeTypes.MacroPdf417` azt mondja a könyvtárnak, hogy a PDF417 makró változatát használja, amely lehetővé teszi fájlszintű metaadatok (fájlazonosító, szegmensszám stb.) beágyazását. A `"Åspóse.Barcóde©"` szöveg azt mutatja, hogy a generátor helyesen kódolja az UTF‑8 karaktereket.

## 4. lépés: Alap vonalkódméretek beállítása

A PDF417 lehetővé teszi az oszlopok számának és az X‑dimenzió (egyetlen modul szélessége) szabályozását. Ezeknek az értékeknek a módosítása befolyásolja a vonalkód fizikai méretét és a beolvasás megbízhatóságát.

```csharp
            // Step 4: Set basic barcode dimensions
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // module width in pixels
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

* **XDimension** – Kisebb értékek sűrűbb vonalkódot eredményeznek; nagyobb értékek könnyebbé teszik az alacsony felbontású szkennerek számára.
* **Columns** – Az adatoszlopok számát szabályozza; a tipikus értékek 1‑től 30‑ig terjednek.

## 5. lépés: Macro PDF417 metaadatok konfigurálása

A Macro PDF417 további mezőket tartalmaz, amelyek leírják a vonalkóddal reprezentált fájlt. Minden mező opcionális, de beállításuk javítja az interoperabilitást az olyan szkennerekkel, amelyek ismerik a makró formátumot.

```csharp
            // Step 5: Configure Macro PDF417 metadata
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // demo checksum
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // bytes
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### Az egyes mezők magyarázata

| Tulajdonság | Cél | Tipikus tartomány |
|------------|-----|-------------------|
| **MacroPdf417FileID** | Az a logikai fájl egyedi azonosítója, amely több vonalkódra is felosztható. | 0‑2³²‑1 |
| **MacroPdf417SegmentID** | Az aktuális szegmens indexe (0‑tól kezdődik). | 0‑(SegmentsCount‑1) |
| **MacroPdf417SegmentsCount** | A teljes fájlt alkotó szegmensek összes száma. | 1‑99 |
| **MacroPdf417FileName** | Az ember által olvasható fájlnév. | Legfeljebb 255 karakter |
| **MacroPdf417Checksum** | Opcionális ellenőrzőösszeg hibakereséshez. | 0‑65535 |
| **MacroPdf417FileSize** | Az eredeti fájl mérete bájtokban. | 0‑2³²‑1 |
| **MacroPdf417TimeStamp** | A fájl létrehozásának vagy módosításának időbélyege. | Bármely `DateTime` |
| **MacroPdf417Addressee** | Célazonosító (pl. részleg vagy gép). | Szabad szöveg |
| **MacroPdf417Sender** | Eredetazonosító (pl. cég neve). | Szabad szöveg |
| **MacroPdf417Terminator** | Jelzi, hogy ez a szegmens az utolsó-e. | `Set` vagy `Unset` |

**Pro tipp:** Ha egy nagy fájlt több vonalkódra osztasz, győződj meg arról, hogy minden szegmens `SegmentID`-ja sorozatos, és a `SegmentsCount` állandó marad az összes szegmensben. A szkennerek ezekre az értékekre támaszkodnak az eredeti fájl rekonstruálásához.

## 6. lépés: A vonalkód kép mentése

Az Aspose.BarCode számos kimeneti formátumot támogat (PNG, JPEG, BMP, SVG stb.). A PNG veszteségmentes minőséget biztosít, ami ideális teszteléshez és dokumentációhoz.

```csharp
            // Step 6: Save the barcode image as PNG
            barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }
    }
}
```

A program futtatása létrehozza a `ExtPDF417Meta.png` nevű fájlt a projekt kimeneti könyvtárában (`bin/Debug/net6.0/`). Nyisd meg a képet bármely megjelenítővel, hogy ellenőrizd, a vonalkód helyesen jelenik‑e meg.

## 7. lépés: A generált vonalkód ellenőrzése (opcionális)

Ha rendelkezel PDF417 szkenner alkalmazással (mobil vagy asztali), olvasd be a mentett PNG-t. A szkennernek a következőket kell visszaadnia:

* A kódolt szöveg `"Åspóse.Barcóde©"`
* Az összes beállított makró mezőt (fájlazonosító, szegmensazonosító stb.)

Automatizált ellenőrzéshez az Aspose.BarCode egy `BarCodeReader` osztályt is kínál:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

using (var reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Text: {result.CodeText}");
        Console.WriteLine($"Macro File ID: {result.GetMacroPdf417FileID()}");
        // Access other macro properties similarly
    }
}
```

Ez a kódrészlet bemutatja, hogyan lehet programozottan visszaolvasni a makró metaadatokat, megerősítve, hogy a **vonalkód generálása az Aspose-dal** végponttól‑végpontig működik.

## Szélsőséges esetek és legjobb gyakorlatok

| Helyzet | Ajánlott kezelés |
|---------|------------------|
| **Unicode karakterek** | Győződj meg róla, hogy a forráskarakterlánc UTF‑8 (alapértelmezett a .NET-ben). Az Aspose.BarCode automatikusan kódolja a Unicode-ot, de ellenőrizd a szkenner karakterkészletét. |
| **Nagy fájlméret** | A Macro PDF417 legfeljebb 99 szegmensre osztja a fájlokat. Ha a fájl meghaladja a 400 KB-ot, növeld a `SegmentsCount` értékét, és generálj több vonalkódot, mindegyiknek sorozatos `SegmentID`-je legyen. |
| **Időbélyeg pontossága** | `DateTime.UtcNow` használata az egyetemes időhez; egyes szkennerek UTC-t várnak. |
| **Ellenőrzőösszeg validálása** | Adj meg helyes ellenőrzőösszeget, ha a fogadó oldalon szeretnéd ellenőrizni az integritást. |
| **Különböző képformátumok** | `BarCodeImageFormat.Svg` használata vektorgrafikához, ha végtelenül skálázható vonalkódokra van szükség. |
| **Teljesítmény** | Használj egyetlen `BarcodeGenerator` példányt sok vonalkód generálásához; csak a `Parameters`-t módosítsd az iterációk között. |

## Teljes, futtatható példa

Az alábbiakban a teljes program látható, amelyet másolhatsz, beilleszthetsz és módosítás nélkül futtathatsz (feltéve, hogy a NuGet csomag telepítve van).



## Mit érdemes következőként megtanulni?

Az alábbi tutorialok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljes működő kódrészleteket tartalmaz lépésről‑lépésre magyarázatokkal, hogy segítsenek elsajátítani további API funkciókat és alternatív megvalósítási megközelítéseket a saját projektjeidben.

- [Aspose vonalkód példa: Macro PDF417 generálása C#-ban](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [PDF417 vonalkód metaadatok létrehozása C#-ban – Teljes lépésről‑lépésre útmutató](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [Hogyan generáljunk PDF417 vonalkód képet C#-ban az Aspose segítségével](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
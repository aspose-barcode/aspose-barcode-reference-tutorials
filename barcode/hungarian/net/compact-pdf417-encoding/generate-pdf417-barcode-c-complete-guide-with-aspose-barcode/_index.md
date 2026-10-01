---
category: general
date: 2026-08-03
description: PDF417 vonalkód generálása C#-ban az Aspose.BarCode használatával. Tanulja
  meg lépésről lépésre, hogyan adjon hozzá Macro PDF417 metaadatokat, és mentse PNG
  formátumban.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode C#
- Macro PDF417 barcode
- Aspose.BarCode
- C# barcode generation
- PDF417 metadata
- barcode image PNG
language: hu
lastmod: 2026-08-03
og_description: PDF417 vonalkód generálása C#-ban az Aspose.BarCode segítségével.
  Ez az útmutató bemutatja, hogyan ágyazhat be Macro PDF417 metaadatokat, és exportálhatja
  az eredményt PNG képként.
og_image_alt: Screenshot of a generated PDF417 barcode created with C#
og_title: PDF417 vonalkód generálása C# – lépésről lépésre Aspose.BarCode útmutató
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Generate PDF417 barcode C# using Aspose.BarCode. Learn step‑by‑step
    how to add Macro PDF417 metadata and save as PNG.
  headline: Generate PDF417 barcode C# – complete guide with Aspose.BarCode
  type: TechArticle
- description: Generate PDF417 barcode C# using Aspose.BarCode. Learn step‑by‑step
    how to add Macro PDF417 metadata and save as PNG.
  name: Generate PDF417 barcode C# – complete guide with Aspose.BarCode
  steps:
  - name: Create a Macro PDF417 barcode generator
    text: First, instantiate `BarcodeGenerator` with the `EncodeTypes.MacroPdf417`
      enum. The constructor also accepts the text you want to encode – in this example
      we use a string that contains Unicode characters to demonstrate full‑width support.
  - name: Adjust basic barcode appearance
    text: Next, define the visual size of the barcode. `XDimension.Pixels` controls
      the width of a single module (the smallest black/white square), while `Pdf417.Columns`
      influences the overall shape by setting the number of columns.
  - name: Populate Macro PDF417 metadata
    text: Macro PDF417 allows you to embed file‑level information that many back‑office
      systems rely on (e.g., file ID, segment ID, timestamp). The following properties
      illustrate the most common fields.
  - name: Save the barcode image as PNG
    text: Finally, call `Save` to write the barcode to disk. PNG is lossless, making
      it ideal for high‑quality scanning.
  - name: How to verify the result
    text: 1. Open `ExtPDF417Meta.png` in any image viewer. 2. Use a PDF417 scanner
      app (e.g., *Zebra Scanner* or *BarCode Reader* on Android/iOS). 3. Confirm that
      the decoded payload includes the original text and a JSON‑like block with the
      macro fields you set.
  - name: Next steps
    text: '- Experiment with other barcode formats (e.g., QR, Code128) by changing
      `EncodeTypes`. - Explore `Pdf417.ErrorCorrectionLevel` to improve scan reliability
      under poor lighting. - Integrate the generated image into a PDF report using
      Aspose.PDF for end‑to‑end document automation.'
  type: HowTo
tags:
- PDF417
- C#
- Barcode
title: PDF417 vonalkód generálása C#-ban – teljes útmutató az Aspose.BarCode segítségével
url: /hu/net/compact-pdf417-encoding/generate-pdf417-barcode-c-complete-guide-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PDF417 vonalkód generálása C#‑ban – teljes útmutató

Ha **PDF417 vonalkód C#‑ban** generálására van szüksége logisztikai vagy dokumentumkezelő rendszerhez, ez a bemutató pontosan megmutatja, hogyan teheti meg az Aspose.BarCode segítségével. Megmutatjuk, hogyan konfigurálja a vonalkódot, hogyan ágyaz be Macro PDF417 metaadatokat, és hogyan menti az eredményt PNG képként néhány sor kóddal.

PDF417 vonalkód generálása C#‑ban gyakran magában foglal további információk kezelését, például fájlazonosítókat, szegmensszámokat vagy időbélyegeket. Ez az útmutató ezeket a részleteket lefedi, így nem kell szétszórt dokumentációban keresgélnie. A cikk végére egy kész, futtatható programot kap, amely megfelelõ Macro PDF417 vonalkód képet állít elő.

## Amire szüksége lesz

- .NET 6.0 vagy újabb (a kód .NET Framework 4.7+‑tel is működik)
- Aspose.BarCode for .NET (v23.9 vagy újabb) – telepítés NuGet‑en: `Install-Package Aspose.BarCode`
- Fejlesztői környezet, például Visual Studio 2022 vagy Visual Studio Code
- Alapvető C# szintaxis ismeret

> **Pro tipp:** Használja az Aspose.BarCode legújabb verzióját a hibajavítások és a legújabb PDF417 specifikációk támogatása érdekében.

## PDF417 vonalkód generálása C#‑ban az Aspose.BarCode‑dal

A folyamat négy logikai lépésből áll. Minden lépés egyértelmű kódrészletbe van ágyazva, így azonnal másolható, beilleszthető és futtatható.

### 1. lépés: Macro PDF417 vonalkód generátor létrehozása

Először példányosítsa a `BarcodeGenerator`‑t a `EncodeTypes.MacroPdf417` enum-mal. A konstruktor a kódolandó szöveget is elfogadja – ebben a példában egy Unicode karaktereket tartalmazó stringet használunk a teljes szélesség támogatásának bemutatására.

```csharp
using System;
using Aspose.BarCode.Generation;

// Create a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417,
           "Åspóse.Barcóde©"))
{
    // Subsequent steps go inside this using block
```

*Miért fontos*: A `MacroPdf417` típus azt mondja az Aspose.BarCode‑nak, hogy a szimbólumot makró vonalkódként kezelje, amely további fájlszintű metaadatokat képes hordozni. Enélkül a később beállított extra mezők figyelmen kívül maradnak.

### 2. lépés: Alapvető vonalkód megjelenés beállítása

Ezután határozza meg a vonalkód vizuális méretét. Az `XDimension.Pixels` szabályozza egyetlen modul (a legkisebb fekete/fehér négyzet) szélességét, míg a `Pdf417.Columns` a teljes alakot befolyásolja az oszlopok számának beállításával.

```csharp
    // Adjust basic barcode appearance
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // size of a single module
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol
```

*Miért fontos*: A kisebb `XDimension` nagyobb felbontású képet eredményez, ami akkor hasznos, ha a vonalkódot képernyőről kell beolvasni. Az oszlopszám módosítása segíthet a vonalkódot korlátozott helyre illeszteni anélkül, hogy csökkenne az adatkapacitás.

### 3. lépés: Macro PDF417 metaadatok feltöltése

A Macro PDF417 lehetővé teszi fájlszintű információk beágyazását, amelyre számos háttérrendszer támaszkodik (pl. fájl‑ID, szegmens‑ID, időbélyeg). Az alábbi tulajdonságok a leggyakoribb mezőket szemléltetik.

```csharp
    // Populate Macro PDF417 metadata
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;          // CCITT‑16 example
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Miért fontos*: Minden mező közvetlenül a makró vonalkód specifikáció egy szegmensére térképeződik. Például a `MacroPdf417FileID` egyedileg azonosítja a logikai fájlt, míg a `MacroPdf417SegmentsCount` megmondja a leolvasónak, hány részt várjon. A pontos metaadatok biztosítják, hogy az utólagos rendszerek hibamentesen rekonstruálhassák az eredeti dokumentumot.

### 4. lépés: Vonalkód mentése PNG‑képként

Végül hívja meg a `Save` metódust a vonalkód lemezre írásához. A PNG veszteségmentes, így ideális a magas minőségű beolvasáshoz.

```csharp
    // Save the barcode image as PNG
    barcodeGenerator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Miért fontos*: A `BarCodeImageFormat.Png` enum garantálja, hogy a kimeneti fájl pontosan azt a pixeladatot tartalmazza, amit beállított. Ha vektoros formátumra van szüksége a méretezéshez, cserélje a `Png`‑t `Svg`‑re – az Aspose.BarCode ezt natívan támogatja.

#### Várható kimenet

A teljes program futtatása után egy **ExtPDF417Meta.png** nevű fájl jön létre. A kép egy sűrű, több soros PDF417 szimbólumot mutat, amely tartalmazza a „Åspóse.Barcóde©” szöveget és a megadott makró metaadatokat. A vonalkód PDF417‑kompatibilis olvasóval történő beolvasása visszaadja az eredeti szöveget, valamint egy strukturált adatblokkot, amely a fájl‑ID‑t, szegmens‑ID‑t, időbélyeget és egyéb mezőket tartalmaz.

![Screenshot of generated PDF417 barcode](/images/pdf417-example.png){: .center-image alt="PDF417 vonalkód generálása C# példakimenet"}

## Teljes forráskód (másolás‑beillesztés kész)

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417MacroDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a Macro PDF417 barcode generator with the desired text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417,
                       "Åspóse.Barcóde©"))
            {
                // Step 2: Adjust basic barcode appearance
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // size of a single module
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol

                // Step 3: Populate Macro PDF417 metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;          // CCITT‑16 example
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the barcode image as PNG
                barcodeGenerator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

### Az eredmény ellenőrzése

1. Nyissa meg az `ExtPDF417Meta.png` fájlt bármely képnézőben.  
2. Használjon PDF417‑olvasó alkalmazást (pl. *Zebra Scanner* vagy *BarCode Reader* Androidon/iOS‑en).  
3. Ellenőrizze, hogy a dekódolt payload tartalmazza az eredeti szöveget és egy JSON‑szerű blokkot a beállított makró mezőkkel.

## Gyakori kérdések és szélsőséges esetek kezelése

| Kérdés | Válasz |
|----------|--------|
| **Létrehozhatok vektoros képet PNG helyett?** | Igen. Cserélje a `BarCodeImageFormat.Png`‑t `BarCodeImageFormat.Svg`‑re. A kód többi része változatlan marad. |
| **Mi van, ha az adataim meghaladják az alapkapacitást?** | Növelje a `Pdf417.Columns` értékét vagy állítsa be manuálisan a `Pdf417.Rows`‑t. A nagyobb értékek több kódszót engednek meg szegmensenként. |
| **Támogatott-e az Unicode a kódolt szövegben?** | Természetesen. A példa a „Åspóse.Barcóde©” szöveget használja. Az Aspose.BarCode szükség esetén automatikusan UTF‑8 kódolásra vált. |
| **Szükséges licencet regisztrálni az Aspose.BarCode‑hoz?** | Éles környezetben licencet kell alkalmazni a vízjel elkerülése érdekében. Hívja meg a `License license = new License(); license.SetLicense("Aspose.BarCode.lic");` sort a generátor létrehozása előtt. |
| **Hogyan kezeljem a mentési hibákat?** | Tegye a `Save` hívást try/catch blokkba, és naplózza az `IOException`‑t vagy `BarCodeException`‑t a hibaelhárításhoz. |

## Következtetés

Most már tudja, hogyan **generáljon PDF417 vonalkódot C#‑ban** az Aspose.BarCode‑dal, hogyan ágyazzon be teljes Macro PDF417 metaadatokat, és hogyan exportálja az eredményt magas minőségű PNG‑képként. A lépések – a generátor létrehozása, a megjelenés beállítása, a metaadatok feltöltése és a kép mentése – újrahasználható mintát adnak, amelyet számlák, szállítócímkék vagy bármely olyan szituáció esetén alkalmazhat, ahol gazdag vonalkód adatokra van szükség.

### Következő lépések

- Kísérletezzen más vonalkódformátumokkal (pl. QR, Code128) az `EncodeTypes` módosításával.  
- Fedezze fel a `Pdf417.ErrorCorrectionLevel` beállítást a rossz fényviszonyok közti beolvasási megbízhatóság javításához.  
- Integrálja a generált képet PDF‑jelentésbe az Aspose.PDF segítségével a teljes dokumentumautomatizálás érdekében.  

Nyugodtan módosítsa a metaadatmezőket a saját üzleti szabályai szerint, és tegye a vonalkódgenerálást zökkenőmentes részeivé C#‑alkalmazásainak. Boldog kódolást!

## Mit érdemes még tanulni?

Az alábbi oktatóanyagok szorosan kapcsolódó témákat fednek le, amelyek a jelen útmutatóban bemutatott technikákra épülnek. Minden forrás teljesen működő kódrészleteket és lépésről‑lépésre magyarázatokat tartalmaz, hogy segítsen elsajátítani további API‑funkciókat és alternatív megvalósítási megközelítéseket saját projektjeiben.

- [Hogyan hozzunk létre vonalkódot – Kompakt PDF417 az Aspose.BarCode‑dal](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hogyan hozzunk létre vonalkódot – Kompakt PDF417 az Aspose.BarCode‑dal (német) ](/barcode/german/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [java vonalkód könyvtár – Vonalkód hozzáadása PDF‑hez az Aspose használatával](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
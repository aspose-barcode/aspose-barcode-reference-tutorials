---
category: general
date: 2026-09-10
description: Skapa PDF417‑streckkod i C# snabbt. Lär dig hur du aktiverar kompakt
  läge, ställer in kolumner och genererar en PNG med BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- enable compact mode
- barcode generator C#
- how to generate barcode
- how to set columns
language: sv
lastmod: 2026-09-10
og_description: Skapa PDF417‑streckkod i C# genom att aktivera kompakt läge, ange
  kolumner och spara som PNG. Följ den kompletta steg‑för‑steg‑guiden.
og_image_alt: Screenshot of a compact PDF417 barcode generated with C#
og_title: Skapa PDF417-streckkod i C# – handledning för kompakt läge
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create PDF417 barcode in C# quickly. Learn how to enable compact mode,
    set columns, and generate a PNG with BarcodeGenerator.
  headline: How to create PDF417 barcode in C# with compact mode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Hur man skapar PDF417‑streckkod i C# med kompakt läge
url: /sv/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så skapar du PDF417-streckkod i C# med kompakt läge

Om du behöver **skapa PDF417-streckkod** i en .NET‑applikation visar den här guiden exakt hur du gör det. Du får se hur du **aktiverar kompakt läge**, anger antalet kolumner och sparar resultatet som en PNG‑bild med BarcodeGenerator C#‑biblioteket.

Att generera en streckkod är ett vanligt krav för lagerhantering, biljettsystem och mobila skannings‑appar. I slutet av den här handledningen har du ett självständigt, körbart exempel som producerar en kompakt PDF417‑streckkod klar för produktionsbruk.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 eller senare installerat (koden fungerar också med .NET Framework 4.7+)
* En aktuell version av **BarcodeGenerator**‑biblioteket (t.ex. Aspose.BarCode for .NET)
* En IDE eller editor som Visual Studio 2022 eller VS Code
* Skrivbehörighet till en mapp där PNG‑filen ska sparas

Inga extra NuGet‑paket krävs utöver själva streckkodsbiblioteket.

## Steg 1: Skapa en PDF417-streckkodsgenerator

Det första steget är att instansiera ett `BarcodeGenerator`‑objekt med `EncodeTypes.Pdf417`‑enum och den text du vill koda. Detta objekt driver hela genereringsprocessen.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

*Varför detta är viktigt*: Värdet `EncodeTypes.Pdf417` talar om för biblioteket att använda PDF417‑symbologi, medan det andra argumentet levererar data. Du kan ersätta `"Compact mode"` med vilken alfanumerisk sträng du än behöver koda.

## Steg 2: Ställ in X-dimensionen (modulbredd)

X-dimensionen styr bredden på varje liten ruta (modul) i streckkoden. Mindre värden ger en tätare bild, vilket är användbart när utrymmet är begränsat.

```csharp
// Step 2: Set the X dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Ett värde på `2` pixlar är en bra balans mellan läsbarhet och kompaktitet för de flesta skärmbaserade skannrar.

## Steg 3: Definiera antalet kolumner

PDF417 kan ordna data i ett rutnät av rader och kolumner. Genom att justera antalet kolumner ändras streckkodens bildförhållande.

```csharp
// Step 3: Define the number of columns for the PDF417 barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

Att sätta **antal kolumner** till `3` ger en kort, bred streckkod som passar bra på en etikett. Du kan experimentera med värden från `1` till `30` beroende på mängden data och den avsedda skannern.

## Steg 4: Aktivera kompakt läge

Kompakt läge tar bort onödiga padding‑rader, vilket gör streckkoden mindre utan att förlora dataintegritet. Detta är nyckelsteget för en **kompakt PDF417**.

```csharp
// Step 4: Enable compact mode by truncating the barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

När `Truncate` är `true` beräknar biblioteket automatiskt det minsta antalet rader som krävs för att lagra data, vilket är anledningen till att den slutgiltiga bilden ser “tight” ut.

## Steg 5: Spara den genererade streckkoden som en PNG‑bild

Till sist skriver du streckkoden till en fil. PNG bevarar de skarpa kanterna som behövs för pålitlig skanning.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

Ersätt `YOUR_DIRECTORY` med en absolut eller relativ sökväg som din applikation kan skriva till. Efter körning hittar du en `CompactPdf417.png`‑fil som innehåller streckkoden.

### Fullständig källkod

Att sätta ihop alla stegen ger dig ett enda, färdigt‑att‑köra program:

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

        // Set the X dimension (module width) in pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the number of columns for the PDF417 barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;

        // Enable compact mode by truncating the barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("CompactPdf417.png", BarCodeImageFormat.Png);

        Console.WriteLine("PDF417 barcode created successfully.");
    }
}
```

När du kör programmet skapas `CompactPdf417.png` i samma mapp som den körbara filen. Öppna bilden i någon bildvisare; du bör se en tät, högkontrast PDF417‑streckkod redo för skanning.

## Hur man aktiverar kompakt läge i andra scenarier

* **Batch‑generering** – När du skapar många streckkoder, sätt `Truncate` en gång på generatorn och återanvänd den för varje ny data.
* **Olika bildformat** – Samma `Save`‑metod fungerar med `BarCodeImageFormat.Jpeg` eller `BarCodeImageFormat.Bmp` om du behöver en annan filtyp.
* **Dynamiskt kolumnantal** – Om längden på den kodade strängen varierar, beräkna ett optimalt kolumnantal baserat på stränglängden och skannarens upplösning.

## Hur man sätter kolumner för specifika användningsfall

* **Etikettutskrift** – Använd ett lågt kolumnantal (t.ex. `2`‑`5`) för att hålla streckkoden kort nog att passa på smala etiketter.
* **Mobil skanning** – Högre kolumnantal (`10`‑`15`) ger längre streckkoder som är lättare för telefonkameror att fokusera på.
* **Avvägning av felkorrigering** – Fler kolumner minskar antalet rader, vilket kan påverka streckkodens inbyggda felkorrigering. Testa med din målskanner för att hitta den bästa balansen.

## Vanliga fallgropar och pro‑tips

| Problem | Varför det händer | Lösning |
|---------|-------------------|---------|
| Streckkoden är oläslig | X-dimensionen för låg (t.ex. `1` pixel) | Öka `XDimension.Pixels` till minst `2` |
| Bilden är för stor | Kolumnerna är för många för en kort data | Minska `Pdf417.Columns` eller aktivera `Truncate` |
| PNG‑filen är tom | Utdatamappen finns inte eller saknar skrivbehörighet | Säkerställ att katalogen finns och att processen har skrivbehörighet |
| Skannern rapporterar “data korrupt” | Truncate inaktiverat medan många kolumner används | Aktivera `Truncate` eller minska antalet kolumner |

## Verifiera resultatet

Du kan verifiera streckkoden med någon PDF417‑skannerapp (många gratis Android/iOS‑appar finns). Öppna `CompactPdf417.png` i appen och bekräfta att den avkodade texten matchar den ursprungliga datan (“Compact mode”). Om texten skiljer sig, dubbelkolla `Truncate`‑flaggan och kolumninställningarna.

## Nästa steg

* **Integrera med ASP.NET Core** – Returnera PNG‑filen direkt från en controller‑action istället för att spara till disk.
* **Lägg till mänskligt läsbar text** – Använd `barcodeGenerator.Parameters.Barcode.CodeTextParameters` för att visa den kodade strängen under streckkoden.
* **Utforska andra symbologier** – Samma `BarcodeGenerator`‑klass stödjer QR, Code128, DataMatrix och mer. Byt `EncodeTypes` för att prova dem.

---

### Slutsats

Du vet nu hur du **skapar PDF417-streckkod** i C# samtidigt som du **aktiverar kompakt läge**, styr **hur man sätter kolumner**, och använder **barcode generator C#**‑API:t för att **generera en streckkod** som uppfyller verkliga storlekskrav. Applicera dessa steg i alla .NET‑projekt som behöver kompakt, högdensitets‑streckkoder, och utöka mönstret till andra streckkodformat vid behov. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

De följande handledningarna täcker närbesläktade ämnen som bygger vidare på teknikerna i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
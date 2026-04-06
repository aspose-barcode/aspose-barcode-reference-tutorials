---
date: 2026-03-07
description: Lär dig hur du skapar EAN-13-streckkod med tilläggsdata i C# med Aspose.BarCode
  för .NET – generera streckkod PNG snabbt.
linktitle: Supplemental Barcode Data Configuration
second_title: Aspose.BarCode .NET API
title: Skapa EAN-13-streckkod med tilläggsdata – Aspose.BarCode
url: /sv/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa EAN-13-streckkod med kompletterande data – Aspose.BarCode för .NET

## Quick Answers
- **Vad betyder “supplemental data”?** Extra siffror (EAN‑2/EAN‑5) som skrivs bredvid huvudstreckkoden, ofta använda för pris‑ eller nummer‑uppgifter.  
- **Vilken streckkodstyp används?** EAN‑13 som huvudsymbol, med valfria EAN‑2‑ eller EAN‑5‑kompletteringar.  
- **Kan jag exportera PNG‑bilder?** Ja – `Save`‑metoden låter dig exportera direkt till PNG.  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en kommersiell licens krävs för produktion.  
- **Är detta kompatibelt med .NET Core / .NET 6?** Absolut – Aspose.BarCode stödjer alla moderna .NET‑miljöer.

## Prerequisites

Innan vi dyker in i koden, se till att du har:

- Visual Studio (eller någon .NET‑kompatibel IDE).  
- En kopia av Aspose.BarCode för .NET – ladda ner den **[här](https://releases.aspose.com/barcode/net/)**.  
- Grundläggande kunskaper i C#.  
- En skrivbar mapp där de genererade PNG‑filerna kommer att sparas.

## Importing Namespaces

Först, lägg till Aspose.BarCode‑namnutrymmet så att du kan komma åt generator‑klasserna:

```csharp
using Aspose.BarCode.Generation;
```

> **Pro tip:** Om du använder .NET Core, lägg till NuGet‑paketet `Aspose.BarCode` i ditt projekt istället för att referera DLL‑filen manuellt.

## What is a Supplemental Barcode?

En kompletterande streckkod är en extra numerisk sträng som skrivs bredvid huvudstreckkoden.  
- **EAN‑2** – tvåsiffrig komplettering, ofta använd för nummer på tidskrifter.  
- **EAN‑5** – femsiffrig komplettering, vanligt för prisutökningar på detaljhandelsvaror.

## Why Use Aspose.BarCode for Supplemental Data?

- **One‑line API** – konfigurera både huvudstreckkoden och dess komplettering i ett enda objekt.  
- **Full control over dimensions** – justera X‑dimension, avstånd för komplettering och bildformat.  
- **Cross‑platform** – fungerar på .NET Framework, .NET Core och .NET 5/6+.  

## Step‑by‑Step Guide

### Step 1: Set Up the Output Directory

Definiera var PNG‑filerna ska lagras. Ersätt platshållaren med en riktig sökväg på din maskin.

```csharp
string path = "Your Directory Path";
```

### Step 2: Initialise the Barcode Generator (Barcode Generator C#)

Skapa en `BarcodeGenerator`‑instans, ange **EAN‑13** som huvudtyp och ange den 13‑siffriga datamängden.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

### Step 3: Adjust Barcode Dimensions

Finjustera den visuella storleken på streckkoden och utrymmet som reserveras för kompletteringen.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

### Step 4: Add an EAN‑2 Supplement

Ställ in den kompletterande datan till ett tvåsiffrigt värde (t.ex. “12”). Detta visas till höger om huvudstreckkoden.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

### Step 5: Save the EAN‑2 Barcode as PNG

Exportera bilden. Argumentet `BarCodeImageFormat.Png` säkerställer en högkvalitativ PNG‑fil.

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

### Step 6: Switch to an EAN‑5 Supplement

Ändra `SupplementData` till en femsiffrig sträng för prisutökningar.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

### Step 7: Save the EAN‑5 Barcode as PNG

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

> **Why this works:** Samma `BarcodeGenerator`‑instans återanvänds, så du behöver bara modifiera `SupplementData`‑egenskapen innan varje `Save`‑anrop. Detta håller koden koncis och undviker onödig objekt‑skapande.

## Common Issues & Tips

- **Invalid directory path** – se till att mappen finns och att applikationen har skrivbehörighet.  
- **Incorrect supplement length** – EAN‑2 förväntar exakt 2 siffror, EAN‑5 förväntar 5; annars kastas ett undantag.  
- **Image not visible** – verifiera att `BarCodeImageFormat.Png` används; andra format (t.ex. JPEG) kan introducera komprimeringsartefakter som påverkar skannerns läsbarhet.  

## Frequently Asked Questions

### Kan jag använda Aspose.BarCode för .NET i mitt .NET Core‑projekt?
Ja, Aspose.BarCode för .NET är fullt kompatibel med .NET Core, .NET 5 och .NET 6.

### Finns det en gratis provversion av Aspose.BarCode för .NET?
Ja, du kan prova den kostnadsfritt genom att besöka **[den här länken](https://releases.aspose.com/)**.

### Var kan jag få en tillfällig licens för Aspose.BarCode för .NET?
Du kan skaffa en tillfällig licens från **[den här länken](https://purchase.aspose.com/temporary-license/)**.

### Stöder Aspose.BarCode ett brett sortiment av streckkodstyper?
Absolut – den stödjer EAN‑13, QR Code, Code 128, DataMatrix, PDF‑417 och många fler.

### Kan jag anpassa utseendet på de genererade streckkoderna?
Ja, du kan ändra färger, typsnitt, marginaler och till och med lägga till bakgrundsbilder via det omfattande `Parameters`‑API‑et.

## Conclusion

Du vet nu hur du **skapar EAN-13-streckkod** med kompletterande EAN‑2‑ eller EAN‑5‑data och **genererar streckkod‑PNG‑filer** med Aspose.BarCode för .NET. Detta tillvägagångssätt ger dig full kontroll över streckkodens dimensioner, avstånd för komplettering och utdataformat, vilket gör det idealiskt för detaljhandel, logistik och alla scenarier där extra numerisk information krävs.

För djupare utforskning, kolla in den fullständiga referensguiden: **[Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)**.

---

**Last Updated:** 2026-03-07  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
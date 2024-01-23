---
title: Generera DataMatrix-streckkoder med Aspose.BarCode för .NET
linktitle: DataMatrix-versioner
second_title: Aspose.BarCode .NET API
description: Lär dig hur du genererar DataMatrix-streckkoder i .NET med Aspose.BarCode för .NET. Anpassade mått, ECC-stöd och mer.
type: docs
weight: 12
url: /sv/net/datamatrix-barcode-reading/datamatrix-versions/
---
Om du letar efter en pålitlig lösning för att generera DataMatrix-streckkoder i dina .NET-applikationer är Aspose.BarCode för .NET rätt väg att gå. I den här steg-för-steg-guiden går vi igenom processen med att använda Aspose.BarCode för .NET för att skapa DataMatrix-streckkoder. Vi delar upp varje exempel i flera steg, så att du enkelt kan följa med.

## Förutsättningar

Innan vi dyker in i koden, se till att du har följande förutsättningar på plats:
- En utvecklingsmiljö med .NET-stöd.
-  En kopia av Aspose.BarCode för .NET, som du kan ladda ner från[den här länken](https://releases.aspose.com/barcode/net/).
- Grundläggande kunskaper i C# och .NET-ramverket.

Låt oss nu utforska DataMatrix-versionerna och hur man genererar dem med Aspose.BarCode för .NET.

## Importera namnområden

I alla C#-projekt är det viktigt att importera de nödvändiga namnrymden. När det gäller Aspose.BarCode måste du inkludera följande:

```csharp
using Aspose.BarCode.Generation;
```

 Detta namnutrymme ger åtkomst till`BarcodeGenerator` klass, vilket är avgörande för att generera streckkoder.

Låt oss nu dela upp exemplet i flera steg.

## Steg 1: Ställ in din katalogsökväg

Börja med att definiera katalogsökvägen där du vill spara de genererade DataMatrix-streckkoderna.

```csharp
string path = "Your Directory Path";
```

 Byta ut`"Your Directory Path"` med den faktiska sökvägen där du vill spara streckkodsbilderna.

## Steg 2: Initiera streckkodsgeneratorn

 Skapa en instans av`BarcodeGenerator` klass och ange streckkodstypen som`DataMatrix`. Du kan också ange de data som du vill koda i streckkoden.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Koden för att generera streckkoder går här
}
```

## Steg 3: Konfigurera streckkodsegenskaper

Du kan anpassa olika egenskaper för DataMatrix-streckkoden, såsom dess dimensioner och ECC-typ (Error Correction Code). Här är ett exempel på att ställa in X-dimensionen till 4 pixlar och välja ECC200:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4;
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

## Steg 4: Ställ in DataMatrix-version och spara

Du kan ange DataMatrix-versionen genom att ställa in antalet rader och kolumner. När du har konfigurerat versionen sparar du streckkodsbilden.

Till exempel, för att skapa en DataMatrix-streckkod med 22 rader och 22 kolumner med ECC200:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC200_22x22;
generator.Save($"{path}DataMatrixRows22Columns22Ecc200.png", BarCodeImageFormat.Png);
```

På samma sätt kan du generera en streckkod med olika parametrar genom att ändra version och ECC-typ efter behov.

## Steg 5: Upprepa för andra versioner

Du kan upprepa steg 4 för andra DataMatrix-versioner. Till exempel, för att skapa en streckkod med 12 rader och 64 kolumner med ECC200:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.DMRE_12x64;
generator.Save($"{path}DataMatrixRows12Columns64Ecc200.png", BarCodeImageFormat.Png);
```

## Steg 6: Byt ECC-typer

Om du vill ändra ECC-typen till Ecc140 kan du göra det genom att uppdatera ECC-egenskapen:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;
```

## Steg 7: Generera streckkoder med olika versioner och ECC

Upprepa steg 4 för andra DataMatrix-versioner och ECC-typer, och spara varje streckkod med ett unikt filnamn.

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC000_140_29x29;
generator.Save($"{path}DataMatrixRows29Columns29Ecc140.png", BarCodeImageFormat.Png);
```

Nu när du har lärt dig hur du genererar DataMatrix-streckkoder med Aspose.BarCode för .NET, kan du enkelt integrera denna funktion i dina .NET-applikationer.

## Slutsats

Aspose.BarCode för .NET förenklar processen att generera DataMatrix-streckkoder i dina .NET-applikationer. Med denna steg-för-steg-guide kan du skapa streckkoder med olika versioner och ECC-typer, vilket erbjuder flexibilitet och anpassning för att möta dina specifika behov.

 Om du har några frågor eller behöver hjälp, tveka inte att besöka[Aspose.BarCode för .NET-dokumentation](https://reference.aspose.com/barcode/net/) eller kolla in[Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) för support.

## FAQ's

### F1: Vad är ECC i DataMatrix-streckkoder?

S1: ECC (Error Correction Code) är en viktig komponent i DataMatrix-streckkoder som hjälper till att säkerställa dataintegritet. Olika ECC-nivåer ger olika grader av felkorrigering.

### F2: Kan jag generera DataMatrix-streckkoder med anpassade dimensioner med Aspose.BarCode för .NET?

S2: Ja, du kan anpassa dimensionerna för DataMatrix-streckkoder genom att ställa in antalet rader och kolumner som visas i handledningen.

### F3: Var kan jag ladda ner Aspose.BarCode för .NET?

 S3: Du kan ladda ner Aspose.BarCode för .NET från[den här länken](https://releases.aspose.com/barcode/net/).

### F4: Finns det en gratis testversion tillgänglig för Aspose.BarCode för .NET?

 S4: Ja, du kan få tillgång till en gratis testversion av Aspose.BarCode för .NET[här](https://releases.aspose.com/).

### F5: Hur kan jag få en tillfällig licens för Aspose.BarCode för .NET?

 S5: För att få en tillfällig licens för Aspose.BarCode för .NET, besök[den här länken](https://purchase.aspose.com/temporary-license/).
---
title: Skapa kompletterande streckkodsdata med Aspose.BarCode för .NET
linktitle: Kompletterande streckkodsdatakonfiguration
second_title: Aspose.BarCode .NET API
description: Generera kompletterande streckkodsdata med Aspose.BarCode för .NET. Anpassa streckkoderna EAN-2 och EAN-5 utan ansträngning. Steg-för-steg-guide för .NET-utvecklare.
type: docs
weight: 10
url: /sv/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
---

I en värld av streckkodsgenerering och anpassning framstår Aspose.BarCode för .NET som ett kraftfullt och mångsidigt verktyg. Oavsett om du är en erfaren utvecklare eller precis har börjat, kommer denna steg-för-steg-guide att leda dig genom processen att konfigurera kompletterande streckkodsdata med Aspose.BarCode för .NET. 

## Förutsättningar

Innan vi dyker in i världen av kompletterande streckkodsdata, se till att du har följande förutsättningar på plats:

- En utvecklingsmiljö konfigurerad med Visual Studio eller något annat .NET-utvecklingsverktyg.
-  En kopia av Aspose.BarCode för .NET. Om du inte redan har gjort det kan du ladda ner den[här](https://releases.aspose.com/barcode/net/).
- Grundläggande kunskaper i C#-programmering.
- En katalog där du kan spara de genererade streckkodsbilderna.

## Importera namnområden

Se först till att du har de nödvändiga namnrymden inkluderade i din C#-kod för att fungera med Aspose.BarCode för .NET. Importera de nödvändiga namnrymden i början av din C#-fil:

```csharp
using Aspose.BarCode.Generation;
```

Låt oss nu dela upp processen för att konfigurera kompletterande streckkodsdata i flera steg.

## Steg 1: Konfigurera katalogsökvägen

 I din C#-kod definierar du sökvägen till katalogen där du vill spara de genererade streckkodsbilderna. Byta ut`"Your Directory Path"` med din faktiska katalogsökväg.

```csharp
string path = "Your Directory Path";
```

## Steg 2: Skapa en streckkodsgenerator

 Skapa en instans av`BarcodeGenerator` genom att ange streckkodstypen och de data du vill koda. I det här exemplet använder vi en EAN-13 streckkod med data "1234567890128".

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

## Steg 3: Anpassa streckkodsmått

Ställ in måtten på streckkoden, till exempel X-dimensionen (bredden på det minsta elementet i streckkoden) och det extra utrymmet. I det här exemplet ställer vi in X-dimensionen till 2 pixlar och det kompletterande utrymmet till 20 pixlar.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

## Steg 4: Konfigurera EAN-2-tillägg

För att konfigurera en EAN-2 tilläggsstreckkod, ställ in tilläggsdata till önskat värde. I det här fallet ställer vi in den på "12". 

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

## Steg 5: Spara streckkodsbilden

Spara den genererade streckkodsbilden till din angivna katalog med ett meningsfullt namn. I det här exemplet sparar vi den kompletterande streckkoden EAN-2 som "SupplementEAN2.png".

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

## Steg 6: Konfigurera EAN-5-tillägg

 För att konfigurera en EAN-5 tilläggsstreckkod, ändra helt enkelt`SupplementData` till ditt önskade värde. Här ställer vi in den på "12345".

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

## Steg 7: Spara streckkodsbilden (EAN-5)

Slutligen, spara EAN-5 kompletterande streckkodsbild i din angivna katalog. I det här fallet sparar vi det som "SupplementEAN5.png".

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

Nu har du framgångsrikt konfigurerat och genererat kompletterande streckkodsdata med Aspose.BarCode för .NET. Du kan använda detta tillvägagångssätt för att skapa ett brett utbud av streckkodstyper med varierande tilläggsdata.

## Slutsats

Aspose.BarCode för .NET är ett kraftfullt verktyg för generering och anpassning av streckkoder. I den här guiden gick vi igenom processen att konfigurera och generera kompletterande streckkodsdata steg för steg. Med rätt förutsättningar och lite kodning kan du effektivt arbeta med streckkodsdata och möta dina specifika behov.

 För mer information och avancerad användning, se[Aspose.BarCode för .NET-dokumentation](https://reference.aspose.com/barcode/net/).

## Vanliga frågor

### Kan jag använda Aspose.BarCode för .NET i mitt .NET Core-projekt?
Ja, Aspose.BarCode för .NET är kompatibel med .NET Core.

### Finns det en gratis testversion tillgänglig för Aspose.BarCode för .NET?
 Ja, du kan prova det gratis genom att besöka[den här länken](https://releases.aspose.com/).

### Var kan jag få en tillfällig licens för Aspose.BarCode för .NET?
 Du kan få en tillfällig licens från[den här länken](https://purchase.aspose.com/temporary-license/).

### Stöder Aspose.BarCode ett brett utbud av streckkodstyper?
Ja, den stöder olika streckkodstyper, inklusive EAN-13, QR Code, Code 128 och mer.

### Kan jag anpassa utseendet på de genererade streckkoderna?
Absolut, du kan anpassa dimensioner, färger och andra aspekter av streckkoderna för att uppfylla dina krav.

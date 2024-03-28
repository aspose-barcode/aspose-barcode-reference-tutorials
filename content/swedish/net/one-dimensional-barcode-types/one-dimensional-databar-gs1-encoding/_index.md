---
title: Endimensionell datafält GS1-kodning
linktitle: Endimensionell datafält GS1-kodning
second_title: Aspose.BarCode .NET API
description: Lär dig att skapa Databar GS1-kodade streckkoder i .NET med Aspose.BarCode. Generera streckkoder med lätthet. Följ vår steg-för-steg-guide.
type: docs
weight: 18
url: /sv/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
---

I den här handledningen går vi igenom processen att skapa endimensionella Databar GS1-kodade streckkoder med hjälp av Aspose.BarCode for .NET-biblioteket. Oavsett om du vill generera streckkoder med GS1-kodning eller utan den, så har vi dig täckt. Den här steg-för-steg-guiden hjälper dig att förstå förutsättningarna, importera namnrymder och demonstrera varje exempel för att enkelt skapa Databar GS1-kodade streckkoder.

## Förutsättningar

Innan vi dyker in i koden, se till att du har följande förutsättningar på plats:

1.  Aspose.BarCode för .NET: Du bör ha Aspose.BarCode för .NET installerat. Om du inte redan har gjort det kan du ladda ner det från[här](https://releases.aspose.com/barcode/net/).

2.  Din katalogsökväg: Ersätt`"Your Directory Path"` i kodexemplen med den faktiska sökvägen där du vill spara de genererade streckkodsbilderna.

Nu när du har de nödvändiga förutsättningarna redo, låt oss gå vidare till kodningsdelen.

## Importera namnområden

För att komma igång måste du importera relevanta namnområden för Aspose.BarCode. Lägg till följande kodrader i början av ditt .NET-projekt:

```csharp
using Aspose.BarCode;
using System;
```

## Steg 1: Initiera streckkodsgeneratorn

Det första steget är att initiera BarcodeGenerator-objektet med önskad kodningstyp. I det här fallet använder vi Databar Expanded-kodning. 

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## Steg 2: Generera en streckkod med GS1-kodning

Nu kommer vi att ställa in kodtexten med GS1Encoding check och spara den genererade streckkodsbilden. 

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## Steg 3: Generera en streckkod för variabel kodning

I det här steget kommer vi att generera en streckkod med variabel kodtext utan kontroll av GS1Encoding.

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## Steg 4: Hantera undantag för GS1-kodningskontroll

Om du försöker generera en streckkod med variabel kodtext med GS1Encoding-kontroll aktiverad, kommer det att skapa ett undantag. Så här kan du hantera det:

```csharp
try
{
    gen.CodeText = "ASPOSE";
    gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

Nu har du framgångsrikt skapat endimensionella Databar GS1-kodade streckkoder med Aspose.BarCode för .NET. Du kan ytterligare utforska och anpassa din streckkodsgenerering baserat på dina specifika krav.

## Slutsats

den här handledningen har vi täckt processen att generera endimensionella Databar GS1-kodade streckkoder med Aspose.BarCode för .NET. Vi diskuterade förutsättningarna, importerade de nödvändiga namnrymden och gav steg-för-steg-vägledning för att skapa både GS1-kodade och variabla streckkoder.

 Med Aspose.BarCode för .NET blir streckkodsgenerering en sömlös uppgift, som erbjuder flexibilitet och kontroll över dina streckkodsskapande behov. Om du stöter på några problem eller har frågor, tveka inte att besöka[Aspose.BarCode dokumentation](https://reference.aspose.com/barcode/net/) eller sök hjälp på[Aspose.BarCode supportforum](https://forum.aspose.com/c/barcode/13).

## Vanliga frågor

### 1. Vad är GS1-kodning i streckkoder?
GS1-kodning är en standard som används vid streckkodning för att säkerställa korrekt datastruktur och identifiering. Det används ofta för varor inom detaljhandeln, sjukvården och logistiken för att underlätta korrekt spårning och informationsutbyte.

### 2. Kan jag anpassa utseendet på de genererade streckkoderna?
Ja, du kan anpassa utseendet på streckkoderna som genereras med Aspose.BarCode för .NET. Du har kontroll över olika parametrar som storlek, färg och stil.

### 3. Var kan jag hitta ytterligare resurser och dokumentation för Aspose.BarCode?
 Du hittar omfattande dokumentation och exempel på[Aspose.BarCode dokumentation](https://reference.aspose.com/barcode/net/). Det är en värdefull resurs för lärande och felsökning.

### 4. Finns det en testversion tillgänglig för Aspose.BarCode?
 Ja, du kan få en gratis testversion av Aspose.BarCode för .NET från[här](https://releases.aspose.com/).

### 5. Hur kan jag köpa en licens för Aspose.BarCode för .NET?
 För att köpa en licens för Aspose.BarCode för .NET, besök[köpsidan](https://purchase.aspose.com/buy) på Asposes hemsida.

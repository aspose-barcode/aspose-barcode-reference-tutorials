---
title: Genereer DataMatrix-streepjescodes met Aspose.BarCode voor .NET
linktitle: DataMatrix-versies
second_title: Aspose.BarCode .NET API
description: Leer hoe u DataMatrix-barcodes kunt genereren in .NET met behulp van Aspose.BarCode voor .NET. Aangepaste afmetingen, ECC-ondersteuning en meer.
type: docs
weight: 12
url: /nl/net/datamatrix-barcode-reading/datamatrix-versions/
---
Als u op zoek bent naar een betrouwbare oplossing om DataMatrix-barcodes te genereren in uw .NET-toepassingen, dan is Aspose.BarCode voor .NET de juiste keuze. In deze stapsgewijze handleiding leiden we u door het proces van het gebruik van Aspose.BarCode voor .NET om DataMatrix-barcodes te maken. We splitsen elk voorbeeld op in meerdere stappen, zodat u het gemakkelijk kunt volgen.

## Vereisten

Voordat we in de code duiken, moet je ervoor zorgen dat je aan de volgende vereisten voldoet:
- Een ontwikkelomgeving met .NET-ondersteuning.
-  Een kopie van Aspose.BarCode voor .NET, die u kunt downloaden[deze link](https://releases.aspose.com/barcode/net/).
- Basiskennis van C# en het .NET-framework.

Laten we nu eens kijken naar de DataMatrix-versies en hoe u deze kunt genereren met Aspose.BarCode voor .NET.

## Naamruimten importeren

In elk C#-project is het essentieel om de benodigde naamruimten te importeren. In het geval van Aspose.BarCode moet u het volgende opnemen:

```csharp
using Aspose.BarCode.Generation;
```

 Deze naamruimte biedt toegang tot de`BarcodeGenerator` klasse, wat cruciaal is voor het genereren van streepjescodes.

Laten we het voorbeeld nu in meerdere stappen opsplitsen.

## Stap 1: Stel uw directorypad in

Begin met het definiëren van het directorypad waar u de gegenereerde DataMatrix-barcodes wilt opslaan.

```csharp
string path = "Your Directory Path";
```

 Vervangen`"Your Directory Path"` met het daadwerkelijke pad waar u de streepjescodeafbeeldingen wilt opslaan.

## Stap 2: Initialiseer de streepjescodegenerator

 Maak een exemplaar van de`BarcodeGenerator` class en specificeer het barcodetype als`DataMatrix`. U kunt ook de gegevens opgeven die u in de streepjescode wilt coderen.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Hier vindt u de code voor het genereren van streepjescodes
}
```

## Stap 3: Configureer streepjescode-eigenschappen

U kunt verschillende eigenschappen van de DataMatrix-barcode aanpassen, zoals de afmetingen en het ECC-type (Error Correction Code). Hier is een voorbeeld van het instellen van de X-dimensie op 4 pixels en het kiezen van ECC200:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4;
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

## Stap 4: DataMatrix-versie instellen en opslaan

U kunt de DataMatrix-versie opgeven door het aantal rijen en kolommen in te stellen. Nadat u de versie hebt geconfigureerd, slaat u de streepjescodeafbeelding op.

Om bijvoorbeeld een DataMatrix-barcode met 22 rijen en 22 kolommen te maken met behulp van ECC200:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC200_22x22;
generator.Save($"{path}DataMatrixRows22Columns22Ecc200.png", BarCodeImageFormat.Png);
```

Op dezelfde manier kunt u een streepjescode met verschillende parameters genereren door de versie en het ECC-type indien nodig te wijzigen.

## Stap 5: Herhaal voor andere versies

U kunt stap 4 herhalen voor andere DataMatrix-versies. Om bijvoorbeeld een streepjescode met 12 rijen en 64 kolommen te maken met ECC200:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.DMRE_12x64;
generator.Save($"{path}DataMatrixRows12Columns64Ecc200.png", BarCodeImageFormat.Png);
```

## Stap 6: Wissel van ECC-type

Als u het ECC-type wilt wijzigen in Ecc140, kunt u dit doen door de ECC-eigenschap bij te werken:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;
```

## Stap 7: Genereer streepjescodes met verschillende versies en ECC

Herhaal stap 4 voor andere DataMatrix-versies en ECC-typen, waarbij elke streepjescode wordt opgeslagen met een unieke bestandsnaam.

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC000_140_29x29;
generator.Save($"{path}DataMatrixRows29Columns29Ecc140.png", BarCodeImageFormat.Png);
```

Nu u hebt geleerd hoe u DataMatrix-barcodes kunt genereren met Aspose.BarCode voor .NET, kunt u deze functionaliteit eenvoudig in uw .NET-toepassingen integreren.

## Conclusie

Aspose.BarCode voor .NET vereenvoudigt het proces van het genereren van DataMatrix-barcodes in uw .NET-toepassingen. Met deze stapsgewijze handleiding kunt u barcodes maken met verschillende versies en ECC-typen, waardoor u flexibiliteit en maatwerk krijgt om aan uw specifieke behoeften te voldoen.

 Als u vragen heeft of hulp nodig heeft, aarzel dan niet om langs te komen[Aspose.BarCode voor .NET-documentatie](https://reference.aspose.com/barcode/net/) of bekijk de[Aspose.BarCode-forum](https://forum.aspose.com/c/barcode/13) Voor ondersteuning.

## Veelgestelde vragen

### Vraag 1: Wat is ECC in DataMatrix-barcodes?

A1: ECC (Error Correction Code) is een essentieel onderdeel van DataMatrix-barcodes en helpt de gegevensintegriteit te garanderen. Verschillende ECC-niveaus bieden een verschillende mate van foutcorrectie.

### V2: Kan ik DataMatrix-barcodes met aangepaste afmetingen genereren met Aspose.BarCode voor .NET?

A2: Ja, u kunt de afmetingen van DataMatrix-barcodes aanpassen door het aantal rijen en kolommen in te stellen, zoals gedemonstreerd in de tutorial.

### V3: Waar kan ik Aspose.BarCode voor .NET downloaden?

 A3: U kunt Aspose.BarCode voor .NET downloaden van[deze link](https://releases.aspose.com/barcode/net/).

### V4: Is er een gratis proefversie beschikbaar voor Aspose.BarCode voor .NET?

 A4: Ja, u heeft toegang tot een gratis proefversie van Aspose.BarCode voor .NET[hier](https://releases.aspose.com/).

### V5: Hoe kan ik een tijdelijke licentie verkrijgen voor Aspose.BarCode voor .NET?

 A5: Ga naar om een tijdelijke licentie voor Aspose.BarCode voor .NET te verkrijgen[deze link](https://purchase.aspose.com/temporary-license/).
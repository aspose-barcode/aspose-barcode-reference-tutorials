---
category: general
date: 2026-09-23
description: Le tutoriel du générateur de codes-barres C# montre comment créer des
  images de codes-barres avec des rapports d’aspect personnalisés en utilisant la
  bibliothèque Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- DataBar barcode C#
- barcode aspect ratio
- Aspose.BarCode C#
- barcode image export
language: fr
lastmod: 2026-09-23
og_description: Le guide du générateur de codes-barres C# vous explique comment créer
  des images de codes-barres, ajuster les rapports d’aspect et exporter des fichiers
  PNG à l’aide d’Aspose.BarCode.
og_image_alt: Screenshot of a barcode created with a C# barcode generator
og_title: Créez des codes‑barres de haute qualité avec un générateur de codes‑barres
  C#
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  headline: How to use a C# barcode generator for DataBar codes
  type: TechArticle
- description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  name: How to use a C# barcode generator for DataBar codes
  steps:
  - name: Switching to another barcode type
    text: 'If you need a QR code, Code 128, or PDF417, replace the enum value in the
      constructor:'
  - name: Handling unsupported characters
    text: 'The `BarcodeGenerator` validates the input string against the selected
      symbology. Supplying an illegal character throws an `ArgumentException`. Wrap
      the creation in a try‑catch block to provide a friendly error message:'
  - name: Exporting to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the second argument
      of `Save` accordingly:'
  - name: High‑resolution output for printing
    text: 'When printing on high‑DPI printers, increase the X‑dimension and optionally
      set the `Resolution` property:'
  type: HowTo
tags:
- barcode
- c#
- Aspose
title: Comment utiliser un générateur de codes‑barres C# pour les codes DataBar
url: /fr/python-java/general/how-to-use-a-c-barcode-generator-for-databar-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment utiliser un générateur de code-barres C# pour les codes DataBar

Si vous avez besoin d'un **générateur de code-barres c#** capable de produire des symboles DataBar empilés Omni‑Directional, ce guide vous fournit une solution complète, prête à l'emploi. Vous verrez comment générer des images de code-barres, contrôler la X‑dimension et modifier le rapport d'aspect sans quitter l'IDE.

La génération de codes-barres est une exigence courante pour les systèmes d'inventaire, les étiquettes d'expédition et les applications de point de vente. À la fin de ce tutoriel, vous pourrez créer des fichiers PNG avec le rapport d'aspect de votre choix, et vous comprendrez comment adapter le code à d'autres types de codes-barres.

## Prérequis

* .NET 6.0 SDK ou version ultérieure installé  
* Visual Studio 2022 (ou tout éditeur C# de votre choix)  
* Une référence NuGet à **Aspose.BarCode** – la bibliothèque qui alimente la classe `BarcodeGenerator`  

Vous n'avez pas besoin d'une bibliothèque graphique séparée ; Aspose.BarCode gère l'encodage d'image en interne.

## Étape 1 : Installer le package NuGet Aspose.BarCode

Ouvrez un terminal dans le dossier de votre projet et exécutez :

```bash
dotnet add package Aspose.BarCode
```

La commande ajoute la dernière version stable de la bibliothèque à votre fichier de projet, rendant la classe `BarcodeGenerator` disponible pour utilisation.

## Étape 2 : Définir le dossier de sortie

Choisissez un dossier où les fichiers PNG générés seront enregistrés. L'utilisation d'un chemin absolu ou relatif fonctionne de la même manière, mais un chemin relatif rend le projet portable.

```csharp
// Define the output folder (relative to the project root)
string outputFolder = "GeneratedBarcodes/";
Directory.CreateDirectory(outputFolder); // Ensure the folder exists
```

Créer le répertoire de façon programmatique évite les erreurs d'exécution si le dossier est absent.

## Étape 3 : Instancier le générateur de code-barres C# avec des données d'exemple

Le constructeur `BarcodeGenerator` nécessite deux arguments : le type de code-barres et la chaîne de données. Pour un symbole DataBar empilé Omni‑Directional, vous utilisez `EncodeTypes.DatabarStackedOmniDirectional`.

```csharp
// Create a barcode generator for a DataBar stacked Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

La chaîne de données suit le format GS1 Application Identifier. L'énumération `EncodeTypes` contient plus de 150 normes de code-barres ; vous pouvez passer à un autre type en modifiant la valeur de l'énumération.

## Étape 4 : Définir la X‑dimension (taille en pixels) du code-barres

La X‑dimension contrôle la largeur de la barre la plus étroite. Une valeur de 2 pixels donne une image nette et haute résolution adaptée à la plupart des écrans.

```csharp
// Set the X‑dimension to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Ajuster la X‑dimension est optionnel, mais cela vous donne un contrôle fin sur la densité visuelle du code-barres.

## Étape 5 : Générer un code-barres avec un rapport d'aspect de 15 et l'enregistrer en PNG

La propriété `AspectRatio` appartient au sous‑objet `DataBar`. Modifier cette valeur étire ou compresse le code-barres verticalement tout en préservant les données encodées.

```csharp
// Set aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

La méthode `Save` écrit le code-barres sur le chemin de fichier spécifié. L'énumération `BarCodeImageFormat.Png` assure une compression sans perte.

![exemple de sortie du générateur de code-barres c#](generated_barcode_example.png)

*Image : code-barres généré avec un rapport d'aspect de 15.*

## Étape 6 : Modifier le rapport d'aspect à 30 et générer une seconde image

Réutiliser la même instance `BarcodeGenerator` évite d'allouer un nouvel objet. Il suffit de mettre à jour `AspectRatio` et d'appeler à nouveau `Save`.

```csharp
// Update aspect ratio to 30 and save a second image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

Vous avez maintenant deux fichiers PNG qui ne diffèrent que par l'échelle verticale. Cette technique est utile lorsque vous avez besoin des mêmes données rendues pour différentes tailles d'étiquette.

## Variations courantes et cas limites

### Passer à un autre type de code-barres

Si vous avez besoin d'un QR code, Code 128 ou PDF417, remplacez la valeur de l'énumération dans le constructeur :

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(
    EncodeTypes.QR, "https://example.com");
```

Toutes les autres étapes de configuration (X‑dimension, enregistrement) restent identiques.

### Gestion des caractères non pris en charge

Le `BarcodeGenerator` valide la chaîne d'entrée par rapport à la symbologie sélectionnée. Fournir un caractère illégal déclenche une `ArgumentException`. Enveloppez la création dans un bloc try‑catch pour fournir un message d'erreur convivial :

```csharp
try
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid data for the selected barcode type: {ex.Message}");
}
```

### Exportation vers d'autres formats d'image

Aspose.BarCode prend en charge BMP, JPEG, TIFF et SVG. Modifiez le deuxième argument de `Save` en conséquence :

```csharp
barcodeGenerator.Save($"{outputFolder}Databar.svg", BarCodeImageFormat.Svg);
```

### Sortie haute résolution pour l'impression

Lors de l'impression sur des imprimantes haute DPI, augmentez la X‑dimension et, éventuellement, définissez la propriété `Resolution` :

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.ImageResolution.Dpi = 300;
```

Ces paramètres produisent des fichiers plus volumineux mais conservent des bords nets sur les supports physiques.

## Résultat attendu

L'exécution du programme complet crée les fichiers suivants dans `GeneratedBarcodes/` :

* `DatabarAspectRatio15.png` – un code DataBar de hauteur standard  
* `DatabarAspectRatio30.png` – une version étirée verticalement  

Les deux images contiennent les mêmes données GS1 encodées, et vous pouvez les vérifier avec n'importe quelle application de lecture de code-barres.

## Code source complet

Copiez le code ci‑dessous dans un nouveau projet console (`dotnet new console`) et exécutez‑le. Le programme affiche des messages d'état dans la console et écrit les fichiers PNG sur le disque.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Define the output folder
        string outputFolder = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputFolder);

        // Step 3: Create a C# barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Step 4: Set common barcode properties (pixel size of X‑dimension)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 5: Generate a barcode with aspect ratio 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        string file15 = Path.Combine(outputFolder, "DatabarAspectRatio15.png");
        barcodeGenerator.Save(file15, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

        // Step 6: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        string file30 = Path.Combine(outputFolder, "DatabarAspectRatio30.png");
        barcodeGenerator.Save(file30, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
    }
}
```

L'exécution du programme produit une sortie console similaire à :

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

## Conclusion

Vous disposez maintenant d'un **générateur de code-barres c#** capable de créer des symboles DataBar empilés Omni‑Directional, d'ajuster la X‑dimension et d'exporter des fichiers PNG avec des rapports d'aspect personnalisés. Le même modèle fonctionne pour toute autre symbologie de code-barres prise en charge par Aspose.BarCode, ce qui facilite l'intégration de la création de code-barres dans les solutions d'inventaire, d'expédition ou de point de vente.

Si vous souhaitez aller plus loin, essayez :

* Générer des QR codes ou des symboles PDF417 (`how to generate barcode` pour les applications mobiles)  
* Exporter en SVG pour des graphiques web évolutifs  
* Intégrer les images générées directement dans les factures PDF à l'aide d'Aspose.PDF  

Expérimentez avec différentes valeurs `AspectRatio`, tailles de X‑dimension et formats de sortie pour correspondre exactement au

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment générer un code-barres Aztec avec un rapport d'aspect personnalisé en utilisant Aspose.BarCode pour .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Comment ajuster la taille du code-barres – Rapport d'aspect Codablock F avec Aspose.BarCode pour .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [Comment générer et ajuster la hauteur du code-barres One‑Dimensional Databar en utilisant Aspose.BarCode pour .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
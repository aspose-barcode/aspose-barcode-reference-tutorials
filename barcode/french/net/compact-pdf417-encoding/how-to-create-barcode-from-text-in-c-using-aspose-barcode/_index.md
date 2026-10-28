---
category: general
date: 2026-10-28
description: Créer un code‑barres à partir de texte en C# avec Aspose.BarCode. Apprenez
  à générer une image de code‑barres PDF417, à définir les colonnes, à ajuster la
  dimension X et à activer le mode compact.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate barcode c#
- generate pdf417 barcode
- pdf417 barcode image
language: fr
lastmod: 2026-10-28
og_description: Créer un code-barres à partir du texte en C# avec Aspose.BarCode.
  Ce tutoriel montre comment générer une image de code-barres PDF417, personnaliser
  la taille, les colonnes et le mode compact.
og_image_alt: Screenshot showing a compact PDF417 barcode created from text using
  C#
og_title: Créer un code‑barres à partir de texte en C# – guide étape par étape
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode from text in C# with Aspose.BarCode. Learn to generate
    PDF417 barcode image, set columns, adjust X‑dimension, and enable compact mode.
  headline: How to create barcode from text in C# using Aspose.BarCode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- image generation
title: Comment créer un code‑barres à partir de texte en C# avec Aspose.BarCode
url: /fr/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code-barres à partir de texte en C# avec Aspose.BarCode

Si vous devez **créer un code-barres à partir de texte** dans une application .NET, ce guide fournit une solution prête à l'emploi. Vous verrez comment **générer des images de code-barres PDF417**, contrôler la largeur du module, le nombre de colonnes et activer le mode compact sans quitter votre IDE.

Le tutoriel couvre tout ce qui est nécessaire pour **générer du code barcode C#**, depuis l'installation de la bibliothèque jusqu'à l'enregistrement du fichier PNG final. À la fin, vous pourrez intégrer un code-barres PDF417 haute densité dans des rapports, des tickets ou des étiquettes d'inventaire.

## Prérequis

* SDK .NET 6.0 ou version ultérieure installé  
* Visual Studio 2022 (ou tout éditeur qui prend en charge .NET)  
* Accès Internet pour télécharger le package NuGet Aspose.BarCode pour .NET  

Ces éléments sont suffisants pour compiler et exécuter l'exemple sous Windows, Linux ou macOS.

## Étape 1 : Installer le package NuGet Aspose.BarCode

La bibliothèque qui alimente la génération de code-barres est **Aspose.BarCode for .NET**. Installez‑la avec la CLI .NET :

```bash
dotnet add package Aspose.BarCode
```

Le package ajoute l'espace de noms `Aspose.BarCode`, qui contient la classe `BarcodeGenerator` utilisée tout au long de ce tutoriel.

## Étape 2 : Créer un projet console et ajouter le code

Créez un nouveau projet console et remplacez le fichier `Program.cs` généré par le code suivant. Le programme montre comment **créer un code-barres à partir de texte** et l'enregistrer en tant qu'**image de code-barres PDF417**.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 2.1: Define the text to encode.
            // Unicode characters such as Å, ó, and © are supported out of the box.
            string data = "Åspóse.Barcóde©";

            // Step 2.2: Initialize the PDF417 generator with the desired text.
            // EncodeTypes.Pdf417 tells the generator which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // Step 2.3: Set the X‑dimension (module width) to 2 pixels for a denser barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 2.4: Define the number of columns in the PDF417 symbol.
            // Fewer columns produce a taller barcode; three columns keep it compact.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Step 2.5: Enable compact mode by truncating the right‑hand column.
            // Truncate reduces the overall width while preserving data integrity.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Step 2.6: Choose the output folder and file name.
            string outputPath = "CompactPdf417.png";

            // Step 2.7: Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

### Pourquoi chaque ligne est importante

* **`EncodeTypes.Pdf417`** sélectionne la symbologie PDF417, idéale pour encoder de grandes quantités de données dans un format bidimensionnel.  
* **`XDimension.Pixels = 2`** réduit la largeur du module, rendant le code-barres plus dense et plus adapté aux espaces limités.  
* **`Pdf417.Columns = 3`** contrôle le nombre de colonnes de données verticales ; un nombre plus faible produit un code-barres plus haut mais plus étroit.  
* **`Pdf417.Truncate = true`** active le mode compact, en supprimant les colonnes inutilisées du côté droit. C’est le paramètre clé qui transforme un PDF417 standard en **image de code-barres PDF417 compact**.  

## Étape 3 : Compiler et exécuter le projet

Exécutez les commandes suivantes dans le répertoire du projet :

```bash
dotnet build
dotnet run
```

Lorsque le programme se termine, vous verrez un message dans la console confirmant l'emplacement du fichier. Ouvrez `CompactPdf417.png` avec n'importe quel visualiseur d'images pour vérifier le résultat.

**Sortie attendue** – un PNG à fort contraste affichant un code-barres PDF417 compact qui encode la chaîne `Åspóse.Barcóde©`. Scanner l'image avec un lecteur de code-barres standard renvoie le texte original, confirmant que **generate pdf417 barcode** a réussi.

## Étape 4 : Personnaliser le code-barres pour différents scénarios

Bien que l'exemple utilise un nombre de colonnes fixe et une X‑dimension, vous pouvez adapter le générateur à d'autres exigences :

| Scénario | Ajustement |
|----------|------------|
| Charge de données plus importante | Augmenter `Pdf417.Columns` ou définir `Pdf417.Rows` manuellement |
| Fiabilité de lecture supérieure | Augmenter `XDimension.Pixels` à 3 ou 4 |
| Format d'image différent | Remplacer `BarCodeImageFormat.Png` par `Jpeg` ou `Bmp` |
| Arrière-plan transparent | Définir `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent` |

Ces options vous permettent de **generate barcode C#** des solutions qui s'adaptent aux applications mobiles, aux rapports de bureau ou aux services web.

## Étape 5 : Gestion des cas limites et bonnes pratiques

* **Prise en charge Unicode** – Le générateur encode automatiquement les caractères Unicode, mais assurez‑vous que votre chaîne source est encodée en UTF‑8 si vous la lisez depuis un fichier.  
* **Texte long** – PDF417 peut encoder jusqu'à 1 850 caractères alphanumériques. Si vous dépassez cette limite, la bibliothèque lève une exception ; divisez les données en plusieurs codes-barres ou passez à une symbologie à plus grande capacité.  
* **Gestion des erreurs** – Enveloppez le code de génération dans un bloc `try/catch` pour capturer `BarCodeException` et fournir un message d'erreur convivial.  
* **Performance** – Générer de nombreux codes-barres dans une boucle bénéficie de la réutilisation d'une seule instance `BarcodeGenerator` et de la mise à jour uniquement de `CodeText` entre les itérations.

```csharp
try
{
    generator.CodeText = nextText;
    generator.Save($"barcode_{i}.png", BarCodeImageFormat.Png);
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

## Listing complet du code source

Ci‑dessous se trouve le programme complet et autonome que vous pouvez copier dans `Program.cs`. Aucun fichier supplémentaire n'est requis.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            string data = "Åspóse.Barcóde©";

            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

L'exécution de ce programme crée l'**image de code-barres pdf417** illustrée ci‑dessous.

![Code-barres PDF417 compact créé à partir de texte avec C#](/images/compact-pdf417.png){.img-fluid alt="exemple de création de code-barres à partir de texte montrant une image de code-barres PDF417 compact"}

*Description de l'image : Le fichier PNG affiche un code-barres PDF417 compact qui encode la chaîne « Åspóse.Barcóde© ». *

## Conclusion

Vous savez maintenant comment **create barcode from text** en C# et produire une **image de code-barres PDF417** avec des dimensions personnalisées et le mode compact. L'exemple montre les étapes essentielles pour **generate barcode C#**, gérer les données Unicode et ajuster les paramètres visuels pour différents scénarios de déploiement.

Ensuite, explorez des sujets connexes tels que **generate QR code in C#**, **add barcode to PDF documents**, ou **embed barcodes in ASP.NET Core APIs**. Chacun de ces sujets s'appuie sur les mêmes fondamentaux `BarcodeGenerator` présentés ici.

Bon codage, et profitez de l'intégration des codes-barres dans vos solutions .NET !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Générer un code-barres PDF417 en C# – Créer un code-barres PDF417 C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/)
- [Comment générer un code-barres PDF417 avec Aspose.BarCode en C#](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/)
- [Comment créer une image de code-barres PDF417 en C# – guide complet](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
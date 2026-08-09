---
category: general
date: 2026-08-09
description: Créez une image de code‑barres avec un générateur de codes‑barres C#
  et apprenez à générer plusieurs codes‑barres avec des rapports d’aspect personnalisés
  en quelques minutes.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- c# barcode generator
- generate multiple barcodes
- barcode aspect ratio
- barcode image format
language: fr
lastmod: 2026-08-09
og_description: Créez une image de code-barres à l'aide d'un générateur de codes-barres
  en C#. Ce tutoriel montre comment générer plusieurs codes-barres, ajuster les rapports
  d'aspect et enregistrer des fichiers PNG efficacement.
og_image_alt: Example of create barcode image output with aspect ratios 15 and 30
  using C# barcode generator
og_title: Créer une image de code-barres avec le générateur de code-barres C# – guide
  rapide
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create barcode image with a C# barcode generator and learn to generate
    multiple barcodes with custom aspect ratios in minutes.
  headline: Create barcode image with C# barcode generator – guide
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: Créer une image de code-barres avec le générateur de code-barres C# – guide
url: /fr/python-java/general/create-barcode-image-with-c-barcode-generator-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une image de code-barres avec le générateur de code-barres C# – guide

Si vous devez **créer une image de code-barres** rapidement, ce guide vous montre comment le faire avec un générateur de code-barres C#. Vous apprendrez à générer plusieurs codes-barres, à modifier le rapport d'aspect et à enregistrer chaque image au format PNG.

Générer des images de code-barres est une tâche courante lors de la création de systèmes d'inventaire, de terminaux point de vente ou d'étiquettes d'expédition. À la fin de ce tutoriel, vous disposerez de deux fichiers PNG prêts à l'emploi qui illustrent différents rapports d'aspect, et vous comprendrez comment étendre l'approche à n'importe quel nombre de codes-barres.

## Prérequis

* SDK .NET 6.0 ou version ultérieure installé  
* Visual Studio 2022 (ou tout IDE prenant en charge C#)  
* Une référence à une bibliothèque de codes-barres qui prend en charge DataBar Stacked Omnidirectional (par exemple, **Aspose.BarCode for .NET**). Les extraits de code utilisent l'API Aspose, mais les concepts s'appliquent à toute bibliothèque avec des propriétés similaires.

Vous n'avez pas besoin d'une base de données ou d'un serveur web séparé — il s'agit d'une simple application console.

## Étape 1 : Configurer le projet console

Créez un nouveau projet console et ajoutez la bibliothèque de codes-barres via NuGet.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

La commande `dotnet add package` récupère la dernière version stable de **Aspose.BarCode**, qui fournit la classe `BarcodeGenerator` utilisée plus tard.

## Étape 2 : Écrire le programme complet

Ouvrez *Program.cs* et remplacez son contenu par l'exemple complet ci‑dessous. Le programme crée une **image de code-barres**, modifie le rapport d'aspect et enregistre deux fichiers PNG.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // -----------------------------------------------------------------
            // 1️⃣ Create a DataBar Stacked Omnidirectional generator with sample data
            // -----------------------------------------------------------------
            // The EncodeTypes enum tells the generator which barcode symbology to use.
            // Here we use DataBar Stacked Omnidirectional (GS1 DataBar) and encode
            // a sample GTIN (01) followed by a 14‑digit numeric string.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // -----------------------------------------------------------------
            // 2️⃣ Configure common parameters (pixel size and X‑dimension)
            // -----------------------------------------------------------------
            // XDimension.Pixels controls the width of the smallest bar in the image.
            // A value of 2 gives a clear, high‑resolution output without increasing file size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // -----------------------------------------------------------------
            // 3️⃣ Set the first aspect ratio (15) and save the image
            // -----------------------------------------------------------------
            // AspectRatio influences the height of the barcode relative to its width.
            // An aspect ratio of 15 is typical for compact labels.
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;

            string outputFolder = "BarcodeOutputs/";
            System.IO.Directory.CreateDirectory(outputFolder); // Ensure folder exists

            string file15 = $"{outputFolder}DatabarAspectRatio15.png";
            generator.Save(file15, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with aspect ratio 15 → {file15}");

            // -----------------------------------------------------------------
            // 4️⃣ Change the aspect ratio to 30 and save a second image
            // -----------------------------------------------------------------
            // A larger aspect ratio (e.g., 30) produces a taller barcode, useful for
            // scanning devices that expect more vertical space.
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;

            string file30 = $"{outputFolder}DatabarAspectRatio30.png";
            generator.Save(file30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with aspect ratio 30 → {file30}");

            // -----------------------------------------------------------------
            // 5️⃣ Verify that both files exist
            // -----------------------------------------------------------------
            Console.WriteLine("\nVerification:");
            Console.WriteLine($"File 15 exists: {System.IO.File.Exists(file15)}");
            Console.WriteLine($"File 30 exists: {System.IO.File.Exists(file30)}");
        }
    }
}
```

### Pourquoi chaque partie est importante

* **Créer une image de code-barres** – Le constructeur `BarcodeGenerator` initialise l'objet avec la symbologie et les données souhaitées.  
* **c# barcode generator** – La propriété `Parameters` vous donne un contrôle total sur les options de rendu ; définir `XDimension.Pixels` garantit que chaque barre est nette à l'écran.  
* **generate multiple barcodes** – En modifiant `DataBar.AspectRatio` entre les sauvegardes, la même instance du générateur produit deux images distinctes sans recréer l'objet, ce qui est plus efficace.

## Étape 3 : Exécuter le programme et voir les résultats

Exécutez l'application :

```bash
dotnet run
```

Vous devriez voir une sortie console similaire à :

```
Saved barcode with aspect ratio 15 → BarcodeOutputs/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 → BarcodeOutputs/DatabarAspectRatio30.png

Verification:
File 15 exists: True
File 30 exists: True
```

Ouvrez le dossier `BarcodeOutputs`. Vous y trouverez deux fichiers PNG :

* **DatabarAspectRatio15.png** – un code-barres compact adapté aux étiquettes de hauteur limitée.  
* **DatabarAspectRatio30.png** – un code-barres plus haut que de nombreux lecteurs lisent plus fiable à distance.

Les deux images sont prêtes à être intégrées dans des PDF, imprimées sur des reçus ou envoyées à une application mobile.

## Étape 4 : Étendre la solution pour générer n'importe quel nombre de codes-barres

Le modèle présenté ci‑dessus s'adapte facilement :

```csharp
int[] ratios = { 10, 15, 20, 30, 40 };
foreach (int ratio in ratios)
{
    generator.Parameters.Barcode.DataBar.AspectRatio = ratio;
    string path = $"{outputFolder}DatabarAspectRatio{ratio}.png";
    generator.Save(path, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved aspect ratio {ratio} → {path}");
}
```

* **generate multiple barcodes** – La boucle parcourt un tableau de rapports d'aspect, créant une **image de code-barres** distincte pour chaque valeur.  
* Ajustez les `EncodeTypes` ou la chaîne encodée pour produire des QR codes, Code 128 ou d'autres symbologies sans modifier la logique environnante.

## Conseils pratiques et pièges courants

| Conseil | Explication |
|-----|-------------|
| **Réutiliser le même générateur** | Ré‑initialiser `BarcodeGenerator` pour chaque image ajoute une surcharge inutile. Modifier les paramètres entre les appels `Save` est plus rapide et utilise moins de mémoire. |
| **Valider le dossier de sortie** | Appelez toujours `Directory.CreateDirectory` avant d'enregistrer ; sinon `Save` lève une `DirectoryNotFoundException`. |
| **Choisir une X‑dimension appropriée** | Des valeurs de pixels très faibles (par ex., 1) peuvent rendre le code-barres illisible sur des écrans basse résolution. Des valeurs de 2–3 fonctionnent bien pour la plupart des imprimantes. |
| **Faire attention à l'encodage** | GS1 DataBar attend un préfixe `(01)` pour le GTIN. Si vous omettez les parenthèses, la bibliothèque peut générer un code-barres invalide. |
| **Tester avec un vrai scanner** | L'inspection visuelle ne suffit pas. Testez les fichiers PNG avec le matériel de scanner réel que vous prévoyez d'utiliser. |

## Résultat attendu (description visuelle)

*Les deux fichiers PNG affichent un code-barres DataBar Stacked Omnidirectional sombre sur fond clair. La version avec un rapport d'aspect 15 est plus courte, tandis que celle avec un rapport d'aspect 30 est approximativement deux fois plus haute.*  

Si vous intégrez les images dans un document, elles s'afficheront nettes car nous avons défini `XDimension.Pixels = 2`.

## Conclusion

Vous savez maintenant comment **créer des fichiers d'image de code-barres** en utilisant un **générateur de code-barres C#**, et vous pouvez **générer plusieurs codes-barres** en ajustant le rapport d'aspect ou tout autre paramètre. L'exemple complet et exécutable montre les meilleures pratiques telles que la réutilisation de l'instance du générateur, la gestion des dossiers de sortie et la vérification de la création des fichiers.

Ensuite, vous pourriez explorer :

* Ajouter des couleurs personnalisées avec `generator.Parameters.Barcode.Color` (mot‑clé secondaire : **c# barcode generator**)  
* Exporter vers d'autres formats comme JPEG ou SVG (`BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Svg`)  
* Intégrer la logique de création de code-barres dans une Web API pour fournir des images à la demande (mot‑clé secondaire

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités d'API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Créer un PNG de code-barres – Ratio d'aspect DataMatrix – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [Tutoriel générateur de code-barres C# – Personnaliser les rapports d'aspect du code 16K avec Aspose.BarCode pour .NET](/barcode/english/net/code-16k-encoding/code-16k-aspect-ratio-customization/)
- [Comment générer un code-barres Aztec avec un rapport d'aspect personnalisé en utilisant Aspose.BarCode pour .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
---
category: general
date: 2026-11-17
description: Créer une image de code‑barres en C# à l’aide de la bibliothèque Barcode
  Generator. Suivez ce guide pour apprendre à générer des codes DataBar empilés omnidirectionnels
  étape par étape.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- how to generate databar
language: fr
lastmod: 2026-11-17
og_description: Créer une image de code-barres en C# avec un exemple concis. Apprenez
  à générer des codes-barres DataBar empilés omnidirectionnels à l'aide de la bibliothèque
  Barcode Generator.
og_image_alt: Screenshot showing a generated barcode image created with C# code
og_title: Créer une image de code-barres en C# – guide complet des codes DataBar
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Create barcode image in C# using the Barcode Generator library. Follow
    this guide to learn how to generate DataBar stacked omnidirectional codes step‑by‑step.
  headline: How to create barcode image in C# with DataBar stacked omnidirectional
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Comment créer une image de code‑barres en C# avec DataBar empilé omnidirectionnel
url: /fr/python-java/general/how-to-create-barcode-image-in-c-with-databar-stacked-omnidi/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer une image de code‑barres en C# avec DataBar empilé omnidirectionnel

Si vous devez **créer une image de code‑barres** dans une application .NET, ce tutoriel vous montre une solution complète, prête à l’emploi. Vous verrez exactement comment utiliser l’API **Barcode Generator C#** pour produire un DataBar empilé omnidirectionnel, le format couvert par la requête *how to generate databar*.

Le guide parcourt chaque étape requise — de l’installation de la bibliothèque à l’ajustement du ratio d’aspect — afin que vous puissiez copier le code, l’exécuter et obtenir immédiatement un fichier PNG. Aucune recherche dans une documentation externe n’est nécessaire.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

* le SDK .NET 6.0 ou une version ultérieure installé (l’exemple fonctionne également avec .NET Framework 4.7+)
* un environnement de développement tel que Visual Studio 2022 ou VS Code
* le package NuGet **Aspose.BarCode for .NET** (la bibliothèque qui fournit `BarcodeGenerator`)

Vous pouvez ajouter le package avec la commande suivante :

```bash
dotnet add package Aspose.BarCode
```

> **Astuce :** Utilisez le drapeau `--version` pour verrouiller le package à la dernière version stable, par ex., `dotnet add package Aspose.BarCode --version 23.9`.

## Étape 1 : Configurer le projet et importer les espaces de noms

Créez un nouveau projet console et référencez les espaces de noms requis. Cette étape prépare l’environnement pour le code **barcode generator c#** qui suit.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // All barcode generation logic lives here
```

L’espace de noms `Aspose.BarCode.Generation` contient la classe `BarcodeGenerator`, qui constitue le cœur du flux de travail **create barcode image**.

## Étape 2 : Initialiser le BarcodeGenerator pour un DataBar empilé omnidirectionnel

Le générateur a besoin de deux informations : le type de code‑barres et les données à encoder. La valeur d’énumération `EncodeTypes.DatabarStackedOmniDirectional` sélectionne la variante exacte de DataBar requise par les scénarios *how to generate databar*.

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // Example GTIN-14 payload
```

*Pourquoi c’est important :* choisir la bonne valeur `EncodeTypes` garantit que l’image résultante respecte les spécifications industrielles pour la lecture en magasin.

## Étape 3 : Définir la taille du module (dimension X) en pixels

La densité visuelle d’un code‑barres est contrôlée par la dimension X. La définir à une valeur de pixel raisonnable assure que l’image soit lisible à l’écran comme à l’impression.

```csharp
            // Step 3: Define the module size (X‑dimension) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Si vous avez besoin d’un code‑barres plus grand pour une impression basse résolution, augmentez la valeur en pixels en conséquence.

## Étape 4 : Ajuster le ratio d’aspect du DataBar pour rendre les rangées plus hautes

Le DataBar empilé omnidirectionnel se compose de deux rangées. Modifier le `AspectRatio` vous permet de contrôler la hauteur de chaque rangée, ce qui peut être utile lorsque la taille par défaut paraît trop compacte.

```csharp
            // Step 4: Adjust the DataBar aspect ratio to make rows taller
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

Un ratio d’aspect de `15` est un choix courant pour les étiquettes de détail ; vous pouvez expérimenter avec des valeurs entre `10` et `20` pour répondre à des exigences de mise en page spécifiques.

## Étape 5 : Enregistrer le code‑barres généré sous forme d’image PNG

Enfin, écrivez l’image sur le disque. Le PNG est sans perte, ce qui le rend idéal pour un traitement ultérieur ou une insertion dans des PDF.

```csharp
            // Step 5: Save the generated barcode as a PNG image
            string outputPath = "DatabarAspectRatio15.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to {outputPath}");
        }
    }
}
```

L’exécution du programme produit un fichier nommé **DatabarAspectRatio15.png** dans le répertoire de sortie du projet. L’ouverture du fichier montre un code‑barres net, à fort contraste, prêt à être scanné.

### Résultat attendu

L’image enregistrée ressemble à l’illustration ci‑dessous (l’image réelle est omise pour des raisons de concision).

*Texte alternatif pour l’image d’exemple :* **create barcode image** – un fichier PNG affichant un DataBar empilé omnidirectionnel avec un ratio d’aspect de 15.

## Variations courantes et cas limites

| Situation | Ajustement |
|-----------|------------|
| **Longueur de charge utile différente** | Remplacez la chaîne GTIN par tout contenu DataBar valide (par ex., `(01)01234567890123`). |
| **Résolution supérieure pour impressions larges** | Augmentez `XDimension.Pixels` à 4 ou 5 et, éventuellement, définissez `Resolution` dans `Parameters.Image`. |
| **Autres formats DataBar** | Utilisez `EncodeTypes.DatabarStacked` pour une variante à deux rangées sans capacité omnidirectionnelle. |
| **Enregistrement en JPEG** | Changez `BarCodeImageFormat.Png` en `BarCodeImageFormat.Jpeg` et, éventuellement, définissez `Quality`. |

Ces variations répondent à la question plus large *how to generate databar* en montrant que le même générateur peut être reconfiguré pour plusieurs familles DataBar.

## Récapitulatif du code source complet

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // Define the module size (X‑dimension) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Adjust the DataBar aspect ratio to make rows taller
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;

            // Save the generated barcode as a PNG image
            string outputPath = "DatabarAspectRatio15.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to {outputPath}");
        }
    }
}
```

Copiez le code dans `Program.cs`, restaurez les packages NuGet, puis exécutez `dotnet run`. La console confirmera l’emplacement de l’image, et vous pourrez ouvrir le PNG pour vérifier le résultat **create barcode image**.

## Conclusion

Vous savez maintenant comment **create barcode image** en C# en utilisant la bibliothèque Barcode Generator et comment **generate DataBar** avec un contrôle précis de la taille et du ratio d’aspect. L’exemple complet montre chaque paramètre requis — de l’initialisation de `BarcodeGenerator` à l’exportation d’un fichier PNG— afin que vous puissiez intégrer la création de codes‑barres dans n’importe quelle application .NET sans recherche supplémentaire.

### Et après ?

* Explorez d’autres symbologies de code‑barres avec `EncodeTypes` (par ex., QR, Code128) – une extension naturelle du flux de travail **barcode generator c#**.  
* Combinez l’image générée avec des rapports PDF ou Excel en utilisant Aspose.PDF ou Aspose.Cells.  
* Ajustez la couleur, ajoutez des marges, ou intégrez le code‑barres dans une API web pour une génération à la demande.

N’hésitez pas à expérimenter avec les paramètres, et laissez ce code servir de base fiable pour tous vos futurs projets liés aux codes‑barres. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment utiliser un générateur de code‑barres C# pour créer des codes‑barres DataBar](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)
- [Comment utiliser un générateur de code‑barres C# pour créer des codes‑barres DataBar omnidirectionnels](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [Comment créer un code‑barres DataBar empilé en C# – guide pas à pas](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
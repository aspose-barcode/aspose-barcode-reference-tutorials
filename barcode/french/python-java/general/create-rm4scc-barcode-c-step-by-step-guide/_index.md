---
category: general
date: 2026-09-29
description: Créer un code‑barres RM4SCC en C# avec un exemple complet de code et
  apprendre à générer un code‑barres Planet en utilisant la même bibliothèque. Inclut
  des options de hauteur automatique et fixe.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create rm4scc barcode c#
- barcode generator example c#
- how to generate planet barcode
language: fr
lastmod: 2026-09-29
og_description: Créer un code‑barres RM4SCC en C# avec un exemple prêt à l’emploi.
  Le guide montre également comment générer un code‑barres Planet, en couvrant les
  hauteurs de barres automatiques et fixes.
og_image_alt: Screenshot showing a generated RM4SCC barcode created with C#
og_title: Créer un code‑barres RM4SCC en C# – tutoriel complet du générateur
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create RM4SCC barcode C# with a full code example and learn how to
    generate Planet barcode using the same library. Includes auto and fixed height
    options.
  headline: Create RM4SCC barcode C# – step‑by‑step guide
  type: TechArticle
tags:
- C#
- barcode
- Aspose
title: Créer un code‑barres RM4SCC C# – guide pas à pas
url: /fr/python-java/general/create-rm4scc-barcode-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code-barres RM4SCC C# – guide étape par étape

Si vous devez **créer un code-barres RM4SCC C#** rapidement, ce guide vous montre un exemple complet et exécutable. Vous verrez également un **exemple de générateur de code-barres C#** qui démontre **comment générer un code-barres Planet** dans le même projet.  

Le code utilise la bibliothèque Aspose.BarCode for .NET, qui prend en charge les normes postales (RM4SCC, Planet) ainsi qu’une large gamme de symbologies linéaires et 2‑D. À la fin de ce tutoriel, vous serez capable de :

* Générer un code-barres RM4SCC avec calcul automatique de la hauteur.  
* Générer le même code-barres avec une hauteur de barre fixe.  
* Créer un code-barres Planet en utilisant les mêmes étapes de configuration.  

Aucun service externe n’est requis — tout s’exécute localement sur n’importe quel environnement .NET 6+.

## Prérequis

| Exigence | Pourquoi c’est important |
|----------|---------------------------|
| .NET 6 SDK ou version ultérieure | La bibliothèque cible .NET Standard 2.0+, donc .NET 6 garantit la compatibilité. |
| Visual Studio 2022 (ou tout IDE) | Fournit IntelliSense et une gestion de projet simplifiée. |
| Aspose.BarCode for .NET NuGet package | Contient `BarcodeGenerator`, `EncodeTypes` et la prise en charge des formats d’image. |

Installez le package NuGet avec la commande suivante :

```bash
dotnet add package Aspose.BarCode
```

## Étape 1 : Configurer le projet et les imports

Créez un nouveau projet console et ajoutez les directives `using` requises :

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
            // The tutorial code starts here.
```

Ces espaces de noms exposent `BarcodeGenerator`, `EncodeTypes` et l’énumération `BarCodeImageFormat` utilisées plus tard.

## Étape 2 : Créer un code-barres RM4SCC – hauteur automatique

Le premier exemple montre comment **créer un code-barres RM4SCC C#** sans spécifier de hauteur de barre. La bibliothèque détermine automatiquement la hauteur optimale en fonction de la dimension X.

```csharp
            // Create a Planet (postal) barcode generator – auto height
            BarcodeGenerator rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

            // Define the module width (X‑dimension) in pixels
            rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4;

            // Optional: comment out the next line to keep automatic height
            // rm4sccAuto.Parameters.Barcode.BarHeight.Pixels = 100;

            // Save the image as PNG
            rm4sccAuto.Save("RM4SCC_AutoHeight.png", BarCodeImageFormat.Png);
```

**Pourquoi cela fonctionne :**  
* `EncodeTypes.RM4SCC` indique au générateur d’utiliser la symbologie postale RM4SCC.  
* `XDimension.Pixels` contrôle la largeur de la barre étroite ; 4 px est un choix courant pour le rendu à l’écran.  
* Lorsque `BarHeight.Pixels` est omis, Aspose calcule une hauteur qui satisfait la spécification RM4SCC, garantissant la lisibilité pour les scanners postaux.

## Étape 3 : Créer un code-barres RM4SCC – hauteur fixe

Parfois, un système de conception nécessite une hauteur de barre spécifique. Le code suivant fixe la hauteur à 100 px :

```csharp
            // Create a RM4SCC barcode generator – fixed height
            BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

            // X‑dimension stays the same
            rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;

            // Explicitly set the bar height to 100 px
            rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;

            // Save the image
            rm4sccFixed.Save("RM4SCC_FixedHeight.png", BarCodeImageFormat.Png);
```

**Pourquoi vous pourriez utiliser une hauteur fixe :**  
Les directives de conception imposent souvent un poids visuel uniforme entre différents codes-barres. En définissant `BarHeight.Pixels`, vous assurez une apparence cohérente quel que soit le type de symbologie sous‑jacent.

## Étape 4 : Créer un code-barres Planet – hauteur automatique

L’**exemple de générateur de code-barres C#** fonctionne de la même manière pour le code postal Planet. Changez la valeur `EncodeTypes` et réutilisez la même logique de configuration :

```csharp
            // Create a Planet barcode generator – auto height
            BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // Same X‑dimension as before
            planetAuto.Parameters.Barcode.XDimension.Pixels = 4;

            // Keep automatic height (comment out the line below if you want auto)
            // planetAuto.Parameters.Barcode.BarHeight.Pixels = 100;

            // Save the PNG file
            planetAuto.Save("Planet_AutoHeight.png", BarCodeImageFormat.Png);
```

**Comment générer un code-barres Planet :**  
Le seul changement est la valeur d’énumération `EncodeTypes.Planet`. Tous les autres paramètres (dimension X, hauteur optionnelle) se comportent de façon identique, ce qui fait de ce tutoriel un **exemple de générateur de code-barres C#** pour plusieurs formats postaux.

## Étape 5 : Créer un code-barres Planet – hauteur fixe

Si vous avez besoin d’une hauteur spécifique pour le code-barres Planet, appliquez la même propriété utilisée pour RM4SCC :

```csharp
            // Create a Planet barcode generator – fixed height
            BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
            planetFixed.Parameters.Barcode.BarHeight.Pixels = 100; // fixed 100 px

            planetFixed.Save("Planet_FixedHeight.png", BarCodeImageFormat.Png);
```

## Étape 6 : Exécuter et vérifier la sortie

Fermez la méthode `Main` et les accolades de classe :

```csharp
        }
    }
}
```

Compilez et exécutez le projet :

```bash
dotnet run
```

Après l’exécution, vous trouverez quatre fichiers PNG dans le dossier du projet :

* `RM4SCC_AutoHeight.png`
* `RM4SCC_FixedHeight.png`
* `Planet_AutoHeight.png`
* `Planet_FixedHeight.png`

Chaque image contient un code-barres clair et lisible. Ouvrez n’importe quel fichier pour vérifier que les barres sont rendues avec la largeur attendue (4 px) et la hauteur (automatique ou 100 px).  

![Code-barres RM4SCC généré avec C#](rm4scc_example.png "Capture d’écran montrant un code-barres RM4SCC généré avec C#")

*Texte alternatif de l’image :* **Capture d’écran montrant un code-barres RM4SCC généré avec C#** (correspond à l’exigence d’alt de l’image OG).

## Astuces pro et pièges courants

| Situation | Recommandation |
|-----------|----------------|
| **Dimension X incorrecte** | Conservez `XDimension.Pixels` entre 2 px et 6 px pour la plupart des imprimantes. Des valeurs plus petites peuvent provoquer du flou. |
| **Hauteur de barre ignorée** | Assurez‑vous de *décommenter* la ligne `BarHeight.Pixels` ; laisser le commentaire entraînera le retour à la hauteur automatique. |
| **Chaîne de données invalide** | RM4SCC et Planet n’acceptent que des caractères numériques (0‑9). Fournir des lettres déclenche une `ArgumentException`. |
| **Sortie haute résolution** | Utilisez `BarCodeImageFormat.Tiff` ou `Pdf` pour une impression sans perte. |
| **Performance** | Réutilisez une seule instance de `BarcodeGenerator` si vous devez créer de nombreux codes-barres avec les mêmes paramètres ; modifiez uniquement la propriété `CodeText` entre les sauvegardes. |

## Conclusion

Vous savez maintenant comment **créer un code-barres RM4SCC C#** et **générer un code-barres Planet** en utilisant un modèle de code concis et réutilisable. Le tutoriel a couvert les scénarios de hauteur automatique et fixe, vous a fourni un squelette de projet prêt à l’emploi, et a mis en avant les meilleures pratiques pour une génération fiable de codes-barres.

Ensuite, envisagez d’explorer d’autres symbologies postales telles que **POSTNET** ou **USPS Intelligent Mail** — la même API `BarcodeGenerator` s’applique, vous pouvez donc étendre cet **exemple de générateur de code-barres C#** avec peu de modifications. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Générateur de code-barres C# – créer un code-barres Planet et exemple RM4SCC](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)
- [Créer un code-barres RM4SCC C# et définir la hauteur du code-barres](/barcode/english/python-java/general/create-rm4scc-barcode-c-and-set-barcode-height/)
- [Créer un code-barres Planet en C# – guide complet étape par étape](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
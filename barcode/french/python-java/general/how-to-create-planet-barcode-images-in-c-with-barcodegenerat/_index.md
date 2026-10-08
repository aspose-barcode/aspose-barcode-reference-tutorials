---
category: general
date: 2026-09-26
description: Apprenez à créer rapidement un code‑barres Planet en C#. Ce guide couvre
  les codes‑barres Planet remplis et vides, les réglages de la dimension X et l’exportation
  d’image.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode C#
- filled planet barcode
- empty planet barcode
- barcode generator parameters
language: fr
lastmod: 2026-09-26
og_description: Créer un code‑barres Planet en C# avec un exemple complet. Générer
  des codes‑barres Planet remplis et vides, définir la largeur des barres et enregistrer
  au format PNG.
og_image_alt: Screenshot showing generated filled and empty planet barcode PNG files
og_title: Créer des images de code‑barres planétaires en C# – guide étape par étape
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create planet barcode in C# quickly. This guide covers
    filled and empty Planet barcodes, X‑dimension settings, and image export.
  headline: How to create planet barcode images in C# with BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Comment créer des images de code‑barres Planet en C# avec BarcodeGenerator
url: /fr/python-java/general/how-to-create-planet-barcode-images-in-c-with-barcodegenerat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer des images de code‑barres Planet en C# avec BarcodeGenerator

Si vous devez **créer des codes‑barres Planet** dans une application .NET, ce tutoriel vous montre les étapes exactes. Vous apprendrez à générer à la fois un code‑barres Planet rempli et un code‑barres Planet vide, à ajuster la largeur des barres et à exporter les résultats au format PNG — le tout avec la bibliothèque Aspose.BarCode pour .NET.

Générer une solution **Planet barcode C#** est simple une fois que vous comprenez les principaux **paramètres du générateur de code‑barres**. Dans les sections suivantes, nous parcourrons le code complet et exécutable, expliquerons pourquoi chaque paramètre est important et soulignerons les pièges courants afin que vous puissiez les éviter dès la première tentative.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

* .NET 6.0 SDK ou version ultérieure installé.
* Visual Studio 2022 (ou tout IDE C# de votre choix).
* Le package NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`) ajouté à votre projet.

Vous pouvez ajouter le package via la console du Gestionnaire de packages NuGet :

```bash
dotnet add package Aspose.BarCode
```

## Étape 1 : Configurer le BarcodeGenerator

La classe `BarcodeGenerator` est le point d’entrée pour toutes les tâches de création de code‑barres. Elle nécessite deux arguments : le type de code‑barres (`EncodeTypes.Planet`) et les données à encoder.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PlanetBarcodeDemo
{
    static void Main()
    {
        // Create a generator for a filled Planet barcode
        BarcodeGenerator filledPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*Pourquoi c’est important :* Instancier le générateur avec `EncodeTypes.Planet` indique à la bibliothèque d’utiliser la symbologie **Planet barcode**, couramment utilisée par les services postaux dans certains pays. La chaîne `"123456"` est la charge utile qui apparaîtra dans le code‑barres.

## Étape 2 : Configurer la X‑dimension (largeur des barres)

La X‑dimension contrôle la largeur physique de chaque barre. Une valeur typique pour l’affichage à l’écran est de 4 pixels, mais vous pouvez l’ajuster en fonction des exigences d’impression.

```csharp
        // Define the bar width (X dimension) in pixels
        filledPlanet.Parameters.Barcode.XDimension.Pixels = 4;
```

*Pourquoi c’est important :* Définir `XDimension.Pixels` garantit que le code‑barres généré n’est ni trop fin (ce qui provoquerait des échecs de lecture) ni trop épais (gaspillant de l’espace). Le même réglage sera réutilisé pour le code‑barres vide.

## Étape 3 : Enregistrer le code‑barres Planet rempli

Exportez le code‑barres vers un fichier PNG à l’aide de la méthode `Save`. L’énumération `BarCodeImageFormat.Png` indique à la bibliothèque de produire une image sans perte adaptée à un traitement ultérieur.

```csharp
        // Save the filled barcode as a PNG image
        filledPlanet.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

Après l’exécution du programme, vous trouverez `PostalPlanetFilledBars.png` dans le dossier de sortie. Ouvrez‑le pour vérifier que les barres sont solides (remplies).

## Étape 4 : Créer un générateur pour un code‑barres Planet vide

Un **code‑barres Planet vide** affiche les mêmes données mais avec des barres non remplies (blanches). Cela est utile pour les conceptions visuelles qui superposent le code‑barres sur des arrière‑plans colorés.

```csharp
        // Create a generator for an empty Planet barcode (unfilled bars)
        BarcodeGenerator emptyPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

L’appel du constructeur est identique à la version remplie ; la différence réside dans le paramètre que nous modifierons ensuite.

## Étape 5 : Réutiliser la même X‑dimension

Pour garder une taille visuelle cohérente, appliquez la même largeur de barre au code‑barres vide.

```csharp
        // Use the same bar width as before
        emptyPlanet.Parameters.Barcode.XDimension.Pixels = 4;
```

Réutiliser les **paramètres du générateur de code‑barres** garantit que les deux images s’alignent parfaitement lorsqu’elles sont placées côte à côte.

## Étape 6 : Passer aux barres non remplies

Le drapeau `FilledBars` détermine si les barres sont rendues en noir plein (par défaut) ou en blanc transparent.

```csharp
        // Configure the generator to produce empty (unfilled) bars
        emptyPlanet.Parameters.Barcode.FilledBars = false;
```

*Pourquoi c’est important :* Définir `FilledBars = false` inverse le mode de rendu, ce qui constitue la différence principale entre un code‑barres Planet rempli et un code‑barres Planet vide.

## Étape 7 : Enregistrer le code‑barres Planet vide

Enfin, exportez la version vide au format PNG.

```csharp
        // Save the empty barcode as a PNG image
        emptyPlanet.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

Lorsque vous exécutez le programme, deux fichiers apparaissent :

* `PostalPlanetFilledBars.png` – barres noires solides.
* `PostalPlanetEmptyBars.png` – barres transparentes (non remplies).

Les deux images contiennent les mêmes données (`123456`) et partagent la même X‑dimension, ce qui les rend interchangeables dans la plupart des scénarios d’interface utilisateur.

## Exemple complet et exécutable

En rassemblant tous les éléments, voici le fichier source complet que vous pouvez copier‑coller dans un nouveau projet console :

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PlanetBarcodeDemo
{
    static void Main()
    {
        // ----------- Filled Planet barcode -----------
        BarcodeGenerator filledPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        filledPlanet.Parameters.Barcode.XDimension.Pixels = 4;
        filledPlanet.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // ----------- Empty Planet barcode ------------
        BarcodeGenerator emptyPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        emptyPlanet.Parameters.Barcode.XDimension.Pixels = 4;
        emptyPlanet.Parameters.Barcode.FilledBars = false;
        emptyPlanet.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

**Sortie attendue**

L’exécution du programme crée deux fichiers PNG dans le répertoire de travail de l’exécutable. Ouvrez‑les avec n’importe quel visualiseur d’images :

* **Version remplie** – barres sombres et solides, facilement lisibles par les scanners standards.
* **Version vide** – les barres apparaissent comme des espaces blancs sur un fond noir, utile pour les effets de superposition.

## Pièges courants et astuces professionnelles

| Problème | Pourquoi cela se produit | Comment le corriger |
|----------|--------------------------|---------------------|
| Les barres semblent trop fines | X‑dimension laissée à la valeur par défaut (1 pixel) | Définissez `XDimension.Pixels` à 3‑5 pixels pour l’affichage à l’écran ; augmentez pour les impressions haute résolution. |
| Le code‑barres vide apparaît complètement noir | `FilledBars` n’est pas réglé sur `false` | Assurez‑vous que `emptyPlanet.Parameters.Barcode.FilledBars = false;` est exécuté **après** la définition de la X‑dimension. |
| Le fichier PNG est manquant | Le chemin de sortie est incorrect ou le répertoire n’existe pas | Fournissez un chemin complet (`@"C:\Barcodes\PostalPlanetFilledBars.png"`) ou créez le répertoire au préalable avec `Directory.CreateDirectory`. |
| Le code‑barres ne se lit pas | La chaîne de données contient des caractères illégaux pour la symbologie Planet | Les codes‑barres Planet n’acceptent que des charges numériques ; validez l’entrée avec `int.TryParse`. |

**Astuce pro :** Si vous devez intégrer le code‑barres dans un PDF, vous pouvez charger le PNG généré dans un `PdfDocument` avec Aspose.PDF, ou ajouter directement le code‑barres comme flux d’image sans l’écrire sur le disque.

## Étapes suivantes

Maintenant que vous pouvez **créer des images de code‑barres Planet**, envisagez d’explorer ces sujets connexes :

* **Planet barcode C#** – personnaliser les couleurs, ajouter du texte lisible par l’homme, ou intégrer le code‑barres dans un PDF.
* **Paramètres du générateur de code‑barres** – ajuster le niveau de correction d’erreur, la zone silencieuse ou la rotation.
* **Génération par lots** – parcourir une liste de codes postaux pour produire un fichier zip de PNG.
* **Formats alternatifs** – exporter en SVG ou JPEG pour une diffusion adaptée au web.

Expérimentez avec différentes valeurs de `XDimension` et le drapeau `FilledBars` pour voir comment ils influencent la fiabilité de la lecture et le style visuel. Lorsque vous êtes prêt, intégrez le code de génération dans votre API web ou application de bureau pour automatiser la création de codes‑barres postaux à la volée.

---


## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Créer un code‑barres Planet en C# – Guide complet étape par étape](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Générateur de code‑barres C# – créer un code‑barres Planet et un exemple RM4SCC](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)
- [Générer un code‑barres postal en C# – Guide complet avec le code‑barres Planet](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
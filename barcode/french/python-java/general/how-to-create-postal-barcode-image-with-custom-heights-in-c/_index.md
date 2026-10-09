---
category: general
date: 2026-09-26
description: Apprenez à créer une image de code‑barres postal en C#. Ce guide vous
  montre comment générer un code‑barres Planet et définir la hauteur du code‑barres
  pour une sortie personnalisée.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- barcode generator custom height
- how to set barcode height
language: fr
lastmod: 2026-09-26
og_description: Créez rapidement une image de code‑barres postal en C#. Suivez ce
  tutoriel pour générer un code‑barres Planet, définir la hauteur du code‑barres et
  produire des fichiers PNG de haute qualité.
og_image_alt: Screenshot of a generated postal barcode image with custom bar height
og_title: Créer une image de code‑barres postal avec des hauteurs personnalisées en
  C# – guide étape par étape
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create postal barcode image in C#. This guide shows you
    how to generate planet barcode and set barcode height for custom output.
  headline: How to create postal barcode image with custom heights in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: Comment créer une image de code‑barres postal avec des hauteurs personnalisées
  en C#
url: /fr/python-java/general/how-to-create-postal-barcode-image-with-custom-heights-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer une image de code‑barres postal avec des hauteurs personnalisées en C#

Si vous devez **créer une image de code‑barres postal** pour des étiquettes d’envoi, ce tutoriel vous montre les étapes exactes. Vous apprendrez à générer un code‑barres Planet, à ajuster la hauteur des barres et à enregistrer le résultat sous forme de fichier PNG — le tout avec la bibliothèque Aspose.BarCode pour .NET.

Créer une image de code‑barres ne nécessite aucun outil de conception externe. À la fin de ce guide, vous pourrez produire des codes‑barres à hauteur par défaut et à hauteur personnalisée pour les normes Planet et RM4SCC, prêts à être intégrés dans n’importe quel flux de travail d’expédition.

## Prérequis

* .NET 6.0 ou version ultérieure installé  
* Visual Studio 2022 (ou tout IDE C#)  
* Aspose.BarCode pour .NET ajouté via NuGet (`Install-Package Aspose.BarCode`)  

Aucune configuration supplémentaire n’est requise ; la bibliothèque gère le rendu de l’image en interne.

## Étape 1 : Configurer le projet et importer les espaces de noms

Créez une nouvelle application console et ajoutez les instructions `using` requises.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Ces espaces de noms exposent la classe `BarcodeGenerator` et l’énumération `EncodeTypes` que vous utiliserez pour **générer un code‑barres planet** et d’autres formats postaux.

## Étape 2 : Créer un code‑barres Planet avec la hauteur de barre par défaut

Le premier exemple crée un code‑barres Planet en utilisant la hauteur de barre par défaut de la bibliothèque. Cela montre le rendu de base avant d’appliquer une taille personnalisée.

```csharp
// Initialize the generator for a Planet barcode
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the X‑dimension (module width) to 4 pixels for better readability
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the barcode image; the default bar height is applied automatically
planetGenerator.Save("PostalPlanetBarHeightDefault.png", BarCodeImageFormat.Png);
```

**Pourquoi c’est important :** La hauteur par défaut convient à la plupart des imprimantes d’étiquettes, mais certains flux de travail nécessitent des barres plus hautes pour améliorer la fiabilité du scan. Le code ci‑dessus vous fournit une image de référence à comparer avec la version à hauteur personnalisée.

## Étape 3 : Appliquer une hauteur de barre personnalisée au code‑barres Planet

Pour **définir la hauteur du code‑barres** manuellement, attribuez une valeur en pixels à `BarHeight.Pixels`. L’extrait suivant crée un code‑barres Planet de 100 pixels de haut.

```csharp
// Initialize a second generator for the same data
BarcodeGenerator planetHeightGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Define X‑dimension and a custom bar height of 100 pixels
planetHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
planetHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the custom‑height image
planetHeightGenerator.Save("PostalPlanetBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

**Astuce :** Choisissez une hauteur de barre qui correspond au DPI de votre imprimante. Pour une imprimante de 300 dpi, une barre de 100 pixels correspond à environ 0,33 pouce, ce qui est souvent recommandé pour les scanners postaux.

## Étape 4 : Générer un code‑barres RM4SCC avec la hauteur par défaut

RM4SCC est une autre symbologie postale courante. Le processus reflète l’exemple Planet mais utilise `EncodeTypes.RM4SCC`.

```csharp
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Set X‑dimension; the library applies the default bar height automatically
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccGenerator.Save("PostalRM4SCCBarHeightDefault.png", BarCodeImageFormat.Png);
```

Cette étape confirme que la même logique de **hauteur personnalisée du générateur de code‑barres** fonctionne avec différents formats postaux.

## Étape 5 : Appliquer une hauteur personnalisée au code‑barres RM4SCC

Enfin, ajustez la hauteur des barres du code‑barres RM4SCC de la même manière que pour le code‑barres Planet.

```csharp
BarcodeGenerator rm4sccHeightGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Define both X‑dimension and a 100‑pixel bar height
rm4sccHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the custom‑height image
rm4sccHeightGenerator.Save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

## Résultat attendu

L’exécution du programme complet génère quatre fichiers PNG dans le répertoire de sortie du projet :

| Nom du fichier                           | Hauteur de la barre | Symbologie |
|------------------------------------------|---------------------|------------|
| `PostalPlanetBarHeightDefault.png`      | default             | Planet     |
| `PostalPlanetBarHeight100Pixels.png`    | 100 px              | Planet     |
| `PostalRM4SCCBarHeightDefault.png`      | default             | RM4SCC     |
| `PostalRM4SCCBarHeight100Pixels.png`    | 100 px              | RM4SCC     |

Chaque image affiche un code‑barres clair et à fort contraste, prêt à être imprimé sur des étiquettes d’envoi. Vous pouvez ouvrir les fichiers PNG avec n’importe quel visualiseur d’image pour vérifier les dimensions des barres.

## Questions fréquentes et cas particuliers

**Et si j’ai besoin d’une hauteur de barre en millimètres plutôt qu’en pixels ?**  
La bibliothèque travaille en pixels car elle correspond directement à la résolution du bitmap. Convertissez les millimètres en pixels en utilisant le DPI de l’imprimante :  
`pixels = (mm / 25.4) * DPI`. Définissez `BarHeight.Pixels` avec la valeur calculée.

**Puis‑je modifier la hauteur de la barre après avoir appelé `Save` ?**  
Non. L’image du code‑barres est rendue au moment où `Save` est invoqué. Ajustez tous les paramètres avant d’appeler `Save`.

**Une dimension X plus grande est‑elle nécessaire pour des barres plus hautes ?**  
Augmenter `XDimension` rend chaque module plus large, ce qui peut améliorer la lisibilité sur les imprimantes à basse résolution. Cependant, cela augmente également la largeur globale du code‑barres. Testez les deux valeurs pour trouver le compromis optimal pour la taille de votre étiquette.

**Le même code fonctionnera‑t‑il sur .NET Framework 4.8 ?**  
Oui. Aspose.BarCode prend en charge .NET Framework 4.6.2 et versions ultérieures, vous pouvez donc cibler des runtimes plus anciens sans modification.

## Code source complet pour copier‑coller rapidement

Voici le programme complet et exécutable qui intègre toutes les étapes décrites ci‑dessus.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // ---------- Planet barcode (default height) ----------
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        planetGenerator.Save("PostalPlanetBarHeightDefault.png", BarCodeImageFormat.Png);

        // ---------- Planet barcode (custom 100‑pixel height) ----------
        BarcodeGenerator planetHeightGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        planetHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        planetHeightGenerator.Save("PostalPlanetBarHeight100Pixels.png", BarCodeImageFormat.Png);

        // ---------- RM4SCC barcode (default height) ----------
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccGenerator.Save("PostalRM4SCCBarHeightDefault.png", BarCodeImageFormat.Png);

        // ---------- RM4SCC barcode (custom 100‑pixel height) ----------
        BarcodeGenerator rm4sccHeightGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4sccHeightGenerator.Save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);

        Console.WriteLine("All barcode images have been generated successfully.");
    }
}
```

Exécutez le programme, et la console confirmera que chaque image a été enregistrée. Vous pouvez maintenant intégrer ces fichiers PNG dans vos modèles d’étiquettes d’envoi, les imprimer ou les envoyer à une API logistique tierce.

## Conclusion

Vous savez maintenant comment **créer des fichiers d’image de code‑barres postal** en C# avec Aspose.BarCode. Le guide a couvert la génération d’un code‑barres Planet, l’ajustement de la hauteur des barres et l’application de la même technique aux codes‑barres RM4SCC. En contrôlant `XDimension` et `BarHeight.Pixels`, vous obtenez des résultats visuels précis qui répondent aux exigences des services postaux.

Ensuite, explorez des sujets connexes tels que **générer des QR codes pour le suivi**, **intégrer des codes‑barres dans des factures PDF**, ou **traiter par lots plusieurs images de code‑barres**. Modifier la hauteur des barres n’est qu’un levier ; vous pouvez également personnaliser les couleurs, ajouter du texte lisible par l’homme, ou exporter en SVG pour une utilisation web.

Bon codage, et que vos envois soient scannés sans accroc !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Créer une image de code‑barres postal en C# – guide étape par étape](/barcode/english/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/)
- [Créer des images de code‑barres postaux – Modifier facilement la hauteur du code‑barres](/barcode/english/python-java/general/create-postal-barcode-images-change-barcode-height-easily/)
- [Comment générer un code‑barres postal en C# avec des dimensions personnalisées](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
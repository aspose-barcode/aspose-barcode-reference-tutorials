---
category: general
date: 2026-08-03
description: Créez rapidement une image de code‑barres postal en C#. Apprenez à générer
  un code‑barres postal, à définir les dimensions du code‑barres et à générer un code‑barres
  Planet.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- how to generate postal barcode
- generate planet barcode
- how to set barcode dimensions
language: fr
lastmod: 2026-08-03
og_description: Créez une image de code-barres postal en C# avec ce tutoriel complet ;
  apprenez à définir les dimensions du code-barres, à générer un code-barres Planet
  et à produire des codes-barres RM4SCC.
og_image_alt: Generated postal barcode image saved as PNG using C# BarcodeGenerator
og_title: Créer une image de code‑barres postal en C# – guide complet de programmation
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create postal barcode image in C# quickly. Learn how to generate postal
    barcode, set barcode dimensions, and generate a Planet barcode.
  headline: Create postal barcode image in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- postal barcode
title: Créer une image de code‑barres postal en C# – guide étape par étape
url: /fr/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une image de code-barres postal en C# – guide étape par étape

Si vous devez **créer une image de code-barres postal** en C#, ce guide vous montre exactement comment faire. Nous couvrirons **comment générer un code-barres postal**, **comment définir les dimensions du code-barres**, et comment **générer un code-barres Planet** pour les normes postales courantes.

Vous terminerez avec deux fichiers PNG prêts à l’emploi — un code-barres Planet et un code-barres RM4SCC — chacun de 100 px de hauteur. Aucun outil supplémentaire n’est requis au-delà de la bibliothèque Aspose.BarCode pour .NET.

## Prérequis

* SDK .NET 6 ou ultérieur (le code fonctionne également avec .NET Framework 4.7+)
* Visual Studio 2022 ou tout IDE C#
* Package NuGet **Aspose.BarCode** (la bibliothèque qui fournit `BarcodeGenerator`)

## Étape 1 : Installer la bibliothèque de codes-barres

Ouvrez un terminal dans le dossier de votre projet et exécutez :

```bash
dotnet add package Aspose.BarCode
```

Le package ajoute l’espace de noms `Aspose.BarCode`, qui contient `BarcodeGenerator` et l’énumération `EncodeTypes` nécessaires aux codes-barres postaux.

## Étape 2 : Définir le dossier de sortie

Créer un chemin de sortie fiable évite les erreurs d’exécution lorsque le dossier n’existe pas.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // Ensure the directory exists
        string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputFolder);
```

*Pourquoi c’est important* : `Directory.CreateDirectory` est idempotent — il crée le dossier uniquement s’il n’est pas déjà présent, évitant ainsi les exceptions lors des exécutions suivantes.

## Étape 3 : Configurer les dimensions communes du code-barres

Définir la dimension X (largeur d’une barre unique) et la hauteur totale de la barre vous permet de contrôler la taille visuelle de l’image générée.

```csharp
        // Common dimension settings
        const int xDimensionPixels = 4;   // Width of a single bar
        const int barHeightPixels = 100; // Desired barcode height
```

**Comment définir les dimensions du code-barres** : la propriété `Parameters.Barcode.XDimension.Pixels` définit la largeur de la barre étroite, tandis que `Parameters.Barcode.BarHeight.Pixels` définit la hauteur totale. Ajustez ces valeurs pour répondre aux spécifications de votre service postal.

## Étape 4 : Générer un code-barres Planet

Planet est un code-barres postal largement utilisé au Royaume-Uni. Le code suivant crée un code-barres Planet de 100 px de hauteur et l’enregistre au format PNG.

```csharp
        // Step 4: Generate Planet barcode
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        planetGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;

        string planetPath = Path.Combine(outputFolder, "PostalPlanetBarHeight100Pixels.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);
```

**Pourquoi cela fonctionne** : `EncodeTypes.Planet` indique au générateur d’utiliser la symbologie Planet. La méthode `Save` écrit un fichier PNG au chemin spécifié, en conservant les dimensions que nous avons définies précédemment.

## Étape 5 : Générer un code-barres RM4SCC

RM4SCC est la norme néerlandaise de code-barres postal. Le code ci‑dessous reproduit l’exemple Planet, démontrant **comment générer un code-barres postal** d’un type différent avec des dimensions identiques.

```csharp
        // Step 5: Generate RM4SCC barcode
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;

        string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCBarHeight100Pixels.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);
```

Les deux fichiers PNG se trouvent maintenant dans le dossier `Barcodes`. Les ouvrir affichera des codes-barres nets de 100 px de hauteur, prêts à être imprimés ou intégrés dans des documents.

## Code source complet

Voici le programme complet et exécutable qui **crée des fichiers d’image de code-barres postal** pour les normes Planet et RM4SCC.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // Ensure output directory exists
        string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // Dimension settings – reusable for all barcodes
        const int xDimensionPixels = 4;   // Width of a single bar
        const int barHeightPixels = 100; // Height of the barcode

        // ---- Generate Planet barcode ----
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        planetGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;
        string planetPath = Path.Combine(outputFolder, "PostalPlanetBarHeight100Pixels.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);

        // ---- Generate RM4SCC barcode ----
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;
        string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCBarHeight100Pixels.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);

        Console.WriteLine("Barcodes generated:");
        Console.WriteLine($"• {planetPath}");
        Console.WriteLine($"• {rm4sccPath}");
    }
}
```

### Résultat attendu

L’exécution du programme affiche les chemins des fichiers et crée deux fichiers PNG :

```
Barcodes/
 ├─ PostalPlanetBarHeight100Pixels.png
 └─ PostalRM4SCCBarHeight100Pixels.png
```

Chaque image mesure 100 px de hauteur, avec une largeur de barre étroite de 4 pixels, correspondant aux dimensions que nous avons définies.

## Conseils pratiques et pièges courants

* **Permissions du dossier** – Si le programme s’exécute sous un compte restreint, assurez‑vous que le dossier cible est accessible en écriture.
* **Dimensions différentes** – Pour créer un code‑barres plus haut, augmentez `barHeightPixels`. Pour une résolution plus fine, réduisez `xDimensionPixels`, mais gardez‑la ≥ 2 pour éviter les artefacts de rendu.
* **Autres symbologies postales** – Aspose.BarCode prend également en charge `EncodeTypes.Postnet` et `EncodeTypes.AustralianPost`. Changez la valeur de `EncodeTypes` et conservez la même logique de dimensions.
* **Format d’image** – Utilisez `BarCodeImageFormat.Jpeg` pour une taille de fichier plus petite lorsque la qualité sans perte n’est pas requise.

## Conclusion

Vous savez maintenant comment **créer des fichiers d’image de code‑barres postal** en C# en configurant les dimensions, en sélectionnant la symbologie appropriée et en enregistrant le résultat au format PNG. Le tutoriel a couvert **comment générer un code‑barres postal**, a démontré **la génération d’un code‑barres Planet**, et a expliqué **comment définir les dimensions du code‑barres** pour un rendu cohérent.

Ensuite, explorez **la personnalisation des couleurs du code‑barres**, l’ajout de **texte lisible par l’homme**, ou l’intégration des images dans des factures PDF. Le même modèle s’applique à tout autre type de code‑barres pris en charge par Aspose.BarCode, vous permettant d’étendre cette solution à un flux complet d’automatisation postale.

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment générer un code‑barres – Types de code‑barres unidimensionnels](/barcode/english/net/one-dimensional-barcode-types/)
- [Comment générer un code‑barres Aztec avec un rapport d’aspect personnalisé en utilisant Aspose.BarCode pour .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Comment générer un code‑barres java – Code‑barres Australia Post avec Aspose](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
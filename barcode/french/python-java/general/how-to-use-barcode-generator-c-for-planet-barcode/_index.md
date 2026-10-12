---
category: general
date: 2026-09-19
description: Le guide du générateur de codes-barres C# montre comment générer un code-barres
  Planet et exporter l’image du code-barres au format PNG en quelques lignes seulement.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- how to generate barcode
- create planet barcode
- export barcode image
language: fr
lastmod: 2026-09-19
og_description: Le générateur de codes-barres C# vous permet de créer rapidement un
  code-barres Planet et d’exporter l’image au format PNG pour toute application .NET.
og_image_alt: Screenshot of a Planet barcode generated with barcode generator C# showing
  empty bars
og_title: générateur de code-barres C# – créer un code-barres Planet et exporter l'image
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator C# guide shows how to generate a Planet barcode and
    export barcode image as PNG in just a few lines.
  headline: How to use barcode generator C# for Planet barcode
  type: TechArticle
tags:
- barcode
- C#
- image export
title: Comment utiliser le générateur de code-barres C# pour le code-barres Planet
url: /fr/python-java/general/how-to-use-barcode-generator-c-for-planet-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment utiliser le générateur de code‑barres C# pour le code‑barres Planet

Si vous avez besoin d'un **barcode generator C#** capable de produire un code‑barres Planet, ce guide vous fournit une solution complète. Vous apprendrez **comment générer des données de code‑barres**, personnaliser l'apparence et **exporter l'image du code‑barres** au format PNG en quelques lignes de code.

Créer des codes‑barres est une exigence courante pour les systèmes d'inventaire, les plateformes de billetterie et les appareils IoT. À la fin de ce tutoriel, vous disposerez d'une application console autonome qui génère un code‑barres Planet propre, désactive le remplissage des barres et enregistre le résultat sur le disque. Aucun outil externe n'est requis en dehors de la bibliothèque de code‑barres.

## Prérequis

* .NET 6.0 SDK ou version ultérieure installé  
* Une bibliothèque de code‑barres compatible C# (l'exemple utilise **Aspose.BarCode for .NET**, qui prend en charge la symbologie Planet)  
* Un IDE ou éditeur tel que Visual Studio 2022, VS Code ou Rider  

La bibliothèque peut être ajoutée via NuGet :

```bash
dotnet add package Aspose.BarCode
```

> **Astuce :** Utilisez la dernière version stable du package pour bénéficier des corrections de bugs et des améliorations de performances.

## Utiliser le générateur de code‑barres C# pour créer un code‑barres Planet

La première étape consiste à instancier le générateur avec la symbologie Planet et les données que vous souhaitez encoder.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for the Planet symbology with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

`BarcodeGenerator` est le point d'entrée pour toutes les opérations de code‑barres. Le constructeur reçoit la symbologie (`EncodeTypes.Planet`) et les données brutes (`"123456"`). Ce code **crée un code‑barres Planet** qui pourra ensuite être rendu sous forme d'image.

## Ajustement des paramètres du code‑barres

Pour contrôler la qualité visuelle, vous pouvez modifier la X‑dimension (largeur du module) et décider si les barres sont remplies.

```csharp
        // Step 2: Adjust the X-dimension (module width) to 4 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 3: Disable filling of the bars so that only the outlines are drawn
        generator.Parameters.Barcode.FilledBars = false;
```

* Définir `XDimension.Pixels` à **4** produit un code‑barres à plus haute résolution sans augmenter de façon dramatique la taille du fichier.  
* `FilledBars = false` génère un style uniquement en contour, utile lorsque vous souhaitez que le code‑barres se fonde dans l'arrière‑plan ou lors d'une impression sur des appareils à faible consommation d'encre.

## Exporter l'image du code‑barres

Après avoir configuré le générateur, enregistrez le résultat dans un fichier PNG. La méthode `Save` accepte un chemin complet et le format d'image souhaité.

```csharp
        // Step 4: Save the generated barcode image as a PNG file
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "PlanetEmptyBars.png");

        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

Le code écrit **export barcode image** `PlanetEmptyBars.png` sur le bureau de l'utilisateur. PNG est un format sans perte qui préserve les bords nets du code‑barres, le rendant idéal tant pour l'affichage à l'écran que pour l'impression haute résolution.

> **Cas particulier :** Si vous avez besoin d'un format différent (JPEG, BMP, GIF), remplacez `BarCodeImageFormat.Png` par la valeur d'énumération appropriée. JPEG introduit des artefacts de compression qui peuvent affecter la lisibilité par le scanner, donc utilisez‑le uniquement lorsque la taille du fichier est un enjeu critique.

## Exemple complet et exécutable

Voici le programme complet que vous pouvez copier, coller et exécuter immédiatement.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Create a barcode generator for the Planet symbology with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Adjust the X-dimension (module width) to 4 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 4;

        // Disable filling of the bars so that only the outlines are drawn
        generator.Parameters.Barcode.FilledBars = false;

        // Define the output file path (Desktop folder is used for convenience)
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "PlanetEmptyBars.png");

        // Export the barcode image as a PNG file
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

Lorsque vous exécutez le programme, vous devriez voir un message similaire à :

```
Barcode saved to: C:\Users\YourName\Desktop\PlanetEmptyBars.png
```

L'ouverture du fichier PNG affiche un code‑barres Planet propre avec des barres vides, exactement comme configuré.

![barcode generator C# example](/images/barcode-generator-csharp.png){alt="exemple de générateur de code‑barres C#"}

## Questions fréquentes et dépannage

| Question | Réponse |
|----------|--------|
| **Puis-je générer d'autres symbologies avec le même code ?** | Oui. Remplacez `EncodeTypes.Planet` par n'importe quel type pris en charge, tel que `EncodeTypes.Code128` ou `EncodeTypes.QR`. |
| **Que faire si le code‑barres ne se lit pas ?** | Vérifiez que la longueur des données respecte la spécification Planet (exactement 6 caractères numériques). Assurez‑vous également d'un contraste suffisant entre le code‑barres et l'arrière‑plan. |
| **Comment modifier la taille de l'image ?** | Ajustez `generator.Parameters.ImageWidth` et `generator.Parameters.ImageHeight` ou modifiez `XDimension` pour mettre à l'échelle le code‑barres proportionnellement. |
| **Est‑il possible d'ajouter une légende sous le code‑barres ?** | Utilisez `generator.Parameters.Barcode.CodeTextVisible = true;` et personnalisez `CodeTextParameters` pour la police, l'alignement et la marge. |

## Prochaines étapes

Maintenant que vous avez maîtrisé **comment générer des codes‑barres** avec un **barcode generator C#**, vous pouvez explorer :

* Générer des fichiers de codes‑barres en lot à l'aide d'une liste CSV de valeurs.  
* Intégrer le PNG dans des factures PDF avec Aspose.PDF.  
* Passer aux formats `export barcode image` comme SVG pour des graphiques web évolutifs.  

Ces extensions approfondissent votre compréhension de l'automatisation des codes‑barres en .NET et vous préparent aux scénarios d'intégration du monde réel.

---

**Résumé :** Ce tutoriel a démontré un flux de travail complet **barcode generator C#** — création d'un code‑barres Planet, personnalisation de son apparence, et **exportation de l'image du code‑barres** au format PNG. Vous pouvez adapter le même modèle à d'autres symbologies, formats d'image et destinations de sortie. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code fonctionnels complets avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités d'API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Générateur de code‑barres C# – générer l'image du code‑barres](/barcode/english/python-java/general/barcode-generator-c-generate-barcode-image/)
- [Créer une image de code‑barres Planet en C# – Comment générer un code‑barres postal](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Exemple de générateur de code‑barres en C# – Définir les colonnes, lignes et exporter l'image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
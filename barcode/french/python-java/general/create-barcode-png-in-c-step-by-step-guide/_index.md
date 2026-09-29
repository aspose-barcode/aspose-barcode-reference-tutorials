---
category: general
date: 2026-08-03
description: Créez un PNG de code‑barres en C# et apprenez à modifier le rapport d’aspect
  des images DataBar. Suivez cet exemple complet avec le code et des conseils.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode PNG
- how to change aspect ratio
- Aspose.BarCode C#
- DataBar stacked omnidirectional
- barcode image format PNG
language: fr
lastmod: 2026-08-03
og_description: Créez un PNG de code‑barres en C# et découvrez comment modifier le
  rapport d’aspect des codes‑barres DataBar. Ce guide vous fournit du code prêt à
  l’emploi et des conseils pratiques.
og_image_alt: Sample barcode PNG generated with aspect ratio 15
og_title: Créer un PNG de code‑barres en C# – exemple complet avec contrôle du rapport
  d’aspect
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  headline: Create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  name: Create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: How to change other visual properties?
    text: 'You can adjust foreground color, background color, or add human‑readable
      text through the `generator.Parameters.Barcode` object. For example:'
  - name: What if I need a different image format?
    text: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as needed.
      PNG remains the best choice for lossless barcode images.
  - name: Does the aspect ratio affect scanning speed?
    text: Higher aspect ratios increase the barcode’s height, which can improve scan
      reliability on devices that struggle with short stacked symbols. However, extremely
      tall barcodes may not fit on small labels, so test with your target hardware.
  - name: Can I generate multiple barcodes in a loop?
    text: Yes. Create a new `BarcodeGenerator` instance for each data string or reuse
      the same instance while updating `CodeText` and `DataBar.AspectRatio`. This
      approach reduces object allocation overhead.
  type: HowTo
tags:
- barcode
- C#
- PNG
- Aspose
title: Créer un PNG de code‑barres en C# – guide étape par étape
url: /fr/python-java/general/create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un PNG de code‑barres en C# – guide étape par étape

Si vous devez **créer un PNG de code‑barres** en C#, ce tutoriel vous montre exactement comment faire. Vous générerez un code‑barres DataBar omnidirectionnel empilé, l’enregistrerez sous forme de fichier PNG, et apprendrez **comment modifier le ratio d’aspect** pour l’adapter à différents environnements de numérisation.

Le guide couvre tout ce dont vous avez besoin : les packages requis, un programme complet et exécutable, ainsi que des explications sur l’importance de chaque paramètre. À la fin, vous disposerez de deux fichiers PNG — l’un avec un ratio d’aspect de 15 et l’autre de 30 — prêts pour les tests ou la production.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

- le SDK .NET 6.0 ou une version ultérieure installé
- Visual Studio 2022 (ou tout autre IDE C#)
- une référence NuGet à **Aspose.BarCode** (la bibliothèque qui fournit `BarcodeGenerator`)
- les droits d’écriture sur le répertoire où les fichiers PNG seront enregistrés

Vous pouvez ajouter le package Aspose.BarCode avec la commande suivante :

```bash
dotnet add package Aspose.BarCode
```

## Étape 1 : Configurer le projet et importer les espaces de noms

Créez une nouvelle application console et importez les espaces de noms nécessaires à la génération de code‑barres et aux opérations d’E/S de fichiers.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodePngDemo
{
    class Program
    {
        static void Main()
        {
            // All subsequent steps are inside Main
```

**Pourquoi c’est important :** L’importation de `Aspose.BarCode.Generation` vous donne accès à `BarcodeGenerator`. Garder le code à l’intérieur de `Main` rend l’exemple autonome et facile à exécuter.

## Étape 2 : Créer un générateur de code‑barres pour un DataBar omnidirectionnel empilé

Instanciez `BarcodeGenerator` avec le type `EncodeTypes.DatabarStackedOmniDirectional` et une chaîne de données GS1‑128 d’exemple.

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");
```

**Pourquoi c’est important :** Le type d’encodage choisi produit un DataBar à haute densité qui peut être lu par la plupart des scanners modernes. La chaîne de données suit le format de l’Identifiant d’Application GS1 (01), couramment utilisé pour les identifiants de produit.

## Étape 3 : Définir la dimension X (largeur du module) en pixels

Définissez la largeur du module pour contrôler la taille globale du code‑barres sans affecter sa lisibilité.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Pourquoi c’est important :** Une dimension X de 2 pixels donne un code‑barres ni trop petit pour les scanners, ni trop grand pour les espaces d’étiquetage habituels.

## Étape 4 : Enregistrer le premier PNG avec un ratio d’aspect de 15

Ajustez le ratio d’aspect du DataBar, puis enregistrez l’image au format PNG.

```csharp
            // Step 4: Set the DataBar aspect ratio to 15 and save the image
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;
            string outputPath15 = @"YOUR_DIRECTORY\DatabarAspectRatio15.png";
            generator.Save(outputPath15, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath15} (aspect ratio 15).");
```

**Pourquoi c’est important :** Le ratio d’aspect contrôle la relation hauteur‑largeur du DataBar empilé. Un ratio de 15 est une valeur par défaut courante qui équilibre lisibilité et hauteur d’étiquette.

## Étape 5 : Modifier le ratio d’aspect à 30 et enregistrer un deuxième PNG

Modifiez la même instance du générateur pour utiliser un ratio d’aspect plus grand, puis enregistrez la seconde image.

```csharp
            // Step 5: Change the aspect ratio to 30 and save another image
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string outputPath30 = @"YOUR_DIRECTORY\DatabarAspectRatio30.png";
            generator.Save(outputPath30, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath30} (aspect ratio 30).");
        }
    }
}
```

**Pourquoi c’est important :** Augmenter le ratio d’aspect étire le code‑barres verticalement, ce qui peut améliorer la fiabilité de la lecture sur des appareils à faible résolution ou lorsque l’étiquette est imprimée sur un support étroit.

## Résultat attendu

L’exécution du programme crée deux fichiers PNG :

| Fichier                              | Ratio d’aspect | Dimensions approximatives (pixels) |
|--------------------------------------|----------------|------------------------------------|
| `DatabarAspectRatio15.png`           | 15             | 200 × 300 (largeur × hauteur)       |
| `DatabarAspectRatio30.png`           | 30             | 200 × 600 (largeur × hauteur)       |

Les deux images contiennent un code‑barres DataBar clair et lisible qui encode l’identifiant GS1 `(01)12345678901231`.

## Questions courantes et cas limites

### Comment changer d’autres propriétés visuelles ?

Vous pouvez ajuster la couleur de premier plan, la couleur d’arrière‑plan ou ajouter du texte lisible par l’homme via l’objet `generator.Parameters.Barcode`. Par exemple :

```csharp
generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
generator.Parameters.Barcode.CodeTextParameters.ShowCodeText = true;
```

### Et si j’ai besoin d’un autre format d’image ?

Remplacez `BarCodeImageFormat.Png` par `Jpeg`, `Bmp` ou `Gif` selon vos besoins. Le PNG reste le meilleur choix pour des images de code‑barres sans perte.

### Le ratio d’aspect affecte‑il la vitesse de numérisation ?

Des ratios d’aspect plus élevés augmentent la hauteur du code‑barres, ce qui peut améliorer la fiabilité de la lecture sur des appareils qui ont du mal avec des symboles empilés courts. Cependant, des codes‑barres très hauts peuvent ne pas tenir sur de petites étiquettes, il faut donc tester avec le matériel cible.

### Puis‑je générer plusieurs codes‑barres dans une boucle ?

Oui. Créez une nouvelle instance de `BarcodeGenerator` pour chaque chaîne de données ou réutilisez la même instance en mettant à jour `CodeText` et `DataBar.AspectRatio`. Cette approche réduit la surcharge d’allocation d’objets.

## Conseils pro

- **Réutiliser le générateur** : Modifier uniquement le `CodeText` ou le `AspectRatio` évite de réinstancier l’objet, ce qui accélère le traitement par lots.
- **Valider la sortie** : Utilisez un scanner portable ou une application mobile pour confirmer que le PNG généré se lit correctement avant de le déployer en production.
- **Nommer les fichiers** : Incluez le ratio d’aspect dans le nom du fichier (comme indiqué) pour suivre les variantes lors des tests.

## Conclusion

Vous savez maintenant comment **créer des PNG de code‑barres** en C# et précisément **modifier le ratio d’aspect** pour les symboles DataBar omnidirectionnels empilés. L’exemple complet montre l’initialisation, le réglage de la dimension X, la manipulation du ratio d’aspect et l’enregistrement de l’image—le tout dans un seul programme exécutable.

À partir d’ici, vous pouvez explorer d’autres types de code‑barres, expérimenter avec les couleurs, ou intégrer le générateur dans un système de reporting ou de gestion d’inventaire plus vaste. Bonne programmation !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser d’autres fonctionnalités de l’API et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Créer un PNG de code‑barres – Ratio d’aspect DataMatrix – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [Comment générer un code‑barres Aztec avec un ratio d’aspect personnalisé en utilisant Aspose.BarCode pour .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Comment personnaliser le ratio d’aspect du code‑barres Codablock F avec Aspose.BarCode pour .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
---
category: general
date: 2026-10-02
description: Créer une image de code‑barres en C# à l'aide d'un générateur de code‑barres,
  contrôler la taille des pixels du code‑barres et ajuster la hauteur du code‑barres
  pour des dimensions personnalisées.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- barcode pixel size
- adjust barcode height
- custom barcode dimensions
language: fr
lastmod: 2026-10-02
og_description: Créer une image de code‑barres en C# avec un générateur de codes‑barres.
  Apprenez à définir la taille des pixels du code‑barres, à ajuster la hauteur du
  code‑barres et à définir des dimensions personnalisées du code‑barres.
og_image_alt: Sample DataBar Omnidirectional barcode saved at 30 px height and 60 px
  height
og_title: Créer une image de code-barres en C# – guide du générateur de codes-barres
  et des dimensions personnalisées
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create barcode image in C# using a barcode generator, control barcode
    pixel size and adjust barcode height for custom barcode dimensions.
  headline: How to create barcode image in C# with a barcode generator
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: Comment créer une image de code-barres en C# avec un générateur de codes-barres
url: /fr/python-java/general/how-to-create-barcode-image-in-c-with-a-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer une image de code‑barres en C# avec un générateur de code‑barres

Si vous devez **créer des fichiers image de code‑barres** de manière programmatique, ce guide vous montre une solution complète, prête à l’emploi en C#. En utilisant un générateur de code‑barres, vous pouvez contrôler la **taille des pixels du code‑barres**, **ajuster la hauteur du code‑barres**, et définir des **dimensions personnalisées du code‑barres** sans quitter votre IDE.

Vous apprendrez à générer deux fichiers PNG — l’un avec une hauteur de barre de 30 px et l’autre de 60 px — tout en conservant la largeur du module constante. Les étapes fonctionnent avec n’importe quel type de code‑barres pris en charge par la bibliothèque, vous pouvez donc les adapter aux QR codes, Code 128 ou autres symbologies.

## Ce dont vous avez besoin

- .NET 6.0 ou version ultérieure (le code compile également avec .NET Framework 4.8)
- Une référence à la bibliothèque de code‑barres (par ex., Aspose.BarCode for .NET ou toute classe compatible `BarcodeGenerator`)
- Connaissances de base en C#
- Permission d’écriture sur un dossier où les fichiers PNG seront enregistrés

## Étape 1 : Initialiser le générateur de code‑barres pour **créer une image de code‑barres**

Tout d’abord, importez les espaces de noms requis et créez une instance de `BarcodeGenerator`. Le constructeur reçoit le type de code‑barres (`EncodeTypes.DatabarOmniDirectional`) et la chaîne de données que vous souhaitez encoder.

```csharp
using Aspose.BarCode.Generation;   // or the namespace of your barcode library
using Aspose.BarCode;               // for BarCodeImageFormat
using System.IO;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator to create barcode image
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Créer le générateur constitue la base de tout flux de travail **barcode generator c#**. Il alloue le canevas de dessin interne et prépare les données pour le rendu.

## Étape 2 : Définir la **taille des pixels du code‑barres** et la hauteur initiale des barres

La qualité visuelle de l’image finale dépend de deux paramètres :

| Paramètre | Signification |
|-----------|----------------|
| `XDimension.Pixels` | Largeur d’un seul module (l’élément noir/blanc le plus petit). |
| `BarHeight.Pixels` | Hauteur des barres pour l’image courante. |

```csharp
        // Step 2: Set common visual parameters – module size and initial bar height
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // barcode pixel size (module width)
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first image height in pixels
```

Conserver la **taille des pixels du code‑barres** constante tout en modifiant la hauteur vous permet de créer des **dimensions personnalisées du code‑barres** qui respectent les directives de marque ou les exigences de numérisation.

## Étape 3 : Enregistrer le premier fichier PNG (hauteur 30 px)

Écrivez maintenant l’image sur le disque. La méthode `Save` accepte le chemin du fichier et le format d’image souhaité.

```csharp
        // Step 3: Save the first barcode image (30 px height)
        string outputFolder = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputFolder); // ensure the folder exists

        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);
```

Le fichier résultant est une **barcode image** avec une hauteur de barre de 30 px et une largeur de module de 2 px, parfaite pour les étiquettes compactes.

## Étape 4 : **Ajuster la hauteur du code‑barres** pour une version plus grande

Pour générer une seconde image avec une taille visuelle différente, il suffit de modifier la propriété `BarHeight.Pixels`. Cela montre à quel point il est simple d’**ajuster la hauteur du code‑barres** sans recréer le générateur.

```csharp
        // Step 4: Change the bar height to 60 px for a larger barcode
        barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

Modifier la hauteur tout en préservant la **taille des pixels du code‑barres** garantit que les barres restent nettes et que le rapport d’aspect global reste cohérent.

## Étape 5 : Enregistrer le deuxième fichier PNG (hauteur 60 px)

Enfin, persistez la version plus grande.

```csharp
        // Step 5: Save the second barcode image (60 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);
    }
}
```

Vous disposez maintenant de deux **dimensions personnalisées du code‑barres** enregistrées côte à côte :

- `DatabarBarHeight30Pixels.png` – hauteur de barre 30 px
- `DatabarBarHeight60Pixels.png` – hauteur de barre 60 px

Les deux images partagent la même **taille des pixels du code‑barres** de 2 px, garantissant une cohérence visuelle entre les différentes tailles.

## Pourquoi ces réglages sont importants

- La **taille des pixels du code‑barres** (`XDimension`) influence la lisibilité par le scanner. Une largeur de 2 px est une valeur par défaut courante qui équilibre la taille du fichier et la fiabilité de la lecture.
- La **hauteur des barres** détermine la taille du code‑barres sur une étiquette. Certains scanners de détail exigent une hauteur minimale ; d’autres autorisent des barres plus hautes pour des raisons esthétiques.
- Conserver l’instance du générateur active tout en ne modifiant que `BarHeight` réduit les allocations mémoire et accélère le traitement par lots.

## Cas limites et conseils de bonnes pratiques

| Situation | Approche recommandée |
|-----------|----------------------|
| **Différents formats d’image** (JPEG, BMP) | Changez `BarCodeImageFormat.Jpeg` ou `.Bmp` dans l’appel `Save`. JPEG est plus petit mais peut introduire des artefacts de compression. |
| **Sortie haute résolution** (par ex., 300 DPI) | Augmentez proportionnellement `XDimension.Pixels` (par ex., 4 px) et ajustez `BarHeight.Pixels` pour conserver la même taille physique. |
| **Chaînes de données dynamiques** | Encapsulez la création du générateur dans une méthode qui accepte la chaîne de données en paramètre, puis réutilisez la même instance `barcode` pour plusieurs enregistrements. |
| **Génération par lots thread‑safe** | Instanciez un `BarcodeGenerator` distinct par thread ou utilisez un pool thread‑local pour éviter les conditions de concurrence. |
| **Erreurs de permission du système de fichiers** | Vérifiez que `outputFolder` existe et que le processus possède les droits d’écriture ; gérez `IOException` de façon élégante. |

## Listing complet du code source

Voici le programme complet, autonome, que vous pouvez copier, coller et exécuter.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.IO;

class Program
{
    static void Main()
    {
        // Create a barcode generator – this is the core of the create barcode image workflow
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // Define barcode pixel size (module width) and initial height
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // barcode pixel size
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first image height

        // Prepare output folder
        string outputFolder = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputFolder);

        // Save first image (30 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);

        // Adjust height for the second image
        barcode.Parameters.Barcode.BarHeight.Pixels = 60; // adjust barcode height

        // Save second image (60 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);
    }
}
```

### Résultat attendu

Après l’exécution du programme, le dossier `YOUR_DIRECTORY` contient deux fichiers PNG :

- **DatabarBarHeight30Pixels.png** – un code‑barres compact adapté aux petites étiquettes.
- **DatabarBarHeight60Pixels.png** – une version plus grande idéale pour les applications à haute visibilité.

Les deux fichiers peuvent être ouverts avec n’importe quel visualiseur d’images, imprimés ou intégrés dans des PDF.

## Conclusion

Vous savez maintenant comment **créer des fichiers image de code‑barres** en C# avec un **barcode generator c#**, contrôler la **taille des pixels du code‑barres**, **ajuster la hauteur du code‑barres**, et produire des **dimensions personnalisées du code‑barres** répondant à des exigences de numérisation ou de marque spécifiques. L’exemple montre un modèle propre et réutilisable qui s’étend au traitement par lots ou à d’autres symbologies.

### Que devriez‑vous explorer ensuite

- Remplacez `EncodeTypes.DatabarOmniDirectional` par d’autres types tels que `EncodeTypes.Code128` ou `EncodeTypes.QR`.
- Appliquez des couleurs de premier plan/arrière‑plan via `barcode.Parameters.Barcode.ForeColor` et `BackColor`.
- Générez des sorties SVG ou PDF pour une impression vectorielle.
- Combinez plusieurs codes‑barres dans une même image à l’aide de `Graphics` pour des étiquettes composites.

N’hésitez pas à expérimenter avec les paramètres et à intégrer ce modèle dans votre gestion d’inventaire, de billetterie ou tout autre système nécessitant la création programmatique de codes‑barres. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code fonctionnels complets avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment créer une image de code‑barres en C# avec hauteur réglable](/barcode/english/python-java/general/how-to-create-barcode-image-in-c-with-adjustable-height/)
- [Comment générer un jeu de codes‑barres taille personnalisée et enregistrer l’image en C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [Créer une image de code‑barres C# avec exemple de générateur de code‑barres](/barcode/english/python-java/general/create-barcode-image-c-with-barcode-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
---
category: general
date: 2026-11-23
description: Créer un code‑barres postal Planet en C# avec Aspose.BarCode. Apprenez
  à générer un code‑barres Planet, à définir la dimension X et à enregistrer les barres
  remplies ou vides.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal planet barcode
- how to generate planet barcode
- Aspose.BarCode C#
- postal barcode example
- Planet barcode settings
language: fr
lastmod: 2026-11-23
og_description: Créez un code‑barres postal Planet en C# et apprenez à générer un
  code‑barres Planet avec Aspose.BarCode. Suivez l’exemple complet pour produire des
  barres pleines et vides.
og_image_alt: Example of a created postal planet barcode with filled bars
og_title: Comment créer un code‑barres Postal Planet en C# – guide étape par étape
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  headline: How to create postal planet barcode in C#
  type: TechArticle
- description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  name: How to create postal planet barcode in C#
  steps:
  - name: Changing the image format
    text: If your downstream system prefers JPEG, replace `BarCodeImageFormat.Png`
      with `BarCodeImageFormat.Jpeg`. JPEG introduces compression artifacts, so use
      it only when file size is a critical constraint.
  - name: Scaling the barcode
    text: 'You can enlarge the barcode while preserving the module width by adjusting
      the `Resolution` property:'
  - name: Using a custom background color
    text: 'The background can be set with:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Comment créer un code‑barres Postal Planet en C#
url: /fr/python-java/general/how-to-create-postal-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code‑barres postal Planet en C#

Si vous devez **créer un code‑barres postal Planet** dans une application .NET, ce guide vous montre exactement **comment générer un code‑barres Planet** en utilisant la bibliothèque Aspose.BarCode. Vous verrez comment configurer la dimension X, basculer entre les barres pleines et vides, et enregistrer les images au format PNG.

La génération d’un code‑barres Planet est courante pour les services postaux qui nécessitent des symboles à haute densité et lisibles par machine. À la fin de ce tutoriel, vous disposerez de deux fichiers PNG — l’un avec des barres pleines et l’autre avec des barres creuses — prêts à être intégrés dans n’importe quel flux de travail d’envoi postal.

## Prérequis

* SDK .NET 6.0 ou version ultérieure installé.
* Visual Studio 2022 (ou tout éditeur C#) configuré pour le développement .NET.
* Une licence NuGet active pour **Aspose.BarCode for .NET**. Installez le package avec :

```bash
dotnet add package Aspose.BarCode
```

Aucun service externe supplémentaire n’est requis ; la bibliothèque effectue tout l’encodage localement.

## Étape 1 – créer un code‑barres postal Planet

La première opération consiste à instancier un `BarcodeGenerator` pour la symbologie **Planet** et à fournir les données à encoder. La chaîne de données doit être numérique et comporter jusqu’à 12 chiffres selon la spécification postale.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

La création du générateur alloue toutes les structures internes nécessaires au rendu. La valeur d’énumération `EncodeTypes.Planet` sélectionne l’algorithme d’encodage approprié pour le format postal.

## Étape 2 – définir la dimension X pour une meilleure visibilité

La dimension X définit la largeur d’un seul module (l’élément de barre le plus petit). Une valeur de 4 pixels offre une représentation visuelle claire sans agrandir l’image globale.

```csharp
// Step 2: Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
```

Ajuster la dimension X est essentiel lorsque le code‑barres sera imprimé sur un support à basse résolution. Le même réglage sera réutilisé pour la version à barres vides afin de garder les deux images cohérentes.

## Étape 3 – enregistrer le code‑barres avec des barres pleines

Par défaut, le générateur rend des **barres pleines** (modules noirs solides). Enregistrer l’image se fait en un seul appel de méthode qui écrit le fichier PNG sur le disque.

```csharp
// Step 3: Save the barcode with the default setting (filled bars)
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

Remplacez `YOUR_DIRECTORY` par le chemin réel où vous souhaitez placer les fichiers de sortie. L’énumération `BarCodeImageFormat.Png` garantit une compression sans perte, idéale pour le traitement en aval.

## Étape 4 – créer un autre générateur de code‑barres Planet pour les barres vides

Pour produire une version qui utilise des **barres vides** (modules blancs sur fond noir), vous avez besoin d’une seconde instance de `BarcodeGenerator`. Réutiliser la même chaîne de données garantit que les deux images représentent le même code postal.

```csharp
// Step 4: Create another Planet barcode generator for the same data
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

Créer un générateur séparé isole la propriété `FilledBars`, vous permettant de basculer le style visuel sans affecter la première image.

## Étape 5 – configurer le générateur pour rendre des barres vides

Le drapeau `FilledBars` inverse le mode de rendu. Le définir à `false` indique à la bibliothèque de dessiner les barres comme vides (transparentes) tout en conservant le fond solide.

```csharp
// Step 5: Apply the same X‑dimension and configure empty bars
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
planetEmpty.Parameters.Barcode.FilledBars = false;
```

Conserver la même dimension X que la version remplie garantit que les deux fichiers PNG ont les mêmes dimensions, ce qui simplifie les calculs de mise en page dans les modèles d’impression.

## Étape 6 – enregistrer le code‑barres qui rend des barres vides

Enfin, écrivez l’image à barres vides sur le disque. Le même format PNG est utilisé, mais vous pouvez passer à JPEG ou BMP en modifiant la valeur de `BarCodeImageFormat`.

```csharp
// Step 6: Save the barcode that renders empty bars
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

À ce stade, vous avez deux fichiers :

* `PostalPlanetFilledBars.png` – barres noires pleines.
* `PostalPlanetEmptyBars.png` – barres creuses sur fond noir.

Les deux respectent la spécification postale pour la symbologie Planet.

## Code source complet

Assembler toutes les étapes donne une application console compacte que vous pouvez exécuter directement.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a Planet barcode with filled bars
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
            planetFilled.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

            // Create a Planet barcode with empty bars
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
            planetEmpty.Parameters.Barcode.FilledBars = false;
            planetEmpty.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcodes generated successfully.");
        }
    }
}
```

Compilez et exécutez le programme :

```bash
dotnet run
```

La console affiche *Barcodes generated successfully.* et les deux fichiers PNG apparaissent dans le dossier du projet.

## Résultat attendu

Ci‑dessous se trouve une représentation visuelle de l’image à barres pleines. La version à barres vides est identique, sauf que les barres sont transparentes.

![Exemple d’un code‑barres postal Planet créé avec des barres pleines](postal-planet-filled.png)

*Texte alternatif de l’image :* **Exemple d’un code‑barres postal Planet créé avec des barres pleines** (contient le mot‑clé principal).

Les deux images font 150 × 150 pixels par défaut, mais vous pouvez contrôler la taille globale avec les paramètres `ImageWidth` et `ImageHeight` si une résolution différente est requise.

## Variantes optionnelles

### Modifier le format d’image

Si votre système en aval préfère le JPEG, remplacez `BarCodeImageFormat.Png` par `BarCodeImageFormat.Jpeg`. Le JPEG introduit des artefacts de compression, donc utilisez‑le uniquement lorsque la taille du fichier est une contrainte critique.

### Redimensionner le code‑barres

Vous pouvez agrandir le code‑barres tout en conservant la largeur du module en ajustant la propriété `Resolution` :

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI
```

Des valeurs DPI plus élevées améliorent la qualité d’impression sur les imprimantes laser.

### Utiliser une couleur de fond personnalisée

Le fond peut être défini avec :

```csharp
planetEmpty.Parameters.Barcode.BackColor = System.Drawing.Color.LightGray;
```

Ceci est utile pour les tests visuels mais doit être évité sur les étiquettes postales de production, qui nécessitent un fond blanc.

## Questions fréquentes

**Cette fonctionnalité fonctionne‑t‑elle avec .NET Core ?**  
Oui. La bibliothèque Aspose.BarCode cible .NET Standard 2.0, qui est compatible avec .NET 5, .NET 6 et .NET Core 3.1.

**Que se passe‑t‑il si la chaîne de données contient des caractères non numériques ?**  
Les codes‑barres Planet n’acceptent que des entrées numériques. Fournir des lettres ou des symboles déclenche une `BarcodeException`. Validez l’entrée avant de créer le générateur.

**Puis‑je générer un code‑barres en mémoire sans l’écrire sur le disque ?**  
Utilisez la méthode `GenerateBarCodeImage` pour obtenir un objet `System.Drawing.Image`, puis diffusez‑le directement vers une réponse ou une base de données.

## Conclusion

Vous savez maintenant comment **créer un code‑barres postal Planet** en C# et comprenez **comment générer un code‑barres Planet** avec des styles de barres pleines et vides. Le tutoriel a couvert le flux complet — de l’initialisation du générateur, la configuration de la dimension X, le basculement du drapeau `FilledBars`, à l’enregistrement des fichiers PNG. Expérimentez avec les formats d’image, les réglages DPI et les couleurs de fond pour adapter le code‑barres à votre système d’envoi spécifique.

Pour l’étape suivante, explorez d’autres symbologies postales telles que **POSTNET** ou **Intelligent Mail** en utilisant la même API Aspose.BarCode. Ajuster des paramètres comme `EncodeTypes.Postnet` suit le même schéma démontré ici, vous permettant de créer une suite complète de génération de codes‑barres dans une seule base de code.

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [Create empty planet barcode, generate postal barcode in C#](/barcode/english/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/)
- [How to set width and generate a Planet barcode in C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Generate Postal Barcode in C# – Complete Guide with Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
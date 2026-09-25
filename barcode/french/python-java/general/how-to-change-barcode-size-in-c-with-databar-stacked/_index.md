---
category: general
date: 2026-08-22
description: Comment modifier la taille du code‑barres en C# avec le générateur DataBar
  Stacked Omni‑Directional. Apprenez à définir la dimension X et le rapport d’aspect
  pour la sortie PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to change barcode size
- DataBar Stacked Omni‑Directional barcode
- C# barcode generator
- barcode aspect ratio
- X‑dimension pixels
- BarCodeImageFormat PNG
language: fr
lastmod: 2026-08-22
og_description: Comment modifier la taille du code‑barres en C# avec le générateur
  DataBar Stacked Omni‑Directional. Suivez le guide étape par étape pour ajuster la
  dimension X et le rapport d’aspect.
og_image_alt: Screenshot showing how to change barcode size in C#
og_title: Comment modifier la taille du code-barres en C# – guide complet
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to change barcode size in C# using the DataBar Stacked Omni‑Directional
    generator. Learn to set X‑dimension and aspect ratio for PNG output.
  headline: How to change barcode size in C# with DataBar Stacked
  type: TechArticle
- description: How to change barcode size in C# using the DataBar Stacked Omni‑Directional
    generator. Learn to set X‑dimension and aspect ratio for PNG output.
  name: How to change barcode size in C# with DataBar Stacked
  steps:
  - name: Create a DataBar Stacked Omni‑Directional barcode generator
    text: The generator object holds all barcode settings. By passing `EncodeTypes.DatabarStackedOmniDirectional`
      and sample data, you create a valid barcode ready for further customization.
  - name: Set the basic module size (X‑dimension) in pixels
    text: The X‑dimension defines the width of a single barcode module. Adjusting
      it changes the overall width and height proportionally.
  - name: Change the barcode aspect ratio to 15 and save the image
    text: The **barcode aspect ratio** controls the height‑to‑width relationship.
      An aspect ratio of 15 yields a relatively tall barcode.
  - name: Change the barcode aspect ratio to 30 and save the new image
    text: Increasing the aspect ratio to 30 makes the barcode even taller, illustrating
      the flexibility of size adjustments.
  - name: Verify the generated images
    text: Open the PNG files in any image viewer. You should see two barcodes with
      identical width (controlled by the X‑dimension) but different heights (controlled
      by the aspect ratio). If the images appear blurry, increase the X‑dimension
      pixels; if they are too tall, lower the aspect ratio.
  - name: What to explore next
    text: '* **Custom colors** – experiment with `barcodeGenerator.Parameters.Barcode.ForeColor`
      and `BackColor` to match brand guidelines. * **Different barcode types** – replace
      `EncodeTypes.DatabarStackedOmniDirectional` with `EncodeTypes.QR` or `EncodeTypes.Code128`
      to see how size parameters differ across'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Comment modifier la taille du code‑barres en C# avec DataBar Stacked
url: /fr/python-java/general/how-to-change-barcode-size-in-c-with-databar-stacked/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment modifier la taille d’un code‑barres en C# avec DataBar Stacked

Si vous devez **modifier la taille d’un code‑barres** dans une application .NET, ce guide montre les étapes exactes en utilisant le générateur de code‑barres DataBar Stacked Omni‑Directional. Vous verrez comment contrôler la dimension X en pixels, ajuster le ratio d’aspect du code‑barres et enregistrer le résultat au format PNG.

Modifier la taille d’un code‑barres est souvent nécessaire lorsque l’espace d’étiquette imprimée est limité ou lorsqu’une image à plus haute résolution est requise pour les canaux numériques. Ce tutoriel couvre tout ce dont vous avez besoin, de l’initialisation du générateur à la production de deux images de tailles différentes.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

* Le SDK .NET 6.0 ou une version ultérieure installé  
* Une référence au package NuGet **Aspose.BarCode for .NET**  
* Une connaissance de base de la syntaxe C#  

Aucune configuration supplémentaire n’est requise ; le code fonctionne sous Windows, Linux ou macOS.

## Comment modifier la taille d’un code‑barres en C# – étape par étape

Les sections suivantes décomposent le processus en étapes discrètes et réutilisables. Chaque étape explique **pourquoi** le code est nécessaire, pas seulement **ce que** fait le code.

### Étape 1 : Créer un générateur de code‑barres DataBar Stacked Omni‑Directional

L’objet générateur contient tous les paramètres du code‑barres. En passant `EncodeTypes.DatabarStackedOmniDirectional` et des données d’exemple, vous créez un code‑barres valide prêt à être personnalisé davantage.

```csharp
// Step 1: Create a DataBar Stacked Omni‑Directional barcode generator with sample data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

*Pourquoi c’est important* – La classe **C# barcode generator** encapsule l’algorithme d’encodage. Commencer avec un générateur valide garantit que les modifications de taille ultérieures affectent le bon type de code‑barres.

### Étape 2 : Définir la taille de base du module (dimension X) en pixels

La dimension X définit la largeur d’un seul module du code‑barres. La modifier change la largeur et la hauteur globales proportionnellement.

```csharp
// Step 2: Define the basic module size (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Pourquoi c’est important* – Une dimension X plus grande produit un code‑barres plus gros, utile pour les imprimantes à basse résolution. À l’inverse, une valeur plus petite crée un code‑barres compact adapté aux petites étiquettes.

### Étape 3 : Modifier le ratio d’aspect du code‑barres à 15 et enregistrer l’image

Le **barcode aspect ratio** contrôle la relation hauteur‑largeur. Un ratio d’aspect de 15 donne un code‑barres relativement haut.

```csharp
// Step 3: Set the DataBar aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

*Pourquoi c’est important* – Différents appareils de lecture ont des exigences optimales de ratio d’aspect. Fixer le ratio à 15 montre comment **modifier la taille d’un code‑barres** en modifiant la hauteur tout en conservant la largeur définie par la dimension X.

#### Résultat attendu

Le fichier `DatabarAspectRatio15.png` montre un code‑barres DataBar Stacked Omni‑Directional plus haut que la valeur par défaut. La largeur du code‑barres reflète la dimension X de 2 pixels, et la hauteur suit le ratio 15.

### Étape 4 : Modifier le ratio d’aspect du code‑barres à 30 et enregistrer la nouvelle image

Augmenter le ratio d’aspect à 30 rend le code‑barres encore plus haut, illustrant la flexibilité des ajustements de taille.

```csharp
// Step 4: Change the DataBar aspect ratio to 30 and save the new image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

*Pourquoi c’est important* – En changeant simplement la valeur du **barcode aspect ratio**, vous voyez immédiatement comment **modifier la taille d’un code‑barres** sans recréer le générateur. Cela fait gagner du temps de traitement dans les scénarios par lots.

#### Résultat attendu

Le fichier `DatabarAspectRatio30.png` est visiblement plus haut que l’image précédente, confirmant que le ratio d’aspect influence directement la hauteur du code‑barres.

### Étape 5 : Vérifier les images générées

Ouvrez les fichiers PNG dans n’importe quel visualiseur d’images. Vous devez voir deux codes‑barres avec une largeur identique (contrôlée par la dimension X) mais des hauteurs différentes (contrôlées par le ratio d’aspect). Si les images apparaissent floues, augmentez les pixels de la dimension X ; si elles sont trop hautes, réduisez le ratio d’aspect.

```csharp
// Optional verification code – load images and print dimensions
using (var img15 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio15.png"))
using (var img30 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio30.png"))
{
    Console.WriteLine($"15‑ratio size: {img15.Width}×{img15.Height}");
    Console.WriteLine($"30‑ratio size: {img30.Width}×{img30.Height}");
}
```

*Pourquoi c’est important* – La vérification programmatique assure que les changements de taille ont été appliqués correctement, ce qui est crucial pour les pipelines de construction automatisés.

## Variantes courantes et cas limites

| Situation | Ajustement | Raison |
|-----------|------------|--------|
| **Étiquettes très petites** | Définir `XDimension.Pixels = 1` et `AspectRatio = 10` | Réduit l'empreinte globale tout en conservant la lisibilité |
| **Impression haute résolution** | Définir `XDimension.Pixels = 4` et `AspectRatio = 20` | Augmente la densité de pixels pour un rendu net |
| **Format d’image différent** | Remplacer `BarCodeImageFormat.Png` par `BarCodeImageFormat.Jpeg` | Utile lorsque le support PNG est limité |
| **Données dynamiques** | Passer une chaîne variable au constructeur `BarcodeGenerator` | Génère des codes‑barres pour chaque produit automatiquement |

Lorsque vous devez générer de nombreux codes‑barres de tailles variées, encapsulez les étapes dans une méthode :

```csharp
void GenerateDatabar(string data, int xDim, int aspectRatio, string filePath)
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
    generator.Parameters.Barcode.XDimension.Pixels = xDim;
    generator.Parameters.Barcode.DataBar.AspectRatio = aspectRatio;
    generator.Save(filePath, BarCodeImageFormat.Png);
}
```

Appeler `GenerateDatabar("(01)98765432109876", 3, 25, "output.png")` produit un code‑barres à taille personnalisée en une seule ligne de code.

## Astuces pro pour des changements de taille fiables

* **Toujours définir la dimension X avant le ratio d’aspect.** Modifier d’abord le ratio d’aspect peut entraîner un redimensionnement inattendu si la dimension X prend une valeur par défaut non idéale.  
* **Utiliser un dossier de sortie cohérent.** Hard‑coding `"YOUR_DIRECTORY"` fonctionne pour les démonstrations, mais en production privilégiez `Path.Combine(Environment.CurrentDirectory, "Barcodes")`.  
* **Valider la taille de l’image générée.** De petits changements de dimension X peuvent ne pas être perceptibles à l’écran ; vérifier les dimensions en pixels garantit que la modification a bien été prise en compte.  

## Conclusion

Vous savez maintenant **comment modifier la taille d’un code‑barres** en C# avec le générateur DataBar Stacked Omni‑Directional. En ajustant les **pixels de la dimension X** et le **ratio d’aspect du code‑barres**, vous pouvez produire des images PNG qui s’adaptent à n’importe quel format d’étiquette ou exigence de résolution. L’exemple complet et exécutable ci‑dessus montre le flux complet, de la création du générateur à la vérification de la taille.

### Ce que vous pouvez explorer ensuite

* **Couleurs personnalisées** – expérimentez avec `barcodeGenerator.Parameters.Barcode.ForeColor` et `BackColor` pour respecter la charte graphique.  
* **Autres types de code‑barres** – remplacez `EncodeTypes.DatabarStackedOmniDirectional` par `EncodeTypes.QR` ou `EncodeTypes.Code128` pour voir comment les paramètres de taille diffèrent selon les symbologies.  
* **Traitement par lots** – combinez la méthode `GenerateDatabar` avec une importation CSV pour créer des milliers de codes‑barres automatiquement.

N’hésitez pas à adapter les extraits de code à l’architecture de votre projet, et laissez les ajustements de taille du code‑barres améliorer la fiabilité de lecture et le design visuel. Bon codage !

## Que devez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets et fonctionnels avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
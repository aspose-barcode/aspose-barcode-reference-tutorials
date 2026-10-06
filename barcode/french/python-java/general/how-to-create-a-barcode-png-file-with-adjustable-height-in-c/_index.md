---
category: general
date: 2026-08-19
description: Apprenez à générer un fichier PNG de code‑barres en C# et à ajuster sa
  hauteur, en couvrant la génération d’images de code‑barres et la modification facile
  de la hauteur du code‑barres.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode png file
- how to generate barcode
- adjust barcode height
- change barcode height
language: fr
lastmod: 2026-08-19
og_description: Créez un fichier PNG de code‑barres en C# et apprenez à générer des
  images de code‑barres, à ajuster la hauteur du code‑barres et à modifier la hauteur
  du code‑barres pour des scans optimaux.
og_image_alt: barcode PNG file showing Databar OmniDirectional barcode at two heights
og_title: Créer un fichier PNG de code‑barres en C# – guide étape par étape
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Learn how to generate a barcode PNG file in C# and adjust its height,
    covering how to generate barcode images and change barcode height easily.
  headline: How to create a barcode PNG file with adjustable height in C#
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`,
      `BarCodeImageFormat.Bmp`, etc.
    question: Can I generate other image formats (JPEG, BMP)?
  - answer: Serve the generated PNG via an HTTP endpoint or convert it to a Base64
      string and place it in an `<img>` tag’s `src` attribute.
    question: How do I embed the PNG in a web page?
  - answer: 'Use `generator.Parameters.Image.BackgroundColor = Color.White;` (or any
      `System.Drawing.Color`). ## Conclusion You now know how to **generate a barcode
      PNG file** in C# and precisely **adjust barcode height** to meet scanning or
      design requirements. By changing the `BarHeight.Pixels` property you ca'
    question: Is there a way to set the background color?
  type: FAQPage
tags:
- barcode
- C#
- image generation
title: Comment créer un fichier PNG de code‑barres avec une hauteur réglable en C#
url: /fr/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un fichier PNG de code‑barres avec hauteur réglable en C#

Si vous devez créer un **fichier PNG de code‑barres** en C#, ce guide vous montre exactement comment faire. Vous verrez un exemple complet et exécutable qui démontre **comment générer des images de code‑barres** et comment **ajuster la hauteur du code‑barres** pour différents cas d’utilisation.

Générer un fichier PNG de code‑barres est une exigence courante pour les systèmes d’inventaire, les terminaux de point de vente et toute application qui doit imprimer ou afficher des données lisibles par machine. À la fin de ce tutoriel, vous serez capable de modifier la hauteur du code‑barres, d’enregistrer plusieurs fichiers PNG et de comprendre l’impact de la hauteur sur la fiabilité de la lecture.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

* Le SDK .NET 6.0 ou une version ultérieure installé  
* Visual Studio 2022 (ou tout IDE supportant .NET)  
* Le package NuGet **Aspose.BarCode for .NET** (l’exemple de code utilise cette bibliothèque)  

Vous pouvez ajouter le package depuis la ligne de commande :

```bash
dotnet add package Aspose.BarCode
```

> **Astuce :** La version d’évaluation gratuite d’Aspose.BarCode fonctionne pour le développement et les tests. Pour la production, obtenez une clé sous licence.

## Installer la bibliothèque de code‑barres

La première étape consiste à référencer la bibliothèque dans votre projet. Ajoutez les directives `using` suivantes en haut de votre fichier C# :

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Ces espaces de noms vous donnent accès à `BarcodeGenerator`, `EncodeTypes` et `BarCodeImageFormat`.

## Créer le fichier PNG de code‑barres

Nous créons maintenant une instance de `BarcodeGenerator` qui produira un **fichier PNG de code‑barres**. L’exemple utilise la symbologie Databar OmniDirectional, mais vous pouvez remplacer `EncodeTypes.DatabarOmniDirectional` par n’importe quel type supporté.

```csharp
// Step 1: Create a DataBar Omnidirectional generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

La chaîne `"(01)12345678901231"` suit le format d’Identifiant d’Application GS1 pour un GTIN à 14 chiffres. Ajustez les données pour correspondre à vos propres identifiants de produit.

## Définir la dimension X (facultatif)

La dimension X définit la largeur d’un seul module du code‑barres. Une valeur basée sur les pixels vous donne un contrôle précis sur la taille de l’image.

```csharp
// Optional: Set the pixel size of the X‑dimension (module width)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Une valeur de `2` pixels fonctionne bien pour la plupart des affichages écran. Augmentez‑la si vous avez besoin d’un code‑barres plus grand lors de l’impression.

## Ajuster la hauteur du code‑barres et enregistrer le fichier PNG

La propriété **BarHeight** contrôle la taille verticale des barres. Modifier cette valeur vous permet de **ajuster la hauteur du code‑barres** sans affecter les données encodées.

```csharp
// Step 2: Generate a 30‑pixel‑high barcode and save it as PNG
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Le fichier `DatabarBarHeight30Pixels.png` est maintenant un **fichier PNG de code‑barres** de 30 pixels de haut.  

Pour **modifier la hauteur du code‑barres** et créer une seconde image, il suffit d’assigner une nouvelle valeur et d’appeler à nouveau `Save` :

```csharp
// Step 3: Change the height to 60 pixels and save the new image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
barcodeGenerator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Vous avez maintenant deux fichiers PNG — un à 30 px et un autre à 60 px — démontrant comment **ajuster la hauteur du code‑barres** à la volée.

### Pourquoi la hauteur des barres est importante

* **Lisibilité :** Les lecteurs attendent une hauteur minimale pour une détection fiable. Un code‑barres trop court peut être manqué, surtout avec des caméras basse résolution.  
* **Esthétique :** Adapter la hauteur du code‑barres aux éléments de design environnants crée une interface plus propre.  
* **Contraintes d’impression :** Certains imprimantes d’étiquettes ont des emplacements de hauteur fixes ; ajuster la hauteur du code‑barres garantit qu’il s’y intègre.

**Bonne pratique :** Gardez la hauteur comme multiple de la dimension X (par ex., 30 px lorsque la dimension X est de 2 px) afin de maintenir les proportions et éviter les distorsions.

## Exemple complet

Voici le programme complet, autonome, que vous pouvez coller dans une application console et exécuter immédiatement.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator with Databar OmniDirectional data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set a reasonable X‑dimension (module width)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First height: 30 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode as DatabarBarHeight30Pixels.png");

        // 4️⃣ Second height: 60 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode as DatabarBarHeight60Pixels.png");
    }
}
```

**Sortie attendue**

L’exécution du programme crée deux fichiers dans le répertoire de travail de l’exécutable :

* `DatabarBarHeight30Pixels.png` – un fichier PNG de code‑barres de 30 pixels de haut  
* `DatabarBarHeight60Pixels.png` – un fichier PNG de code‑barres de 60 pixels de haut  

Ouvrez l’un ou l’autre PNG avec n’importe quel visualiseur d’images ; vous verrez un code‑barres Databar OmniDirectional clair, prêt à être scanné.

## Cas limites et dépannage

| Situation | À vérifier | Correction recommandée |
|-----------|------------|------------------------|
| Le code‑barres apparaît flou | Dimension X trop basse pour la hauteur choisie | Augmentez `XDimension.Pixels` (par ex., de 2 à 3) |
| Le lecteur échoue sur un code‑barres de faible hauteur | Hauteur inférieure au minimum du lecteur | Définissez `BarHeight.Pixels` à au moins 30 px (ou selon les spécifications du lecteur) |
| Le fichier PNG est vide ou corrompu | Chemin de sortie invalide ou permission d’écriture refusée | Utilisez un chemin absolu ou assurez‑vous que l’application a les droits d’écriture |
| Besoin d’une symbologie différente | `EncodeTypes` actuel inadapté | Remplacez `EncodeTypes.DatabarOmniDirectional` par une autre valeur d’énumération (par ex., `EncodeTypes.Code128`) |

## Questions fréquentes

**Q : Puis‑je générer d’autres formats d’image (JPEG, BMP) ?**  
R : Oui. Remplacez `BarCodeImageFormat.Png` par `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp`, etc.

**Q : Comment intégrer le PNG dans une page web ?**  
R : Servez le PNG généré via un point de terminaison HTTP ou convertissez‑le en chaîne Base64 et placez‑le dans l’attribut `src` d’une balise `<img>`.

**Q : Existe‑t‑il un moyen de définir la couleur d’arrière‑plan ?**  
R : Utilisez `generator.Parameters.Image.BackgroundColor = Color.White;` (ou toute `System.Drawing.Color`).

## Conclusion

Vous savez maintenant comment **générer un fichier PNG de code‑barres** en C# et **ajuster précisément la hauteur du code‑barres** pour répondre aux exigences de lecture ou de design. En modifiant la propriété `BarHeight.Pixels`, vous pouvez **modifier la hauteur du code‑barres** à la volée et produire plusieurs actifs PNG à partir d’une même base de code.

Ensuite, explorez d’autres options de personnalisation telles que la couleur du premier plan, les marges et l’ajout de texte lisible par l’homme. Vous pouvez également expérimenter avec différentes symbologies (`EncodeTypes.Code128`, `EncodeTypes.QR`) pour élargir le champ des données que vous pouvez encoder.

Bon codage, et que vos codes‑barres soient toujours lus du premier coup !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités supplémentaires de l’API et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
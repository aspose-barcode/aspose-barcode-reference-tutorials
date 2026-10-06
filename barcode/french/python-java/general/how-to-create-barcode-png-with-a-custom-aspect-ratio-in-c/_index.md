---
category: general
date: 2026-10-05
description: Créer un PNG de code-barres en C# et apprendre comment définir le rapport
  d’aspect à 15 pour les codes-barres DataBar empilés omnidirectionnels.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to set aspect ratio
- set aspect ratio 15
language: fr
lastmod: 2026-10-05
og_description: Créez un PNG de code-barres en C# et découvrez comment définir le
  rapport d’aspect 15 pour les codes-barres DataBar empilés omnidirectionnels en quelques
  étapes.
og_image_alt: Screenshot showing a generated barcode PNG with aspect ratio 15
og_title: Créer un PNG de code-barres en C# – définir le rapport d’aspect 15 tutoriel
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Create barcode PNG in C# and learn how to set aspect ratio 15 for stacked
    DataBar omnidirectional barcodes.
  headline: How to create barcode PNG with a custom aspect ratio in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Comment créer un PNG de code‑barres avec un rapport d’aspect personnalisé en
  C#
url: /fr/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un PNG de code-barres avec un ratio d'aspect personnalisé en C#

Si vous devez **créer un PNG de code-barres** en C#, ce guide vous montre **comment définir le ratio d'aspect** 15 pour un code-barres DataBar empilé omnidirectionnel. Nous passerons en revue chaque appel d'API, expliquerons pourquoi le ratio d'aspect est important, et vous fournirons un exemple complet et exécutable que vous pouvez intégrer à n'importe quel projet .NET.

Générer une image de code-barres est une exigence courante pour les systèmes d'inventaire, les étiquettes d'expédition et les applications de point de vente au détail. À la fin de ce tutoriel, vous disposerez d'un fichier PNG qui répond exactement aux spécifications visuelles requises par votre partenaire commercial. Aucun outil externe, aucune retouche d'image manuelle — juste du code.

## Pré-requis

Avant de commencer, assurez‑vous d'avoir :

* .NET 6.0 ou version ultérieure (l'exemple utilise .NET 6 mais fonctionne avec .NET 5+)
* Visual Studio 2022 (ou tout IDE supportant .NET)
* Le package NuGet **Aspose.BarCode for .NET**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Permission d'écriture sur le dossier où vous souhaitez enregistrer le fichier PNG

Ces exigences sont minimales ; le même code fonctionne sous .NET Core, .NET Framework ou une application console.

## Créer un PNG de code-barres avec Aspose.BarCode

La première étape consiste à instancier la classe `BarcodeGenerator` avec le type de code‑barres correct. Dans ce cas, nous utilisons `EncodeTypes.DatabarStackedOmniDirectional`, qui produit un DataBar empilé pouvant être lu depuis n'importe quelle direction.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

*Pourquoi c'est important :* Le constructeur prend deux arguments — **la symbologie du code‑barres** et **la chaîne de données**. Le format DataBar attend un identifiant d'application GS1, c'est pourquoi les données d'exemple commencent par `(01)`.

## Comment définir le ratio d'aspect pour un DataBar empilé

La largeur visuelle d'un DataBar est contrôlée par la propriété **ratio d'aspect**. Un ratio plus élevé rend les barres plus larges, ce qui peut améliorer la fiabilité de la lecture sur des imprimantes à basse résolution.

```csharp
// Step 2: Define the module width (X‑dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Le `XDimension` définit la taille d'un module unique (la plus petite barre ou espace). Le garder à 2 px donne une image nette et à haute densité, adaptée à la plupart des imprimantes d'étiquettes.

## Définir le ratio d'aspect 15 – explication du code

Nous appliquons maintenant l'exigence **définir le ratio d'aspect 15**. C'est le cœur du tutoriel et montre l'appel d'API exact dont vous avez besoin.

```csharp
// Step 3: Set the DataBar aspect ratio to 15 for a wider appearance
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

*Pourquoi 15 ?* Le ratio d'aspect par défaut pour le DataBar empilé est 12. Le porter à 15 augmente la largeur de chaque barre de 25 %, ce qui correspond souvent aux spécifications des prestataires logistiques qui exigent un code‑barres plus large pour une lecture plus rapide.

## Enregistrer le code‑barres au format PNG

Une fois le générateur configuré, l'étape finale consiste à écrire l'image sur le disque. La méthode `Save` accepte un chemin de fichier et une énumération de format d'image.

```csharp
// Step 4: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Le format PNG conserve une qualité sans perte, garantissant que le code‑barres s'affiche exactement comme prévu sur n'importe quel écran ou imprimante.

## Exemple complet et sortie attendue

Voici le programme complet que vous pouvez copier dans la méthode `Main` d'une application console. Il inclut toutes les étapes décrites ci‑dessus, ainsi qu'un petit message de vérification.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with stacked DataBar (omnidirectional) and sample GS1 data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Set the DataBar aspect ratio to 15 – this is the key to a wider barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;

        // Choose a folder you have write access to
        string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";

        // Save the barcode as a PNG file
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode PNG created at: {outputPath}");
    }
}
```

**Sortie attendue**

L'exécution du programme crée un fichier nommé `DatabarAspectRatio15.png` contenant un code‑barres DataBar empilé clair et large. Lorsque vous ouvrez le PNG, vous devez voir un code‑barres étiré horizontalement qui reste conforme aux spécifications GS1 DataBar.

![Barcode PNG with aspect ratio 15](barcode-aspect15.png)

*texte alternatif de l'image :* **créer un PNG de code‑barres montrant un DataBar empilé avec un ratio d'aspect 15**

### Conseils et pièges courants

| Situation | Recommandation |
|-----------|----------------|
| **L'image apparaît floue** | Augmentez `XDimension.Pixels` à 3 px ou plus, mais gardez la taille globale de l'image inférieure à 500 px pour éviter des fichiers trop volumineux. |
| **Le scanner ne peut pas lire le code** | Vérifiez que la chaîne de données respecte le format GS1 (préfixe `(01)`). Assurez‑vous également que la résolution de l'imprimante est d'au moins 300 dpi. |
| **Besoin d'un autre format de fichier** | Remplacez `BarCodeImageFormat.Png` par `Jpeg`, `Bmp` ou `Gif` — l'API prend en charge tous les principaux formats raster. |
| **Exécution dans une application web** | Utilisez `generator.Save(Stream, BarCodeImageFormat.Png)` pour écrire directement à la réponse HTTP sans toucher au système de fichiers. |

### Extension de l'exemple

* **Plusieurs codes‑barres dans une même image :** Créez des instances supplémentaires de `BarcodeGenerator` et dessinez‑les sur un même `Bitmap` en utilisant `Graphics`.  
* **Ajout de texte lisible par l'homme :** Définissez `generator.Parameters.Caption.Visible = true` et personnalisez la police via `generator.Parameters.Caption.Font`.  
* **Ratio d'aspect dynamique :** Récupérez la valeur du ratio depuis un fichier de configuration ou une base de données pour générer des codes‑barres avec des largeurs variables à la volée.

## Conclusion

Dans ce tutoriel, vous avez appris comment **créer un PNG de code‑barres** en C# et à définir précisément le **ratio d'aspect** 15 pour un DataBar omnidirectionnel empilé. Le code complet et exécutable montre chaque appel d'API requis, explique pourquoi chaque paramètre est important, et fournit des conseils pratiques pour des déploiements en conditions réelles.  

Ensuite, vous pourrez explorer **comment définir le ratio d'aspect** pour d'autres types de code‑barres (par ex., QR Code ou Code 128) ou intégrer le générateur dans un service ASP .NET Core qui renvoie des images de code‑barres à la demande. Bon codage !

## Quoi apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets et fonctionnels avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités API supplémentaires et à explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment créer des images PNG de databar avec C# et Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [Comment créer un code‑barres databar empilé en C# avec Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [Personnaliser le ratio d'aspect d'un databar empilé omnidirectionnel dans .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
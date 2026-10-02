---
category: general
date: 2026-10-02
description: Apprenez à créer un code‑barres rm4scc en C# et à générer un code‑barres
  postal avec une hauteur personnalisée. Inclut du code étape par étape pour les codes‑barres
  Planet.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create rm4scc barcode
- how to generate postal barcode
- generate planet barcode
- how to set barcode height
language: fr
lastmod: 2026-10-02
og_description: Créez un code‑barres rm4scc en C# et apprenez à générer un code‑barres
  postal avec des dimensions exactes. Exemple complet de code et conseils de bonnes
  pratiques.
og_image_alt: Screenshot of RM4SCC and Planet barcodes generated with Aspose.BarCode
  in C#
og_title: Créer un code‑barres rm4scc avec hauteur personnalisée – Guide C#
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to create rm4scc barcode in C# and how to generate postal
    barcode with custom height. Includes step‑by‑step code for Planet barcodes.
  headline: How to create rm4scc barcode and control its height in C#
  type: TechArticle
- description: Learn how to create rm4scc barcode in C# and how to generate postal
    barcode with custom height. Includes step‑by‑step code for Planet barcodes.
  name: How to create rm4scc barcode and control its height in C#
  steps:
  - name: 2.1 Create an RM4SCC barcode (auto height)
    text: '```csharp // RM4SCC with automatic height BarcodeGenerator rm4sccAuto =
      new BarcodeGenerator(EncodeTypes.RM4SCC, "123456"); rm4sccAuto.Parameters.Barcode.XDimension.Pixels
      = 4; // controls bar width rm4sccAuto.Save($"{outputFolder}PostalRM4SCC_AutoHeight.png",
      BarCodeImageFormat.Png); ```'
  - name: 2.2 Create a Planet barcode (auto height)
    text: '```csharp // Planet barcode with automatic height BarcodeGenerator planetAuto
      = new BarcodeGenerator(EncodeTypes.Planet, "123456"); planetAuto.Parameters.Barcode.XDimension.Pixels
      = 4; planetAuto.Save($"{outputFolder}PostalPlanet_AutoHeight.png", BarCodeImageFormat.Png);
      ```'
  - name: 3.1 Fixed-height RM4SCC barcode
    text: '```csharp // RM4SCC with fixed height of 100 px BarcodeGenerator rm4sccFixed
      = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456"); rm4sccFixed.Parameters.Barcode.XDimension.Pixels
      = 4; rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100; // explicit height
      rm4sccFixed.Save($"{outputFolder}PostalRM'
  - name: 3.2 Fixed-height Planet barcode
    text: '```csharp // Planet barcode with fixed height of 100 px BarcodeGenerator
      planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456"); planetFixed.Parameters.Barcode.XDimension.Pixels
      = 4; planetFixed.Parameters.Barcode.BarHeight.Pixels = 100; planetFixed.Save($"{outputFolder}PostalPlanet_FixedH'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
- postal codes
title: Comment créer un code‑barres rm4scc et contrôler sa hauteur en C#
url: /fr/python-java/general/how-to-create-rm4scc-barcode-and-control-its-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code‑barres rm4scc et contrôler sa hauteur en C#

Si vous devez **créer un code‑barres rm4scc** pour un système de courrier, ce guide vous montre exactement comment générer des codes‑barres postaux et définir une hauteur de barre précise. Vous verrez à la fois l'approche par défaut (taille automatique) et la technique de hauteur explicite, afin de choisir la méthode qui correspond à vos exigences de conception.

Générer un code‑barres postal est une tâche courante lors de la création d’étiquettes d’expédition, de logiciels d’envoi en masse ou de toute solution qui s’intègre aux services postaux nationaux. Ce tutoriel couvre :

* **comment générer un code‑barres postal** pour les symbologies RM4SCC et Planet  
* **générer un code‑barres planet** avec les mêmes paramètres pour comparaison  
* **comment définir la hauteur du code‑barres** à une valeur en pixels fixe  
* code C# complet et exécutable utilisant la bibliothèque Aspose.BarCode  

À la fin de l’article, vous disposerez d’un programme console prêt à l’emploi qui produit quatre fichiers PNG — deux avec hauteur automatique et deux avec une hauteur fixe de 100 px.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

* .NET 6.0 SDK ou version ultérieure (le code fonctionne également avec .NET Framework 4.7+).  
* Visual Studio 2022 ou tout IDE capable de compiler des projets C#.  
* Le package NuGet **Aspose.BarCode for .NET** (`Install-Package Aspose.BarCode`).  

Aucune configuration supplémentaire n’est requise ; la bibliothèque gère tout le rendu d’image en interne.

## Étape 1 : Configurer le projet et importer les espaces de noms

Créez un nouveau projet console et ajoutez les directives `using` nécessaires. Cette étape prépare l’environnement pour la génération de codes‑barres.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generator
using Aspose.BarCode;               // For ImageFormat enum

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Define where the PNG files will be saved
            string outputFolder = "C:/Barcodes/";   // <-- adjust to a writable folder
            // Ensure the folder exists
            System.IO.Directory.CreateDirectory(outputFolder);
```

*Pourquoi c’est important* : déclarer `outputFolder` une seule fois évite les répétitions et facilite la modification du chemin de destination ultérieurement. L’appel à `CreateDirectory` garantit que l’opération d’enregistrement ne échouera pas parce que le dossier est absent.

## Étape 2 : Comment générer un code‑barres postal avec hauteur par défaut

### 2.1 Créer un code‑barres RM4SCC (hauteur auto)

```csharp
            // RM4SCC with automatic height
            BarcodeGenerator rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4; // controls bar width
            rm4sccAuto.Save($"{outputFolder}PostalRM4SCC_AutoHeight.png", BarCodeImageFormat.Png);
```

### 2.2 Créer un code‑barres Planet (hauteur auto)

```csharp
            // Planet barcode with automatic height
            BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
            planetAuto.Save($"{outputFolder}PostalPlanet_AutoHeight.png", BarCodeImageFormat.Png);
```

Les deux appels omettent la propriété `BarHeight`, de sorte que la bibliothèque calcule la hauteur optimale selon les spécifications de la symbologie. C’est la façon la plus simple **comment générer un code‑barres postal** lorsque vous n’avez pas de contraintes de mise en page strictes.

## Étape 3 : Comment définir la hauteur du code‑barres pour une mise en page précise

Lorsqu’un modèle d’étiquette nécessite une taille visuelle fixe, vous devez définir explicitement la hauteur des barres. Le code suivant montre **comment définir la hauteur du code‑barres** à 100 pixels pour les deux symbologies.

### 3.1 Code‑barres RM4SCC à hauteur fixe

```csharp
            // RM4SCC with fixed height of 100 px
            BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100; // explicit height
            rm4sccFixed.Save($"{outputFolder}PostalRM4SCC_FixedHeight.png", BarCodeImageFormat.Png);
```

### 3.2 Code‑barres Planet à hauteur fixe

```csharp
            // Planet barcode with fixed height of 100 px
            BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
            planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            planetFixed.Save($"{outputFolder}PostalPlanet_FixedHeight.png", BarCodeImageFormat.Png);
```

*Pourquoi cela fonctionne* : la propriété `BarHeight.Pixels` remplace le calcul automatique, forçant le rendu à utiliser exactement le nombre de pixels indiqué. C’est essentiel lorsque le code‑barres doit s’aligner avec d’autres éléments UI ou des modèles imprimés.

## Étape 4 : Vérifier les images générées

Après l’exécution du programme, ouvrez les quatre fichiers PNG dans le `outputFolder`. Vous devriez voir :

| Nom du fichier | Hauteur | Symbologie |
|----------------|---------|------------|
| `PostalRM4SCC_AutoHeight.png` | Auto‑calculée (≈ 50 px) | RM4SCC |
| `PostalPlanet_AutoHeight.png` | Auto‑calculée (≈ 50 px) | Planet |
| `PostalRM4SCC_FixedHeight.png` | **100 px** (exacte) | RM4SCC |
| `PostalPlanet_FixedHeight.png` | **100 px** (exacte) | Planet |

Les deux images « FixedHeight » ont des barres précisément de 100 px de haut, ce qui répond à la exigence **comment définir la hauteur du code‑barres** pour un format d’étiquette standardisé.

## Étape 5 : Pièges courants et conseils de bonnes pratiques

* **Valeurs de hauteur invalides** – Attribuer `BarHeight.Pixels` à un nombre négatif déclenche une `ArgumentException`. Validez toujours les entrées utilisateur avant de les affecter.  
* **Sensibilité à la résolution** – La taille visuelle à l’écran dépend également du DPI. Si vous exportez plus tard en PDF, envisagez de définir `ImageResolution` pour conserver des dimensions physiques cohérentes.  
* **X‑dimension vs. bar height** – `XDimension.Pixels` contrôle la **width** des barres, pas leur hauteur. Oublier de le régler peut rendre le code‑barres trop fin, surtout à faible DPI.  
* **Thread safety** – Les instances de `BarcodeGenerator` ne sont **pas** thread‑safe. Créez une nouvelle instance par thread ou synchronisez l’accès si vous générez de nombreux codes‑barres en parallèle.

## Code source complet (exécutable)

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Output directory – change as needed
            string outputFolder = "C:/Barcodes/";
            System.IO.Directory.CreateDirectory(outputFolder);

            // -----------------------------------------------------------------
            // 1. RM4SCC – automatic height
            // -----------------------------------------------------------------
            BarcodeGenerator rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccAuto.Save($"{outputFolder}PostalRM4SCC_AutoHeight.png", BarCodeImageFormat.Png);

            // -----------------------------------------------------------------
            // 2. Planet – automatic height
            // -----------------------------------------------------------------
            BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
            planetAuto.Save($"{outputFolder}PostalPlanet_AutoHeight.png", BarCodeImageFormat.Png);

            // -----------------------------------------------------------------
            // 3. RM4SCC – fixed height of 100 px
            // -----------------------------------------------------------------
            BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            rm4sccFixed.Save($"{outputFolder}PostalRM4SCC_FixedHeight.png", BarCodeImageFormat.Png);

            // -----------------------------------------------------------------
            // 4. Planet – fixed height of 100 px
            // -----------------------------------------------------------------
            BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
            planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            planetFixed.Save($"{outputFolder}PostalPlanet_FixedHeight.png", BarCodeImageFormat.Png);

            Console.WriteLine("All barcodes generated successfully.");
        }
    }
}
```

Copiez le code dans `Program.cs`, restaurez les packages NuGet, puis exécutez `dotnet run`. La console confirmera la génération réussie, et les fichiers PNG apparaîtront dans `C:/Barcodes/`.

## Conclusion

Vous savez maintenant comment **créer un code‑barres rm4scc** et **générer un code‑barres planet** en C#, à la fois avec dimensionnement automatique et avec une hauteur de barre définie manuellement. En contrôlant `BarHeight.Pixels`, vous répondez à la question **comment définir la hauteur du code‑barres**, garantissant que vos codes‑barres postaux s’intègrent parfaitement dans n’importe quel modèle d’étiquette.

Ensuite, vous pourriez explorer :

* **comment générer un code‑barres postal** dans d’autres formats tels que PDF ou SVG (`BarCodeImageFormat.Pdf`, `BarCodeImageFormat.Svg`).  
* Ajouter du texte lisible par l’homme sous le code‑barres (`Parameters.Caption`).  
* Intégrer le générateur dans une API ASP.NET Core pour fournir des codes‑barres à la demande.

N’hésitez pas à expérimenter avec différentes valeurs de `XDimension`, des couleurs ou des images d’arrière‑plan afin d’harmoniser votre identité visuelle tout en respectant les normes des codes‑barres. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets et fonctionnels avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment générer un code‑barres postal en C# avec des dimensions personnalisées](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/)
- [Comment créer un code‑barres planet PNG avec C# – guide pas à pas](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/)
- [Comment définir la largeur et générer un code‑barres Planet en C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
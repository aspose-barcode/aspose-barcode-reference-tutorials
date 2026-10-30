---
category: general
date: 2026-10-28
description: Créez rapidement une image de code‑barres en C#. Apprenez à utiliser
  le générateur de codes‑barres C#, comment définir la taille des pixels et comment
  modifier le rapport d’aspect pour DataBar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- how to set pixel size
- how to change aspect ratio
- how to generate databar
language: fr
lastmod: 2026-10-28
og_description: Créez une image de code-barres en C# avec un générateur de codes-barres.
  Suivez ce guide pour définir la taille des pixels, modifier le rapport d’aspect
  et générer des codes-barres DataBar.
og_image_alt: Screenshot of a generated barcode image created with C#
og_title: Créer une image de code-barres en C# – guide étape par étape
schemas:
- author: GroupDocs
  dateModified: '2026-10-28'
  description: Create barcode image in C# quickly. Learn barcode generator c# usage,
    how to set pixel size, and how to change aspect ratio for DataBar.
  headline: How to create barcode image with C# using Barcode Generator
  type: TechArticle
tags:
- barcode
- C#
- imaging
title: Comment créer une image de code‑barres avec C# en utilisant Barcode Generator
url: /fr/python-java/general/how-to-create-barcode-image-with-c-using-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer une image de code-barres avec C# en utilisant Barcode Generator

Si vous devez **créer une image de code-barres** dans une application .NET, ce guide vous montre exactement comment faire. Vous verrez un exemple complet et exécutable qui utilise la bibliothèque Barcode Generator C# pour générer un code-barres DataBar empilé omnidirectionnel, définir la taille des pixels et modifier le rapport d'aspect.

Générer des codes-barres de manière programmatique élimine le besoin d'outils externes et vous permet d'intégrer l'image directement dans des PDF, des rapports ou des contrôles UI. Dans les étapes ci‑dessous, nous couvrons également **comment définir la taille des pixels** et **comment modifier le rapport d'aspect**, deux exigences courantes lorsque vous avez besoin d'un code-barres net et correctement mis à l'échelle.

## Prérequis

* .NET 6.0 SDK ou version ultérieure installé  
* Un IDE compatible C# (Visual Studio, Rider ou VS Code)  
* Le package NuGet `BarcodeGenerator` (par ex., `GroupDocs.Barcode` ou `Aspose.Barcode`) installé dans votre projet  

Vous pouvez ajouter le package avec la commande suivante :

```bash
dotnet add package GroupDocs.Barcode
```

> **Astuce :** Vérifiez que la version du package correspond à votre framework cible pour éviter les incompatibilités d'exécution.

## Créer une image de code-barres avec Barcode Generator C#

La première étape consiste à instancier le générateur avec le type de code-barres et les données souhaités. L'exemple ci‑dessous crée un code-barres **DataBar empilé omnidirectionnel**, idéal pour les scénarios de numérisation en magasin.

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // Step 1: Create a BarcodeGenerator for DataBar stacked omnidirectional
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example data

        // Step 2: Set the pixel size of the X‑dimension (how to set pixel size)
        barcode.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 3: Save an image with the first aspect ratio (how to generate databar)
        barcode.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcode.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // Step 4: Change the aspect ratio (how to change aspect ratio) and save a second image
        barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcode.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### Pourquoi chaque ligne est importante

- **Instantiate `BarcodeGenerator`** – Le constructeur prend une symbologie de code‑barres (`EncodeTypes.DatabarStackedOmniDirectional`) et la chaîne de données brute. Choisir la bonne symbologie garantit que le scanner peut lire le code.  
- **Set `XDimension.Pixels`** – Cette propriété contrôle la largeur de l'élément de barre le plus petit. Une valeur de `2` produit une image fine qui reste lisible sur la plupart des écrans. Augmentez‑la si vous avez besoin d'un code‑barres plus grand pour les imprimantes basse résolution.  
- **Configure `AspectRatio`** – La famille DataBar prend en charge plusieurs rapports d'aspect qui affectent la relation hauteur‑largeur. Les valeurs `15` et `30` sont courantes ; `15` donne un code‑barres plus court, tandis que `30` en produit un plus haut.  
- **`Save` method** – Enregistre le code‑barres généré dans un fichier PNG. Vous pouvez remplacer `BarCodeImageFormat.Png` par `Jpeg` ou `Bmp` si votre système en aval nécessite un format différent.

## Comment définir la taille des pixels pour différents contextes de rendu

La taille des pixels détermine la densité visuelle du code‑barres. Si le code‑barres doit être affiché sur un moniteur haute DPI, vous pouvez augmenter la taille des pixels à `3` ou `4`. À l'inverse, pour les imprimantes thermiques basse résolution, une taille de pixel plus petite (par ex., `1`) réduit la consommation d'encre.

```csharp
// Example: increase pixel size for a high‑resolution display
barcode.Parameters.Barcode.XDimension.Pixels = 4;
```

**Cas limite :** Définir la taille des pixels trop basse (< 1) déclenche une `ArgumentOutOfRangeException`. Validez toujours la valeur avant de l'assigner.

## Comment modifier le rapport d'aspect sans recréer le générateur

Modifier le rapport d'aspect est une simple mise à jour de propriété ; vous n'avez **pas** besoin de recréer l'instance `BarcodeGenerator`. Cela économise de la mémoire et améliore les performances lorsque vous avez besoin de plusieurs images avec des formes différentes.

```csharp
// Switch from a short to a tall barcode
barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
barcode.Save("TallDatabar.png", BarCodeImageFormat.Png);
```

Si vous avez besoin de plus de deux rapports, vous pouvez parcourir un tableau :

```csharp
int[] ratios = { 15, 20, 25, 30 };
foreach (int ratio in ratios)
{
    barcode.Parameters.Barcode.DataBar.AspectRatio = ratio;
    string fileName = $"DatabarAspectRatio{ratio}.png";
    barcode.Save(fileName, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {fileName}");
}
```

## Résultat attendu

L'exécution du programme crée deux fichiers PNG (ou plus, si vous utilisez la boucle). Ouvrez-les dans n'importe quel visualiseur d'images ; vous devriez voir un code‑barres DataBar propre :

* **DatabarAspectRatio15.png** – code‑barres court et large, adapté aux espaces d'étiquettes étroits.  
* **DatabarAspectRatio30.png** – code‑barres plus haut qui améliore la fiabilité de lecture sur les scanners inclinés.

Les deux images partagent la même taille de pixel (2 px par module) mais diffèrent uniquement en hauteur, démontrant **comment modifier le rapport d'aspect** tout en conservant les autres paramètres constants.

## Pièges courants et comment les éviter

| Symptom | Cause | Fix |
|---------|-------|-----|
| Le code‑barres apparaît flou | `XDimension.Pixels` réglé trop bas pour la résolution de sortie | Augmentez la taille des pixels à au moins `2` pour l'affichage à l'écran, `3` pour l'impression |
| Le scanner ne peut pas lire le code | `EncodeTypes` incorrect pour le format des données | Vérifiez que les données GTIN‑14 correspondent à la symbologie choisie |
| `ArgumentOutOfRangeException` sur le rapport d'aspect | Valeur de ratio non prise en charge par la bibliothèque (plage valide : 15‑30) | Utilisez uniquement les valeurs documentées par la bibliothèque, ou capturez l'exception et revenez à une valeur par défaut |
| Fichier introuvable après `Save` | Le chemin relatif pointe vers un répertoire inexistant | Utilisez un chemin absolu ou assurez‑vous que `Directory.CreateDirectory` est appelé d'abord |

```csharp
// Ensure the output folder exists
string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputDir);
barcode.Save(Path.Combine(outputDir, "DatabarAspectRatio15.png"), BarCodeImageFormat.Png);
```

## Prochaines étapes – étendre le flux de travail du code‑barres

Maintenant que vous pouvez **créer une image de code‑barres**, vous pourriez vouloir :

* **Intégrer le PNG dans un PDF** en utilisant une bibliothèque comme `PdfSharp` ou `iTextSharp`.  
* **Générer d'autres symbologies** (QR, Code128, PDF417) en modifiant l'énumération `EncodeTypes`.  
* **Appliquer des transformations de couleur** en accédant à `barcode.Parameters.Barcode.Image.Color`.  
* **Servir l'image via un point de terminaison ASP.NET Core** pour une génération à la volée dans les applications web.

Chacun de ces sujets s'appuie sur les mêmes concepts de base abordés dans ce tutoriel, tels que l'utilisation du **barcode generator c#**, le contrôle de la taille des pixels et la manipulation du rapport d'aspect.

## Conclusion

Vous savez maintenant comment **créer une image de code‑barres** en C# avec Barcode Generator, comment définir la taille des pixels, comment modifier le rapport d'aspect et comment générer efficacement des codes‑barres DataBar. L'exemple complet et exécutable peut être copié dans n'importe quel projet .NET, adapté à d'autres symbologies et étendu pour répondre à des flux de travail réels.

N'hésitez pas à expérimenter avec différentes valeurs `XDimension`, rapports d'aspect et formats de sortie. Si vous rencontrez des problèmes, consultez à nouveau le tableau « Pièges courants » ou la documentation officielle de la bibliothèque pour des options de configuration plus avancées. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités d'API supplémentaires et à explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment créer une image de code‑barres et ajuster son rapport d'aspect en C#](/barcode/english/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/)
- [Comment générer un code‑barres avec taille personnalisée et enregistrer l'image en C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [Comment utiliser un générateur de code‑barres C# pour créer des codes‑barres DataBar](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
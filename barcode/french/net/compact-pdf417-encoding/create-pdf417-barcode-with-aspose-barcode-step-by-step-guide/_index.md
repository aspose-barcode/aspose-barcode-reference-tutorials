---
category: general
date: 2026-08-25
description: Créer un code‑barres PDF417 avec Aspose.BarCode en C#. Ce tutoriel explique
  comment générer rapidement un code‑barres PDF417 avec des exemples de code clairs.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417 barcode
- create barcode with aspose
language: fr
lastmod: 2026-08-25
og_description: Créer un code‑barres PDF417 avec Aspose.BarCode en C#. Apprenez à
  générer un code‑barres PDF417 grâce à un exemple complet et exécutable.
og_image_alt: Screenshot of a generated PDF417 barcode created with Aspose.BarCode
og_title: Créer un code‑barres PDF417 avec Aspose.BarCode – guide rapide
schemas:
- author: Aspose
  dateModified: '2026-08-25'
  description: Create PDF417 barcode using Aspose.BarCode in C#. This tutorial explains
    how to generate PDF417 barcode quickly with clear code examples.
  headline: Create PDF417 barcode with Aspose.BarCode – step-by-step guide
  type: TechArticle
tags:
- Aspose.BarCode
- PDF417
- C#
title: Créer un code-barres PDF417 avec Aspose.BarCode – guide étape par étape
url: /fr/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-barcode-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code-barres PDF417 avec Aspose.BarCode – guide étape par étape

Si vous devez **créer un code-barres PDF417** dans une application .NET, ce guide vous montre comment générer un code-barres PDF417 avec Aspose.BarCode. Vous verrez un exemple complet, prêt à l'exécution, comprendrez pourquoi chaque paramètre est important et apprendrez comment adapter le code à différents scénarios.

Le tutoriel couvre :

* Ajouter le package Aspose.BarCode à votre projet  
* Configurer le générateur de code-barres (texte, X‑dimension, colonnes)  
* Enregistrer le code-barres en tant que fichier PNG  
* Gérer les caractères Unicode et les pièges courants  

Aucune documentation externe n'est requise — tout ce dont vous avez besoin est inclus ci-dessous.

## Prérequis

Avant de commencer, assurez-vous d'avoir :

* SDK .NET 6.0 ou ultérieur (le code fonctionne également avec .NET Framework 4.7+)
* Une version récente du package NuGet **Aspose.BarCode for .NET**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Un IDE ou éditeur de votre choix (Visual Studio, VS Code, Rider, etc.)

## Étape 1 : Configurer le projet et importer les espaces de noms

Créez un nouveau projet console et importez les espaces de noms Aspose.BarCode requis.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // The full barcode generation logic starts here.
```

*`Aspose.BarCode`* contient les classes de base, tandis que *`Aspose.BarCode.Generation`* fournit le `BarcodeGenerator` utilisé pour créer des codes-barres.

## Étape 2 : Créer le générateur de code-barres PDF417 avec le texte souhaité

La première ligne crée un `BarcodeGenerator` pour la symbologie PDF417 et assigne les données que vous souhaitez encoder.

```csharp
            // Step 2: Create a PDF417 barcode generator with the desired text
            // Unicode characters such as Å, ó, and © are supported out of the box.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

**Pourquoi c'est important :**  
PDF417 peut stocker jusqu'à 1 850 caractères, ce qui le rend adapté aux documents, billets ou pièces d'identité. Passer le texte directement au constructeur garantit que les données sont correctement encodées avant l'application de tout paramètre visuel.

## Étape 3 : Configurer les paramètres visuels (X‑dimension et colonnes)

Un réglage fin de l'apparence améliore la fiabilité du scan et correspond aux exigences de mise en page.

```csharp
            // Step 3: Set the X‑dimension (module width) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 4: Define the number of columns for the PDF417 barcode
            // Fewer columns produce a taller barcode; more columns make it wider.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
```

* **X‑dimension** – Contrôle la largeur d'un seul module du code-barres. Une valeur de `2` pixels est un bon compromis entre lisibilité et taille du fichier pour la plupart des écrans.  
* **Columns** – Détermine le nombre de colonnes de données du code-barres. Ajustez cette valeur en fonction de la quantité de données et de l'espace disponible sur le support cible.

## Étape 4 : Enregistrer l'image du code-barres

Choisissez un format d'image qui correspond à votre flux de travail en aval. PNG conserve une qualité sans perte, ce qui est idéal pour un traitement ou une impression ultérieure.

```csharp
            // Step 5: Save the generated barcode as a PNG image
            string outputPath = "Pdf417Basic.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

La méthode `Save` écrit l'image au chemin spécifié. Si vous avez besoin d'un format différent (JPEG, BMP, SVG), remplacez `BarCodeImageFormat.Png` par la valeur d'énumération appropriée.

## Exemple complet et exécutable

Copiez le bloc de code complet ci‑dessous dans `Program.cs` d'un nouveau projet console, exécutez `dotnet run`, et vous trouverez `Pdf417Basic.png` dans le dossier du projet.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create a PDF417 barcode generator with Unicode text
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // Adjust visual parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Save as PNG
            string outputPath = "Pdf417Basic.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

### Résultat attendu

L'exécution du programme produit un fichier PNG similaire à l'illustration ci‑dessous.

![Create PDF417 barcode example](https://example.com/images/pdf417-sample.png "Create PDF417 barcode example")

*L'image montre un code-barres PDF417 clair avec trois colonnes et une largeur de module de 2 px.*

## Comment générer un code-barres PDF417 avec des longueurs de données personnalisées

Si vos données dépassent la capacité par défaut, vous devrez peut‑être ajuster des paramètres supplémentaires :

| Paramètre | Paramètre recommandé | Raison |
|-----------|----------------------|--------|
| `Pdf417.Rows` | `0` (auto) | Laisser Aspose calculer le nombre optimal de lignes. |
| `Pdf417.ErrorLevel` | `2` (par défaut) | Des niveaux plus élevés augmentent la redondance, améliorant la fiabilité du scan sur des supports endommagés. |
| `Pdf417.SecurityLevel` | `0`–`8` | À n'utiliser que si vous avez besoin d'une correction d'erreurs au‑delà du défaut. |

```csharp
generator.Parameters.Barcode.Pdf417.Rows = 0;          // Auto‑calculate rows
generator.Parameters.Barcode.Pdf417.ErrorLevel = 2;   // Standard error correction
generator.Parameters.Barcode.Pdf417.SecurityLevel = 5; // Optional extra security
```

**Astuce :** Testez toujours le code-barres généré avec le matériel de scanner prévu. Des niveaux d'erreur plus élevés peuvent augmenter la taille de l'image, ce qui peut affecter les contraintes de mise en page.

## Pièges courants et comment les éviter

| Problème | Cause | Solution |
|----------|-------|----------|
| Le code-barres apparaît flou | Enregistrement en PNG basse résolution | Augmenter `XDimension.Pixels` ou exporter en SVG (`BarCodeImageFormat.Svg`) |
| Les caractères sont remplacés par � | Chaîne d'entrée non encodée en UTF‑8 | Assurez‑vous que le fichier source est enregistré avec l'encodage UTF‑8 (la plupart des IDE le font par défaut) |
| Le scanner ne peut pas lire le code-barres | Trop peu de colonnes pour la quantité de données | Augmenter `Pdf417.Columns` ou laisser Aspose déterminer automatiquement les colonnes en omettant ce paramètre |

## Créer un code-barres avec Aspose – au‑delà de PDF417

Aspose.BarCode prend en charge de nombreuses symbologies (QR, Code128, DataMatrix, etc.). Passer à un type différent ne nécessite que de modifier l'énumération `EncodeTypes` :

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
qrGenerator.Save("QRCode.png", BarCodeImageFormat.Png);
```

Cela démontre le modèle **create barcode with Aspose** : instancier `BarcodeGenerator` avec la valeur `EncodeTypes` souhaitée, configurer les paramètres, puis appeler `Save`.

## Conclusion

Vous savez maintenant comment **créer un code-barres PDF417** en C# avec Aspose.BarCode, depuis la configuration du projet jusqu'au réglage fin des paramètres visuels et à la gestion des données Unicode. L'exemple complet et exécutable peut être adapté à des ensembles de données plus volumineux, à différents formats d'image ou à d'autres symbologies.

Les prochaines étapes que vous pourriez explorer :

* **Comment générer un code-barres PDF417** dans une API web (ASP.NET Core) – utile pour la génération à la demande.  
* Intégrer le code-barres dans un document PDF avec Aspose.PDF.  
* Utiliser `Pdf417.Rows` et `Pdf417.ErrorLevel` pour répondre à des normes de numérisation spécifiques.

N'hésitez pas à expérimenter avec le nombre de colonnes, les valeurs de X‑dimension et les formats de sortie pour répondre à votre cas d'utilisation exact. Bon codage !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets et fonctionnels avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités d'API supplémentaires et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment créer un code-barres – PDF417 compact avec Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Comment générer un code-barres PDF417 – Encodage PDF417 compact](/barcode/english/net/compact-pdf417-encoding/)
- [Comment lire un code-barres depuis un PDF en Java avec Aspose.BarCode](/barcode/english/java/document-barcode-recognition/recognizing-barcodes-from-pdf/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
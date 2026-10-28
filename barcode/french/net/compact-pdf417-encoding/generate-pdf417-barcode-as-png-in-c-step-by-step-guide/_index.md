---
category: general
date: 2026-10-28
description: Générez un code‑barres PDF417 en C# et exportez‑le en image PNG. Apprenez
  à configurer la mise en page, à définir les colonnes et les lignes, et à enregistrer
  le fichier.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- barcode generator PNG
- how to set PDF417
- how to generate PNG barcode
- how to configure PDF417 barcode
language: fr
lastmod: 2026-10-28
og_description: Générez un code‑barres PDF417 en C# et enregistrez‑le au format PNG.
  Suivez ce guide complet pour configurer la mise en page, définir les colonnes et
  les lignes, et produire un fichier de code‑barres de haute qualité.
og_image_alt: Screenshot of a generated PDF417 barcode saved as a PNG file
og_title: Générer un code‑barres PDF417 au format PNG – Tutoriel C#
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Generate PDF417 barcode in C# and export it as a PNG image. Learn how
    to configure layout, set columns and rows, and save the file.
  headline: Generate PDF417 barcode as PNG in C# – step‑by‑step guide
  type: TechArticle
tags:
- C#
- PDF417
- barcode
- image generation
title: Générer un code‑barres PDF417 au format PNG en C# – guide étape par étape
url: /fr/net/compact-pdf417-encoding/generate-pdf417-barcode-as-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Générer un code‑barres PDF417 en PNG avec C# – guide étape par étape

Si vous devez **générer un code‑barres PDF417** dans une application .NET, ce guide vous montre exactement comment créer le code‑barres et l’enregistrer en tant qu’image PNG. Vous apprendrez à configurer la mise en page du code‑barres, à définir le nombre de colonnes et de lignes, et à produire un fichier pouvant être utilisé dans les scénarios d’inventaire, de billetterie ou de numérisation mobile.

Le tutoriel couvre tout, de l’installation de la bibliothèque requise à la gestion des cas limites tels que les valeurs de mise en page invalides. Aucune documentation externe n’est nécessaire — il suffit de copier le code, de l’exécuter, et vous disposerez d’une image de code‑barres prête à l’emploi.

## Prérequis

Avant de commencer, assurez-vous d’avoir :

* .NET 6.0 SDK ou version ultérieure installé  
* Un environnement de développement C# (Visual Studio, VS Code ou Rider)  
* Un accès Internet pour télécharger le package NuGet **Aspose.BarCode for .NET** (la bibliothèque utilisée dans les exemples)  

Ces exigences garantissent que le code se compile et s’exécute sans configuration supplémentaire.

## Étape 1 : Installer la bibliothèque de code‑barres

La façon la plus simple d’obtenir la capacité de **générateur de code‑barres PNG** est d’utiliser le package officiel Aspose.BarCode. Ouvrez un terminal dans le dossier de votre projet et exécutez :

```bash
dotnet add package Aspose.BarCode
```

La commande ajoute la bibliothèque et ses dépendances à votre fichier de projet. Une fois l’installation réussie, vous pouvez référencer les classes dans vos fichiers source C#.

## Étape 2 : Créer un générateur de code‑barres PDF417

Créer l’objet code‑barres est la base du processus. L’extrait suivant construit un générateur qui encode le texte `"Sample"` en utilisant la symbologie PDF417.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for PDF417
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");
```

*Pourquoi cette étape est importante* – La classe `BarcodeGenerator` encapsule tous les paramètres nécessaires au rendu. En spécifiant `EncodeTypes.Pdf417`, vous indiquez à la bibliothèque de produire un **code‑barres PDF417**, qui est un code linéaire empilé idéal pour stocker de grandes quantités de données.

## Étape 3 : Comment définir les colonnes et les lignes du PDF417

Un code‑barres PDF417 peut être personnalisé en ajustant sa matrice. Les deux paramètres les plus courants sont les **colonnes** (modules horizontaux) et les **lignes** (modules verticaux). Le contrôle de ces valeurs influence la taille et la lisibilité du code‑barres.

```csharp
        // Step 3: Configure a custom layout – set columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4; // allowed range: 2‑30
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // allowed range: 1‑90
```

### Comment configurer le code‑barres PDF417 pour des dimensions spécifiques

- Utilisez des valeurs dans les plages documentées ; des nombres hors plage déclenchent une exception.  
- Un nombre de colonnes plus élevé compresse le code‑barres horizontalement, tandis que davantage de lignes augmentent la hauteur verticale.  
- Ajustez la mise en page pour correspondre à la surface d’impression cible ou à la distance de numérisation.  

Si vous avez besoin d’une forme différente, modifiez les nombres en conséquence. La bibliothèque recalcule automatiquement la taille du module pour que le code‑barres reste lisible.

## Étape 4 : Comment générer un code‑barres PNG

Enregistrer le code‑barres en tant que fichier PNG est une opération en une seule ligne une fois le générateur entièrement configuré. PNG offre une compression sans perte, ce qui le rend idéal pour des images de code‑barres nettes.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        generator.Save("CustomLayout.png", BarCodeImageFormat.Png);
    }
}
```

*Pourquoi PNG* – L’énumération `BarCodeImageFormat.Png` indique à la bibliothèque de rendre le code‑barres au format PNG. Ce format préserve les bords nets, ce qui est essentiel pour les lecteurs de code‑barres qui dépendent de bords à fort contraste.

### Résultat attendu

L’exécution du programme crée un fichier nommé **CustomLayout.png** dans le répertoire de travail de l’application. L’ouverture du fichier montre un code‑barres PDF417 rectangulaire avec quatre colonnes et neuf lignes, encodant la chaîne `"Sample"`.

![Générer un code‑barres PDF417 en PNG](https://example.com/images/pdf417-custom.png "Générer un code‑barres PDF417 en PNG")

*Texte alternatif de l'image* : **Générer un code‑barres PDF417 en PNG** – une image de code‑barres produite par le code du tutoriel.

## Étape 5 : Vérifier le code‑barres et dépanner les problèmes courants

Après avoir généré l’image, vous devez vérifier qu’un lecteur ou un outil de validation peut le lire. Voici quelques vérifications rapides :

| Problème | Cause | Solution |
|----------|-------|----------|
| Le code‑barres est flou | L’image a été redimensionnée après la génération | Conservez la taille PNG originale ; évitez le redimensionnement dans les contrôles UI |
| Le lecteur signale « données invalides » | Colonnes/lignes hors plage ou données trop longues pour la mise en page choisie | Réduisez la quantité de texte encodé ou augmentez le nombre de lignes/colonnes |
| Le fichier PNG est vide | `generator.Save` pointe vers un répertoire inexistant | Assurez‑vous que le répertoire existe ou utilisez un chemin absolu |

**Astuce :** Lorsque vous avez besoin d’un arrière‑plan transparent (par ex., superposer le code‑barres sur un élément UI), définissez `generator.Parameters.Image.TransparentBackground = true;` avant d’appeler `Save`.

## Exemple complet fonctionnel

Voici le programme complet que vous pouvez copier, coller et exécuter sans modification (à l’exception du chemin de sortie si vous le souhaitez).

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the generator for PDF417 with sample data
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");

        // Configure custom layout – set columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4; // 2‑30
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // 1‑90

        // Optional: make background transparent
        generator.Parameters.Image.TransparentBackground = true;

        // Save the barcode as a PNG file
        string outputPath = "CustomLayout.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode saved to {outputPath}");
    }
}
```

L’exécution du programme affiche un message de confirmation et produit `CustomLayout.png` dans le même dossier que l’exécutable.

## Conclusion

Vous savez maintenant comment **générer un code‑barres PDF417** en C#, configurer sa mise en page avec des colonnes et des lignes spécifiques, et exporter le résultat sous forme d’image **code‑barres PNG**. Les étapes ont couvert l’installation de la bibliothèque Aspose.BarCode, l’initialisation du générateur, l’application de dimensions personnalisées, l’enregistrement du fichier et la vérification du résultat.

À partir de là, vous pouvez explorer des paramètres supplémentaires tels que le niveau de correction d’erreurs, les marges du code‑barres, ou l’intégration de l’image directement dans un rapport PDF. Chacun de ces sujets s’appuie sur le modèle de base présenté dans ce guide, vous permettant d’adapter la solution à tout scénario de génération de code‑barres .NET.

---

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités API supplémentaires et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment générer un code‑barres PDF417 – Guide de programmation complet](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)
- [Comment générer un code‑barres PDF417 en C# et définir la taille du code‑barres](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/)
- [Comment générer un code‑barres PDF417 avec Aspose – Guide complet](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
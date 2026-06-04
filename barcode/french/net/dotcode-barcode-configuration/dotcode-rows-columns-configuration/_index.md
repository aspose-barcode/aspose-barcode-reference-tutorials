---
date: 2026-02-04
description: Apprenez à créer une image de code‑barres DotCode en configurant les
  lignes et les colonnes à l’aide d’Aspose.BarCode pour .NET.
linktitle: DotCode Rows and Columns Configuration
second_title: Aspose.BarCode .NET API
title: Créer une image de code‑barres DotCode – lignes et colonnes (Aspose.BarCode)
url: /fr/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer une image de code-barres DotCode – lignes & colonnes (Aspose.BarCode)

## Introduction

Bienvenue dans le monde de la génération de codes-barres avec Aspose.BarCode pour .NET ! Dans ce guide, vous allez **créer des images de code-barres DotCode** et apprendre à ajuster finement les lignes et les colonnes pour répondre à vos exigences exactes. Que vous construisiez un système d’étiquetage pour le secteur de la santé, une application de suivi logistique, ou que vous expérimentiez simplement les symbologies 2D, maîtriser cette configuration vous donne un contrôle précis sur la taille du code-barres et sa capacité de données.

## Quick Answers
- **Que signifie « créer une image de code-barres DotCode » ?** Cela signifie générer un fichier visuel PNG/JPEG/etc. qui encode vos données en utilisant la symbologie DotCode 2‑D.  
- **Quelle bibliothèque gère la génération ?** Aspose.BarCode for .NET fournit une API simple pour produire des images DotCode de haute qualité.  
- **Ai‑je besoin d’une licence ?** Un essai gratuit fonctionne pour le développement ; une licence commerciale est requise pour une utilisation en production.  
- **Puis‑je personnaliser les lignes et les colonnes indépendamment ?** Oui – vous pouvez définir les lignes, les colonnes, ou laisser la bibliothèque les dimensionner automatiquement.  
- **Quels formats de sortie sont pris en charge ?** PNG, JPEG, BMP, GIF, TIFF, et plus via `BarCodeImageFormat`.

## What is a DotCode barcode image?

DotCode est un code-barres 2‑dimensionnel compact qui stocke de grandes quantités de données dans une petite zone carrée ou rectangulaire. Il est largement utilisé dans les secteurs **santé** et **pharmaceutique** pour le suivi des produits, l’encodage des informations patients, et plus encore. En configurant les lignes et les colonnes, vous contrôlez la densité du code-barres et ses dimensions physiques.

## Why configure rows and columns?

Personnaliser les lignes et les colonnes vous permet de :

* Adapter le code-barres à un espace d’étiquette limité.  
* Optimiser la fiabilité de la lecture pour des imprimantes ou des scanners spécifiques.  
* Équilibrer la taille de l’image avec la capacité de données — plus de lignes/colonnes signifient plus de données mais une image plus grande.  

Maintenant que vous comprenez le pourquoi, parcourons le **processus de création d’une image de code-barres DotCode** avec vos propres paramètres de lignes et colonnes.

## Prerequisites

Avant de plonger dans le code, assurez‑vous d’avoir :

1. **Environnement de développement .NET** – Visual Studio, Rider, ou VS Code avec le SDK .NET installé.  
2. **Aspose.BarCode for .NET** – Téléchargez‑le depuis le site officiel **[here](https://releases.aspose.com/barcode/net/)**.  
3. **Une licence valide** (ou une licence d’essai temporaire) pour la génération en production.  
4. **Des connaissances de base en C#** – vous écrirez quelques courts extraits, mais les concepts sont simples.

## Import Namespaces

Nous n’avons besoin que d’un seul espace de noms pour les exemples :

```csharp
using Aspose.BarCode.Generation;
```

## Step‑by‑step guide to create DotCode barcode image

### Step 1: Set up your Directory Path

Tout d’abord, décidez où les images générées seront enregistrées. Remplacez le texte de substitution par un dossier réel sur votre machine.

```csharp
string path = "Your Directory Path";
```

> **Astuce :** Utilisez `Path.Combine(Environment.CurrentDirectory, "Barcodes")` pour construire un chemin qui fonctionne sur toutes les plateformes.

### Step 2: Initialize the DotCode Generator

Créez une instance de `BarcodeGenerator`, spécifiez la symbologie `EncodeTypes.DotCode`, et fournissez les données que vous souhaitez encoder (par ex., « Aspose »).

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, "Aspose"))
{
    // All configuration and saving will happen inside this block.
}
```

### Step 3: Configure DotCode Columns

Si vous souhaitez un nombre fixe de colonnes, définissez la propriété `Columns`. Ici nous choisissons **18 colonnes** et enregistrons le résultat sous forme de fichier PNG.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 10;
gen.Parameters.Barcode.DotCode.Columns = 18;
gen.Save($"{path}DotCodeColumns18.png", BarCodeImageFormat.Png);
```

> **Pourquoi XDimension ?** Ajuster la taille en pixels modifie la densité visuelle de chaque point sans affecter les données encodées.

### Step 4: Configure DotCode Rows

Vous pouvez également fixer le nombre de lignes tout en laissant la bibliothèque déterminer le nombre de colonnes (en définissant `Columns = -1`). L’exemple ci‑dessous crée un code‑barres avec **12 lignes**.

```csharp
gen.Parameters.Barcode.DotCode.Columns = -1;
gen.Parameters.Barcode.DotCode.Rows = 12;
gen.Save($"{path}DotCodeRows12.png", BarCodeImageFormat.Png);
```

### Step 5: Configure Rows and Columns Simultaneously

Lorsque vous avez besoin d’un contrôle complet, définissez les deux propriétés. L’extrait suivant produit un code‑barres avec **29 colonnes** et **26 lignes**.

```csharp
gen.Parameters.Barcode.DotCode.Columns = 29;
gen.Parameters.Barcode.DotCode.Rows = 26;
gen.Save($"{path}DotCodeRows26Columns29.png", BarCodeImageFormat.Png);
```

> **Erreur fréquente :** Définir à la fois les lignes et les colonnes à des valeurs trop élevées peut produire une image qui dépasse les dimensions typiques d’une étiquette. Testez avec un aperçu avant l’impression.

## Common Issues and Solutions

| Problème | Cause | Solution |
|----------|-------|----------|
| Le code‑barres apparaît flou | XDimension trop faible | Augmentez `XDimension.Pixels` (par ex., 12‑15). |
| Le scanner ne peut pas lire le code‑barres | Lignes/Colonnes trop denses pour l’imprimante | Réduisez les lignes/colonnes ou utilisez une imprimante à plus haute résolution. |
| Image non enregistrée | Chaîne `path` invalide | Assurez‑vous que le répertoire existe ou appelez `Directory.CreateDirectory(path)`. |

## Frequently Asked Questions

**Q : Quelle est la quantité maximale de données que je peux stocker dans un code‑barres DotCode ?**  
R : Cela dépend du nombre de lignes et de colonnes que vous configurez. Plus de cellules signifient plus de données, mais aussi une image plus grande.

**Q : Puis‑je modifier les couleurs du code‑barres ?**  
R : Oui. Utilisez `gen.Parameters.Barcode.ForeColor` et `BackColor` pour définir des couleurs personnalisées avant l’enregistrement.

**Q : La symbologie DotCode est‑elle prise en charge sur toutes les plateformes ?**  
R : Aspose.BarCode for .NET fonctionne sur .NET Framework, .NET Core et .NET 5/6+, vous pouvez donc générer des images sous Windows, Linux ou macOS.

**Q : Où puis‑je trouver une liste complète de tous les paramètres DotCode ?**  
R : La référence officielle de l’API fournit une documentation détaillée – voir la [documentation Aspose.BarCode](https://reference.aspose.com/barcode/net/).

**Q : Comment générer un code‑barres dans une API web sans écrire sur le disque ?**  
R : Appelez `gen.Save(Stream, BarCodeImageFormat.Png)` et renvoyez le flux comme résultat de fichier.

## Conclusion

Vous savez maintenant comment **créer des images de code‑barres DotCode** et contrôler précisément leurs lignes et colonnes à l’aide d’Aspose.BarCode pour .NET. En ajustant les propriétés `Rows` et `Columns`, vous pouvez adapter la taille du code‑barres à n’importe quel scénario d’étiquetage ou d’emballage. Expérimentez avec différentes dimensions, couleurs et formats de sortie pour répondre aux besoins de votre projet, et explorez l’ensemble plus large des fonctionnalités d’Aspose.BarCode pour encore plus de personnalisation.

Si vous rencontrez des difficultés ou souhaitez approfondir, consultez les ressources officielles :

* [Documentation Aspose.BarCode](https://reference.aspose.com/barcode/net/)  
* [Support communautaire Aspose.BarCode](https://forum.aspose.com/c/barcode/13)

---

**Dernière mise à jour** : 2026-02-04  
**Testé avec** : Aspose.BarCode for .NET 24.11 (dernière version au moment de la rédaction)  
**Auteur** : Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
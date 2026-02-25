---
date: 2026-02-25
description: Apprenez à générer une image de code‑barres et à enregistrer le PNG du
  code‑barres à l’aide d’Aspose.BarCode pour .NET – un exemple complet d’Aspose Barcode.
linktitle: One-Dimensional Code 93 Configuration
second_title: Aspose.BarCode .NET API
title: Générer une image de code‑barres – Code 93 avec Aspose.BarCode
url: /fr/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/
weight: 12
---

 craft final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Générer une image de code‑barres – Code 93 unidimensionnel avec Aspose.BarCode

## Introduction

À l’ère numérique actuelle, les codes‑barres sont devenus une partie intégrante de notre quotidien, simplifiant des processus tels que la gestion des stocks, l’étiquetage des produits et le suivi en point de vente. **Générer une image de code‑barres** est souvent la première étape pour intégrer ces identifiants dans vos applications. Aspose.BarCode pour .NET fournit une API robuste et facile à utiliser qui vous permet de créer des codes‑barres Code 93 de haute qualité en quelques lignes de code C#. Que vous construisiez un système d’entrepôt, une application de vente au détail ou un outil de génération de rapports personnalisé, ce tutoriel vous guide à travers un **exemple de code‑barres Aspose** complet montrant comment générer, personnaliser et **enregistrer des fichiers PNG de code‑barres**.

## Réponses rapides
- **Que couvre le tutoriel ?** Création et enregistrement d’une image de code‑barres Code 93 avec gestion du checksum.  
- **Quelle bibliothèque est utilisée ?** Aspose.BarCode pour .NET (dernière version stable).  
- **Ai‑je besoin d’une licence ?** Une version d’essai gratuite suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Puis‑je changer le format de sortie ?** Oui – vous pouvez enregistrer en PNG, JPEG, BMP, etc., en modifiant le `BarCodeImageFormat`.  
- **Quelles sont les exigences minimales ?** .NET Framework 4.6+ ou .NET Core 3.1+ et Visual Studio.

## Qu’est‑ce qu’un code‑barres Code 93 ?
Le Code 93 est une symbologie alphanumérique à haute densité qui prend en charge l’ensemble complet du jeu de caractères ASCII. Il est souvent choisi pour sa taille compacte et son checksum intégré, qui aide à garantir l’intégrité des données lors du scan.

## Pourquoi générer des images de code‑barres avec Aspose.BarCode ?
- **Contrôle total** sur le type d’encodage, le checksum, la taille et le format d’image.  
- **Aucune dépendance externe** – la bibliothèque fonctionne sur n’importe quelle plateforme .NET.  
- **Qualité de rendu exceptionnelle**, adaptée à l’affichage à l’écran comme à l’impression haute résolution.  
- **Documentation complète** et un grand nombre d’exemples qui accélèrent le développement.

## Prérequis

Avant de plonger dans le code, assurez‑vous de disposer de :

1. **Visual Studio** (toute version récente).  
2. **Aspose.BarCode pour .NET** installé – vous pouvez le télécharger depuis la page officielle.  
3. Une connaissance de base du **C#** et de la structure d’un projet .NET.

Une fois prêt, passons au guide étape par étape.

## Importer les espaces de noms

Tout d’abord, importez les espaces de noms requis afin de pouvoir accéder aux classes de génération de code‑barres.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## Étape 1 : Définir le chemin du répertoire

Spécifiez l’endroit où l’image de code‑barres générée sera enregistrée. Remplacez le texte de substitution par un dossier valide sur votre machine.

```csharp
string path = "Your Directory Path";
```

## Étape 2 : Créer un code‑barres Code 93 unidimensionnel

Instanciez un `BarcodeGenerator` avec le type `Code93Extended` et les données que vous souhaitez encoder.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code93Extended, "CODE");
```

## Étape 3 : Activer le checksum (optionnel)

Le Code 93 inclut un checksum par défaut. Vous pouvez le désactiver ou l’activer via la propriété `IsChecksumEnabled`.

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
```

## Étape 4 : Enregistrer l’image du code‑barres (Enregistrer le PNG du code‑barres)

Générez l’image et enregistrez‑la au format PNG dans le dossier que vous avez indiqué précédemment.

```csharp
gen.Save($"{path}OneCSCode93WithChecksum.png", BarCodeImageFormat.Png);
```

## Étape 5 : Gestion des exceptions – Générer sans checksum

Si vous devez créer un code‑barres **sans** checksum, vous devez gérer les éventuelles exceptions qui peuvent survenir.

```csharp
try
{
    gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.No;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

### Problèmes courants et solutions
- **Chemin invalide** – assurez‑vous que le répertoire existe et que l’application possède les droits d’écriture.  
- **Caractères non pris en charge** – le Code 93 accepte l’ensemble complet ASCII, mais les caractères de contrôle peuvent provoquer des erreurs.  
- **Licence non définie** – sans licence valide, la bibliothèque fonctionne en mode d’évaluation et peut ajouter un filigrane.

## Questions fréquentes (FAQ)

### Q : Où puis‑je trouver la documentation d’Aspose.BarCode pour .NET ?
R : Vous pouvez consulter la documentation à l’adresse [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/).

### Q : Comment télécharger Aspose.BarCode pour .NET ?
R : Vous pouvez télécharger Aspose.BarCode pour .NET depuis le site web à l’adresse [Aspose.BarCode for .NET Download](https://releases.aspose.com/barcode/net/).

### Q : Existe‑t‑il une version d’essai gratuite d’Aspose.BarCode pour .NET ?
R : Oui, vous pouvez obtenir une version d’essai gratuite d’Aspose.BarCode pour .NET [ici](https://releases.aspose.com/).

### Q : Comment acheter une licence pour Aspose.BarCode pour .NET ?
R : Vous pouvez acheter une licence sur la page d’achat à l’adresse [Aspose.BarCode for .NET Purchase](https://purchase.aspose.com/buy).

### Q : Où puis‑je obtenir du support ou poser des questions sur Aspose.BarCode pour .NET ?
R : Vous trouverez un forum communautaire pour le support et les discussions à l’adresse [Aspose.BarCode for .NET Support](https://forum.aspose.com/c/barcode/13).

---

**Dernière mise à jour :** 2026-02-25  
**Testé avec :** Aspose.BarCode 24.11 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-06-09
description: Apprenez à créer un code-barres DataMatrix en mode ASCII en utilisant
  Aspose.BarCode pour .NET. Ce guide montre comment générer rapidement un code-barres
  en C#.
keywords:
- create datamatrix barcode
- generate barcode c#
- how to encode barcode
- barcode generator example
linktitle: Mode d'encodage DataMatrix (ASCII)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  headline: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  name: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  steps:
  - name: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
    text: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
  - name: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
  - name: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
    text: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
  - name: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
    text: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
  type: HowTo
- questions:
  - answer: Yes, a valid Aspose license is required for production use; a free trial
      is available for evaluation.
    question: Can I use this in a commercial application?
  - answer: Absolutely – Aspose.BarCode fully supports .NET Core 3.1+, .NET 5, .NET
      6, and later versions.
    question: Does the library work with .NET Core?
  - answer: Up to 2,335 alphanumeric characters fit in a single DataMatrix symbol
      when using ASCII encoding.
    question: How many characters can I encode in ASCII mode?
  - answer: Yes, adjust `generator.Parameters.Image.ForeColor` and `BackColor` to
      any `System.Drawing.Color` value.
    question: Can I change the barcode’s foreground or background color?
  - answer: The official documentation contains dozens of samples covering custom
      sizes, colors, and error‑correction levels.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Créer un code-barres DataMatrix en mode ASCII avec Aspose.BarCode pour .NET
url: /fr/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code‑barres DataMatrix en mode ASCII avec Aspose.BarCode pour .NET

## Introduction

Prêt à **créer des images de code‑barres DataMatrix** utilisant le codage ASCII efficace ? Dans ce tutoriel, vous apprendrez à générer un code‑barres DataMatrix en mode ASCII avec Aspose.BarCode pour .NET. Nous parcourrons chaque étape — de la configuration du projet à l’enregistrement de l’image finale — afin que vous puissiez ajouter la génération de codes‑barres à vos applications C# en quelques minutes.

## Réponses rapides
- **Quelle bibliothèque est la meilleure pour DataMatrix en .NET ?** Aspose.BarCode for .NET  
- **Combien de lignes de code sont nécessaires ?** Environ 5‑7 lignes pour un code‑barres ASCII de base  
- **Ai-je besoin d’une licence ?** Un essai gratuit suffit pour le développement ; une licence est requise pour la production  
- **Plateformes prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **Puis-je changer la taille ou les couleurs ?** Oui, Aspose.BarCode expose des propriétés pour les dimensions et les couleurs de premier plan/arrière‑plan  

## Qu’est‑ce qu’un code‑barres DataMatrix ?
DataMatrix est un code‑barres bidimensionnel qui stocke du texte et des données binaires dans un motif carré compact.  
Un code‑barres DataMatrix encode les informations dans une grille de modules noirs et blancs, permettant jusqu’à 2 335 caractères alphanumériques dans un seul symbole. Il est largement utilisé dans la fabrication, la logistique et la santé car il peut être imprimé à des tailles très petites tout en restant hautement lisible.

## Comment créer un code‑barres DataMatrix en mode ASCII ?
Chargez l’espace de noms Aspose.BarCode, créez une instance de `BarcodeGenerator`, définissez le `EncodeMode` sur **EncodeMode.ASCII**, assignez votre chaîne de données, puis appelez `Save` pour écrire le fichier image. Cette approche produit un code‑barres DataMatrix parfaitement conforme avec un encodage uniquement ASCII en quelques lignes de code C#.

## Pourquoi utiliser le codage ASCII pour DataMatrix ?
Le mode ASCII est le codage par défaut et le plus efficace pour les données texte simples, offrant la plus petite taille de symbole possible pour les chaînes alphanumériques. Il prend en charge les 128 caractères ASCII, traite les données plus rapidement que les modes étendus et garantit une compatibilité maximale avec les lecteurs hérités qui attendent des symboles ASCII standard.

## Prérequis

1. **Environnement de développement** – Visual Studio, Rider ou tout IDE compatible C#.  
2. **Aspose.BarCode for .NET** – Téléchargez le dernier package depuis [ici](https://releases.aspose.com/barcode/net/).  
   - Documentation : [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)  
   - Aide communautaire : [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)  
3. **Connaissances de base en C#** – Une familiarité avec la structure des projets .NET vous aidera à suivre rapidement les étapes.  
4. **D’autres produits Aspose** sont disponibles [ici](https://releases.aspose.com/).

## Importer les espaces de noms

Pour commencer, ajoutez les directives `using` requises en haut de votre fichier C# :

```csharp
using Aspose.BarCode.Generation;
using System.Drawing;
```

Ces espaces de noms vous donnent accès à la classe `BarcodeGenerator` et aux types liés aux images nécessaires pour enregistrer la sortie.

## Étape 1 : Créer un répertoire

Choisissez un dossier où les images de code‑barres générées seront stockées. Remplacez `"Your Directory Path"` par un chemin absolu ou relatif qui existe sur votre machine.

```csharp
string outputDir = @"C:\Barcodes";
if (!System.IO.Directory.Exists(outputDir))
{
    System.IO.Directory.CreateDirectory(outputDir);
}
```

Le code garantit que le répertoire existe avant d’essayer d’écrire des fichiers, évitant ainsi les erreurs d’exécution.

## Étape 2 : Encodage des données en mode ASCII

La classe `BarcodeGenerator` crée et configure les images de code‑barres. L’énumération `DataMatrixEncodeMode` sélectionne l’algorithme d’encodage pour les symboles DataMatrix.

```csharp
// Initialise the generator with the data you want to encode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "1234567890");

// Set the encoding mode to ASCII for optimal size
generator.Parameters.Barcode.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;

// Optional: adjust image dimensions or colors here
generator.Parameters.Image.Width = 200;
generator.Parameters.Image.Height = 200;

// Save the barcode as a PNG file
string filePath = System.IO.Path.Combine(outputDir, "datamatrix_ascii.png");
generator.Save(filePath, BarCodeImageFormat.Png);
```

Après l’exécution du code, vous trouverez `datamatrix_ascii.png` dans le dossier que vous avez spécifié. L’image contient un code‑barres DataMatrix qui encode la chaîne `"1234567890"` en utilisant le mode ASCII compact.

## Problèmes courants et solutions

- **Erreurs d’accès aux fichiers** – Assurez‑vous que l’application possède les droits d’écriture sur le dossier cible. Exécuter Visual Studio en tant qu’administrateur peut résoudre les problèmes de permission sous Windows.  
- **Taille du symbole incorrecte** – Si le code‑barres apparaît trop grand ou trop petit, ajustez `generator.Parameters.Image.Width` et `Height` ou laissez Aspose calculer automatiquement la taille optimale en omettant ces propriétés.  
- **Caractères non pris en charge** – Le mode ASCII n’accepte que les caractères de la plage 0‑127. Pour des données Unicode, passez à `DataMatrixEncodeMode.Base256` ou à un autre mode approprié.

## Questions fréquemment posées

**Q : Puis‑je utiliser cela dans une application commerciale ?**  
R : Oui, une licence Aspose valide est requise pour une utilisation en production ; un essai gratuit est disponible pour l’évaluation.

**Q : La bibliothèque fonctionne‑t‑elle avec .NET Core ?**  
R : Absolument – Aspose.BarCode prend entièrement en charge .NET Core 3.1+, .NET 5, .NET 6 et les versions ultérieures.

**Q : Combien de caractères puis‑je encoder en mode ASCII ?**  
R : Jusqu’à 2 335 caractères alphanumériques tiennent dans un seul symbole DataMatrix lorsqu’on utilise le codage ASCII.

**Q : Puis‑je changer la couleur de premier plan ou d’arrière‑plan du code‑barres ?**  
R : Oui, ajustez `generator.Parameters.Image.ForeColor` et `BackColor` à n’importe quelle valeur `System.Drawing.Color`.

**Q : Où puis‑je trouver des exemples plus avancés ?**  
R : La documentation officielle contient des dizaines d’exemples couvrant les tailles personnalisées, les couleurs et les niveaux de correction d’erreurs.

## FAQ

### Q1 : Puis‑je utiliser Aspose.BarCode pour .NET avec d’autres langages de programmation que C# ?
R1 : Aspose.BarCode prend en charge plusieurs langages de programmation, mais ce tutoriel se concentre sur C#.

### Q2 : Quels sont les différents modes d’encodage disponibles dans les codes‑barres DataMatrix ?
R2 : Les codes‑barres DataMatrix prennent en charge divers modes d’encodage, notamment ASCII, C40, Text et Base256. Chaque mode convient à différents types de données.

### Q3 : Puis‑je personnaliser l’apparence du code‑barres généré, comme sa taille et sa couleur ?
R3 : Oui, Aspose.BarCode offre un large éventail de paramètres pour personnaliser l’apparence du code‑barres, y compris la taille, la couleur, etc.

### Q4 : Existe‑t‑il une version d’essai gratuite d’Aspose.BarCode pour .NET ?
R4 : Oui, vous pouvez explorer Aspose.BarCode pour .NET avec un essai gratuit [ici](https://releases.aspose.com/).

### Q5 : Où puis‑je acheter une licence pour Aspose.BarCode pour .NET ?
R5 : Vous pouvez acheter une licence sur le site d’Aspose [ici](https://purchase.aspose.com/buy).

---

**Dernière mise à jour :** 2026-06-09  
**Testé avec :** Aspose.BarCode 24.11 pour .NET  
**Auteur :** Aspose

## Tutoriels associés

- [Encodage DataMatrix en octets avec Aspose.BarCode pour .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [Lire le code‑barres DataMatrix C# – Générer le mode DataMatrix (Auto)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Comment générer des codes‑barres DataMatrix (ECC 200) avec Aspose.BarCode pour .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.BarCode.Generation;
```

```csharp
string path = "Your Directory Path";
```

```csharp
System.Console.WriteLine("DataMatrixEncodeModeASCII:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    // Set the X-dimension (size) of the barcode in pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set the encoding mode to ASCII
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;
    
    // Save the barcode as a PNG image
    gen.Save($"{path}DataMatrixEncodeModeASCII.png", BarCodeImageFormat.Png);
}
```

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
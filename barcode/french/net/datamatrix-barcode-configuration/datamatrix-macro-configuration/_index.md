---
date: 2026-08-17
description: Apprenez à créer un code-barres DataMatrix avec des caractères macro
  en utilisant Aspose.BarCode pour .NET et découvrez comment utiliser DataMatrix dans
  vos applications.
keywords:
- create datamatrix barcode
- datamatrix barcode error correction
- aspose barcode macro
- .net barcode generation
lastmod: 2026-08-17
linktitle: Configuration Macro DataMatrix
og_description: Apprenez à créer un code-barres DataMatrix avec des caractères macro
  en utilisant Aspose.BarCode pour .NET. Ce guide fournit du code étape par étape,
  des options de personnalisation et des conseils de vérification pour une génération
  fiable de codes-barres.
og_image_alt: Guide showing creation of DataMatrix barcode with macro characters in
  .NET using Aspose.BarCode
og_title: Créer un code-barres DataMatrix avec des caractères macro en utilisant Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-17'
  description: Learn how to create DataMatrix barcode with macro characters using
    Aspose.BarCode for .NET and discover how to use DataMatrix in your applications.
  headline: How to create DataMatrix barcode with macro characters in .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode with macro characters using
    Aspose.BarCode for .NET and discover how to use DataMatrix in your applications.
  name: How to create DataMatrix barcode with macro characters in .NET
  steps:
  - name: setting up your project
    text: Create a new Console Application (or any .NET project) in Visual Studio.
      Add a reference to the Aspose.BarCode DLLs that you obtained from the download.
  - name: DataMatrix macro configuration
    text: The core of the tutorial – here we actually **create DataMatrix barcode**
      with a macro character. > **Pro tip:** Replace `"ASPOSE"` with any string you
      need to encode. The macro character (`Macro05`) tells scanners that this barcode
      is part of a macro sequence.
  - name: customize barcode parameters for error correction
    text: 'Before saving, you can tweak additional settings: - **XDimension** – controls
      the size of each module (pixel). - **Margin**, **ErrorCorrection**, and **EncodingMode**
      – all accessible via `gen.Parameters.Barcode.DataMatrix`.'
  - name: save the barcode
    text: The snippet above saves the image as `DataMatrixMacro.png` in the folder
      you specified. PNG is loss‑less, making it ideal for further processing.
  - name: recognize the barcode
    text: '`BarCodeReader` is Aspose.BarCode''s class for decoding barcodes from images.
      Using `BarCodeReader` we immediately read back the generated image to confirm
      that the macro character and data are correct. This round‑trip validation is
      especially handy during automated testing.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET is a powerful library that allows .NET developers
      to generate and recognize barcodes in various formats, including DataMatrix,
      QR, and more.
    question: What is Aspose.BarCode for .NET?
  - answer: DataMatrix barcodes are compact, highly reliable, and can store large
      amounts of data, making them ideal for manufacturing, logistics, and healthcare.
    question: Why should I use DataMatrix barcodes?
  - answer: You can find the documentation at [the Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).
    question: Where can I find the documentation for Aspose.BarCode for .NET?
  - answer: Yes, you can download a free trial from [the free trial link](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: If you have any questions or need support, you can visit the Aspose.BarCode
      for .NET forum at [the support forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- aspose.barcode
- c# barcode generation
- macro barcode
- barcode error correction
title: Comment créer un code-barres DataMatrix avec des caractères macro dans .NET
url: /fr/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code-barres DataMatrix avec des caractères macro dans .NET

## Introduction

Générer un **code-barres DataMatrix** qui inclut des caractères macro vous permet d'intégrer des informations de référence supplémentaires dans un petit symbole carré. Dans ce tutoriel, vous apprendrez comment **créer un code-barres DataMatrix** avec des caractères macro en utilisant Aspose.BarCode pour .NET, personnaliser la taille et le niveau de correction d'erreurs, et vérifier instantanément le résultat. À la fin, vous serez prêt à intégrer des codes-barres avec macro dans les étiquettes de produits, les documents ou les dispositifs médicaux.

## Réponses rapides
- **Quelle est la bibliothèque principale ?** Aspose.BarCode for .NET  
- **Puis-je créer un code-barres DataMatrix avec des caractères macro ?** Oui – définissez la propriété `MacroCharacters`.  
- **Ai-je besoin d'une licence pour la production ?** Une licence Aspose valide est requise pour une utilisation en production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Une version d'essai gratuite est-elle disponible ?** Absolument – téléchargez‑la depuis le site officiel d'Aspose.

## Prérequis

Avant de plonger dans la configuration macro, assurez‑vous de disposer de ce qui suit :

1. **Visual Studio** – toute édition récente fonctionnera.  
2. **Aspose.BarCode for .NET** – téléchargez‑le depuis [the download link](https://releases.aspose.com/barcode/net/).  
3. **Connaissances de base en .NET** – familiarité avec C# et l'écosystème .NET.

## Importer les espaces de noms

Nous commençons par importer les espaces de noms nécessaires à la génération et à la reconnaissance de codes-barres.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

## Qu’est‑ce que « générer un code-barres DataMatrix » avec des caractères macro ?

`MacroCharacters` permet aux codes-barres DataMatrix d'inclure des symboles macro qui font référence à des données supplémentaires. En utilisant des caractères macro tels que Macro05 ou Macro06, un seul code-barres peut pointer vers un ensemble de données plus grand ou une séquence de codes-barres liés, ce qui est précieux dans la logistique, la fabrication et le suivi de documents où un encodage compact d'informations liées est requis.

## Pourquoi utiliser Aspose.BarCode pour générer un code-barres DataMatrix ?

Aspose.BarCode vous offre un contrôle précis sur la taille du DataMatrix, le niveau de correction d’erreurs et les paramètres macro, prenant en charge plus de 30 symbologies de codes-barres et gérant des fichiers jusqu'à 10 Mo sans charger l'image complète en mémoire. Son implémentation .NET multiplateforme fonctionne sur .NET Framework, .NET Core et .NET 5/6, et inclut une reconnaissance intégrée afin que vous puissiez valider le code-barres instantanément.

## Guide étape par étape

### Étape 1 : configurer votre projet

Créez une nouvelle application console (ou tout projet .NET) dans Visual Studio. Ajoutez une référence aux DLL Aspose.BarCode que vous avez obtenues lors du téléchargement.

### Étape 2 : configuration macro DataMatrix

Le cœur du tutoriel – ici nous **créons réellement un code-barres DataMatrix** avec un caractère macro.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixMacro:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE"))
{
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    // Set the macro character to 05
    gen.Parameters.Barcode.DataMatrix.MacroCharacters = MacroCharacter.Macro05;
    gen.Save($"{path}DataMatrixMacro.png", BarCodeImageFormat.Png);

    // Try to recognize it
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixMacro:" + result.CodeText);
    }
}
```

> **Astuce :** Remplacez `"ASPOSE"` par n'importe quelle chaîne que vous devez encoder. Le caractère macro (`Macro05`) indique aux scanners que ce code-barres fait partie d'une séquence macro.

### Étape 3 : personnaliser les paramètres du code-barres pour la correction d’erreurs

Avant d'enregistrer, vous pouvez ajuster des paramètres supplémentaires :

- **XDimension** – contrôle la taille de chaque module (pixel).  
- **Margin**, **ErrorCorrection** et **EncodingMode** – tous accessibles via `gen.Parameters.Barcode.DataMatrix`.

### Étape 4 : enregistrer le code-barres

L'extrait ci‑dessus enregistre l'image sous le nom `DataMatrixMacro.png` dans le dossier que vous avez spécifié. Le PNG est sans perte, ce qui le rend idéal pour un traitement ultérieur.

### Étape 5 : reconnaître le code-barres

`BarCodeReader` est la classe d'Aspose.BarCode pour décoder les codes-barres à partir d'images. En utilisant `BarCodeReader`, nous lisons immédiatement l'image générée afin de confirmer que le caractère macro et les données sont corrects. Cette validation en aller‑retour est particulièrement pratique lors des tests automatisés.

## Comment utiliser DataMatrix dans des scénarios réels ?

Vous pouvez appliquer des codes-barres DataMatrix avec caractères macro à l'étiquetage de produits, en liant les numéros de série à une base de données centrale, au suivi de documents en intégrant une référence à un enregistrement numérique, et aux étiquettes d'équipements de santé qui stockent les données du patient ou de l'appareil dans un petit symbole scannable. Ces cas d'utilisation réduisent la saisie manuelle de données et améliorent la traçabilité.

## Problèmes courants & solutions

| Problème | Raison | Solution |
|----------|--------|----------|
| Code-barres non reconnu | XDimension incorrecte ou résolution d'image faible | Augmentez `XDimension.Pixels` à 4‑6 et enregistrez en PNG ou TIFF |
| Caractère macro ignoré | Le lecteur ne prend pas en charge le mode macro | Utilisez un scanner/lecteur qui prend explicitement en charge le macro DataMatrix (par ex. les versions plus récentes de ZXing) |
| Chemin introuvable | Variable `path` invalide | Assurez‑vous que le répertoire existe ou utilisez `Path.Combine` avec `Environment.CurrentDirectory` |

## Questions fréquemment posées

**Q : Qu’est‑ce que Aspose.BarCode pour .NET ?**  
R : Aspose.BarCode pour .NET est une bibliothèque puissante qui permet aux développeurs .NET de générer et de reconnaître des codes-barres dans divers formats, y compris DataMatrix, QR, et plus.

**Q : Pourquoi devrais‑je utiliser les codes-barres DataMatrix ?**  
R : Les codes-barres DataMatrix sont compacts, très fiables et peuvent stocker de grandes quantités de données, ce qui les rend idéaux pour la fabrication, la logistique et la santé.

**Q : Où puis‑je trouver la documentation d’Aspose.BarCode pour .NET ?**  
R : Vous pouvez trouver la documentation sur [the Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).

**Q : Une version d’essai gratuite est‑elle disponible pour Aspose.BarCode pour .NET ?**  
R : Oui, vous pouvez télécharger une version d’essai gratuite depuis [the free trial link](https://releases.aspose.com/).

**Q : Où puis‑je obtenir du support pour Aspose.BarCode pour .NET ?**  
R : Si vous avez des questions ou besoin d’assistance, vous pouvez visiter le forum Aspose.BarCode pour .NET à [the support forum](https://forum.aspose.com/c/barcode/13).

---

**Dernière mise à jour :** 2026-08-17  
**Testé avec :** Aspose.BarCode 24.11 pour .NET  
**Auteur :** Aspose

## Tutoriels associés

- [Créer un code-barres aspose .net - Configurer le texte du code DataMatrix](/barcode/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Comment générer des codes-barres DataMatrix (ECC 200) avec Aspose.BarCode pour .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Configuration de l’ajout structuré DataMatrix avec Aspose.BarCode pour .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
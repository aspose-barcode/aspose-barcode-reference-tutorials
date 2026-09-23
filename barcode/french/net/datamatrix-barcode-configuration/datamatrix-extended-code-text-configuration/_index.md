---
date: 2026-09-23
description: Apprenez à utiliser Aspose.BarCode pour générer un code-barres DataMatrix
  avec texte de code étendu en .NET, idéal pour les applications d'inventaire et de
  logistique.
keywords:
- how to use aspose
- create barcode for inventory
- barcode generation .net core
- generate barcode image c#
lastmod: 2026-09-23
linktitle: Configuration du texte de code étendu DataMatrix
og_description: Comment utiliser Aspose.BarCode pour générer un code-barres DataMatrix
  avec texte de code étendu en .NET. Suivez un guide rapide étape par étape pour les
  solutions d'inventaire et de logistique.
og_image_alt: Screenshot of a DataMatrix barcode generated with Aspose.BarCode in
  a .NET console app
og_title: Comment utiliser Aspose.BarCode pour créer du texte de code DataMatrix en
  .NET
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  headline: How to use Aspose.BarCode to create DataMatrix code text in .NET
  type: TechArticle
- description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  name: How to use Aspose.BarCode to create DataMatrix code text in .NET
  steps:
  - name: Define the output folder
    text: Specify where the generated barcode image will be saved. Replace the placeholder
      with a valid path on your machine.
  - name: Build the extended code text
    text: '`DataMatrixExtCodetextBuilder` is a helper class that assembles the extended
      code text according to the DataMatrix specification. It automatically inserts
      the required ECI (Extended Channel Interpretation) markers. This mix demonstrates
      how you can combine Unicode characters, C40 encoding, plain tex'
  - name: Generate the final codetext string
    text: After configuring all parts, retrieve the combined string that Aspose.BarCode
      will embed into the barcode.
  - name: Create the DataMatrix barcode
    text: '`BarcodeGenerator` is the core class that produces barcode images. Instantiate
      it with `EncodeTypes.DataMatrix` and the extended codetext, then set visual
      parameters such as X‑dimension, image format, and optional human‑readable text.
      The above code **creates barcode aspose .net** with the desired e'
  - name: Verify the barcode by reading it back
    text: '`BarCodeReader` validates that the generated symbol can be decoded correctly,
      which is essential for automated test pipelines and quality assurance. If everything
      is set up properly, the console will output the exact extended code text you
      built earlier.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET
    question: What library is needed?
  - answer: DataMatrix with extended code text
    question: Which barcode type?
  - answer: Yes, the API is cross‑platform
    question: Can I use .NET Core / .NET 6?
  - answer: A free trial works for development; a license is required for production
    question: Do I need a license for testing?
  - answer: About 10‑15 minutes for a basic example
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- Aspose.BarCode
- DataMatrix
- .NET barcode
- C# barcode generation
- inventory labeling
title: Comment utiliser Aspose.BarCode pour créer du texte de code DataMatrix en .NET
url: /fr/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment utiliser Aspose.BarCode pour créer du texte de code DataMatrix en .NET

## Réponses rapides
- **Quelle bibliothèque est nécessaire ?** Aspose.BarCode for .NET  
- **Quel type de code-barres ?** DataMatrix avec texte de code étendu  
- **Puis-je utiliser .NET Core / .NET 6 ?** Oui, l'API est multiplateforme  
- **Ai-je besoin d'une licence pour les tests ?** Un essai gratuit fonctionne pour le développement ; une licence est requise pour la production  
- **Combien de temps prend l'implémentation ?** Environ 10‑15 minutes pour un exemple de base  

## Qu'est-ce qu'Aspose.BarCode pour .NET ?
Aspose.BarCode for .NET est une bibliothèque commerciale qui permet aux développeurs de générer et de reconnaître plus de 30 symbologies de codes-barres, y compris DataMatrix, QR et Code 128, et de produire des images jusqu'à 10 000 × 10 000 pixels sans dépendances externes. Elle prend en charge .NET Framework 4.5+, .NET Core 3.1+, et .NET 5/6/7.

## Pourquoi utiliser le texte de code étendu DataMatrix ?
Le texte de code étendu DataMatrix vous permet d'intégrer plusieurs schémas d'encodage—UTF‑8, C40, Text, X12—dans un seul symbole, autorisant jusqu'à **3116 codewords** (environ 155 KB de données) dans un carré compact. Cette capacité est idéale pour l'étiquetage multilingue de produits, le suivi de dispositifs médicaux et l'emballage intelligent où vous devez combiner des identifiants alphanumériques avec des charges binaires.

## Prérequis
1. **Aspose.BarCode for .NET** – téléchargez-le depuis le site officiel **[Aspose.BarCode .NET download page](https://releases.aspose.com/barcode/net/)**.  
2. **Un environnement de développement .NET** – Visual Studio, Rider ou VS Code avec le SDK .NET.  
3. **Connaissances de base en C#** – vous devez être à l'aise avec les classes, les espaces de noms et la directive `using`.

## Importer les espaces de noms
Ajoutez les espaces de noms requis en haut de votre fichier C# afin que le compilateur sache où trouver les classes de code-barres.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

Ces espaces de noms vous donnent accès aux fonctionnalités de génération et de reconnaissance de codes-barres.

## Comment configurer le texte de code étendu DataMatrix ?
Chargez le constructeur, ajoutez les segments souhaités, et laissez Aspose.BarCode gérer automatiquement les marqueurs ECI. Ce paragraphe de réponse directe vous indique les étapes exactes : créez un `DataMatrixExtCodetextBuilder`, ajoutez des segments Unicode, C40, texte brut et mode Text, puis récupérez la chaîne combinée pour le générateur.

### Étape 1 : Définir le dossier de sortie
Spécifiez où l'image du code-barres généré sera enregistrée. Remplacez le texte de substitution par un chemin valide sur votre machine.

```csharp
string path = "Your Directory Path";
```

### Étape 2 : Construire le texte de code étendu
`DataMatrixExtCodetextBuilder` est une classe d'aide qui assemble le texte de code étendu selon la spécification DataMatrix. Elle insère automatiquement les marqueurs ECI (Extended Channel Interpretation) requis.

```csharp
DataMatrixExtCodetextBuilder codetextBuilder = new DataMatrixExtCodetextBuilder();
codetextBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
codetextBuilder.AddECICodetextWithEncodeMode(ECIEncodings.UTF8, DataMatrixEncodeMode.C40, "ABCDE");
codetextBuilder.AddPlainCodetext("test");
codetextBuilder.AddCodetextWithEncodeMode(DataMatrixEncodeMode.Text, "abcde");
```

Cet exemple montre comment vous pouvez combiner des caractères Unicode, l'encodage C40, du texte brut et le mode Text dans un seul symbole DataMatrix.

### Étape 3 : Générer la chaîne de texte de code finale
Après avoir configuré toutes les parties, récupérez la chaîne combinée que Aspose.BarCode intégrera dans le code-barres.

```csharp
string codetext = codetextBuilder.GetExtendedCodetext();
```

### Étape 4 : Créer le code-barres DataMatrix
`BarcodeGenerator` est la classe principale qui produit les images de code-barres. Instanciez‑la avec `EncodeTypes.DataMatrix` et le texte de code étendu, puis définissez les paramètres visuels tels que la dimension X, le format d'image et le texte lisible optionnel.

```csharp
using (var generator = new BarcodeGenerator(EncodeTypes.DataMatrix, codetext))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended Codetext";
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ExtendedCodetext;

    generator.Save($"{path}DataMatrixExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Le code ci‑dessus **crée un code-barres Aspose .NET** avec le texte de code étendu souhaité et l'enregistre au format PNG.

### Étape 5 : Vérifier le code-barres en le lisant à nouveau
`BarCodeReader` valide que le symbole généré peut être décodé correctement, ce qui est essentiel pour les pipelines de tests automatisés et l'assurance qualité.

```csharp
using (var reader = new BarCodeReader(generator.GenerateBarCodeImage(), DecodeType.DataMatrix))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
        Console.WriteLine("DataMatrixExtendedCodetext:" + result.CodeText);
}
```

Si tout est correctement configuré, la console affichera le texte de code étendu exact que vous avez construit précédemment.

## Problèmes courants et dépannage

| Problème | Raison | Solution |
|----------|--------|----------|
| Code-barres illisible | Dimension X trop faible | Augmentez `XDimension.Pixels` (par ex., 4 → 6) |
| Caractères corrompus | Encodage ECI incorrect | Assurez‑vous que `ECIEncodings.UTF8` correspond au jeu de caractères |
| Fichier non enregistré | Chemin invalide | Utilisez un chemin absolu ou assurez‑vous que le dossier existe |
| Exception de licence | Essai expiré | Appliquez une licence temporaire ou complète (voir FAQ) |

## Questions fréquemment posées

### Q1 : Qu'est‑ce qu'Aspose.BarCode pour .NET ?
R1 : Aspose.BarCode for .NET est une bibliothèque puissante qui permet aux développeurs de générer et de reconnaître une grande variété de symbologies de codes-barres, y compris DataMatrix, QR, Code128, et plus encore.

### Q2 : Où puis‑je trouver la documentation d'Aspose.BarCode pour .NET ?
R2 : Vous pouvez accéder à la référence complète de l'API **[Aspose.BarCode .NET API reference](https://reference.aspose.com/barcode/net/)**.

### Q3 : Existe‑t‑il un essai gratuit disponible pour Aspose.BarCode pour .NET ?
R3 : Oui, une version d'essai gratuite peut être téléchargée depuis **[Aspose.BarCode free trial download](https://releases.aspose.com/)**.

### Q4 : Comment obtenir une licence temporaire pour les tests ?
R4 : Les licences temporaires sont fournies à des fins d'évaluation et peuvent être demandées via **[Aspose temporary license request page](https://purchase.aspose.com/temporary-license/)**.

### Q5 : Où puis‑je obtenir du support ou poser des questions sur Aspose.BarCode pour .NET ?
R5 : Le forum officiel d'Aspose.BarCode est le meilleur endroit pour obtenir de l'aide : **[Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)**.

**Dernière mise à jour :** 2026-09-23  
**Testé avec :** Aspose.BarCode 24.11 for .NET  
**Auteur :** Aspose

## Tutoriels associés

- [Comment générer des codes-barres DataMatrix avec Aspose.BarCode pour .NET – Guide étape par étape](/barcode/net/datamatrix-barcode-configuration/)
- [Générer un code-barres DataMatrix en mode ASCII avec Aspose.BarCode pour .NET (C#)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Générer un code-barres Aztec avec encodage texte en utilisant Aspose.BarCode pour .NET](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
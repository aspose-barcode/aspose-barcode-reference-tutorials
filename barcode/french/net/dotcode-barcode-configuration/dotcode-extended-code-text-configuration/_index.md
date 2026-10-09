---
date: 2026-09-28
description: Apprenez comment créer un 2d matrix barcode avec Aspose.BarCode for .NET
  – un guide étape par étape pour générer des codes-barres DotCode avec extended code
  text.
keywords:
- create 2d matrix barcode
- how to generate dotcode
- dotcode extended codetext
lastmod: 2026-09-28
linktitle: Configuration de DotCode Extended Code Text
og_description: Apprenez à créer un 2d matrix barcode en utilisant Aspose.BarCode
  for .NET. Ce guide montre étape par étape comment générer des codes-barres DotCode
  avec extended code text.
og_image_alt: Guide showing how to create a 2d matrix DotCode barcode with extended
  codetext in .NET
og_title: Créer un 2d matrix barcode avec Aspose.BarCode for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create 2d matrix barcode with Aspose.BarCode for .NET
    – a step‑by‑step guide for generating DotCode barcodes with extended code text.
  headline: How to create 2d matrix barcode via Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. The PNG image produced by the generator can be embedded in iOS, Android,
      or any cross‑platform mobile application.
    question: Can I use the generated barcode in a mobile app?
  - answer: Use the `AddECICodetext` method with the appropriate `ECIEncodings` (e.g.,
      `ECIEncodings.Base64`) to embed binary payloads.
    question: What if I need to encode binary data instead of text?
  - answer: Adjust the `XDimension.Pixels` property; higher values increase module
      size, while lower values make the barcode more compact.
    question: How do I change the barcode size without affecting readability?
  - answer: Yes. Set `gen.Parameters.Barcode.Margin` to define the desired quiet zone
      in pixels.
    question: Is there a way to add a quiet zone around the barcode?
  - answer: The latest Aspose.BarCode releases are compatible with .NET 8; just reference
      the appropriate NuGet package version.
    question: Does the library support .NET 8?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- dotcode
- Aspose.BarCode
- .NET barcode generation
- 2d matrix barcode
title: Comment créer un 2d matrix barcode via Aspose.BarCode for .NET
url: /fr/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code-barres matriciel 2D avec Aspose.BarCode pour .NET

## Introduction

Dans le domaine de la génération et de la gestion des codes-barres, Aspose.BarCode pour .NET se distingue comme une solution polyvalente qui prend en charge **plus de 50 formats d'entrée et de sortie** et peut traiter des documents de plusieurs centaines de pages sans charger le fichier complet en mémoire. Que vous ayez besoin de codes-barres pour le suivi des produits, le contrôle des stocks ou des applications riches en données, créer un **code-barres matriciel 2D** tel que DotCode avec un codetext étendu vous permet d'intégrer à la fois des charges utiles textuelles et binaires dans un symbole carré compact. Ce tutoriel vous guide pas à pas dans la construction de ce codetext étendu et le rendu de l'image finale.

## Réponses rapides
- **Que signifie « créer un codetext étendu pour dotcode » ?** Cela signifie créer un code-barres DotCode qui inclut FNC1, ECICodetext, texte brut et séparateurs de symboles dans une seule charge utile étendue.  
- **Quelle bibliothèque est requise ?** Aspose.BarCode pour .NET.  
- **Ai-je besoin d'une licence ?** Une licence temporaire fonctionne pour l'évaluation ; une licence complète est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **Combien de temps prend l'implémentation ?** Environ 10‑15 minutes pour un exemple de base.

## Comment créer un codetext étendu pour dotcode

Chargez votre projet, définissez le répertoire, construisez le codetext étendu et générez l'image – le tout en moins d'une douzaine de lignes de code. La réponse directe suivante résume l'ensemble du processus :

Chargez le `BarcodeGenerator` avec `EncodeTypes.DotCode`, construisez le codetext étendu à l'aide de `DotCodeExtendedCodetextBuilder` (en ajoutant FNC1, ECICodetext, texte brut et séparateurs FNC3), puis appelez `Save` pour écrire un fichier PNG. Cette séquence crée un code-barres matriciel 2D entièrement conforme en un seul appel.

## Qu'est-ce que le codetext étendu pour dotcode ?

Le **dotcode extended codetext** est une chaîne composite qui combine plusieurs segments de données — tels que les identifiants FNC1, ECICodetext, texte brut et séparateurs FNC3 — en une seule charge utile que DotCode peut décoder. Il permet l'encodage de texte multilingue, de blobs binaires et de données structurées dans un seul code-barres matriciel 2D, ce qui le rend idéal pour les scénarios de chaîne d'approvisionnement, de santé et d'IoT.

## Pourquoi utiliser Aspose.BarCode pour cette tâche ?

Aspose.BarCode traite **jusqu'à 500 pages par seconde** sur du matériel serveur typique et prend en charge **plus de 30 symbologies de codes-barres**, y compris DotCode. Son API `GetExtendedCodetext` garantit le placement correct des caractères de contrôle, éliminant les erreurs de concaténation manuelle de chaînes et assurant la conformité à la norme ISO/IEC 24724. De plus, il offre une correction d'erreurs intégrée et une gestion automatique de la zone silencieuse, réduisant le besoin d'ajustements manuels.

## Prérequis

- **Aspose.BarCode for .NET** – téléchargez depuis la [documentation Aspose.BarCode for .NET](https://reference.aspose.com/barcode/net/).  
- Un environnement de développement .NET (Visual Studio 2022 ou version ultérieure recommandé).  
- Optionnel : un fichier de licence temporaire pour l'évaluation.

## Importer les espaces de noms

`using Aspose.BarCode.Generation;`  
`using Aspose.BarCode.ComplexBarcodes;`  

Ces espaces de noms exposent la classe `BarcodeGenerator` et l'aide `DotCodeExtendedCodetextBuilder` nécessaires à l'exemple.

```csharp
using Aspose.BarCode.Generation;
```

Maintenant que nous avons couvert les prérequis, décomposons le processus de génération du DotCode Extended Code Text en un guide étape par étape.

## Étape 1 : définir le chemin du répertoire

Spécifiez où le PNG généré sera enregistré. Utilisez un chemin absolu ou relatif que votre application peut écrire.

```csharp
string path = "Your Directory Path";
```

Remplacez `"Your Directory Path"` par le chemin réel sur votre système.

## Étape 2 : créer le codetext étendu pour dotcode

La classe `DotCodeExtendedCodetextBuilder` assemble les différents segments en une seule chaîne de codetext étendu.

Pour créer le DotCode Extended Code Text, suivez ces sous‑étapes :

### 2.1 ajouter l'identifiant de format fnc1

L'identifiant de format FNC1 marque le début d'un nouveau champ de données. Il est requis pour les symboles DotCode conformes à GS1.

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 ajouter ecicodetext

L'ECICodetext encode les caractères spéciaux et le texte international. Dans cet exemple, nous encodons `"犬Right狗"` en UTF‑8.

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 ajouter du texte brut

Vous pouvez également ajouter du texte brut au DotCode Extended Code Text. Ici, nous ajoutons `"Plain text"`.

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 ajouter le séparateur de symbole fnc3

Le séparateur de symbole FNC3 sépare les différentes sections du code, améliorant la lisibilité pour les scanners.

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 ajouter l'initialisation du lecteur fnc3

Cette étape ajoute les informations d'Initialisation du Lecteur FNC3, qui indiquent au scanner comment interpréter les données suivantes.

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 générer le codetext

Générez maintenant le DotCode Extended Codetext en appelant la méthode `GetExtendedCodetext` sur l'objet `textBuilder`.

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## Étape 3 : générer l'image dotcode

Rendez l'image du code-barres à partir du codetext étendu.

#### 3.1 initialiser le générateur de code-barres

La classe `BarcodeGenerator` est l'objet central d'Aspose.BarCode pour créer n'importe quel code-barres. Vous l'instanciez avec la symbologie souhaitée (`EncodeTypes.DotCode`) et le codetext étendu que vous venez de construire.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    // Set the X-dimension for the barcode (adjust as needed).
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    // Set the DotCode encoding mode to ExtendedCodetext.
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    // Save the generated barcode image.
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Enfin, appelez `Save` pour écrire le fichier PNG sur le disque. L'image est prête à être intégrée dans des rapports, des applications mobiles ou des étiquettes imprimées.

## Problèmes courants et solutions

- **Encodage incorrect** – Assurez-vous d'utiliser `ECIEncodings.UTF8` lors de l'ajout de texte multilingue ; sinon les caractères peuvent apparaître corrompus.  
- **Erreurs d'accès aux fichiers** – Vérifiez que l'application possède les permissions d'écriture sur le répertoire cible.  
- **Zone silencieuse manquante** – Définissez `gen.Parameters.Barcode.Margin` si les scanners nécessitent un espace blanc supplémentaire autour du symbole.

## Questions fréquemment posées

**Q : Puis-je utiliser le code-barres généré dans une application mobile ?**  
R : Oui. L'image PNG produite par le générateur peut être intégrée dans iOS, Android ou toute application mobile multiplateforme.

**Q : Et si je dois encoder des données binaires au lieu du texte ?**  
R : Utilisez la méthode `AddECICodetext` avec le `ECIEncodings` approprié (par ex., `ECIEncodings.Base64`) pour intégrer des charges binaires.

**Q : Comment modifier la taille du code-barres sans affecter la lisibilité ?**  
R : Ajustez la propriété `XDimension.Pixels` ; des valeurs plus élevées augmentent la taille du module, tandis que des valeurs plus faibles rendent le code-barres plus compact.

**Q : Existe-t-il un moyen d'ajouter une zone silencieuse autour du code-barres ?**  
R : Oui. Définissez `gen.Parameters.Barcode.Margin` pour spécifier la zone silencieuse souhaitée en pixels.

**Q : La bibliothèque prend‑elle en charge .NET 8 ?**  
R : Les dernières versions d'Aspose.BarCode sont compatibles avec .NET 8 ; il suffit de référencer la version appropriée du package NuGet.

Si vous avez besoin de plus d'informations ou avez des questions, n'hésitez pas à consulter la [documentation Aspose.BarCode for .NET](https://reference.aspose.com/barcode/net/) ou à interagir avec la communauté sur le [forum de support Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**Dernière mise à jour :** 2026-09-28  
**Testé avec :** Aspose.BarCode 24.12 pour .NET  
**Auteur :** Aspose

## Tutoriels associés

- [Créer un code-barres DotCode .NET (mode automatique) avec Aspose.BarCode](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)
- [Comment générer des codes-barres DataMatrix avec Aspose.BarCode pour .NET – Guide étape par étape](/barcode/net/datamatrix-barcode-configuration/)
- [Comment créer un code-barres Aztec avec Aspose.BarCode pour .NET](/barcode/net/aztec-barcode-encoding/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
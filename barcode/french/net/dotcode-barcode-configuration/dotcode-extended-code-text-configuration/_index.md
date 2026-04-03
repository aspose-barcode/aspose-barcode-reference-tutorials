---
date: 2026-01-27
description: Apprenez à créer du texte de code étendu DotCode avec Aspose.BarCode
  pour .NET – un guide étape par étape pour générer des codes‑barres DotCode contenant
  du texte de code étendu.
linktitle: DotCode Extended Code Text Configuration
second_title: Aspose.BarCode .NET API
title: Comment créer un texte de code étendu DotCode avec Aspose.BarCode pour .NET
url: /fr/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un texte de code étendu dotcode avec Aspose.BarCode pour .NET

## Introduction

Dans le domaine de la génération et de la gestion des codes‑barres, Aspose.BarCode pour .NET se distingue comme une solution polyvalente et efficace. Que vous ayez besoin de générer des codes‑barres pour des produits, des stocks ou toute autre application, Aspose.BarCode pour .NET répond à vos besoins. Dans ce tutoriel complet, nous allons **créer un texte de code étendu dotcode** et explorer pourquoi cette capacité est essentielle dans les environnements modernes riches en données. DotCode est un code‑barres matriciel bidimensionnel qui peut encoder à la fois des données textuelles et binaires, ce qui en fait un outil précieux dans diverses industries.

## Réponses rapides
- **Que signifie « créer un texte de code étendu dotcode » ?** Cela consiste à construire un code‑barres DotCode incluant FNC1, ECICodetext, texte simple et séparateurs de symbole dans une charge utile étendue unique.  
- **Quelle bibliothèque est requise ?** Aspose.BarCode pour .NET.  
- **Ai‑je besoin d’une licence ?** Une licence temporaire suffit pour l’évaluation ; une licence complète est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **Combien de temps prend l’implémentation ?** Environ 10‑15 minutes pour un exemple de base.

## Comment créer un texte de code étendu dotcode

Voici un guide concis, étape par étape, qui montre exactement comment construire le texte de code étendu et rendre l’image du code‑barres.

## Prérequis

Avant de plonger dans le guide pas à pas, voici quelques prérequis nécessaires pour suivre efficacement :

1. Aspose.BarCode pour .NET : assurez‑vous que la bibliothèque Aspose.BarCode pour .NET est installée et prête. Sinon, vous pouvez la télécharger depuis la [documentation Aspose.BarCode pour .NET](https://reference.aspose.com/barcode/net/).

2. Environnement de développement : vous devez disposer d’un environnement de développement .NET fonctionnel, de préférence Visual Studio, installé sur votre système.

Avec ces prérequis en place, nous pouvons maintenant procéder à la génération du texte de code étendu DotCode.

## Importer les espaces de noms

Tout d’abord, vous devez importer les espaces de noms nécessaires dans votre projet .NET afin d’accéder aux fonctionnalités requises de la bibliothèque Aspose.BarCode. Voici comment faire :

```csharp
using Aspose.BarCode.Generation;
```

Maintenant que les prérequis sont couverts, détaillons le processus de génération du texte de code étendu DotCode étape par étape.

## Étape 1 : définir le chemin du répertoire

Dans cette étape, vous devez spécifier le chemin du répertoire où vous souhaitez enregistrer l’image du texte de code étendu DotCode générée.

```csharp
string path = "Your Directory Path";
```

Remplacez `"Your Directory Path"` par le chemin réel sur votre système.

## Étape 2 : créer le texte de code étendu DotCode

Pour créer le texte de code étendu DotCode, suivez ces sous‑étapes :

### 2.1 Ajouter l'identifiant de format FNC1

L'identifiant de format FNC1 est utilisé pour indiquer le début d'un nouveau champ de données. C'est une partie essentielle du texte de code étendu DotCode.

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 Ajouter ECICodetext

L'ECICodetext est l'endroit où vous pouvez encoder des caractères spéciaux et du texte international. Dans cet exemple, nous avons encodé `"犬Right狗"` en utilisant l'encodage UTF‑8.

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 Ajouter un texte de code simple

Vous pouvez également ajouter du texte simple au texte de code étendu DotCode. Ici, nous avons ajouté `"Plain text"`.

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 Ajouter le séparateur de symbole FNC3

Le séparateur de symbole FNC3 est utilisé pour séparer différentes sections du code.

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 Ajouter l'initialisation du lecteur FNC3

Cette étape ajoute les informations d'initialisation du lecteur FNC3.

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 Générer le texte de code

Maintenant, générez le texte de code étendu DotCode en appelant la méthode `GetExtendedCodetext` sur l'objet `textBuilder`.

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## Étape 3 : générer l'image DotCode

Pour générer le texte de code étendu DotCode sous forme d'image, suivez ces sous‑étapes :

#### 4.1 Initialiser le générateur de code‑barres

Initialisez le `BarcodeGenerator` avec les paramètres appropriés. Dans ce cas, nous utilisons `EncodeTypes.DotCode` et le texte de code généré.

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

Et voilà ! Vous avez généré avec succès le texte de code étendu DotCode à l’aide d’Aspose.BarCode pour .NET.

## Conclusion

Aspose.BarCode pour .NET est un outil puissant qui simplifie la génération de codes‑barres. Dans ce tutoriel, nous nous sommes concentrés sur la **création d’un texte de code étendu dotcode**, essentiel dans diverses industries, notamment lorsqu’un encodage multilingue et de caractères spécialisés est requis. En suivant les étapes décrites ci‑dessus, vous pouvez facilement créer le texte de code étendu DotCode pour vos besoins spécifiques.

Si vous avez besoin d’une assistance supplémentaire ou avez des questions, n’hésitez pas à consulter la [documentation Aspose.BarCode pour .NET](https://reference.aspose.com/barcode/net/) ou à rejoindre la communauté sur le [forum de support Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

## FAQ

### Q1 : À quoi sert DotCode ?

R1 : DotCode sert à encoder à la fois des données textuelles et binaires et est couramment utilisé dans des secteurs comme la santé et la logistique pour le suivi et l’encodage de données.

### Q2 : Puis‑je personnaliser l’apparence des codes‑barres DotCode ?

R2 : Oui, Aspose.BarCode pour .NET offre des options pour personnaliser l’apparence des codes‑barres DotCode, y compris la taille et le mode d’encodage.

### Q3 : Aspose.BarCode pour .NET est‑il compatible avec différents frameworks .NET ?

R3 : Oui, Aspose.BarCode pour .NET est compatible avec un large éventail de frameworks .NET, garantissant flexibilité et facilité d’intégration.

### Q4 : Comment obtenir une licence temporaire pour Aspose.BarCode pour .NET ?

R4 : Vous pouvez obtenir une licence temporaire depuis le [site d’Aspose](https://purchase.aspose.com/temporary-license/) pour l’évaluation et les tests.

### Q5 : Aspose.BarCode pour .NET convient‑il à la génération de codes‑barres de niveau entreprise ?

R5 : Absolument, Aspose.BarCode pour .NET est conçu pour répondre aux besoins tant des petites que des grandes entreprises, offrant évolutivité et fiabilité.

## Questions fréquemment posées

**Q : Puis‑je utiliser le code‑barres généré dans une application mobile ?**  
R : Oui. L’image PNG produite par le générateur peut être intégrée dans iOS, Android ou toute application mobile multiplateforme.

**Q : Et si je dois encoder des données binaires au lieu de texte ?**  
R : Utilisez la méthode `AddECICodetext` avec le `ECIEncodings` approprié (par ex., `ECIEncodings.Base64`) pour intégrer des charges binaires.

**Q : Comment modifier la taille du code‑barres sans affecter la lisibilité ?**  
R : Ajustez la propriété `XDimension.Pixels` ; des valeurs plus élevées augmentent la taille du module, tandis que des valeurs plus faibles rendent le code‑barres plus compact.

**Q : Existe‑t‑il un moyen d’ajouter une zone silencieuse autour du code‑barres ?**  
R : Oui. Définissez `gen.Parameters.Barcode.Margin` pour spécifier la zone silencieuse souhaitée en pixels.

**Q : La bibliothèque prend‑elle en charge .NET 8 ?**  
R : Les dernières versions d’Aspose.BarCode sont compatibles avec .NET 8 ; il suffit de référencer la version NuGet appropriée.

---

**Dernière mise à jour :** 2026-01-27  
**Testé avec :** Aspose.BarCode 24.12 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
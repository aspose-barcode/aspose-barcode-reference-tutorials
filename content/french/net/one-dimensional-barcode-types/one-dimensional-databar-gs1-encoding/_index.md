---
title: Encodage GS1 de barre de données unidimensionnelle
linktitle: Encodage GS1 de barre de données unidimensionnelle
second_title: API Aspose.BarCode .NET
description: Apprenez à créer des codes à barres codés Databar GS1 dans .NET à l'aide d'Aspose.BarCode. Générez facilement des codes-barres. Suivez notre guide étape par étape.
type: docs
weight: 18
url: /fr/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
---

Dans ce didacticiel, nous vous guiderons tout au long du processus de création de codes-barres codés Databar GS1 unidimensionnels à l'aide de la bibliothèque Aspose.BarCode for .NET. Que vous cherchiez à générer des codes-barres avec ou sans encodage GS1, nous avons ce qu'il vous faut. Ce guide étape par étape vous aidera à comprendre les conditions préalables, à importer des espaces de noms et à démontrer chaque exemple pour créer facilement des codes-barres codés Databar GS1.

## Conditions préalables

Avant de plonger dans le code, assurez-vous que les conditions préalables suivantes sont en place :

1.  Aspose.BarCode pour .NET : Aspose.BarCode pour .NET doit être installé. Si ce n'est pas déjà fait, vous pouvez le télécharger depuis[ici](https://releases.aspose.com/barcode/net/).

2.  Votre chemin de répertoire : Remplacer`"Your Directory Path"` dans les exemples de code avec le chemin réel où vous souhaitez enregistrer les images de codes-barres générées.

Maintenant que vous disposez des prérequis nécessaires, passons à la partie codage.

## Importation d'espaces de noms

Pour commencer, vous devez importer les espaces de noms pertinents pour Aspose.BarCode. Ajoutez les lignes de code suivantes au début de votre projet .NET :

```csharp
using Aspose.BarCode;
using System;
```

## Étape 1 : initialiser le générateur de codes-barres

La première étape consiste à initialiser l'objet BarcodeGenerator avec le type d'encodage souhaité. Dans ce cas, nous utilisons l’encodage Databar Expanded. 

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## Étape 2 : générer un code-barres avec l'encodage GS1

Maintenant, nous allons définir le texte du code avec la vérification GS1Encoding et enregistrer l'image du code-barres générée. 

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## Étape 3 : générer un code-barres à codage variable

Dans cette étape, nous générerons un code-barres avec un texte de code variable sans vérification GS1Encoding.

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## Étape 4 : Gérer l'exception pour la vérification de l'encodage GS1

Si vous essayez de générer un code-barres avec un texte de code variable avec la vérification GS1Encoding activée, une exception sera levée. Voici comment vous pouvez le gérer :

```csharp
try
{
    gen.CodeText = "ASPOSE";
    gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

Vous avez maintenant créé avec succès des codes à barres codés Databar GS1 unidimensionnels avec Aspose.BarCode pour .NET. Vous pouvez explorer et personnaliser davantage votre génération de codes-barres en fonction de vos besoins spécifiques.

## Conclusion

Dans ce didacticiel, nous avons couvert le processus de génération de codes-barres codés Databar GS1 unidimensionnels à l'aide d'Aspose.BarCode pour .NET. Nous avons discuté des conditions préalables, importé les espaces de noms nécessaires et fourni des conseils étape par étape pour créer des codes-barres codés GS1 et à codage variable.

 Avec Aspose.BarCode pour .NET, la génération de codes-barres devient une tâche transparente, offrant flexibilité et contrôle sur vos besoins en matière de création de codes-barres. Si vous rencontrez des problèmes ou avez des questions, n'hésitez pas à visiter le[Documentation Aspose.BarCode](https://reference.aspose.com/barcode/net/) ou demander de l'aide sur le[Forum d'assistance Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

## Questions fréquemment posées

### 1. Qu'est-ce que l'encodage GS1 dans les codes-barres ?
Le codage GS1 est une norme utilisée dans les codes-barres pour garantir une structure et une identification correctes des données. Il est couramment utilisé pour les articles de vente au détail, de soins de santé et de logistique afin de faciliter un suivi précis et un échange d'informations.

### 2. Puis-je personnaliser l’apparence des codes-barres générés ?
Oui, vous pouvez personnaliser l'apparence des codes-barres générés avec Aspose.BarCode for .NET. Vous contrôlez divers paramètres tels que la taille, la couleur et le style.

### 3. Où puis-je trouver des ressources et de la documentation supplémentaires pour Aspose.BarCode ?
 Vous pouvez trouver une documentation complète et des exemples sur[Documentation Aspose.BarCode](https://reference.aspose.com/barcode/net/). Il s'agit d'une ressource précieuse pour l'apprentissage et le dépannage.

### 4. Existe-t-il une version d'essai disponible pour Aspose.BarCode ?
 Oui, vous pouvez obtenir une version d'essai gratuite d'Aspose.BarCode pour .NET à partir de[ici](https://releases.aspose.com/).

### 5. Comment puis-je acheter une licence pour Aspose.BarCode pour .NET ?
 Pour acheter une licence pour Aspose.BarCode pour .NET, visitez le[page d'achat](https://purchase.aspose.com/buy) sur le site Aspose.

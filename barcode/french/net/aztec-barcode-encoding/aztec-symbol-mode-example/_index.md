---
date: 2026-01-02
description: Apprenez à utiliser le générateur de code‑barres Aztec avec Aspose.BarCode
  pour .NET – guide étape par étape sur la façon de définir le mode de symbole Aztec
  (Auto, FullRange, Compact, Rune).
linktitle: Aztec Symbol Mode Example
second_title: Aspose.BarCode .NET API
title: générateur de code-barres aztec – Maîtriser le mode symbole Aztec avec Aspose.BarCode
  pour .NET
url: /fr/net/aztec-barcode-encoding/aztec-symbol-mode-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# barcode generator aztec – Maîtriser le mode symbole Aztec avec Aspose.BarCode pour .NET

## Quick Answers
- **Quelle est la classe principale ?** `BarcodeGenerator` de `Aspose.BarCode.Generation`.
- **Quels modes symbole sont disponibles ?** Auto, FullRange, Compact et Rune.
- **Ai-je besoin d'une licence ?** Une licence temporaire fonctionne pour les tests ; une licence complète est requise en production.
- **Puis-je modifier le texte du code ?** Oui, définissez `gen.CodeText` avant d'enregistrer.
- **Quels formats d'image sont pris en charge ?** PNG, JPEG, BMP, GIF, TIFF, et plus.

## What is a barcode generator aztec?
Le barcode generator aztec crée des codes Aztec bidimensionnels, un code matriciel compact capable de stocker une grande quantité de données dans un petit espace. Il est idéal pour les tickets mobiles, les URL et les données binaires où l'espace est limité.

## Why use Aspose.BarCode for .NET?
- **Support complet .NET** – fonctionne avec .NET Framework, .NET Core et .NET 5/6.
- **Ensemble de fonctionnalités riche** – plusieurs modes symbole, correction d’erreurs et personnalisation étendue.
- **Aucune dépendance externe** – générez des codes-barres entièrement en‑processus.
- **Cross‑platform** – fonctionne sous Windows, Linux et macOS.

## Prerequisites

- Une connaissance pratique du développement .NET.  
- Visual Studio installé sur votre machine.  
- Une copie d'Aspose.BarCode pour .NET. Vous pouvez le télécharger [ici](https://releases.aspose.com/barcode/net/).

Maintenant que vous êtes prêt, explorons les options du mode symbole Aztec.

## How to set Aztec Symbol Mode with the barcode generator aztec

### Importing Namespaces

Tout d'abord, ajoutez l'espace de noms requis en haut de votre fichier C# :

```csharp
using Aspose.BarCode.Generation;
```

Avec l'espace de noms importé, vous pouvez commencer à créer des codes Aztec.

### Step 1: Setting up the Barcode Generator

Initialisez le générateur avec le type d'encodage Aztec et fournissez le texte que vous souhaitez encoder :

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecSymbolModeExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

> **Astuce :** Utilisez une chaîne compatible UTF‑8 pour les caractères internationaux, comme illustré ci‑dessus.

### Step 2: Setting the Symbol Mode to Auto

Le mode **Auto** permet à la bibliothèque de choisir la taille optimale en fonction de la longueur des données :

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Auto;
gen.Save($"{path}AztecSymbolModeAuto.png", BarCodeImageFormat.Png);
```

Le PNG généré sera enregistré dans le dossier que vous avez spécifié.

### Step 3: Setting the Symbol Mode to FullRange

Si vous souhaitez que la bibliothèque utilise toute la gamme des tailles de symboles Aztec, choisissez **FullRange** :

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
gen.Save($"{path}AztecSymbolModeFullRange.png", BarCodeImageFormat.Png);
```

### Step 4: Setting the Symbol Mode to Compact

Pour un code-barres plus compact tout en conservant une bonne lisibilité, utilisez **Compact** :

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Compact;
gen.Save($"{path}AztecSymbolModeCompact.png", BarCodeImageFormat.Png);
```

### Step 5: Setting the Symbol Mode to Rune

Le mode **Rune** est conçu pour des cas d'utilisation spéciaux où un style visuel différent est requis :

```csharp
gen.CodeText = "123"; // Change the code text if needed
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Rune;
gen.Save($"{path}AztecSymbolModeRune.png", BarCodeImageFormat.Png);
```

### Common Issues and Solutions

| Problème | Solution |
|----------|----------|
| L'image du code-barres est vide | Vérifiez que `path` pointe vers un répertoire existant et accessible en écriture. |
| Caractères non pris en charge | Utilisez uniquement les caractères pris en charge par la norme Aztec ou passez à l'encodage UTF‑8. |
| Taille de symbole incorrecte | Expérimentez avec `AztecSymbolMode.Auto` pour laisser la bibliothèque choisir la meilleure taille. |

## Frequently Asked Questions

**Q : Quel est le but du mode symbole Aztec dans la génération de code-barres ?**  
R : Il vous permet de contrôler la densité visuelle et le niveau de correction d’erreurs du code Aztec, en adaptant le code-barres à vos exigences d'espace et de lisibilité.

**Q : Puis-je modifier le texte du code pour les codes Aztec dans Aspose.BarCode pour .NET ?**  
R : Oui, il suffit d'assigner une nouvelle chaîne à `gen.CodeText` avant d'appeler `Save`.

**Q : Existe-t-il une version d'essai gratuite d'Aspose.BarCode pour .NET ?**  
R : Oui, vous pouvez télécharger une version d'essai gratuite [ici](https://releases.aspose.com/).

**Q : Où puis-je trouver la documentation complète d'Aspose.BarCode pour .NET ?**  
R : La référence API complète est disponible [ici](https://reference.aspose.com/barcode/net/).

**Q : Comment obtenir une licence temporaire pour Aspose.BarCode pour .NET ?**  
R : Une licence temporaire peut être demandée via [ce lien](https://purchase.aspose.com/temporary-license/).

## Conclusion

Dans ce guide, nous avons couvert tout ce que vous devez savoir pour utiliser le **barcode generator aztec** avec Aspose.BarCode pour .NET, de la configuration du générateur à la maîtrise de chaque mode symbole (Auto, FullRange, Compact, Rune). Armé de ces exemples, vous pouvez désormais intégrer rapidement et de manière fiable des codes Aztec polyvalents dans n'importe quelle application .NET.

Si vous avez d'autres questions, n'hésitez pas à rejoindre la communauté Aspose.BarCode sur leur [forum de support](https://forum.aspose.com/c/barcode/13).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2026-01-02  
**Testé avec :** Aspose.BarCode 24.10 for .NET  
**Auteur :** Aspose
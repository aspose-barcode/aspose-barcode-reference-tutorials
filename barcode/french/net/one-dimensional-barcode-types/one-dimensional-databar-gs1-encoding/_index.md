---
date: 2026-03-07
description: Apprenez à créer des codes‑barres databar unidimensionnels encodés GS1
  en .NET avec Aspose.BarCode. Ce guide montre comment définir GS1, configurer le
  générateur de codes‑barres et générer rapidement des codes‑barres.
linktitle: One-Dimensional Databar GS1 Encoding
second_title: Aspose.BarCode .NET API
title: Créer un encodage GS1 Databar unidimensionnel avec Aspose.BarCode
url: /fr/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code-barres Databar unidimensionnel avec encodage GS1 à l'aide d'Aspose.BarCode

Dans ce tutoriel, vous allez **créer des codes-barres databar unidimensionnels** conformes à la norme GS1, en utilisant la bibliothèque Aspose.BarCode pour .NET. Que vous ayez besoin d’une validation GS1 stricte ou d’un code-barres plus flexible, nous parcourrons chaque étape — de l’installation de la bibliothèque à la gestion des exceptions d’encodage — afin que vous puissiez générer des codes-barres fiables dans vos propres applications.

## Réponses rapides
- **Que signifie « créer un databar unidimensionnel » ?** Cela signifie générer un code-barres linéaire (1‑D) de la famille Databar, souvent utilisé dans le commerce de détail et la logistique.  
- **Comment définir la validation GS1 ?** Définissez `IsAllowOnlyGS1Encoding` sur `true` dans les paramètres `DataBar`.  
- **Ai‑je besoin d’une licence ?** Un essai gratuit suffit pour le développement ; une licence commerciale est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Où puis‑je télécharger la bibliothèque ?** Depuis la page officielle de téléchargement d’Aspose (voir les prérequis).

## Qu’est‑ce que « créer un databar unidimensionnel » ?
Un Databar unidimensionnel (également appelé RSS) est un code‑barres linéaire compact capable d’encoder des données numériques, des dates ou des chaînes AI (Application Identifier). Lorsqu’il est associé à l’encodage GS1, le code‑barres suit une structure de données reconnue mondialement, ce qui le rend idéal pour le commerce de détail, la santé et les scénarios de chaîne d’approvisionnement.

## Pourquoi utiliser Aspose.BarCode pour .NET ?
Aspose.BarCode propose une API fluide, une prise en charge complète de GS1 et la possibilité d’ajuster finement chaque aspect visuel du code‑barres. Elle élimine les approximations de l’encodage bas‑niveau et vous permet de vous concentrer sur la logique métier.

## Prérequis

1. **Aspose.BarCode pour .NET** – téléchargez‑le et installez‑le depuis [here](https://releases.aspose.com/barcode/net/).  
2. **Your Directory Path** – remplacez `"Your Directory Path"` dans les exemples par un dossier où vous avez les droits d’écriture.

## Importation des espaces de noms

Ajoutez les instructions `using` requises en haut de votre fichier C# :

```csharp
using Aspose.BarCode;
using System;
```

## Étape 1 : Initialiser le générateur de code‑barres

Créez une instance `BarcodeGenerator` et spécifiez la symbologie Databar Expanded :

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## Étape 2 : Comment définir GS1 – Générer un code‑barres avec validation GS1 stricte

Activez l’encodage uniquement GS1, attribuez un texte de code conforme GS1, puis enregistrez l’image :

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## Étape 3 : Génération de code‑barres avec Aspose – Encodage variable (sans vérification GS1)

Si vous avez besoin d’un code‑barres qui **n’impose pas** les règles GS1, désactivez la vérification :

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## Étape 4 : Vérification GS1 du générateur de code‑barres – Gestion d’une exception

Lorsque `IsAllowOnlyGS1Encoding` est `true` mais que le texte de code n’est pas conforme GS1, Aspose lève une exception. Le modèle suivant montre comment la capturer et la consigner :

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

### Pièges courants et conseils
- **Piège :** Fournir une chaîne non‑GS1 alors que la vérification GS1 est activée interrompra la génération du code‑barres.  
- **Conseil pro :** Validez vos chaînes AI avant de les affecter à `CodeText` afin d’éviter les erreurs d’exécution.  
- **Astuce :** Utilisez des chemins absolus ou `Path.Combine` pour construire les noms de fichiers en toute sécurité sur toutes les plateformes.

## Conclusion

Vous savez maintenant comment **créer des codes-barres databar unidimensionnels** avec encodage GS1, comment activer ou désactiver la vérification GS1, et comment gérer les exceptions associées — le tout en utilisant Aspose.BarCode pour .NET. N’hésitez pas à explorer des options de style supplémentaires telles que la taille du code‑barres, la couleur et les marges via l’objet `Parameters.Barcode`.

Si vous rencontrez des problèmes, la documentation officielle et le forum communautaire sont d’excellentes ressources :

- [Documentation Aspose.BarCode](https://reference.aspose.com/barcode/net/)  
- [Forum de support Aspose.BarCode](https://forum.aspose.com/c/barcode/13)

## Questions fréquemment posées

### 1. Qu’est‑ce que l’encodage GS1 dans les codes‑barres ?
L’encodage GS1 est une méthode normalisée pour structurer les données (par ex., les identifiants de produit) à l’intérieur d’un code‑barres, garantissant l’interopérabilité entre détaillants, fabricants et prestataires logistiques.

### 2. Puis‑je personnaliser l’apparence des codes‑barres générés ?
Oui. Aspose.BarCode vous permet d’ajuster la taille, les couleurs, les marges et même d’ajouter du texte lisible par l’homme via les paramètres `Parameters.Barcode`.

### 3. Où puis‑je trouver des ressources supplémentaires et de la documentation pour Aspose.BarCode ?
Vous pouvez trouver une documentation complète et des exemples sur [Documentation Aspose.BarCode](https://reference.aspose.com/barcode/net/). C’est une ressource précieuse pour l’apprentissage et le dépannage.

### 4. Existe‑t‑il une version d’essai disponible pour Aspose.BarCode ?
Oui, vous pouvez obtenir une version d’essai gratuite d’Aspose.BarCode pour .NET depuis [here](https://releases.aspose.com/).

### 5. Comment puis‑je acheter une licence pour Aspose.BarCode pour .NET ?
Pour acheter une licence d’Aspose.BarCode pour .NET, rendez‑vous sur la [page d’achat](https://purchase.aspose.com/buy) du site Aspose.

---

**Dernière mise à jour :** 2026-03-07  
**Testé avec :** Aspose.BarCode 24.11 pour .NET  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
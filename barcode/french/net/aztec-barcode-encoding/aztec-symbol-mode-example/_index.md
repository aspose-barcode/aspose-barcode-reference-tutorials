---
date: 2026-05-24
description: Apprenez à créer un code-barres Aztec .NET en utilisant Aspose.BarCode
  pour .NET, en couvrant les modes de symbole Auto, FullRange, Compact et Rune, avec
  un guide étape par étape.
keywords:
- create aztec barcode .net
- aztec symbol mode
- aspose barcode .net
linktitle: Exemple de mode de symbole Aztec
schemas:
- author: Aspose
  dateModified: '2026-05-24'
  description: Learn how to create aztec barcode .net using Aspose.BarCode for .NET,
    covering Auto, FullRange, Compact, and Rune symbol modes with step‑by‑step guidance.
  headline: Create Aztec Barcode .NET with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Aztec Symbol Mode determines how the library packs data into layers, affecting
      size, capacity, and readability.
    question: What is the purpose of Aztec Symbol Mode in barcode generation?
  - answer: Yes, simply assign a new string to the `CodeText` property before calling
      `Save`.
    question: Can I change the code text for Aztec barcodes in Aspose.BarCode for
      .NET?
  - answer: Yes, you can download a free trial version of Aspose.BarCode for .NET
      [here](https://releases.aspose.com/).
    question: Is there a free trial version of Aspose.BarCode for .NET available?
  - answer: You can refer to the complete documentation for Aspose.BarCode for .NET
      [here](https://reference.aspose.com/barcode/net/).
    question: Where can I find the full documentation for Aspose.BarCode for .NET?
  - answer: You can acquire a temporary license for Aspose.BarCode for .NET by visiting
      [this link](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Créer un code-barres Aztec .NET avec Aspose.BarCode
url: /fr/net/aztec-barcode-encoding/aztec-symbol-mode-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maîtriser le mode symbole Aztec avec Aspose.BarCode pour .NET

Si vous cherchez à **create aztec barcode .net** rapidement et de manière fiable, Aspose.BarCode pour .NET vous offre une API complète qui fonctionne sur .NET Framework, .NET Core et .NET 5/6+. Dans ce tutoriel, nous explorerons les quatre modes de symbole Aztec — Auto, FullRange, Compact et Rune — en vous montrant exactement comment basculer entre eux et enregistrer le résultat sous forme d’image. À la fin, vous pourrez intégrer des codes-barres Aztec dans n’importe quelle application .NET avec seulement quelques lignes de code.

## Réponses rapides
- **Quelle bibliothèque génère les codes-barres Aztec en .NET ?** Aspose.BarCode for .NET.  
- **Combien de modes de symbole Aztec sont pris en charge ?** Quatre : Auto, FullRange, Compact et Rune.  
- **Ai-je besoin d’une licence pour le développement ?** Un essai gratuit suffit pour l’évaluation ; une licence commerciale est requise pour la production.  
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ et .NET 6+.  
- **Puis-je exporter en PNG, JPEG ou SVG ?** Oui — tout format d’image standard est pris en charge.

## Qu’est-ce que create aztec barcode .net ?
`create aztec barcode .net` désigne le processus de génération d’un code‑barres Aztec bidimensionnel à l’aide de l’API Aspose.BarCode dans un environnement .NET. L’API gère l’encodage, la sélection du mode de symbole et le rendu de l’image automatiquement, permettant aux développeurs de produire des codes‑barres de haute qualité sans se soucier des détails de bas niveau tels que les calculs de correction d’erreurs ou la manipulation des pixels.

## Pourquoi utiliser Aspose.BarCode pour les codes‑barres Aztec ?
Aspose.BarCode prend en charge **plus de 30 symbologies de codes‑barres** et peut rendre des images jusqu’à **10 000 × 10 000 px** sans charger le fichier complet en mémoire. Il traite un document de 500 pages en moins de **2 secondes** sur un serveur typique, ce qui le rend idéal pour les scénarios d’entreprise à haut débit.

## Prérequis

Avant de commencer, assurez-vous d’avoir les prérequis suivants :

- Une connaissance pratique du développement .NET.  
- Visual Studio installé sur votre machine.  
- Une copie d’Aspose.BarCode pour .NET. Vous pouvez le télécharger [ici](https://releases.aspose.com/barcode/net/). Vous pouvez également explorer d’autres produits Aspose [ici](https://releases.aspose.com/).

Maintenant que tout est prêt, plongeons dans les exemples de mode de symbole Aztec.

## Importation des espaces de noms

Tout d’abord, vous devez importer les espaces de noms nécessaires pour travailler avec Aspose.BarCode pour .NET. Ouvrez votre projet Visual Studio et ajoutez les instructions using suivantes en haut de votre fichier de code :

```csharp
using Aspose.BarCode.Generation;
```

Avec les espaces de noms en place, vous pouvez maintenant commencer à utiliser Aspose.BarCode pour .NET.

## Comment configurer le générateur de code‑barres pour les codes‑barres Aztec ?

La classe `BarcodeGenerator` est le composant principal qui crée des images de code‑barres en fonction de la symbologie sélectionnée et des options de configuration. Elle fournit une API simple pour spécifier le type de code‑barres, les données à encoder et divers paramètres de rendu avant d’enregistrer le résultat dans un fichier image.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecSymbolModeExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

Dans cette étape, nous avons configuré le générateur et fourni le texte du code à encoder.

## Comment définir le mode symbole Aztec sur Auto ?

L’énumération `AztecSymbolMode` définit les quatre modes de symbole possibles pour les codes‑barres Aztec, et l’option **Auto** permet à la bibliothèque de choisir automatiquement la taille la plus compacte tout en préservant toutes les exigences de données et de correction d’erreurs. Ce mode est idéal pour la plupart des scénarios où vous souhaitez le code‑barres le plus petit possible sans réglage manuel.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Auto;
gen.Save($"{path}AztecSymbolModeAuto.png", BarCodeImageFormat.Png);
```

Cette étape garantit que le mode symbole Aztec est déterminé automatiquement, et que l’image du code‑barres résultant est enregistrée.

## Comment forcer le mode symbole FullRange ?

Lorsque vous avez besoin de la capacité maximale de données, vous pouvez sélectionner la valeur **FullRange** de l’énumération `AztecSymbolMode`. Ce mode désactive la réduction automatique de la taille, permettant au code‑barres de stocker l’ensemble complet des caractères et d’atteindre la densité d’information la plus élevée possible, ce qui est utile pour de grands ensembles de données.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
gen.Save($"{path}AztecSymbolModeFullRange.png", BarCodeImageFormat.Png);
```

Cela créera un code‑barres avec le mode symbole Aztec FullRange.

## Comment générer un code‑barres Aztec Compact ?

La valeur **Compact** de l’énumération `AztecSymbolMode` produit un code‑barres plus petit en réduisant le nombre de couches utilisées dans la matrice. Cela donne une image plus efficace en termes d’espace, la rendant adaptée aux applications avec une zone d’affichage limitée comme les écrans mobiles ou les petites étiquettes.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Compact;
gen.Save($"{path}AztecSymbolModeCompact.png", BarCodeImageFormat.Png);
```

Cette étape configure le code‑barres pour être généré avec le mode symbole Aztec Compact.

## Comment créer un code‑barres Aztec Rune ?

Le mode **Rune** est une variante spécialisée de la symbologie Aztec qui encode les données numériques à l’aide d’un jeu de caractères personnalisé, offrant un style visuel distinct tout en conservant la même robustesse de correction d’erreurs que les autres modes. Il est utile lorsque vous avez besoin d’un code‑barres qui met l’accent sur les informations numériques.

```csharp
gen.CodeText = "123"; // Change the code text if needed
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Rune;
gen.Save($"{path}AztecSymbolModeRune.png", BarCodeImageFormat.Png);
```

Cette étape change le texte du code en "123" et génère un code‑barres avec le mode symbole Aztec Rune.

## Problèmes courants et solutions

- **Image non enregistrée** – Assurez-vous que le dossier de sortie existe et que l’application dispose des permissions d’écriture.  
- **Taille de symbole inattendue** – Vérifiez que vous n’avez pas remplacé `EncodeMode` ailleurs dans votre code.  
- **Exception de licence** – Une version d’essai ajoute un filigrane ; appliquez une licence valide pour le supprimer.

## Questions fréquemment posées

**Q : Quel est le but du mode symbole Aztec dans la génération de codes‑barres ?**  
R : Le mode symbole Aztec détermine comment la bibliothèque regroupe les données en couches, affectant la taille, la capacité et la lisibilité.

**Q : Puis-je modifier le texte du code pour les codes‑barres Aztec dans Aspose.BarCode pour .NET ?**  
R : Oui, il suffit d’assigner une nouvelle chaîne à la propriété `CodeText` avant d’appeler `Save`.

**Q : Existe-t-il une version d’essai gratuite d’Aspose.BarCode pour .NET ?**  
R : Oui, vous pouvez télécharger une version d’essai gratuite d’Aspose.BarCode pour .NET [ici](https://releases.aspose.com/).

**Q : Où puis‑je trouver la documentation complète d’Aspose.BarCode pour .NET ?**  
R : Vous pouvez consulter la documentation complète d’Aspose.BarCode pour .NET [ici](https://reference.aspose.com/barcode/net/).

**Q : Comment obtenir une licence temporaire pour Aspose.BarCode pour .NET ?**  
R : Vous pouvez obtenir une licence temporaire pour Aspose.BarCode pour .NET en visitant [ce lien](https://purchase.aspose.com/temporary-license/).

## Conclusion

Dans ce tutoriel, nous avons exploré comment **create aztec barcode .net** à l’aide d’Aspose.BarCode, en couvrant les modes de symbole Auto, FullRange, Compact et Rune. Vous disposez maintenant d’une base solide pour intégrer des codes‑barres Aztec polyvalents dans n’importe quelle application .NET, qu’elle s’exécute sur un ordinateur de bureau, un serveur web ou un service cloud.

Si vous avez des questions ou avez besoin d’aide supplémentaire, n’hésitez pas à contacter la communauté Aspose.BarCode sur leur [forum de support](https://forum.aspose.com/c/barcode/13).

---

**Dernière mise à jour :** 2026-05-24  
**Testé avec :** Aspose.BarCode 24.11 pour .NET  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriels associés

- [Encodage du texte du code Aztec avec Aspose.BarCode pour .NET](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)
- [Encodage des octets Aztec avec le générateur de code‑barres .net](/barcode/net/aztec-barcode-encoding/aztec-bytes-encoding/)
- [Comment créer un code‑barres Aztec avec correction d’erreurs en .NET](/barcode/net/aztec-barcode-encoding/aztec-error-level-example/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
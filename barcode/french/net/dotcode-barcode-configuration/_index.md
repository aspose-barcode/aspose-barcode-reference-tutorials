---
date: 2026-06-14
description: Apprenez à générer des codes-barres DotCode avec Aspose.BarCode for .NET,
  en couvrant le rapport d'aspect, les modes d'encodage, le texte étendu et l'initialisation
  du lecteur.
keywords:
- how to generate dotcode
- dotcode barcode configuration
- aspose barcode .net
linktitle: Comment générer des codes-barres DotCode – Guide de configuration
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to generate DotCode barcodes with Aspose.BarCode for .NET,
    covering aspect ratio, encoding modes, extended text, and reader initialization.
  headline: How to Generate DotCode Barcodes – Configuration Guide
  type: TechArticle
- questions:
  - answer: Yes, set `BarCodeImageFormat = BarCodeImageFormat.Svg` on the generator
      to receive a scalable vector output.
    question: Can I generate DotCode barcodes in SVG format?
  - answer: Aspose.BarCode does not support direct logo embedding for DotCode, but
      you can overlay an image after generation using standard graphics libraries.
    question: Is it possible to embed a logo inside a DotCode symbol?
  - answer: The symbology includes built‑in Reed‑Solomon error correction; increasing
      rows/columns automatically raises the correction level.
    question: How does error correction work for DotCode?
  - answer: No, the same `BarCodeReader` can extract DotCode from PDF pages, images,
      or streams without additional tools.
    question: Do I need a separate library to read DotCode from a PDF?
  - answer: Up to **1 200** numeric or **800** alphanumeric characters, depending
      on the chosen rows/columns configuration.
    question: What is the maximum data size for a single DotCode symbol?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Comment générer des codes-barres DotCode – Guide de configuration
url: /fr/net/dotcode-barcode-configuration/
weight: 32
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer des codes-barres DotCode – Guide de configuration

## Introduction
**Comment générer DotCode** les codes-barres rapidement et de manière fiable est une exigence courante pour les développeurs créant des solutions d’inventaire, de suivi ou de numérisation mobile. Dans ce tutoriel, nous passerons en revue chaque option de configuration offerte par Aspose.BarCode pour .NET pour les symboles DotCode — ajustements du rapport d’aspect, modes d’encodage Auto et Bytes, gestion du texte de code étendu, initialisation du lecteur, disposition des lignes/colonnes et mode d’ajout structuré. À la fin, vous serez capable de produire des images DotCode parfaitement dimensionnées et à haute densité qui respectent les normes de l’industrie et s’intègrent parfaitement à toute application .NET.

## Réponses rapides
- **Quelle est la classe principale pour créer un code-barres DotCode ?** `BarcodeGenerator` avec `EncodeTypes.DotCode`.
- **Quelle propriété contrôle le rapport d’aspect ?** `BarCodeImageAspectRatio`.
- **Puis-je basculer entre les encodages Auto et Bytes ?** Oui, via la propriété `EncodeMode`.
- **Un lecteur séparé est‑il requis pour DotCode ?** Non, le même `BarcodeGenerator` peut décoder lorsqu’on appelle `ReadBarcode`.
- **Quelles versions de .NET sont prises en charge ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Comment générer des codes-barres DotCode avec Aspose.BarCode pour .NET ?
`BarcodeGenerator` est la classe principale dans Aspose.BarCode pour créer des images de code‑barres. Chargez le `BarcodeGenerator` avec `EncodeTypes.DotCode`, définissez les propriétés souhaitées (rapport d’aspect, mode d’encodage, lignes/colonnes, etc.) et appelez `GenerateBarCodeImage()` — la bibliothèque renvoie un `System.Drawing.Image` prêt à l’emploi ou un tableau d’octets. Ce flux de travail en une seule étape gère tous les détails d’encodage de bas niveau, prend en charge les formats de sortie tels que PNG, JPEG et SVG, et peut rendre des images jusqu’à 10 000 × 10 000 px sans consommer une mémoire excessive.

## Qu’est‑ce qu’un code-barres DotCode ?
Un code-barres DotCode est une symbologie 2D haute densité, de forme carrée, qui stocke jusqu’à 1 200 caractères numériques ou 800 caractères alphanumériques dans une matrice compacte de points. Elle est optimisée pour l’étiquetage de petits colis et la numérisation mobile, offrant des taux de lecture rapides même avec des caméras basse résolution.

## Pourquoi utiliser DotCode avec Aspose.BarCode ?
Aspose.BarCode prend en charge **plus de 20** types de codes-barres 2D, y compris DotCode, et peut traiter des fichiers de plus de **200 Mo** sans charger l’image entière en mémoire. La bibliothèque garantit **99,9 %** de précision de lecture avec les caméras de smartphones standard et fournit des niveaux de correction d’erreurs intégrés pour minimiser les échecs de lecture.

## Prérequis
- .NET Framework 4.5 ou supérieur, ou .NET Core 3.1 / .NET 5+.
- Aspose.BarCode pour .NET (dernière version recommandée).
- Une clé de licence temporaire ou complète (l’essai fonctionne pour le développement).

## Personnalisation du rapport d’aspect DotCode
Le **rapport d’aspect** détermine comment la matrice DotCode apparaît étirée ou comprimée. Utilisez la propriété `BarCodeImageAspectRatio` pour définir une valeur entre **0,5** (plus haut) et **2,0** (plus large). Un ratio de **1,0** donne un symbole parfaitement carré, qui est la valeur par défaut et fonctionne le mieux pour la plupart des lecteurs.

> **Conseil :** Lors de l’impression sur des étiquettes étroites, un ratio de **0,75** améliore souvent la lisibilité sans sacrifier la capacité de données.

## Mode d’encodage DotCode (Auto)
En mode **Auto**, la bibliothèque analyse la chaîne d’entrée et sélectionne automatiquement l’encodage le plus efficace (numérique, alphanumérique ou octet). Cela maximise la densité des données et réduit la taille globale du symbole.

> **Réponse directe :** Définissez `EncodeMode = EncodeModes.Auto` sur le `BarcodeGenerator` pour laisser Aspose.BarCode choisir l’encodage optimal pour vos données, garantissant le DotCode le plus petit possible tout en préservant tous les caractères.

## Mode d’encodage DotCode (Bytes)
Lorsque vous devez stocker des données binaires ou des tableaux d’octets pré‑encodés, choisissez le mode **Bytes**. Cela force le générateur à traiter l’entrée comme des octets bruts, contournant la détection automatique du jeu de caractères.

> **Réponse directe :** Utilisez `EncodeMode = EncodeModes.Bytes` et fournissez une charge utile `byte[]` pour intégrer des informations binaires telles que des identifiants chiffrés ou des fichiers compressés directement dans le symbole DotCode.

## Configuration du texte de code étendu DotCode
Le texte de code étendu vous permet d’attacher des informations supplémentaires qui ne font pas partie de la charge utile principale mais peuvent être affichées à côté du code‑barres dans les rapports ou les interfaces graphiques. Définissez la propriété `ExtendedCodeText` sur n’importe quelle chaîne (jusqu’à **256** caractères) et choisissez une police via `ExtendedCodeTextFont`.

> **Astuce pro :** Associez le texte étendu à une taille de police plus petite (par ex., 8 pt) pour réduire l’empreinte visuelle tout en fournissant un contexte lisible par l’homme.

## Initialisation du lecteur DotCode
`BarCodeReader` est la classe utilisée pour décoder les codes‑barres à partir d’images ou de flux. Lire une image DotCode est aussi simple que la génération. Instanciez un `BarCodeReader` avec le flux d’image et spécifiez `EncodeTypes.DotCode`. Appelez `ReadBarCode()` pour récupérer la chaîne décodée.

> **Réponse directe :** `using (var reader = new BarCodeReader(imageStream, DecodeType.DotCode)) { if (reader.ReadBarCode()) { string data = reader.GetCodeText(); } }` – ce bloc unique décode le symbole sans dépendances externes.

## Configuration des lignes et colonnes DotCode
DotCode permet un contrôle explicite du nombre de lignes et de colonnes, ce qui influence la taille du symbole et la capacité de correction d’erreurs. Utilisez les propriétés `Rows` et `Columns` pour définir des valeurs entre **10** et **144**. Des matrices plus grandes augmentent la capacité de données et la robustesse.

> **Bonne pratique :** Pour les étiquettes d’inventaire qui doivent résister à des manipulations brutales, configurez **Rows = 64** et **Columns = 64** afin d’ajouter une redondance supplémentaire.

## Configuration du mode Structured Append DotCode
Structured Append permet de diviser une charge utile importante en plusieurs symboles DotCode qui peuvent être lus séquentiellement. Définissez `StructuredAppend = true` et spécifiez `StructuredAppendCount` et `StructuredAppendIndex` pour chaque partie.

> **Réponse directe :** Activez `StructuredAppend` sur chaque `BarcodeGenerator`, attribuez un indice unique (commençant à 1) et définissez le nombre total ; la bibliothèque intégrera automatiquement les informations de liaison nécessaires.

## Problèmes courants et solutions
- **Code-barres illisible sur des écrans basse résolution :** Augmentez la propriété `Resolution` à au moins **300 dpi** avant la génération.
- **Avertissements de troncature de données :** Vérifiez que la longueur d’entrée ne dépasse pas le maximum pour les lignes/colonnes sélectionnées ; ajustez la taille ou passez au mode Bytes si nécessaire.
- **Expiration de licence pendant le développement :** Utilisez une licence temporaire obtenue sur le portail Aspose ; remplacez‑la par une clé permanente avant le déploiement en production.

## Questions fréquemment posées

**Q : Puis‑je générer des codes-barres DotCode au format SVG ?**  
R : Oui, définissez `BarCodeImageFormat = BarCodeImageFormat.Svg` sur le générateur pour obtenir une sortie vectorielle évolutive.

**Q : Est‑il possible d’intégrer un logo à l’intérieur d’un symbole DotCode ?**  
R : Aspose.BarCode ne prend pas en charge l’intégration directe de logo pour DotCode, mais vous pouvez superposer une image après la génération à l’aide de bibliothèques graphiques standard.

**Q : Comment fonctionne la correction d’erreurs pour DotCode ?**  
R : La symbologie inclut une correction d’erreurs Reed‑Solomon intégrée ; augmenter les lignes/colonnes élève automatiquement le niveau de correction.

**Q : Ai‑je besoin d’une bibliothèque séparée pour lire DotCode depuis un PDF ?**  
R : Non, le même `BarCodeReader` peut extraire DotCode des pages PDF, des images ou des flux sans outils supplémentaires.

**Q : Quelle est la taille maximale des données pour un seul symbole DotCode ?**  
R : Jusqu’à **1 200** caractères numériques ou **800** caractères alphanumériques, selon la configuration des lignes/colonnes choisie.

---

**Dernière mise à jour :** 2026-06-14  
**Testé avec :** Aspose.BarCode 24.11 for .NET  
**Auteur :** Aspose  

## Tutoriels de configuration du code-barres DotCode
### [Personnaliser le rapport d’aspect DotCode](./dotcode-aspect-ratio-customization/)
Apprenez à personnaliser le rapport d’aspect du code-barres DotCode avec Aspose.BarCode pour .NET. Créez des codes-barres sur mesure pour vos applications sans effort.
### [Mode d’encodage DotCode (Auto)](./dotcode-encoding-mode-auto/)
Explorez le mode d’encodage DotCode (Auto) dans Aspose.BarCode pour .NET, un outil puissant pour la génération de codes-barres. Apprenez à générer des codes-barres DotCode étape par étape. Consultez la documentation, téléchargez la bibliothèque et obtenez des licences temporaires.
### [Mode d’encodage DotCode (Bytes)](./dotcode-encoding-mode-bytes/)
Apprenez l’encodage DotCode avec Aspose.BarCode pour .NET : guide étape par étape pour générer des codes-barres.
### [Configuration du texte de code étendu DotCode](./dotcode-extended-code-text-configuration/)
Générez facilement la configuration du texte de code étendu DotCode avec Aspose.BarCode pour .NET. Suivez notre guide étape par étape pour une création efficace de codes-barres.
### [Initialisation du lecteur DotCode](./dotcode-reader-initialization/)
Apprenez à initialiser le lecteur DotCode avec Aspose.BarCode pour .NET. Créez des codes-barres DotCode facilement pour diverses applications.
### [Configuration des lignes et colonnes DotCode](./dotcode-rows-columns-configuration/)
Apprenez à configurer les lignes et colonnes DotCode avec Aspose.BarCode pour .NET. Générez des codes-barres 2D précis et personnalisables sans effort.
### [Configuration du mode Structured Append DotCode](./dotcode-structured-append-mode-configuration/)
Apprenez à configurer le mode Structured Append DotCode avec Aspose.BarCode pour .NET et créez des codes-barres efficaces.

## Tutoriels associés

- [Personnaliser le rapport d’aspect DotCode avec Aspose.BarCode pour .NET](/barcode/net/dotcode-barcode-configuration/dotcode-aspect-ratio-customization/)
- [Configuration du texte de code étendu DotCode avec Aspose.BarCode pour .NET](/barcode/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Mode d’encodage DotCode (Auto) dans Aspose.BarCode pour .NET](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}
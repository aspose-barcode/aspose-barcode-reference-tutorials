---
date: 2026-06-29
description: Apprenez à générer un code-barres Codabar avec somme de contrôle en utilisant
  Aspose.BarCode pour .NET. Guide étape par étape couvrant les modes de somme de contrôle
  Mod10 et Mod16.
keywords:
- generate codabar barcode
- aspose barcode .net
- codabar checksum
- mod10 checksum
- mod16 checksum
linktitle: Calcul de la somme de contrôle Codabar
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to generate Codabar barcode with checksum using Aspose.BarCode
    for .NET. Step‑by‑step guide covering Mod10 and Mod16 checksum modes.
  headline: Generate Codabar barcode with checksum (Aspose.BarCode .NET)
  type: TechArticle
- questions:
  - answer: Absolutely. Mod16 provides stronger error detection, which is beneficial
      for high‑throughput environments like libraries.
    question: Can I use the Mod16 checksum for library book barcodes?
  - answer: The additional digit adds negligible processing time; most scanners handle
      it without noticeable delay.
    question: Does enabling checksum affect scanning speed?
  - answer: After generating the barcode, recompute the checksum using the same `CodabarChecksumMode`
      and compare it to the last character of the encoded string.
    question: How do I verify the checksum programmatically?
  - answer: Yes. Use the `BarcodeGenerator` appearance settings (e.g., `BarHeight`,
      `ForeColor`) to style the entire barcode, including the checksum digit.
    question: Is it possible to customize the appearance of the checksum digit?
  - answer: Instantiate a single `BarcodeGenerator`, update the `CodeText` property
      for each iteration, and call `Save` with a unique filename each time.
    question: What if I need to generate multiple barcodes in a loop?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Générer un code-barres Codabar avec somme de contrôle (Aspose.BarCode .NET)
url: /fr/net/codabar-encoding-and-checksum/codabar-checksum-calculation/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Générer un code-barres Codabar avec somme de contrôle (Aspose.BarCode .NET)

Codabar est une symbologie de code-barres linéaire largement adoptée dans la logistique, les bibliothèques et le secteur de la santé. **Générer un code-barres Codabar avec somme de contrôle** améliore considérablement l'intégrité des données en détectant les erreurs de transcription avant qu'elles ne posent problème. Dans ce tutoriel, vous apprendrez comment ajouter une somme de contrôle lors de la *génération d'un code-barres Codabar* avec Aspose.BarCode pour .NET, et vous verrez les deux modes de somme de contrôle Mod10 et Mod16 en action.

## Réponses rapides
- **Que signifie « ajouter une somme de contrôle » pour Codabar ?** Il ajoute un chiffre de détection d'erreur qui valide les données encodées.  
- **Quels modes de somme de contrôle sont pris en charge ?** Mod10 (standard) et Mod16 (précision supérieure).  
- **Ai-je besoin d'une licence pour utiliser cette fonctionnalité ?** Oui – une licence valide d'Aspose.BarCode pour .NET est requise en production.  
- **Quelles versions de .NET sont compatibles ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Où les images générées sont‑elles enregistrées ?** Dans le dossier que vous spécifiez dans la variable `path`.

## Comment générer un code-barres Codabar avec somme de contrôle ?

Chargez vos données, activez la somme de contrôle, choisissez `CodabarChecksumMode.Mod10` ou `CodabarChecksumMode.Mod16`, puis appelez `Save`. Aspose.BarCode gère le calcul et ajoute automatiquement le chiffre de somme de contrôle, de sorte que vous obtenez une image prête à être scannée en un seul appel de méthode. Vous pouvez également spécifier le dossier de sortie, le nom du fichier et le format d'image (par ex., PNG) lors de l'enregistrement.

## Pourquoi ajouter une somme de contrôle au code-barres Codabar ?

L'ajout d'une somme de contrôle réduit les erreurs d'un seul caractère de **jusqu'à 99,9 %** et détecte la plupart des erreurs de transposition, ce qui est essentiel pour des secteurs comme les banques de sang où une erreur d'un seul chiffre pourrait avoir de graves conséquences. Cela permet également de répondre aux exigences réglementaires de nombreuses normes logistiques.

## Prérequis

1. **Aspose.BarCode for .NET** – téléchargez la dernière version depuis [ici](https://releases.aspose.com/barcode/net/).  
2. **Environnement de développement C#** – Visual Studio, VS Code, ou tout IDE qui prend en charge .NET.

Maintenant que tout est configuré, parcourons l'implémentation.

## Importer les espaces de noms

La classe `BarcodeGenerator` se trouve dans l'espace de noms `Aspose.BarCode.Generation`. Importez‑la en haut de votre fichier :

`using Aspose.BarCode.Generation;`

## Qu'est‑ce que la classe BarcodeGenerator ?

La classe `BarcodeGenerator` est l'objet principal d'Aspose.BarCode qui crée, configure et rend une image de code‑barres. Elle regroupe tous les paramètres spécifiques aux codes‑barres tels que la symbologie, le texte, la taille et les options de somme de contrôle, vous permettant de générer des images avec un seul appel `Save`. En modifiant sa propriété `Parameters`, vous pouvez personnaliser l'apparence, le mode d'encodage et les fonctionnalités de détection d'erreurs pour tout type de code‑barres pris en charge.

## Étape 1 : Initialiser le générateur de code‑barres

Créez une instance de `BarcodeGenerator`, spécifiez la symbologie Codabar et fournissez les données que vous souhaitez encoder. Remplacez `"Your Directory Path"` par le dossier réel où vous souhaitez enregistrer les images.

`var generator = new BarcodeGenerator(EncodeTypes.Codabar, "A123456A");`  
`string path = @"Your Directory Path";`

## Étape 2 : Générer un code‑barres Codabar **sans** somme de contrôle

Si un système hérité attend un code‑barres simple, définissez l'option de somme de contrôle sur `Default`. Cela désactive tout chiffre supplémentaire.

`generator.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Default;`  
`generator.Save($"{path}\\Codabar_NoChecksum.png", BarCodeImageFormat.Png);`

## Étape 3 : Générer un code‑barres Codabar avec somme de contrôle **Mod10**

Activez la somme de contrôle et sélectionnez l'algorithme Mod10, qui est le mode le plus courant pour Codabar.

`generator.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;`  
`generator.Parameters.Barcode.CodabarChecksumMode = CodabarChecksumMode.Mod10;`  
`generator.Save($"{path}\\Codabar_Mod10.png", BarCodeImageFormat.Png);`

## Étape 4 : Générer un code‑barres Codabar avec somme de contrôle **Mod16**

Pour des scénarios de détection d'erreurs plus élevés, passez à Mod16. Le changement se limite à une seule affectation de propriété.

`generator.Parameters.Barcode.CodabarChecksumMode = CodabarChecksumMode.Mod16;`  
`generator.Save($"{path}\\Codabar_Mod16.png", BarCodeImageFormat.Png);`

Avec ces quatre étapes simples, vous avez appris **comment générer un code‑barres Codabar** avec somme de contrôle et comment basculer entre les modes Mod10 et Mod16 en utilisant Aspose.BarCode pour .NET.

## Problèmes courants et solutions

| Problème | Raison | Solution |
|----------|--------|----------|
| L'image générée est vide | `path` pointe vers un dossier inexistant | Assurez‑vous que le répertoire existe ou appelez `Directory.CreateDirectory(path)` avant d'enregistrer |
| Somme de contrôle non appliquée | `IsChecksumEnabled` laissé à `Default` | Définissez `IsChecksumEnabled = EnableChecksum.Yes` avant d'enregistrer |
| Mode de somme de contrôle incorrect | Utilisation d'une mauvaise valeur d'énumération | Utilisez `CodabarChecksumMode.Mod10` ou `CodabarChecksumMode.Mod16` selon les besoins |

## Questions fréquentes

**Q : Puis‑je utiliser la somme de contrôle Mod16 pour les codes‑barres de livres de bibliothèque ?**  
R : Absolument. Mod16 offre une détection d'erreurs plus forte, ce qui est bénéfique pour les environnements à haut débit comme les bibliothèques.

**Q : L'activation de la somme de contrôle affecte‑t‑elle la vitesse de lecture ?**  
R : Le chiffre supplémentaire ajoute un temps de traitement négligeable ; la plupart des lecteurs le gèrent sans retard perceptible.

**Q : Comment vérifier la somme de contrôle par programme ?**  
R : Après avoir généré le code‑barres, recalculer la somme de contrôle en utilisant le même `CodabarChecksumMode` et la comparer au dernier caractère de la chaîne encodée.

**Q : Est‑il possible de personnaliser l'apparence du chiffre de somme de contrôle ?**  
R : Oui. Utilisez les paramètres d'apparence du `BarcodeGenerator` (par ex., `BarHeight`, `ForeColor`) pour styliser l'ensemble du code‑barres, y compris le chiffre de somme de contrôle.

**Q : Que faire si je dois générer plusieurs codes‑barres dans une boucle ?**  
R : Instanciez un seul `BarcodeGenerator`, mettez à jour la propriété `CodeText` à chaque itération, et appelez `Save` avec un nom de fichier unique à chaque fois.

Si vous rencontrez des difficultés, la communauté Aspose.BarCode est prête à aider sur le [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**Dernière mise à jour :** 2026-06-29  
**Testé avec :** Aspose.BarCode 24.11 for .NET  
**Auteur :** Aspose  

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.BarCode.Generation;
```

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarChecksum:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Default;
gen.Save($"{path}CodabarChecksumNone.png", BarCodeImageFormat.Png);
```

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Parameters.Barcode.Codabar.CodabarChecksumMode = CodabarChecksumMode.Mod10;
gen.Save($"{path}CodabarChecksumMod10.png", BarCodeImageFormat.Png);
```

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Parameters.Barcode.Codabar.CodabarChecksumMode = CodabarChecksumMode.Mod16;
gen.Save($"{path}CodabarChecksumMod16.png", BarCodeImageFormat.Png);
```

## Tutoriels associés

- [Générer un code‑barres Codabar avec caractères de début/fin dans Aspose.BarCode pour .NET](/barcode/net/codabar-encoding-and-checksum/codabar-start-stop-characters/)
- [Tutoriels et exemples complets d'Aspose.BarCode pour .NET](/barcode/net/)
- [Générer un code‑barres DataMatrix – Guide pro avec Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
---
category: general
date: 2026-08-22
description: Apprenez à générer un code‑barres DataMatrix en Python et à encoder du
  texte russe avec Aspose.BarCode – guide étape par étape.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate DataMatrix barcode
- encode Russian text
language: fr
lastmod: 2026-08-22
og_description: Générez un code‑barres DataMatrix en Python et encodez du texte russe
  avec Aspose.BarCode. Suivez l’exemple complet et exécutez‑le immédiatement.
og_image_alt: Python script that generate DataMatrix barcode with encoded Russian
  text
og_title: Générer un code‑barres DataMatrix en Python – tutoriel complet Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  headline: How to generate DataMatrix barcode in Python with Aspose.BarCode
  type: TechArticle
- description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  name: How to generate DataMatrix barcode in Python with Aspose.BarCode
  steps:
  - name: '**ABC123** – the plain identifier.'
    text: '**ABC123** – the plain identifier.'
  - name: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
    text: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
  - name: Open the PNG file in an image viewer.
    text: Open the PNG file in an image viewer.
  - name: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
    text: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
  - name: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
    text: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
  type: HowTo
tags:
- Aspose.BarCode
- Python
- barcode generation
title: Comment générer un code‑barres DataMatrix en Python avec Aspose.BarCode
url: /fr/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer un code‑barres DataMatrix en Python avec Aspose.BarCode

Si vous devez **générer un code‑barres DataMatrix** en Python tout en **encodant du texte russe**, ce guide vous montre les étapes exactes. Vous verrez un exemple complet et exécutable qui construit un texte de code étendu, configure le code‑barres et enregistre l’image dans un seul script.

Créer des codes‑barres contenant des caractères non‑ASCII soulève souvent des questions sur les jeux de caractères et l’encodage des données. En utilisant `ExtCodetextBuilder` d’Aspose.BarCode, vous pouvez intégrer en toute sécurité du texte UTF‑8 tel que des caractères cyrilliques dans un symbole DataMatrix. Le résultat fonctionne avec n’importe quel lecteur compatible avec la norme DataMatrix.

Dans ce tutoriel, vous allez :

* Installer le package Aspose.BarCode requis.  
* Construire un texte de code étendu qui mélange des données simples et du texte russe.  
* **Générer un code‑barres DataMatrix** avec la chaîne étendue.  
* Ajuster les paramètres du code‑barres comme la taille du module.  
* Enregistrer le code‑barres sous forme de fichier PNG.  

Aucun service externe n’est nécessaire ; tout s’exécute localement sur votre machine.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

* Python 3.8 ou une version plus récente installé.  
* Une licence active d’Aspose.BarCode for Python (une version d’essai gratuite suffit pour le développement).  
* Une connaissance de base du scripting Python.  

Vous pouvez installer la bibliothèque Aspose.BarCode via pip :

```bash
pip install aspose-barcode
```

## Étape 1 : Construire une chaîne de texte de code étendue

La première tâche consiste à créer une seule chaîne contenant à la fois l’identifiant produit simple et la phrase russe. `ExtCodetextBuilder` vous permet de concaténer différentes parties de texte de code tout en préservant leurs informations d’encodage.

```python
# Import required Aspose.BarCode classes
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

# Initialize the extended codetext builder
builder = ExtCodetextBuilder()

# Add a plain ASCII identifier – this could be a SKU, part number, etc.
builder.add_plain_codetext("ABC123")

# Add Russian text using ECI (Extended Channel Interpretation) encoding.
# The eci_encoding value 3 corresponds to UTF‑8.
builder.add_eci_codetext(eci_encoding=3, codetext="Привет")

# Retrieve the combined string that Aspose.BarCode will use.
extended_text = builder.get_extended_codetext()
print("Generated extended codetext:", extended_text)
```

**Pourquoi cette étape est importante** – Les symboles DataMatrix stockent des octets bruts. Lorsque vous devez mélanger des alphabets, vous devez indiquer à l’encodeur quel jeu de caractères s’applique à chaque segment. La méthode `add_eci_codetext` insère un indicateur ECI avant le texte russe, garantissant que les lecteurs interprètent les octets comme UTF‑8. Sans ECI, les caractères cyrilliques apparaîtraient comme des données corrompues.

## Étape 2 : Créer un générateur de code‑barres DataMatrix

Une fois le texte de code étendu prêt, créez une instance de `BarcodeGenerator` en spécifiant le type `EncodeTypes.DATA_MATRIX`.

```python
# Create a DataMatrix barcode generator using the extended codetext
generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)
```

**Pourquoi DataMatrix ?** – DataMatrix est un code‑barres bidimensionnel qui peut stocker jusqu’à 2 335 caractères alphanumériques ou 1 556 octets. Il est idéal pour les petits objets, les pièces industrielles et les situations où vous devez intégrer du texte multilingue.

## Étape 3 : (Facultatif) Configurer les paramètres du code‑barres

Aspose.BarCode expose de nombreux paramètres. Pour la plupart des cas d’usage, les paramètres par défaut produisent un symbole lisible. Cependant, vous pouvez vouloir contrôler la taille de chaque module (le plus petit carré de la matrice) afin de répondre aux exigences d’impression.

```python
# Set the module (pixel) size to 2.5 points – adjust as needed for your printer DPI
generator.parameters.barcode.x_dimension = 2.5
```

D’autres paramètres utiles incluent le niveau de correction d’erreurs, la marge et la couleur d’arrière‑plan. Ajustez‑les uniquement si votre environnement de lecture cible impose des tolérances spécifiques.

## Étape 4 : Enregistrer l’image du code‑barres

Enfin, écrivez le code‑barres dans un fichier. La méthode `save` prend en charge PNG, JPEG, BMP et plusieurs formats vectoriels.

```python
# Save the barcode image to the desired folder
output_path = "YOUR_DIRECTORY/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

Lorsque vous ouvrirez `extended_codetext.png`, vous verrez un symbole DataMatrix net. Le scanner le décodera en deux parties :

1. **ABC123** – l’identifiant simple.  
2. **Привет** – le salut russe, correctement décodé en UTF‑8.

## Exemple complet et exécutable

Voici le script complet que vous pouvez copier‑coller dans un fichier nommé `generate_datamatrix.py`. Remplacez `YOUR_DIRECTORY` par un dossier existant sur votre système.

```python
# generate_datamatrix.py
# -------------------------------------------------
# Complete example: generate DataMatrix barcode and encode Russian text
# -------------------------------------------------

import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

def main():
    # Step 1: Build extended codetext
    builder = ExtCodetextBuilder()
    builder.add_plain_codetext("ABC123")
    builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_text = builder.get_extended_codetext()
    print("Generated extended codetext:", extended_text)

    # Step 2: Create DataMatrix generator
    generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)

    # Step 3: Optional parameters (adjust module size if needed)
    generator.parameters.barcode.x_dimension = 2.5

    # Step 4: Save the image
    output_path = "YOUR_DIRECTORY/extended_codetext.png"
    generator.save(output_path)
    print(f"Barcode saved as {output_path}")

if __name__ == "__main__":
    main()
```

Exécutez le script depuis la ligne de commande :

```bash
python generate_datamatrix.py
```

Vous devriez voir une sortie console similaire à :

```
Generated extended codetext: (ECI:3)ПриветABC123
Barcode saved as YOUR_DIRECTORY/extended_codetext.png
```

## Vérifier le résultat

Pour confirmer que le code‑barres encode correctement la phrase russe :

1. Ouvrez le fichier PNG dans un visualiseur d’images.  
2. Utilisez n’importe quelle application de lecture DataMatrix (de nombreuses applications mobiles le supportent) ou un scanner matériel.  
3. La chaîne décodée doit afficher `ABC123Привет` (ou les deux parties séparées selon l’interface du scanner).  

Si les caractères russes apparaissent comme du texte illisible, vérifiez que le scanner prend en charge l’ECI UTF‑8. La plupart des lecteurs modernes le font, mais les appareils plus anciens peuvent nécessiter une configuration explicite.

## Pièges courants et comment les éviter

| Problème | Cause | Solution |
|----------|-------|----------|
| Texte cyrillique corrompu | Indicateur ECI manquant | Utilisez `add_eci_codetext` avec `eci_encoding=3`. |
| Code‑barres trop petit pour l’imprimante | Taille de module par défaut trop fine pour une faible résolution DPI | Augmentez `x_dimension` (par ex., `3.0` ou `4.0`). |
| Fichier non enregistré | Chemin du répertoire invalide | Assurez‑vous que `YOUR_DIRECTORY` existe et est accessible en écriture. |
| Le scanner ne lit pas | Densité de données excessive | Réduisez la quantité de données encodées ou augmentez le niveau de correction d’erreurs (`generator.parameters.barcode.error_correction_level`). |

## Étendre l’exemple

Vous pouvez adapter ce modèle à d’autres langues ou types de données :

* **Encoder du texte japonais ou arabe** – changez `eci_encoding` à la valeur appropriée (par ex., 5 pour ISO‑8859‑5, 6 pour ISO‑8859‑7).  
* **Ajouter plusieurs segments ECI** – appelez `add_eci_codetext` plusieurs fois, chacun avec son propre encodage.  
* **Créer un QR code à la place** – remplacez `EncodeTypes.DATA_MATRIX` par `EncodeTypes.QR`.  

Toutes les autres étapes restent identiques car `ExtCodetextBuilder` abstrait la gestion bas‑niveau des octets.

## Conclusion

Vous savez maintenant comment **générer un code‑barres DataMatrix** en Python et **encoder du texte russe** en utilisant la fonction de texte de code étendu d’Aspose.BarCode. Le script complet gère la négociation du jeu de caractères, la création du code‑barres et la génération de l’image avec seulement quelques lignes de code.

Ensuite, explorez d’autres symbologies de code‑barres (PDF417, Aztec) ou intégrez le générateur dans un service web qui renvoie des images PNG à la demande. Les mêmes principes—construction d’un texte de code étendu et sélection du `EncodeTypes` approprié—s’appliquent à l’ensemble de la suite Aspose.BarCode.

Bon codage, et profitez de la puissance de la génération multilingue de codes‑barres !

## Que devez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)  
- [Generate a DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET (C#)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)  
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
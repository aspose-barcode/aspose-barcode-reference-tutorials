---
category: general
date: 2026-07-15
description: Comment générer une image de code QR en Python avec Aspose.Barcode. Apprenez
  la création de code QR étape par étape avec un texte codé étendu, l’encodage ECI
  et la prise en charge Unicode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate qr code image
- Aspose.Barcode QR
- Python barcode generation
- extended codetext builder
- ECI encoding in QR
- QR code with Unicode
language: fr
lastmod: 2026-07-15
og_description: Comment générer une image de code QR en Python avec Aspose.Barcode.
  Ce guide vous explique comment créer des codes QR en utilisant un texte de code
  étendu, l’encodage ECI et les caractères Unicode.
og_image_alt: Python script generating a QR code image with extended codetext via
  Aspose.Barcode
og_title: Comment générer une image de code QR en Python – Tutoriel complet Aspose.Barcode
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: How to generate QR code image in Python using Aspose.Barcode. Learn
    step‑by‑step QR code creation with extended codetext, ECI encoding, and Unicode
    support.
  headline: How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide
  type: TechArticle
- description: How to generate QR code image in Python using Aspose.Barcode. Learn
    step‑by‑step QR code creation with extended codetext, ECI encoding, and Unicode
    support.
  name: How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide
  steps:
  - name: 1. *What if I need more than two segments?*
    text: Simply call `add_plain_codetext` or `add_eci_codetext` as many times as
      you like. The builder maintains the correct ordering, so the QR code will contain
      each segment in the sequence you add them.
  - name: 2. *Can I embed emojis?*
    text: "Yes—emojis are just Unicode characters. Use the UTF‑8 ECI (value 26) and
      pass the emoji string, e.g., `builder.add_eci_codetext(26, \"\U0001F680\")`.
      The QR will display the rocket emoji on supporting scanners."
  - name: 3. *What if the QR becomes too dense?*
    text: 'QR codes have version limits. If you exceed the data capacity, Aspose will
      automatically bump the version up to the next size, but the image might become
      larger. To control size, you can lower the error correction level:'
  - name: 4. *Do I need to worry about character sets other than UTF‑8?*
    text: Only if you have legacy systems that require a specific encoding (e.g.,
      ISO‑8859‑1). In that case, replace `26` with the appropriate ECI value (see
      Aspose’s ECI table). For most modern apps, UTF‑8 is the safest bet.
  - name: 5. *How do I add a logo in the center?*
    text: 'Aspose.Barcode supports `barcode.generator.QRCodeParameters.logo_image`.
      Load an image with Pillow (`from PIL import Image`) and assign it:'
  type: HowTo
tags:
- QR code
- Python
- Aspose
title: Comment générer une image de code QR en Python avec Aspose.Barcode – Guide
  complet
url: /fr/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment générer une image de QR Code en Python avec Aspose.Barcode – Guide complet

Vous vous êtes déjà demandé **comment générer une image de QR code** en Python sans devoir fouiller des dizaines de bibliothèques ? Vous n'êtes pas seul. De nombreux développeurs ont besoin d’une méthode fiable pour intégrer du texte multilingue—par exemple du russe, de l’arabe ou des emojis—dans un QR code, et les bibliothèques natives sont souvent insuffisantes.

Voici le point clé : Aspose.Barcode pour Python rend cela étonnamment simple. Dans ce tutoriel, nous passerons en revue les étapes exactes, de l’installation du package à la création d’une chaîne de texte étendue qui mélange du ASCII simple avec du Unicode encodé en ECI. À la fin, vous disposerez d’une image QR prête à l’emploi sur le disque.

## Ce que couvre ce guide

- Installation de **Aspose.Barcode** pour Python (compatible avec Python 3.8+)
- Construction d’un **texte de code étendu** combinant des segments ASCII et Unicode
- Utilisation du **codage ECI** pour rendre correctement les caractères russes
- Configuration du `BarcodeGenerator` pour produire un QR code
- Enregistrement de l’image au format PNG
- Astuces, pièges courants et idées de prochaines étapes (comme ajouter des logos ou ajuster le niveau de correction d’erreur)

Aucune expérience préalable avec Aspose n’est requise ; il suffit d’une configuration Python de base et d’une curiosité pour les QR codes.

---

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

1. **Python 3.8 ou plus récent** installé sur votre machine.  
2. Un **environnement virtuel** (optionnel mais recommandé) pour garder les dépendances propres.  
3. Un accès **pip** pour installer le package `aspose-barcode`.  
4. Le droit d’écriture dans un dossier où le PNG généré sera sauvegardé.

Si l’un de ces points vous est inconnu, faites une pause ici et configurez‑le — une fois prêt, le reste est un jeu d’enfant.

---

## Étape 1 : Installer Aspose.Barcode pour Python

Le premier obstacle consiste à obtenir la bibliothèque. Aspose distribue ses packages sur PyPI, donc une simple commande `pip` suffit :

```bash
pip install aspose-barcode
```

> **Astuce pro :** Si vous travaillez dans un environnement virtuel, vous garderez vos packages globaux propres. En cas d’erreurs de permission, préfixez la commande avec `--user` ou exécutez‑la avec `sudo` (bien que ce dernier soit rarement nécessaire sur les configurations modernes).

Après l’installation, vous pouvez vérifier avec :

```python
import aspose.barcode as barcode
print(barcode.__version__)   # Should print something like 23.12.0
```

Si la version s’affiche sans problème, vous êtes prêt à continuer.

---

## Étape 2 : Créer une instance du **Extended Codetext Builder**

Aspose.Barcode fournit la classe `ExtCodetextBuilder` pour composer des charges utiles QR complexes. Pensez‑y comme à un petit éditeur de texte qui sait préfixer les bons caractères de contrôle pour chaque segment.

```python
# Step 2: Initialise the builder
builder = barcode.generation.ExtCodetextBuilder()
```

Pourquoi utiliser un builder ? Concaténer directement des octets bruts est source d’erreurs ; le builder garantit les bons basculements ECI (Extended Channel Interpretation), de sorte que votre lecteur QR puisse décoder chaque langue correctement.

---

## Étape 3 : Commencer frais (optionnel mais propre)

Si vous réutilisez la même instance du builder, appeler `clear()` efface les données précédentes. C’est un filet de sécurité qui empêche des segments résiduels de se retrouver dans le QR suivant.

```python
# Step 3: Ensure the builder is empty
builder.clear()
```

Vous pouvez ignorer cette ligne lors de la première exécution du script, mais la conserver rend le code idempotent—utile lorsqu’on intègre cette logique dans une fonction pouvant être appelée plusieurs fois.

---

## Étape 4 : Ajouter un segment simple (non encodé)

La plupart des QR codes commencent par une chaîne ASCII simple—peut‑être un identifiant ou une URL. La méthode `add_plain_codetext` ajoute exactement cela, sans aucun marqueur ECI.

```python
# Step 4: Add plain ASCII text
builder.add_plain_codetext("HelloWorld")
```

Dans cet exemple nous utilisons `"HelloWorld"` comme espace réservé. Remplacez‑le par ce dont vous avez besoin—peut‑être un SKU produit ou un court message.

---

## Étape 5 : Ajouter un segment **ECI‑encodé** (UTF‑8 = 26)

Passons maintenant à la partie multilingue. La valeur ECI **26** correspond à UTF‑8, le standard de facto pour Unicode. En passant `26` avec une phrase russe, nous indiquons au lecteur QR de basculer en UTF‑8 avant de lire les caractères suivants.

```python
# Step 5: Append a Russian phrase using UTF‑8 ECI (value 26)
builder.add_eci_codetext(26, "Привет")   # "Privet" means "Hello" in Russian
```

Vous pouvez remplacer `26` par d’autres valeurs ECI (par ex., `27` pour ISO‑8859‑1) si vous avez besoin d’un encodage différent. Le builder insérera automatiquement les bons caractères de contrôle.

---

## Étape 6 : Récupérer le texte de code étendu combiné

Une fois tous les segments ajoutés, récupérez la chaîne finale que le générateur QR consommera. Cette chaîne contient des séquences de contrôle invisibles, mais vous pouvez tout de même l’imprimer pour le débogage.

```python
# Step 6: Get the full extended codetext
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

La sortie console apparaîtra brouillée (à cause des octets de contrôle intégrés), ce qui est tout à fait normal. L’important est que le builder ait correctement assemblé les parties ASCII et Unicode.

---

## Étape 7 : Configurer le générateur de code‑barres

Nous transmettons maintenant le texte de code étendu à `BarcodeGenerator` d’Aspose. Définissez la symbologie sur `QR` et assignez la chaîne combinée à `code_text`.

```python
# Step 7: Initialise the QR code generator
generator = barcode.generation.BarcodeGenerator()
generator.symbology = barcode.Symbology.QR          # Choose QR symbology
generator.code_text = extended_codetext           # Use the extended codetext
```

Vous pouvez ajuster d’autres propriétés ici—comme `resolution`, `error_correction_level` ou `foreground_color`. Ces options sont détaillées dans la documentation Aspose, mais pour une image basique les valeurs par défaut suffisent.

---

## Étape 8 : Enregistrer l’image QR générée

Enfin, écrivez le QR code sur le disque. La méthode `save` accepte un chemin de fichier et un format optionnel ; PNG est une valeur sûre.

```python
# Step 8: Persist the QR code as a PNG file
output_path = "qr_extended.png"   # Adjust path as needed
generator.save(output_path)
print(f"QR code saved to {output_path}")
```

Ouvrez le fichier `qr_extended.png` avec n’importe quel visualiseur d’images. Le scanner de votre smartphone devrait révéler deux messages distincts : “HelloWorld” et “Привет”. La plupart des lecteurs QR modernes gèrent automatiquement le basculement ECI.

---

## Exemple complet fonctionnel

En rassemblant le tout, voici le script complet que vous pouvez copier‑coller et exécuter :

```python
import aspose.barcode as barcode

# Initialise the extended codetext builder
builder = barcode.generation.ExtCodetextBuilder()
builder.clear()                                   # Ensure a clean start
builder.add_plain_codetext("HelloWorld")          # Plain ASCII segment
builder.add_eci_codetext(26, "Привет")            # Russian UTF‑8 segment
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# Configure the QR generator
generator = barcode.generation.BarcodeGenerator()
generator.symbology = barcode.Symbology.QR
generator.code_text = extended_codetext

# Save the image
output_file = "qr_extended.png"
generator.save(output_file)
print(f"QR code image saved as {output_file}")
```

**Sortie attendue** (console) :

```
Extended codetext: <binary data>   # appears garbled due to ECI markers
QR code image saved as qr_extended.png
```

Ouvrez `qr_extended.png` → scannez → vous verrez “HelloWorld” suivi de “Привет”.

---

## Questions fréquentes & cas particuliers

### 1. *Et si j’ai besoin de plus de deux segments ?*  
Il suffit d’appeler `add_plain_codetext` ou `add_eci_codetext` autant de fois que nécessaire. Le builder maintient l’ordre correct, de sorte que le QR code contiendra chaque segment dans la séquence que vous avez définie.

### 2. *Puis‑je intégrer des emojis ?*  
Oui—les emojis sont simplement des caractères Unicode. Utilisez l’ECI UTF‑8 (valeur 26) et passez la chaîne emoji, par ex., `builder.add_eci_codetext(26, "🚀")`. Le QR affichera l’emoji fusée sur les lecteurs compatibles.

### 3. *Que faire si le QR devient trop dense ?*  
Les QR codes ont des limites de version. Si vous dépassez la capacité de données, Aspose augmentera automatiquement la version au prochain niveau, mais l’image pourra devenir plus grande. Pour contrôler la taille, vous pouvez réduire le niveau de correction d’erreur :

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorCorrectionLevel.L
```

### 4. *Dois‑je me soucier d’autres jeux de caractères que UTF‑8 ?*  
Seulement si vous avez des systèmes hérités nécessitant un encodage spécifique (par ex., ISO‑8859‑1). Dans ce cas, remplacez `26` par la valeur ECI appropriée (voir le tableau ECI d’Aspose). Pour la plupart des applications modernes, UTF‑8 reste le choix le plus sûr.

### 5. *Comment ajouter un logo au centre ?*  
Aspose.Barcode supporte `barcode.generator.QRCodeParameters.logo_image`. Chargez une image avec Pillow (`from PIL import Image`) et assignez‑la :

```python
from PIL import Image
logo = Image.open("logo.png")
generator.parameters.qr.logo_image = logo
```

Le logo sera superposé tout en préservant la lisibilité (Aspose ajuste automatiquement les zones calmes).

---

## Astuces pro pour la production

- **Mettez en cache le builder** si vous générez le même QR de façon répétée ; cela évite de reconstruire la chaîne étendue à chaque appel.
- **Validez la sortie** avec un test unitaire qui décode le QR (par ex., avec `zxing` ou `pyzbar`) afin de garantir que vos basculements ECI sont corrects.
- **Utilisez un nom de fichier déterministe** (par exemple en incluant un hash du payload) pour éviter d’écraser des images existantes.
- **Pensez à la licence** : Aspose.Barcode est un logiciel commercial. L’évaluation gratuite suffit pour le développement, mais une licence est requise pour le déploiement en production.

---

## Prochaines étapes & sujets associés

Maintenant que vous savez **comment générer un QR code**


## Que devriez‑vous apprendre ensuite ?


Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques présentées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et à explorer des approches alternatives dans vos projets.

- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to create dotcode extended codetext with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
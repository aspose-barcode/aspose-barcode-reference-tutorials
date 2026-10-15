---
category: general
date: 2026-10-15
description: Créez un code‑barres à partir d’une chaîne en Python avec Aspose.BarCode,
  apprenez à générer un code 128 et à enregistrer le code‑barres au format PNG en
  quelques lignes seulement.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from string
- generate code 128 barcode
- how to save barcode
- generate barcode png
- encode data into barcode
language: fr
lastmod: 2026-10-15
og_description: Créer un code‑barres à partir d’une chaîne en Python pour encoder
  des données dans un code‑barres Code 128 et l’enregistrer au format PNG avec Aspose.BarCode.
og_image_alt: Screenshot of a generated Code 128 barcode saved as a PNG image
og_title: Créer un code‑barres à partir d’une chaîne en Python – guide étape par étape
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode from string in Python using Aspose.BarCode, learn how
    to generate Code 128 barcode and save barcode PNG in just a few lines.
  headline: Create barcode from string in Python with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Replace `EncodeTypes.CODE_128` with another enum value such as `EncodeTypes.QR`,
      `EncodeTypes.EAN_13`, or `EncodeTypes.PDF_417`. The rest of the code remains
      the same.
    question: What if I need a different symbology?
  - answer: Code 128 supports the full 128‑character ASCII set. For Unicode data,
      consider using QR Code (`EncodeTypes.QR`) which handles UTF‑8 natively.
    question: Can I generate a barcode from non‑ASCII characters?
  - answer: Pass a different member of `BarCodeImageFormat` to `save`, e.g., `BarCodeImageFormat.JPEG`
      or `BarCodeImageFormat.BMP`.
    question: How do I change the image format?
  - answer: Wrap the `save` call in a try/except block and handle `PermissionError`
      gracefully, perhaps by prompting the user for an alternative path.
    question: What if the output directory is read‑only?
  type: FAQPage
tags:
- barcode
- Python
- Aspose
- Code128
title: Créer un code‑barres à partir d’une chaîne en Python avec Aspose.BarCode
url: /fr/python-java/general/create-barcode-from-string-in-python-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Créer un code-barres à partir d'une chaîne en Python avec Aspose.BarCode

Si vous devez **créer un code-barres à partir d'une chaîne** en Python, ce guide vous montre les étapes exactes avec Aspose.BarCode. Vous apprendrez comment **générer un code-barres Code 128**, ajuster son apparence, et **enregistrer le PNG du code-barres** sur le disque. La solution fonctionne sur n'importe quelle plateforme supportant Python 3.9+ et ne nécessite que quelques lignes de code.

Générer des codes-barres de manière programmatique élimine les erreurs de saisie manuelle et rationalise les flux de travail tels que le suivi d'inventaire, la billetterie et l'impression d'étiquettes. À la fin de ce tutoriel, vous serez capable de **encoder des données dans un code-barres**, de personnaliser les dimensions et de stocker l'image où vous le souhaitez.

## Prérequis

- Python 3.9 ou version plus récente installé  
- Accès Internet pour télécharger le package Aspose.BarCode  
- Permission d'écriture dans le répertoire où vous enregistrerez le fichier PNG  

Si vous utilisez un environnement virtuel (fortement recommandé), activez-le maintenant.

## Installer le package Python Aspose.BarCode

Aspose fournit une bibliothèque pure‑Python qui gère toutes les symbologies de code-barres courantes, y compris Code 128. Installez‑la avec pip :

```bash
pip install aspose-barcode
```

*Astuce :* Verrouillez la version (par ex., `aspose-barcode==23.9`) pour éviter des changements incompatibles inattendus en production.

## Créer un code-barres à partir d'une chaîne en Python

La première étape fonctionnelle consiste à importer les classes requises et à instancier un générateur pour la symbologie souhaitée. Cet exemple utilise **Code 128**, qui est idéal pour les données alphanumériques.

```python
# Step 1: Import the Aspose.BarCode classes
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 2: Create a generator for Code 128 and provide the data string
barcode_generator = BarcodeGenerator(EncodeTypes.CODE_128, "1234567890")
```

**Pourquoi c'est important :** `EncodeTypes.CODE_128` indique à la bibliothèque quel standard de code-barres appliquer, tandis que le deuxième argument (`"1234567890"`) est la **chaîne que vous souhaitez encoder en code-barres**. Vous pouvez le remplacer par n'importe quelle chaîne ASCII jusqu'à 80 caractères pour Code 128.

## Générer un code‑barres Code 128

Une fois le générateur prêt, vous pouvez produire l'image du code‑barres en mémoire. La bibliothèque rend automatiquement le code‑barres à partir des données fournies.

```python
# Step 3: Render the barcode to an image object (in memory)
barcode_image = barcode_generator.generate_barcode_image()
```

À ce stade, `barcode_image` est une instance de `System.Drawing.Image` (sur Windows) ou un objet image compatible sur d'autres plateformes. Vous pouvez l'afficher directement dans une interface graphique, l'intégrer dans un PDF, ou continuer à le personnaliser.

## Ajuster l'apparence du code‑barres

Le réglage fin des propriétés visuelles garantit que le code‑barres se lit de manière fiable dans votre environnement spécifique. Les ajustements courants comprennent la X‑dimension (la largeur de la barre la plus étroite) et la hauteur globale des barres.

```python
# Step 4: Adjust appearance – X dimension and bar height
barcode_generator.parameters.barcode.x_dimension.pixels = 2   # width of the smallest bar
barcode_generator.parameters.barcode.bar_height.pixels = 100  # height of the bars (optional)
```

*Pourquoi ajuster ces valeurs ?*  
- **Dimension X** influence la densité du code‑barres ; une valeur plus petite produit un code‑barres plus compact qui tient sur de petites étiquettes.  
- **Hauteur des barres** affecte la lisibilité ; des barres plus hautes sont plus faciles à détecter pour les scanners à distance.

Vous pouvez également changer les couleurs, ajouter des marges, ou intégrer du texte lisible par l'homme via l'objet `parameters`. Consultez la documentation Aspose.BarCode pour la liste complète des options.

## Comment enregistrer le code‑barres au format PNG

Enregistrer l'image générée est la dernière étape du flux de travail **créer un code‑barres à partir d'une chaîne**. La bibliothèque prend en charge plusieurs formats ; PNG est sans perte et largement supporté.

```python
# Step 5: Save the barcode image to a PNG file
output_path = "output/barcode.png"
barcode_generator.save(output_path, BarCodeImageFormat.PNG)
```

La méthode `save` écrit l'image sur le système de fichiers en utilisant le format que vous spécifiez. Si le répertoire cible (`output/` dans cet exemple) n'existe pas, Python lèvera une `FileNotFoundError`. Créez le répertoire au préalable ou gérez l'exception :

```python
import os

output_dir = os.path.dirname(output_path)
os.makedirs(output_dir, exist_ok=True)   # ensures the directory exists
barcode_generator.save(output_path, BarCodeImageFormat.PNG)
```

**Résultat attendu :** Après l'exécution du script, `output/barcode.png` contient un code‑barres Code 128 clair qui encode "1234567890". L'ouverture du fichier dans n'importe quel visualiseur d'images affichera un code‑barres noir sur blanc prêt à être scanné.

## Exemple complet et exécutable

En rassemblant tous les éléments, voici un script autonome que vous pouvez copier, coller et exécuter :

```python
"""
Complete example: create barcode from string, generate Code 128 barcode,
customize appearance, and save barcode PNG using Aspose.BarCode.
"""

import os
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1. Define input data and output location
data_to_encode = "1234567890"
output_path = "output/barcode.png"

# 2. Ensure the output directory exists
os.makedirs(os.path.dirname(output_path), exist_ok=True)

# 3. Initialise the generator for Code 128
generator = BarcodeGenerator(EncodeTypes.CODE_128, data_to_encode)

# 4. Optional: tweak visual parameters
generator.parameters.barcode.x_dimension.pixels = 2
generator.parameters.barcode.bar_height.pixels = 100

# 5. Save as PNG
generator.save(output_path, BarCodeImageFormat.PNG)

print(f"Barcode saved to {output_path}")
```

Exécutez le script avec `python create_barcode.py`. Si tout est installé correctement, vous verrez :

```
Barcode saved to output/barcode.png
```

Ouvrez le fichier PNG et vérifiez que le code‑barres correspond à la chaîne originale à l'aide de n'importe quelle application de lecture de code‑barres.

## Questions fréquentes et cas particuliers

- **Et si j'ai besoin d'une symbologie différente ?**  
  Remplacez `EncodeTypes.CODE_128` par une autre valeur d'énumération telle que `EncodeTypes.QR`, `EncodeTypes.EAN_13` ou `EncodeTypes.PDF_417`. Le reste du code reste identique.

- **Puis-je générer un code‑barres à partir de caractères non‑ASCII ?**  
  Code 128 prend en charge l'ensemble complet des 128 caractères ASCII. Pour des données Unicode, envisagez d'utiliser le QR Code (`EncodeTypes.QR`) qui gère nativement UTF‑8.

- **Comment changer le format de l'image ?**  
  Passez un autre membre de `BarCodeImageFormat` à `save`, par ex., `BarCodeImageFormat.JPEG` ou `BarCodeImageFormat.BMP`.

- **Que faire si le répertoire de sortie est en lecture seule ?**  
  Enveloppez l'appel `save` dans un bloc try/except et gérez `PermissionError` de façon élégante, éventuellement en demandant à l'utilisateur un chemin alternatif.

- **Astuce de performance :**  
  Générer des milliers de codes‑barres dans une boucle peut être intensif en CPU. Réutilisez une seule instance de `BarcodeGenerator` et ne mettez à jour que `generator.parameters.barcode.code_text` entre les itérations.

## Conclusion

Vous savez maintenant comment **créer un code‑barres à partir d'une chaîne** en Python avec Aspose.BarCode, **générer un code‑barres Code 128**, personnaliser sa taille, et **enregistrer le PNG du code‑barres** sur le disque. Cette solution de bout en bout vous permet d'**encoder des données dans un code‑barres** rapidement et de manière fiable, facilitant l'intégration des codes‑barres dans les systèmes d'inventaire, les plateformes de billetterie ou toute application nécessitant des identifiants lisibles par machine.

**Prochaines étapes**

- Explorez d'autres symbologies (alternatives à `generate code 128 barcode`) telles que QR ou DataMatrix.  
- Ajoutez une logique de gestion des erreurs pour rendre le script robuste en production (échecs de `how to save barcode`).  
- Intégrez le PNG généré dans des PDF ou des rapports HTML (`generate barcode png` pour le web).  

Bon codage, et profitez de la simplicité de la génération programmatique de codes‑barres !

## Que devriez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s'appuient sur les techniques démontrées dans ce guide. Chaque ressource comprend des exemples de code fonctionnels complets avec des explications étape par étape pour vous aider à maîtriser des fonctionnalités supplémentaires de l'API et explorer des approches d'implémentation alternatives dans vos propres projets.

- [Comment générer un code‑barres Code 128 et enregistrer l'image du code‑barres avec Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [Comment générer une image de QR Code en Python avec Aspose.Barcode – Guide complet](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Créer un PNG de code‑barres en Python – Guide complet Aspose.Barcode](/barcode/english/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
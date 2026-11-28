---
category: general
date: 2026-11-27
description: Apprenez à créer un code‑barres avec du texte et à générer un code‑barres
  planétaire en Python — guide étape par étape pour une sortie PNG haute résolution.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode with text
- how to generate barcode
- generate planet barcode
- Python barcode generation
- high‑resolution barcode PNG
language: fr
lastmod: 2026-11-27
og_description: Créez un code‑barres avec du texte et générez un code‑barres planétaire
  en Python. Suivez ce guide complet pour obtenir un PNG haute résolution.
og_image_alt: Screenshot showing how to create barcode with text using the Planet
  barcode generator
og_title: Créer un code-barres avec du texte en Python – générez facilement le code-barres
  Planet
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Learn how to create barcode with text and generate planet barcode in
    Python—step‑by‑step guide for high‑resolution PNG output.
  headline: How to create barcode with text using the Planet format in Python
  type: TechArticle
tags:
- barcode
- Python
- Planet format
- image generation
title: Comment créer un code‑barres avec du texte en utilisant le format Planet en
  Python
url: /fr/python-java/general/how-to-create-barcode-with-text-using-the-planet-format-in-p/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Comment créer un code‑barres avec texte en utilisant le format Planet en Python

Si vous devez **créer un code‑barres avec texte** pour un système de distribution du courrier, ce tutoriel vous montre exactement comment le faire. Vous verrez un exemple concis, de bout en bout, qui génère un code‑barres Planet, ajuste la résolution et enregistre le résultat sous forme d’image PNG.

Générer des codes‑barres est une exigence courante pour la logistique, la gestion des stocks et les applications de billetterie. Dans ce guide, vous apprendrez non seulement **comment générer des fichiers de code‑barres**, mais aussi pourquoi chaque étape de configuration est importante et comment éviter les pièges habituels.

## Ce que vous allez apprendre

* Configurer le générateur de code‑barres Planet avec du texte personnalisé.  
* Ajuster la dimension X pour augmenter la netteté de l’image.  
* Enregistrer le code‑barres sous forme de fichier PNG pouvant être imprimé ou affiché sur le web.  
* Étendre l’exemple à d’autres types de code‑barres ou formats de sortie.

**Prérequis**

* Python 3.8 ou version supérieure.  
* Le package `aspose-barcode` (ou toute bibliothèque compatible qui fournit `BarcodeGenerator`, `EncodeTypes` et `BarCodeImageFormat`).  
* Une connaissance de base du scripting Python.

Vous pouvez installer le package requis avec :

```bash
pip install aspose-barcode
```

---

## Étape 1 : Créer un code‑barres avec texte – initialiser le générateur

La première chose à faire est de créer une instance de `BarcodeGenerator` qui sait quelle symbologie utiliser et quel texte encoder. Pour un code‑barres Planet, la valeur d’énumération `EncodeTypes.Planet` indique à la bibliothèque de suivre la spécification USPS Planet.

```python
# Import the necessary classes from the Aspose.BarCode library
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1: Initialize the generator with the desired text
# The text "123456" will appear beneath the Planet barcode pattern.
gen = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

**Pourquoi c’est important :**  
L’objet `BarcodeGenerator` regroupe tous les paramètres du code‑barres. Fournir le texte lors de la construction garantit que la valeur encodée reste immuable pendant le reste du processus, ce qui élimine les incohérences accidentelles plus tard.

---

## Étape 2 : Ajuster les paramètres – comment générer un code‑barres avec une résolution supérieure

Un code‑barres à basse résolution peut paraître flou lorsqu’il est imprimé sur une imprimante d’étiquettes. La dimension X (largeur du module) contrôle la taille de chaque barre individuelle. La régler à 4 pixels donne une image nette, haute résolution adaptée à la plupart des imprimantes modernes.

```python
# Step 2: Increase the X‑dimension to 4 pixels for better clarity
gen.parameters.barcode.x_dimension.pixels = 4
```

**Explication :**  
* `gen.parameters.barcode.x_dimension.pixels` correspond directement à la largeur physique d’un seul module.  
* Une valeur de **4** signifie que chaque barre fait quatre pixels de large, ce qui correspond approximativement à 0,127 mm à 300 dpi — bien dans la fourchette recommandée pour les codes‑barres USPS Planet.  

**Astuce :** Si vous avez besoin d’un DPI différent, calculez la largeur en pixels en conséquence (par ex., 2 pixels pour 150 dpi, 8 pixels pour 600 dpi).

---

## Étape 3 : Enregistrer l’image – générer le code‑barres Planet en PNG

Une fois le générateur configuré, vous pouvez rendre le code‑barres dans un fichier image. Le PNG est sans perte, garantissant que le motif exact des modules est préservé.

```python
# Step 3: Save the generated barcode as a PNG image
output_path = "output/PostalPlanetBarHeightNone.png"
gen.save(output_path, BarCodeImageFormat.Png)
print(f"Barcode saved to {output_path}")
```

**Résultat :**  
L’exécution du script crée un fichier nommé `PostalPlanetBarHeightNone.png` contenant un code‑barres Planet encodant la chaîne « 123456 ». Les dimensions de l’image seront d’environ 200 × 100 pixels, selon la dimension X que vous avez choisie.

---

## Optionnel : Vérifier visuellement le code‑barres

Vous pouvez rapidement ouvrir le PNG généré avec n’importe quel visualiseur d’image pour confirmer que le code‑barres est net et que le texte lisible par l’homme apparaît sous le motif.

```python
from PIL import Image

img = Image.open(output_path)
img.show()
```

Si l’image apparaît floue, revenez à **l’Étape 2** et augmentez la dimension X jusqu’à ce que les barres soient clairement définies.

---

## Variations courantes et cas limites

| Situation | Ajustement |
|-----------|------------|
| **Longueur de texte différente** | Les codes‑barres Planet supportent jusqu’à 12 caractères numériques. Si vous dépassez cette limite, la bibliothèque lèvera une exception. |
| **Format de sortie alternatif** | Remplacez `BarCodeImageFormat.Png` par `BarCodeImageFormat.Jpeg` ou `BarCodeImageFormat.Bmp` pour d’autres cas d’usage. |
| **Couleurs de premier plan/arrière‑plan personnalisées** | Utilisez `gen.parameters.barcode.barcode_color = Color.Blue` et `gen.parameters.barcode.back_color = Color.White`. |
| **Pas de texte lisible** | Définissez `gen.parameters.barcode.hide_code_text = True` pour générer un code‑barres sans légende inférieure. |
| **Génération par lots** | Parcourez une liste de chaînes, créez un nouveau `BarcodeGenerator` pour chacune, et enregistrez‑les dans des fichiers aux noms uniques. |

Ces variations vous permettent de **générer des fichiers de code‑barres Planet** adaptés à un large éventail d’exigences métier.

---

## Script complet – prêt à l’emploi

Voici le script complet, autonome, que vous pouvez copier, coller et exécuter. Il inclut tous les imports, la gestion des erreurs et les commentaires.

```python
"""
Complete example: create barcode with text and generate a Planet barcode PNG.
Author: Your Name
Date: 2026-11-27
"""

import os
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from aspose.barcode import Color  # optional, for color customization
from PIL import Image

def create_planet_barcode(text: str, output_dir: str, x_dim_pixels: int = 4) -> str:
    """
    Generates a Planet barcode with the given text and saves it as a PNG.
    
    Args:
        text: Numeric string to encode (max 12 characters for Planet).
        output_dir: Directory where the PNG will be stored.
        x_dim_pixels: Width of a single module in pixels (default 4 for high resolution).
    
    Returns:
        Full path to the saved PNG file.
    """
    if not text.isdigit():
        raise ValueError("Planet barcode requires numeric text only.")
    if len(text) > 12:
        raise ValueError("Planet barcode supports up to 12 digits.")
    
    # Ensure the output directory exists
    os.makedirs(output_dir, exist_ok=True)
    
    # Initialize the generator with the desired text
    gen = BarcodeGenerator(EncodeTypes.Planet, text)
    
    # Adjust resolution via X‑dimension
    gen.parameters.barcode.x_dimension.pixels = x_dim_pixels
    
    # Build the output file path
    file_name = f"Planet_{text}.png"
    full_path = os.path.join(output_dir, file_name)
    
    # Save as PNG
    gen.save(full_path, BarCodeImageFormat.Png)
    
    return full_path

if __name__ == "__main__":
    try:
        result_path = create_planet_barcode("123456", "output")
        print(f"Barcode successfully generated: {result_path}")
        
        # Open the image for a quick visual check
        Image.open(result_path).show()
    except Exception as e:
        print(f"Error: {e}")
```

**Explication du script**

* La fonction `create_planet_barcode` regroupe les trois étapes principales, rendant le code réutilisable.  
* La validation des entrées garantit le respect de la spécification Planet (uniquement des chiffres, maximum 12 chiffres).  
* La fonction crée automatiquement le dossier de sortie, vous n’avez donc pas à gérer les répertoires manuellement.  
* Après la génération, le script ouvre l’image avec Pillow (`PIL`) pour une vérification immédiate.

---

## Conclusion

Vous savez maintenant comment **créer un code‑barres avec texte** et **générer des fichiers de code‑barres Planet** en Python. Le guide a couvert l’initialisation, le réglage de la résolution et la sortie du fichier, ainsi que des personnalisations optionnelles et des cas limites courants.  

À partir d’ici, vous pouvez :

* Remplacer `EncodeTypes.Planet` par d’autres symbologies (par ex., `EncodeTypes.Code128`) pour réutiliser le même modèle.  
* Intégrer la fonction dans un service web qui renvoie des images de code‑barres à la demande.  
* Expérimenter la génération par lots pour produire des milliers de codes‑barres pour le publipostage.

N’hésitez pas à adapter le script aux besoins de votre projet et à partager vos résultats dans les commentaires. Bon codage !

## Que devez‑vous apprendre ensuite ?

Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code complets avec des explications pas à pas pour vous aider à maîtriser d’autres fonctionnalités de l’API et explorer des approches d’implémentation alternatives dans vos propres projets.

- [Comment générer un code‑barres en Python – guide complet étape par étape](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Créer un code‑barres PNG en Python – guide étape par étape](/barcode/english/python-java/general/create-barcode-png-in-python-step-by-step-guide/)
- [Comment créer un code‑barres Planet PNG avec Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
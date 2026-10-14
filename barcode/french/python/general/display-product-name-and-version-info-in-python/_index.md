---
category: general
date: 2026-09-29
description: Afficher le nom du produit en Python tout en imprimant la date de sortie
  et en récupérant les détails de version de la bibliothèque barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- display product name
- print release date
- how to get version
- how to print product
- show minor version
language: fr
lastmod: 2026-09-29
og_description: Affichez le nom du produit en Python et apprenez comment imprimer
  la date de sortie, obtenir la version et afficher la version mineure en quelques
  lignes de code.
og_image_alt: Screenshot of terminal output showing product name, version, and release
  date
og_title: Afficher le nom du produit et les informations de version en Python
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Display product name in Python while printing release date and retrieving
    version details from the barcode library.
  headline: Display product name and version info in Python
  type: TechArticle
tags:
- Python
- barcode library
- version information
title: Afficher le nom du produit et les informations de version en Python
url: /fr/python/general/display-product-name-and-version-info-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Afficher le nom du produit et les informations de version en Python

Si vous devez **afficher le nom du produit** à partir d’une bibliothèque, ce guide vous montre exactement comment faire. Vous apprendrez également à **imprimer la date de sortie**, **obtenir la version**, et **afficher la version mineure** à l’aide d’un code Python concis.

De nombreux développeurs intègrent des fonctionnalités de lecture ou de génération de codes‑barres et doivent exposer les métadonnées de la bibliothèque aux utilisateurs ou aux journaux. Ce tutoriel couvre tout ce qui est nécessaire pour récupérer et présenter ces informations de manière fiable.

## Ce que vous allez apprendre

* Récupérer les informations de version de la bibliothèque `barcode`.  
* **Afficher le nom du produit** avec les numéros de version majeure et mineure.  
* **Imprimer la date de sortie** dans un format lisible par l’homme.  
* Gérer les attributs manquants de façon élégante.  

**Prérequis**  
* Python 3.8 ou supérieur.  
* Accès au package `barcode` (installez-le avec `pip install python-barcode` ou la bibliothèque qui fournit `BuildVersionInfo`).  

---

## Comment afficher le nom du produit et les informations de version en Python

La première étape consiste à importer la bibliothèque et à appeler la méthode qui renvoie un objet contenant les informations de version. L’objet possède des attributs tels que `PRODUCT`, `PRODUCT_MAJOR`, `PRODUCT_MINOR` et `RELEASE_DATE`.

```python
import barcode

def main():
    # Step 1: Retrieve version information from the barcode library
    info = barcode.BuildVersionInfo()

    # Step 2: Display product name
    print(f"Product: {info.PRODUCT}")

    # Step 3: Show major and minor version numbers
    print(f"Version: {info.PRODUCT_MAJOR}.{info.PRODUCT_MINOR}")

    # Step 4: Print release date
    print(f"Release date: {info.RELEASE_DATE}")

if __name__ == "__main__":
    main()
```

**Pourquoi cela fonctionne**  
`BuildVersionInfo()` renvoie un objet léger dont les attributs sont remplis au moment de l’importation. Accéder directement aux attributs évite des I/O supplémentaires et garantit que les données affichées correspondent à la version de la bibliothèque réellement utilisée par votre code.

### Résultat attendu

```
Product: BarcodeLib
Version: 2.5
Release date: 2024-03-15
```

Les valeurs exactes dépendent de la version installée de la bibliothèque barcode.

---

## Comment obtenir la version de la bibliothèque barcode

Si vous avez seulement besoin des numéros de version, vous pouvez ignorer l’affichage du nom du produit et vous concentrer sur les champs numériques.

```python
import barcode

info = barcode.BuildVersionInfo()
major = info.PRODUCT_MAJOR
minor = info.PRODUCT_MINOR

print(f"Current version: {major}.{minor}")
```

*Les attributs `PRODUCT_MAJOR` et `PRODUCT_MINOR` suivent le versionnage sémantique, ce qui vous permet de comparer les versions de façon programmatique.*

---

## Comment imprimer la date de sortie

La date de sortie est stockée sous forme de chaîne au format `YYYY‑MM‑DD`. Pour la présenter dans une locale différente, convertissez‑la d’abord en objet `datetime`.

```python
import barcode
from datetime import datetime

info = barcode.BuildVersionInfo()
raw_date = info.RELEASE_DATE          # e.g., "2024-03-15"
date_obj = datetime.strptime(raw_date, "%Y-%m-%d")
formatted = date_obj.strftime("%B %d, %Y")  # "March 15, 2024"

print(f"Release date: {formatted}")
```

**Astuce :** Validez toujours la chaîne de date avant de la parser afin d’éviter un `ValueError` si la bibliothèque modifie son format.

---

## Afficher la version mineure à côté de la version majeure

Parfois, il est nécessaire d’afficher la version mineure séparément, par exemple lors de l’enregistrement d’avertissements de compatibilité.

```python
import barcode

info = barcode.BuildVersionInfo()
print(f"Major version: {info.PRODUCT_MAJOR}")
print(f"Minor version: {info.PRODUCT_MINOR}")
```

**Pro tip :** Utilisez la version mineure pour déclencher des drapeaux de fonctionnalité :

```python
if info.PRODUCT_MINOR >= 5:
    enable_new_feature()
```

---

## Gestion des attributs manquants (cas limites)

Les versions plus anciennes de la bibliothèque barcode peuvent ne pas exposer tous les attributs. Enveloppez l’accès aux attributs dans `getattr` avec des valeurs par défaut sensées.

```python
import barcode

info = barcode.BuildVersionInfo()

product = getattr(info, "PRODUCT", "Unknown Product")
major = getattr(info, "PRODUCT_MAJOR", 0)
minor = getattr(info, "PRODUCT_MINOR", 0)
release = getattr(info, "RELEASE_DATE", "N/A")

print(f"Product: {product}")
print(f"Version: {major}.{minor}")
print(f"Release date: {release}")
```

Ce modèle garantit que votre script ne plantera jamais à cause d’un champ manquant, le rendant robuste pour les pipelines CI qui peuvent être exécutés contre plusieurs versions de la bibliothèque.

---

## Exemple complet et exécutable

Voici le script complet qui combine toutes les bonnes pratiques : validation des attributs, formatage de la date et sortie claire.

```python
import barcode
from datetime import datetime

def fetch_info():
    """Retrieve version info safely, providing defaults for missing attributes."""
    raw = barcode.BuildVersionInfo()
    return {
        "product": getattr(raw, "PRODUCT", "Unknown Product"),
        "major": getattr(raw, "PRODUCT_MAJOR", 0),
        "minor": getattr(raw, "PRODUCT_MINOR", 0),
        "release_raw": getattr(raw, "RELEASE_DATE", "N/A")
    }

def format_release(date_str):
    """Convert YYYY‑MM‑DD to a friendly format; fall back to the original string."""
    try:
        dt = datetime.strptime(date_str, "%Y-%m-%d")
        return dt.strftime("%B %d, %Y")
    except (ValueError, TypeError):
        return date_str

def main():
    info = fetch_info()

    # Display product name
    print(f"Product: {info['product']}")

    # Show major and minor version numbers
    print(f"Version: {info['major']}.{info['minor']}")

    # Print release date in a readable form
    print(f"Release date: {format_release(info['release_raw'])}")

if __name__ == "__main__":
    main()
```

L’exécution de ce script sur un système où la bibliothèque barcode est installée produit une sortie similaire à l’exemple précédent, mais il protège désormais contre les champs manquants et formate la date de façon agréable.

---

## Conclusion

Vous savez maintenant comment **afficher le nom du produit**, **imprimer la date de sortie**, **obtenir la version**, **imprimer le produit**, et **afficher la version mineure** en utilisant un flux de travail Python simple. L’exemple complet montre un accès fiable aux attributs, la gestion des dates et la comparaison de versions — des compétences réutilisables pour toute bibliothèque tierce exposant des objets de métadonnées.

**Étapes suivantes**

* Explorez les autres méthodes de métadonnées de la bibliothèque barcode, comme `BuildCommitInfo()`.  
* Intégrez la sortie dans un framework de journalisation (par ex., `logging.info`).  
* Comparez les versions de façon programmatique pour imposer des versions minimales requises dans votre application.

N’hésitez pas à expérimenter avec différents formats de sortie ou à étendre le script pour écrire les informations dans un fichier à des fins d’audit. Bon codage !  

![Sortie du terminal affichant le nom du produit et les détails de version](image.png "Sortie du terminal affichant le nom du produit et les détails de version")


## Que devriez‑vous apprendre ensuite ?


Les tutoriels suivants couvrent des sujets étroitement liés qui s’appuient sur les techniques démontrées dans ce guide. Chaque ressource inclut des exemples de code fonctionnels complets avec des explications pas à pas pour vous aider à maîtriser des fonctionnalités API supplémentaires et à explorer des approches d’implémentation alternatives dans vos propres projets.

- [afficher le nom du produit avec la bibliothèque Python barcode – guide étape par étape](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)
- [Comment imprimer la version d’Aspose.Barcode (Python)](/barcode/english/python/general/how-to-print-version-of-aspose-barcode-python/)
- [Comment générer un code‑barcode avec Aspose.BarCode en Python](/barcode/english/python-java/general/how-to-generate-barcode-with-aspose-barcode-in-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
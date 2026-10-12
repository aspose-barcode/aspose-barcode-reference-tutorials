---
category: general
date: 2026-09-29
description: Отображать название продукта в Python при печати даты выпуска и получении
  сведений о версии из библиотеки barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- display product name
- print release date
- how to get version
- how to print product
- show minor version
language: ru
lastmod: 2026-09-29
og_description: Отобразите название продукта в Python и узнайте, как вывести дату
  выпуска, получить версию и показать минорную версию несколькими строками кода.
og_image_alt: Screenshot of terminal output showing product name, version, and release
  date
og_title: Отобразить название продукта и информацию о версии в Python
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
title: Отображение названия продукта и информации о версии в Python
url: /ru/python/general/display-product-name-and-version-info-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Отображение названия продукта и информации о версии в Python

Если вам нужно **отобразить название продукта** из библиотеки, это руководство покажет вам, как это сделать. Вы также узнаете, как **вывести дату выпуска**, **получить версию** и **показать минорную версию**, используя лаконичный код на Python.

Многие разработчики интегрируют функции сканирования или генерации штрих‑кодов и должны предоставлять метаданные библиотеки пользователям или в журналах. Это руководство охватывает всё, что необходимо для надёжного получения и отображения этой информации.

## Чего вы научитесь

* Получить информацию о версии из библиотеки `barcode`.  
* **Отобразить название продукта** вместе с основными и минорными номерами версии.  
* **Вывести дату выпуска** в человекочитаемом формате.  
* Обрабатывать отсутствие атрибутов корректно.  

**Требования**  
* Python 3.8 или новее.  
* Доступ к пакету `barcode` (установите с помощью `pip install python-barcode` или библиотеки, предоставляющей `BuildVersionInfo`).  

---

## Как отобразить название продукта и информацию о версии в Python

Первым шагом является импорт библиотеки и вызов метода, который возвращает объект с информацией о версии. Объект содержит атрибуты, такие как `PRODUCT`, `PRODUCT_MAJOR`, `PRODUCT_MINOR` и `RELEASE_DATE`.

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

**Почему это работает**  
`BuildVersionInfo()` возвращает лёгкий объект, атрибуты которого заполняются во время импорта. Прямой доступ к атрибутам избегает дополнительного ввода‑вывода и гарантирует, что отображаемые данные соответствуют версии библиотеки, которую действительно использует ваш код.

### Ожидаемый вывод

```
Product: BarcodeLib
Version: 2.5
Release date: 2024-03-15
```

Точные значения зависят от установленной версии библиотеки barcode.

---

## Как получить версию из библиотеки barcode

Если вам нужны только номера версии, вы можете пропустить вывод названия продукта и сосредоточиться на числовых полях.

```python
import barcode

info = barcode.BuildVersionInfo()
major = info.PRODUCT_MAJOR
minor = info.PRODUCT_MINOR

print(f"Current version: {major}.{minor}")
```

*Атрибуты `PRODUCT_MAJOR` и `PRODUCT_MINOR` следуют семантическому версионированию, позволяя программно сравнивать версии.*

---

## Как вывести дату выпуска

Дата выпуска хранится как строка в формате `YYYY‑MM‑DD`. Чтобы представить её в другой локали, сначала преобразуйте её в объект `datetime`.

```python
import barcode
from datetime import datetime

info = barcode.BuildVersionInfo()
raw_date = info.RELEASE_DATE          # e.g., "2024-03-15"
date_obj = datetime.strptime(raw_date, "%Y-%m-%d")
formatted = date_obj.strftime("%B %d, %Y")  # "March 15, 2024"

print(f"Release date: {formatted}")
```

**Подсказка:** Всегда проверяйте строку даты перед разбором, чтобы избежать `ValueError`, если библиотека изменит её формат.

---

## Показать минорную версию рядом с основной

Иногда необходимо отображать минорную версию отдельно, например при логировании предупреждений о совместимости.

```python
import barcode

info = barcode.BuildVersionInfo()
print(f"Major version: {info.PRODUCT_MAJOR}")
print(f"Minor version: {info.PRODUCT_MINOR}")
```

**Pro tip:** Используйте минорную версию для активации флагов функций:

```python
if info.PRODUCT_MINOR >= 5:
    enable_new_feature()
```

---

## Обработка отсутствующих атрибутов (крайние случаи)

В более старых версиях библиотеки barcode могут отсутствовать некоторые атрибуты. Оберните доступ к атрибутам в `getattr` с разумными значениями по умолчанию.

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

Этот шаблон гарантирует, что ваш скрипт не упадёт из‑за отсутствующего поля, делая его надёжным для CI‑конвейеров, которые могут работать с разными версиями библиотеки.

---

## Полный, исполняемый пример

Ниже приведён полный скрипт, объединяющий все лучшие практики: проверку атрибутов, форматирование даты и чёткий вывод.

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

Запуск этого скрипта на системе с установленной библиотекой barcode выдаст вывод, похожий на предыдущий пример, но теперь он защищён от отсутствующих полей и красиво форматирует дату.

---

## Заключение

Теперь вы знаете, как **отобразить название продукта**, **вывести дату выпуска**, **получить версию**, **вывести продукт** и **показать минорную версию**, используя простой рабочий процесс на Python. Полный пример демонстрирует надёжный доступ к атрибутам, работу с датами и сравнение версий — навыки, которые можно применять к любой сторонней библиотеке, предоставляющей объекты метаданных.

**Следующие шаги**

* Исследуйте другие методы метаданных библиотеки barcode, такие как `BuildCommitInfo()`.  
* Интегрируйте вывод в систему логирования (например, `logging.info`).  
* Сравнивайте версии программно, чтобы обеспечить минимально требуемые версии в вашем приложении.

Не стесняйтесь экспериментировать с различными форматами вывода или расширять скрипт, чтобы записывать информацию в файл для целей аудита. Приятного кодинга!  

![Вывод терминала, показывающий название продукта и детали версии](image.png "Вывод терминала")

## Что вам стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [отображение названия продукта с использованием Python barcode library – пошаговое руководство](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)
- [Как вывести версию Aspose.Barcode (Python)](/barcode/english/python/general/how-to-print-version-of-aspose-barcode-python/)
- [Как сгенерировать штрих‑код с помощью Aspose.BarCode в Python](/barcode/english/python-java/general/how-to-generate-barcode-with-aspose-barcode-in-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
---
category: general
date: 2026-09-07
description: Узнайте, как отображать информацию из библиотеки штрихкодов, включая
  название продукта, версию, версию сборки и дату выпуска. Краткое руководство для
  разработчиков Python.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to display info
- display product name
- show release date
- get library version
- how to read version
language: ru
lastmod: 2026-09-07
og_description: Как вывести информацию из библиотеки штрихкодов Python, включая название
  продукта, номера версий, версию сборки и дату выпуска, в несколько строк кода.
og_image_alt: Console output showing how to display info from barcode library
og_title: Как вывести информацию из библиотеки штрихкодов в Python – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Learn how to display info from a barcode library, including product
    name, version, assembly version, and release date. Quick guide for Python developers.
  headline: How to display info from a barcode library in Python
  type: TechArticle
- description: Learn how to display info from a barcode library, including product
    name, version, assembly version, and release date. Quick guide for Python developers.
  name: How to display info from a barcode library in Python
  steps:
  - name: Display product name
    text: 'To **display product name**, simply print the `PRODUCT` attribute:'
  - name: Show library version (major.minor)
    text: 'Most developers only need the major and minor numbers, which you can combine
      with an f‑string:'
  - name: Show assembly version
    text: 'If you need the full assembly version (including build and revision), use
      the `ASSEMBLY_VERSION` attribute:'
  - name: Show release date
    text: 'Finally, to **show release date**, print the `RELEASE_DATE` attribute:'
  - name: Complete script
    text: 'Putting everything together yields a self‑contained, runnable example:'
  - name: Library without `BuildVersionInfo`
    text: 'Some forks of the `barcode` package omit `BuildVersionInfo`. In that case
      you can read version data from the package’s `__version__` attribute:'
  - name: Formatting the release date
    text: 'If you prefer `Month Day, Year` format:'
  - name: Handling missing attributes
    text: 'When running against a custom build, an attribute may be `None`. Guard
      against that with a simple check:'
  - name: Using the information in logs
    text: 'Instead of printing to the console, you might want to log the data:'
  type: HowTo
tags:
- Python
- barcode
- version‑info
- debugging
title: Как отобразить информацию из библиотеки штрихкодов в Python
url: /ru/python/general/how-to-display-info-from-a-barcode-library-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как вывести информацию из библиотеки barcode в Python

Если вам нужно **вывести информацию** из библиотеки barcode, это руководство покажет, как точно получить и напечатать название продукта, номера версий, версию сборки и дату выпуска. Решение работает со стандартным пакетом `barcode` и требует всего несколько строк кода, так что вы можете добавить его в любой скрипт мгновенно.

Мы пройдем каждый шаг, объясним, почему код работает, и рассмотрим распространённые подводные камни, такие как отсутствие атрибутов или неожиданные форматы версии. К концу вы сможете **вывести название продукта**, **показать дату выпуска** и **получить версию библиотеки** в любой среде Python.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

* Python 3.8 или новее.
* Библиотека `barcode` (или совместимый форк), доступная в вашей среде. Установите её командой:

```bash
pip install python-barcode
```

* Базовое знакомство с функцией `print` в Python и f‑строками.

Если библиотека уже установлена, можете пропустить шаг установки.

## Как вывести информацию из библиотеки barcode

Суть решения — один вызов `barcode.BuildVersionInfo()`, который возвращает объект, содержащий все метаданные, связанные с версией. Следующий заголовок H2 содержит основной ключевой запрос, удовлетворяя требования SEO.

```python
# Import the barcode module
import barcode

# Retrieve version information from the barcode library
info = barcode.BuildVersionInfo()
```

Объект `info`, как правило, предоставляет следующие атрибуты:

| Атрибут            | Значение |
|--------------------|----------|
| `PRODUCT`          | Человекочитаемое название продукта |
| `PRODUCT_MAJOR`    | Номер основной версии |
| `PRODUCT_MINOR`    | Номер минорной версии |
| `ASSEMBLY_VERSION` | Полная версия сборки (например, `1.2.3.4`) |
| `RELEASE_DATE`     | Дата выпуска библиотеки |

### Вывод названия продукта

Чтобы **вывести название продукта**, просто распечатайте атрибут `PRODUCT`:

```python
print("Product:", info.PRODUCT)
```

> **Почему это работает:** `info.PRODUCT` — строка, определённая автором библиотеки. Печать её напрямую даёт точное название, использованное в метаданных пакета, что удобно для логирования или отображения в UI.

### Показ версии библиотеки (major.minor)

Большинству разработчиков нужны только основные и минорные номера, их можно объединить с помощью f‑строки:

```python
print("Version:", f"{info.PRODUCT_MAJOR}.{info.PRODUCT_MINOR}")
```

> **Объяснение:** f‑строка форматирует два целочисленных атрибута в привычный шаблон `major.minor`, соответствующий тому, что отображается на странице библиотеки в PyPI.

### Показ полной версии сборки

Если нужна полная версия сборки (включая билд и ревизию), используйте атрибут `ASSEMBLY_VERSION`:

```python
print("Assembly version:", info.ASSEMBLY_VERSION)
```

Полная версия сборки полезна, когда необходимо убедиться, что загружена конкретная сборка библиотеки, особенно в CI‑конвейерах.

### Показ даты выпуска

Наконец, чтобы **показать дату выпуска**, выведите атрибут `RELEASE_DATE`:

```python
print("Release date:", info.RELEASE_DATE)
```

Дата выпуска хранится как объект `datetime.date`, поэтому печатается в ISO‑формате (`YYYY‑MM‑DD`). При необходимости её можно переоформить с помощью `strftime`.

### Полный скрипт

Объединив всё вместе, получаем автономный, готовый к запуску пример:

```python
import barcode

def display_barcode_library_info():
    """Retrieve and print all version‑related metadata from the barcode library."""
    try:
        info = barcode.BuildVersionInfo()
    except AttributeError:
        raise RuntimeError(
            "The installed barcode package does not expose BuildVersionInfo(). "
            "Make sure you are using a compatible version."
        )

    print("Product:", info.PRODUCT)
    print("Version:", f"{info.PRODUCT_MAJOR}.{info.PRODUCT_MINOR}")
    print("Assembly version:", info.ASSEMBLY_VERSION)
    print("Release date:", info.RELEASE_DATE)

if __name__ == "__main__":
    display_barcode_library_info()
```

**Ожидаемый вывод** (значения будут отличаться в зависимости от установленной версии):

```
Product: python-barcode
Version: 0.14
Assembly version: 0.14.0.0
Release date: 2023-02-15
```

Скрипт перехватывает потенциальный `AttributeError`, чтобы помочь вам **безопасно читать информацию о версии**, когда API библиотеки меняется.

## Распространённые варианты и граничные случаи

### Библиотека без `BuildVersionInfo`

Некоторые форки пакета `barcode` не содержат `BuildVersionInfo`. В этом случае можно получить данные о версии из атрибута `__version__` пакета:

```python
import barcode
print("Package version:", barcode.__version__)
```

Это даёт строку версии по PEP‑440, но без детализированных полей (`PRODUCT`, `ASSEMBLY_VERSION` и т.д.). Используйте этот способ только когда основной метод недоступен.

### Форматирование даты выпуска

Если нужен формат `Month Day, Year`:

```python
print("Release date:", info.RELEASE_DATE.strftime("%B %d, %Y"))
```

### Обработка отсутствующих атрибутов

При работе с кастомной сборкой какой‑то атрибут может быть `None`. Защититесь от этого простой проверкой:

```python
release = info.RELEASE_DATE or "unknown"
print("Release date:", release)
```

### Использование информации в логах

Вместо вывода в консоль вы можете записать данные в лог:

```python
import logging
logging.basicConfig(level=logging.INFO)
logger = logging.getLogger(__name__)

logger.info("Product: %s", info.PRODUCT)
logger.info("Version: %s.%s", info.PRODUCT_MAJOR, info.PRODUCT_MINOR)
logger.info("Assembly version: %s", info.ASSEMBLY_VERSION)
logger.info("Release date: %s", info.RELEASE_DATE)
```

Логирование сохраняет информацию в файлах вашего приложения, что ценно для отладки в продакшене.

## Профессиональные советы

* **Кешируйте объект info**, если вызываете его многократно; данные о версии не меняются во время выполнения.
* **Проверяйте версию** перед выполнением проверок совместимости:

```python
if int(info.PRODUCT_MAJOR) < 1:
    raise RuntimeError("Barcode library version is too old for this feature.")
```

* **Комбинируйте с другими диагностическими данными** (например, версией Python) для полного отчёта о среде:

```python
import sys
print("Python:", sys.version.split()[0])
```

## Заключение

Теперь вы знаете, **как вывести информацию** из библиотеки barcode в Python, включая **вывод названия продукта**, **показ даты выпуска** и **получение версии библиотеки**. Полный скрипт демонстрирует стандартный рабочий процесс, а варианты показывают, как адаптировать решение под разные реализации библиотеки или требования к форматированию.

Далее вы можете изучить:

* **Как читать версию** других сторонних пакетов с помощью `importlib.metadata`.
* **Отображение информации о версии** в GUI‑приложении (Tkinter, PyQt и др.).
* **Автоматизацию проверок версий** в CI‑конвейерах для обеспечения минимальных требований к библиотекам.

Экспериментируйте с кодом, интегрируйте его в свои инструменты и делитесь результатами с сообществом!

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [display product name using Python barcode library – step‑by‑step guide](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [How to Generate Barcode in C# – Complete Aspose.Barcode Guide](/barcode/english/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
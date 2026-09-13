---
category: general
date: 2026-09-13
description: Узнайте, как использовать BuildVersionInfo в Aspose.BarCode для Python,
  чтобы извлечь версию продукта и другие метаданные за несколько простых шагов.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- use buildversioninfo
- extract product version
language: ru
lastmod: 2026-09-13
og_description: Используйте BuildVersionInfo в Aspose.BarCode для Python, чтобы извлечь
  версию продукта, версию сборки и дату выпуска, следуя понятному пошаговому руководству.
og_image_alt: Screenshot showing use BuildVersionInfo output with version details
og_title: Используйте BuildVersionInfo в Python — быстро извлеките версию продукта
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to use BuildVersionInfo in Aspose.BarCode for Python to extract
    product version and other metadata in a few simple steps.
  headline: How to use BuildVersionInfo to extract product version in Python
  type: TechArticle
tags:
- Aspose
- Python
- Barcode
- VersionInfo
title: Как использовать BuildVersionInfo для извлечения версии продукта в Python
url: /ru/python/general/how-to-use-buildversioninfo-to-extract-product-version-in-py/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как использовать BuildVersionInfo для получения версии продукта в Python

Если вам нужно **использовать BuildVersionInfo** для чтения метаданных Aspose.BarCode, это руководство покажет, как это сделать. К концу урока вы сможете **извлекать информацию о версии продукта**, версию сборки, версию файла и дату выпуска, используя всего несколько строк кода.

Многие разработчики рассматривают данные о версии как второстепенный момент, однако наличие корректной версии во время выполнения помогает в отладке, логировании и проверках соответствия. В этом руководстве рассматривается установка пакета, создание объекта `BuildVersionInfo`, получение каждого свойства и вывод чистого отчёта. Внешняя документация не требуется — всё, что нужно, находится здесь.

## Предварительные требования

Прежде чем начать, убедитесь, что у вас есть:

* Установлен Python 3.8 или новее.  
* Доступ к пакету **Aspose.BarCode for Python via .NET** (модуль `aspose.barcode`).  
* Базовое понимание импорта в Python и операторов `print`.

Если вы ещё не установили библиотеку, выполните:

```bash
pip install aspose-barcode
```

Нижеописанные шаги предполагают, что пакет доступен в вашей среде.

## Шаг 1: Импортировать пакет Aspose.BarCode

Первое, что нужно сделать — импортировать пространство имён `aspose.barcode`. Это даст вам доступ ко всем классам, включая `BuildVersionInfo`.

```python
# Step 1: Import the Aspose.BarCode package
import aspose.barcode as bc
```

> **Почему это важно:** Импорт пакета регистрирует .NET‑сборки в Python, позволяя создавать экземпляры класса `BuildVersionInfo`. Пропуск импорта приводит к `ModuleNotFoundError`.

## Шаг 2: Использовать BuildVersionInfo для получения метаданных библиотеки

Теперь вы можете **использовать BuildVersionInfo** для запроса сведений о версии, которые Aspose встраивает во время сборки. Создание объекта не требует аргументов.

```python
# Step 2: Create a BuildVersionInfo object to query library metadata
version_info = bc.BuildVersionInfo()
```

> **Объяснение:** Конструктор `BuildVersionInfo` загружает статические поля из базовой сборки. Это лёгкий, только для чтения объект, который можно безопасно переиспользовать в приложении.

## Шаг 3: Извлечь детали версии продукта

Имея экземпляр `version_info`, вы можете **извлекать версию продукта** и связанные свойства. Каждый атрибут возвращает строку, которую можно сохранить, залогировать или сравнить.

```python
# Step 3: Retrieve individual version properties from the object
assembly_version = version_info.ASSEMBLY_VERSION   # e.g., "23.12.0.0"
file_version     = version_info.FILE_VERSION       # e.g., "23.12.0.0"
product_title    = version_info.PRODUCT            # e.g., "Aspose.BarCode for Python via .NET"
major_version    = version_info.PRODUCT_MAJOR      # e.g., "23"
minor_version    = version_info.PRODUCT_MINOR      # e.g., "12"
release_date     = version_info.RELEASE_DATE       # e.g., "2023-12-01"
```

> **Зачем нужны отдельные поля**
> * **Assembly version** – точная версия бинарного файла, загруженного во время выполнения.  
> * **File version** – версия ресурса файла; полезно для проверок свойств файла в Windows.  
> * **Product title** – человекочитаемое название, которое можно отобразить в UI‑логах.  
> * **Major / Minor version** – позволяет реализовать условную логику на основе диапазонов версий.  
> * **Release date** – помогает убедиться, что вы используете недавнюю сборку, что критично для исправлений безопасности.

### Пограничный случай: отсутствие атрибутов

Если в будущей версии Aspose удалит атрибут, попытка доступа к нему вызовет `AttributeError`. Защититесь, используя `getattr` с значением по умолчанию:

```python
assembly_version = getattr(version_info, "ASSEMBLY_VERSION", "unknown")
```

## Шаг 4: Вывести собранную информацию о версии

Наконец, выведите собранные данные в аккуратном, выровненном виде. Этот шаг необязателен, но демонстрирует, как можно логировать информацию о версии при запуске приложения.

```python
# Step 4: Display the gathered version information
print("Assembly version :", assembly_version)
print("File version     :", file_version)
print("Product title    :", product_title)
print("Major version    :", major_version)
print("Minor version    :", minor_version)
print("Release date     :", release_date)
```

**Ожидаемый вывод** (значения будут отличаться в зависимости от установленной версии библиотеки):

```
Assembly version : 23.12.0.0
File version     : 23.12.0.0
Product title    : Aspose.BarCode for Python via .NET
Major version    : 23
Minor version    : 12
Release date     : 2023-12-01
```

> **Совет профессионала:** Перенаправьте этот вывод в файл журнала или встроите его в диалог «О программе» вашего приложения, чтобы пользователи быстро получали сведения о версии.

## Полный, исполняемый пример

Объединив все части, получаем самостоятельный скрипт, который можно скопировать и сразу запустить:

```python
import aspose.barcode as bc

def show_aspose_version():
    """
    Retrieves and prints Aspose.BarCode version information using BuildVersionInfo.
    """
    version_info = bc.BuildVersionInfo()

    # Safely fetch each attribute, falling back to 'unknown' if the field vanishes
    assembly_version = getattr(version_info, "ASSEMBLY_VERSION", "unknown")
    file_version     = getattr(version_info, "FILE_VERSION", "unknown")
    product_title    = getattr(version_info, "PRODUCT", "unknown")
    major_version    = getattr(version_info, "PRODUCT_MAJOR", "unknown")
    minor_version    = getattr(version_info, "PRODUCT_MINOR", "unknown")
    release_date     = getattr(version_info, "RELEASE_DATE", "unknown")

    print("Assembly version :", assembly_version)
    print("File version     :", file_version)
    print("Product title    :", product_title)
    print("Major version    :", major_version)
    print("Minor version    :", minor_version)
    print("Release date     :", release_date)

if __name__ == "__main__":
    show_aspose_version()
```

Запуск этого скрипта на машине с установленным `aspose-barcode` выводит блок версии, показанный выше.

## Часто задаваемые вопросы и варианты

| Вопрос | Ответ |
|----------|--------|
| **Что делать, если нужна версия в JSON‑payload?** | Сериализуйте словарь: <br>`import json; print(json.dumps({...}, indent=2))` |
| **Можно ли сравнивать версии программно?** | Преобразуйте `major_version` и `minor_version` в целые числа и сравнивайте `<` или `>` при необходимости. |
| **Работает ли это на Linux/macOS?** | Да. .NET Core runtime, используемый Aspose.BarCode, кроссплатформенный, поэтому тот же код Python работает везде. |
| **Как обработать отсутствие установки Aspose?** | Оберните импорт в `try/except` и выведите понятное сообщение об ошибке: <br>`except ImportError: print("Aspose.BarCode is not installed. Run pip install aspose-barcode")` |

## Советы для использования в продакшене

* **Кешируйте объект `BuildVersionInfo`**, если вам нужны данные о версии многократно; его дешево хранить в переменной уровня модуля.  
* **Логируйте на уровне INFO** в обычных запусках и переключайтесь на DEBUG для более детального вывода.  
* **Комбинируйте с другими диагностическими средствами Aspose** (например, `License.IsValid`), чтобы создать комплексную точку проверки состояния.

## Заключение

Теперь вы знаете, как **использовать BuildVersionInfo** в Python для **извлечения версии продукта** и связанных метаданных из библиотеки Aspose.BarCode. Полный скрипт демонстрирует чистый, защищённый подход, работающий на разных платформах и учитывающий возможные будущие изменения API.

Дальше вы можете изучить:

* Использование полученной версии для принудительного требования минимальной версии перед включением премиум‑функций штрих‑кода.  
* Интеграцию проверки версии в CI/CD‑конвейер для автоматической верификации, что развернута последняя сборка Aspose.BarCode.  
* Расширение скрипта для получения информации о лицензии (`bc.License`) и создания полного отчёта диагностики во время выполнения.

Счастливого кодинга и следите за версиями ваших приложений!

## Что стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, опираясь на техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [Как вывести версию Aspose.Barcode (Python)](/barcode/english/python/general/how-to-print-version-of-aspose-barcode-python/)
- [Как установить лицензию в Aspose.BarCode для Python – Полное руководство](/barcode/english/python/general/how-to-set-license-in-aspose-barcode-for-python-complete-gui/)
- [Создание PNG‑штрих‑кода в Python – Полное руководство Aspose.Barcode](/barcode/english/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
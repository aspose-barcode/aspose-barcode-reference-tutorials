---
category: general
date: 2026-11-27
description: Генерируйте QR‑штрихкоды в Python с помощью Aspose.Barcode и быстро научитесь
  сохранять изображение штрихкода на диск.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate QR barcode
- save barcode image
- Aspose.Barcode Python
- extended codetext QR
- barcode version information
language: ru
lastmod: 2026-11-27
og_description: Создайте QR‑штрихкод в Python с помощью Aspose.Barcode и мгновенно
  сохраните изображение штрихкода. Следуйте полному примеру, чтобы создавать, настраивать
  и сохранять QR‑коды.
og_image_alt: Screenshot of a generated QR barcode created with Python
og_title: Создайте QR‑код и сохраните изображение с помощью Python — пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Generate QR barcode in Python using Aspose.Barcode and learn how to
    save barcode image to disk quickly.
  headline: Generate QR barcode and save image with Python
  type: TechArticle
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: Создать QR‑код и сохранить изображение с помощью Python
url: /ru/python/general/generate-qr-barcode-and-save-image-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Генерация QR‑штрихкода и сохранение изображения с помощью Python

Если вам нужно **генерировать QR‑штрихкод** в приложении на Python, это руководство покажет, как сделать это с помощью библиотеки Aspose.Barcode. Вы также узнаете правильный способ **сохранения изображения штрихкода** в локальную папку, как получить сведения о версии библиотеки и как работать с расширенными сегментами codetext.

Создание QR‑кодов — распространённая задача для систем билетов, мобильных платежей и отслеживания товаров. К концу этого урока у вас будет готовый к запуску скрипт, который создаёт файл изображения QR‑штрихкода и выводит информацию о версии для отладки или соответствия требованиям.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

* Python 3.8 или новее.
* Пакет `aspose-barcode`. Установите его командой `pip install aspose-barcode`.
* Права на запись в каталог, где будет храниться изображение штрихкода.

Дополнительные внешние сервисы не требуются; весь процесс выполняется локально.

## Шаг 1: Создание расширенного codetext с помощью `ExtCodetextBuilder`

Расширенный codetext позволяет смешивать обычный текст и сегменты ECI (Extended Channel Interpretation) в одном QR‑коде. Это полезно, когда необходимо включить символы из разных наборов, например знак евро.

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# Create the builder instance
ext_builder = ExtCodetextBuilder()

# Add a plain text segment
ext_builder.add_plain_codetext("ABC123")

# Add an ECI segment that uses ISO‑IEC 8859‑1 (code page 3)
ext_builder.add_eci_codetext(3, "€123")
```

**Почему этот шаг важен:**  
`ExtCodetextBuilder` собирает окончательную строку, которую будет обрабатывать QR‑энкодер. Без построения расширенного codetext штрихкод будет содержать только обычные ASCII‑символы и не сможет представить локализованные символы.

## Шаг 2: Получение объединённой строки расширенного codetext

```python
# Get the final extended codetext that will be encoded
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

Вывод выглядит так:

```
Extended codetext: ABC123[ECI3]€123
```

Маркер в квадратных скобках `[ECI3]` сообщает QR‑энкодеру переключиться на указанный набор символов для последующих символов.

## Шаг 3: Генерация QR‑штрихкода с использованием расширенного codetext

```python
# Create a QR barcode generator with the extended codetext
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)
```

**Объяснение:**  
`BarcodeGenerator` принимает два аргумента: тип штрихкода (`QR`) и данные для кодирования (`extended_codetext`). Генератор подготавливает все внутренние структуры, необходимые для отрисовки.

## Шаг 4: Сохранение сгенерированного изображения штрихкода

```python
# Define the output path – adjust the folder as needed
output_path = "output/qr_extended.png"

# Save the image in PNG format
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")
```

**Почему стоит использовать такой подход:**  
Вызов `save` сразу записывает изображение на диск, определяя формат по расширению файла. Метод поддерживает PNG, JPEG, BMP и TIFF, что даёт гибкость для разных потребителей.

### Проверка сохранённого изображения

Откройте файл `output/qr_extended.png` любой программой‑просмотрщиком. Вы должны увидеть QR‑код, который при сканировании возвращает строку `ABC123€123`. Большинство современных мобильных сканеров автоматически обрабатывают сегмент ECI.

## Шаг 5: Запрос информации о версии Aspose.BarCode (необязательно, но полезно)

Знание точной версии библиотеки Aspose.BarCode помогает при сообщении об ошибках или проверке совместимости.

```python
# Retrieve version details
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Типичный вывод:

```
Aspose.BarCode version:
  Assembly version : 23.9.0.0
  File version     : 23.9.0
  Product          : Aspose.BarCode for Python via .NET
  Release date     : 2023-09-15
```

## Полный скрипт — скопируйте, вставьте и запустите

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# 1️⃣ Build extended codetext
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC123")
ext_builder.add_eci_codetext(3, "€123")
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 2️⃣ Generate QR barcode
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)

# 3️⃣ Save barcode image
output_path = "output/qr_extended.png"
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")

# 4️⃣ Display version information
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Запуск скрипта создаёт изображение QR‑кода и выводит как расширенный codetext, так и сведения о версии в консоль.

## Частые варианты и граничные случаи

| Ситуация | Рекомендуемая корректировка |
|-----------|------------------------|
| **Другой набор символов** | Измените идентификатор ECI, передаваемый в `add_eci_codetext`. Для UTF‑8 используйте `5`. |
| **Более высокий уровень коррекции ошибок** | Установите `barcode.parameters.barcode.qr_error_level = bc.QRErrorLevel.H` перед вызовом `save`. |
| **Пользовательский размер изображения** | Используйте `barcode.parameters.image_width` и `barcode.parameters.image_height` для задания размеров в пикселях. |
| **Не PNG‑вывод** | Измените расширение файла в `output_path` на `.jpg` или `.bmp`. Библиотека автоматически выберет нужный кодировщик. |

## Профессиональные советы

* **Создавайте папку вывода** программно, если она может отсутствовать:

  ```python
  import os
  os.makedirs(os.path.dirname(output_path), exist_ok=True)
  ```

* **Проверяйте QR‑код** после генерации, считав его обратно с помощью `aspose.barcode.BarcodeReader`. Это гарантирует, что закодированные данные соответствуют ожиданиям, особенно при использовании сегментов ECI.

  ```python
  reader = bc.BarcodeReader(output_path, bc.DecodeType.QR)
  for result in reader.read():
      print("Decoded text:", result.code_text)
  ```

* **Совет по производительности** — используйте один экземпляр `BarcodeGenerator`, если нужно генерировать множество QR‑кодов в цикле. Сбрасывайте свойство `code_text` вместо создания нового объекта на каждой итерации.

## Заключение

Теперь вы знаете, как **генерировать QR‑штрихкод** в Python с помощью Aspose.Barcode, как собрать расширенный codetext, смешивающий обычный текст и сегменты ECI, и как правильно **сохранять изображение штрихкода** на диск. Скрипт также демонстрирует, как получить информацию о версии библиотеки для устранения неполадок.

Дальнейшие шаги, которые вы можете изучить:

* Добавление логотипа или пользовательских цветов к QR‑коду.
* Встраивание QR‑штрихкода напрямую в PDF‑файлы с помощью Aspose.PDF.
* Автоматизация пакетной генерации для больших наборов данных.

Экспериментируйте с различными полезными нагрузками, уровнями коррекции ошибок и форматами изображений. Приятного кодинга!


## Что изучать дальше?


Следующие учебные материалы охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [How to generate Code 128 barcode and save barcode image with Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [How to generate DataMatrix barcode in Python with Aspose.BarCode](/barcode/english/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
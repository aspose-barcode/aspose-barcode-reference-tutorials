---
category: general
date: 2026-09-23
description: Узнайте, как генерировать штрих‑код Code 128 и сохранять изображение
  штрих‑кода с помощью Aspose.BarCode в Python — пошаговое руководство.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate code 128 barcode
- save barcode image
- Aspose.BarCode Python
- extended codetext builder
- barcode PNG export
language: ru
lastmod: 2026-09-23
og_description: Создайте штрих‑код Code 128 и сохраните его изображение с помощью
  Aspose.BarCode в Python. Следуйте этому полному примеру, чтобы создать, настроить
  и экспортировать штрих‑код в файл PNG.
og_image_alt: Python-generated Code 128 barcode saved as PNG image
og_title: Создание штрих‑кода Code 128 и сохранение изображения штрих‑кода – руководство
  по Python
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to generate Code 128 barcode and save barcode image using
    Aspose.BarCode in Python – step‑by‑step guide.
  headline: How to generate Code 128 barcode and save barcode image with Aspose.BarCode
  type: TechArticle
tags:
- barcode
- Code 128
- Python
- Aspose
title: Как сгенерировать штрих‑код Code 128 и сохранить изображение штрих‑кода с помощью
  Aspose.BarCode
url: /ru/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как сгенерировать штрих‑код Code 128 и сохранить изображение штрих‑кода с помощью Aspose.BarCode

Если вам нужно **сгенерировать штрих‑код Code 128** и **сохранить изображение штрих‑кода** в проекте Python, этот учебник покажет точные шаги. С помощью `ExtCodetextBuilder` из Aspose.BarCode вы можете встроить обычный текст и сегменты Unicode в один полезный груз, а затем отрисовать результат в виде PNG‑файла.

Вы увидите полностью готовый, исполняемый скрипт, объяснение каждой строки и советы по типичным подводным камням, таким как обработка кодировки ECI или выбор правильной папки вывода. Никакой внешней документации не требуется — просто скопируйте, вставьте и запустите.

## Предварительные требования

Прежде чем начать, убедитесь, что у вас есть:

* Python 3.8+ установлен.
* Пакет `aspose.barcode` (установите через `pip install aspose-barcode`).
* Права записи в каталог, где будет сохранён PNG.

Код работает с любой символьной системой, поддерживаемой Aspose.BarCode, но пример сосредоточен на **Code 128**, поскольку она эффективно кодирует буквенно‑цифровые данные и поддерживает расширенные наборы символов.

## Шаг 1: Импортировать необходимые классы

```python
import barcode                     # Core Aspose.BarCode namespace
from barcode import BarCodeWriter, BarCodeEncodeMode, BarCodeImageFormat
from barcode import ExtCodetextBuilder, BuildVersionInfo
```

*Зачем это нужно?* Импорт классов даёт доступ к построителю расширенного codetext, писателю, который создаёт изображение, и помощнику версии, который может быть полезен при отладке обновлений библиотеки.

## Шаг 2: Сформировать расширенный codetext

```python
# Create a builder for extended codetext
builder = ExtCodetextBuilder()

# Add plain text (no ECI) – this part is simple ASCII
builder.add_plain_codetext("ABC123")

# Add a Unicode segment with ECI 0x03 (UTF‑8). The word “Пример” means “Example” in Russian.
builder.add_eci_codetext(0x03, "Пример")

# Retrieve the full extended codetext string
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

`ExtCodetextBuilder` позволяет смешивать обычный ASCII и Unicode‑данные в одном полезном грузе штрих‑кода. Байтовый маркер ECI (Extended Channel Interpretation) `0x03` сообщает сканеру, что последующие байты закодированы в UTF‑8, что необходимо для языков вроде русского, китайского или арабского.

## Шаг 3: Настроить писатель штрих‑кода для Code 128

```python
writer = BarCodeWriter()
writer.encode_type = BarCodeEncodeMode.CODE_128   # Choose Code 128 symbology
writer.code_text = extended_codetext
```

Установка `encode_type` в `CODE_128` инструктирует писателя отрисовать **штрих‑код Code 128**. Свойство `code_text` получает расширенную строку, построенную на предыдущем шаге.

## Шаг 4: Сохранить изображение штрих‑кода в PNG

```python
output_path = "YOUR_DIRECTORY/extended_codetext.png"
writer.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode image saved to {output_path}")
```

Метод `save` записывает штрих‑код в файл. Использование `BarCodeImageFormat.PNG` обеспечивает безпотерьную компрессию и широкую совместимость с веб‑ и мобильными приложениями.

## Шаг 5 (необязательно): Проверить версию библиотеки Aspose.BarCode

```python
version_info = BuildVersionInfo()
print("Assembly version :", version_info.ASSEMBLY_VERSION)
print("Product version   :", f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR}")
print("Release date      :", version_info.RELEASE_DATE)
```

Знание точной версии библиотеки помогает при сообщении об ошибках или сравнении поведения между релизами.

## Ожидаемый результат

Запуск скрипта выдаёт вывод в консоль, похожий на:

```
Extended codetext: ABC123[ECI=03]Пример
Assembly version : 23.12.0.0
Product version   : 23.12
Release date      : 2023-12-01
Barcode image saved to YOUR_DIRECTORY/extended_codetext.png
```

Сгенерированный PNG (`extended_codetext.png`) выглядит так:

![Python‑сгенерированный штрих‑код Code 128, сохранённый как PNG‑изображение](images/code128_extended.png)

*Изображение показывает штрих‑код Code 128, который кодирует как ASCII‑строку `ABC123`, так и русское слово «Пример».*

## Часто задаваемые вопросы и обработка граничных случаев

| Вопрос | Ответ |
|----------|--------|
| **Можно ли использовать другую символьную систему?** | Да. Замените `BarCodeEncodeMode.CODE_128` на любой другой поддерживаемый режим, например `QR`, `EAN_13` или `PDF_417`. |
| **Что делать, если мой Unicode‑текст содержит эмодзи?** | Эмодзи также являются UTF‑8‑символами, поэтому тот же вызов `add_eci_codetext` работает. Убедитесь, что целевой сканер поддерживает используемый ECI. |
| **Как изменить размер изображения?** | Установите `writer.x_dimension` и `writer.bar_height` перед вызовом `save`. |
| **Какую папку использовать для `output_path`?** | Любую папку, в которую процесс Python может писать. Используйте `os.makedirs` с `exist_ok=True`, чтобы создать её автоматически. |

## Профессиональные советы

* **Избегайте жёстко заданных путей.** Используйте `os.path.join` и `Path` из модуля `pathlib` для кросс‑платформенной совместимости.
* **Проверьте штрих‑код.** После сохранения можно заново прочитать изображение с помощью `barcode.BarCodeReader`, чтобы убедиться, что закодированный текст совпадает с `extended_codetext`.
* **Совет по производительности.** Если генерируете множество штрих‑кодов в цикле, переиспользуйте один экземпляр `BarCodeWriter` и обновляйте только `code_text` на каждой итерации.

## Заключение

Теперь вы знаете, как **сгенерировать штрих‑код Code 128** с смешанными ASCII и Unicode‑данными и **сохранить изображение штрих‑кода** в PNG с помощью Aspose.BarCode в Python. Полный скрипт охватывает построение расширенного codetext, настройку писателя, экспорт изображения и проверку версии библиотеки.

Дальше вы можете исследовать:

* Добавление цветов переднего/фонового плана (`writer.back_color`, `writer.fore_color`).
* Встраивание штрих‑кода в PDF‑файлы с помощью `Aspose.PDF`.
* Использование класса `BarCodeReader` для декодирования сохранённого изображения и автоматической проверки содержимого.

Приятного кодинга, экспериментируйте с другими символьными системами и форматами изображений!

## Что изучать дальше?

Следующие учебники охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [Generate Code128 Barcode with Aspose.Barcode Python – Full Guide](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [How to generate barcode in Python – complete step‑by‑step guide](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
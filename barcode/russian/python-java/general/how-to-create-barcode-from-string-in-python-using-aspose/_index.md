---
category: general
date: 2026-10-15
description: Создайте штрих‑код из строки с помощью Aspose.Barcode для Python. Узнайте,
  как сгенерировать штрих‑код, задать размеры и сохранить его в формате PNG за считанные
  минуты.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from string
- how to generate barcode
- barcode generator example
- generate postal barcode
- aspose barcode python
language: ru
lastmod: 2026-10-15
og_description: Создайте штрих‑код из строки с помощью Aspose.Barcode для Python.
  Этот учебник покажет вам пошагово, как сгенерировать почтовый штрих‑код и сохранить
  его в формате PNG.
og_image_alt: Screenshot of a generated postal barcode saved as PNG
og_title: Создание штрихкода из строки в Python – руководство Aspose
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode from string with Aspose.Barcode for Python. Learn how
    to generate barcode, set dimensions, and save as PNG in minutes.
  headline: How to create barcode from string in Python using Aspose
  type: TechArticle
tags:
- barcode
- python
- Aspose
title: Как создать штрих‑код из строки в Python с помощью Aspose
url: /ru/python-java/general/how-to-create-barcode-from-string-in-python-using-aspose/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать штрих‑код из строки в Python с помощью Aspose

Если вам нужно **быстро создать штрих‑код из строки**, Aspose.Barcode for Python делает это простым. В этом руководстве вы увидите, как **генерировать изображения штрих‑кода**, настроить X‑размер и сохранить результат в файл PNG — всё это с помощью нескольких строк кода.

Вы также получите полный **пример генератора штрих‑кода**, который можно скопировать и вставить в свой проект. Не требуется внешних скриптов или сложных настроек, а руководство работает с текущей версией Aspose.Barcode 23.10.

## Требования

Прежде чем начать, убедитесь, что у вас есть:

- Python 3.8+ установленный на вашем компьютере  
- Действующая лицензия Aspose.Barcode for Python (бесплатная пробная версия подходит для оценки)  
- Выполненная команда `pip install aspose-barcode` в вашем виртуальном окружении  

Эти пункты гарантируют, что код запустится без ошибок импорта.

## Создание штрих‑кода из строки с Aspose.Barcode (Python)

Первый шаг — создать экземпляр `BarcodeGenerator` с нужной символьностью; в данном случае это почтовый штрих‑код **Planet**, а также строка, которую вы хотите закодировать.

```python
# Step 1: Import the required classes
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 2: Create a barcode generator for the Planet symbology with data "123456"
# This is the core of the "create barcode from string" operation.
generator = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

**Почему это важно:**  
`EncodeTypes.Planet` указывает Aspose использовать символьность Planet, предназначенную для сортировки почты в многих странах. Второй аргумент (`"123456"`) — это исходная строка, которая будет закодирована в штрих‑коде. Изменив это значение, вы сможете **создать штрих‑код из строки** для любого почтового индекса или номера отслеживания.

## Как генерировать штрих‑код с пользовательскими размерами

Ширина модуля почтового штрих‑кода (X‑размер) часто должна соответствовать требованиям печати. Aspose позволяет задать ширину в пикселях, автоматически рассчитывая высоту.

```python
# Step 3: Set the X dimension (module width) in pixels; height is calculated automatically
generator.parameters.barcode.x_dimension.pixels = 4
```

**Зачем это может понадобиться:**  
Большой X‑размер делает полосы толще, что повышает надёжность сканирования на принтерах с низким разрешением. Меньшее значение уменьшает размер изображения для веб‑использования. Эта строка демонстрирует **как генерировать штрих‑код** изображениями, соответствующими точным требованиям к размеру.

## Сохранение изображения штрих‑кода

После настройки генератора достаточно вызвать `save`. Метод принимает путь к файлу и желаемый формат изображения.

```python
# Step 4: Save the generated barcode as a PNG image
output_path = "YOUR_DIRECTORY/PostalPlanetAuto.png"
generator.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_path}")
```

**Что вы получите:**  
Файл PNG с именем `PostalPlanetAuto.png`, содержащий штрих‑код Planet, кодирующий `"123456"`. Вы можете открыть файл в любом просмотрщике изображений, чтобы проверить результат.

![Снимок сгенерированного почтового штрих‑кода, сохранённого как PNG](barcode_example.png){.align-center alt="Снимок сгенерированного почтового штрих‑кода, сохранённого как PNG"}

## Полный пример генератора штрих‑кода

Ниже представлен полностью готовый к запуску скрипт, включающий все шаги, описанные выше. Скопируйте его в файл `generate_postal_barcode.py` и выполните `python generate_postal_barcode.py`.

```python
# generate_postal_barcode.py
# -------------------------------------------------
# Complete example that shows how to create barcode from string,
# set custom dimensions, and save the result as PNG using Aspose.Barcode for Python.
# -------------------------------------------------

from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def create_postal_barcode(data: str, output_file: str, x_dim_pixels: int = 4):
    """
    Generates a Planet postal barcode from the supplied string.

    Args:
        data: The raw string to encode (e.g., "123456").
        output_file: Full path where the PNG image will be saved.
        x_dim_pixels: Desired X dimension in pixels (default = 4).

    Returns:
        None. The PNG file is written to disk.
    """
    # Validate data length for Planet symbology (6‑digit numeric is standard)
    if not data.isdigit() or len(data) != 6:
        raise ValueError("Planet barcode requires a 6‑digit numeric string.")

    # Create the generator (this is the core of create barcode from string)
    generator = BarcodeGenerator(EncodeTypes.Planet, data)

    # Adjust module width; height is calculated automatically
    generator.parameters.barcode.x_dimension.pixels = x_dim_pixels

    # Save as PNG
    generator.save(output_file, BarCodeImageFormat.PNG)
    print(f"Barcode saved to {output_file}")

if __name__ == "__main__":
    # Example usage – you can change the values to test other strings
    try:
        create_postal_barcode(
            data="123456",
            output_file="PostalPlanetAuto.png",
            x_dim_pixels=4
        )
    except Exception as e:
        print(f"Error generating barcode: {e}")
```

### Ожидаемый вывод

Запуск скрипта выдаёт:

```
Barcode saved to PostalPlanetAuto.png
```

…и создаёт файл `PostalPlanetAuto.png`, выглядящий так:

![Сгенерированный штрих‑код Planet](barcode_example.png){.align-center alt="Сгенерированный штрих‑код Planet, сохранённый как PNG"}

## Распространённые варианты и граничные случаи

| Ситуация | Что изменить | Почему |
|-----------|----------------|-----|
| **Другая символьность** (например, Code128) | Заменить `EncodeTypes.Planet` на `EncodeTypes.Code128` | Позволяет **генерировать штрих‑код** для инвентарных меток, а не только для почтовых индексов. |
| **Более длинные строки данных** | Убедиться, что выбранная символьность поддерживает нужную длину; для Planet требуется ровно 6 цифр. | Предотвращает возникновение `ValueError` во время выполнения. |
| **Более высокое разрешение** | Увеличить `x_dimension.pixels` до 6 или 8. | Делает полосы толще для печати с высоким DPI. |
| **Другие форматы изображений** | Использовать `BarCodeImageFormat.JPEG` или `BarCodeImageFormat.GIF`. | Полезно, когда PNG не подходит для вашего рабочего процесса. |
| **Запуск в веб‑службе** | Заменить вызов `save` файловой системы на поток `BytesIO` и вернуть байты. | Позволяет генерировать штрих‑коды «на лету» в Flask или Django. |

**Полезный совет:** Всегда проверяйте входную строку перед вызовом `BarcodeGenerator`. Неправильные данные (неверная длина, недопустимые символы для Planet) вызовут исключение и прервут работу приложения.

## Как генерировать штрих‑код в endpoint Flask (опциональный следующий шаг)

Если вы хотите открыть **пример генератора штрих‑кода** как REST API, можно обернуть функцию `create_postal_barcode`:

```python
from flask import Flask, send_file, request, abort
import io

app = Flask(__name__)

@app.route("/barcode", methods=["GET"])
def barcode_endpoint():
    data = request.args.get("data", "123456")
    try:
        # Generate barcode into an in‑memory stream
        stream = io.BytesIO()
        generator = BarcodeGenerator(EncodeTypes.Planet, data)
        generator.parameters.barcode.x_dimension.pixels = 4
        generator.save(stream, BarCodeImageFormat.PNG)
        stream.seek(0)
        return send_file(stream, mimetype="image/png", as_attachment=False)
    except Exception as exc:
        abort(400, str(exc))

if __name__ == "__main__":
    app.run(debug=True)
```

Этот фрагмент показывает, как **генерировать штрих‑код** по запросу без записи на диск, что удобно для микросервисов.

## Заключение

Теперь вы знаете, как **создать штрих‑код из строки** в Python с помощью Aspose.Barcode, как **генерировать штрих‑код** с пользовательскими размерами и как **сохранить** результат в файл PNG. Полный **пример генератора штрих‑кода** включает проверку входных данных, обработку ошибок и переиспользуемую функцию, которую можно интегрировать в более крупные приложения.

Далее изучайте другие символьности (`EncodeTypes.Code128`, `EncodeTypes.QR`) или внедряйте генератор в веб‑фреймворки, такие как Flask или Django. Оба шага углубят ваше понимание библиотеки **aspose barcode python** и расширят возможности **генерации почтовых штрих‑кодов** для реальных проектов.

## Что изучать дальше?

Следующие руководства охватывают тесно связанные темы, которые опираются на техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, помогая вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [Как генерировать штрих‑код в Python – полное пошаговое руководство](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Создание штрих‑кода PNG в Python – полный справочник Aspose.Barcode](/barcode/english/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/)
- [Как генерировать штрих‑код с ECI, используя Aspose.Barcode Python](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
---
category: general
date: 2026-11-20
description: Узнайте, как использовать ECI, генерировать QR из текста, очищать билдер
  и сохранять изображение QR с помощью библиотеки Python barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use eci
- generate qr from text
- how to clear builder
- save qr image
- clear qr builder
language: ru
lastmod: 2026-11-20
og_description: Как использовать ECI для генерации QR из текста, очистки конструктора
  QR и сохранения изображения QR — полное пошаговое руководство.
og_image_alt: Diagram illustrating how to use ECI to generate a QR code and save the
  QR image
og_title: Как использовать ECI при генерации QR‑кода с помощью Python
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to use ECI, generate QR from text, clear the builder, and
    save QR image using the Python barcode library.
  headline: How to use ECI in QR code generation with Python
  type: TechArticle
tags:
- QR code
- Python
- barcode
- ECI
title: Как использовать ECI при генерации QR‑кода с помощью Python
url: /ru/python/general/how-to-use-eci-in-qr-code-generation-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как использовать ECI при генерации QR-кода с помощью Python

Если вам нужно **how to use eci** при создании QR‑кодов, это руководство покажет точные шаги. Вы увидите, как генерировать QR из текста, очистить builder и, наконец, сохранить изображение QR — всё с помощью нескольких строк кода на Python.

QR‑коды, содержащие многоязычные данные, часто требуют сегмента Extended Channel Interpretation (ECI), чтобы сканеры знали, какой набор символов применять. В этом руководстве мы пройдем процесс создания расширенного codetext, очистки builder при повторном использовании и сохранения результата в файл PNG.

## Требования

- Установлен Python 3.8+.
- Пакет Aspose.BarCode for Python via .NET (или любая совместимая библиотека `barcode`, предоставляющая `ExtCodetextBuilder` и `BarcodeGenerator`).
- Базовое знакомство с концепциями QR‑кодов.

Установите библиотеку с помощью pip:

```bash
pip install aspose-barcode
```

> **Pro tip:** Используйте виртуальное окружение, чтобы избежать конфликтов версий.

## Шаг 1: Импортировать необходимые классы

Основные классы, с которыми вы будете работать, — `ExtCodetextBuilder` для построения расширенного codetext и `BarcodeGenerator` для рендеринга QR‑кода.

```python
from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
```

Эти импорты дают вам доступ к методам builder (`add_plain_codetext`, `add_eci_codetext` и т.д.) и функциям генератора `set_code_text`, `set_symbology` и `save`.

## Шаг 2: Создать и настроить ExtCodetextBuilder

Создание нового экземпляра builder — первый конкретный пример **how to use eci**. Вы также можете очистить builder позже, если нужно повторно использовать его.

```python
# Create an ExtCodetextBuilder instance
extended_text_builder = ExtCodetextBuilder()

# Optional: clear any previous items (useful when reusing the same builder)
extended_text_builder.clear()   # this demonstrates how to clear builder
```

Вызов `clear()` гарантирует, что builder начнёт с чистого состояния, что необходимо при генерации нескольких QR‑кодов в цикле.

## Шаг 3: Добавить обычный (не‑ECI) codetext

Обычный текст не требует сегмента ECI. Используйте `add_plain_codetext` для строк, совместимых с ASCII.

```python
# Add plain codetext (e.g., an English phrase)
extended_text_builder.add_plain_codetext("HelloWorld")
```

Теперь builder содержит обычный сегмент "HelloWorld".

## Шаг 4: Добавить сегмент, закодированный с ECI

Это основа **how to use eci**: вы указываете значение ECI (26 для UTF‑8) и предоставляете Unicode‑строку, которую хотите закодировать. Это позволяет QR‑коду содержать русский, китайский или любой другой язык, не покрытый набором по умолчанию ISO‑8859‑1.

```python
# Add ECI‑encoded codetext (ECI value 26 = UTF‑8, Russian “Hello”)
extended_text_builder.add_eci_codetext(26, "Привет")
```

> **Why this matters:** Без индикатора ECI сканер будет интерпретировать байты с использованием набора символов по умолчанию и отображать искажённые символы для текста, не являющегося ASCII.

## Шаг 5: Получить объединённую строку расширенного codetext

После добавления всех необходимых сегментов получите окончательную строку, которая будет передана генератору QR.

```python
combined_extended_text = extended_text_builder.get_extended_codetext()
print("Extended codetext:", combined_extended_text)
```

Выведенное значение выглядит примерно так:

```
Extended codetext: [ECI26]ПриветHelloWorld
```

Точный формат зависит от библиотеки, но важная часть — маркер ECI (`[ECI26]`) предшествует полезной нагрузке UTF‑8.

## Шаг 6: Сгенерировать QR‑код, используя объединённый текст

Теперь вы можете **generate QR from text**, передавая расширенный codetext в `BarcodeGenerator`.

```python
# Initialize the QR generator
qr_generator = barcode.generation.BarcodeGenerator()

# Assign the combined extended codetext
qr_generator.set_code_text(combined_extended_text)

# Choose QR symbology (the library supports many, QR is the most common)
qr_generator.set_symbology(barcode.Symbology.QR)

# Save the QR image to disk – this demonstrates how to save QR image
output_path = "qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

Когда вы откроете `qr_extended.png`, появится QR‑код, который кодирует как обычную английскую строку, так и русское приветствие. Сканирование его современным QR‑сканером корректно отобразит “HelloWorld” и “Привет”.

### Почему следует вызывать `clear()` перед повторным использованием builder

Если вы генерируете несколько QR‑кодов в цикле, забыв очистить builder, вы соедините старые сегменты с новыми, получив недействительный код. Вот быстрый шаблон:

```python
for text, eci, unicode_str in data_set:
    extended_text_builder.clear()                       # ensures a fresh start
    extended_text_builder.add_plain_codetext(text)
    extended_text_builder.add_eci_codetext(eci, unicode_str)
    qr_generator.set_code_text(extended_text_builder.get_extended_codetext())
    qr_generator.save(f"qr_{text}.png")
```

Этот фрагмент иллюстрирует **how to clear builder** и **how to generate QR from text** многократно.

## Пограничные случаи и распространённые подводные камни

| Ситуация | На что обратить внимание | Как действовать |
|-----------|-------------------|---------------|
| **Неподдерживаемое значение ECI** | Библиотека бросает `InvalidArgumentException`. | Используйте только значения ECI, перечисленные в спецификации (например, 26 для UTF‑8, 20 для Shift‑JIS). |
| **Очень длинный объединённый текст** | Версия QR может превысить максимальную ёмкость. | Увеличьте версию QR автоматически (`qr_generator.set_qr_version(QRVersion.AUTO)`) или разбейте данные на несколько QR‑кодов. |
| **Ошибки прав доступа к файловой системе** | `save` завершится с ошибкой `IOError`. | Убедитесь, что целевой каталог существует и процесс имеет права на запись. |
| **Неправильное отображение кодировки** | Сканер показывает искажённые символы. | Проверьте, что выбранное значение ECI соответствует реальной кодировке строки. |

## Полный исполняемый пример

Ниже представлен автономный скрипт, который вы можете скопировать, вставить и запустить. Он включает все импорты, обработку ошибок и комментарии для ясности.

```python
# qr_eci_example.py
# Demonstrates how to use ECI, generate QR from text, clear the builder,
# and save QR image using Aspose.BarCode for Python.

from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
import os

def generate_qr(plain_text: str, eci_value: int, unicode_text: str, out_file: str):
    """
    Creates a QR code that contains both plain and ECI‑encoded text.
    Parameters:
        plain_text – ASCII‑compatible string.
        eci_value  – Numeric ECI identifier (e.g., 26 for UTF‑8).
        unicode_text – Text that requires the specified ECI.
        out_file – Destination file path for the PNG image.
    """
    # Step 1: instantiate and clear the builder
    builder = ExtCodetextBuilder()
    builder.clear()                       # how to clear builder

    # Step 2: add segments
    builder.add_plain_codetext(plain_text)
    builder.add_eci_codetext(eci_value, unicode_text)

    # Step 3: retrieve combined text
    combined = builder.get_extended_codetext()
    print("Combined extended codetext:", combined)

    # Step 4: generate QR code
    generator = barcode.generation.BarcodeGenerator()
    generator.set_code_text(combined)
    generator.set_symbology(barcode.Symbology.QR)

    # Ensure output directory exists
    os.makedirs(os.path.dirname(out_file), exist_ok=True)

    # Step 5: save QR image – how to save QR image
    generator.save(out_file)
    print(f"QR code saved as {out_file}")

if __name__ == "__main__":
    # Example usage
    generate_qr(
        plain_text="HelloWorld",
        eci_value=26,               # UTF‑8
        unicode_text="Привет",      # Russian "Hello"
        out_file="output/qr_extended.png"
    )
```

Запуск этого скрипта создаст `output/qr_extended.png` — QR‑код, который корректно кодирует как английский, так и русский текст.

## Заключение

Теперь вы знаете **how to use eci** при построении QR‑кодов, как **clear the QR builder** перед повторным использованием, как **generate QR from text**, и точные шаги для **save QR image** с помощью Python. Следуя приведённому шаблону, вы можете внедрять любую Unicode‑строку в QR‑код, сохраняя предсказуемое состояние builder.

### Что дальше?

- Изучите другие значения ECI для языков, таких как китайский (ECI 20) или ISO‑8859‑5.
- Настройте уровни коррекции ошибок (`qr_generator.set_error_correction_level`), чтобы повысить надёжность сканирования.
- Объедините несколько сегментов ECI в одном QR‑коде для сообщений на нескольких языках.

Удачной разработки и приятного создания многоязычных QR‑кодов!

## Что вам стоит изучить дальше?

Следующие учебники охватывают тесно связанные темы, опирающиеся на техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как сгенерировать штрих‑код с ECI, используя Aspose.Barcode Python](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)
- [Как сгенерировать изображение QR‑кода в Python с Aspose.Barcode – Полное руководство](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Как сгенерировать штрих‑код в Python – полное пошаговое руководство](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
---
category: general
date: 2026-11-27
description: Узнайте, как создать штрих‑код с текстом и сгенерировать планетарный
  штрих‑код в Python — пошаговое руководство для получения PNG высокого разрешения.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode with text
- how to generate barcode
- generate planet barcode
- Python barcode generation
- high‑resolution barcode PNG
language: ru
lastmod: 2026-11-27
og_description: Создайте штрих‑код с текстом и сгенерируйте планетарный штрих‑код
  на Python. Следуйте этому полному руководству, чтобы получить PNG высокого разрешения.
og_image_alt: Screenshot showing how to create barcode with text using the Planet
  barcode generator
og_title: Создайте штрих‑код с текстом в Python — легко генерируйте штрих‑код Planet
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
title: Как создать штрих‑код с текстом, используя формат Planet в Python
url: /ru/python-java/general/how-to-create-barcode-with-text-using-the-planet-format-in-p/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать штрих‑код с текстом в формате Planet на Python

Если вам нужно **создать штрих‑код с текстом** для почтовой системы, этот учебник покажет вам точно, как это сделать. Вы увидите лаконичный, полный пример, который генерирует штрих‑код Planet, регулирует разрешение и сохраняет результат в виде PNG‑изображения.

Генерация штрих‑кодов — распространённая задача для логистики, учёта и систем билетирования. В этом руководстве вы узнаете не только **как генерировать файлы штрих‑кода**, но и почему каждый шаг конфигурации важен и как избежать типичных ошибок.

## Чего вы научитесь

* Настроить генератор штрих‑кода Planet с пользовательским текстом.  
* Отрегулировать X‑размер для повышения чёткости изображения.  
* Сохранить штрих‑код в PNG‑файле, который можно распечатать или отобразить в вебе.  
* Расширить пример для других типов штрих‑кодов или форматов вывода.

**Prerequisites**

* Python 3.8 или новее.  
* Пакет `aspose-barcode` (или любая совместимая библиотека, предоставляющая `BarcodeGenerator`, `EncodeTypes` и `BarCodeImageFormat`).  
* Базовое знакомство с написанием скриптов на Python.

Вы можете установить необходимый пакет с помощью:

```bash
pip install aspose-barcode
```

---

## Шаг 1: Создать штрих‑код с текстом – инициализировать генератор

Первое, что нужно сделать, – создать экземпляр `BarcodeGenerator`, который знает, какую символьную систему использовать и какой текст кодировать. Для штрих‑кода Planet значение перечисления `EncodeTypes.Planet` указывает библиотеке следовать спецификации USPS Planet.

```python
# Import the necessary classes from the Aspose.BarCode library
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1: Initialize the generator with the desired text
# The text "123456" will appear beneath the Planet barcode pattern.
gen = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

**Why this matters:**  
Объект `BarcodeGenerator` инкапсулирует все настройки штрих‑кода. Передача текста при создании гарантирует, что закодированное значение будет неизменным на протяжении всего процесса, что исключает случайные несоответствия позже.

---

## Шаг 2: Настроить параметры – как генерировать штрих‑код с более высоким разрешением

Штрих‑код низкого разрешения может выглядеть размытым при печати на этикеточном принтере. X‑размер (ширина модуля) контролирует размер каждой отдельной полосы. Установка значения в 4 пикселя даёт чёткое, высокоразрешённое изображение, подходящее для большинства современных принтеров.

```python
# Step 2: Increase the X‑dimension to 4 pixels for better clarity
gen.parameters.barcode.x_dimension.pixels = 4
```

**Explanation:**  
* `gen.parameters.barcode.x_dimension.pixels` напрямую соответствует физической ширине одного модуля.  
* Значение **4** означает, что каждая полоса шириной четыре пикселя, что приблизительно соответствует 0.127 мм при 300 dpi — в пределах рекомендованного диапазона для штрих‑кодов USPS Planet.  

**Pro tip:** Если нужен другой DPI, рассчитайте ширину в пикселях соответственно (например, 2 пикселя для 150 dpi, 8 пикселей для 600 dpi).

---

## Шаг 3: Сохранить изображение – сгенерировать штрих‑код Planet в PNG

Теперь, когда генератор настроен, вы можете отрисовать штрих‑код в файл изображения. PNG — без потерь, что гарантирует сохранение точного шаблона модулей.

```python
# Step 3: Save the generated barcode as a PNG image
output_path = "output/PostalPlanetBarHeightNone.png"
gen.save(output_path, BarCodeImageFormat.Png)
print(f"Barcode saved to {output_path}")
```

**Result:**  
Запуск скрипта создаёт файл с именем `PostalPlanetBarHeightNone.png`, содержащий штрих‑код Planet, кодирующий строку «123456». Размеры изображения будут примерно 200 × 100 пикселей, в зависимости от выбранного X‑размера.

---

## Опционально: Визуальная проверка штрих‑кода

Вы можете быстро открыть сгенерированный PNG в любом просмотрщике изображений, чтобы убедиться, что штрих‑код выглядит чётко и человекочитаемый текст присутствует под шаблоном.

```python
from PIL import Image

img = Image.open(output_path)
img.show()
```

Если изображение выглядит размытым, вернитесь к **Шагу 2** и увеличьте X‑размер, пока полосы не станут явно определёнными.

---

## Распространённые варианты и граничные случаи

| Ситуация | Корректировка |
|-----------|------------|
| **Разная длина текста** | Штрих‑коды Planet поддерживают до 12 цифровых символов. При превышении этого лимита библиотека выдаст исключение. |
| **Альтернативный формат вывода** | Замените `BarCodeImageFormat.Png` на `BarCodeImageFormat.Jpeg` или `BarCodeImageFormat.Bmp` для других сценариев. |
| **Пользовательские цвета переднего/фонового плана** | Используйте `gen.parameters.barcode.barcode_color = Color.Blue` и `gen.parameters.barcode.back_color = Color.White`. |
| **Без человекочитаемого текста** | Установите `gen.parameters.barcode.hide_code_text = True`, чтобы генерировать штрих‑код без подписи снизу. |
| **Пакетная генерация** | Пройдитесь по списку строк, создайте новый `BarcodeGenerator` для каждой и сохраните их в файлы с уникальными именами. |

Эти варианты позволяют вам **генерировать штрих‑коды Planet**, подходящие для широкого спектра бизнес‑требований.

---

## Полный скрипт – готов к запуску

Ниже представлен полностью автономный скрипт, который вы можете скопировать, вставить и выполнить. В нём включены все импорты, обработка ошибок и комментарии.

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

**Explanation of the script**

* Функция `create_planet_barcode` инкапсулирует три основных шага, делая код переиспользуемым.  
* Проверка входных данных гарантирует соблюдение спецификации Planet (только цифры, максимум 12 знаков).  
* Функция автоматически создаёт выходную папку, так что вам не придётся вручную управлять каталогами.  
* После генерации скрипт открывает изображение с помощью Pillow (`PIL`) для мгновенной проверки.

---

## Заключение

Теперь вы знаете, как **создать штрих‑код с текстом** и **генерировать файлы штрих‑кода Planet** на Python. Руководство охватило инициализацию, настройку разрешения и вывод в файл, а также дополнительные настройки и типичные граничные случаи.  

Дальше вы можете:

* Заменить `EncodeTypes.Planet` на другие символьные системы (например, `EncodeTypes.Code128`), чтобы переиспользовать тот же шаблон.  
* Интегрировать функцию в веб‑службу, возвращающую изображения штрих‑кодов по запросу.  
* Поэкспериментировать с пакетной обработкой для создания тысяч штрих‑кодов для массовой рассылки.

Не стесняйтесь адаптировать скрипт под нужды вашего проекта и делиться результатами в комментариях. Приятного кодинга!

## Что изучать дальше?

Следующие учебники охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогая вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [Как генерировать штрих‑код в Python – полный пошаговый гид](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Создать PNG‑штрих‑код в Python – пошаговый гид](/barcode/english/python-java/general/create-barcode-png-in-python-step-by-step-guide/)
- [Как создать PNG‑штрих‑код Planet с помощью Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
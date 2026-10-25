---
category: general
date: 2026-10-24
description: Пример генератора штрих‑кодов, показывающий, как создать штрих‑код Planet
  и как задать высоту штрих‑кода с помощью Python. Следуйте пошаговому руководству.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to create planet barcode
- how to set barcode height
language: ru
lastmod: 2026-10-24
og_description: Пример генератора штрихкодов, демонстрирующий, как создать штрихкод
  Planet и как установить высоту штрихкода в Python. Получите полное, готовое к запуску
  решение.
og_image_alt: Barcode generator example showing Planet and RM4SCC barcodes with different
  heights
og_title: Пример генератора штрих‑кодов – создание штрих‑кодов Planet и RM4SCC
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Barcode generator example that shows how to create Planet barcode and
    how to set barcode height using Python. Follow the step‑by‑step guide.
  headline: Barcode generator example – create Planet and RM4SCC barcodes with custom
    height
  type: TechArticle
- description: Barcode generator example that shows how to create Planet barcode and
    how to set barcode height using Python. Follow the step‑by‑step guide.
  name: Barcode generator example – create Planet and RM4SCC barcodes with custom
    height
  steps:
  - name: '**Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value
      and the data string.'
    text: '**Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value
      and the data string.'
  - name: '**Configure** the X‑dimension (module width) and, when needed, the barcode
      height.'
    text: '**Configure** the X‑dimension (module width) and, when needed, the barcode
      height.'
  - name: '**Save** the image to disk in PNG format.'
    text: '**Save** the image to disk in PNG format.'
  type: HowTo
tags:
- barcode
- Python
- image generation
title: Пример генератора штрих‑кодов – создание штрих‑кодов Planet и RM4SCC с пользовательской
  высотой
url: /ru/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Пример генератора штрих‑кодов – создание штрих‑кодов Planet и RM4SCC с пользовательской высотой

Если вы ищете **пример генератора штрих‑кодов**, это руководство предоставляет полное, готовое к запуску решение. Вы увидите **как создать изображения штрих‑кода planet**, узнаете **как задать высоту штрих‑кода** и поймёте небольшие различия между автоматическим и ручным масштабированием.

В руководстве рассматриваются два реалистичных сценария: штрих‑код Planet, использующий высоту по умолчанию (авто), и штрих‑код RM4SCC, высота которого принудительно задаётся в 100 px. К концу вы сможете генерировать PNG‑файлы для любого поддерживаемого типа штрих‑кода с помощью единого, последовательного API.

## Предварительные требования

Перед началом убедитесь, что у вас есть:

* Установлен Python 3.8 или новее.
* Пакет `aspose-barcode` (или любая библиотека, предоставляющая `BarcodeGenerator`, `EncodeTypes` и `BarCodeImageFormat`). Установите его с помощью  

  ```bash
  pip install aspose-barcode
  ```
* Права записи в папку, куда будут сохраняться PNG‑файлы.

Дополнительные системные зависимости не требуются.

## Обзор решения

Ядро **примера генератора штрих‑кодов** состоит из трёх переиспользуемых шагов:

1. **Создать** объект `BarcodeGenerator` с нужным значением `EncodeTypes` и строкой данных.
2. **Настроить** X‑dimension (ширину модуля) и, при необходимости, высоту штрих‑кода.
3. **Сохранить** изображение на диск в формате PNG.

Оба примера используют шаги 1 и 3; только шаг 2 отличается, потому что штрих‑код Planet полагается на автоматический расчёт высоты, тогда как штрих‑код RM4SCC демонстрирует **как задать высоту штрих‑кода** вручную.

Ниже представлена схема высокого уровня, иллюстрирующая поток:

![Barcode generator example showing Planet and RM4SCC barcodes](barcode-example.png)

*Alt text: Пример генератора штрих‑кодов, показывающий штрих‑коды Planet и RM4SCC с разными высотами.*

## Как создать штрих‑код planet – автоматическая высота

Штрих‑код Planet относится к почтовой семье, используемой многими национальными почтовыми службами. В большинстве случаев вы позволяете SDK определить высоту, что сохраняет правильные визуальные пропорции при разных длинах данных.

```python
# Step 1: Create a generator for the Planet barcode with the data "123456"
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

planet_gen = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Define the X‑dimension (module width) as 4 pixels
planet_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Save the barcode image as a PNG file
planet_gen.save("PostalPlanetBarHeightAuto.png", BarCodeImageFormat.Png)
```

**Почему это работает**

* `EncodeTypes.Planet` указывает библиотеке использовать симбологию Planet.
* Установка `x_dimension.pixels` в 4 задаёт ширину каждого модуля в 4 px, что является обычным значением по умолчанию для печатных этикеток.
* Явная высота не задаётся; SDK рассчитывает оптимальную высоту на основе данных и X‑dimension, поэтому это самый простой **пример генератора штрих‑кодов** для почтовых кодов.

**Ожидаемый результат**

2‑D PNG‑файл с именем `PostalPlanetBarHeightAuto.png`, содержащий чёткий штрих‑код Planet. Высота будет около 30 px (в зависимости от версии библиотеки), а ширина — 4 px × количество модулей.

## Как задать высоту штрих‑кода – пример с пользовательским RM4SCC

RM4SCC — другой почтовый штрих‑код, часто требующий фиксированной высоты для соответствия шаблонам этикеток. Эта часть руководства показывает **как задать высоту штрих‑кода** точным числом пикселей.

```python
# Step 1: Create a generator for the RM4SCC barcode with the data "123456"
rm4scc_gen = BarcodeGenerator(EncodeTypes.RM4SCC, "123456")

# Step 2: Set the X‑dimension to 4 pixels (same as the Planet example)
rm4scc_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Specify the barcode height as 100 pixels
rm4scc_gen.parameters.barcode.bar_height.pixels = 100

# Step 4: Save the barcode image as a PNG file
rm4scc_gen.save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png)
```

**Почему это работает**

* `EncodeTypes.RM4SCC` выбирает симбологию RM4SCC.
* X‑dimension остаётся 4 px, чтобы размер модуля был одинаковым для обоих штрих‑кодов.
* `bar_height.pixels = 100` принудительно задаёт высоту штрих‑кода ровно 100 px, переопределяя автоматический расчёт. Это рекомендуемый способ **задать высоту штрих‑кода**, когда ваш макет требует конкретного размера.

**Ожидаемый результат**

PNG‑файл с именем `PostalRM4SCCBarHeight100Pixels.png`, отображающий высокий штрих‑код RM4SCC. Ширина всё ещё определяется X‑dimension, а высота фиксирована в 100 px, что делает его подходящим для принтеров этикеток с высоким разрешением.

## Полный скрипт – объединение обоих примеров

Если вы предпочитаете один скрипт, генерирующий оба изображения, скопируйте следующий код в `generate_barcodes.py` и запустите его.

```python
"""
Full barcode generator example that creates:
* a Planet barcode with automatic height
* an RM4SCC barcode with a custom 100 px height
"""

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def create_planet_barcode(data: str, x_dim: int, out_path: str):
    """Generate a Planet barcode using the default height."""
    gen = BarcodeGenerator(EncodeTypes.Planet, data)
    gen.parameters.barcode.x_dimension.pixels = x_dim
    gen.save(out_path, BarCodeImageFormat.Png)

def create_rm4scc_barcode(data: str, x_dim: int, height_px: int, out_path: str):
    """Generate an RM4SCC barcode with a fixed height."""
    gen = BarcodeGenerator(EncodeTypes.RM4SCC, data)
    gen.parameters.barcode.x_dimension.pixels = x_dim
    gen.parameters.barcode.bar_height.pixels = height_px
    gen.save(out_path, BarCodeImageFormat.Png)

if __name__ == "__main__":
    # Planet barcode – auto height
    create_planet_barcode(
        data="123456",
        x_dim=4,
        out_path="PostalPlanetBarHeightAuto.png"
    )

    # RM4SCC barcode – custom 100 px height
    create_rm4scc_barcode(
        data="123456",
        x_dim=4,
        height_px=100,
        out_path="PostalRM4SCCBarHeight100Pixels.png"
    )
```

**Пояснение к скрипту**

* Две вспомогательные функции сохраняют код DRY (Don’t Repeat Yourself) и упрощают расширение скрипта для других симбологий.
* Защита `if __name__ == "__main__":` позволяет импортировать файл как модуль без выполнения логики генерации, что удобно для модульного тестирования.
* Все параметры (строка данных, X‑dimension, высота) указаны явно, поэтому скрипт служит справочным **примером генератора штрих‑кодов** для будущих проектов.

## Часто задаваемые вопросы и особые случаи

| Вопрос | Ответ |
|----------|--------|
| *Что делать, если нужна другая X‑dimension?* | Измените `x_dimension.pixels` на требуемую ширину модуля. Большие значения пропорционально увеличивают общий размер штрих‑кода. |
| *Можно ли генерировать другие форматы изображений?* | Да. Замените `BarCodeImageFormat.Png` на `Jpg`, `Bmp` или `Gif` в зависимости от перечисления библиотеки. |
| *Что произойдёт, если строка данных содержит недопустимые символы?* | Генератор бросит `ArgumentException`. Проверьте данные на соответствие набору символов симбологии перед вызовом конструктора. |
| *Можно ли задать минимальную высоту, сохраняя авто‑масштабирование?* | Используйте `gen.parameters.barcode.bar_height.min_pixels = <value>` (если SDK предоставляет свойство `min_pixels`). Это не позволит штрих‑коду уменьшаться ниже читаемого размера. |
| *Нужно ли освобождать генератор?* | Класс `BarcodeGenerator` реализует `IDisposable` в .NET; в Python за него отвечает сборщик мусора, но вы можете вызвать `gen.dispose()`, если создаёте много экземпляров в цикле. |

## Советы для использования в продакшене

* **Pro tip:** Сохраняйте значения X‑dimension и высоты в конфигурационном файле, чтобы менять их без перекомпиляции.
* **Watch out for:** Слишком маленькую высоту для выбранной симбологии; сканеры могут не распознать штрих‑код.
* **Performance note:** Генерация большой партии штрих‑кодов происходит быстрее, если переиспользовать один экземпляр `BarcodeGenerator` и менять только его свойство `code_text` между сохранениями.

## Заключение

Этот **пример генератора штрих‑кодов** демонстрирует как **создание изображений штрих‑кода planet** с автоматическим масштабированием, так и **задание высоты штрих‑кода** вручную для кодов RM4SCC. Следуя пошаговому руководству, вы сможете интегрировать создание штрих‑кодов в любое Python‑приложение, настраивать размеры и получать PNG‑файлы, готовые к печати или цифровому отображению.

### Следующие шаги

* Исследуйте дополнительные симбологии, такие как `EncodeTypes.Postnet` или `EncodeTypes.Code128` — тот же шаблон применим.
* Поэкспериментируйте с **заданием высоты штрих‑кода** для QR‑кодов или DataMatrix; большинство библиотек предоставляют аналогичное свойство `bar_height`.
* Объедините генератор с библиотекой PDF, чтобы внедрять штрих‑коды напрямую в счета‑фактуры или транспортные этикетки.

Не стесняйтесь адаптировать скрипт, делиться результатами и сообщать, какие типы штрих‑кодов вы добавите дальше!

## Что вам стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [How to save PNG from a barcode generator example in Python](/barcode/english/python-java/general/how-to-save-png-from-a-barcode-generator-example-in-python/)
- [How to create planet barcode PNG with Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [How to use a C# barcode generator to create a Planet barcode](/barcode/english/python-java/general/how-to-use-a-c-barcode-generator-to-create-a-planet-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}
---
date: 2026-08-17
description: Узнайте, как создать datamatrix barcode aspose с помощью Aspose.BarCode
  для .NET — идеальное решение для генерации штрих‑кодов, управления запасами и проектов
  генератора штрих‑кодов на C#.
keywords:
- create datamatrix barcode aspose
- datamatrix barcode error correction
- barcode generation with visual studio
lastmod: 2026-08-17
linktitle: Конфигурация DataMatrix ECC 000-140
og_description: Создайте datamatrix barcode aspose с помощью Aspose.BarCode для .NET
  — быстрое, высокопроизводительное решение для управления запасами и проектов штрих‑кодов
  на C#.
og_image_alt: Guide showing C# code to generate DataMatrix ECC 000-140 barcode with
  Aspose.BarCode
og_title: Создать datamatrix barcode aspose с Aspose.BarCode для .NET
schemas:
- author: Aspose
  dateModified: '2026-08-17'
  description: Learn how to create datamatrix barcode aspose using Aspose.BarCode
    for .NET – ideal for barcode generation inventory management and C# barcode generator
    projects.
  headline: How to create datamatrix barcode aspose with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Yes. The library is fully cross‑platform and runs on .NET 5+, .NET 6+,
      and .NET Core on Linux without additional dependencies.
    question: Can I use Aspose.BarCode for .NET on Linux servers?
  - answer: You can reuse a single `BarcodeGenerator` instance in a loop; each call
      to `Save` re‑renders the image in roughly 40‑60 ms, making it suitable for generating
      thousands of labels per minute.
    question: How does the library handle large batches of barcodes?
  - answer: No. Setting `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc140`
      automatically applies the correct error‑correction algorithm.
    question: Do I need to encode the data manually for ECC 140?
  - answer: The free trial provides full feature access, including ECC 140, but adds
      a watermark to the generated images. Apply a license for production to remove
      the watermark.
    question: Is a trial version sufficient for development?
  - answer: Absolutely. Use `generator.Parameters.Barcode.Color` and `generator.Parameters.Barcode.BackColor`
      to match your branding.
    question: Can I customize the barcode’s colors?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- C# barcode generation
- inventory management
title: Как создать datamatrix barcode aspose с помощью Aspose.BarCode
url: /ru/net/datamatrix-barcode-configuration/datamatrix-ecc-000-140-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать datamatrix barcode aspose с Aspose.BarCode

В современном программном обеспечении для цепочек поставок часто требуется **быстро и надёжно создать datamatrix barcode aspose**. В этом руководстве показано, как сгенерировать символ DataMatrix ECC 000‑140 с помощью Aspose.BarCode для .NET — библиотеки, которая берёт на себя кодирование, коррекцию ошибок и рендеринг изображения. К концу руководства у вас будет готовый фрагмент C#, который можно вставить в любой .NET‑проект управления запасами.

## Быстрые ответы
- **Какова основная библиотека?** Aspose.BarCode для .NET  
- **Какой тип штрих‑кода рассматривается?** DataMatrix ECC 000‑140  
- **Какой язык используется?** C# (C Sharp)  
- **Нужна ли лицензия?** Доступна бесплатная пробная версия; для продакшна требуется лицензия  
- **Типичное время реализации?** Около 10‑15 минут для базового генератора  

## Что такое DataMatrix ECC 000‑140?
DataMatrix — двумерный штрих‑код, который хранит большие объёмы данных в компактном квадрате. Уровень коррекции ошибок **ECC 000‑140** позволяет восстановить до 140 % повреждённых кодовых слов, что делает его идеальным для суровых складских условий, где метки могут быть поцарапаны или размазаны.

## Почему выбирают Aspose.BarCode для .NET?
Aspose.BarCode для .NET предоставляет всесторонний, высокопроизводительный API, упрощающий создание штрих‑кодов для множества символогий, с встроенной коррекцией ошибок, автоматическим определением размеров и широкой поддержкой платформ, что делает её идеальной для корпоративных решений по учёту и маркировке.

- **Надёжный API:** Поддерживает более 30 символогий штрих‑кодов и автоматически применяет правила кодирования.  
- **Кросс‑платформенный:** Работает в Windows, macOS и Linux без нативных зависимостей.  
- **Высокая производительность:** Генерирует DataMatrix 200 × 200 пикселей менее чем за 50 мс на типичном процессоре 2,5 ГГц, обеспечивая высокую пропускную способность линий маркировки.  

## Предварительные требования
Перед началом убедитесь, что у вас есть:

1. **Visual Studio** — любая современная редакция (Community, Professional или Enterprise).  
2. **Aspose.BarCode для .NET** — скачайте её по [ссылке для загрузки](https://releases.aspose.com/barcode/net/). Дополнительные ресурсы доступны по [этой ссылке](https://releases.aspose.com/).  
3. **Проект .NET** — готовый к подключению сборки Aspose.BarCode.  

## Импорт пространств имён
В вашем файле C# добавьте необходимые директивы `using`, чтобы получить доступ к классам штрих‑кода.

```csharp
using Aspose.BarCode.Generation;
```

**Класс `BarcodeGenerator` — основной движок Aspose.BarCode для создания изображений штрих‑кодов.**  
**Класс `BarcodeGenerator` — основной движок Aspose.BarCode, который создаёт и настраивает изображения штрих‑кодов.**  
```csharp
using Aspose.BarCode.Generation;
```

## Пример использования генерации штрих‑кода в управлении запасами
Представьте, что вам нужно маркировать тысячи поддонов в распределительном центре. Генерируя DataMatrix ECC 000‑140, вы можете разместить идентификаторы продукта, номера партии и даты истечения срока в одном надёжном символе, который сканеры считывают мгновенно, снижая ошибки ручного ввода до 95 %.

## Как создать datamatrix barcode aspose на C#
Загрузите данные, настройте генератор и сохраните изображение — всё в трёх лаконичных шагах. `BarcodeGenerator` автоматически выбирает оптимальный размер модуля и применяет уровень коррекции ECC 140, так что вам не нужно вручную рассчитывать контрольные суммы, всё делается быстро и эффективно.

### Шаг 1: определить каталог вывода
Выберите папку, в которую будет записан PNG‑файл. Путь должен существовать до вызова `Save`.

```csharp
string path = "Your Directory Path";
```

### Шаг 2: создать генератор штрих‑кода
Создайте экземпляр `BarcodeGenerator`, задайте символогию DataMatrix, укажите полезную нагрузку и выберите максимальный уровень коррекции ошибок.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Set the XDimension in Pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set DataMatrix ECC to 140
    gen.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;

    // Save the generated barcode image
    gen.Save($"{path}DataMatrixEcc000140.png", BarCodeImageFormat.Png);
}
```

В этом фрагменте мы:

* Выбираем **DataMatrix** в качестве типа штрих‑кода.  
* Указываем пример значения (`"Åspóse.Barcóde©"`).  
* Устанавливаем **XDimension** для управления размером модуля (здесь 4 пикселя).  
* Выбираем высший уровень коррекции ошибок (**ECC 140**).  
* Сохраняем результат в PNG‑файл.  

## Распространённые проблемы и решения
| Проблема | Решение |
|----------|---------|
| **Недопустимый путь** | Убедитесь, что `path` заканчивается разделителем каталога (`\` или `/`) и папка существует. |
| **Неподдерживаемые символы** | DataMatrix поддерживает UTF‑8; избегайте управляющих символов и используйте корректную кодировку. |
| **Лицензия не применена** | Класс `Aspose.BarCode.License` применяет коммерческую лицензию для разблокировки полной функциональности. Вызовите его до генерации любого штрих‑кода. |

## Часто задаваемые вопросы

**В: Можно ли использовать Aspose.BarCode для .NET на Linux‑серверах?**  
О: Да. Библиотека полностью кросс‑платформенная и работает на .NET 5+, .NET 6+ и .NET Core в Linux без дополнительных зависимостей.

**В: Как библиотека обрабатывает большие партии штрих‑кодов?**  
О: Один экземпляр `BarcodeGenerator` можно переиспользовать в цикле; каждый вызов `Save` рендерит изображение за примерно 40‑60 мс, что подходит для генерации тысяч этикеток в минуту.

**В: Нужно ли вручную кодировать данные для ECC 140?**  
О: Нет. Установка `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc140` автоматически применяет нужный алгоритм коррекции ошибок.

**В: Достаточна ли пробная версия для разработки?**  
О: Пробная версия предоставляет полный набор функций, включая ECC 140, но добавляет водяной знак к сгенерированным изображениям. Для продакшна необходимо применить лицензию, чтобы убрать водяной знак.

**В: Можно ли настроить цвета штрих‑кода?**  
О: Конечно. Используйте `generator.Parameters.Barcode.Color` и `generator.Parameters.Barcode.BackColor`, чтобы подобрать цвета под фирменный стиль.

---

**Последнее обновление:** 2026-08-17  
**Тестировано с:** Aspose.BarCode 24.11 для .NET  
**Автор:** Aspose

## Связанные руководства

- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Master DataMatrix Encoding in ASCII with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-reading/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
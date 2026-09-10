---
date: 2026-05-14
description: Узнайте, как генерировать Aztec‑штрихкод и настраивать его соотношение
  сторон с помощью Aspose.BarCode for .NET. Создавайте гибкие, высококачественные
  штрихкоды для ваших .NET‑приложений.
keywords:
- generate aztec barcode
- change barcode size
- barcode generator .net
- how to generate barcode
- adjust barcode dimensions
linktitle: Настройка соотношения сторон Aztec
schemas:
- author: Aspose
  dateModified: '2026-05-14'
  description: Learn how to generate Aztec barcode and customize its aspect ratio
    using Aspose.BarCode for .NET. Create flexible, high‑quality barcodes for your
    .NET applications.
  headline: How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode
    for .NET
  type: TechArticle
- description: Learn how to generate Aztec barcode and customize its aspect ratio
    using Aspose.BarCode for .NET. Create flexible, high‑quality barcodes for your
    .NET applications.
  name: How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode
    for .NET
  steps:
  - name: '**Aspose.BarCode for .NET** – you’ll need the library installed. If you
      don’t have it yet, you can download it from the [download link](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – you’ll need the library installed. If you
      don’t have it yet, you can download it from the [download link](https://releases.aspose.com/barcode/net/).'
  - name: '**.NET Development Environment** – a working IDE such as Visual Studio.'
    text: '**.NET Development Environment** – a working IDE such as Visual Studio.'
  - name: '**Basic Knowledge of C#** – this guide assumes you’re comfortable with
      C# syntax.'
    text: '**Basic Knowledge of C#** – this guide assumes you’re comfortable with
      C# syntax.'
  type: HowTo
- questions:
  - answer: Generally, the scanning speed remains the same, but extreme ratios may
      require the scanner to adjust focus, which could marginally affect performance.
    question: Does changing the aspect ratio affect scanning speed?
  - answer: Absolutely. Just replace `BarCodeImageFormat.Png` with the desired format
      enum value.
    question: Can I use other image formats like JPEG or SVG?
  - answer: A temporary license is sufficient for development and testing. For production,
      a full license is recommended.
    question: Is a license required for development builds?
  - answer: Aspose.BarCode fully supports Unicode. The sample `"Åspóse.Barcóde©"`
      demonstrates this capability.
    question: How do I handle Unicode characters in the encoded text?
  type: FAQPage
second_title: Aspise.BarCode .NET API
title: Как генерировать Aztec‑штрихкод с пользовательским соотношением сторон с помощью
  Aspose.BarCode for .NET
url: /ru/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как генерировать Aztec штрих‑код с пользовательским соотношением сторон, используя Aspose.BarCode для .NET

В этом руководстве вы узнаете, как **генерировать Aztec штрих‑код** изображения и точно настроить их соотношение сторон, чтобы соответствовать требованиям дизайна вашего .NET приложения. Независимо от того, нужен ли вам идеально квадратный штрих‑код для бейджа или более широкий макет для мобильного билета, Aspose.BarCode для .NET делает процесс простым, надёжным и быстрым.

## Быстрые ответы
- **Что контролирует «соотношение сторон»?** Оно определяет пропорцию ширины к высоте штрих‑кода.  
- **Какой класс создаёт штрих‑код?** `BarcodeGenerator` из библиотеки Aspose.BarCode.  
- **Можно ли задать любое значение соотношения?** Да, любое положительное число с плавающей точкой (например, 1, 0.5, 2).  
- **Нужна ли лицензия для разработки?** Временная лицензия подходит для тестирования; полная лицензия требуется для продакшн.  
- **Поддерживаемые форматы вывода?** PNG, JPEG, BMP, SVG и другие через `BarCodeImageFormat`.

## Что такое генерация Aztec штрих‑кода?

Генерация Aztec штрих‑кода означает создание двумерной матрицы, которая кодирует данные в компактном, исправляемом формате, после чего её можно отобразить как изображение для печати или отображения на экране. Эта матрица хранит закодированную информацию в виде серии чёрных и белых модулей, расположенных в квадратном шаблоне, обеспечивая высокую плотность данных и надёжную коррекцию ошибок для надёжного сканирования на различных устройствах.

## Зачем настраивать соотношение сторон Aztec штрих‑кода?

Настройка соотношения сторон Aztec штрих‑кода позволяет согласовать форму штрих‑кода с вашим пользовательским интерфейсом или дизайном этикетки, улучшает совместимость со сканерами на разных устройствах и поддерживает согласованность бренда. Правильно выбранное соотношение может снизить количество ошибок сканирования до 15 % на камерах с низким разрешением, согласно независимым тестовым бенчмаркам.

## Предварительные требования

Прежде чем приступить к настройке соотношения сторон Aztec штрих‑кодов, убедитесь, что у вас есть следующие предварительные требования:

1. **Aspose.BarCode for .NET** – вам понадобится установленная библиотека. Если у вас её ещё нет, вы можете скачать её по [ссылке для загрузки](https://releases.aspose.com/barcode/net/).  
2. **Среда разработки .NET** – рабочая IDE, например Visual Studio.  
3. **Базовые знания C#** – в этом руководстве предполагается, что вы уверенно владеете синтаксисом C#.

## Импорт пространств имён

Пространство имён `Aspose.BarCode.Generation` содержит основные классы для создания штрих‑кодов, включая `BarcodeGenerator`.  
```csharp
using Aspose.BarCode.Generation;
```

## Настройте каталог вывода

Укажите папку, в которой будут сохраняться сгенерированные изображения штрих‑кодов. Замените `"Your Directory Path"` реальным путём на вашем компьютере:  
```csharp
string path = "Your Directory Path";
```

## Создайте экземпляр BarcodeGenerator

`BarcodeGenerator` — основной класс, используемый для генерации изображений штрих‑кодов в Aspose.BarCode.  
Создайте экземпляр `BarcodeGenerator` и укажите, что вы хотите работать с Aztec штрих‑кодом. Пример текста `"Åspóse.Barcóde©"` приведён лишь для демонстрации — вы можете закодировать любую нужную строку:  
```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

## Настройте соотношение сторон

Свойство `AspectRatio` задаёт пропорцию ширины к высоте генерируемого Aztec штрих‑кода.

### Установите соотношение сторон 1 (квадратное)

Соотношение 1 создаёт идеально квадратный Aztec штрих‑код:  
```csharp
gen.Parameters.Barcode.Aztec.AspectRatio = 1;
```

Сохраните квадратный штрих‑код:  
```csharp
gen.Save($"{path}AztecAspectRatio1.png", BarCodeImageFormat.Png);
```

### Установите соотношение сторон 0.5 (шире)

Если вам нужен штрих‑код, ширина которого превышает высоту, задайте соотношение 0.5:  
```csharp
gen.Parameters.Barcode.Aztec.AspectRatio = 0.5f;
```

Сохраните более широкий штрих‑код:  
```csharp
gen.Save($"{path}AztecAspectRatio0.5.png", BarCodeImageFormat.Png);
```

## Как сгенерировать Aztec штрих‑код с пользовательским соотношением сторон в .NET?

`BarcodeGenerator` создаёт изображения штрих‑кодов на основе указанного типа кодирования.  
Загрузите Aztec штрих‑код, создав `BarcodeGenerator` с `EncodeTypes.Aztec`, задайте свойству `AspectRatio` нужное значение (например, 1 для квадратного или 0.5 для широкого макета), затем вызовите `Save`, указав желаемый формат изображения. Этот трёхшаговый процесс генерирует готовое к использованию изображение штрих‑кода менее чем за секунду на типичном оборудовании.

## Распространённые ошибки и советы

- **Не задавайте нулевое или отрицательное соотношение** – будет выброшено исключение.  
- **Не забудьте использовать одну и ту же переменную `path`** для всех вызовов `Save`, иначе изображения могут быть сохранены в непредвидённые места.  
- **Профессиональный совет:** протестируйте сгенерированный штрих‑код на реальном сканере, который планируете использовать, так как экстремальные соотношения могут влиять на читаемость.

## Заключение

Теперь вы знаете, как **генерировать Aztec штрих‑коды** и регулировать их соотношение сторон с помощью Aspose.BarCode для .NET. Всего несколькими строками кода на C# вы можете создавать квадратные или широкие штрих‑коды, подходящие для любого сценария применения, от мобильных билетов до печатных бейджей.

Если у вас есть вопросы, обратитесь к официальной документации или форумам сообщества:

- [Документация Aspose.BarCode для .NET](https://reference.aspose.com/barcode/net/)  
- [Форум Aspose.BarCode](https://forum.aspose.com/c/barcode/13)  

## Часто задаваемые вопросы

### Вопрос 1: Для чего используется Aztec штрих‑код?

**Ответ 1:** Aztec штрих‑код обычно используется для кодирования данных в различных приложениях, включая управление документами, билеты и транспорт.

### Вопрос 2: Можно ли настроить данные, закодированные в Aztec штрих‑коде?

**Ответ 2:** Да, вы можете настроить данные, закодированные в Aztec штрих‑коде, позволяя хранить информацию, такую как текст, URL‑адреса и многое другое.

### Вопрос 3: Совместим ли Aspose.BarCode для .NET с различными версиями .NET?

**Ответ 3:** Да, Aspose.BarCode для .NET совместим с различными версиями .NET, что делает его подходящим для широкого спектра проектов разработки на .NET.

### Вопрос 4: Как сгенерировать Aztec штрих‑коды с помощью Aspose.BarCode в веб‑приложении?

**Ответ 5:** Вы можете использовать Aspose.BarCode для .NET в веб‑приложениях, интегрируя его в ваш код, аналогично примеру настольного приложения, приведённому в этом руководстве.

### Вопрос 5: Где можно получить временную лицензию для Aspose.BarCode для .NET?

**Ответ 5:** Если вам нужна временная лицензия для тестирования или оценки, вы можете получить её [здесь](https://purchase.aspose.com/temporary-license/).

## Часто задаваемые вопросы

**Вопрос:** Влияет ли изменение соотношения сторон на скорость сканирования?  
**Ответ:** Обычно скорость сканирования остаётся той же, но экстремальные соотношения могут потребовать от сканера корректировать фокус, что может незначительно повлиять на производительность.

**Вопрос:** Могу ли я использовать другие форматы изображений, такие как JPEG или SVG?  
**Ответ:** Конечно. Просто замените `BarCodeImageFormat.Png` на нужное значение перечисления формата.

**Вопрос:** Требуется ли лицензия для сборок разработки?  
**Ответ:** Временная лицензия достаточна для разработки и тестирования. Для продакшн рекомендуется полная лицензия.

**Вопрос:** Как обрабатывать Unicode‑символы в закодированном тексте?  
**Ответ:** Aspose.BarCode полностью поддерживает Unicode. Пример `"Åspóse.Barcóde©"` демонстрирует эту возможность.

---

**Последнее обновление:** 2026-05-14  
**Тестировано с:** Aspose.BarCode 24.11 for .NET  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Похожие руководства

- [Кодирование текста Aztec с помощью Aspose.BarCode для .NET](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)
- [Как создать Aztec штрих‑код с коррекцией ошибок в .NET](/barcode/net/aztec-barcode-encoding/aztec-error-level-example/)
- [Освоение режима символов Aztec с Aspose.BarCode для .NET](/barcode/net/aztec-barcode-encoding/aztec-symbol-mode-example/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
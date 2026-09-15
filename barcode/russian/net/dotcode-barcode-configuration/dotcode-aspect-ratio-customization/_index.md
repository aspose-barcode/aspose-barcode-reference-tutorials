---
date: 2026-06-14
description: Узнайте, как создать штрих‑код DotCode .NET и настроить его соотношение
  сторон с помощью Aspose.BarCode for .NET.
keywords:
- create dotcode barcode .net
- dotcode aspect ratio
- aspose barcode .net
- barcode customization
- .net barcode generation
linktitle: Настройка соотношения сторон DotCode
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to create DotCode barcode .NET and customize its aspect ratio
    using Aspose.BarCode for .NET.
  headline: Create DotCode Barcode .NET – Customize Aspect Ratio
  type: TechArticle
- description: Learn how to create DotCode barcode .NET and customize its aspect ratio
    using Aspose.BarCode for .NET.
  name: Create DotCode Barcode .NET – Customize Aspect Ratio
  steps:
  - name: '**Aspose.BarCode for .NET** – download the library from the official site [here](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – download the library from the official site [here](https://releases.aspose.com/barcode/net/).'
  - name: '**IDE** – Visual Studio, Rider, or any .NET‑compatible editor.'
    text: '**IDE** – Visual Studio, Rider, or any .NET‑compatible editor.'
  - name: '**Output folder** – replace “Your Directory Path” in the sample with a
      real folder on your machine.'
    text: '**Output folder** – replace “Your Directory Path” in the sample with a
      real folder on your machine.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode supports DotCode out‑of‑the‑box.
    question: Can I generate DotCode barcodes in .NET?
  - answer: The `AspectRatio` property of `BarcodeGenerator`.
    question: Which property controls the shape?
  - answer: A commercial license is required; a free trial works for development.
    question: Do I need a license for production?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Supported .NET versions?
  - answer: Less than a second for a typical 200 × 200 pixel barcode.
    question: How long does the code take to run?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Создать штрих‑код DotCode .NET – Настройка соотношения сторон
url: /ru/net/dotcode-barcode-configuration/dotcode-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создать штрих‑код DotCode .NET – Настройка соотношения сторон

Если вам нужно **создать штрих‑код DotCode .NET** решения, которые помещаются в ограниченных пространствах или соответствуют определённым требованиям к макету, Aspose.BarCode for .NET предоставляет полный контроль. В этом руководстве мы пройдём весь процесс генерации штрих‑кода DotCode и настройки его соотношения сторон, чтобы он выглядел именно так, как вам нужно на упаковке, этикетках или экранах мобильных устройств.  

## Быстрые ответы
- **Могу ли я генерировать штрих‑коды DotCode в .NET?** Да, Aspose.BarCode поддерживает DotCode из коробки.  
- **Какое свойство управляет формой?** Свойство `AspectRatio` класса `BarcodeGenerator`.  
- **Нужна ли лицензия для продакшн?** Требуется коммерческая лицензия; бесплатная пробная версия подходит для разработки.  
- **Поддерживаемые версии .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Сколько времени занимает выполнение кода?** Менее секунды для типичного штрих‑кода размером 200 × 200 пикселей.

## Какова основная цель данного руководства?
Руководство демонстрирует, как сгенерировать штрих‑код DotCode с помощью Aspose.BarCode for .NET и как настроить его соотношение сторон для соответствия конкретным ограничениям макета. Следуя шагам, вы научитесь конфигурировать генератор, изменять параметры размера и экспортировать изображение в распространённые форматы.

## Как создать штрих‑код DotCode в .NET?
Чтобы создать штрих‑код DotCode в .NET, создайте экземпляр `BarcodeGenerator` с `EncodeTypes.DotCode` и данными, которые нужно закодировать. Затем задайте свойства X‑Dimension и AspectRatio для управления размером и формой, и наконец вызовите метод `Save` для записи изображения в файл нужного формата.

## Требования

1. **Aspose.BarCode for .NET** – скачайте библиотеку с официального сайта [здесь](https://releases.aspose.com/barcode/net/).  
2. **IDE** – Visual Studio, Rider или любой совместимый с .NET редактор.  
3. **Папка вывода** – замените «Your Directory Path» в примере реальной папкой на вашем компьютере.

## Импорт пространств имён

`Aspose.BarCode.Generation` предоставляет классы, необходимые для генерации и настройки штрих‑кодов в .NET.  
```csharp
using Aspose.BarCode.Generation;
```

## Шаг 1: Инициализация генератора штрих‑кода

`BarcodeGenerator` – основной класс, создающий изображение штрих‑кода на основе указанной символьной системы и данных.  
```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, "Aspose"))
{
    // Your code goes here
}
```

## Шаг 2: Установка X‑Dimension (размера) штрих‑кода

`XDimension` определяет ширину отдельного модуля (точки) в пикселях, влияя на общий размер штрих‑кода.  
```csharp
gen.Parameters.Barcode.XDimension.Pixels = 10;
```

## Шаг 3: Настройка соотношения сторон

`AspectRatio` задаёт пропорцию высоты к ширине каждого модуля, позволяя растягивать или сжимать штрих‑код по вертикали.  
```csharp
gen.Parameters.Barcode.DotCode.AspectRatio = 0.5f;
```

## Шаг 4: Сохранение изображения штрих‑кода

`Save` записывает сгенерированный штрих‑код в файл выбранного формата изображения, например PNG или JPEG.  
```csharp
gen.Save($"{path}DotCodeAspectRatio0.5.png", BarCodeImageFormat.Png);
```

## Почему стоит использовать Aspose.BarCode для настройки DotCode?
Aspose.BarCode предоставляет полный набор функций для генерации DotCode, включая вывод высокого разрешения, широкую поддержку форматов и тонкую настройку размеров штрих‑кода, таких как соотношение сторон. Библиотека работает на всех основных платформах .NET, не требует внешних зависимостей и обеспечивает быструю отрисовку, что делает её идеальной как для настольных, так и для веб‑приложений.

## Общие сценарии использования

- **Здравоохранение**: Компактные бирки с идентификаторами пациентов, которые должны помещаться на небольших браслетах.  
- **Почтовые службы**: Широкоформатные транспортные этикетки, где меньшая высота повышает надёжность сканирования.  
- **Производство**: Непрерывная маркировка деталей, где ограничения по пространству требуют индивидуального соотношения сторон.

## Часто задаваемые вопросы

**В:** Что такое соотношение сторон штрих‑кода DotCode?  
**О:** Это отношение высоты модуля к его ширине; изменение этого параметра меняет общую форму штрих‑кода.

**В:** Какие отрасли получают наибольшую выгоду от штрих‑кодов DotCode?  
**О:** Здравоохранение, почтовые службы и производство часто используют DotCode для компактного, высокоплотного кодирования данных.

**В:** Могу ли я настроить другие параметры DotCode с помощью Aspose.BarCode for .NET?  
**О:** Конечно. Вы можете изменять уровень коррекции ошибок, цвета переднего/фонового плана и даже встраивать логотипы.

**В:** Подходит ли Aspose.BarCode как для веб‑, так и для настольных .NET‑приложений?  
**О:** Да, библиотека без проблем работает в ASP.NET, WPF, WinForms и консольных приложениях.

**В:** Где можно найти дополнительную документацию и примеры?  
**О:** Подробная ссылка на API и образцы кода доступны [здесь](https://reference.aspose.com/barcode/net/).

---

**Обновлено:** 2026-06-14  
**Тестировано с:** Aspose.BarCode 24.12 for .NET  
**Автор:** Aspose

## Связанные руководства

- [DotCode Extended Code Text Configuration with Aspose.BarCode for .NET](/barcode/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [DotCode Structured Append Mode Configuration with Aspose.BarCode for .NET](/barcode/net/dotcode-barcode-configuration/dotcode-structured-append-mode-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
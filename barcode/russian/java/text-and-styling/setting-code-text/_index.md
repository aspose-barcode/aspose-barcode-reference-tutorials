---
date: 2026-06-09
description: Узнайте, как создать штрих‑код Code128 в Java с помощью Aspose.BarCode.
  Это пошаговое руководство показывает, как генерировать штрих‑код в Java, задавать
  пользовательский текст, регулировать ширину полос и сохранять изображение.
keywords:
- create code128 barcode java
- how to generate barcode java
- java barcode generator example
linktitle: Установка Code Text
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to create Code128 barcode Java using Aspose.BarCode. This
    step‑by‑step guide shows how to generate barcode Java, set custom text, adjust
    bar width, and save the image.
  headline: Create Code128 Barcode Java – Set Code Text using Aspose.BarCode
  type: TechArticle
- description: Learn how to create Code128 barcode Java using Aspose.BarCode. This
    step‑by‑step guide shows how to generate barcode Java, set custom text, adjust
    bar width, and save the image.
  name: Create Code128 Barcode Java – Set Code Text using Aspose.BarCode
  steps:
  - name: Create an Instance of `BarcodeGenerator`
    text: 'The `BarcodeGenerator` constructor takes two arguments: the barcode symbology
      (`CODE_128`) and the **custom code text** you want to encode, such as `"12345678"`.'
  - name: Adjust Barcode Width for Custom Barcode Text
    text: Set the `XDimension` property (bar width) to control how wide each bar appears.
      In this example we use `0.5` mm, a size that balances readability and label
      space for most applications.
  - name: Save the Barcode Image
    text: Call the `save` method, specifying the output path and image format (JPEG,
      PNG, SVG, etc.). The example saves the file as **`setCodeText.jpg`** in the
      project’s document folder.
  type: HowTo
- questions:
  - answer: Aspose.BarCode for Java.
    question: What library should I use?
  - answer: CODE_128.
    question: Which barcode type is demonstrated?
  - answer: Use the `BarcodeGenerator` constructor or the `setCodeText` method.
    question: How do I set custom barcode text?
  - answer: Yes—adjust `XDimension` (bar width) in millimetres.
    question: Can I change the bar width?
  - answer: A commercial license is required for non‑trial deployments.
    question: Do I need a license for production?
  type: FAQPage
second_title: Aspose.BarCode Java API
title: Создание штрих‑кода Code128 в Java – Установка Code Text с помощью Aspose.BarCode
url: /ru/java/text-and-styling/setting-code-text/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание штрих‑кода Code128 в Java – Установка текста кода с помощью Aspose.BarCode

В этом руководстве вы узнаете, как **создать штрих‑код Code128 в Java** с использованием библиотеки Aspose.BarCode Java. Независимо от того, разрабатываете ли вы систему учёта, решение для отслеживания документов или любое приложение, которому нужны штрих‑коды, мы проведём вас через каждый шаг — от создания штрих‑кода **Code128** до настройки текста кода и точной настройки ширины полосы. К концу у вас будет готовое изображение, которое можно вставить в любое место.

## Быстрые ответы
- **Какую библиотеку следует использовать?** Aspose.BarCode for Java.  
- **Какой тип штрих‑кода демонстрируется?** CODE_128.  
- **Как установить пользовательский текст штрих‑кода?** Use the `BarcodeGenerator` constructor or the `setCodeText` method.  
- **Можно ли изменить ширину полосы?** Yes—adjust `XDimension` (bar width) in millimetres.  
- **Нужна ли лицензия для продакшн?** A commercial license is required for non‑trial deployments.

## Как создать штрих‑код Code128 в Java?

Загрузите `BarcodeGenerator` с символогией `CODE_128` и желаемым текстом, задайте ширину полосы через `XDimension`, затем вызовите `save` для записи файла изображения. Эта трёхшаговая схема создаёт высококачественный штрих‑код за секунды и работает на любой среде выполнения Java 8+, Windows, Linux или macOS.

## Требования для генерации штрих‑кода в Java

- Базовые знания программирования на Java.  
- Среда разработки Java (JDK 8 или новее).  
- Aspose.BarCode for Java library – скачайте её **[здесь](https://releases.aspose.com/barcode/java/)**.  
- Ваш предпочитаемый IDE (IntelliJ IDEA, Eclipse и т.д.).

## Импорт пакетов

Импортируйте необходимые пространства имён Aspose.BarCode, чтобы классы были доступны в вашем проекте.

## Что такое класс BarcodeGenerator?

`BarcodeGenerator` — основной класс Aspose.BarCode, который создаёт изображения штрих‑кодов в памяти. Он предоставляет удобный API для установки символогии, текста кода, размеров, цветов и дополнительных параметров рендеринга перед экспортом результата в форматы PNG, JPEG, SVG или PDF. При необходимости можно настроить подписи, отступы и уровни коррекции ошибок.

## Руководство по генератору штрих‑кода: создание штрих‑кода Code128

### Шаг 1: Создать экземпляр `BarcodeGenerator`

Конструктор `BarcodeGenerator` принимает два аргумента: символогию штрих‑кода (`CODE_128`) и **пользовательский текст кода**, который вы хотите закодировать, например `"12345678"`.

```java
// The path to the documents directory.
String path = "Your Directory Path";
// The path to the resource directory.
String dataDir = "Your Document Directory";
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");
```

### Шаг 2: Настроить ширину штрих‑кода для пользовательского текста

Установите свойство `XDimension` (ширина полосы), чтобы контролировать, насколько широкими будут отдельные полосы. В этом примере мы используем `0.5` mm — размер, который обеспечивает баланс между читаемостью и экономией места на этикетке для большинства приложений.

```java
generator.getParameters().getBarcode().getXDimension().setMillimeters(0.5f);
```

### Шаг 3: Сохранить изображение штрих‑кода

Вызовите метод `save`, указав путь вывода и формат изображения (JPEG, PNG, SVG и т.д.). Пример сохраняет файл как **`setCodeText.jpg`** в папке `document` проекта.

```java
generator.save(dataDir + "setCodeText.jpg");
```

## Почему стоит использовать Aspose.BarCode для Java?

Aspose.BarCode for Java предлагает обширный набор функций, упрощающих генерацию штрих‑кодов на разных платформах. Он поддерживает более шестидесяти символогий, обеспечивает высококачественный растровый и векторный вывод, а также оптимизирован для массовой обработки, что делает его идеальным для корпоративных приложений и бесшовной интеграции с существующими Java‑проектами.

- **Широкая поддержка символогии** – более **60** типов штрих‑кодов, включая Code128, QR, DataMatrix и PDF417.  
- **Высококачественная отрисовка** – генерирует чёткие PNG, JPEG, SVG и PDF изображения шириной до **2000 mm** без потери качества.  
- **Оптимизирована по производительности** – обрабатывает пакет из 500 страниц штрих‑кодов менее чем за **2 секунды** на стандартном серверном оборудовании.  
- **Кроссплатформенность** – полностью совместима с Windows, Linux и macOS, работает на любой среде выполнения Java 8+.

## Распространённые проблемы и решения

| Проблема | Решение |
|----------|---------|
| **Штрих‑код выглядит размытым** | Увеличьте разрешение изображения или экспортируйте в векторный формат (SVG, PDF). |
| **Текст обрезан** | Увеличьте `XDimension` и `BarHeight`, чтобы предоставить символогии достаточно места. |
| **Лицензия не применена** | Поместите `Aspose.BarCode.lic` в корень проекта и загрузите её с помощью `License license = new License(); license.setLicense("Aspose.BarCode.lic");`. |

## Часто задаваемые вопросы

**Q:** *В чём разница между `CODE_128` и другими вариантами Code128?*  
**A:** `CODE_128` автоматически выбирает наиболее эффективное кодирование (A, B или C) в зависимости от входных данных, обеспечивая оптимальную плотность и скорость.

**Q:** *Можно ли изменить формат вывода на PNG вместо JPEG?*  
**A:** Да — используйте `generator.save(dataDir + "setCodeText.png", com.aspose.barcode.BarcodeImageFormat.PNG);`.

**Q:** *Можно ли добавить подпись, читаемую человеком, под штрих‑кодом?*  
**A:** Конечно. Установите `generator.getParameters().getBarcode().getCaption().setTopMargin(5);` и задайте текст подписи через `setText`.

**Q:** *Поддерживает ли Aspose.BarCode Unicode‑символы?*  
**A:** Да. Передайте текст в кодировке UTF‑8 и убедитесь, что выбранная симвология поддерживает данный набор символов.

**Q:** *Как сгенерировать несколько штрих‑кодов в цикле?*  
**A:** Создайте новый `BarcodeGenerator` внутри цикла, присвойте уникальный текст для каждой итерации и вызовите `save` с отдельным именем файла.

**Последнее обновление:** 2026-06-09  
**Тестировано с:** Aspose.BarCode 24.12 for Java  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Создание Data Matrix штрих‑кода и установка положения текста кода в Java](/barcode/java/text-and-styling/setting-code-text-location/)
- [Как установить цвет текста штрих‑кода в Java с Aspose.BarCode](/barcode/java/text-and-styling/setting-code-text-foreground-color/)
- [Генерация штрих‑кода Java – Установка разрешения изображения с Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.barcode.generation.BarcodeGenerator;
```
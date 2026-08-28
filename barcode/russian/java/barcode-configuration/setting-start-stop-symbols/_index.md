---
date: 2026-08-28
description: Узнайте, как создать изображение штрихкода Java с помощью Aspose Barcode
  Java, установить символы начала и конца CODABAR и генерировать PNG‑файлы без водяных
  знаков.
keywords:
- create barcode image java
- barcode generation without watermark
- codabar start stop symbols
lastmod: 2026-08-28
linktitle: Установка символов начала и конца
og_description: Создание изображения штрихкода Java с использованием Aspose Barcode
  Java. Это руководство показывает, как установить символы начала/конца CODABAR и
  экспортировать PNG без водяных знаков.
og_image_alt: 'Aspose Barcode Java tutorial: create barcode image with start/stop
  symbols'
og_title: Создание изображения штрихкода Java – руководство по символам начала/конца
schemas:
- author: Aspose
  dateModified: '2026-08-28'
  description: Learn how to create barcode image java with Aspose Barcode Java, set
    CODABAR start and stop symbols, and generate PNG files without watermarks.
  headline: Aspose Barcode Java – Create barcode image with start/stop symbols
  type: TechArticle
- questions:
  - answer: Aspose.BarCode for Java.
    question: What library creates barcode images in Java?
  - answer: Yes, using `setCodabarStartSymbol` and `setCodabarStopSymbol`.
    question: Can I customize start/stop symbols?
  - answer: CODABAR.
    question: Which barcode type is used in this example?
  - answer: A commercial license is required for non‑trial use.
    question: Do I need a license for production?
  - answer: PNG image saved to disk.
    question: What output format is generated?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- barcode generation
- Aspose.BarCode
- Java barcode tutorial
title: Aspose Barcode Java – Создание изображения штрихкода с символами начала/конца
url: /ru/java/barcode-configuration/setting-start-stop-symbols/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Barcode Java – Создание изображения штрихкода с символами начала/конца

## Введение

В этом полном руководстве вы создадите файлы **create barcode image java** с помощью Aspose Barcode Java и узнаете **как установить символы начала и конца** для штрихкодов CODABAR. Независимо от того, создаёте ли вы терминал точки продаж, систему управления складом или любое приложение, требующее надёжного генератора штрихкодов, настройка этих символов позволяет соответствовать устаревшим спецификациям, сохраняя код чистым и поддерживаемым. Мы пройдём каждый шаг, объясним, почему каждое настройка важна, и покажем, как создать PNG‑изображение без пробной водяной метки.

## Быстрые ответы
- **Какая библиотека создаёт изображения штрихкодов в Java?** Aspose.BarCode for Java.  
- **Могу ли я настроить символы начала/конца?** Да, используя `setCodabarStartSymbol` и `setCodabarStopSymbol`.  
- **Какой тип штрихкода используется в этом примере?** CODABAR.  
- **Нужна ли лицензия для продакшна?** Требуется коммерческая лицензия для использования без пробного режима.  
- **В каком формате генерируется вывод?** PNG‑изображение, сохранённое на диск.

## Что такое Aspose Barcode Java?

Aspose Barcode Java — это **независимая от зависимостей Java‑библиотека, генерирующая более 70 символогий штрихкодов**, от классических 1‑D кодов, таких как CODABAR, до современных 2‑D кодов, как QR и DataMatrix. Она обрабатывает всё низкоуровневое кодирование, позволяя сосредоточиться на бизнес‑логике, гарантируя соответствие отраслевым стандартам.

## Почему стоит использовать Aspose Barcode Java для генерации штрихкодов без водяного знака?

Сначала загрузите лицензию, и библиотека будет создавать чистые изображения — без наложения «Aspose Evaluation». Она также предоставляет **тонкую настройку** (символы начала/конца, цвета, размеры) и **кроссплатформенную совместимость** (любой Java‑runtime, включая Android). С поддержкой **более 50 форматов вывода** и возможностью напрямую передавать изображения в HTTP‑ответы, это предпочтительный выбор для высокопроизводительного, промышленного создания штрихкодов.

## Предварительные требования

Прежде чем мы начнём, убедитесь, что у вас есть:

1. **Java Development Kit (JDK)** – Установите последнюю версию JDK с сайта [Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).  
2. **Aspose.BarCode for Java library** – Скачайте её по [download link](https://releases.aspose.com/barcode/java/).

Наличие этих компонентов гарантирует, что вы сможете **create barcode image java** без недостающих элементов.

## Импорт пакетов

Следующие импорты предоставляют доступ к основным классам, необходимым для генерации штрихкода:

`enum` `CodabarSymbol` определяет допустимые символы начала/конца для штрихкодов CODABAR.  

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.CodabarSymbol;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Пошаговое руководство

### Как задать папку вывода для изображения штрихкода?

Укажите папку, в которую будет записан PNG‑файл. Использование `Paths.get` делает код переносимым между Windows, macOS и Linux.

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

### Как создать генератор штрихкода для CODABAR?

Класс `BarcodeGenerator` создаёт изображение штрихкода для заданной символогии и данных.

Создайте экземпляр `BarcodeGenerator`, указав символогию CODABAR и строку данных, которую нужно закодировать.

```java
// Create instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "12345678");
```

### Как задать символ начала CODABAR?

`setCodabarStartSymbol` задаёт символ, отмечающий начало штрихкода CODABAR.

Вызовите `setCodabarStartSymbol` и передайте один из поддерживаемых символов (`A`, `B`, `C`, `D`). В этом примере используется `A`.

```java
// Set the Codabar start symbol to A
generator.getParameters().getBarcode().getCodabar().setCodabarStartSymbol(CodabarSymbol.A);
```

### Как задать символ окончания CODABAR?

`setCodabarStopSymbol` задаёт символ, отмечающий конец штрихкода CODABAR.

Используйте `setCodabarStopSymbol` с соответствующим символом окончания — `D` в данном случае.

```java
// Set the Codabar stop symbol to D
generator.getParameters().getBarcode().getCodabar().setCodabarStopSymbol(CodabarSymbol.D);
```

### Как сохранить сгенерированный штрихкод в PNG‑файл?

`enum` `SaveFormat` указывает формат файла для сохранения изображения штрихкода.

Вызовите метод `save`, указав полное имя файла и значение `SaveFormat.Png`. Изображение будет записано без водяного знака после применения действующей лицензии.

```java
// Save the image to disk in PNG format
generator.save(dataDir + "startAndStopSymbols.png");
```

## Распространённые ошибки и советы

Класс `License` загружает файл лицензии Aspose, чтобы включить режим полной функциональности.

- **Неправильный путь к каталогу** – Убедитесь, что `dataDir` заканчивается правильным разделителем файловой системы или формируйте путь с помощью `Paths.get`.  
- **Неподдерживаемые символы начала/конца** – CODABAR принимает только `A`, `B`, `C` или `D`. Передача любого другого значения вызывает `IllegalArgumentException`.  
- **Лицензия не применена** – В пробном режиме вывод содержит водяной знак. Загрузите файл лицензии с помощью `License license = new License(); license.setLicense("Aspose.Total.Java.lic");` перед созданием генератора, чтобы избежать этого.  
- **Генерация в большом масштабе** – При создании тысяч штрихкодов переиспользуйте один экземпляр `BarcodeGenerator` и меняйте только текст кода, чтобы снизить накладные расходы на создание объектов.

## Часто задаваемые вопросы

### Могу ли я использовать Aspose.BarCode for Java в коммерческом проекте?

Да. Приобретите коммерческую лицензию [purchase a commercial license](https://purchase.aspose.com/buy), чтобы убрать водяной знак оценки и получить полную техническую поддержку.

### Доступна ли бесплатная пробная версия?

Конечно. Скачайте пробную версию [download the trial version](https://releases.aspose.com/), чтобы оценить все функции перед покупкой.

### Как я могу получить поддержку для Aspose.BarCode for Java?

Посетите форум Aspose.BarCode [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) для получения помощи от сообщества или откройте запрос в службу поддержки через портал вашего аккаунта Aspose.

### Как получить временную лицензию для тестирования?

Вы можете запросить временную 30‑дневную лицензию [request a temporary 30‑day license](https://purchase.aspose.com/temporary-license/). Это позволяет проводить тесты, приближённые к продакшн, без полной покупки.

### Какие другие символогии штрихкодов поддерживает Aspose.BarCode?

Библиотека поддерживает **более 70 символогий**, включая Code128, EAN‑13, QR, DataMatrix, PDF417 и многие другие. Полный список см. в официальной документации.

## Дополнительные вопросы и ответы (AI‑friendly)

**Q:** Какие форматы изображений я могу экспортировать помимо PNG?  
**A:** Aspose.BarCode поддерживает PNG, JPEG, BMP, GIF и TIFF. Выберите нужный формат, изменив значение `SaveFormat` в вызове `save`.

**Q:** Могу ли я генерировать изображения штрихкодов в памяти без записи на диск?  
**A:** Да. Вызовите `generator.save(OutputStream)`, чтобы записать напрямую в поток — идеально для веб‑API, возвращающих изображение в HTTP‑ответе.

**Q:** Работает ли библиотека на Android?  
**A:** Версия Java работает на Android, но вам нужно вручную включить необходимые зависимости (Maven Central для Android недоступен). Основной API остаётся идентичным.

## Заключение

Теперь вы узнали, как **create barcode image java** и точно **задать символы начала/конца** для штрихкода CODABAR с помощью Aspose Barcode Java. Этот подход даёт гибкость для соответствия устаревшим спецификациям, сохраняя ваш код чистым и поддерживаемым. Изучайте дальнейшие настройки — например, изменение цветов, добавление читаемого человеком текста или переход к другим символогиям — обращаясь к официальной справке API по адресу [documentation](https://reference.aspose.com/barcode/java/).

---

**Последнее обновление:** 2026-08-28  
**Тестировано с:** Aspose.BarCode for Java 24.12  
**Автор:** Aspose

## Связанные руководства

- [Проверка контрольной суммы и создание штрихкода Codabar в Java с Aspose.BarCode](/barcode/java/checksum-and-validation/)
- [Создание штрихкода с Aspose — установка размеров X и Y в Java](/barcode/java/barcode-configuration/managing-x-y-dimension-barcode/)
- [Как генерировать штрихкод java: создание точного изображения штрихкода](/barcode/java/barcode-basics/creating-image-exact-barcode/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
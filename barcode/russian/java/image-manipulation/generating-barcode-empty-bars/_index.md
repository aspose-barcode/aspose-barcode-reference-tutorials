---
title: Генерация штрих-кода с пустыми полосами в Java
linktitle: Генерация штрих-кода с пустыми полосами
second_title: API Aspose.BarCode Java
description: Легко создавайте штрих-коды с пустыми полосами на Java с помощью Aspose.BarCode. Настройте внешний вид и легко интегрируйте. Изучите руководство прямо сейчас!
weight: 14
url: /ru/java/image-manipulation/generating-barcode-empty-bars/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Генерация штрих-кода с пустыми полосами в Java


## Введение

В динамичном мире разработки программного обеспечения интеграция возможностей генерации штрих-кодов в приложения Java стала обычным требованием. Aspose.BarCode for Java выделяется как надежное решение, предоставляющее разработчикам мощный набор инструментов для создания различных типов штрих-кодов. В этом уроке мы углубимся в процесс создания штрих-кода с пустыми полосами с помощью Aspose.BarCode для Java.

## Предварительные условия

Прежде чем мы приступим к созданию штрих-кода, убедитесь, что у вас есть следующие предварительные условия:

1. Среда разработки Java: убедитесь, что на вашем компьютере установлена среда разработки Java.

2.  Библиотека Aspose.BarCode для Java: загрузите и установите библиотеку Aspose.BarCode для Java из[страница загрузки](https://releases.aspose.com/barcode/java/).

3. Каталог документов: создайте каталог в своей системе для хранения сгенерированного изображения штрих-кода.

## Импортировать пакеты

В свой Java-проект импортируйте необходимые пакеты для работы с Aspose.BarCode:

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Шаг 1. Настройте каталог ресурсов

```java
// Путь к каталогу ресурсов.
String dataDir = "Your Document Directory";
```

 Заменять`"Your Document Directory"`с фактическим путем к каталогу вашего документа.

## Шаг 2. Создайте экземпляр генератора штрих-кода

```java
// Создайте экземпляр BarcodeGenerator и инициализируйте его с помощью CodeText и Символики.
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

Здесь мы создаем экземпляр BarcodeGenerator с символикой CODE_128 и текстом «ТЕКСТ» в качестве кода для кодирования.

## Шаг 3. Установите для свойства FilledBars значение False

```java
// Установите для свойства FilledBars значение false.
generator.getParameters().getBarcode().setFilledBars(false);
```

 Установив`FilledBars` к`false`, мы гарантируем, что сгенерированный штрих-код будет иметь пустые столбцы.

## Шаг 4. Сохраните изображение штрих-кода

```java
// Сохраните полученное изображение штрих-кода на диск.
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

Этот шаг включает сохранение сгенерированного изображения штрих-кода в указанный каталог в формате PNG.

Повторите эти шаги в своем Java-приложении, чтобы легко сгенерировать штрих-код с пустыми полосами, используя Aspose.BarCode для Java.

## Заключение

В заключение, в этом руководстве вы прошли процесс создания штрих-кода с пустыми полосами в Java с использованием библиотеки Aspose.BarCode. Благодаря интуитивно понятному API и обширной документации Aspose.BarCode упрощает интеграцию штрих-кодов, что делает его ценным активом для разработчиков.

## Часто задаваемые вопросы

### Совместим ли Aspose.BarCode со всеми средами разработки Java?
Да, Aspose.BarCode предназначен для полной интеграции с различными средами разработки Java.

### Могу ли я настроить внешний вид сгенерированного штрих-кода?
Абсолютно! Aspose.BarCode предоставляет множество возможностей настройки, позволяющих адаптировать штрих-код к вашим конкретным потребностям.

### Доступна ли пробная версия для Aspose.BarCode?
 Да, вы можете изучить возможности Aspose.BarCode, получив бесплатную пробную версию.[здесь](https://releases.aspose.com/).

### Как я могу получить поддержку Aspose.BarCode?
 По любым вопросам или помощи посетите[Форум Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

### Где я могу найти подробную документацию по Aspose.BarCode?
 Полная документация доступна[здесь](https://reference.aspose.com/barcode/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
date: 2025-12-30
description: Узнайте, как генерировать штрих‑код в Java с помощью Aspose.BarCode.
  Это пошаговое руководство покажет, как установить пользовательский текст штрих‑кода,
  настроить ширину и сохранить изображение.
linktitle: Setting Code Text
second_title: Aspose.BarCode Java API
title: 'Генерация штрихкода в Java - установка текста кода с помощью Aspose.BarCode'
url: /ru/java/text-and-styling/setting-code-text/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Генерация штрихкода Java: Установка текста кода с помощью Aspose.BarCode

## Введение

В этом руководстве вы узнаете, как **generate barcode java** с библиотекой Aspose.BarCode для Java. Независимо от того, создаёте ли вы систему учёта, решение для отслеживания документов или любое приложение, требующее штрихкоды, это руководство проведёт вас через каждый шаг — от создания штрихкода **Code128** до настройки текста кода и регулировки ширины полос. В конце у вас будет готовое изображение, которое можно вставить в любое место.

## Быстрые ответы
- **Какую библиотеку использовать?** Aspose.BarCode for Java.
- **Какой тип штрихкода демонстрируется?** CODE_128.
- **Как установить пользовательский текст штрихкода?** Используйте конструктор `BarcodeGenerator` или метод `setCodeText`.
- **Можно ли изменить ширину полосы?** Да, через `XDimension` в миллиметрах.
- **Нужна ли лицензия для продакшн?** Да, требуется коммерческая лицензия.

## Предварительные требования

Прежде чем приступить к руководству, убедитесь, что у вас есть следующее:

- Базовое понимание программирования на Java.  
- Установленная рабочая среда разработки Java.  
- Библиотека Aspose.BarCode for Java. Вы можете скачать её **[here](https://releases.aspose.com/barcode/java/)**.  
- Редактор кода, например IntelliJ IDEA или Eclipse.  

## Импорт пакетов

Начните с импорта необходимых пакетов в ваш проект Java. Эти пакеты необходимы для работы с Aspose.BarCode.

```java
import com.aspose.barcode.generation.BarcodeGenerator;
```

Теперь давайте рассмотрим процесс установки текста кода с помощью Aspose.BarCode в Java. Следуйте этим шагам:

## Руководство по генератору штрихкодов: Создание штрихкода Code128

### Шаг 1: Создание экземпляра `BarcodeGenerator`

```java
// The path to the documents directory.
String path = "Your Directory Path";
// The path to the resource directory.
String dataDir = "Your Document Directory";
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");
```

Здесь мы создаём экземпляр `BarcodeGenerator`, указывая символьную схему штрихкода (**CODE_128**) и **пользовательский текст штрихкода** `"12345678"`.

### Шаг 2: Регулировка ширины штрихкода для пользовательского текста

```java
generator.getParameters().getBarcode().getXDimension().setMillimeters(0.5f);
```

Отрегулируйте ширину полос по вашему усмотрению. В этом примере мы **регулируем ширину штрихкода** до `0.5` mm, что подходит для большинства размеров этикеток.

### Шаг 3: Сохранение изображения штрихкода

```java
generator.save(dataDir + "setCodeText.jpg");
```

Сохраните сгенерированное изображение штрихкода в указанную директорию. В данном случае файл сохраняется как **`setCodeText.jpg`** в вашей директории документов.

## Почему использовать Aspose.BarCode для Java?

- **Comprehensive API** – Поддерживает более 60 символьных схем штрихкодов, включая Code128, QR, DataMatrix и другие.  
- **High‑quality rendering** – Генерирует чёткие изображения в форматах PNG, JPEG, SVG и PDF.  
- **Easy customization** – Изменяйте текст, размер, цвета и даже добавляйте подписи, читаемые человеком, несколькими строками кода.  
- **Cross‑platform** – Работает на Windows, Linux и macOS с любой средой выполнения Java 8+.

## Распространённые проблемы и решения

| Issue | Solution |
|-------|----------|
| **Barcode looks blurry** | Увеличьте разрешение изображения или экспортируйте в векторные форматы (SVG, PDF). |
| **Text is truncated** | Убедитесь, что `XDimension` (ширина полосы) и `BarHeight` достаточно велики для выбранной символьной схемы. |
| **License not applied** | Поместите файл лицензии (`Aspose.BarCode.lic`) в корень проекта и загрузите его с помощью `License license = new License(); license.setLicense("Aspose.BarCode.lic");`. |

## Дополнительные часто задаваемые вопросы

**Q:** *В чём разница между `CODE_128` и другими вариантами Code128?*  
**A:** `CODE_128` — стандартная символьная схема, которая автоматически выбирает наиболее эффективное кодирование (A, B или C) в зависимости от входного текста.

**Q:** *Можно ли изменить формат вывода на PNG вместо JPEG?*  
**A:** Конечно. Используйте `generator.save(dataDir + "setCodeText.png", com.aspose.barcode.BarcodeImageFormat.PNG);`.

**Q:** *Можно ли добавить подпись, читаемую человеком, под штрихкодом?*  
**A:** Да. Установите `generator.getParameters().getBarcode().getCaption().setTopMargin(5);` и задайте текст подписи.

**Q:** *Поддерживает ли Aspose.BarCode Unicode‑символы?*  
**A:** Да. Передайте текст в UTF‑8 и убедитесь, что выбранная символьная схема поддерживает данный набор символов.

**Q:** *Как сгенерировать несколько штрихкодов в цикле?*  
**A:** Создайте новый `BarcodeGenerator` внутри цикла, задайте текст для каждой итерации и вызовите `save` с уникальным именем файла.

---

**Последнее обновление:** 2025-12-30  
**Тестировано с:** Aspose.BarCode 24.12 for Java  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
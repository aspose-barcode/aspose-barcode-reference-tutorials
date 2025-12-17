---
date: 2025-12-17
description: Узнайте, как создать изображение штрих‑кода в Java и как задать символы
  с помощью Aspose.BarCode. Это пошаговое руководство покажет, как сгенерировать штрих‑код
  Codabar с пользовательскими стартовыми/конечными символами.
linktitle: Setting Start and Stop Symbols
second_title: Aspose.BarCode Java API
title: Создание изображения штрихкода в Java – установка стартовых и стоп‑символов
url: /ru/java/barcode-configuration/setting-start-stop-symbols/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание изображения штрих‑кода Java – установка стартовых и конечных символов

## Введение

В этом полном руководстве вы **создадите файлы barcode image java** с помощью Aspose.BarCode for Java и узнаете **как задать символы** для штрих‑кодов Codabar. Независимо от того, разрабатываете ли вы систему точек продаж, логистическое приложение или любое решение, требующее надёжного создания штрих‑кодов, настройка стартовых и конечных символов даёт вам полный контроль над форматом штрих‑кода. Мы пройдём каждый шаг, объясним, почему важна каждая настройка, и покажем, как получить готовое PNG‑изображение.

## Быстрые ответы
- **Какая библиотека создаёт изображения штрих‑кодов в Java?** Aspose.BarCode for Java.  
- **Можно ли настроить стартовые/конечные символы?** Да, с помощью `setCodabarStartSymbol` и `setCodabarStopSymbol`.  
- **Какой тип штрих‑кода используется в примере?** CODABAR.  
- **Нужна ли лицензия для продакшн‑использования?** Для использования не в режиме пробной версии требуется коммерческая лицензия.  
- **В каком формате генерируется вывод?** PNG‑изображение, сохраняемое на диск.

## Что такое «create barcode image java»?

Создание изображения штрих‑кода в Java означает программное получение визуального представления (обычно PNG, JPG или BMP) символьного набора штрих‑кода, которое может быть считано стандартными сканерами. Aspose.BarCode предоставляет удобный API, скрывающий детали низкоуровневого кодирования, позволяя сосредоточиться на бизнес‑логике.

## Почему использовать Aspose.BarCode для генерации штрих‑кода?

Aspose.BarCode предлагает:
- **Широкую поддержку символьных наборов** (включая CODABAR, QR, DataMatrix и др.).  
- **Тонкую настройку** внешнего вида, размеров и параметров кодирования.  
- **Кроссплатформенную совместимость** с любой Java‑средой.  
- **Отсутствие внешних зависимостей**, что упрощает развертывание.

## Требования

Прежде чем приступить, убедитесь, что у вас есть:

1. **Java Development Kit (JDK)** – установите последнюю версию JDK с сайта [Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).  
2. **Библиотека Aspose.BarCode for Java** – скачайте её по [ссылке загрузки](https://releases.aspose.com/barcode/java/).

Наличие этих компонентов гарантирует, что вы сможете **generate barcode image java** без проблем.

## Импорт пакетов

В вашем Java‑проекте импортируйте необходимые классы для работы с Aspose.BarCode:

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.CodabarSymbol;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Пошаговое руководство

### Шаг 1: Определите каталог документа

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Замените `"Your Document Directory"` на абсолютный или относительный путь, где вы хотите сохранить изображение штрих‑кода.

### Шаг 2: Создайте экземпляр Barcode Generator

```java
// Create instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "12345678");
```

Здесь мы указываем Aspose.BarCode использовать символьный набор **CODABAR** и строку данных `"12345678"`.

### Шаг 3: Установите стартовый символ Codabar

```java
// Set the Codabar start symbol to A
generator.getParameters().getBarcode().getCodabar().setCodabarStartSymbol(CodabarSymbol.A);
```

Метод `setCodabarStartSymbol` позволяет **how to set symbols** для стартового символа. В данном случае выбираем `A`.

### Шаг 4: Установите конечный символ Codabar

```java
// Set the Codabar stop symbol to D
generator.getParameters().getBarcode().getCodabar().setCodabarStopSymbol(CodabarSymbol.D);
```

Аналогично, `setCodabarStopSymbol` задаёт конечный символ. Использование `D` завершает формат CODABAR, требуемый многими устаревшими системами.

### Шаг 5: Сохраните сгенерированное изображение

```java
// Save the image to disk in PNG format
generator.save(dataDir + "startAndStopSymbols.png");
```

Вызов `save` записывает штрих‑код в PNG‑файл **startAndStopSymbols.png** в указанный ранее каталог.

### Распространённые ошибки и советы

- **Неправильный путь к каталогу** – Убедитесь, что `dataDir` заканчивается разделителем файлов (`/` или `\`) или используйте конкатенацию через `Paths.get`.  
- **Неподдерживаемые стартовые/конечные символы** – CODABAR поддерживает только A, B, C, D в качестве стартовых и конечных символов. Любое другое значение вызовет исключение.  
- **Лицензия не применена** – В пробном режиме сгенерированное изображение может содержать водяной знак. Примените лицензию перед развертыванием в продакшн.

## Заключение

Теперь вы знаете, как **create barcode image java** и точно **how to set symbols** для штрих‑кода Codabar с помощью Aspose.BarCode. Этот подход даёт гибкость для соответствия отраслевым требованиям к штрих‑кодам, сохраняя ваш код чистым и поддерживаемым.

Изучайте дополнительные возможности настройки — изменение цветов, добавление читаемого текста или переход к другим символьным наборам — в официальной документации API по ссылке [documentation](https://reference.aspose.com/barcode/java/).

## Часто задаваемые вопросы

### Можно ли использовать Aspose.BarCode for Java в коммерческом проекте?
Да, можно. Для коммерческого использования приобретите лицензию [здесь](https://purchase.aspose.com/buy).

### Доступна ли бесплатная пробная версия?
Да, бесплатную пробную версию можно скачать [здесь](https://releases.aspose.com/).

### Как получить поддержку по Aspose.BarCode for Java?
Посетите форум Aspose.BarCode [здесь](https://forum.aspose.com/c/barcode/13) для вопросов и поддержки.

### Как получить временную лицензию?
При необходимости временную лицензию можно оформить [здесь](https://purchase.aspose.com/temporary-license/).

### Поддерживает ли Aspose.BarCode for Java другие символьные наборы?
Да, Aspose.BarCode поддерживает широкий спектр символьных наборов штрих‑кодов. Смотрите полную таблицу в документации.

**Дополнительные вопросы и ответы**

**В: Какие форматы изображений можно экспортировать помимо PNG?**  
О: Aspose.BarCode поддерживает PNG, JPEG, BMP, GIF и TIFF. Указывайте соответствующее расширение в методе `save`.

**В: Можно ли генерировать изображения штрих‑кода в памяти без записи на диск?**  
О: Да, вызовите `generator.save(OutputStream)`, чтобы записать напрямую в поток, что удобно для веб‑ответов.

**В: Работает ли библиотека на Android?**  
О: Версия Java совместима с Android, однако необходимо вручную добавить требуемые зависимости.

---

**Последнее обновление:** 2025-12-17  
**Тестировано с:** Aspose.BarCode for Java 24.12  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
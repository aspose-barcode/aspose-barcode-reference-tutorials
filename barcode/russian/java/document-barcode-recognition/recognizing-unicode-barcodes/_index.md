---
date: 2025-12-21
description: Узнайте, как считывать изображение штрихкода с помощью библиотеки Aspose.BarCode
  для Java, охватывая генерацию штрихкода PDF417 на Java и распознавание Unicode‑штрихкода.
linktitle: Recognizing Unicode Barcodes
second_title: Aspose.BarCode Java API
title: Как считать изображение штрих‑кода с Unicode‑штрих‑кодами в Java
url: /ru/java/document-barcode-recognition/recognizing-unicode-barcodes/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Распознавание Unicode штрихкодов в Java

## Введение

Если вам нужно **how to read barcode image** в Java‑приложении, особенно когда штрихкод содержит Unicode‑символы, вы попали по адресу. В этом руководстве мы пройдем каждый шаг, необходимый для распознавания Unicode‑штрихкодов — например, арабского, китайского или кириллического текста — с помощью мощной библиотеки Aspose.BarCode. К концу вы сможете уверенно генерировать и считывать такие штрихкоды, расширяя охват вашего программного обеспечения на глобальную аудиторию.

## Быстрые ответы
- **Какая библиотека лучше всего подходит для чтения штрихкодов в Java?** Aspose.BarCode for Java.  
- **Можно ли генерировать PDF417 штрихкоды с Unicode‑текстом?** Да, используя класс `BarcodeGenerator`.  
- **Нужна ли лицензия для использования в продакшене?** Требуется действующая лицензия Aspose.BarCode.  
- **Какая версия Java поддерживается?** Java 8 и выше.  
- **Есть ли бесплатная пробная версия?** Да, её можно скачать с сайта Aspose.

## Что такое «how to read barcode image» в Java?

Чтение изображения штрихкода означает декодирование визуального шаблона в исходную строку данных. Когда данные содержат Unicode‑символы, библиотека должна правильно обрабатывать кодировку и декодирование символов, что Aspose.BarCode делает автоматически после преобразования текста в нужный кодовый формат.

## Почему стоит использовать Aspose.BarCode для pdf417 barcode generation java?

Aspose.BarCode предоставляет простой API для **pdf417 barcode generation java**, поддерживает широкий набор символогий и из коробки работает с Unicode‑кодировкой. Это делает её идеальной для корпоративных приложений, требующих надёжной и высокопроизводительной обработки штрихкодов.

## Предварительные требования

Прежде чем приступить, убедитесь, что у вас есть:

- Базовые знания программирования на Java.  
- Установленная библиотека Aspose.BarCode for Java. Скачать её можно [здесь](https://releases.aspose.com/barcode/java/).  
- Действующая лицензия Aspose.BarCode. Получить её можно [здесь](https://purchase.aspose.com/buy).

## Импорт пакетов

Чтобы начать, импортируйте необходимые пакеты в ваш Java‑проект. Библиотека Aspose.BarCode предоставляет полный набор функций для генерации и распознавания штрихкодов.

```java
import com.aspose.barcode.*;
import com.aspose.barcode.generation.BarcodeGenerator;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;

import java.io.IOException;
import java.io.UnsupportedEncodingException;
```

## Шаг 1: Установите каталог ресурсов

Определите путь к вашему каталогу ресурсов.

```java
String dataDir = "Your Document Directory";
```

## Шаг 2: Установите лицензию Aspose.BarCode

Загрузите вашу лицензию Aspose.BarCode, чтобы открыть полный потенциал библиотеки.

```java
try {
    License lic = new License();
    lic.setLicense("aspose.barcode.lic");
} catch (Exception ex) {
    System.out.println(ex.getMessage());
}
```

## Шаг 3: Сгенерируйте Unicode‑штрихкод

Создайте Unicode‑штрихкод, используя заданный текст.

```java
String file = dataDir + "pdf417_un.png";
String scodeText = "منحة";
System.out.println("codetext: " + scodeText);
String codeText = getCodeTextFromUnicode(scodeText);
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.PDF_417, codeText);
generator.save(file);
```

## Шаг 4: Считайте Unicode‑штрихкод

Прочитайте сгенерированный Unicode‑штрихкод.

```java
BarCodeReader reader = new BarCodeReader(file, DecodeType.PDF_417);
for (BarCodeResult result : reader.readBarCodes()) {
    String rc = result.getCodeText();
    try {
        String s = getUnicodeFromCodeText(rc);
        System.out.println(s);
    } catch (UnsupportedEncodingException e) {
        e.printStackTrace();
    }
}
```

## Шаг 5: Преобразуйте Unicode в кодовый текст

Реализуйте метод для преобразования Unicode в кодовый текст.

```java
private static String getCodeTextFromUnicode(String s) throws UnsupportedEncodingException {
    // Implementation details
}
```

## Шаг 6: Преобразуйте кодовый текст в Unicode

Реализуйте метод для преобразования кодового текста в Unicode.

```java
private static String getUnicodeFromCodeText(String cs) throws UnsupportedEncodingException {
    // Implementation details
}
```

## Распространённые проблемы и их решения

| Проблема | Причина | Решение |
|----------|---------|---------|
| Искажённый вывод после чтения | Неправильная кодировка символов | Убедитесь, что `getUnicodeFromCodeText` использует ту же кодировку (`UTF‑8`), что и `getCodeTextFromUnicode`. |
| `Reader` возвращает `null` | Неправильный `DecodeType` | Используйте `DecodeType.PDF_417` для PDF417 штрихкодов. |
| Лицензия не применяется | Неправильный путь к файлу лицензии | Поместите `aspose.barcode.lic` в корень проекта или укажите абсолютный путь. |

## Часто задаваемые вопросы

### Требуется ли лицензия для Aspose.BarCode?
Да, для Aspose.BarCode необходима действующая лицензия. Её можно получить [здесь](https://purchase.aspose.com/buy).

### Где найти документацию Aspose.BarCode?
Документация доступна [здесь](https://reference.aspose.com/barcode/java/).

### Можно ли попробовать Aspose.BarCode бесплатно?
Да, бесплатную пробную версию можно получить [здесь](https://releases.aspose.com/).

### Как получить временную лицензию для Aspose.BarCode?
Временные лицензии доступны [здесь](https://purchase.aspose.com/temporary-license/).

### Нужна поддержка или есть вопросы?
Посетите [форум Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

## Часто задаваемые вопросы

**В: Можно ли использовать этот код с другими символогиями штрихкодов?**  
О: Конечно. Замените `EncodeTypes.PDF_417` на любую поддерживаемую, например `EncodeTypes.CODE_128`, и соответственно измените `DecodeType`.

**В: Что произойдёт, если входной текст содержит эмодзи?**  
О: Эмодзи — это Unicode‑символы; они будут корректно закодированы, если методы преобразования работают с UTF‑8.

**В: Можно ли читать штрихкоды из потока, а не из файла?**  
О: Да, `BarCodeReader` принимает `InputStream` в качестве первого аргумента.

**В: Как улучшить скорость распознавания при обработке больших партий?**  
О: Переиспользуйте один экземпляр `BarCodeReader` и обрабатывайте изображения в цикле, своевременно освобождая каждый результат.

**В: Поддерживает ли Aspose.BarCode многостраничные PDF для извлечения штрихкодов?**  
О: Да. Используйте `BarCodeReader` с путём к PDF‑файлу — библиотека автоматически перебирает все страницы.

## Заключение

Поздравляем! Теперь вы владеете навыком **how to read barcode image** в Java с помощью Aspose.BarCode, от генерации Unicode‑PDF417 штрихкода до его декодирования обратно в исходный текст. Эта возможность открывает двери для интернационализированных приложений, многоязычных систем учёта и любых сценариев, где требуются глобальные наборы символов.

---

**Последнее обновление:** 2025-12-21  
**Тестировано с:** Aspose.BarCode for Java 24.11  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
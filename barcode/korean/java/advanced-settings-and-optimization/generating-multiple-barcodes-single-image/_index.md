---
date: 2026-10-19
description: Aspose.BarCode for Java를 사용하여 QR 코드 Java를 만들고 하나의 이미지에 여러 바코드를 생성하는 방법을
  배웁니다. 설정, 코드, 문제 해결을 포함합니다.
keywords:
- create qr code java
- how to create qr
- java barcode library
- generate multiple barcodes
- aspose trial license
lastmod: 2026-10-19
linktitle: 하나의 이미지에 여러 바코드 생성하기
og_description: Aspose.BarCode for Java와 함께 QR 코드 Java를 만들고 여러 바코드 유형을 하나의 이미지로 결합합니다.
  단계별 가이드를 따라 코드 스니펫을 확인하고 문제 해결 팁을 배웁니다.
og_image_alt: Screenshot of a Java application generating a QR code and other barcodes
  on one combined image
og_title: QR 코드 Java 만들기 – 하나의 이미지에 여러 바코드 생성
schemas:
- author: Aspose
  dateModified: '2026-10-19'
  description: Learn how to create QR code java and generate multiple barcodes on
    a single image using Aspose.BarCode for Java. Includes setup, code, and troubleshooting.
  headline: Create QR code java – generate multiple barcodes on one image
  type: TechArticle
- questions:
  - answer: Yes. Use the `BarcodeGenerator` properties such as `setBarColor`, `setBackgroundColor`,
      and `setXDimension` to style each barcode independently before adding it to
      the canvas.
    question: Can I customize the appearance of individual barcodes in the generated
      image?
  - answer: Absolutely. The library supports 50+ symbologies, including CODE_39, DATA_MATRIX,
      QR, CODE_128, EAN_13, and AZTEC, as demonstrated in this tutorial.
    question: Is Aspose.BarCode compatible with different barcode symbologies?
  - answer: Download the JAR from the Aspose.BarCode for Java library download page,
      add it to your project’s classpath, and import the required namespaces as shown
      in the “Import namespaces” section.
    question: How do I integrate Aspose.BarCode into my Java project?
  - answer: Yes. Purchase a license from the Aspose.BarCode license purchase page
      to remove trial limitations and obtain full production support.
    question: Can I use Aspose.BarCode for commercial applications?
  - answer: Certainly. A free trial license is available from the Aspose.BarCode free
      trial download page, giving you full API access for evaluation.
    question: Are there trial options available for Aspose.BarCode?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- create qr code
- aspose barcode
- java barcode generation
- multiple barcodes image
title: QR 코드 Java 만들기 – 하나의 이미지에 여러 바코드 생성
url: /ko/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# QR 코드 java 생성 – 하나의 이미지에 여러 바코드 생성

## 소개

이 튜토리얼에서는 **QR 코드 java 생성 방법**을 배우고 **Aspose.BarCode for Java**를 사용하여 여러 종류의 바코드를 하나의 캔버스에 병합하는 방법을 알아봅니다. 컴팩트한 QR 라벨, 제품 바코드, 혹은 2‑D와 선형 심볼을 혼합한 경우 등, 이 가이드는 프로젝트 설정부터 최종 결합 이미지 저장까지 모든 단계를 안내하므로 Java 애플리케이션에 바코드 생성을 바로 통합할 수 있습니다.

## 빠른 답변
- **어떤 라이브러리를 사용해야 하나요?** Aspose.BarCode for Java는 가장 완전한 심볼 세트를 제공합니다.  
- **다른 바코드 유형을 함께 생성할 수 있나요?** 예, CODE_39, QR, AZTEC 등 여러 종류를 하나의 캔버스에 혼합할 수 있습니다.  
- **개발에 라이선스가 필요합니까?** 무료 체험판으로 테스트가 가능하며, 상용 환경에서는 상업용 라이선스가 필요합니다.  
- **지원되는 Java 버전은 무엇인가요?** Java 8 및 그 이후 버전과 완전히 호환됩니다.  
- **출력 형식을 설정할 수 있나요?** 결합된 이미지를 PNG, JPEG, BMP 또는 TIFF 형식으로 내보낼 수 있습니다.

## create QR code java란?

`create QR code java`는 텍스트 문자열을 스마트폰이나 바코드 리더기로 스캔할 수 있는 2차원 매트릭스로 변환하는 과정을 의미합니다. Aspose.BarCode for Java가 인코딩 및 렌더링을 수행하므로 픽셀 수준 이미지 처리를 신경 쓰지 않고 비즈니스 로직에 집중할 수 있습니다.

## Java에서 바코드 생성에 Aspose.BarCode Java를 사용하는 이유

Aspose.BarCode는 **50개 이상의 바코드 심볼**(QR, Data Matrix, Code 128, AZTEC 및 전통적인 선형 코드 포함)을 지원하여 가장 다재다능한 Java 바코드 라이브러리입니다. **최대 1200 dpi의 안티앨리어싱 이미지**를 렌더링하여 화면 및 인쇄 시 선명한 스캔을 보장합니다. API는 JVM만 필요하며 몇 줄의 코드로 크기, 색상, 여백 및 오류 정정을 맞춤 설정할 수 있는 유창한 구성 모델을 제공합니다.

## 사전 요구 사항

- Java 기본 지식에 대한 확고한 이해.  
- JDK 8 이상 설치 및 PATH에 설정.  
- Aspose.BarCode for Java JAR(공식 Aspose.BarCode for Java 다운로드 페이지에서 다운로드).  
- IntelliJ IDEA 또는 Eclipse와 같은 IDE를 사용하여 샘플을 편집하고 실행.

## 네임스페이스 가져오기

Import 문은 `BarcodeGenerator`, `EncodeTypes`, `BarCodeImageFormat`와 같은 Aspose.BarCode 클래스를 스코프로 가져와 완전한 이름 없이 참조할 수 있게 합니다.  
`BarcodeGenerator`는 바코드 이미지를 구성하고 생성하는 데 사용되는 주요 클래스입니다.  
`EncodeTypes`는 Aspose.BarCode에서 생성할 바코드 심볼을 지정하는 열거형입니다.  
`BarCodeImageFormat`은 생성된 바코드의 출력 이미지 형식을 정의합니다.

## 단계 1: 리소스 디렉터리 설정

**리소스 디렉터리**는 생성된 모든 바코드 이미지가 기록되는 파일 시스템상의 폴더입니다. 한 번 정의하면 프로젝트가 정리되고 오래된 파일을 쉽게 정리할 수 있습니다.

```java
import java.awt.Color;
import java.awt.Graphics;
import java.awt.image.BufferedImage;
import java.io.File;
import java.util.ArrayList;
import java.util.HashMap;

import javax.imageio.ImageIO;

import com.aspose.barcode.BaseEncodeType;
import com.aspose.barcode.EncodeTypes;


import com.aspose.barcode.generation.BarcodeGenerator;
```

## 단계 2: 바코드 컬렉션 생성

`HashMap<String, EncodeTypes>`는 각 바코드의 데이터 문자열과 사용하려는 심볼을 함께 저장합니다. `HashMap`은 키를 값에 매핑하는 Java 컬렉션입니다. 이 컬렉션은 이후의 생성 루프를 구동합니다. `EncodeTypes`는 생성할 바코드 유형을 지정하는 열거형입니다.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## 단계 3: 바코드 이미지 생성

생성 루프는 `HashMap`을 순회하면서 각 항목에 대해 `BarcodeGenerator`를 생성하고 `generateBarCodeImage()`를 호출하여 `BufferedImage`를 얻습니다. `generateBarCodeImage()`는 렌더링된 바코드를 포함하는 `BufferedImage`를 생성합니다. `BufferedImage`는 메모리 내 이미지를 나타내는 Java 클래스입니다. 모든 이미지는 나중에 합성을 위해 `ArrayList<BufferedImage>`에 추가됩니다. `ArrayList`는 Java의 가변 길이 리스트 구현입니다.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## 단계 4: 결합 이미지 생성

먼저 알고리즘은 모든 바코드 이미지 중 **최대 너비**와 선택적 간격을 포함해 수직으로 쌓기에 필요한 **전체 높이**를 계산합니다. 그런 다음 해당 크기의 `BufferedImage`를 생성하고 `Graphics2D` 객체를 사용해 각 바코드를 캔버스에 그립니다. `Graphics2D`는 도형 및 이미지를 그리기 위한 2D 렌더링 기능을 제공하는 Java 클래스입니다.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## 단계 5: 결과 저장

마지막으로, 합성 이미지는 `ImageIO.write`를 사용해 지정한 형식(PNG, JPEG, BMP 또는 TIFF)으로 디스크에 기록됩니다. `ImageIO.write`는 `BufferedImage`를 지정된 형식의 파일에 씁니다. 파일 경로는 앞서 정의한 리소스 디렉터리를 기준으로 상대 경로입니다.

```java
int maxWidth = 0;
int sumHeight = 0;
for (BufferedImage bmp : images) {
    sumHeight += bmp.getHeight();
    if (maxWidth < bmp.getWidth())
        maxWidth = bmp.getWidth();
}

int offset = 10;
BufferedImage resultBitmap = new BufferedImage(maxWidth + offset * 2, sumHeight + offset * images.size(),
        BufferedImage.TYPE_INT_ARGB);
Graphics g = resultBitmap.getGraphics();
g.setColor(Color.white);
g.fillRect(0, 0, resultBitmap.getWidth(), resultBitmap.getHeight());

int yPosition = offset;
for (int i = 0; i < images.size(); ++i) {
    BufferedImage currentBitmap = images.get(i);
    g.drawImage(currentBitmap, offset, yPosition, null);
    yPosition += currentBitmap.getHeight() + offset;
}
```

## 다중 바코드 생성의 일반적인 사용 사례

- **포장 라벨** – 하나의 라벨에 제품, 배치 및 배송 코드를 결합하여 인쇄 비용을 절감합니다.  
- **이벤트 티켓** – 현장에서 다양한 스캔 스테이션을 위해 QR, Data Matrix 및 Code 128 식별자를 삽입합니다.  
- **재고 관리** – SKU, RFID 태그 데이터 및 일련 번호를 함께 표시하여 빠른 감사와 추적성을 제공합니다.

## 문제 해결 및 팁

- **이미지 크기 문제** – 바코드 간 간격을 늘리거나 줄이려면 `offset` 변수를 조정합니다.  
- **지원되지 않는 심볼** – 사용 중인 Aspose.BarCode 버전이 원하는 바코드 유형을 지원하는지 확인하십시오; 최신 릴리스는 추가 2‑D 코드를 포함합니다.  
- **성능** – 루프에서 다수의 이미지를 생성할 때 단일 `Graphics2D` 객체를 재사용하여 객체 할당 오버헤드를 최소화합니다.

## 자주 묻는 질문

**Q: 생성된 이미지에서 개별 바코드의 모양을 사용자 지정할 수 있나요?**  
A: 예. `BarcodeGenerator`의 `setBarColor`, `setBackgroundColor`, `setXDimension`와 같은 속성을 사용하여 캔버스에 추가하기 전에 각 바코드를 독립적으로 스타일링할 수 있습니다.

**Q: Aspose.BarCode가 다양한 바코드 심볼과 호환되나요?**  
A: 물론입니다. 이 라이브러리는 CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13, AZTEC 등을 포함한 50개 이상의 심볼을 지원하며, 본 튜토리얼에서 시연됩니다.

**Q: Aspose.BarCode를 Java 프로젝트에 어떻게 통합하나요?**  
A: Aspose.BarCode for Java 라이브러리 다운로드 페이지에서 JAR를 다운로드하고 프로젝트 클래스패스에 추가한 뒤, “Import namespaces” 섹션에 표시된 대로 필요한 네임스페이스를 import합니다.

**Q: Aspose.BarCode를 상업용 애플리케이션에 사용할 수 있나요?**  
A: 예. Aspose.BarCode 라이선스 구매 페이지에서 라이선스를 구매하면 체험판 제한이 해제되고 전체 생산 지원을 받을 수 있습니다.

**Q: Aspose.BarCode에 대한 체험 옵션이 있나요?**  
A: 물론입니다. Aspose.BarCode 무료 체험 다운로드 페이지에서 무료 체험 라이선스를 제공받아 전체 API에 접근하여 평가할 수 있습니다.

**Q: 인쇄용 고해상도 QR 코드를 어떻게 생성하나요?**  
A: `generateBarCodeImage()`를 호출하기 전에 `BarcodeGenerator`의 `setResolutionDpi` 속성을 설정하고, 결과를 PNG와 같은 무손실 형식으로 저장합니다.

**Q: 결합된 이미지가 잘려 보이면 어떻게 해야 하나요?**  
A: `offset` 및 캔버스 크기 계산이 모든 바코드 높이를 올바르게 고려하는지 확인하십시오; 캔버스 높이를 늘리거나 개별 바코드 크기를 줄이면 대부분의 잘림 문제를 해결할 수 있습니다.

**마지막 업데이트:** 2026-10-19  
**테스트 환경:** Aspose.BarCode for Java 24.11  
**작성자:** Aspose  








```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## 관련 튜토리얼

- [Java에서 바코드 이미지 생성 – Aspose로 테두리 추가](/barcode/java/image-manipulation/adding-borders-barcode-image/)
- [Java에서 바코드 생성: Aspose.BarCode로 스트림에 저장](/barcode/java/advanced-settings-and-optimization/saving-barcode-image-streams/)
- [Java에서 바코드 생성 및 Aspose로 바코드 인쇄](/barcode/java/barcode-rendering-techniques/rendering-barcode-printer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
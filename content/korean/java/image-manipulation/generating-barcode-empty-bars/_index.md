---
title: Java에서 빈 막대가 있는 바코드 생성
linktitle: 빈 막대가 있는 바코드 생성
second_title: Aspose.BarCode 자바 API
description: Aspose.BarCode를 사용하여 Java에서 빈 막대가 있는 바코드를 손쉽게 생성하세요. 외관을 맞춤화하고 원활하게 통합하세요. 지금 튜토리얼을 살펴보세요!
type: docs
weight: 14
url: /ko/java/image-manipulation/generating-barcode-empty-bars/
---

## 소개

역동적인 소프트웨어 개발 세계에서는 바코드 생성 기능을 Java 애플리케이션에 통합하는 것이 일반적인 요구 사항이 되었습니다. Aspose.BarCode for Java는 개발자에게 다양한 유형의 바코드를 생성할 수 있는 강력한 도구 세트를 제공하는 강력한 솔루션으로 돋보입니다. 이 튜토리얼에서는 Aspose.BarCode for Java를 사용하여 빈 막대가 있는 바코드를 생성하는 과정을 자세히 살펴보겠습니다.

## 전제 조건

바코드 생성 여정을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하십시오.

1. Java 개발 환경: 컴퓨터에 Java 개발 환경이 설정되어 있는지 확인하세요.

2.  Java 라이브러리용 Aspose.BarCode: 다음에서 Java 라이브러리용 Aspose.BarCode를 다운로드하고 설치합니다.[다운로드 페이지](https://releases.aspose.com/barcode/java/).

3. 문서 디렉터리: 생성된 바코드 이미지를 저장할 디렉터리를 시스템에 만듭니다.

## 패키지 가져오기

Java 프로젝트에서 Aspose.BarCode 작업에 필요한 패키지를 가져옵니다.

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## 1단계: 리소스 디렉터리 설정

```java
// 리소스 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
```

 바꾸다`"Your Document Directory"`문서 디렉토리의 실제 경로를 사용하십시오.

## 2단계: 바코드 생성기 인스턴스 생성

```java
// BarcodeGenerator의 인스턴스를 생성하고 CodeText 및 Symbology로 초기화합니다.
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

여기서는 CODE_128 기호와 "TEXT"라는 텍스트를 인코딩할 코드로 사용하여 BarcodeGenerator 인스턴스를 생성합니다.

## 3단계: FilledBars 속성을 False로 설정

```java
// FilledBars 속성을 false로 설정합니다.
generator.getParameters().getBarcode().setFilledBars(false);
```

 설정으로`FilledBars` 에게`false`, 생성된 바코드에 빈 막대가 있는지 확인합니다.

## 4단계: 바코드 이미지 저장

```java
// 결과 바코드 이미지를 디스크에 저장
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

이 단계에는 생성된 바코드 이미지를 지정된 디렉터리에 PNG 형식으로 저장하는 작업이 포함됩니다.

Java 애플리케이션에서 이 단계를 반복하면 Aspose.BarCode for Java를 사용하여 빈 막대가 있는 바코드를 손쉽게 생성할 수 있습니다.

## 결론

결론적으로 이 튜토리얼에서는 Aspose.BarCode 라이브러리를 사용하여 Java에서 빈 막대가 있는 바코드를 생성하는 과정을 안내했습니다. 직관적인 API와 광범위한 문서를 통해 Aspose.BarCode는 바코드 통합을 단순화하여 개발자에게 귀중한 자산이 됩니다.

## 자주 묻는 질문

### Aspose.BarCode는 모든 Java 개발 환경과 호환됩니까?
예, Aspose.BarCode는 다양한 Java 개발 환경과 원활하게 통합되도록 설계되었습니다.

### 생성된 바코드의 모양을 사용자 정의할 수 있나요?
전적으로! Aspose.BarCode는 사용자 정의를 위한 다양한 옵션을 제공하므로 특정 요구 사항에 맞게 바코드를 조정할 수 있습니다.

### Aspose.BarCode에 평가판을 사용할 수 있나요?
 예, 무료 평가판을 통해 Aspose.BarCode의 기능을 탐색할 수 있습니다.[여기](https://releases.aspose.com/).

### Aspose.BarCode에 대한 지원은 어떻게 받을 수 있나요?
 질문이나 도움이 필요하면 다음을 방문하세요.[Aspose.BarCode 포럼](https://forum.aspose.com/c/barcode/13).

### Aspose.BarCode에 대한 자세한 문서는 어디서 찾을 수 있나요?
 포괄적인 문서를 사용할 수 있습니다.[여기](https://reference.aspose.com/barcode/java/).
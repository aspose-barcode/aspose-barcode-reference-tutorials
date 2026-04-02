---
date: 2025-12-27
description: Aspose.BarCode를 사용하여 Java에서 데이터 매트릭스 바코드를 생성하고 바코드 텍스트 위치를 설정하는 방법을 배워보세요.
  전체 맞춤화를 위한 단계별 가이드를 따라보세요.
linktitle: Setting Code Text Location
second_title: Aspose.BarCode Java API
title: Java에서 데이터 매트릭스 바코드를 생성하고 코드 텍스트 위치 설정
url: /ko/java/text-and-styling/setting-code-text-location/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java에서 Data Matrix 바코드 생성 및 코드 텍스트 위치 설정

## 소개

바코드 생성은 재고 관리, 배송 및 기타 많은 Java 기반 애플리케이션에서 일상적인 요구 사항입니다. **Aspose.BarCode for Java**를 사용하면 **Data Matrix 바코드**를 빠르게 생성하고 인간이 읽을 수 있는 텍스트가 표시되는 위치를 포함하여 모든 시각적 요소를 제어할 수 있습니다. 이 튜토리얼에서는 **Data Matrix 바코드**를 생성하는 정확한 단계와 심볼 위에 **바코드 텍스트를 설정하는 방법**을 보여드려 디자인 사양에 맞추는 방법을 설명합니다.

## 빠른 답변
- **어떤 라이브러리를 사용합니까?** Aspose.BarCode for Java  
- **어떤 바코드 유형이 시연됩니까?** Data Matrix  
- **코드 텍스트를 어떻게 위치시키나요?** `CodeLocation.ABOVE` 사용  
- **프로덕션에 라이선스가 필요합니까?** 예, 상업용 라이선스가 필요합니다  
- **코드가 Java 8+에서 실행될 수 있나요?** 물론입니다, Java 8 및 이후 버전을 지원합니다  

## Data Matrix 바코드란 무엇인가요?

Data Matrix 바코드는 큰 양의 데이터를 컴팩트한 정사각형 또는 직사각형 패턴에 저장하는 2차원(2‑D) 심볼입니다. 2,335개의 영숫자 문자까지 인코딩할 수 있어 작은 부품, 전자 제품 및 의료 기기 등에 널리 사용됩니다.

## 바코드 텍스트 위치를 설정하는 이유는?

인간이 읽을 수 있는 텍스트를 바코드 **위에**, **아래에**, 혹은 **옆에** 배치하면 사용자가 스캔 없이도 인코딩된 데이터를 빠르게 확인할 수 있습니다. 텍스트 위치를 조정하면 UI 일관성이 향상되고 브랜드 가이드라인을 충족할 수 있습니다.

## 전제 조건

- Java 프로그래밍에 대한 기본 지식.  
- Java Development Kit (JDK) 설치.  
- Eclipse 또는 IntelliJ IDEA와 같은 IDE.  
- Aspose.BarCode for Java 라이브러리([here](https://releases.aspose.com/barcode/java/)에서 다운로드).

## 패키지 가져오기

먼저, 프로젝트에 필수 Aspose.BarCode 클래스를 가져옵니다:

```java
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.generation.BarcodeGenerator;
```

이러한 import를 통해 바코드 생성기와 텍스트 배치를 제어하는 열거형에 접근할 수 있습니다.

## 단계별 가이드

### 단계 1: 디렉터리 경로 정의

파일을 읽고 쓸 위치를 지정합니다. 플레이스홀더를 실제 경로로 교체하세요.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

### 단계 2: BarcodeGenerator 인스턴스 생성

`BarcodeGenerator`를 **Data Matrix** 유형으로 인스턴스화하고 인코딩하려는 코드 텍스트를 제공합니다.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DATA_MATRIX,
        "GTIN:898978777776665655 " + "UID: 121212121212121212 " + "Batch:GH768 " + "Exp.Date:150923");
```

### 단계 3: 바코드 텍스트 위치 설정 방법

인간이 읽을 수 있는 텍스트를 이동하려면 `CodeLocation` 열거형을 사용합니다. 이 예제에서는 바코드 **위에** 배치합니다.

```java
generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.ABOVE);
```

### 단계 4: 생성된 바코드 이미지 저장

마지막으로 바코드 이미지를 디스크에 저장합니다. 파일에는 텍스트가 위에 배치된 Data Matrix 심볼이 포함됩니다.

```java
generator.save(dataDir + "codetextAbove.png");
```

## 일반적인 문제 및 해결책

- **텍스트가 표시되지 않음:** `CodeLocation`을 지원하는 Aspose.BarCode 버전을 사용하고 있는지 확인하세요.  
- **파일 경로 오류:** `dataDir`이 OS에 맞는 파일 구분자(`/` 또는 `\\`)로 끝나는지 확인하세요.  
- **지원되지 않는 문자:** Data Matrix는 제한된 문자 집합만 인코딩할 수 있으므로 ISO/IEC 16022 표준에 포함되지 않은 특수 기호는 피하세요.

## 자주 묻는 질문 (FAQ)

### Q: 생성된 바코드의 모양을 사용자 정의할 수 있나요?
A: 예, Aspose.BarCode는 색상, 여백 및 글꼴 스타일을 제어할 수 있는 광범위한 사용자 정의 옵션을 제공합니다.

### Q: Aspose.BarCode가 Java 8 및 이후 버전과 호환되나요?
A: 물론입니다, 이 라이브러리는 Java 8 및 이후 모든 릴리스와 호환됩니다.

### Q: 기존 Java 프로젝트에 Aspose.BarCode를 어떻게 통합할 수 있나요?
A: Aspose.BarCode JAR 파일을 프로젝트의 클래스패스에 추가하고, 필요한 패키지를 import하면 바코드 생성 준비가 완료됩니다.

### Q: Aspose.BarCode의 체험판이 있나요?
A: 예, 무료 체험판을 [here](https://releases.aspose.com/)에서 받아 Aspose.BarCode의 기능을 살펴볼 수 있습니다.

### Q: Aspose.BarCode에 대한 도움이나 지원을 어디서 받을 수 있나요?
A: 커뮤니티 지원 및 공식 지원을 위해 [Aspose.BarCode 포럼](https://forum.aspose.com/c/barcode/13)을 방문하세요.

## 추가 자주 묻는 질문

**Q: 텍스트를 심볼 아래에 배치한 바코드를 생성할 수 있나요?**  
A: 예, 동일한 `setLocation` 메서드에서 `CodeLocation.BELOW`를 설정하면 됩니다.

**Q: 라이브러리가 QR Code와 같은 다른 2‑D 바코드를 지원하나요?**  
A: 물론입니다, `EncodeTypes.DATA_MATRIX`를 `EncodeTypes.QR`로 변경하면 됩니다.

**Q: 바코드 텍스트의 글꼴 크기를 어떻게 변경하나요?**  
A: `generator.getParameters().getBarcode().getCodeTextParameters().setFontSize(double size)`를 사용하세요.

## 결론

이제 Java에서 **Data Matrix 바코드**를 생성하고 Aspose.BarCode를 사용해 **바코드 텍스트 위치**를 정확히 제어하는 방법을 배웠습니다. 다른 `CodeLocation` 값과 스타일 옵션을 실험하여 애플리케이션 디자인 요구사항에 맞추세요.

---

**Last Updated:** 2025-12-27  
**Tested With:** Aspose.BarCode for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
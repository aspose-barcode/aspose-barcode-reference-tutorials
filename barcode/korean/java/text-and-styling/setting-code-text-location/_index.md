---
date: 2026-05-04
description: Java 바코드 라이브러리를 사용해 데이터 매트릭스 바코드를 생성하고 Aspose.BarCode로 바코드 텍스트 위치를 심볼
  위에 설정하는 방법을 배워보세요. 단계별 바코드 생성 예제를 따라해 보세요.
keywords:
- java barcode library
- barcode generation example
- barcode text above
- customize barcode text
linktitle: 코드 텍스트 위치 설정
second_title: Aspose.BarCode Java API
title: Java 바코드 라이브러리로 데이터 매트릭스 바코드 생성 및 코드 텍스트 위치 설정
url: /ko/java/text-and-styling/setting-code-text-location/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java 바코드 라이브러리로 데이터 매트릭스 바코드 생성 및 코드 텍스트 위치 설정

## 소개

Java에서 재고, 배송 또는 추적 시스템을 구축하고 있다면 신뢰할 수 있는 **java barcode library**가 필수라는 것을 곧 알게 될 것입니다. **Aspose.BarCode for Java**를 사용하면 몇 줄의 코드만으로 **Data Matrix barcode**를 생성하고, 인간이 읽을 수 있는 텍스트가 나타나는 위치를 포함한 시각적 레이아웃을 완벽하게 제어할 수 있습니다. 이 튜토리얼에서는 완전한 **barcode generation example**를 단계별로 살펴보고, **barcode text** 배치를 **customize**하는 방법을 보여주며, 텍스트를 심볼 위에 배치하면 사용성이 어떻게 향상되는지 설명합니다.

## 빠른 답변
- **사용된 라이브러리는?** Aspose.BarCode for Java  
- **시연된 바코드 유형은?** Data Matrix  
- **코드 텍스트를 어떻게 위치시키나요?** `CodeLocation.ABOVE` 사용 (또는 `BELOW` 사용 가능)  
- **프로덕션에 라이선스가 필요합니까?** 예, 상업용 라이선스가 필요합니다  
- **코드가 Java 8+에서 실행될 수 있나요?** 물론입니다, Java 8 및 이후 버전을 지원합니다  

## Java 바코드 라이브러리란?
**java barcode library**는 개발자가 Java 애플리케이션에서 직접 1‑D 및 2‑D 바코드를 생성, 읽기 및 스타일링할 수 있도록 준비된 API를 제공합니다. 복잡한 인코딩 규칙을 추상화하여 저수준 이미지 처리 대신 비즈니스 로직에 집중할 수 있게 해줍니다.

## 바코드 생성 예제에 Java 바코드 라이브러리를 사용하는 이유는?
- **속도:** 밀리초 단위로 고품질 바코드를 생성합니다.  
- **신뢰성:** ISO/IEC 표준을 내장하고 있습니다.  
- **유연성:** 크기, 색상, 여백 및 **barcode text** 배치에 대한 완전한 제어가 가능합니다.  
- **크로스‑플랫폼:** 데스크톱 앱부터 클라우드 서비스까지 모든 JVM 기반 환경에서 작동합니다.

## Data Matrix 바코드란?
Data Matrix 바코드는 2‑차원(2‑D) 심볼로, 작은 정사각형 또는 직사각형 패턴에 대량의 데이터를 저장합니다. 소형 부품, 전자 제품 및 의료 기기 등에 널리 사용되며 최대 2,335개의 영숫자를 인코딩할 수 있습니다.

## 바코드 텍스트 위치를 설정하는 이유는?
인간이 읽을 수 있는 텍스트를 **위에**, **아래에** 또는 **옆에** 배치하면 사용자가 스캔 없이도 인코딩된 데이터를 빠르게 확인할 수 있습니다. 텍스트 위치를 조정하면 UI 일관성을 높이고, 브랜드 가이드라인을 충족하며, 수동 데이터 입력 오류를 줄일 수 있습니다.

## 전제 조건

- Java 프로그래밍에 대한 기본 지식.  
- Java Development Kit (JDK) 설치.  
- Eclipse 또는 IntelliJ IDEA와 같은 IDE.  
- Aspose.BarCode for Java 라이브러리 ( [here](https://releases.aspose.com/barcode/java/) 에서 다운로드).  

## 패키지 가져오기

먼저 프로젝트에 필수 Aspose.BarCode 클래스를 가져옵니다:

```java
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.generation.BarcodeGenerator;
```

이 가져오기를 통해 바코드 생성기와 텍스트 위치를 제어하는 열거형에 접근할 수 있습니다.

## 단계별 가이드

### 1단계: 디렉터리 경로 정의
파일을 읽고 쓸 위치를 지정합니다. 자리표시자를 실제 경로로 교체하세요.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

### 2단계: BarcodeGenerator 인스턴스 생성
**Data Matrix** 유형과 인코딩할 코드 텍스트를 제공하여 `BarcodeGenerator`를 인스턴스화합니다.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DATA_MATRIX,
        "GTIN:898978777776665655 " + "UID: 121212121212121212 " + "Batch:GH768 " + "Exp.Date:150923");
```

### 3단계: 바코드 텍스트 위치 설정 (바코드 텍스트 사용자 정의)
`CodeLocation` 열거형을 사용해 인간이 읽을 수 있는 텍스트를 이동합니다. 이 예제에서는 텍스트를 **위에** 배치합니다.

```java
generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.ABOVE);
```

> **프로 팁:** 텍스트를 **아래**에 배치하려면 `CodeLocation.ABOVE`를 `CodeLocation.BELOW`로 변경하면 됩니다.

### 4단계: 생성된 바코드 이미지 저장
마지막으로 바코드 이미지를 디스크에 저장합니다. 파일에는 텍스트가 위에 배치된 Data Matrix 심볼이 포함됩니다.

```java
generator.save(dataDir + "codetextAbove.png");
```

## 일반적인 문제 및 해결책
- **텍스트가 표시되지 않음:** `CodeLocation`을 지원하는 Aspose.BarCode 버전을 사용하고 있는지 확인하세요.  
- **파일 경로 오류:** `dataDir`이 OS에 맞는 파일 구분자(`/` 또는 `\\`)로 끝나는지 확인하세요.  
- **지원되지 않는 문자:** Data Matrix는 제한된 문자 집합만 인코딩할 수 있으니 ISO/IEC 16022 표준에 포함되지 않은 특수 기호는 피하세요.  

## 자주 묻는 질문 (FAQ)

### Q: 생성된 바코드의 모양을 사용자 정의할 수 있나요?
A: 예, Aspose.BarCode는 색상, 여백 및 글꼴 스타일을 제어할 수 있는 광범위한 사용자 정의 옵션을 제공합니다.

### Q: Aspose.BarCode는 Java 8 및 이후 버전과 호환되나요?
A: 네, 이 라이브러리는 Java 8 및 이후 모든 릴리스와 호환됩니다.

### Q: 기존 Java 프로젝트에 Aspose.BarCode를 어떻게 통합할 수 있나요?
A: Aspose.BarCode JAR 파일을 프로젝트 클래스패스에 추가하고, 필요한 패키지를 가져오면 바코드 생성 준비가 완료됩니다.

### Q: Aspose.BarCode의 체험판이 있나요?
A: 예, 무료 체험판을 [here](https://releases.aspose.com/)에서 받을 수 있습니다.

### Q: Aspose.BarCode에 대한 도움이나 지원을 어디서 받을 수 있나요?
A: 커뮤니티 지원 및 공식 지원을 위해 [Aspose.BarCode 포럼](https://forum.aspose.com/c/barcode/13)을 방문하세요.

## 추가 자주 묻는 질문

**Q: 바코드 텍스트를 심볼 아래에 배치하여 바코드를 생성할 수 있나요?**  
A: 예, 동일한 `setLocation` 메서드에서 `CodeLocation.BELOW`를 설정하면 됩니다.

**Q: 라이브러리가 QR 코드와 같은 다른 2‑D 바코드를 지원하나요?**  
A: 네, `EncodeTypes.DATA_MATRIX`를 `EncodeTypes.QR`로 변경하면 됩니다.

**Q: 바코드 텍스트의 글꼴 크기를 어떻게 변경하나요?**  
A: `generator.getParameters().getBarcode().getCodeTextParameters().setFontSize(double size)`를 사용하세요.

## 결론

이제 **java barcode library**를 사용해 Java에서 **Data Matrix barcode**를 **생성**하고, Aspose.BarCode를 통해 **barcode text** 위치를 정확히 **설정**하는 방법을 배웠습니다. 다른 `CodeLocation` 값, 글꼴 설정 및 색상 옵션을 실험하여 애플리케이션 디자인 요구사항에 맞게 조정해 보세요.

---

**Last Updated:** 2026-05-04  
**Tested With:** Aspose.BarCode for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
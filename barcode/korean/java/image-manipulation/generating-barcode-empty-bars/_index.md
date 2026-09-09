---
date: 2026-04-12
description: Aspose.BarCode를 사용하여 Java에서 빈 바가 있는 Code128 바코드를 만드는 방법을 배웁니다. 이 가이드는
  Java 바코드 이미지를 빠르게 생성하는 방법을 보여줍니다.
keywords:
- create code128 barcode
- generate barcode java
- barcode generator java example
- java generate barcode image
linktitle: 빈 바가 있는 바코드 생성
second_title: Aspose.BarCode Java API
title: Java로 빈 바가 포함된 Code128 바코드 만드는 방법
url: /ko/java/image-manipulation/generating-barcode-empty-bars/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java에서 빈 바가 있는 Code128 바코드 생성 방법

## 소개

## 빠른 답변
- **어떤 라이브러리?** Aspose.BarCode for Java  
- **주요 사용 사례?** Custom UI 디자인을 위한 빈 바가 있는 Code128 바코드 생성  
- **전제 조건?** Java JDK 8+, Aspose.BarCode JAR, 출력 이미지 저장을 위한 폴더 쓰기 권한  
- **예상 구현 시간?** 기본 예제에 5‑10 분  
- **색상을 사용자 정의할 수 있나요?** 예 – API가 광범위한 스타일 옵션을 제공합니다  

## Code128 바코드란?

Code128은 전체 ASCII 문자 집합을 인코딩하는 고밀도 선형 바코드 심볼입니다. 물류, 배송, 소매 분야에서 알파벳·숫자 데이터를 압축적으로 표현할 수 있어 널리 사용됩니다. 기본적으로 Aspose.BarCode는 Code128 바를 실선 사각형으로 렌더링하지만, **FilledBars** 속성을 `false`로 설정하면 빈(윤곽선) 바가 되어 스타일링 브랜딩에 유용합니다.

## Java용 Aspose.BarCode를 사용하는 이유

- **풍부한 기능 세트** – QR, DataMatrix, PDF417 등을 포함한 50가지 이상의 바코드 유형을 지원합니다.  
- **외부 종속성 없음** – 단일 JAR 파일만 있으면 모든 Java 런타임에서 작동합니다.  
- **세밀한 제어** – 바 너비, 색상, 글꼴 및 `FilledBars` 속성을 조정할 수 있습니다.  
- **크로스 플랫폼** – Windows, Linux, macOS에서 네이티브 라이브러리 없이 작동합니다.  

## 전제 조건

Before you start, make sure you have:

1. **Java 개발 환경** – JDK 8 이상이 설치되고 `JAVA_HOME`이 설정되어 있어야 합니다.  
2. **Aspose.BarCode for Java** – 최신 JAR 파일을 [download page](https://releases.aspose.com/barcode/java/)에서 다운로드합니다.  
3. **문서 디렉터리** – 생성된 바코드 이미지가 저장될 컴퓨터상의 폴더입니다.  

## 패키지 가져오기

Java 프로젝트에서 Aspose.BarCode와 작업하기 위해 필요한 클래스를 가져옵니다:

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## 단계 1: 리소스 디렉터리 설정

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

`"Your Document Directory"`를 전제 조건에서 만든 폴더의 절대 경로로 교체합니다. 이 위치에 PNG 파일이 기록됩니다.

## 단계 2: Code128 바코드 생성기 인스턴스 만들기

```java
// Create an instance of BarcodeGenerator and initialize it with CodeText and Symbology
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

여기서는 **CODE_128** 심볼리지를 사용하고 샘플 텍스트 `"TEXT"`와 함께 `BarcodeGenerator`를 인스턴스화합니다. 이는 인코딩이 필요한 문자열에 맞게 조정할 수 있는 **barcode generator Java example**입니다.

## 단계 3: FilledBars 속성을 False로 설정

```java
// Set the FilledBars property to false
generator.getParameters().getBarcode().setFilledBars(false);
```

`FilledBars`를 `false`로 설정하면 생성된 바코드가 실선 대신 빈 바를 표시하여 원하는 시각 효과를 얻을 수 있습니다.

## 단계 4: 바코드 이미지 저장

```java
// Save the resultant barcode image on disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

`save` 메서드는 지정된 디렉터리에 PNG 형식으로 바코드를 저장합니다. 다른 이미지 형식이 필요하면 `BarCodeImageFormat.PNG`를 `JPG`, `BMP`, `TIFF` 등으로 변경할 수 있습니다.

## 일반적인 사용 사례

- **맞춤 브랜딩** – 빈 바에 배경 패턴이나 색상을 오버레이할 수 있습니다.  
- **인쇄 준비 자산** – 인보이스나 배송 라벨에 포함할 고해상도 PNG를 생성합니다.  
- **동적 생성** – 웹 서비스나 데스크톱 애플리케이션에서 실시간으로 바코드를 생성합니다.  

## 문제 해결 팁

- **잘못된 경로** – `dataDir`이 파일 구분자(`/` 또는 `\\`)로 끝나는지 확인하거나 `File.separator`를 사용해 연결합니다.  
- **라이선스 필요** – 평가용 트라이얼은 사용할 수 있지만, 프로덕션에서는 정식 라이선스가 필요합니다.  
- **지원되지 않는 문자** – Code128은 전체 ASCII 세트를 지원하므로, 다른 심볼리티로 전환하지 않는 한 유니코드 문자는 사용하지 마세요.  

## 결론

이제 Aspose.BarCode for Java를 사용하여 빈 바가 있는 **Code128 barcode** 이미지를 만드는 방법을 배웠습니다. 이 간단한 방법을 통해 데스크톱 재고 도구든 클라우드 기반 API든 빠르게 맞춤형 바코드 그래픽을 생성할 수 있습니다.

## 자주 묻는 질문

### Aspose.BarCode가 모든 Java 개발 환경과 호환되나요?
예, Aspose.BarCode는 Maven, Gradle 및 일반 JAR 프로젝트를 포함한 모든 Java IDE 또는 빌드 시스템과 원활하게 통합되도록 설계되었습니다.

### 생성된 바코드의 외관을 사용자 정의할 수 있나요?
물론입니다! `FilledBars` 외에도 색상, 바 너비, 여백을 수정하고 광범위한 API를 사용해 인간이 읽을 수 있는 텍스트까지 추가할 수 있습니다.

### Aspose.BarCode의 체험판이 제공되나요?
예, 무료 체험판을 [here](https://releases.aspose.com/)에서 받아 Aspose.BarCode의 기능을 살펴볼 수 있습니다.

### Aspose.BarCode 지원을 어떻게 받을 수 있나요?
문의 사항이나 도움이 필요하면 [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) 를 방문하세요.

### Aspose.BarCode에 대한 자세한 문서는 어디서 찾을 수 있나요?
포괄적인 문서는 [here](https://reference.aspose.com/barcode/java/)에서 확인할 수 있습니다.

**추가 질문**

**Q: JPEG와 같은 다른 형식으로 바코드 이미지를 생성하려면 어떻게 해야 하나요?**  
A: `save`의 두 번째 인수를 `BarCodeImageFormat.JPEG`로 변경합니다.

**Q: 루프에서 여러 바코드를 생성할 수 있나요?**  
A: 예 – 루프 내부에서 새로운 `BarcodeGenerator`를 인스턴스화하거나 동일 인스턴스를 새로운 `CodeText`와 함께 재사용하면 됩니다.

---

**마지막 업데이트:** 2026-04-12  
**테스트 환경:** Aspose.BarCode for Java 24.11  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
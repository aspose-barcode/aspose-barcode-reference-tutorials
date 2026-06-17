---
date: 2026-03-07
description: EAN-2 바코드 생성 방법과 Aspose.BarCode for .NET을 이용한 .NET 바코드 생성 방법을 배우세요. 오늘
  바로 보조 바코드 데이터 맞춤 설정을 마스터하세요!
linktitle: Supplemental Barcode Data
second_title: Aspose.BarCode .NET API
title: Aspose.BarCode for .NET를 사용하여 EAN‑2 바코드 생성
url: /ko/net/supplemental-barcode-data/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.BarCode for .NET으로 EAN-2 바코드 만들기

## 소개

.NET 개발자이면서 **EAN-2 바코드**를 만들고 보조 바코드 데이터의 힘을 활용하고 싶다면, 바로 이곳이 정답입니다. 이 포괄적인 가이드에서는 기본 설정부터 심볼 주변 공간 미세 조정까지 알아야 할 모든 것을 단계별로 안내합니다. 새로운 재고 관리 시스템을 구축하든 기존 POS 애플리케이션을 개선하든, 이 기능을 마스터하면 .NET 프로젝트에서 바코드 생성이 보다 유연하고 신뢰성 있게 됩니다.

## 빠른 답변
- **무엇을 생성할 수 있나요?** EAN‑2 및 EAN‑5 보조 바코드.  
- **라이선스가 필요합니까?** 개발 단계에서는 무료 체험판으로 충분합니다; 운영 환경에서는 상업용 라이선스가 필요합니다.  
- **지원되는 .NET 버전은?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **필요한 코드는 얼마나 되나요?** 몇 줄만 작성하면 됩니다—Aspose.BarCode가 대부분을 처리합니다.  
- **간격을 사용자 정의할 수 있나요?** 네, X‑Dimension과 보조 간격을 직접 제어할 수 있습니다.

## 보조 바코드 데이터란?

보조 바코드 데이터는 기본 바코드 옆에 표시되는 작은 추가 심볼(EAN‑2, EAN‑5)을 말하며, 보통 호수, 가격 확장 또는 기타 보조 정보를 전달하는 데 사용됩니다. Aspose.BarCode for .NET을 사용하면 이러한 심볼을 프로그래밍 방식으로 생성할 수 있어 외관과 배치를 완벽히 제어할 수 있습니다.

## Aspose.BarCode for .NET을 선택해야 하는 이유

- **완전한 .NET 통합** – C#, VB.NET, F#와 모두 호환됩니다.  
- **고품질 렌더링** – 어떤 해상도에서도 스캔 가능한 바코드를 생성합니다.  
- **광범위한 커스터마이징** – 심볼 유형부터 X‑Dimension, Quiet Zone, 보조 간격까지 모두 설정 가능.  
- **외부 종속성 없음** – 순수 관리형 라이브러리로 배포가 간편합니다.

## 보조 바코드 데이터 구성

먼저 보조 바코드 데이터 구성의 세계로 들어가 보겠습니다. Aspose.BarCode for .NET은 EAN‑2와 EAN‑5 보조 바코드를 손쉽게 생성할 수 있는 도구를 제공하며, 완전한 제어권을 부여합니다. 어떻게 시작하나요?

먼저 Aspose.BarCode for .NET을 다운로드하고 설치합니다. 무료 체험판으로 기능을 직접 확인해 볼 수 있습니다. 설치가 완료되면 단계별 가이드를 따라 보조 바코드 데이터 구성을 손쉽게 마스터하세요.

이 섹션을 마치면 EAN‑2와 EAN‑5 바코드를 만드는 방법을 확실히 이해하게 되어, 보다 다재다능한 .NET 개발자가 될 수 있습니다.

## EAN-2 바코드 생성 방법 (구성 단계)

1. **바코드 생성기 인스턴스화** – `BarcodeGenerator` 클래스를 선택하고 심볼 유형을 `EncodeTypes.EAN13`(또는 다른 기본 유형)으로 설정합니다.  
2. **보조 부분 활성화** – `SupplementData` 속성을 원하는 숫자 문자열(예: EAN‑2 보조용 `"12"`)로 지정합니다.  
3. **시각 설정 조정** – 필요에 따라 `XDimension`, `BarHeight`, `QuietZone`을 레이아웃 요구에 맞게 수정합니다.  
4. **저장 또는 렌더링** – `Save` 메서드를 호출해 이미지 파일이나 스트림에 기록합니다.

> *전문가 팁:* EAN‑2는 정확히 2자리, EAN‑5는 정확히 5자리의 보조 데이터를 사용해야 바코드가 정상적으로 읽힙니다.

## 보조 바코드 간격 사용자 정의

바코드 세계에서 커스터마이징은 핵심이며, Aspose.BarCode for .NET은 이 부분에서 뛰어납니다. 이제 보조 바코드 간격 사용자 정의에 집중해 보겠습니다. 이 영역은 바코드의 X‑Dimension과 보조 간격을 제어하는 작업입니다.

다시 한 번 Aspose.BarCode for .NET을 설치하고 무료 체험판을 활용하세요. 이후 안내에 따라 바코드 간격을 조정하는 방법을 따라 하면 됩니다. 이 커스터마이징은 재고 관리부터 POS 시스템까지 다양한 적용 사례에 매우 유용합니다.

특정 요구에 맞게 바코드를 맞춤 설정하는 능력은 귀중한 스킬이며, 이 섹션을 통해 충분히 준비될 것입니다.

## 보조 간격을 어떻게 커스터마이징하나요?

- **X‑Dimension** – 하나의 모듈 폭을 정의합니다; 값이 클수록 전체 바코드 크기가 커집니다.  
- **Supplement Space** – 기본 바코드와 보조 부분 사이의 간격; `SupplementSpace` 속성을 통해 조정합니다.  
- **Quiet Zone** – 바코드 전체 주변에 반드시 확보해야 하는 빈 여백; 안정적인 스캔을 위해 최소 10 X‑Dimension 단위로 유지합니다.

테스트 프로젝트에서 이러한 설정을 실험해 보면서 스캐너 하드웨어에 맞는 시각적 균형을 찾으세요.

## 일반적인 사용 사례

| 시나리오 | 보조 데이터가 도움이 되는 이유 |
|----------|------------------------------|
| **소매 가격 확장** | EAN‑5는 라벨에 직접 가격 정보를 인코딩할 수 있습니다. |
| **잡지 호수 표시** | EAN‑2는 호수를 식별해 빠른 정렬을 가능하게 합니다. |
| **물류 및 추적** | 기본 바코드에 작은 보조를 추가하면 라벨 크기를 늘리지 않고도 라우팅 정보를 제공할 수 있습니다. |

## 보조 바코드 데이터 튜토리얼
### [보조 바코드 데이터 구성](./supplemental-barcode-data-configuration/)
Aspose.BarCode for .NET으로 보조 바코드 데이터를 생성합니다. EAN-2와 EAN-5 바코드를 손쉽게 커스터마이징하세요. .NET 개발자를 위한 단계별 가이드.
### [보조 바코드 간격 커스터마이징](./supplemental-barcode-space-customization/)
Aspose.BarCode for .NET으로 바코드를 쉽게 커스터마이징합니다. X‑Dimension과 보조 간격을 제어하세요. 무료 체험판을 사용해 보세요!

## 자주 묻는 질문

**Q: 동일한 코드로 EAN‑2와 EAN‑5를 모두 생성할 수 있나요?**  
A: 네. `SupplementData` 길이만(2자리면 EAN‑2, 5자리면 EAN‑5) 바꾸면 라이브러리가 자동으로 올바른 심볼을 렌더링합니다.

**Q: 보조 부분에 대한 체크섬을 직접 계산해야 하나요?**  
A: 아닙니다. Aspose.BarCode가 필요한 체크섬을 자동으로 계산하고 추가합니다.

**Q: 루프 안에서 바코드를 대량 생성하는 데 제한이 있나요?**  
A: 라이브러리는 대량 생성에 최적화되어 있습니다; 다만 매우 큰 이미지 컬렉션을 다룰 때 메모리 사용량에 유의하세요.

**Q: 바코드를 PDF나 Word 문서에 삽입하려면 어떻게 해야 하나요?**  
A: 바코드를 이미지(PNG, JPEG 등)로 저장한 뒤, 선호하는 문서 생성 API(e.g., Aspose.PDF 또는 Aspose.Words)를 사용해 삽입하면 됩니다.

**Q: 스캐너가 보조 부분을 읽지 못하면 어떻게 해야 하나요?**  
A: `SupplementSpace`가 최소 2 X‑Dimension 단위인지, Quiet Zone이 스캐너 사양을 충족하는지 확인하세요.

---

**마지막 업데이트:** 2026-03-07  
**테스트 환경:** Aspose.BarCode for .NET 24.12  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
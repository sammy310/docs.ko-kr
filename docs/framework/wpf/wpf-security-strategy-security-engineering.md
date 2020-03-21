---
title: 보안 전략 및 엔지니어링
ms.date: 03/30/2017
helpviewer_keywords:
- security [WPF], testing techniques
- Security Development Lifecycle (SDL), security analysis [WPF]
- Security Development Lifecycle (SDL), threat modeling
- Security Development Lifecycle (SDL), testing techniques
- Security Development Lifecycle (SDL), source analysis tools
- Security Development Lifecycle (SDL), critical code management
- threat modeling [WPF]
ms.assetid: 0fc04394-4e47-49ca-b0cf-8cd1161d95b9
ms.openlocfilehash: 970627c5de4964ebd5331c488152022fda55bd74
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174565"
---
# <a name="wpf-security-strategy---security-engineering"></a>WPF 보안 전략 - 보안 엔지니어링
신뢰할 수 있는 컴퓨팅은 보안 코드 생성을 보장하기 위한 Microsoft 이니셔티브입니다. 신뢰할 수 있는 컴퓨팅 이니셔티브의 핵심 요소는 Microsoft 보안 개발 수명 주기(SDL)입니다. SDL은 보안 코드 의 전달을 용이하게하기 위해 표준 엔지니어링 프로세스와 함께 사용되는 엔지니어링 관행입니다. SDL은 모범 사례와 형식화, 측정 가능성 및 다음과 같은 추가 구조를 결합하는 10단계로 구성됩니다.  
  
- 보안 디자인 분석  
  
- 도구 기반 품질 검사  
  
- 침투 테스트  
  
- 최종 보안 검토  
  
- 릴리스 후 제품 보안 관리  
  
## <a name="wpf-specifics"></a>WPF 고유 정보  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 엔지니어링 팀은 SDL을 적용하고 확장하며, 이 조합은 다음과 같은 주요 측면을 포함합니다.  
  
 [위협 모델링](#threat_modeling)  
  
 [보안 분석 및 편집 도구](#tools)  
  
 [테스트 기술](#techniques)  
  
 [중요한 코드 관리](#critical_code)  
  
<a name="threat_modeling"></a>
### <a name="threat-modeling"></a>위협 모델링  
 위협 모델링은 SDL의 핵심 구성 요소이며 잠재적인 보안 취약점을 확인하기 위해 시스템을 프로파일링하는 데 사용됩니다. 취약상이 식별되면 위협 모델링은 적절한 완화가 적용되었는지도 확인합니다.  
  
 높은 수준에서 위협 모델링은 식품점을 예로 들어 다음과 같은 주요 단계를 포함합니다.  
  
1. **자산 식별** 식품점의 자산에는 직원, 금고, 현금 등록기 및 재고가 포함될 수 있습니다.  
  
2. **진입점 열거** 식품점의 진입점에는 앞문과 뒷문, 창, 하역장 및 에어컨 장치가 포함될 수 있습니다.  
  
3. **진입점을 통한 자산 공격 조사** 한 가지 가능한 공격은 *에어컨* 진입점을 통해 식품점의 *금고* 자산을 대상으로 할 수 있습니다. 에어컨 장치의 나사를 풀어 금고를 상점 외부로 끌고 나갈 수 있습니다.  
  
 위협 모델링은 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 전체에 적용되며 다음을 포함합니다.  
  
- [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 파서가 파일을 읽고, 텍스트를 해당 개체 모델 클래스에 매핑하고, 실제 코드를 만드는 방법  
  
- 창 핸들(hWnd)이 만들어지고, 메시지를 보내고, 창의 내용을 렌더링하는 데 사용되는 방법  
  
- 데이터 바인딩이 리소스를 가져오고 시스템과 상호 작용하는 방법  
  
 이러한 위협 모델은 개발 프로세스 중 보안 디자인 요구 사항과 위협 완화를 식별하는 데 중요합니다.  
  
<a name="tools"></a>
### <a name="source-analysis-and-editing-tools"></a>소스 분석 및 편집 도구  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 팀은 SDL의 수동 보안 코드 검토 요소 외에도 소스 분석 및 관련 편집을 위해 여러 도구를 사용하여 보안 취약점을 줄입니다. 다음을 포함하여 다양한 소스 도구가 사용됩니다.  
  
- **FXCop**: 상속 규칙에서 코드 액세스 보안 사용 및 비관리 코드와 안전하게 상호 운용하는 방법에 이르기까지 관리 코드에서 일반적인 보안 문제를 찾습니다. [FXCop](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/bb429476%28v=vs.80%29)을 참조하세요.  
  
- **Prefix/Prefast**: 비관리 코드에서 버퍼 오버런, 형식 문자열 문제 및 오류 검사와 같은 보안 취약성 및 일반적인 보안 문제를 찾습니다.  
  
- **금지된 API**: 소스 코드를 검색하여 `strcpy`와 같이 보안 문제가 발생하는 것으로 잘 알려진 함수가 실수로 사용되었는지 식별합니다. 식별되면 이러한 함수는 보다 안전한 대안으로 대체됩니다.  
  
<a name="techniques"></a>
### <a name="testing-techniques"></a>테스트 기술  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]는 다음을 포함하는 다양한 보안 테스트 기술을 사용합니다.  
  
- **화이트박스 테스트**: 테스터는 소스 코드를 보고 익스플로잇 테스트를 빌드합니다.
  
- **Blackbox 테스트**: 테스터가 API 및 기능을 검사하여 보안 익스플로이트를 찾은 다음 제품을 공격하려고 합니다.  
  
- **다른 제품의 보안 문제 재발**: 해당하는 경우 관련 제품의 보안 문제를 테스트합니다. 예를 들어, Internet Explorer에 대한 약 60개의 보안 문제의 적절한 변형이 식별되어 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]에 적용 가능하도록 시도되었습니다.  
  
- **파일 퍼지 테스트를 통한 도구 기반 침투 테스트**: 파일 퍼지 테스트는 다양한 입력을 통해 파일 판독기의 입력 범위를 악용합니다. [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]에서 이 기술이 사용되는 한 가지 예는 이미지 디코딩 코드 오류 검사입니다.  
  
<a name="critical_code"></a>
### <a name="critical-code-management"></a>중요한 코드 관리  
 XAML 브라우저 응용 프로그램(XBAPs)의 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 경우 권한을 높이는 보안에 중요한 코드를 표시하고 추적하기 위한 .NET Framework 지원을 사용하여 보안 샌드박스를 빌드합니다(WPF 보안 전략 - 플랫폼 [보안의](wpf-security-strategy-platform-security.md)보안 에 중요한 **방법론** 참조). 보안에 중요한 코드의 높은 보안 품질 요구 사항을 감안하여 이러한 코드는 추가 수준의 소스 관리 제어 및 보안 감사를 받습니다. [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]의 약 5%-10%는 전담 검토팀이 검토하는 보안에 중요한 코드로 구성됩니다. 소스 코드 및 체크 인 프로세스는 보안에 중요한 코드를 추적하고 중요한 엔터티(예: 중요한 코드가 포함된 메서드)를 사인오프 상태로 매핑하여 관리합니다. 사인오프 상태에는 하나 이상의 검토자 이름이 포함됩니다. [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]의 각 일별 빌드는 중요한 코드를 이전 빌드의 코드와 비교하여 승인되지 않은 변경 내용을 확인합니다. 엔지니어가 검토팀의 승인 없이 중요한 코드를 수정하는 경우 식별되어 즉시 수정됩니다. 이 프로세스를 통해 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 샌드박스 코드에 특히 높은 수준의 감시를 적용하고 유지할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목

- [보안](security-wpf.md)
- [WPF 부분 신뢰 보안](wpf-partial-trust-security.md)
- [WPF 보안 전략 - 플랫폼 보안](wpf-security-strategy-platform-security.md)
- [신뢰할 수 있는 컴퓨팅](https://www.microsoft.com/mscorp/twc/default.mspx)
- [.NET의 보안](../../standard/security/index.md)

---
title: .NET으로 라이브러리 포팅
description: .NET Framework에서 .NET으로 라이브러리 프로젝트를 포팅하는 방법을 알아봅니다.
author: cartermp
ms.date: 03/04/2021
ms.openlocfilehash: 5fe7b57e583f74c12649746cd9968fde03b94435
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604946"
---
# <a name="port-net-framework-libraries-to-net"></a>.NET으로 .NET Framework 라이브러리 포팅

.NET Framework 라이브러리 코드를 .NET으로 포팅하고, 플랫폼 간에 실행하고, 코드를 사용하는 앱의 도달 범위를 확장하는 방법을 알아봅니다.

## <a name="prerequisites"></a>사전 요구 사항

이 문서에서는 다음을 전제로 합니다.

- Visual Studio 2019 이상을 사용하고 있나요?
  - .NET 5에는 Visual Studio 2019(v16.9) 이상이 필요합니다.
  - .NET Core 3.1에는 Visual Studio 2019(v16.4) 이상이 필요합니다.
- 사용자가 [권장 이식 프로세스](index.md)를 이해합니다.
- 사용자가 [타사 종속성](third-party-deps.md)과 관련된 문제를 모두 해결했습니다.

다음 문서의 내용을 숙지하세요.

- [.NET Standard.](../../standard/net-standard.md)\
이 문서에서는 모든 .NET 구현에서 사용할 수 있는 .NET API의 공식 사양에 관해 설명합니다.

- [.NET CLI를 사용하여 라이브러리를 개발합니다.](../tutorials/libraries.md)\
이 문서에서는 .NET CLI를 사용하여 라이브러리를 작성하는 방법에 대해 설명합니다.

- [.NET 프로젝트 SDK.](../project-sdk/overview.md)\
이 문서에서는 SDK 스타일 프로젝트 파일 형식을 설명합니다.

- [.NET Framework에서 .NET으로 코드를 포팅하기 위한 종속성을 분석합니다.](third-party-deps.md)\
이 문서에서는 타사 종속성의 이식성 및 .NET에서 NuGet 패키지 종속성이 실행되지 않는 경우 수행해야 할 작업에 관해 설명합니다.

## <a name="retarget-to-net-framework-472"></a>.NET Framework 4.7.2로 대상 변경

코드가 .NET Framework 4.7.2를 대상으로 하지 않는 경우 .NET Framework 4.7.2로 대상을 다시 지정하는 것이 좋습니다. 그러면 .NET Standard에서 기존 API를 지원하지 않는 경우 최신 API를 대신 사용할 수 있습니다.

이식하려는 각 프로젝트에 대해 Visual Studio에서 다음을 수행합니다.

01. 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성** 을 선택합니다.
01. **대상 프레임워크** 드롭다운에서 **.NET Framework 4.7.2** 를 선택합니다.
01. 프로젝트를 다시 컴파일합니다.

프로젝트가 .NET Framework 4.7.2를 대상으로 하기 때문에 해당 버전의 .NET Framework를 코드 포팅의 기반으로 사용합니다.

## <a name="determine-portability"></a>이식성 확인

다음 단계에서는 API Portability Analyzer(ApiPort)를 실행하여 분석을 위한 이식성 보고서를 생성합니다.

[API 이식성 분석기(ApiPort)](../../standard/analyzers/portability-analyzer.md)와 .NET을 대상으로 하는 이식성 보고서를 생성하는 방법을 이해하고 있는지 확인합니다. 이 작업을 수행하는 방법은 요구 사항 및 개인적 취향에 따라 달라질 수 있습니다. 다음 섹션에서는 몇 가지 다른 방법을 자세히 설명합니다. 코드가 어떻게 구성되어 있는가에 따라 이러한 접근 방식의 단계를 혼합하여 사용할 수 있습니다.

### <a name="deal-primarily-with-the-compiler"></a>주로 컴파일러 처리

이 접근 방식은 작은 프로젝트 또는 많은 .NET Framework API를 사용하지 않는 프로젝트에 적합합니다. 접근 방식은 간단합니다.

01. 필요에 따라 프로젝트에서 ApiPort를 실행합니다. ApiPort를 실행하는 경우 해결해야 할 문제에 대한 보고서에서 정보를 가져오세요.
01. 모든 코드를 새 .NET 프로젝트에 복사합니다.
01. 이식성 보고서(생성된 경우)를 참조하면서 프로젝트가 완전히 컴파일될 때까지 컴파일러 오류를 해결합니다.

구조화되지 않은 경우에도 이 코드 중심 접근 방식은 문제를 빠르게 해결하는 경우가 많습니다. 데이터 모델만 포함하는 프로젝트가 이 접근 방식에 적합한 후보가 될 수 있습니다.

### <a name="stay-on-the-net-framework-until-portability-issues-are-resolved"></a>이식성 문제가 해결될 때까지 .NET Framework 유지

이 접근 방식은 전체 프로세스 중에 컴파일되는 코드를 선호하는 경우 적합할 수 있습니다. 이 접근 방식은 다음과 같습니다.

01. 프로젝트에서 ApiPort를 실행합니다.
01. 이식 가능한 다른 API를 사용하여 문제를 해결합니다.
01. 직접적인 대안을 사용할 수 없는 영역을 기록해 둡니다.
01. 각 프로젝트를 새 .NET 프로젝트에 복사할 준비가 되었다고 확신할 때까지 포팅하려는 모든 프로젝트에 대해 이전 단계를 반복합니다.
01. 새 .NET 프로젝트에 코드를 복사합니다.
01. 직접적인 대안이 없는 것으로 기록해 둔 문제를 해결합니다.

이 신중한 접근 방식은 단순히 컴파일러 오류를 해결하는 것보다는 구조적이지만 비교적 코드 중심적이며 컴파일되는 코드가 항상 있다는 장점이 있습니다. 다른 API를 사용하여 해결할 수 없는 특정 문제를 해결하는 방법은 현저하게 달라집니다. 특정 프로젝트에 대해 보다 포괄적인 계획을 개발해야 할 수 있으며, 이는 다음 접근 방식에서 설명합니다.

### <a name="develop-a-comprehensive-plan-of-attack"></a>포괄적인 공격 계획 개발

이 접근 방식은 .NET을 지원하기 위해 코드를 재구성하거나 코드의 특정 영역을 완전히 다시 작성해야 할 수 있는 더 크고 더 복잡한 프로젝트에 가장 적합할 수 있습니다. 이 접근 방식은 다음과 같습니다.

01. 프로젝트에서 ApiPort를 실행합니다.
01. 이식 불가능한 각 형식이 사용되고 있는 위치 및 해당 형식이 전체 이식성에 어떻게 영향을 주는지를 파악합니다.

    - 해당 형식의 특성을 이해합니다. 수는 적은데 자주 사용되나요? 아니면 수는 많지만 자주 사용되지 않나요? 집중적으로 사용되나요? 아니면 코드 전체에 분산되어 있나요?
    - 이식할 수 없는 코드는 격리가 쉬우므로 더 효과적으로 처리할 수 있나요?
    - 코드를 리팩터링해야 하나요?
    - 이식할 수 없는 해당 형식에 대해 동일한 작업을 수행하는 다른 API가 있나요? 예를 들어 <xref:System.Net.WebClient> 클래스를 사용하고 있는 경우 <xref:System.Net.Http.HttpClient> 클래스를 대신 사용합니다.
    - 드롭인 대체가 아닌 경우에도 작업을 수행하는 데 사용할 수 있는 이식 가능한 다른 API가 있나요? 예를 들어 <xref:System.Xml.Schema.XmlSchema>를 사용하여 XML을 구문 분석하지만 XML 스키마 검색이 필요하지 않은 경우, API를 사용하는 대신 <xref:System.Xml.Linq> API를 사용하고 직접 구문 분석을 구현할 수 있습니다.

01. 이식하기 어려운 어셈블리가 있는 경우 지금은 .NET Framework에 유지하는 것이 나을까요? 다음과 같은 몇 가지 사항을 고려해야 합니다.

    - .NET Framework 또는 Windows 관련 기능을 너무 많이 사용하기 때문에 .NET과 호환되지 않는 일부 기능이 라이브러리에 있을 수 있습니다. 기능 이식을 위해 리소스를 사용할 수 있을 때까지 해당 기능을 유지하고 당분간은 기능이 적은 라이브러리의 임시 .NET 버전을 릴리스하는 것이 더 나을까요?
    - 리팩터링이 도움이 될까요?

01. 사용할 수 없는 .NET Framework API의 고유한 구현을 작성하는 것이 합리적일까요?

    [.NET Framework 참조 소스](https://github.com/Microsoft/referencesource)에서 코드를 복사, 수정 및 사용하는 것이 좋을 수 있습니다. 참조 소스 코드는 [MIT 라이선스](https://github.com/Microsoft/referencesource/blob/master/LICENSE.txt)에 따라 라이선스가 부여되므로, 소스를 자신의 코드에 대한 기초로 매우 자유롭게 사용할 수 있습니다. 코드에서 Microsoft 특성을 제대로 지정하기만 하면 됩니다.

01. 필요에 따라 다른 프로젝트에 대해 이 프로세스를 반복합니다.

분석 단계는 코드베이스의 크기에 따라 다소 시간이 걸릴 수 있습니다. 이 단계에서 시간을 할애하여 필요한 변경의 범위를 철저하게 이해하고 계획을 개발하면 특히 복잡한 코드베이스가 있는 경우 대개 최종적으로 시간이 절약됩니다.

계획에는 .NET Framework 4.7.2를 계속 대상으로 지정하는 동시에 코드베이스를 크게 변경하는 것이 포함될 수 있습니다. 이는 이전 접근 방식의 좀 더 구조화된 버전입니다. 계획 실행을 시작하는 방법은 코드베이스에 따라 달라집니다.

### <a name="mixed-approach"></a>혼합형 접근 방식

위의 접근 방식을 프로젝트 단위로 혼합하여 사용할 수 있습니다. 사용자 및 코드베이스에 가장 적합한 작업을 수행합니다.

## <a name="port-your-tests"></a>테스트 이식

코드를 이식한 경우 모든 항목이 제대로 작동하는지 확인하는 가장 좋은 방법은 .NET에 이식할 때 코드를 테스트하는 것입니다. 이렇게 하려면 .NET에 대한 테스트를 빌드하고 실행하는 테스트 프레임워크를 사용해야 합니다. 현재는 다음과 같은 세 가지 옵션이 있습니다.

- [xUnit](https://xunit.net/)
  - [시작](https://xunit.net/docs/getting-started/netcore/cmdline)
  - [MSTest 프로젝트를 xUnit으로 변환하는 도구](https://github.com/dotnet/codeformatter/tree/master/src/XUnitConverter)
- [NUnit](https://nunit.org/)
  - [시작](https://github.com/nunit/docs/wiki/Installation)
  - [MSTest에서 NUnit으로 마이그레이션에 대한 블로그 게시물](https://www.florian-rappl.de/News/Page/275/convert-mstest-to-nunit)
- [MSTest](/visualstudio/test/unit-test-basics)

## <a name="recommended-approach"></a>권장 접근 방식

궁극적으로 이식 작업은 .NET Framework 코드가 구성된 방법에 따라 크게 달라집니다. 코드를 이식하는 좋은 방법은 코드의 기본 구성 요소인 라이브러리의 *기본* 으로 시작하는 것입니다. 이는 다른 모든 항목에서 직접적으로나 간접적으로 사용하는 데이터 모델이나 일부 다른 기본 클래스 및 메서드가 될 수 있습니다.

01. 현재 이식하고 있는 라이브러리의 계층을 테스트하는 테스트 프로젝트를 이식합니다.
01. 라이브러리의 기본을 새 .NET 프로젝트에 복사하고 지원하려는 .NET Standard의 버전을 선택합니다.
01. 코드를 컴파일하는 데 필요한 대로 내용을 변경합니다. 이 작업의 많은 부분에서 NuGet 패키지 종속성을 *csproj* 파일에 추가해야 할 수 있습니다.
01. 테스트를 실행하고 필요에 따라 조정합니다.
01. 이식할 다음 코드 계층을 선택하고 이전 단계를 반복합니다.

라이브러리의 기본으로 시작하고 기본에서 바깥쪽으로 이동하면서 필요에 따라 각 계층을 테스트하면, 이식은 한 번에 하나의 코드 계층으로 문제가 격리되는 체계적인 프로세스가 됩니다.

## <a name="next-steps"></a>다음 단계

>[!div class="nextstepaction"]
>[.NET에 대한 프로젝트 구성](project-structure.md)

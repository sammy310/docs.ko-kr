---
title: '호환성이 손상되는 변경: 기본 ActivityIdFormat이 W3C임'
description: 기본 ActivityIdFormat이 W3C인 핵심 .NET 라이브러리의 .NET 5 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: f15c2d61443117cfbcb2be7de9561fecbff9a1d9
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257507"
---
# <a name="default-activityidformat-is-w3c"></a>기본 ActivityIdFormat이 W3C임

활동의 기본 식별자 형식(<xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType>)이 이제 <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>입니다.

## <a name="change-description"></a>변경 내용 설명

W3C 활동 ID 형식은 .NET Core 3.0에서 계층 구조 ID 형식의 대안으로 도입되었습니다. 그러나 호환성을 유지하기 위해 W3C 형식은 .NET 5.0까지 기본값으로 지정되지 않았습니다. [W3C 형식이 비준되고](https://www.w3.org/TR/trace-context/) 여러 언어 구현에서 활발하게 추진되어 .NET 5에서 기본값이 변경되었습니다.

앱이 .NET 5 이상이 아닌 플랫폼을 대상으로 하는 경우 <xref:System.Diagnostics.ActivityIdFormat.Hierarchical>이 기본 형식인 이전 동작이 발생합니다. 이 기본값은 net45 이상, netstandard1.1 이상, netcoreapp(1.x, 2.x, 3.x) 플랫폼에 적용됩니다. .NET 5 이상에서는 <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType>이 <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>로 설정되어 있습니다.

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="recommended-action"></a>권장 조치

애플리케이션이 분산 추적에 사용되는 식별자와 관련이 없는 경우 아무 동작도 필요하지 않습니다. ASP.NET Core 및 <xref:System.Net.Http.HttpClient>와 같은 라이브러리는 <xref:System.Diagnostics.ActivityIdFormat>의 두 버전을 모두 사용하거나 전파할 수 있습니다.

기존 시스템과의 상호 운용성이 필요하거나 현재 시스템이 식별자 형식을 사용하는 경우 <xref:System.Diagnostics.Activity.DefaultIdFormat>을 <xref:System.Diagnostics.ActivityIdFormat.Hierarchical?displayProperty=nameWithType>으로 설정하여 이전 동작을 유지할 수 있습니다. 또는 다음 세 가지 방법 중 하나로 AppContext 스위치를 설정할 수 있습니다.

- 프로젝트 파일에서

  ```xml
  <ItemGroup>
    <RuntimeHostConfigurationOption Include="System.Diagnostics.DefaultActivityIdFormatIsHierarchial" Value="true" />
  </ItemGroup>
  ```

- *runtimeconfig.json* 파일에서

  ```json
  {
      "runtimeOptions": {
          "configProperties": {
              "System.Diagnostics.DefaultActivityIdFormatIsHierarchial": true
          }
      }
  }
  ```

- 환경 변수를 통해

  `DOTNET_SYSTEM_DIAGNOSTICS_DEFAULTACTIVITYIDFORMATISHIERARCHIAL`을 `true` 또는 1로 설정합니다.

## <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Diagnostics.Activity.DefaultIdFormat`

-->

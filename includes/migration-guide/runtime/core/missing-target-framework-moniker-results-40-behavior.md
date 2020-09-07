---
ms.openlocfilehash: 49740d3b1890d72935e6e329a4f4be836ed70b25
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497605"
---
### <a name="missing-target-framework-moniker-results-in-40-behavior"></a>누락된 대상 프레임워크 모니커로 인해 4.0 동작 발생

#### <a name="details"></a>설명

어셈블리 수준에 적용된 <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName>이 없는 애플리케이션은 .NET Framework 4.0의 의미 체계(쿼크)를 사용하여 자동으로 실행됩니다. 높은 품질을 보장하려면 모든 바이너리가 빌드될 때 사용된 .NET Framework의 버전을 나타내는 <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName>로 명시적으로 특성을 사용하는 것이 좋습니다. 프로젝트 파일에서 대상 프레임워크 모니커를 사용하면 MSBuild가 <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName>를 자동으로 적용합니다.

#### <a name="suggestion"></a>제안 해결 방법

어셈블리에 직접 특성을 추가하거나 [프로젝트 파일 또는 Visual Studio의 프로젝트 속성 GUI를 통해](https://devblogs.microsoft.com/visualstudio/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework/) 대상 프레임워크를 지정하여 <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName>을 지정해야 합니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |주요함|
|버전|4.5|
|형식|런타임|

#### <a name="affected-apis"></a>영향을 받는 API

API 분석을 통해 검색할 수 없습니다.

<!--

#### Affected APIs

Not detectable via API analysis.

-->

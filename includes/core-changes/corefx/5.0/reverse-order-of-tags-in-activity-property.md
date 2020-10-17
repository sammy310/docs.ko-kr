---
ms.openlocfilehash: 24b88b3ba1b6cfe9fb9fb1f6398a6daeb57596a9
ms.sourcegitcommit: a8a205034eeffc7c3e1bdd6f506a75b0f7099ebf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2020
ms.locfileid: "91756114"
---
### <a name="order-of-tags-in-activitytags-is-reversed"></a>Activity.Tags의 태그 순서가 반대로 표시됨

이제 <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType>이 항목을 추가된 순서대로 목록에 저장합니다. 즉, 첫 번째로 추가된 항목이 목록의 첫 번째 항목이 됩니다. 이 변경 내용은 [OpenTelemetry 특성 사양](https://github.com/open-telemetry/opentelemetry-specification/blob/master/specification/common/common.md#attributes)을 따른 것입니다.

#### <a name="change-description"></a>변경 내용 설명

이전 .NET 버전에서는 <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType>이 항목을 추가된 순서와 반대로 저장합니다. 즉, 첫 번째로 추가된 항목이 목록의 마지막 항목이 됩니다. .NET 5.0부터 항목 순서가 반대로 전환되어 첫 번째로 추가된 항목이 항상 목록의 첫 번째 항목이 됩니다.

#### <a name="version-introduced"></a>도입된 버전

5.0

#### <a name="recommended-action"></a>권장 조치

앱에 <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> 목록 순서에 대한 종속성이 있고 .NET 5.0 이상으로 업그레이드하는 경우 이 코드 부분을 변경해야 합니다.

#### <a name="category"></a>범주

핵심 .NET 라이브러리

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Diagnostics.Activity.Tags?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Diagnostics.Activity.Tags`

-->

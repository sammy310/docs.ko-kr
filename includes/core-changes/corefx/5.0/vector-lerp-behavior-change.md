---
ms.openlocfilehash: 4bc060f991501b81db0cb7c521e55996a2b5e91e
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281309"
---
### <a name="behavior-change-for-vector2lerp-and-vector4lerp"></a>Vector2.Lerp 및 Vector4.Lerp의 동작 변경

<xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> 및 <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> 구현이 부동 소수점 반올림 오차를 올바르게 고려하도록 변경되었습니다.

#### <a name="change-description"></a>변경 내용 설명

이전에는 <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> 및 <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType>이 `value1 + (value2 - value1) * amount`로 구현되었습니다. 그러나 부동 소수점 반올림 오차로 인해 `amount`가 `1.0f`이면 알고리즘에서 `value2`를 반환하지 않는 경우가 있습니다.

.NET 5.0 이상 구현에서는 <xref:System.Numerics.Vector3.Lerp(System.Numerics.Vector3,System.Numerics.Vector3,System.Single)?displayProperty=nameWithType>과 동일한 알고리즘(`(value1 * (1.0f - amount)) + (value2 * amount)`)을 사용합니다. 이 알고리즘은 반올림 오차를 올바르게 고려합니다. 이제 `amount`가 `1.0f`인 경우 결과는 정확하게 `value2`가 됩니다. 업데이트된 알고리즘이 제공되면 <xref:System.MathF.FusedMultiplyAdd%2A?displayProperty=nameWithType>을 사용하여 알고리즘을 자유롭게 최적화할 수도 있습니다.

#### <a name="version-introduced"></a>도입된 버전

5.0 미리 보기 7

#### <a name="recommended-action"></a>권장 조치

별도의 동작이 필요하지 않습니다. 그러나 이전 동작을 유지하려는 경우 이전 알고리즘인 `value1 + (value2 - value1) * amount`를 사용하는 자체 `Lerp` 함수를 구현할 수 있습니다.

#### <a name="category"></a>범주

핵심 .NET 라이브러리

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=fullName>
- <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)`
- `M:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)`

-->

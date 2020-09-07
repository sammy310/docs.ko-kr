---
ms.openlocfilehash: 05f60978f5380c406c43aa98ded0c812b1d50694
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497857"
---
### <a name="enumerableemptylttresultgt-always-returns-cached-instance"></a>Enumerable.Empty&lt;TResult&gt;가 항상 캐시된 인스턴스를 반환

#### <a name="details"></a>설명

.NET Framework 4.5부터 <xref:System.Linq.Enumerable.Empty%60%601>는 항상 캐시된 내부 인스턴스 <xref:System.Collections.Generic.IEnumerable%601>를 반환합니다. 이전에는 <xref:System.Linq.Enumerable.Empty%60%601>이 API를 호출할 때 빈 <xref:System.Collections.Generic.IEnumerable%601>을 캐시했으며, 이 말은 즉 <xref:System.Linq.Enumerable.Empty%60%601>가 신속하게 동시에 호출된 일부 조건에서 다른 형식의 인스턴스가 다른 호출에 대해 API로 반환되었다는 것입니다.

#### <a name="suggestion"></a>제안 해결 방법

이전 동작이 명확하지 않았으므로 코드가 종속될 가능성이 작습니다. 그러나 빈 열거형은 비교되고 때로는 같지 않은 것으로 예상되는 드문 경우에는, <xref:System.Linq.Enumerable.Empty%60%601>를 사용하는 대신 명시적인 빈 배열을 만들어야 합니다(<code>new T[0]</code>).

| 이름    | 값       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|버전|4.5|
|형식|런타임|

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Linq.Enumerable.Empty%60%601?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``M:System.Linq.Enumerable.Empty``1``

-->

---
ms.openlocfilehash: 02a15f6b9c02002b60c568b9e1d871af49744092
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622147"
---
### <a name="concurrentqueuelttgttrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a>ConcurrentQueue&lt;T&gt;.TryPeek는 out 매개 변수를 통해 잘못된 null을 반환할 수 있습니다.

#### <a name="details"></a>설명

일부 다중 스레드 시나리오에서 <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=fullName> true를 반환할 수 있지만 (올바르고 미리 본 값 대신) null 값으로 out 매개 변수를 채웁니다.

#### <a name="suggestion"></a>제안 해결 방법

이 문제는 .NET Framework 4.5.1에서 수정되었습니다. 해당 프레임워크로 업그레이드하면 문제가 해결됩니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |주요함|
|버전|4.5|
|형식|런타임

#### <a name="affected-apis"></a>영향을 받는 API

-<xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType></li></ul>|

---
ms.openlocfilehash: 986b647047aaa4a185c1403e96e499ae587bea98
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617541"
---
### <a name="httpruntimeappdomainapppath-throws-a-nullreferenceexception"></a>HttpRuntime.AppDomainAppPath가 NullReferenceException을 Throw함

#### <a name="details"></a>세부 정보

.NET Framework 4.6.2에서 런타임은 null 문자를 포함하는 `P:System.Web.HttpRuntime.AppDomainAppPath` 값을 검색할 때 `T:System.NullReferenceException`를 throw합니다. .NET Framework 4.6.1 이전 버전에서 런타임은 `T:System.ArgumentNullException`를 throw합니다.

#### <a name="suggestion"></a>제안 해결 방법

이러한 변경에 대처하기 위해 다음 중 하나를 수행할 수 있습니다.

- 애플리케이션이 .NET Framework 4.6.2에서 실행 중인 경우 `T:System.NullReferenceException`를 처리합니다.
- .NET Framework 4.7로 업그레이드하면 이전 동작이 복원되고 `T:System.ArgumentNullException`가 throw됩니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| 버전 | 4.6.2       |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Web.HttpRuntime.AppDomainAppPath?displayProperty=nameWithType>

---
ms.openlocfilehash: 8b70df0fb2072fd5243d9e46a4a20c22cc7fd677
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "91607796"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a>ASP.NET MVC4 앱을 프로파일링하면 심각한 실행 엔진 오류가 발생할 수 있음

#### <a name="details"></a>설명

NGEN /Profile 어셈블리를 사용하는 프로파일러는 프로파일링된 ASP.NET MVC4 애플리케이션을 시작할 때 '심각한 실행 엔진 예외'로 크래시가 발생할 수 있습니다.

#### <a name="suggestion"></a>제안 해결 방법

이 문제는 .NET Framework 4.5.2에서 해결되었습니다. 또는 프로파일러는 이벤트 마스크에 <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code>를 지정하여 이 문제를 방지할 수 있습니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|버전|4.5|
|형식|런타임|

#### <a name="affected-apis"></a>영향을 받는 API

API 분석을 통해 검색할 수 없습니다.

<!--

#### Affected APIs

Not detectable via API analysis.

-->

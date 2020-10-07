---
ms.openlocfilehash: e450c53008e7562e37518fdfd6872ff9b63b6ac3
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609138"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a>ASP.NET StateServer와 세션 상태를 공유하려면 웹 팜의 모든 서버가 동일한 .NET Framework 버전을 사용해야 함

#### <a name="details"></a>설명

<xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName> 세션 상태를 활성화할 때 상태를 올바르게 공유하려면 지정된 웹 팜의 모든 서버가 동일한 .NET Framework 버전을 사용해야 합니다.

#### <a name="suggestion"></a>제안 해결 방법

동시에 상태를 공유하는 웹 서버에서 .NET Framework 버전을 업그레이드해야 합니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|버전|4.5|
|형식|런타임

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType>

<!--

#### Affected APIs

- `F:System.Web.SessionState.SessionStateMode.StateServer`

-->

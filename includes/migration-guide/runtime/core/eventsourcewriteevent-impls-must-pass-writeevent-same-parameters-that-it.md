---
ms.openlocfilehash: 662c140f019add66ff6605d47ad1f32c3f50d711
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620239"
---
### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a>EventSource.WriteEvent impls는 수신된 매개 변수와 동일한 WriteEvent를 전달해야 합니다(추가 ID).

#### <a name="details"></a>설명

이제 런타임에서는 다음을 지정하는 계약이 적용됩니다. ETW 이벤트 메서드를 정의하는 <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>에서 파생된 클래스는 이벤트 ID 다음에 ETW 이벤트 메서드가 전달된 동일한 인수를 사용하여 기본 클래스 <code>EventSource.WriteEvent</code> 메서드를 호출해야 합니다.

#### <a name="suggestion"></a>제안 해결 방법

<xref:System.IndexOutOfRangeException?displayProperty=fullName>가 이 계약을 위반하는 이벤트 소스에 대해 프로세스의 <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> 데이터를 읽는 경우 <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> 예외가 throw됩니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |부|
|버전|4.5.1|
|형식|런타임|

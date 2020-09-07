---
ms.openlocfilehash: e47a24239872e3fe86ff6902f66b38daaa106598
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496562"
---
### <a name="eventlistener-truncates-strings-with-embedded-nulls"></a>EventListener는 포함된 null이 있는 문자열을 자릅니다.

#### <a name="details"></a>설명

<xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName>는 포함된 null이 있는 문자열을 자릅니다. Null 문자는 <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> 클래스에서 지원되지 않습니다. 이 변경 내용은 <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName>를 사용하여 프로세스의 <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> 데이터를 읽고 null 문자를 구분 기호로 사용하는 앱에만 영향을 줍니다.

#### <a name="suggestion"></a>제안 해결 방법

가능하면 포함된 null 문자를 사용하지 않도록 <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> 데이터를 업데이트해야 합니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|버전|4.5.1|
|형식|런타임|

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Diagnostics.Tracing.EventListener.%23ctor>
- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Diagnostics.Tracing.EventListener.#ctor`
- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)`
- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)`
- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})`

-->

---
ms.openlocfilehash: 0e25d5d9b545e5cb400cbf701fb13da572fadf10
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614674"
---
### <a name="etw-event-names-cannot-differ-only-by-a-start-or-stop-suffix"></a>ETW 이벤트 이름은 "Start" 또는 "Stop" 접미사만 다를 수 없음

#### <a name="details"></a>설명

.NET Framework 4.6 및 4.6.1의 경우 두 개의 ETW(Windows용 이벤트 추적) 이벤트 이름이 "Start" 또는 "Stop" 접미사만 다를 때(예: 한 이벤트는 `LogUser`, 다른 이벤트는 `LogUserStart`라고 이름을 지정하는 경우) 런타임에서 <xref:System.ArgumentException>을 throw합니다. 이 경우 런타임에서 로깅을 발생할 수 없는 이벤트 소스를 구성할 수 없습니다.

#### <a name="suggestion"></a>제안 해결 방법

예외를 방지하려면 두 이벤트 이름이 "Start" 또는 "Stop" 접미사만 다르지 않도록 하세요. 이 요구 사항은 .NET Framework 4.6.2부터 제거됩니다. 런타임은 "Start" 및 "Stop" 접미사만 다른 이벤트 이름을 명확하게 할 수 있습니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| 버전 | 4.6         |
| 형식    | 대상 변경 |

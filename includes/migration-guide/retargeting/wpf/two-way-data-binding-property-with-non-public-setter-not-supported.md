---
ms.openlocfilehash: 5f1a8af37a305ab0904801002dd99e17e8eca62e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616124"
---
### <a name="two-way-data-binding-to-a-property-with-a-non-public-setter-is-not-supported"></a>Public이 아닌 setter를 사용하는 속성에 양방향 데이터 바인딩을 지원하지 않음

#### <a name="details"></a>설명

public setter가 없는 속성에 데이터 바인딩을 시도하는 것은 지원된 적이 없는 시나리오였습니다. .NET Framework 4.5.1부터는 이 시나리오가 <xref:System.InvalidOperationException?displayProperty=fullName>을 throw합니다. 이 새로운 예외는 구체적으로 .NET Framework 4.5.1을 대상으로 하는 응용 프로그램만 throw됩니다. 응용 프로그램이 .NET Framework 4.5를 대상으로 하는 경우 호출이 허용됩니다. 응용 프로그램이 특정 .NET Framework 버전을 대상으로 하지 않는 경우 바인딩은 단방향으로 처리됩니다.

#### <a name="suggestion"></a>제안 해결 방법

응용 프로그램은 단방향 바인딩을 사용하거나 속성의 setter를 공개적으로 노출하도록 업데이트되어야 합니다. 또는 .NET Framework 4.5를 대상으로 하면 응용 프로그램이 이전 동작을 실행하게 됩니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   | 부       |
| 버전 | 4.5.1       |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType>

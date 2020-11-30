---
ms.openlocfilehash: 958dede03e1c15f69f4ee676f13713ff43c29e96
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032600"
---
### <a name="logging-debuglogger-class-made-internal"></a>로깅: DebugLogger 클래스를 내부적으로 만들었습니다.

ASP.NET Core 3.0 이전에는 `DebugLogger`의 액세스 한정자가 `public`였습니다. ASP.NET Core 3.0에서 액세스 한정자가 `internal`로 변경되었습니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="reason-for-change"></a>변경 이유

변경 내용은 다음과 같습니다.

* `ConsoleLogger`와 같은 다른 로거 구현과 일관성을 유지합니다.
* API 표면을 줄입니다.

#### <a name="recommended-action"></a>권장 조치

<xref:Microsoft.Extensions.Logging.DebugLoggerFactoryExtensions.AddDebug%2A> `ILoggingBuilder` 확장 메서드를 사용하여 디버그 로깅을 사용하도록 설정합니다. 서비스를 수동으로 동록해야 하는 경우에도 <xref:Microsoft.Extensions.Logging.Debug.DebugLoggerProvider>는 여전히 `public`입니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

<xref:Microsoft.Extensions.Logging.Debug.DebugLogger?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.Extensions.Logging.Debug.DebugLogger`

-->

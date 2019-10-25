---
ms.openlocfilehash: e5355387d5cb6d9e6de89f5b85e64bc100b32ae1
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522664"
---
### <a name="spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger"></a>SPA: SpaServices 및 NodeServices가 더 이상 콘솔 로거로 대체되지 않습니다.

로깅을 구성하지 않으면 <xref:Microsoft.AspNetCore.SpaServices?displayProperty=nameWithType> 및 <xref:Microsoft.AspNetCore.NodeServices?displayProperty=nameWithType>에 콘솔 로그가 표시되지 않습니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

로깅이 구성되지 않은 경우 `Microsoft.AspNetCore.SpaServices` 및 `Microsoft.AspNetCore.NodeServices`는 콘솔 로거를 자동으로 만드는 데 사용됩니다.

#### <a name="new-behavior"></a>새 동작

로깅을 구성하지 않으면 `Microsoft.AspNetCore.SpaServices` 및 `Microsoft.AspNetCore.NodeServices`에 콘솔 로그가 표시되지 않습니다.

#### <a name="reason-for-change"></a>변경 이유

다른 ASP.NET Core 패키지에서 로깅을 구현하는 방법에 맞춰 조정할 필요가 있습니다.

#### <a name="recommended-action"></a>권장 작업

이전 동작이 필요한 경우 콘솔 로깅을 구성하려면 `Setup.ConfigureServices` 메서드에 `services.AddLogging(builder => builder.AddConsole())`을 추가합니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

없음

<!--

#### Affected APIs

Not detectable via API analysis

-->

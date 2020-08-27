---
ms.openlocfilehash: 115cd6be935ae12a1293f948a0f899c6c3ff0d78
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608466"
---
### <a name="winhttphandler-removed-from-net-runtime"></a>.NET 런타임에서 WinHttpHandler 제거됨

`WinHttpHandler` 클래스가 *System.Net.Http.dll* 어셈블리에서 제거되었습니다. 이제 OOB(대역 외) [NuGet 패키지](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/)로만 제공됩니다.

#### <a name="version-introduced"></a>도입된 버전

5.0

#### <a name="change-description"></a>변경 내용 설명

이전 .NET 버전에서는 <xref:System.Net.Http.WinHttpHandler> 클래스를 핵심 .NET 라이브러리의 일부로 사용할 수 있습니다. .NET 5.0부터 <xref:System.Net.Http.WinHttpHandler> 클래스는 별도로 설치되는 [NuGet 패키지](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/)로만 제공됩니다.

#### <a name="recommended-action"></a>권장 조치

[System.Net.Http.WinHttpHandler NuGet 패키지](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/)를 설치합니다. 또는 WinHTTP 관련 기능이 필요하지 않은 경우 <xref:System.Net.Http.SocketsHttpHandler>를 대신 사용합니다.

#### <a name="category"></a>범주

네트워킹

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Net.Http.WinHttpHandler?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Net.Http.WinHttpHandler`

-->

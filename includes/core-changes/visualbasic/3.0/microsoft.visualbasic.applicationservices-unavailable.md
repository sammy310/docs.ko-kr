---
ms.openlocfilehash: d8cc506d60f3c24087ebde8ead345656fea0f484
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "76116355"
---
### <a name="types-in-microsoftvisualbasicapplicationservices-namespace-not-available"></a>Microsoft.VisualBasic.ApplicationServices 네임스페이스의 형식을 사용할 수 없음

<xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName> 네임스페이스의 형식을 사용할 수 없습니다.

#### <a name="version-introduced"></a>도입된 버전

.NET Core 3.0 미리 보기 8

#### <a name="change-description"></a>변경 내용 설명

일부 .NET Core 3.0 미리 보기 릴리스에서는 <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName> 네임스페이스의 형식을 사용할 수 있었습니다. .NET Core 3.0 미리 보기 9부터는 해당 형식을 더 이상 사용할 수 없습니다.

후속 릴리스에서 불필요한 어셈블리 종속성이나 호환성이 손상되는 변경을 방지하기 위해 형식을 제거했습니다.

#### <a name="recommended-action"></a>권장 조치

코드에서 <xref:Microsoft.VisualBasic.ApplicationServices> 형식과 해당 멤버를 사용해야 하는 경우, .NET 클래스 라이브러리의 해당 형식이나 멤버를 사용할 수 있습니다. 예를 들어 <xref:System.Environment?displayProperty=nameWithType> 및 <xref:System.Security.Principal.WindowsIdentity?displayProperty=nameWithType>의 일부 멤버는 <xref:Microsoft.VisualBasic.ApplicationServices.User?displayProperty=nameWithType> 클래스의 속성과 동등한 기능을 제공합니다.

#### <a name="category"></a>범주

Visual Basic

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.ApplicationServices`

-->

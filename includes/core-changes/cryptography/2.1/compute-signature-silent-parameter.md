---
ms.openlocfilehash: 9583d868ee01117d7bd6e465e7d89a734489d1a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "77449226"
---
### <a name="boolean-parameter-of-signedcmscomputesignature-is-respected"></a>SignedCms.ComputeSignature의 부울 매개 변수를 적용

.NET Core에서 `silent` 메서드의 부울 <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> 매개 변수가 적용됩니다. 이 매개 변수가 `true`로 설정된 경우에는 PIN 프롬프트가 표시되지 않습니다.

#### <a name="change-description"></a>변경 내용 설명

.NET Framework에서 `silent` 메서드의 <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> 매개 변수는 무시되고 공급자에 필요한 경우 PIN 프롬프트가 항상 표시됩니다. .NET Core에서는 `silent` 매개 변수가 적용되며, `true`로 설정된 경우 공급자에 필요한 경우에도 PIN 프롬프트가 표시되지 않습니다.

CMS/PKCS #7 메시지에 대한 지원은 .NET Core 버전 2.1에 도입되었습니다.

#### <a name="version-introduced"></a>도입된 버전

2.1

#### <a name="recommended-action"></a>권장 조치

필요한 경우 PIN 프롬프트가 표시되도록 하려면 데스크톱 애플리케이션에서 <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType>를 호출하고 부울 매개 변수를 `false`로 설정해야 합니다. 자동 컨텍스트가 사용하지 않도록 설정되었는지 여부와 관계없이 결과 동작은 .NET Framework와 동일합니다.

### <a name="category"></a>범주

암호화

### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)`

-->

---
ms.openlocfilehash: e2ae329d027d605e6331afe422e550990fab1042
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614809"
---
### <a name="default-signedxml-and-signedxms-algorithms-changed-to-sha256"></a>기본 SignedXML 및 SignedXMS 알고리즘이 SHA256으로 변경됨

#### <a name="details"></a>설명

.NET Framework 4.7 이전 버전에서는 SignedXML 및 SignedCMS의 기본값이 일부 작업에서 SHA1로 설정되었습니다. .NET Framework 4.7.1부터 SHA256은 기본적으로 이러한 작업에 사용됩니다. SHA1은 더 이상 안전하지 않으므로 이 변경이 필요합니다.

#### <a name="suggestion"></a>제안 해결 방법

다음과 같이 SHA1(안전하지 않음) 또는 SHA256이 기본적으로 사용되는지 여부를 제어하는 두 가지 새로운 컨텍스트 스위치 값이 있습니다.

- Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms
- Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms .NET Framework 4.7.1 이상 버전을 대상으로 하는 애플리케이션의 경우 SHA256 사용이 바람직하지 않으면 앱 구성 파일의 [런타임](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 구성 스위치를 추가하여 기본값을 SHA1을 기본값으로 복원할 수 있습니다.

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms=true;Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms=true" />
```

.NET Framework 4.7 이전 버전을 대상으로 하는 애플리케이션의 경우 앱 구성 파일의 [런타임](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 구성 스위치를 추가하여 이 변경을 옵트인할 수 있습니다.

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms=false;Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms=false" />
```

| 이름    | 값       |
|:--------|:------------|
| Scope   | 부       |
| 버전 | 4.7.1       |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Security.Cryptography.Pkcs.CmsSigner?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.Reference?displayProperty=nameWithType>

---
ms.openlocfilehash: a4476fbff572c004632153e5a98812c241efca57
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721327"
---
### <a name="openssl-versions-on-macos"></a>macOS의 OpenSSL 버전

macOS에서 .NET Core 3.0 이상 런타임은 이제 <xref:System.Security.Cryptography.AesCcm>, <xref:System.Security.Cryptography.AesGcm>, <xref:System.Security.Cryptography.DSAOpenSsl>, <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>, <xref:System.Security.Cryptography.ECDsaOpenSsl>, <xref:System.Security.Cryptography.RSAOpenSsl> 및 <xref:System.Security.Cryptography.SafeEvpPKeyHandle> 형식에 대해 OpenSSL 1.0.x 버전보다 OpenSSL 1.1.x 버전을 선호합니다.

.NET Core 2.1 런타임은 이제 OpenSSL 1.1.x 버전을 지원하지만 여전히 OpenSSL 1.0.x 버전을 선호합니다.

#### <a name="change-description"></a>변경 내용 설명

이전에는 .NET Core 런타임이 macOS에서 OpenSSL과 상호 작용하는 형식에 대해 OpenSSL 1.0.x 버전을 사용했습니다. 최신 OpenSSL 1.0.x 버전인 OpenSSL 1.0.2는 이제 지원되지 않습니다. 지원되는 버전의 OpenSSL에 대해 OpenSSL을 사용하는 형식을 유지하기 위해 .NET Core 3.0 이상 런타임이 이제 macOS에서 최신 버전의 OpenSSL을 사용합니다.

이러한 변경을 통해 macOS에서 .NET Core 런타임에 대한 동작은 다음과 같습니다.

- .NET Core 3.0 이상 버전 런타임은 OpenSSL 1.1.x 버전(사용 가능한 경우)을 사용하고 사용 가능한 1.1.x 버전이 없는 경우에만 OpenSSL 1.0.x 버전으로 대체됩니다.

  사용자 지정 P/Invokes에 OpenSSL interop 형식을 사용하는 호출자의 경우 <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> 설명의 지침을 따릅니다. <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion> 값을 확인하지 않으면 앱의 작동이 중단될 수도 있습니다.

- .NET Core 2.1 런타임은 OpenSSL 1.0.x 버전(사용 가능한 경우)을 사용하고 사용 가능한 1.0.x 버전이 없는 경우 OpenSSL 1.1.x 버전으로 대체됩니다.

  .NET Core 2.1에 <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> 속성이 없어 런타임에 신뢰성 있게 OpenSSL 버전을 확인할 수 없기 때문에 2.1 런타임은 이전 버전의 OpenSSL을 선호합니다.

#### <a name="version-introduced"></a>도입된 버전

- .NET Core 2.1.16
- .NET Core 3.0.3
- .NET Core 3.1.2

#### <a name="recommended-action"></a>권장 조치

- 더 이상 필요하지 않으면 OpenSSL 1.0.2 버전을 제거합니다.

- <xref:System.Security.Cryptography.AesCcm>, <xref:System.Security.Cryptography.AesGcm>, <xref:System.Security.Cryptography.DSAOpenSsl>, <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>, <xref:System.Security.Cryptography.ECDsaOpenSsl>, <xref:System.Security.Cryptography.RSAOpenSsl> 또는 <xref:System.Security.Cryptography.SafeEvpPKeyHandle> 형식을 사용하는 경우 OpenSSL 1.1.x 버전을 설치합니다.

- 사용자 지정 P/Invokes에 OpenSSL interop 형식을 사용하는 경우 <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> 설명의 지침을 따릅니다.

#### <a name="category"></a>범주

핵심 .NET 라이브러리

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Security.Cryptography.AesCcm?displayProperty=fullName>
- <xref:System.Security.Cryptography.AesGcm?displayProperty=fullName>
- <xref:System.Security.Cryptography.DSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDsaOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.RSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.SafeEvpPKeyHandle?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Security.Cryptography.AesCcm``
- `T:System.Security.Cryptography.AesGcm`
- `T:System.Security.Cryptography.DSAOpenSsl`
- `T:System.Security.Cryptography.ECDiffieHellmanOpenSsl`
- `T:System.Security.Cryptography.ECDsaOpenSsl`
- `T:System.Security.Cryptography.RSAOpenSsl`
- `T:System.Security.Cryptography.SafeEvpPKeyHandle`

-->

---
ms.openlocfilehash: 4788f5b80306116e63ee56584d65b862ce0606ee
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497239"
---
### <a name="rsacng-and-dsacng-are-once-again-usable-in-partial-trust-scenarios"></a>RSACng 및 DSACng는 부분 신뢰 시나리오에서 다시 사용할 수 있습니다.

#### <a name="details"></a>세부 정보

CngLightup(<xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType>과 같이 몇 가지 더 높은 수준의 암호화 API에서 사용) 및 <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType>은(경우에 따라) 완전 신뢰에 의존합니다. 여기에 <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType> 권한을 어설션하지 않는 P/Invoke가 포함되며 <xref:System.Security.Cryptography.CngKey?displayProperty=nameWithType>에는 <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode?displayProperty=nameWithType>에 대한 권한 요구 사항이 있는 코드 경로가 포함됩니다. .NET Framework 4.6.2부터는 가능하면 CngLightup을 사용하여 <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType>으로 전환되었습니다. 결과적으로 <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=nameWithType>을 성공적으로 사용한 부분 신뢰 앱이 실패하고 <xref:System.Security.SecurityException> 예외를 throw합니다. 이 변경은 필요한 어설션을 추가하여 CngLightup을 사용하는 모든 함수에 필요한 권한을 부여합니다.

#### <a name="suggestion"></a>제안 해결 방법

.NET Framework 4.6.2에서 이러한 변경 내용이 부분 신뢰 앱에 부정적인 영향을 주는 경우 .NET Framework 4.7.1로 업그레이드합니다.

| Name    | 값       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|버전|4.6.2|
|형식|런타임|

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Security.Cryptography.DSACng.%23ctor(System.Security.Cryptography.CngKey)>
- <xref:System.Security.Cryptography.DSACng.Key?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSACng.LegalKeySizes?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSACng.CreateSignature(System.Byte[])?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSACng.VerifySignature(System.Byte[],System.Byte[])?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSACng.%23ctor(System.Security.Cryptography.CngKey)>
- <xref:System.Security.Cryptography.RSACng.Key?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSACng.Decrypt(System.Byte[],System.Security.Cryptography.RSAEncryptionPadding)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSACng.SignHash(System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.DSACng.#ctor(System.Security.Cryptography.CngKey)`
- `P:System.Security.Cryptography.DSACng.Key`
- `P:System.Security.Cryptography.DSACng.LegalKeySizes`
- `M:System.Security.Cryptography.DSACng.CreateSignature(System.Byte[])`
- `M:System.Security.Cryptography.DSACng.VerifySignature(System.Byte[],System.Byte[])`
- `M:System.Security.Cryptography.RSACng.#ctor(System.Security.Cryptography.CngKey)`
- `P:System.Security.Cryptography.RSACng.Key`
- `M:System.Security.Cryptography.RSACng.Decrypt(System.Byte[],System.Security.Cryptography.RSAEncryptionPadding)`
- `M:System.Security.Cryptography.RSACng.SignHash(System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)`

-->

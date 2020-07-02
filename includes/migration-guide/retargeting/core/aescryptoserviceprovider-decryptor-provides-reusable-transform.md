---
ms.openlocfilehash: 36a9db601f7637185bf48dfcbe2233b4489fcdcf
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614659"
---
### <a name="aescryptoserviceprovider-decryptor-provides-a-reusable-transform"></a>AesCryptoServiceProvider 암호 해독기가 재사용 가능한 변환을 제공

#### <a name="details"></a>설명

.NET Framework 4.6.2를 대상으로 하는 앱부터는 <xref:System.Security.Cryptography.AesCryptoServiceProvider> 암호 해독기가 재사용 가능 변환을 제공합니다. <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>을 호출하고 나면 변환이 다시 초기화되므로 재사용할 수 있습니다. 이전 버전 .NET Framework를 대상으로 하는 앱의 경우 <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>를 호출한 후에 <xref:System.Security.Cryptography.CryptoAPITransform.TransformBlock(System.Byte[],System.Int32,System.Int32,System.Byte[],System.Int32)?displayProperty=fullName>를 호출하여 암호 해독기를 재사용하려고 하면 <xref:System.Security.Cryptography.CryptographicException>가 throw되거나 손상된 데이터가 생성됩니다.

#### <a name="suggestion"></a>제안 해결 방법

이것이 예상된 동작이므로 이 변경의 영향은 최소화되어야 합니다. 이전 동작에 의존하는 애플리케이션은 애플리케이션 구성 파일의 `<runtime>` 섹션에 다음 구성 설정을 추가하여 이 동작을 옵트아웃할 수 있습니다.

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=true"/>
</runtime>
```

또한 이전 버전의 .NET Framework를 대상으로 하지만 .NET Framework 4.6.2부터 시작하는 .NET Framework 버전에서 실행되는 애플리케이션은 애플리케이션 구성 파일의 `<runtime>` 섹션에 다음 구성 설정을 추가하여 이 동작을 옵트인할 수 있습니다.

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=false"/>
</runtime>
```

| 이름    | 값       |
|:--------|:------------|
| Scope   | 부       |
| 버전 | 4.6.2       |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Security.Cryptography.AesCryptoServiceProvider.CreateDecryptor?displayProperty=nameWithType>

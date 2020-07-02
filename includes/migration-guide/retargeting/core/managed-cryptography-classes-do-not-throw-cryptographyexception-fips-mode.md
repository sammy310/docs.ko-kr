---
ms.openlocfilehash: 0b62eff8d70873293aafa539f40bf032672df57a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616277"
---
### <a name="managed-cryptography-classes-do-not-throw-a-cryptographyexception-in-fips-mode"></a>관리형 암호화 클래스가 FIPS 모드에서 CryptographyException을 throw하지 않음

#### <a name="details"></a>설명

.NET Framework 4.7.2 이전 버전에서 <xref:System.Security.Cryptography.SHA256Managed>와 같은 관리형 암호화 공급자 클래스는 시스템 암호화 라이브러리가 FIPS 모드로 구성될 때 <xref:System.Security.Cryptography.CryptographicException>을 throw합니다. 이러한 예외는 관리형 버전이 FIPS(Federal Information Processing) 140-2 인증을 받지 않았고 FIPS 규칙에 따라 승인된 것으로 간주되지 않는 암호화 알고리즘을 차단하기 때문에 throw됩니다.  FIPS 모드에서 개발 머신을 사용하는 개발자는 거의 없기 때문에 이러한 예외는 프로덕션 시스템에서만 자주 throw됩니다. 이러한 경우 .NET Framework 4.8 이상 버전을 대상으로 하는 애플리케이션은 <xref:System.Security.Cryptography.CryptographicException>이 더 이상 기본적으로 제공되지 않도록 자동으로 최신의 완화된 정책으로 전환됩니다. 대신, 관리형 암호화 클래스는 암호화 작업을 시스템 암호화 라이브러리로 리디렉션합니다. 이 정책 변경에 따라 개발자 환경과 프로덕션 환경 간에 혼동될 수 있는 차이가 효과적으로 제거되고 네이티브 구성 요소와 관리형 구성 요소가 동일한 암호화 정책에서 작동합니다.

#### <a name="suggestion"></a>제안 해결 방법

이 동작이 바람직하지 않은 경우 애플리케이션의 구성 파일의 [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 구성 설정을 추가하여 <xref:System.Security.Cryptography.CryptographicException>이 FIPS 모드에서 throw되도록 이전 동작을 옵트아웃하고 복원할 수 있습니다.

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.UseLegacyFipsThrow=true" />
</runtime>
```

애플리케이션이 .NET Framework 4.7.2 이하를 대상으로 하는 경우 애플리케이션 구성 파일의 [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 구성 설정을 추가하여 이 변경 내용을 옵트인할 수도 있습니다.

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.UseLegacyFipsThrow=false" />
</runtime>
```

| 이름    | 값       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| 버전 | 4.8         |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Security.Cryptography.AesManaged?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.MD5Cng?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.MD5CryptoServiceProvider?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RC2CryptoServiceProvider?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RijndaelManaged?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RIPEMD160Managed?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.SHA1Managed?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.SHA256Managed?displayProperty=nameWithType>

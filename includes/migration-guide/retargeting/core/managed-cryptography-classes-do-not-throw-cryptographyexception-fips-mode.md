---
ms.openlocfilehash: 0b62eff8d70873293aafa539f40bf032672df57a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616277"
---
### <a name="managed-cryptography-classes-do-not-throw-a-cryptographyexception-in-fips-mode"></a><span data-ttu-id="d93b2-101">관리형 암호화 클래스가 FIPS 모드에서 CryptographyException을 throw하지 않음</span><span class="sxs-lookup"><span data-stu-id="d93b2-101">Managed cryptography classes do not throw a CryptographyException in FIPS mode</span></span>

#### <a name="details"></a><span data-ttu-id="d93b2-102">설명</span><span class="sxs-lookup"><span data-stu-id="d93b2-102">Details</span></span>

<span data-ttu-id="d93b2-103">.NET Framework 4.7.2 이전 버전에서 <xref:System.Security.Cryptography.SHA256Managed>와 같은 관리형 암호화 공급자 클래스는 시스템 암호화 라이브러리가 FIPS 모드로 구성될 때 <xref:System.Security.Cryptography.CryptographicException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="d93b2-103">In .NET Framework 4.7.2 and earlier versions, managed cryptographic provider classes such as <xref:System.Security.Cryptography.SHA256Managed> throw a <xref:System.Security.Cryptography.CryptographicException> when the system cryptographic libraries are configured in FIPS mode.</span></span> <span data-ttu-id="d93b2-104">이러한 예외는 관리형 버전이 FIPS(Federal Information Processing) 140-2 인증을 받지 않았고 FIPS 규칙에 따라 승인된 것으로 간주되지 않는 암호화 알고리즘을 차단하기 때문에 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d93b2-104">These exceptions are thrown because the managed versions have not undergone FIPS (Federal Information Processing Standards) 140-2 certification, as well as to block cryptographic algorithms that were not considered to be approved based on the FIPS rules.</span></span>  <span data-ttu-id="d93b2-105">FIPS 모드에서 개발 머신을 사용하는 개발자는 거의 없기 때문에 이러한 예외는 프로덕션 시스템에서만 자주 throw됩니다. 이러한 경우 .NET Framework 4.8 이상 버전을 대상으로 하는 애플리케이션은 <xref:System.Security.Cryptography.CryptographicException>이 더 이상 기본적으로 제공되지 않도록 자동으로 최신의 완화된 정책으로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d93b2-105">Because few developers have their development machines in FIPS mode, these exceptions are frequently thrown only on production systems.Applications that target .NET Framework 4.8 and later versions automatically switch to the newer, relaxed policy, so that a <xref:System.Security.Cryptography.CryptographicException> is no longer thrown by default in such cases.</span></span> <span data-ttu-id="d93b2-106">대신, 관리형 암호화 클래스는 암호화 작업을 시스템 암호화 라이브러리로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="d93b2-106">Instead, the managed cryptography classes redirect cryptographic operations to a system cryptography library.</span></span> <span data-ttu-id="d93b2-107">이 정책 변경에 따라 개발자 환경과 프로덕션 환경 간에 혼동될 수 있는 차이가 효과적으로 제거되고 네이티브 구성 요소와 관리형 구성 요소가 동일한 암호화 정책에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="d93b2-107">This policy change effectively removes a potentially confusing difference between developer environments and the production environments and makes native components and managed components operate under the same cryptographic policy.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d93b2-108">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="d93b2-108">Suggestion</span></span>

<span data-ttu-id="d93b2-109">이 동작이 바람직하지 않은 경우 애플리케이션의 구성 파일의 [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 구성 설정을 추가하여 <xref:System.Security.Cryptography.CryptographicException>이 FIPS 모드에서 throw되도록 이전 동작을 옵트아웃하고 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d93b2-109">If this behavior is undesirable, you can opt out of it and restore the previous behavior so that a <xref:System.Security.Cryptography.CryptographicException> is thrown in FIPS mode by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) configuration setting to the [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.UseLegacyFipsThrow=true" />
</runtime>
```

<span data-ttu-id="d93b2-110">애플리케이션이 .NET Framework 4.7.2 이하를 대상으로 하는 경우 애플리케이션 구성 파일의 [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 구성 설정을 추가하여 이 변경 내용을 옵트인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d93b2-110">If your application targets .NET Framework 4.7.2 or earlier, you can also opt in to this change by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) configuration setting to the [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.UseLegacyFipsThrow=false" />
</runtime>
```

| <span data-ttu-id="d93b2-111">이름</span><span class="sxs-lookup"><span data-stu-id="d93b2-111">Name</span></span>    | <span data-ttu-id="d93b2-112">값</span><span class="sxs-lookup"><span data-stu-id="d93b2-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d93b2-113">Scope</span><span class="sxs-lookup"><span data-stu-id="d93b2-113">Scope</span></span>   | <span data-ttu-id="d93b2-114">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d93b2-114">Edge</span></span>        |
| <span data-ttu-id="d93b2-115">버전</span><span class="sxs-lookup"><span data-stu-id="d93b2-115">Version</span></span> | <span data-ttu-id="d93b2-116">4.8</span><span class="sxs-lookup"><span data-stu-id="d93b2-116">4.8</span></span>         |
| <span data-ttu-id="d93b2-117">형식</span><span class="sxs-lookup"><span data-stu-id="d93b2-117">Type</span></span>    | <span data-ttu-id="d93b2-118">대상 변경</span><span class="sxs-lookup"><span data-stu-id="d93b2-118">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="d93b2-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="d93b2-119">Affected APIs</span></span>

- <xref:System.Security.Cryptography.AesManaged?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.MD5Cng?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.MD5CryptoServiceProvider?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RC2CryptoServiceProvider?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RijndaelManaged?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RIPEMD160Managed?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.SHA1Managed?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.SHA256Managed?displayProperty=nameWithType>

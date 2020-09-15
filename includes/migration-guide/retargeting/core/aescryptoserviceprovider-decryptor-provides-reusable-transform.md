---
ms.openlocfilehash: 36a9db601f7637185bf48dfcbe2233b4489fcdcf
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614659"
---
### <a name="aescryptoserviceprovider-decryptor-provides-a-reusable-transform"></a><span data-ttu-id="9cc20-101">AesCryptoServiceProvider 암호 해독기가 재사용 가능한 변환을 제공</span><span class="sxs-lookup"><span data-stu-id="9cc20-101">AesCryptoServiceProvider decryptor provides a reusable transform</span></span>

#### <a name="details"></a><span data-ttu-id="9cc20-102">설명</span><span class="sxs-lookup"><span data-stu-id="9cc20-102">Details</span></span>

<span data-ttu-id="9cc20-103">.NET Framework 4.6.2를 대상으로 하는 앱부터는 <xref:System.Security.Cryptography.AesCryptoServiceProvider> 암호 해독기가 재사용 가능 변환을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9cc20-103">Starting with apps that target the .NET Framework 4.6.2, the <xref:System.Security.Cryptography.AesCryptoServiceProvider> decryptor provides a reusable transform.</span></span> <span data-ttu-id="9cc20-104"><xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>을 호출하고 나면 변환이 다시 초기화되므로 재사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cc20-104">After a call to <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>, the transform is reinitialized and can be reused.</span></span> <span data-ttu-id="9cc20-105">이전 버전 .NET Framework를 대상으로 하는 앱의 경우 <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>를 호출한 후에 <xref:System.Security.Cryptography.CryptoAPITransform.TransformBlock(System.Byte[],System.Int32,System.Int32,System.Byte[],System.Int32)?displayProperty=fullName>를 호출하여 암호 해독기를 재사용하려고 하면 <xref:System.Security.Cryptography.CryptographicException>가 throw되거나 손상된 데이터가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cc20-105">For apps that target earlier versions of the .NET Framework, attempting to reuse the decryptor by calling <xref:System.Security.Cryptography.CryptoAPITransform.TransformBlock(System.Byte[],System.Int32,System.Int32,System.Byte[],System.Int32)?displayProperty=fullName> after a call to <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName> throws a <xref:System.Security.Cryptography.CryptographicException> or produces corrupted data.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9cc20-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="9cc20-106">Suggestion</span></span>

<span data-ttu-id="9cc20-107">이것이 예상된 동작이므로 이 변경의 영향은 최소화되어야 합니다. 이전 동작에 의존하는 애플리케이션은 애플리케이션 구성 파일의 `<runtime>` 섹션에 다음 구성 설정을 추가하여 이 동작을 옵트아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cc20-107">The impact of this change should be minimal, since this is the expected behavior.Applications that depend on the previous behavior can opt out of it using it by adding the following configuration setting to the `<runtime>` section of the application's configuration file:</span></span>

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=true"/>
</runtime>
```

<span data-ttu-id="9cc20-108">또한 이전 버전의 .NET Framework를 대상으로 하지만 .NET Framework 4.6.2부터 시작하는 .NET Framework 버전에서 실행되는 애플리케이션은 애플리케이션 구성 파일의 `<runtime>` 섹션에 다음 구성 설정을 추가하여 이 동작을 옵트인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cc20-108">In addition, applications that target a previous version of the .NET Framework but are running under a version of the .NET Framework starting with .NET Framework 4.6.2 can opt in to it by adding the following configuration setting to the `<runtime>` section of the application's configuration file:</span></span>

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=false"/>
</runtime>
```

| <span data-ttu-id="9cc20-109">이름</span><span class="sxs-lookup"><span data-stu-id="9cc20-109">Name</span></span>    | <span data-ttu-id="9cc20-110">값</span><span class="sxs-lookup"><span data-stu-id="9cc20-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9cc20-111">Scope</span><span class="sxs-lookup"><span data-stu-id="9cc20-111">Scope</span></span>   | <span data-ttu-id="9cc20-112">부</span><span class="sxs-lookup"><span data-stu-id="9cc20-112">Minor</span></span>       |
| <span data-ttu-id="9cc20-113">버전</span><span class="sxs-lookup"><span data-stu-id="9cc20-113">Version</span></span> | <span data-ttu-id="9cc20-114">4.6.2</span><span class="sxs-lookup"><span data-stu-id="9cc20-114">4.6.2</span></span>       |
| <span data-ttu-id="9cc20-115">형식</span><span class="sxs-lookup"><span data-stu-id="9cc20-115">Type</span></span>    | <span data-ttu-id="9cc20-116">대상 변경</span><span class="sxs-lookup"><span data-stu-id="9cc20-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="9cc20-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="9cc20-117">Affected APIs</span></span>

- <xref:System.Security.Cryptography.AesCryptoServiceProvider.CreateDecryptor?displayProperty=nameWithType>

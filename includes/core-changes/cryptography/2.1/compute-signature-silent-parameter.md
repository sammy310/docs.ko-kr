---
ms.openlocfilehash: 9583d868ee01117d7bd6e465e7d89a734489d1a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "77449226"
---
### <a name="boolean-parameter-of-signedcmscomputesignature-is-respected"></a><span data-ttu-id="773e8-101">SignedCms.ComputeSignature의 부울 매개 변수를 적용</span><span class="sxs-lookup"><span data-stu-id="773e8-101">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>

<span data-ttu-id="773e8-102">.NET Core에서 `silent` 메서드의 부울 <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> 매개 변수가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="773e8-102">In .NET Core, the Boolean `silent` parameter of the <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> method is respected.</span></span> <span data-ttu-id="773e8-103">이 매개 변수가 `true`로 설정된 경우에는 PIN 프롬프트가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="773e8-103">A PIN prompt is not shown if this parameter is set to `true`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="773e8-104">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="773e8-104">Change description</span></span>

<span data-ttu-id="773e8-105">.NET Framework에서 `silent` 메서드의 <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> 매개 변수는 무시되고 공급자에 필요한 경우 PIN 프롬프트가 항상 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="773e8-105">In .NET Framework, the `silent` parameter of the <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> method is ignored, and a PIN prompt is always shown if required by the provider.</span></span> <span data-ttu-id="773e8-106">.NET Core에서는 `silent` 매개 변수가 적용되며, `true`로 설정된 경우 공급자에 필요한 경우에도 PIN 프롬프트가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="773e8-106">In .NET Core, the `silent` parameter is respected, and if set to `true`, a PIN prompt is never shown, even if it's required by the provider.</span></span>

<span data-ttu-id="773e8-107">CMS/PKCS #7 메시지에 대한 지원은 .NET Core 버전 2.1에 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="773e8-107">Support for CMS/PKCS #7 messages was introduced into .NET Core in version 2.1.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="773e8-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="773e8-108">Version introduced</span></span>

<span data-ttu-id="773e8-109">2.1</span><span class="sxs-lookup"><span data-stu-id="773e8-109">2.1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="773e8-110">권장 조치</span><span class="sxs-lookup"><span data-stu-id="773e8-110">Recommended action</span></span>

<span data-ttu-id="773e8-111">필요한 경우 PIN 프롬프트가 표시되도록 하려면 데스크톱 애플리케이션에서 <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType>를 호출하고 부울 매개 변수를 `false`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="773e8-111">To ensure a PIN prompt appears if required, desktop applications should call <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> and set the Boolean parameter to `false`.</span></span> <span data-ttu-id="773e8-112">자동 컨텍스트가 사용하지 않도록 설정되었는지 여부와 관계없이 결과 동작은 .NET Framework와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="773e8-112">The resulting behavior is the same as on .NET Framework regardless of whether the silent context is disabled there.</span></span>

### <a name="category"></a><span data-ttu-id="773e8-113">범주</span><span class="sxs-lookup"><span data-stu-id="773e8-113">Category</span></span>

<span data-ttu-id="773e8-114">암호화</span><span class="sxs-lookup"><span data-stu-id="773e8-114">Cryptography</span></span>

### <a name="affected-apis"></a><span data-ttu-id="773e8-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="773e8-115">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)`

-->

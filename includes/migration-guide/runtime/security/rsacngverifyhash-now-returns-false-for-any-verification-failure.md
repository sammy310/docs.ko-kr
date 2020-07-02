---
ms.openlocfilehash: fa5cf2280cdd9535962568a6272d047d261eeba5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621206"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a><span data-ttu-id="7477c-101">RSACng.VerifyHash가 이제 확인 실패에 대해 False를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7477c-101">RSACng.VerifyHash now returns False for any verification failure</span></span>

#### <a name="details"></a><span data-ttu-id="7477c-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="7477c-102">Details</span></span>

<span data-ttu-id="7477c-103">.NET Framework 4.6.2부터 서명 자체의 형식이 잘못된 경우 이 메서드는 **False**를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7477c-103">Starting with the .NET Framework 4.6.2, this method returns **False** if the signature itself is badly formatted.</span></span> <span data-ttu-id="7477c-104">이제 모든 확인 실패에 대해 false를 반환합니다. .NET Framework 4.6 및 4.6.1에서는 서명 자체의 형식이 잘못된 경우 메서드에서 <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="7477c-104">It now returns false for any verification failure.In the .NET Framework 4.6 and 4.6.1, the method throws a <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> if the signature itself is badly formatted.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7477c-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="7477c-105">Suggestion</span></span>

<span data-ttu-id="7477c-106">유효성 검사가 실패하고 이 메서드가 **False**를 반환하는 경우에는 <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> 처리에 따라 실행되는 코드를 대신 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7477c-106">Any code whose execution depends on handling the <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> should instead execute if validation fails and the method returns **False**.</span></span>

| <span data-ttu-id="7477c-107">이름</span><span class="sxs-lookup"><span data-stu-id="7477c-107">Name</span></span>    | <span data-ttu-id="7477c-108">값</span><span class="sxs-lookup"><span data-stu-id="7477c-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7477c-109">Scope</span><span class="sxs-lookup"><span data-stu-id="7477c-109">Scope</span></span>   |<span data-ttu-id="7477c-110">부</span><span class="sxs-lookup"><span data-stu-id="7477c-110">Minor</span></span>|
|<span data-ttu-id="7477c-111">버전</span><span class="sxs-lookup"><span data-stu-id="7477c-111">Version</span></span>|<span data-ttu-id="7477c-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="7477c-112">4.6.2</span></span>|
|<span data-ttu-id="7477c-113">형식</span><span class="sxs-lookup"><span data-stu-id="7477c-113">Type</span></span>|<span data-ttu-id="7477c-114">런타임</span><span class="sxs-lookup"><span data-stu-id="7477c-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7477c-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="7477c-115">Affected APIs</span></span>

-<xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|

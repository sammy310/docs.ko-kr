---
ms.openlocfilehash: acf4e8df2cef3d9ec5d123a14cc7bfcd6f1bfb8b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236041"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a><span data-ttu-id="98a49-101">RSACng.VerifyHash가 이제 확인 실패에 대해 False를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="98a49-101">RSACng.VerifyHash now returns False for any verification failure</span></span>

|   |   |
|---|---|
|<span data-ttu-id="98a49-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="98a49-102">Details</span></span>|<span data-ttu-id="98a49-103">.NET Framework 4.6.2부터 서명 자체의 형식이 잘못된 경우 이 메서드는 <strong>False</strong>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="98a49-103">Starting with the .NET Framework 4.6.2, this method returns <strong>False</strong> if the signature itself is badly formatted.</span></span> <span data-ttu-id="98a49-104">이제 모든 확인 실패에 대해 false를 반환합니다. .NET Framework 4.6 및 4.6.1에서는 서명 자체의 형식이 잘못된 경우 메서드에서 <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="98a49-104">It now returns false for any verification failure.In the .NET Framework 4.6 and 4.6.1, the method throws a <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> if the signature itself is badly formatted.</span></span>|
|<span data-ttu-id="98a49-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="98a49-105">Suggestion</span></span>|<span data-ttu-id="98a49-106">유효성 검사가 실패하고 이 메서드가 <strong>False</strong>를 반환하는 경우에는 <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> 처리에 따라 실행되는 코드를 대신 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98a49-106">Any code whose execution depends on handling the <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> should instead execute if validation fails and the method returns <strong>False</strong>.</span></span>|
|<span data-ttu-id="98a49-107">범위</span><span class="sxs-lookup"><span data-stu-id="98a49-107">Scope</span></span>|<span data-ttu-id="98a49-108">부</span><span class="sxs-lookup"><span data-stu-id="98a49-108">Minor</span></span>|
|<span data-ttu-id="98a49-109">버전</span><span class="sxs-lookup"><span data-stu-id="98a49-109">Version</span></span>|<span data-ttu-id="98a49-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="98a49-110">4.6.2</span></span>|
|<span data-ttu-id="98a49-111">형식</span><span class="sxs-lookup"><span data-stu-id="98a49-111">Type</span></span>|<span data-ttu-id="98a49-112">런타임</span><span class="sxs-lookup"><span data-stu-id="98a49-112">Runtime</span></span>|
|<span data-ttu-id="98a49-113">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="98a49-113">Affected APIs</span></span>|<ul><li><xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|

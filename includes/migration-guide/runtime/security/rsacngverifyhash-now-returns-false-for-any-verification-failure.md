---
ms.openlocfilehash: 7d60578ac2913037e1cdeda329f06f9a4986574d
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67857486"
---
### <a name="rsacngverifyhash-now-returns-false-for-any-verification-failure"></a><span data-ttu-id="2f658-101">RSACng.VerifyHash가 이제 확인 실패에 대해 False를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2f658-101">RSACng.VerifyHash now returns False for any verification failure</span></span>

|   |   |
|---|---|
|<span data-ttu-id="2f658-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="2f658-102">Details</span></span>|<span data-ttu-id="2f658-103">.NET Framework 4.6.2부터 서명 자체의 형식이 잘못된 경우 이 메서드는 <strong>False</strong>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2f658-103">Starting with the .NET Framework 4.6.2, this method returns <strong>False</strong> if the signature itself is badly formatted.</span></span> <span data-ttu-id="2f658-104">이제 모든 확인 실패에 대해 false를 반환합니다. .NET Framework 4.6 및 4.6.1에서는 서명 자체의 형식이 잘못된 경우 메서드에서 <xref:System.Security.Cryptography.CryptographicException?displayProperty=name>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="2f658-104">It now returns false for any verification failure.In the .NET Framework 4.6 and 4.6.1, the method throws a <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> if the signature itself is badly formatted.</span></span>|
|<span data-ttu-id="2f658-105">제안</span><span class="sxs-lookup"><span data-stu-id="2f658-105">Suggestion</span></span>|<span data-ttu-id="2f658-106">유효성 검사가 실패하고 이 메서드가 <strong>False</strong>를 반환하는 경우에는 <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> 처리에 따라 실행되는 코드를 대신 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f658-106">Any code whose execution depends on handling the <xref:System.Security.Cryptography.CryptographicException?displayProperty=name> should instead execute if validation fails and the method returns <strong>False</strong>.</span></span>|
|<span data-ttu-id="2f658-107">범위</span><span class="sxs-lookup"><span data-stu-id="2f658-107">Scope</span></span>|<span data-ttu-id="2f658-108">부</span><span class="sxs-lookup"><span data-stu-id="2f658-108">Minor</span></span>|
|<span data-ttu-id="2f658-109">버전</span><span class="sxs-lookup"><span data-stu-id="2f658-109">Version</span></span>|<span data-ttu-id="2f658-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="2f658-110">4.6.2</span></span>|
|<span data-ttu-id="2f658-111">형식</span><span class="sxs-lookup"><span data-stu-id="2f658-111">Type</span></span>|<span data-ttu-id="2f658-112">런타임</span><span class="sxs-lookup"><span data-stu-id="2f658-112">Runtime</span></span>|
|<span data-ttu-id="2f658-113">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="2f658-113">Affected APIs</span></span>|<ul><li><xref:System.Security.Cryptography.RSACng.VerifyHash(System.Byte[],System.Byte[],System.Security.Cryptography.HashAlgorithmName,System.Security.Cryptography.RSASignaturePadding)?displayProperty=nameWithType></li></ul>|


---
ms.openlocfilehash: c1e85941c8c6c31c7d937d0671ad955fa6490783
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614650"
---
### <a name="rsacng-now-correctly-loads-rsa-keys-of-non-standard-key-size"></a><span data-ttu-id="f209b-101">이제 RSACng가 비표준 키 크기의 RSA 키를 올바르게 로드함</span><span class="sxs-lookup"><span data-stu-id="f209b-101">RSACng now correctly loads RSA keys of non-standard key size</span></span>

#### <a name="details"></a><span data-ttu-id="f209b-102">설명</span><span class="sxs-lookup"><span data-stu-id="f209b-102">Details</span></span>

<span data-ttu-id="f209b-103">4\.6.2 이전의 .NET Framework 버전의 경우, RSA 인증서의 비표준 키 크기를 가진 고객은 <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=fullName> 및 <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=fullName> 확장 메서드를 통해 해당 키에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f209b-103">In .NET Framework versions prior to 4.6.2, customers with non-standard key sizes for RSA certificates are unable to access those keys via the <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=fullName> and <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=fullName> extension methods.</span></span>  <span data-ttu-id="f209b-104">&quot;요청한 키 크기가 지원되지 않습니다&quot; 메시지와 함께 <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="f209b-104">A <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> with the message &quot;The requested key size is not supported&quot; is thrown.</span></span> <span data-ttu-id="f209b-105">.NET Framework 4.6.2에서 이 문제가 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f209b-105">In .NET Framework 4.6.2 this issue has been fixed.</span></span> <span data-ttu-id="f209b-106">마찬가지로, <xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)> 및 <xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)>은 <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>을 throw하지 않고 비표준 키 크기로 작업합니다.</span><span class="sxs-lookup"><span data-stu-id="f209b-106">Similarly, <xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)> and <xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)> now work with non-standard key sizes without throwing a <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f209b-107">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="f209b-107">Suggestion</span></span>

<span data-ttu-id="f209b-108">비표준 키 크기가 사용될 때 <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>이 throw되는 이전 동작에 의존하는 예외 처리 논리가 있는 경우 논리 제거를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="f209b-108">If there is any exception handling logic that relies on the previous behavior where a <xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName> is thrown when non-standard key sizes are used, consider removing the logic.</span></span>

| <span data-ttu-id="f209b-109">이름</span><span class="sxs-lookup"><span data-stu-id="f209b-109">Name</span></span>    | <span data-ttu-id="f209b-110">값</span><span class="sxs-lookup"><span data-stu-id="f209b-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f209b-111">Scope</span><span class="sxs-lookup"><span data-stu-id="f209b-111">Scope</span></span>   | <span data-ttu-id="f209b-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f209b-112">Edge</span></span>        |
| <span data-ttu-id="f209b-113">버전</span><span class="sxs-lookup"><span data-stu-id="f209b-113">Version</span></span> | <span data-ttu-id="f209b-114">4.6.2</span><span class="sxs-lookup"><span data-stu-id="f209b-114">4.6.2</span></span>       |
| <span data-ttu-id="f209b-115">형식</span><span class="sxs-lookup"><span data-stu-id="f209b-115">Type</span></span>    | <span data-ttu-id="f209b-116">대상 변경</span><span class="sxs-lookup"><span data-stu-id="f209b-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="f209b-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="f209b-117">Affected APIs</span></span>

- <xref:System.Security.Cryptography.RSA.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSACng.ImportParameters(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?displayProperty=nameWithType>

---
ms.openlocfilehash: 2fb980c8b75e25ba347c56ccc1c90f2959e83e21
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2019
ms.locfileid: "74567945"
---
### <a name="minimum-size-for-rsaopenssl-key-generation-has-increased"></a><span data-ttu-id="a1ebb-101">RSAOpenSsl 키 생성 최소 크기가 증가</span><span class="sxs-lookup"><span data-stu-id="a1ebb-101">Minimum size for RSAOpenSsl key generation has increased</span></span>

<span data-ttu-id="a1ebb-102">Linux에서 새 RSA 키를 생성하기 위한 최소 크기가 384비트에서 512비트로 증가했습니다.</span><span class="sxs-lookup"><span data-stu-id="a1ebb-102">The minimum size for generating new RSA keys on Linux has increased from 384-bit to 512-bit.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a1ebb-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="a1ebb-103">Change description</span></span>

<span data-ttu-id="a1ebb-104">.NET Core 3.0부터는 Linux의 <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>, <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor%2A?displayProperty=nameWithType> 및 <xref:System.Security.Cryptography.RSACryptoServiceProvider.%23ctor%2A?displayProperty=nameWithType>에서 RSA 인스턴스의 `LegalKeySizes` 속성이 보고하는 합법적인 최소 키 크기가 384에서 512로 증가했습니다.</span><span class="sxs-lookup"><span data-stu-id="a1ebb-104">Starting with .NET Core 3.0, the minimum legal key size reported by the `LegalKeySizes` property on RSA instances from <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>, <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor%2A?displayProperty=nameWithType>, and <xref:System.Security.Cryptography.RSACryptoServiceProvider.%23ctor%2A?displayProperty=nameWithType> on Linux has increased from 384 to 512.</span></span>

<span data-ttu-id="a1ebb-105">따라서 .NET Core 2.2 버전 이하에서는 `RSA.Create(384)` 같은 메서드 호출이 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="a1ebb-105">As a result, in .NET Core 2.2 and earlier versions, a method call such as `RSA.Create(384)` succeeds.</span></span> <span data-ttu-id="a1ebb-106">.Net Core 3.0 버전 이상에서 메서드 호출 `RSA.Create(384)`는 크기가 너무 작음을 나타내는 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="a1ebb-106">In .NET Core 3.0 and later versions, the method call `RSA.Create(384)` throws an exception indicating the size is too small.</span></span>

<span data-ttu-id="a1ebb-107">이 변경은 Linux에서 암호화 작업을 수행하는 OpenSSL이 버전 1.0.2와 1.1.0 간에 최소값을 상향했기 때문에 적용된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a1ebb-107">This change was made because OpenSSL, which performs the cryptographic operations on Linux, raised its minimum between versions 1.0.2 and 1.1.0.</span></span> <span data-ttu-id="a1ebb-108">.NET Core 3.0은 OpenSSL 1.0.x보다 1.1.x를 기본으로 적용하고, 이 높아진 새 종속성 제한을 반영하기 위해 보고된 최소 버전이 상향되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a1ebb-108">.NET Core 3.0 prefers OpenSSL 1.1.x to 1.0.x, and the minimum reported version was raised to reflect this new higher dependency limitation.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a1ebb-109">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="a1ebb-109">Version introduced</span></span>

<span data-ttu-id="a1ebb-110">3.0</span><span class="sxs-lookup"><span data-stu-id="a1ebb-110">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a1ebb-111">권장 작업</span><span class="sxs-lookup"><span data-stu-id="a1ebb-111">Recommended action</span></span>

<span data-ttu-id="a1ebb-112">영향을 받는 API를 호출하는 경우 생성된 키의 크기가 공급자 최소값보다 작지 않은지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="a1ebb-112">If you call any of the affected APIs, ensure that the size of any generated keys is not less than the provider minimum.</span></span>

> [!NOTE]
> <span data-ttu-id="a1ebb-113">384비트 RSA는 이미 안전하지 않은 것으로 간주됩니다(512비트 RSA도 마찬가지).</span><span class="sxs-lookup"><span data-stu-id="a1ebb-113">384-bit RSA is already considered insecure (as is 512-bit RSA).</span></span> <span data-ttu-id="a1ebb-114">[NIST 특별 간행물 800-57 1부 수정 버전 4](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf)와 같은 최신 권장 사항은 새로 생성된 키에 대한 최소 크기로 2048 비트를 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="a1ebb-114">Modern recommendations, such as [NIST Special Publication 800-57 Part 1 Revision 4](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf), suggest 2048-bit as the minimum size for newly generated keys.</span></span>

#### <a name="category"></a><span data-ttu-id="a1ebb-115">범주</span><span class="sxs-lookup"><span data-stu-id="a1ebb-115">Category</span></span>

<span data-ttu-id="a1ebb-116">암호화</span><span class="sxs-lookup"><span data-stu-id="a1ebb-116">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a1ebb-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="a1ebb-117">Affected APIs</span></span>

- <xref:System.Security.Cryptography.AsymmetricAlgorithm.LegalKeySizes?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor%2A?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSACryptoServiceProvider.%23ctor%2A?displayProperty=nameWithType>

<!--
### Affected APIs

- `P:System.Security.Cryptography.AsymmetricAlgorithm.LegalKeySizes`
- `Overload:System.Security.Cryptography.RSA.Create`
- `Overload:System.Security.Cryptography.RSAOpenSsl.#ctor`
- `Overload:System.Security.Cryptography.RSACryptoServiceProvider.#ctor`

-->

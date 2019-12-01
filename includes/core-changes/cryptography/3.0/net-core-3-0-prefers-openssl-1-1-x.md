---
ms.openlocfilehash: b49b2f88b130bb952b77964d5bf38374dc606385
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2019
ms.locfileid: "74567967"
---
### <a name="net-core-30-prefers-openssl-11x-to-openssl-10x"></a><span data-ttu-id="6f45a-101">.NET Core 3.0은 OpenSSL 1.0.x보다 OpenSSL 1.1.x를 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="6f45a-101">.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x</span></span>

<span data-ttu-id="6f45a-102">여러 Linux 배포판에서 작동하는 Linux용 .NET Core는 OpenSSL 1.0.x와 OpenSSL 1.1.x를 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6f45a-102">.NET Core for Linux, which works across multiple Linux distributions, can support both OpenSSL 1.0.x and OpenSSL 1.1.x.</span></span>  <span data-ttu-id="6f45a-103">.NET Core 2.1 및 .NET Core 2.2는 먼저 1.0.x를 찾은 다음 1.1.x로 대체합니다. .NET Core 3.0은 1.1.x부터 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="6f45a-103">.NET Core 2.1 and .NET Core 2.2 look for 1.0.x first, then fall back to 1.1.x; .NET Core 3.0 looks for 1.1.x first.</span></span> <span data-ttu-id="6f45a-104">이 변경은 새로운 암호화 표준에 대한 지원을 추가하기 위해 실시된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6f45a-104">This change was made to add support for new cryptographic standards.</span></span>

<span data-ttu-id="6f45a-105">이 변경이 .NET Core에서 OpenSSL 특정 상호 작용 형식으로 플랫폼 상호 작용을 수행하는 라이브러리나 애플리케이션에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f45a-105">This change may impact libraries or applications that do platform interop with the OpenSSL-specific interop types in .NET Core.</span></span>

#### <a name="change-description"></a><span data-ttu-id="6f45a-106">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="6f45a-106">Change description</span></span>

<span data-ttu-id="6f45a-107">.NET Core 2.2 버전 이하에서 런타임은 OpenSSL 1.0.x보다 1.1.x를 우선적으로 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="6f45a-107">In .NET Core 2.2 and earlier versions, the runtime prefers loading OpenSSL 1.0.x over 1.1.x.</span></span> <span data-ttu-id="6f45a-108">이는 OpenSSL과 상호 작용을 위한 <xref:System.IntPtr> 및 <xref:System.Runtime.InteropServices.SafeHandle> 형식이 기본적으로 libcrypto.so.1.0.0 / libcrypto.so.1.0 / libcrypto.so.10에 사용된다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="6f45a-108">This means that the <xref:System.IntPtr> and <xref:System.Runtime.InteropServices.SafeHandle> types for interop with OpenSSL are used with libcrypto.so.1.0.0 / libcrypto.so.1.0 / libcrypto.so.10 by preference.</span></span>

<span data-ttu-id="6f45a-109">.Net Core 3.0부터 런타임은 OpenSSL 1.0.x보다 OpenSSL 1.1.x를 우선적으로 로드하므로 OpenSSL과 상호 작용을 위한 <xref:System.IntPtr> 및 <xref:System.Runtime.InteropServices.SafeHandle> 형식이 기본적으로 ibcrypto.so.1.1 / libcrypto.so.11 / libcrypto.so.1.1.0 / libcrypto.so.1.1.1에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f45a-109">Starting with .NET Core 3.0, the runtime prefers loading OpenSSL 1.1.x over OpenSSL 1.0.x, so the <xref:System.IntPtr> and <xref:System.Runtime.InteropServices.SafeHandle> types for interop with OpenSSL are used with libcrypto.so.1.1 / libcrypto.so.11 / libcrypto.so.1.1.0 / libcrypto.so.1.1.1 by preference.</span></span> <span data-ttu-id="6f45a-110">따라서 OpenSSL과 직접 상호 운용되는 라이브러리 및 애플리케이션은 .NET Core 2.1 또는 .NET Core 2.2에서 업그레이드할 경우 .NET Core에 노출된 값과 호환되지 않는 포인터를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f45a-110">As a result, libraries and applications that interoperate with OpenSSL directly may have incompatible pointers with the .NET Core-exposed values when upgrading from .NET Core 2.1 or .NET Core 2.2.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="6f45a-111">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="6f45a-111">Version introduced</span></span>

<span data-ttu-id="6f45a-112">3.0</span><span class="sxs-lookup"><span data-stu-id="6f45a-112">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6f45a-113">권장 작업</span><span class="sxs-lookup"><span data-stu-id="6f45a-113">Recommended action</span></span>

<span data-ttu-id="6f45a-114">OpenSSL을 사용하여 직접 작업을 수행하는 라이브러리 및 애플리케이션은 .NET Core 런타임과 동일한 버전의 OpenSSL을 사용하고 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f45a-114">Libraries and applications that do direct operations with OpenSSL need to be careful to ensure they are using the same version of OpenSSL as the .NET Core runtime.</span></span>

<span data-ttu-id="6f45a-115">OpenSSL을 사용하여 직접 .NET Core 암호화 형식에서 <xref:System.IntPtr> 또는 <xref:System.Runtime.InteropServices.SafeHandle> 값을 사용하는 모든 라이브러리 또는 애플리케이션은사용하는 라이브러리 버전을 새 <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> 속성과 비교하여 포인터가 호환되는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f45a-115">All libraries or applications that use <xref:System.IntPtr> or <xref:System.Runtime.InteropServices.SafeHandle> values from the .NET Core cryptographic types directly with OpenSSL should compare the version of the library they use with the new <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> property to ensure the pointers are compatible.</span></span>

#### <a name="category"></a><span data-ttu-id="6f45a-116">범주</span><span class="sxs-lookup"><span data-stu-id="6f45a-116">Category</span></span>

<span data-ttu-id="6f45a-117">암호화</span><span class="sxs-lookup"><span data-stu-id="6f45a-117">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6f45a-118">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="6f45a-118">Affected APIs</span></span>

- <xref:System.Security.Cryptography.SafeEvpPKeyHandle.%23ctor%2A?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor(System.IntPtr)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.RSAOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSAOpenSsl.%23ctor(System.IntPtr)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSAOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSAOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDsaOpenSsl.%23ctor(System.IntPtr)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDsaOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDsaOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl.%23ctor(System.IntPtr)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Handle?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Security.Cryptography.SafeEvpPKeyHandle.#ctor`
- `M:System.Security.Cryptography.RSAOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.RSAOpenSsl.#ctor(System.Security.Cryptography.SafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.RSAOpenSsl.DuplicateKeyHandle`
- `M:System.Security.Cryptography.DSAOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.DSAOpenSsl.#ctor(System.Security.Cryptography.SafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.DSAOpenSsl.DuplicateKeyHandle`
- `M:System.Security.Cryptography.ECDsaOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.ECDsaOpenSsl.#ctor(System.Security.CryptographySafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.ECDsaOpenSsl.DuplicateKeyHandle`
- `M:System.Security.Cryptography.ECDiffieHellmanOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.ECDiffieHellmanOpenSsl.#ctor(System.Security.Cryptography.SafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.ECDiffieHellmanOpenSsl.DuplicateKeyHandle`
- `P:System.Security.Cryptography.X509Certificates.X509Certificate.Handle`

-->

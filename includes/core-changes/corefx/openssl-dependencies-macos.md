---
ms.openlocfilehash: 8790637c31d503455eb8ba722cca827c2a24b7c9
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021461"
---
### <a name="openssl-versions-on-macos"></a><span data-ttu-id="56928-101">macOS의 OpenSSL 버전</span><span class="sxs-lookup"><span data-stu-id="56928-101">OpenSSL versions on macOS</span></span>

<span data-ttu-id="56928-102">macOS에서 .NET Core 3.0 이상 런타임은 이제 <xref:System.Security.Cryptography.AesCcm>, <xref:System.Security.Cryptography.AesGcm>, <xref:System.Security.Cryptography.DSAOpenSsl>, <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>, <xref:System.Security.Cryptography.ECDsaOpenSsl>, <xref:System.Security.Cryptography.RSAOpenSsl> 및 <xref:System.Security.Cryptography.SafeEvpPKeyHandle> 형식에 대해 OpenSSL 1.0.x 버전보다 OpenSSL 1.1.x 버전을 선호합니다.</span><span class="sxs-lookup"><span data-stu-id="56928-102">The .NET Core 3.0 and later runtimes on macOS now prefer OpenSSL 1.1.x versions to OpenSSL 1.0.x versions for the <xref:System.Security.Cryptography.AesCcm>, <xref:System.Security.Cryptography.AesGcm>, <xref:System.Security.Cryptography.DSAOpenSsl>, <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>, <xref:System.Security.Cryptography.ECDsaOpenSsl>, <xref:System.Security.Cryptography.RSAOpenSsl>, and <xref:System.Security.Cryptography.SafeEvpPKeyHandle> types.</span></span>

<span data-ttu-id="56928-103">.NET Core 2.1 런타임은 이제 OpenSSL 1.1.x 버전을 지원하지만 여전히 OpenSSL 1.0.x 버전을 선호합니다.</span><span class="sxs-lookup"><span data-stu-id="56928-103">The .NET Core 2.1 runtime now supports OpenSSL 1.1.x versions, but still prefers OpenSSL 1.0.x versions.</span></span>

#### <a name="change-description"></a><span data-ttu-id="56928-104">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="56928-104">Change description</span></span>

<span data-ttu-id="56928-105">이전에는 .NET Core 런타임이 macOS에서 OpenSSL과 상호 작용하는 형식에 대해 OpenSSL 1.0.x 버전을 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="56928-105">Previously, the .NET Core runtime used OpenSSL 1.0.x versions on macOS for types that interact with OpenSSL.</span></span> <span data-ttu-id="56928-106">최신 OpenSSL 1.0.x 버전인 OpenSSL 1.0.2는 이제 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56928-106">The most recent OpenSSL 1.0.x version, OpenSSL 1.0.2, is now out of support.</span></span> <span data-ttu-id="56928-107">지원되는 버전의 OpenSSL에 대해 OpenSSL을 사용하는 형식을 유지하기 위해 .NET Core 3.0 이상 런타임이 이제 macOS에서 최신 버전의 OpenSSL을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="56928-107">To keep types that use OpenSSL on supported versions of OpenSSL, the .NET Core 3.0 and later runtimes now use newer versions of OpenSSL on macOS.</span></span>

<span data-ttu-id="56928-108">이러한 변경을 통해 macOS에서 .NET Core 런타임에 대한 동작은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="56928-108">With this change, the behavior for the .NET Core runtimes on macOS is as follows:</span></span>

- <span data-ttu-id="56928-109">.NET Core 3.0 이상 버전 런타임은 OpenSSL 1.1.x 버전(사용 가능한 경우)을 사용하고 사용 가능한 1.1.x 버전이 없는 경우에만 OpenSSL 1.0.x 버전으로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="56928-109">The .NET Core 3.0 and later version runtimes use OpenSSL 1.1.x, if available, and fall back to OpenSSL 1.0.x only if there's no 1.1.x version available.</span></span>

  <span data-ttu-id="56928-110">사용자 지정 P/Invokes에 OpenSSL interop 형식을 사용하는 호출자의 경우 <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> 설명의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="56928-110">For callers that use the OpenSSL interop types with custom P/Invokes, follow the guidance in the <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> remarks.</span></span> <span data-ttu-id="56928-111"><xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion> 값을 확인하지 않으면 앱의 작동이 중단될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56928-111">Your app may crash if you don't check the <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion> value.</span></span>

- <span data-ttu-id="56928-112">.NET Core 2.1 런타임은 OpenSSL 1.0.x 버전(사용 가능한 경우)을 사용하고 사용 가능한 1.0.x 버전이 없는 경우 OpenSSL 1.1.x 버전으로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="56928-112">The .NET Core 2.1 runtime uses OpenSSL 1.0.x, if available, and falls back to OpenSSL 1.1.x if there's no 1.0.x version available.</span></span>

  <span data-ttu-id="56928-113">.NET Core 2.1에 <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> 속성이 없어 런타임에 신뢰성 있게 OpenSSL 버전을 확인할 수 없기 때문에 2.1 런타임은 이전 버전의 OpenSSL을 선호합니다.</span><span class="sxs-lookup"><span data-stu-id="56928-113">The 2.1 runtime prefers the earlier version of OpenSSL because the <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> property does not exist in .NET Core 2.1, so the OpenSSL version cannot be reliably determined at run time.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="56928-114">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="56928-114">Version introduced</span></span>

- <span data-ttu-id="56928-115">.NET Core 2.1.16</span><span class="sxs-lookup"><span data-stu-id="56928-115">.NET Core 2.1.16</span></span>
- <span data-ttu-id="56928-116">.NET Core 3.0.3</span><span class="sxs-lookup"><span data-stu-id="56928-116">.NET Core 3.0.3</span></span>
- <span data-ttu-id="56928-117">.NET Core 3.1.2</span><span class="sxs-lookup"><span data-stu-id="56928-117">.NET Core 3.1.2</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="56928-118">권장 조치</span><span class="sxs-lookup"><span data-stu-id="56928-118">Recommended action</span></span>

- <span data-ttu-id="56928-119">더 이상 필요하지 않으면 OpenSSL 1.0.2 버전을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="56928-119">Uninstall OpenSSL version 1.0.2 if it's no longer needed.</span></span>

- <span data-ttu-id="56928-120"><xref:System.Security.Cryptography.AesCcm>, <xref:System.Security.Cryptography.AesGcm>, <xref:System.Security.Cryptography.DSAOpenSsl>, <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>, <xref:System.Security.Cryptography.ECDsaOpenSsl>, <xref:System.Security.Cryptography.RSAOpenSsl> 또는 <xref:System.Security.Cryptography.SafeEvpPKeyHandle> 형식을 사용하는 경우 OpenSSL 1.1.x 버전을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="56928-120">Install OpenSSL 1.1.x if you use the <xref:System.Security.Cryptography.AesCcm>, <xref:System.Security.Cryptography.AesGcm>, <xref:System.Security.Cryptography.DSAOpenSsl>, <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>, <xref:System.Security.Cryptography.ECDsaOpenSsl>, <xref:System.Security.Cryptography.RSAOpenSsl>, or <xref:System.Security.Cryptography.SafeEvpPKeyHandle> types.</span></span>

- <span data-ttu-id="56928-121">사용자 지정 P/Invokes에 OpenSSL interop 형식을 사용하는 경우 <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> 설명의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="56928-121">If you use the OpenSSL interop types with custom P/Invokes, follow the guidance in the <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> remarks.</span></span>

#### <a name="category"></a><span data-ttu-id="56928-122">범주</span><span class="sxs-lookup"><span data-stu-id="56928-122">Category</span></span>

<span data-ttu-id="56928-123">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="56928-123">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="56928-124">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="56928-124">Affected APIs</span></span>

- <xref:System.Security.Cryptography.AesCcm?displayProperty=fullName>
- <xref:System.Security.Cryptography.AesGcm?displayProperty=fullName>
- <xref:System.Security.Cryptography.DSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDsaOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.RSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.SafeEvpPKeyHandle?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Security.Cryptography.AesCcm``
- `T:System.Security.Cryptography.AesGcm`
- `T:System.Security.Cryptography.DSAOpenSsl`
- `T:System.Security.Cryptography.ECDiffieHellmanOpenSsl`
- `T:System.Security.Cryptography.ECDsaOpenSsl`
- `T:System.Security.Cryptography.RSAOpenSsl`
- `T:System.Security.Cryptography.SafeEvpPKeyHandle`

-->

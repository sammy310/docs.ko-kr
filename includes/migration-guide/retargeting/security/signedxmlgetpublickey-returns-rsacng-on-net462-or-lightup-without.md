---
ms.openlocfilehash: 23e278d38d6904d8afe927e6b54c388d443e41f5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616094"
---
### <a name="signedxmlgetpublickey-returns-rsacng-on-net462-or-lightup-without-retargeting-change"></a><span data-ttu-id="cc830-101">SignedXml.GetPublicKey는 대상 변경 없이 net462(또는 lightup)에서 RSACng를 반환</span><span class="sxs-lookup"><span data-stu-id="cc830-101">SignedXml.GetPublicKey returns RSACng on net462 (or lightup) without retargeting change</span></span>

#### <a name="details"></a><span data-ttu-id="cc830-102">설명</span><span class="sxs-lookup"><span data-stu-id="cc830-102">Details</span></span>

<span data-ttu-id="cc830-103">.NET Framework 4.6.2부터는 <xref:System.Security.Cryptography.Xml.SignedXml.GetPublicKey%2A?displayProperty=nameWithType> 메서드에서 반환된 개체의 구체적인 형식이 CryptoServiceProvider 구현에서 Cng 구현으로 변경되었습니다(쿼크 사용 안 함).</span><span class="sxs-lookup"><span data-stu-id="cc830-103">Starting with the .NET Framework 4.6.2, the concrete type of the object returned by the <xref:System.Security.Cryptography.Xml.SignedXml.GetPublicKey%2A?displayProperty=nameWithType> method changed (without a quirk) from a CryptoServiceProvider implementation to a Cng implementation.</span></span> <span data-ttu-id="cc830-104">이는 구현이 `certificate.PublicKey.Key` 사용에서 <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey%2A?displayProperty=nameWithType>로 전달되는 내부 `certificate.GetAnyPublicKey` 사용으로 변경 되었기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="cc830-104">This is because the implementation changed from using `certificate.PublicKey.Key` to using the internal `certificate.GetAnyPublicKey` which forwards to <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey%2A?displayProperty=nameWithType>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="cc830-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="cc830-105">Suggestion</span></span>

<span data-ttu-id="cc830-106">.NET Framework 4.7.1에서 실행되는 앱부터는 앱 구성 파일의 [런타임](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 구성 스위치를 추가하여 .NET Framework 4.6.1 이전 버전에서 기본적으로 사용되는 CryptoServiceProvider 구현을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc830-106">Starting with apps running on the .NET Framework 4.7.1, you can use the CryptoServiceProvider implementation used by default in the .NET Framework 4.6.1 and earlier versions by adding the following configuration switch to the [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.Security.Cryptography.Xml.SignedXmlUseLegacyCertificatePrivateKey=true" />
```

| <span data-ttu-id="cc830-107">이름</span><span class="sxs-lookup"><span data-stu-id="cc830-107">Name</span></span>    | <span data-ttu-id="cc830-108">값</span><span class="sxs-lookup"><span data-stu-id="cc830-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="cc830-109">Scope</span><span class="sxs-lookup"><span data-stu-id="cc830-109">Scope</span></span>   | <span data-ttu-id="cc830-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="cc830-110">Edge</span></span>        |
| <span data-ttu-id="cc830-111">버전</span><span class="sxs-lookup"><span data-stu-id="cc830-111">Version</span></span> | <span data-ttu-id="cc830-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="cc830-112">4.6.2</span></span>       |
| <span data-ttu-id="cc830-113">형식</span><span class="sxs-lookup"><span data-stu-id="cc830-113">Type</span></span>    | <span data-ttu-id="cc830-114">대상 변경</span><span class="sxs-lookup"><span data-stu-id="cc830-114">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="cc830-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="cc830-115">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignatureReturningKey(System.Security.Cryptography.AsymmetricAlgorithm@)?displayProperty=nameWithType>

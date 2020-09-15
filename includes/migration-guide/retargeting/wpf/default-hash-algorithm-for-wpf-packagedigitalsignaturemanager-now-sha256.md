---
ms.openlocfilehash: d3e0a61601f60a389b662f6f74934b6e6dc6e663
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614918"
---
### <a name="the-default-hash-algorithm-for-wpf-packagedigitalsignaturemanager-is-now-sha256"></a><span data-ttu-id="d7d6f-101">WPF PackageDigitalSignatureManager의 기본 해시 알고리즘은 이제 SHA256입니다.</span><span class="sxs-lookup"><span data-stu-id="d7d6f-101">The default hash algorithm for WPF PackageDigitalSignatureManager is now SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="d7d6f-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="d7d6f-102">Details</span></span>

<span data-ttu-id="d7d6f-103">`System.IO.Packaging.PackageDigitalSignatureManager`는 WPF 패키지와 관련하여 디지털 서명을 위한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d7d6f-103">The `System.IO.Packaging.PackageDigitalSignatureManager` provides functionality for digital signatures in relation to WPF packages.</span></span>  <span data-ttu-id="d7d6f-104">.NET Framework 4.7 및 이전 버전에서 패키지 서명 부분에 사용되는 기본 알고리즘(<xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>)은 SHA1입니다.</span><span class="sxs-lookup"><span data-stu-id="d7d6f-104">In the .NET Framework 4.7 and earlier versions, the default algorithm (<xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>) used for signing parts of a package was SHA1.</span></span>  <span data-ttu-id="d7d6f-105">SHA1의 최근 보안 문제로 인해 이 기본값은 .NET Framework 4.7.1부터 SHA256으로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d7d6f-105">Due to recent security concerns with SHA1, this default has been changed to SHA256 starting with the .NET Framework 4.7.1.</span></span>  <span data-ttu-id="d7d6f-106">이 변경 내용은 XPS 문서를 포함한 모든 패키지 서명에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7d6f-106">This change affects all package signing, including XPS documents.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d7d6f-107">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="d7d6f-107">Suggestion</span></span>

<span data-ttu-id="d7d6f-108">.NET Framework 4.7.1 미만의 프레임워크 버전을 대상으로 하며 이 변경 내용을 활용하려는 개발자 또는 .NET Framework 4.7.1 이상을 대상으로 하며 이전 기능을 필요로 하는 개발자는 다음 AppContext 플래그를 적절하게 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7d6f-108">A developer who wants to utilize this change while targeting a framework version below .NET Framework 4.7.1 or a developer who requires the previous functionality while targeting .NET Framework 4.7.1 or greater can set the following AppContext flag appropriately.</span></span>  <span data-ttu-id="d7d6f-109">true 값을 지정하면 SHA1이 기본 알고리즘으로 사용됩니다. false를 지정하면 SHA256이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7d6f-109">A value of true will result in SHA1 being used as the default algorithm; false results in SHA256.</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.UseSha1AsDefaultHashAlgorithmForDigitalSignatures=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="d7d6f-110">이름</span><span class="sxs-lookup"><span data-stu-id="d7d6f-110">Name</span></span>    | <span data-ttu-id="d7d6f-111">값</span><span class="sxs-lookup"><span data-stu-id="d7d6f-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d7d6f-112">Scope</span><span class="sxs-lookup"><span data-stu-id="d7d6f-112">Scope</span></span>   | <span data-ttu-id="d7d6f-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d7d6f-113">Edge</span></span>        |
| <span data-ttu-id="d7d6f-114">버전</span><span class="sxs-lookup"><span data-stu-id="d7d6f-114">Version</span></span> | <span data-ttu-id="d7d6f-115">4.7.1</span><span class="sxs-lookup"><span data-stu-id="d7d6f-115">4.7.1</span></span>       |
| <span data-ttu-id="d7d6f-116">형식</span><span class="sxs-lookup"><span data-stu-id="d7d6f-116">Type</span></span>    | <span data-ttu-id="d7d6f-117">대상 변경</span><span class="sxs-lookup"><span data-stu-id="d7d6f-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="d7d6f-118">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="d7d6f-118">Affected APIs</span></span>

- <xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>

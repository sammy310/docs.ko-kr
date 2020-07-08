---
ms.openlocfilehash: acb5b467fc8f0692d8fa1b3b8263fd27308cc124
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617167"
---
### <a name="webutilityhtmlencode-and-webutilityhtmldecode-round-trip-bmp-correctly"></a><span data-ttu-id="19661-101">WebUtility.HtmlEncode 및 WebUtility.HtmlDecode가 BMP를 올바르게 라운드트립</span><span class="sxs-lookup"><span data-stu-id="19661-101">WebUtility.HtmlEncode and WebUtility.HtmlDecode round-trip BMP correctly</span></span>

#### <a name="details"></a><span data-ttu-id="19661-102">설명</span><span class="sxs-lookup"><span data-stu-id="19661-102">Details</span></span>

<span data-ttu-id="19661-103">.NET Framework 4.5를 대상으로 하는 애플리케이션의 경우 BMP(기본적인 다국어 문자표) 외의 문자는 <xref:System.Net.WebUtility.HtmlDecode(System.String)> 메서드에 전달될 때 올바르게 라운드트립합니다.</span><span class="sxs-lookup"><span data-stu-id="19661-103">For applications that target the .NET Framework 4.5, characters that are outside the Basic Multilingual Plane (BMP) round-trip correctly when they are passed to the <xref:System.Net.WebUtility.HtmlDecode(System.String)> methods.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="19661-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="19661-104">Suggestion</span></span>

<span data-ttu-id="19661-105">이 변경은 현재 애플리케이션에 영향을 주지 않지만, 원래의 동작을 복원하려면 `<httpRuntime>` 요소의 `targetFramework` 특성을 “4.5” 이외의 문자열로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="19661-105">This change should have no effect on current applications, but to restore the original behavior, set the `targetFramework` attribute of the `<httpRuntime>` element to a string other than "4.5".</span></span> <span data-ttu-id="19661-106">`unicodeEncodingConformance` 구성 요소의 `unicodeDecodingConformance` 및 `<webUtility>` 특성을 설정하여 대상 버전의 .NET Framework에 관계없이 이 동작을 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19661-106">You can also set the `unicodeEncodingConformance` and `unicodeDecodingConformance` attributes of the `<webUtility>` configuration element to control this behavior independently of the targeted version of the .NET Framework.</span></span>

| <span data-ttu-id="19661-107">이름</span><span class="sxs-lookup"><span data-stu-id="19661-107">Name</span></span>    | <span data-ttu-id="19661-108">값</span><span class="sxs-lookup"><span data-stu-id="19661-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="19661-109">Scope</span><span class="sxs-lookup"><span data-stu-id="19661-109">Scope</span></span>   | <span data-ttu-id="19661-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="19661-110">Edge</span></span>        |
| <span data-ttu-id="19661-111">버전</span><span class="sxs-lookup"><span data-stu-id="19661-111">Version</span></span> | <span data-ttu-id="19661-112">4.5</span><span class="sxs-lookup"><span data-stu-id="19661-112">4.5</span></span>         |
| <span data-ttu-id="19661-113">형식</span><span class="sxs-lookup"><span data-stu-id="19661-113">Type</span></span>    | <span data-ttu-id="19661-114">대상 변경</span><span class="sxs-lookup"><span data-stu-id="19661-114">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="19661-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="19661-115">Affected APIs</span></span>

- <xref:System.Net.WebUtility.HtmlEncode(System.String)?displayProperty=nameWithType>
- <xref:System.Net.WebUtility.HtmlEncode(System.String,System.IO.TextWriter)?displayProperty=nameWithType>

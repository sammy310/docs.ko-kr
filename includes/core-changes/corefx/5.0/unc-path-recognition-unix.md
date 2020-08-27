---
ms.openlocfilehash: 0246f325a6274082b7fb0d5590cec7c80687ae85
ms.sourcegitcommit: ef86c24c418439b8bb5e3e7d64bbdbe5e11c3e9c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2020
ms.locfileid: "88720202"
---
### <a name="uri-recognition-of-unc-paths-on-unix"></a><span data-ttu-id="f7381-101">Unix에서 UNC 경로의 URI 인식</span><span class="sxs-lookup"><span data-stu-id="f7381-101">Uri recognition of UNC paths on Unix</span></span>

<span data-ttu-id="f7381-102">이제 <xref:System.Uri> 클래스가 두 개의 슬래시(`//`)로 시작하는 문자열을 Unix 운영 체제의 UNC(범용 명명 규칙) 경로로 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-102">The <xref:System.Uri> class now recognizes strings that start with two forward slashes (`//`) as universal naming convention (UNC) paths on Unix operating systems.</span></span> <span data-ttu-id="f7381-103">이 변경으로 인해 모든 플랫폼에서 해당 문자열에 대해 일관된 동작이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-103">This change makes the behavior for such strings consistent across all platforms.</span></span>

#### <a name="change-description"></a><span data-ttu-id="f7381-104">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="f7381-104">Change description</span></span>

<span data-ttu-id="f7381-105">이전 버전의 .NET에서는 <xref:System.Uri> 클래스가 두 개의 슬래시로 시작하는 문자열(예: `//contoso`)을 Unix 운영 체제의 절대 파일 경로로 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-105">In previous versions of .NET, the <xref:System.Uri> class recognizes strings that start with with two forward slashes, for example, `//contoso`, as absolute file paths on Unix operating systems.</span></span> <span data-ttu-id="f7381-106">그러나 Windows에서는 해당 문자열이 UNC 경로로 인식됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-106">However, on Windows, such strings are recognized as UNC paths.</span></span>

<span data-ttu-id="f7381-107">.NET 5.0부터 <xref:System.Uri> 클래스는 Unix를 비롯한 모든 플랫폼에서 두 개의 슬래시로 시작하는 문자열을 UNC 경로로 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-107">Starting in .NET 5.0,  the <xref:System.Uri> class recognizes strings that start with with two forward slashes as UNC paths on all platforms, including Unix.</span></span> <span data-ttu-id="f7381-108">또한 속성이 UNC 의미 체계에 따라 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-108">In addition, properties behave according to UNC semantics:</span></span>

- <span data-ttu-id="f7381-109"><xref:System.Uri.IsUnc?displayProperty=nameWithType>가 `true`를 반환하는 경우</span><span class="sxs-lookup"><span data-stu-id="f7381-109"><xref:System.Uri.IsUnc?displayProperty=nameWithType> returns `true`.</span></span>
- <span data-ttu-id="f7381-110">경로의 백슬래시가 슬래시로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-110">Backslashes in the path are replaced with forward slashes.</span></span> <span data-ttu-id="f7381-111">예를 들어 `//first\second`는 `//first/second`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-111">For example, `//first\second` becomes `//first/second`.</span></span>
- <span data-ttu-id="f7381-112"><xref:System.Uri.LocalPath?displayProperty=nameWithType>이 문자를 백분율 인코딩하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-112"><xref:System.Uri.LocalPath?displayProperty=nameWithType> doesn't percent-encode characters.</span></span> <span data-ttu-id="f7381-113">예를 들어 `//first/\uFFF0`이 `//first/%EF%BF%B0`으로 변환되지 ‘않습니다’.</span><span class="sxs-lookup"><span data-stu-id="f7381-113">For example, `//first/\uFFF0` is *not* converted to `//first/%EF%BF%B0`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f7381-114">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="f7381-114">Version introduced</span></span>

<span data-ttu-id="f7381-115">5.0</span><span class="sxs-lookup"><span data-stu-id="f7381-115">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f7381-116">권장 조치</span><span class="sxs-lookup"><span data-stu-id="f7381-116">Recommended action</span></span>

<span data-ttu-id="f7381-117">개발자는 아무 작업도 수행하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7381-117">No action is required on the part of the developer.</span></span>

#### <a name="category"></a><span data-ttu-id="f7381-118">범주</span><span class="sxs-lookup"><span data-stu-id="f7381-118">Category</span></span>

<span data-ttu-id="f7381-119">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="f7381-119">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f7381-120">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="f7381-120">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Uri`

-->

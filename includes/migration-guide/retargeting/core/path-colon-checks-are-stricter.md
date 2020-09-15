---
ms.openlocfilehash: 6af63c0a58a3273aa98fa70f22e3637b481806b4
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496619"
---
### <a name="path-colon-checks-are-stricter"></a><span data-ttu-id="91049-101">경로 콜론 검사가 더욱 엄격해짐</span><span class="sxs-lookup"><span data-stu-id="91049-101">Path colon checks are stricter</span></span>

#### <a name="details"></a><span data-ttu-id="91049-102">설명</span><span class="sxs-lookup"><span data-stu-id="91049-102">Details</span></span>

<span data-ttu-id="91049-103">.NET Framework 4.6.2에서 이전에 지원되지 않던 경로(길이 및 형식 모두)를 지원하도록 여러 가지가 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="91049-103">In .NET Framework 4.6.2, a number of changes were made to support previously unsupported paths (both in length and format).</span></span> <span data-ttu-id="91049-104">적절한 드라이브 구분 기호(콜론) 구문에 대해 검사가 좀 더 정확해졌습니다. 이 구문은 이전에 허용되었던 일부 선택 경로 API에서 일부 URI 경로가 차단되는 부작용이 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="91049-104">Checks for proper drive separator (colon) syntax were made more correct, which had the side effect of blocking some URI paths in a few select Path APIs where they were previously tolerated.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="91049-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="91049-105">Suggestion</span></span>

<span data-ttu-id="91049-106">영향을 받는 API로 URI를 전달하는 경우 먼저 합법적인 경로가 되도록 문자열을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="91049-106">If passing a URI to affected APIs, modify the string to be a legal path first.</span></span>

- <span data-ttu-id="91049-107">URL에서 스키마를 수동으로 제거합니다(예: URL에서 `file://` 제거).</span><span class="sxs-lookup"><span data-stu-id="91049-107">Remove the scheme from URLs manually (for example, remove `file://` from URLs).</span></span>

- <span data-ttu-id="91049-108">URI를 <xref:System.Uri> 클래스에 전달하고 <xref:System.Uri.LocalPath>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="91049-108">Pass the URI to the <xref:System.Uri> class and use <xref:System.Uri.LocalPath>.</span></span>

<span data-ttu-id="91049-109">또는 `Switch.System.IO.UseLegacyPathHandling` AppContext 스위치를 `true`로 설정하여 새 경로 정규화를 옵트아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="91049-109">Alternatively, you can opt out of the new path normalization by setting the `Switch.System.IO.UseLegacyPathHandling` AppContext switch to `true`.</span></span>

| <span data-ttu-id="91049-110">이름</span><span class="sxs-lookup"><span data-stu-id="91049-110">Name</span></span>    | <span data-ttu-id="91049-111">값</span><span class="sxs-lookup"><span data-stu-id="91049-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="91049-112">Scope</span><span class="sxs-lookup"><span data-stu-id="91049-112">Scope</span></span>   | <span data-ttu-id="91049-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="91049-113">Edge</span></span>        |
| <span data-ttu-id="91049-114">버전</span><span class="sxs-lookup"><span data-stu-id="91049-114">Version</span></span> | <span data-ttu-id="91049-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="91049-115">4.6.2</span></span>       |
| <span data-ttu-id="91049-116">형식</span><span class="sxs-lookup"><span data-stu-id="91049-116">Type</span></span>    | <span data-ttu-id="91049-117">대상 변경</span><span class="sxs-lookup"><span data-stu-id="91049-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="91049-118">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="91049-118">Affected APIs</span></span>

- <xref:System.IO.Path.GetDirectoryName(System.String)?displayProperty=nameWithType>
- <xref:System.IO.Path.GetPathRoot(System.String)?displayProperty=nameWithType>

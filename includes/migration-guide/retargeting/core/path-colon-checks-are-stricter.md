---
ms.openlocfilehash: 3e4a5936bbac4e77efc5f7e68b55ddf49bae5d43
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614719"
---
### <a name="path-colon-checks-are-stricter"></a><span data-ttu-id="c017e-101">경로 콜론 검사가 더욱 엄격해짐</span><span class="sxs-lookup"><span data-stu-id="c017e-101">Path colon checks are stricter</span></span>

#### <a name="details"></a><span data-ttu-id="c017e-102">설명</span><span class="sxs-lookup"><span data-stu-id="c017e-102">Details</span></span>

<span data-ttu-id="c017e-103">.NET Framework 4.6.2에서 이전에 지원되지 않던 경로(길이 및 형식 모두)를 지원하도록 여러 가지가 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c017e-103">In .NET Framework 4.6.2, a number of changes were made to support previously unsupported paths (both in length and format).</span></span> <span data-ttu-id="c017e-104">적절한 드라이브 구분 기호(콜론) 구문에 대해 검사가 좀 더 정확해졌습니다. 이 구문은 허용되었던 일부 선택 경로 API에서 일부 URI 경로가 차단되는 부작용이 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="c017e-104">Checks for proper drive separator (colon) syntax were made more correct, which had the side effect of blocking some URI paths in a few select Path APIs where they used to be tolerated.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c017e-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="c017e-105">Suggestion</span></span>

<span data-ttu-id="c017e-106">영향을 받는 API로 URI를 전달하는 경우 먼저 합법적인 경로가 되도록 문자열을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="c017e-106">If passing a URI to affected APIs, modify the string to be a legal path first.</span></span><ul><li><span data-ttu-id="c017e-107">URL에서 스키마를 수동으로 제거합니다(예: URL에서 `file://` 제거).</span><span class="sxs-lookup"><span data-stu-id="c017e-107">Remove the scheme from URLs manually (e.g. remove `file://` from URLs)</span></span>

- <span data-ttu-id="c017e-108">URI를 <xref:System.Uri> 클래스에 전달하고 <xref:System.Uri.LocalPath>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c017e-108">Pass the URI to the <xref:System.Uri> class and use <xref:System.Uri.LocalPath></span></span>

<span data-ttu-id="c017e-109">또는 `Switch.System.IO.UseLegacyPathHandling` AppContext 스위치를 true로 설정하여 새 경로 정규화를 옵트아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="c017e-109">Alternatively, you can opt out of the new path normalization by setting the `Switch.System.IO.UseLegacyPathHandling` AppContext switch to true.</span></span>

| <span data-ttu-id="c017e-110">이름</span><span class="sxs-lookup"><span data-stu-id="c017e-110">Name</span></span>    | <span data-ttu-id="c017e-111">값</span><span class="sxs-lookup"><span data-stu-id="c017e-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c017e-112">Scope</span><span class="sxs-lookup"><span data-stu-id="c017e-112">Scope</span></span>   | <span data-ttu-id="c017e-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c017e-113">Edge</span></span>        |
| <span data-ttu-id="c017e-114">버전</span><span class="sxs-lookup"><span data-stu-id="c017e-114">Version</span></span> | <span data-ttu-id="c017e-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="c017e-115">4.6.2</span></span>       |
| <span data-ttu-id="c017e-116">형식</span><span class="sxs-lookup"><span data-stu-id="c017e-116">Type</span></span>    | <span data-ttu-id="c017e-117">대상 변경</span><span class="sxs-lookup"><span data-stu-id="c017e-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="c017e-118">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="c017e-118">Affected APIs</span></span>

- <xref:System.IO.Path.GetDirectoryName(System.String)?displayProperty=nameWithType>
- <xref:System.IO.Path.GetPathRoot(System.String)?displayProperty=nameWithType>

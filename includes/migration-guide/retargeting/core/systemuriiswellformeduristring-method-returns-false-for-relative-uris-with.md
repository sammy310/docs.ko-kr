---
ms.openlocfilehash: f7dcf9c4c3dc7ea536ddc847769a1a30f1298bb2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617212"
---
### <a name="systemuriiswellformeduristring-method-returns-false-for-relative-uris-with-a-colon-char-in-first-segment"></a><span data-ttu-id="53bde-101">첫 번째 세그먼트에 콜론 문자가 있는 상대 URI에 대해 System.Uri.IsWellFormedUriString 메서드가 false를 반환</span><span class="sxs-lookup"><span data-stu-id="53bde-101">System.Uri.IsWellFormedUriString method returns false for relative URIs with a colon char in first segment</span></span>

#### <a name="details"></a><span data-ttu-id="53bde-102">설명</span><span class="sxs-lookup"><span data-stu-id="53bde-102">Details</span></span>

<span data-ttu-id="53bde-103">.NET Framework 4.5부터 <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)>은 첫 번째 세그먼트에서 `:`가 있는 상대 URI가 잘 형성되지 않은 것으로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="53bde-103">Beginning with the .NET Framework 4.5, <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)> will treat relative URIs with a `:` in their first segment as not well formed.</span></span> <span data-ttu-id="53bde-104">이는 RFC3986을 준수하도록 만들어진 .NET Framework 4.0의 <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName> 동작의 변경입니다.</span><span class="sxs-lookup"><span data-stu-id="53bde-104">This is a change from <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName> behavior in the .NET Framework 4.0 that was made to conform to RFC3986.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="53bde-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="53bde-105">Suggestion</span></span>

<span data-ttu-id="53bde-106">이 변경(다른 많은 URI 변경과 마찬가지)은 .NET Framework 4.5(또는 그 이상)를 대상으로 하는 애플리케이션에만 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="53bde-106">This change (like many other URI changes) will only affect applications targeting the .NET Framework 4.5 (or later).</span></span> <span data-ttu-id="53bde-107">이전 동작을 계속 사용하려면 .NET Framework 4.0에 대해 앱을 대상으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="53bde-107">To keep using the old behavior, target the app against the .NET Framework 4.0.</span></span> <span data-ttu-id="53bde-108">또는 이전 동작이 바람직한 경우 <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName>을 호출하기 전에 URI를 검사하여 유효성 검사를 위해 제거하려는 `:` 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="53bde-108">Alternatively, scan URI's prior to calling <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName> looking for `:` characters that you may want to remove for validation purposes, if the old behavior is desirable.</span></span>

| <span data-ttu-id="53bde-109">이름</span><span class="sxs-lookup"><span data-stu-id="53bde-109">Name</span></span>    | <span data-ttu-id="53bde-110">값</span><span class="sxs-lookup"><span data-stu-id="53bde-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="53bde-111">Scope</span><span class="sxs-lookup"><span data-stu-id="53bde-111">Scope</span></span>   | <span data-ttu-id="53bde-112">부</span><span class="sxs-lookup"><span data-stu-id="53bde-112">Minor</span></span>       |
| <span data-ttu-id="53bde-113">버전</span><span class="sxs-lookup"><span data-stu-id="53bde-113">Version</span></span> | <span data-ttu-id="53bde-114">4.5</span><span class="sxs-lookup"><span data-stu-id="53bde-114">4.5</span></span>         |
| <span data-ttu-id="53bde-115">형식</span><span class="sxs-lookup"><span data-stu-id="53bde-115">Type</span></span>    | <span data-ttu-id="53bde-116">대상 변경</span><span class="sxs-lookup"><span data-stu-id="53bde-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="53bde-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="53bde-117">Affected APIs</span></span>

- <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=nameWithType>

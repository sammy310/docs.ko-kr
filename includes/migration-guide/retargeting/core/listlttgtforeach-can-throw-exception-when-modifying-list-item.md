---
ms.openlocfilehash: 3300a74b81fc9eeba670ee0ceb2c2615fd3925bd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617221"
---
### <a name="listlttgtforeach-can-throw-exception-when-modifying-list-item"></a><span data-ttu-id="35b90-101">List&lt;T&gt;.ForEach는 목록 항목을 수정할 때 예외를 throw할 수 있음</span><span class="sxs-lookup"><span data-stu-id="35b90-101">List&lt;T&gt;.ForEach can throw exception when modifying list item</span></span>

#### <a name="details"></a><span data-ttu-id="35b90-102">설명</span><span class="sxs-lookup"><span data-stu-id="35b90-102">Details</span></span>

<span data-ttu-id="35b90-103">.NET Framework 4.5부터는 호출 컬렉션의 요소가 수정되면 <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> 열거자가 <xref:System.InvalidOperationException?displayProperty=fullName> 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="35b90-103">Beginning in .NET Framework 4.5, a <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> enumerator will throw an <xref:System.InvalidOperationException?displayProperty=fullName> exception if an element in the calling collection is modified.</span></span> <span data-ttu-id="35b90-104">이전에는 예외를 throw하지 않고 경합 상태가 발생할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="35b90-104">Previously, this would not throw an exception but could lead to race conditions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="35b90-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="35b90-105">Suggestion</span></span>

<span data-ttu-id="35b90-106">이상적으로, 안전한 작업을 위해 요소를 열거하는 동안 목록을 수정하지 않도록 코드를 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35b90-106">Ideally, code should be fixed to not modify lists while enumerating their elements because that is never a safe operation.</span></span> <span data-ttu-id="35b90-107">그러나 이전 동작으로 되돌리려면 응용 프로그램이 .NET Framework 4.0을 대상으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35b90-107">To revert to the previous behavior, though, an app may target .NET Framework 4.0.</span></span>

| <span data-ttu-id="35b90-108">이름</span><span class="sxs-lookup"><span data-stu-id="35b90-108">Name</span></span>    | <span data-ttu-id="35b90-109">값</span><span class="sxs-lookup"><span data-stu-id="35b90-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="35b90-110">Scope</span><span class="sxs-lookup"><span data-stu-id="35b90-110">Scope</span></span>   | <span data-ttu-id="35b90-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="35b90-111">Edge</span></span>        |
| <span data-ttu-id="35b90-112">버전</span><span class="sxs-lookup"><span data-stu-id="35b90-112">Version</span></span> | <span data-ttu-id="35b90-113">4.5</span><span class="sxs-lookup"><span data-stu-id="35b90-113">4.5</span></span>         |
| <span data-ttu-id="35b90-114">형식</span><span class="sxs-lookup"><span data-stu-id="35b90-114">Type</span></span>    | <span data-ttu-id="35b90-115">대상 변경</span><span class="sxs-lookup"><span data-stu-id="35b90-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="35b90-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="35b90-116">Affected APIs</span></span>

- <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})?displayProperty=nameWithType>

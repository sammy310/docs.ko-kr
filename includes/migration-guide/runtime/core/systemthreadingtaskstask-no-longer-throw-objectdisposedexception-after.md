---
ms.openlocfilehash: 58dbb54d42d89b450134758072e3133ae4e6b13d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496734"
---
### <a name="systemthreadingtaskstask-no-longer-throw-objectdisposedexception-after-object-is-disposed"></a><span data-ttu-id="74f89-101">개체를 삭제한 후 System.Threading.Tasks.Task는 더 이상 ObjectDisposedException을 throw하지 않습니다</span><span class="sxs-lookup"><span data-stu-id="74f89-101">System.Threading.Tasks.Task no longer throw ObjectDisposedException after object is disposed</span></span>

#### <a name="details"></a><span data-ttu-id="74f89-102">설명</span><span class="sxs-lookup"><span data-stu-id="74f89-102">Details</span></span>

<span data-ttu-id="74f89-103"><xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle>을 제외하고, <xref:System.Threading.Tasks.Task?displayProperty=fullName> 메서드는 개체가 삭제된 후에 <xref:System.ObjectDisposedException?displayProperty=fullName> 예외를 더 이상 throw하지 않습니다. 이 변경은 캐시된 작업의 사용을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="74f89-103">Except for <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle>, <xref:System.Threading.Tasks.Task?displayProperty=fullName> methods no longer throw an <xref:System.ObjectDisposedException?displayProperty=fullName> exception after the object is disposed.This change supports the use of cached tasks.</span></span> <span data-ttu-id="74f89-104">예를 들어, 메서드는 새로운 작업을 할당하는 대신에 이미 완료된 작업을 나타내기 위해 캐시된 작업을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74f89-104">For example, a method can return a cached task to represent an already completed operation instead of allocating a new task.</span></span> <span data-ttu-id="74f89-105">작업의 모든 소비자는 다시 사용할 수 없게 렌더링된 작업을 삭제할 수 있었기 때문에 이전 .NET Framework 버전에서는 이것이 불가능했습니다.</span><span class="sxs-lookup"><span data-stu-id="74f89-105">This was impossible in previous .NET Framework versions, because any consumer of the task could dispose of it, which rendered it unusable.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="74f89-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="74f89-106">Suggestion</span></span>

<span data-ttu-id="74f89-107">작업 메서드는 개체가 삭제되는 경우에 <xref:System.ObjectDisposedException?displayProperty=fullName>을 더 이상 throw하지 않는다는 것을 기억하세요.</span><span class="sxs-lookup"><span data-stu-id="74f89-107">Be aware that Task methods may no longer throw <xref:System.ObjectDisposedException?displayProperty=fullName> in cases when the object is disposed.</span></span> <span data-ttu-id="74f89-108">앱이 작업이 삭제되었는지 알도록 이 예외에 종속된 경우 <xref:System.Threading.Tasks.Task.Status>를 사용하여 작업의 상태를 명시적으로 확인하도록 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74f89-108">If an app was depending on this exception to know that a task was disposed, it should be updated to explicitly check the task's status using <xref:System.Threading.Tasks.Task.Status>.</span></span>

| <span data-ttu-id="74f89-109">이름</span><span class="sxs-lookup"><span data-stu-id="74f89-109">Name</span></span>    | <span data-ttu-id="74f89-110">값</span><span class="sxs-lookup"><span data-stu-id="74f89-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="74f89-111">Scope</span><span class="sxs-lookup"><span data-stu-id="74f89-111">Scope</span></span>   |<span data-ttu-id="74f89-112">부</span><span class="sxs-lookup"><span data-stu-id="74f89-112">Minor</span></span>|
|<span data-ttu-id="74f89-113">버전</span><span class="sxs-lookup"><span data-stu-id="74f89-113">Version</span></span>|<span data-ttu-id="74f89-114">4.5</span><span class="sxs-lookup"><span data-stu-id="74f89-114">4.5</span></span>|
|<span data-ttu-id="74f89-115">형식</span><span class="sxs-lookup"><span data-stu-id="74f89-115">Type</span></span>|<span data-ttu-id="74f89-116">런타임</span><span class="sxs-lookup"><span data-stu-id="74f89-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="74f89-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="74f89-117">Affected APIs</span></span>

<span data-ttu-id="74f89-118">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74f89-118">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->

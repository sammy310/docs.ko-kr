---
ms.openlocfilehash: c557f1cb65a675446bc77c57ef91972df92712bb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617158"
---
### <a name="iasyncresultcompletedsynchronously-property-must-be-correct-for-the-resulting-task-to-complete"></a><span data-ttu-id="8c199-101">결과 작업을 완료하려면 IAsyncResult.CompletedSynchronously 속성이 정확해야 함</span><span class="sxs-lookup"><span data-stu-id="8c199-101">IAsyncResult.CompletedSynchronously property must be correct for the resulting task to complete</span></span>

#### <a name="details"></a><span data-ttu-id="8c199-102">설명</span><span class="sxs-lookup"><span data-stu-id="8c199-102">Details</span></span>

<span data-ttu-id="8c199-103">TaskFactory.FromAsync를 호출할 때 <xref:System.IAsyncResult.CompletedSynchronously> 속성이 올바르게 구현되어야 결과 작업을 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c199-103">When calling TaskFactory.FromAsync, the implementation of the <xref:System.IAsyncResult.CompletedSynchronously> property must be correct for the resulting task to complete.</span></span> <span data-ttu-id="8c199-104">즉, 이 속성은 구현이 동기적으로 완료된 경우에만 true를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c199-104">That is, the property must return true if, and only if, the implementation completed synchronously.</span></span> <span data-ttu-id="8c199-105">이전에는 이 속성이 선택되어 있지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="8c199-105">Previously, the property was not checked.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8c199-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="8c199-106">Suggestion</span></span>

<span data-ttu-id="8c199-107"><xref:System.IAsyncResult?displayProperty=fullName> 구현이 작업이 동기적으로 완료된 경우에만 <xref:System.IAsyncResult.CompletedSynchronously?displayProperty=fullName> 속성에 대해 true를 반환한다면, 중단이 관찰되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8c199-107">If <xref:System.IAsyncResult?displayProperty=fullName> implementations correctly return true for the <xref:System.IAsyncResult.CompletedSynchronously?displayProperty=fullName> property only when a task completed synchronously, then no break will be observed.</span></span> <span data-ttu-id="8c199-108">사용자는 소유하고 있는 <xref:System.IAsyncResult?displayProperty=fullName> 구현(소유한 경우)을 검토하여 작업의 동기적 완료 여부를 올바르게 평가하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c199-108">Users should review <xref:System.IAsyncResult?displayProperty=fullName> implementations they own (if any) to ensure that they correctly evaluate whether a task completed synchronously or not.</span></span>

| <span data-ttu-id="8c199-109">이름</span><span class="sxs-lookup"><span data-stu-id="8c199-109">Name</span></span>    | <span data-ttu-id="8c199-110">값</span><span class="sxs-lookup"><span data-stu-id="8c199-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8c199-111">Scope</span><span class="sxs-lookup"><span data-stu-id="8c199-111">Scope</span></span>   | <span data-ttu-id="8c199-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8c199-112">Edge</span></span>        |
| <span data-ttu-id="8c199-113">버전</span><span class="sxs-lookup"><span data-stu-id="8c199-113">Version</span></span> | <span data-ttu-id="8c199-114">4.5</span><span class="sxs-lookup"><span data-stu-id="8c199-114">4.5</span></span>         |
| <span data-ttu-id="8c199-115">형식</span><span class="sxs-lookup"><span data-stu-id="8c199-115">Type</span></span>    | <span data-ttu-id="8c199-116">대상 변경</span><span class="sxs-lookup"><span data-stu-id="8c199-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="8c199-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="8c199-117">Affected APIs</span></span>

- <xref:System.Threading.Tasks.TaskFactory.FromAsync(System.IAsyncResult,System.Action{System.IAsyncResult})?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync(System.IAsyncResult,System.Action{System.IAsyncResult},System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync(System.IAsyncResult,System.Action{System.IAsyncResult},System.Threading.Tasks.TaskCreationOptions,System.Threading.Tasks.TaskScheduler)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601(System.IAsyncResult,System.Func{System.IAsyncResult,%60%600})?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync(System.Func{System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync(System.Func{System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601(System.Func{%60%600,System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},%60%600,System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601(System.Func{%60%600,System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},%60%600,System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601(System.Func{System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%600},System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601(System.Func{System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%600},System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601(System.IAsyncResult,System.Func{System.IAsyncResult,%60%600},System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%601(System.IAsyncResult,System.Func{System.IAsyncResult,%60%600},System.Threading.Tasks.TaskCreationOptions,System.Threading.Tasks.TaskScheduler)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602(System.Func{%60%600,%60%601,System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},%60%600,%60%601,System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602(System.Func{%60%600,%60%601,System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},%60%600,%60%601,System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602(System.Func{%60%600,System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%601},%60%600,System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%602(System.Func{%60%600,System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%601},%60%600,System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603(System.Func{%60%600,%60%601,System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%602},%60%600,%60%601,System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603(System.Func{%60%600,%60%601,%60%602,System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},%60%600,%60%601,%60%602,System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603(System.Func{%60%600,%60%601,%60%602,System.AsyncCallback,System.Object,System.IAsyncResult},System.Action{System.IAsyncResult},%60%600,%60%601,%60%602,System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%603(System.Func{%60%600,%60%601,System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%602},%60%600,%60%601,System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%604(System.Func{%60%600,%60%601,%60%602,System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%603},%60%600,%60%601,%60%602,System.Object)?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskFactory.FromAsync%60%604(System.Func{%60%600,%60%601,%60%602,System.AsyncCallback,System.Object,System.IAsyncResult},System.Func{System.IAsyncResult,%60%603},%60%600,%60%601,%60%602,System.Object,System.Threading.Tasks.TaskCreationOptions)?displayProperty=nameWithType>

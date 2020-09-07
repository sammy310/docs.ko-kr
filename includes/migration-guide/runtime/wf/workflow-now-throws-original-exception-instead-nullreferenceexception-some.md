---
ms.openlocfilehash: 61d5885c19e39b138090c1a98fa26348724893c5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497526"
---
### <a name="workflow-now-throws-original-exception-instead-of-nullreferenceexception-in-some-cases"></a><span data-ttu-id="db1ff-101">일부 경우에 워크플로가 이제 NullReferenceException 대신 원래 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="db1ff-101">Workflow now throws original exception instead of NullReferenceException in some cases</span></span>

#### <a name="details"></a><span data-ttu-id="db1ff-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="db1ff-102">Details</span></span>

<span data-ttu-id="db1ff-103">.NET Framework 4.6.2 및 이전 버전에서 워크플로 작업의 Execute 메서드가 <xref:System.Exception.Message> 속성에 대한 <code>null</code> 값을 가진 예외를 throw하면 System.Activities 워크플로 런타임은 <xref:System.NullReferenceException?displayProperty=fullName>을 throw하여 원래 예외를 마스킹합니다. .NET Framework 4.7에서는 이전에 마스크된 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="db1ff-103">In the .NET Framework 4.6.2 and earlier versions, when the Execute method of a workflow activity throws an exception with a <code>null</code> value for the <xref:System.Exception.Message> property, the System.Activities Workflow runtime throws a <xref:System.NullReferenceException?displayProperty=fullName>, masking the original exception.In the .NET Framework 4.7, the previously masked exception is thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="db1ff-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="db1ff-104">Suggestion</span></span>

<span data-ttu-id="db1ff-105">코드가 <xref:System.NullReferenceException?displayProperty=fullName> 처리에 의존하는 경우 사용자 지정 작업에서 throw될 수 있는 예외를 catch하도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="db1ff-105">If your code relies on handling the <xref:System.NullReferenceException?displayProperty=fullName>, change it to catch the exceptions that could be thrown from your custom activities.</span></span>

| <span data-ttu-id="db1ff-106">Name</span><span class="sxs-lookup"><span data-stu-id="db1ff-106">Name</span></span>    | <span data-ttu-id="db1ff-107">값</span><span class="sxs-lookup"><span data-stu-id="db1ff-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="db1ff-108">Scope</span><span class="sxs-lookup"><span data-stu-id="db1ff-108">Scope</span></span>   |<span data-ttu-id="db1ff-109">부</span><span class="sxs-lookup"><span data-stu-id="db1ff-109">Minor</span></span>|
|<span data-ttu-id="db1ff-110">버전</span><span class="sxs-lookup"><span data-stu-id="db1ff-110">Version</span></span>|<span data-ttu-id="db1ff-111">4.7</span><span class="sxs-lookup"><span data-stu-id="db1ff-111">4.7</span></span>|
|<span data-ttu-id="db1ff-112">형식</span><span class="sxs-lookup"><span data-stu-id="db1ff-112">Type</span></span>|<span data-ttu-id="db1ff-113">런타임</span><span class="sxs-lookup"><span data-stu-id="db1ff-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="db1ff-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="db1ff-114">Affected APIs</span></span>

- <xref:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)?displayProperty=nameWithType>
- <xref:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType>
- <xref:System.Activities.AsyncCodeActivity%601.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType>
- <xref:System.Activities.WorkflowInvoker.Invoke?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)`
- `M:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)`
- ``M:System.Activities.AsyncCodeActivity`1.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)``
- `M:System.Activities.WorkflowInvoker.Invoke`

-->

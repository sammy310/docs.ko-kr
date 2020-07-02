---
ms.openlocfilehash: ae0c7322b7415157838278b5568e6e49936e9a93
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621242"
---
### <a name="workflow-now-throws-original-exception-instead-of-nullreferenceexception-in-some-cases"></a><span data-ttu-id="c852e-101">일부 경우에 워크플로가 이제 NullReferenceException 대신 원래 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="c852e-101">Workflow now throws original exception instead of NullReferenceException in some cases</span></span>

#### <a name="details"></a><span data-ttu-id="c852e-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="c852e-102">Details</span></span>

<span data-ttu-id="c852e-103">.NET Framework 4.6.2 및 이전 버전에서 워크플로 작업의 Execute 메서드가 <xref:System.Exception.Message> 속성에 대한 <code>null</code> 값을 가진 예외를 throw하면 System.Activities 워크플로 런타임은 <xref:System.NullReferenceException?displayProperty=fullName>을 throw하여 원래 예외를 마스킹합니다. .NET Framework 4.7에서는 이전에 마스크된 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="c852e-103">In the .NET Framework 4.6.2 and earlier versions, when the Execute method of a workflow activity throws an exception with a <code>null</code> value for the <xref:System.Exception.Message> property, the System.Activities Workflow runtime throws a <xref:System.NullReferenceException?displayProperty=fullName>, masking the original exception.In the .NET Framework 4.7, the previously masked exception is thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c852e-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="c852e-104">Suggestion</span></span>

<span data-ttu-id="c852e-105">코드가 <xref:System.NullReferenceException?displayProperty=fullName> 처리에 의존하는 경우 사용자 지정 작업에서 throw될 수 있는 예외를 catch하도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="c852e-105">If your code relies on handling the <xref:System.NullReferenceException?displayProperty=fullName>, change it to catch the exceptions that could be thrown from your custom activities.</span></span>

| <span data-ttu-id="c852e-106">이름</span><span class="sxs-lookup"><span data-stu-id="c852e-106">Name</span></span>    | <span data-ttu-id="c852e-107">값</span><span class="sxs-lookup"><span data-stu-id="c852e-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c852e-108">Scope</span><span class="sxs-lookup"><span data-stu-id="c852e-108">Scope</span></span>   |<span data-ttu-id="c852e-109">부</span><span class="sxs-lookup"><span data-stu-id="c852e-109">Minor</span></span>|
|<span data-ttu-id="c852e-110">버전</span><span class="sxs-lookup"><span data-stu-id="c852e-110">Version</span></span>|<span data-ttu-id="c852e-111">4.7</span><span class="sxs-lookup"><span data-stu-id="c852e-111">4.7</span></span>|
|<span data-ttu-id="c852e-112">형식</span><span class="sxs-lookup"><span data-stu-id="c852e-112">Type</span></span>|<span data-ttu-id="c852e-113">런타임</span><span class="sxs-lookup"><span data-stu-id="c852e-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c852e-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="c852e-114">Affected APIs</span></span>

-<xref:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity%601.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.WorkflowInvoker.Invoke?displayProperty=nameWithType></li></ul>|

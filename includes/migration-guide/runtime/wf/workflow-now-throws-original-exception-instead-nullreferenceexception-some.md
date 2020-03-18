---
ms.openlocfilehash: 470fc2ddcfbb29a677cadb6e7e1d2e55784d7ac2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802489"
---
### <a name="workflow-now-throws-original-exception-instead-of-nullreferenceexception-in-some-cases"></a><span data-ttu-id="05ed2-101">일부 경우에 워크플로가 이제 NullReferenceException 대신 원래 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="05ed2-101">Workflow now throws original exception instead of NullReferenceException in some cases</span></span>

|   |   |
|---|---|
|<span data-ttu-id="05ed2-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="05ed2-102">Details</span></span>|<span data-ttu-id="05ed2-103">.NET Framework 4.6.2 및 이전 버전에서 워크플로 작업의 Execute 메서드가 <code>null</code> 속성에 대한 <xref:System.Exception.Message> 값을 가진 예외를 throw하면 System.Activities 워크플로 런타임은 <xref:System.NullReferenceException?displayProperty=name>을 throw하여 원래 예외를 마스킹합니다. .NET Framework 4.7에서는 이전에 마스크된 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="05ed2-103">In the .NET Framework 4.6.2 and earlier versions, when the Execute method of a workflow activity throws an exception with a <code>null</code> value for the <xref:System.Exception.Message> property, the System.Activities Workflow runtime throws a <xref:System.NullReferenceException?displayProperty=name>, masking the original exception.In the .NET Framework 4.7, the previously masked exception is thrown.</span></span>|
|<span data-ttu-id="05ed2-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="05ed2-104">Suggestion</span></span>|<span data-ttu-id="05ed2-105">코드가 <xref:System.NullReferenceException?displayProperty=name> 처리에 의존하는 경우 사용자 지정 작업에서 throw될 수 있는 예외를 catch하도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="05ed2-105">If your code relies on handling the <xref:System.NullReferenceException?displayProperty=name>, change it to catch the exceptions that could be thrown from your custom activities.</span></span>|
|<span data-ttu-id="05ed2-106">범위</span><span class="sxs-lookup"><span data-stu-id="05ed2-106">Scope</span></span>|<span data-ttu-id="05ed2-107">사소함</span><span class="sxs-lookup"><span data-stu-id="05ed2-107">Minor</span></span>|
|<span data-ttu-id="05ed2-108">Version</span><span class="sxs-lookup"><span data-stu-id="05ed2-108">Version</span></span>|<span data-ttu-id="05ed2-109">4.7</span><span class="sxs-lookup"><span data-stu-id="05ed2-109">4.7</span></span>|
|<span data-ttu-id="05ed2-110">형식</span><span class="sxs-lookup"><span data-stu-id="05ed2-110">Type</span></span>|<span data-ttu-id="05ed2-111">런타임</span><span class="sxs-lookup"><span data-stu-id="05ed2-111">Runtime</span></span>|
|<span data-ttu-id="05ed2-112">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="05ed2-112">Affected APIs</span></span>|<ul><li><xref:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity%601.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.WorkflowInvoker.Invoke?displayProperty=nameWithType></li></ul>|

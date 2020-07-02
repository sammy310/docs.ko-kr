---
ms.openlocfilehash: ddc98448101c65003001ad05e67f29d75d99ad44
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616089"
---
### <a name="workflowdesignerload-doesnt-remove-symbol-property"></a><span data-ttu-id="9fc28-101">WorkflowDesigner.Load가 기호 속성을 제거하지 않음</span><span class="sxs-lookup"><span data-stu-id="9fc28-101">WorkflowDesigner.Load doesn't remove symbol property</span></span>

#### <a name="details"></a><span data-ttu-id="9fc28-102">설명</span><span class="sxs-lookup"><span data-stu-id="9fc28-102">Details</span></span>

<span data-ttu-id="9fc28-103">워크플로 디자이너에서 .NET Framework 4.5를 대상으로 하고 <xref:System.Activities.Presentation.WorkflowDesigner.Load> 메서드를 사용하여 다시 호스트된 3.5 워크플로를 로드하면 워크플로를 저장하는 동안 <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=fullName>가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fc28-103">When targeting the .NET Framework 4.5 in the workflow designer, and loading a re-hosted 3.5 workflow with the <xref:System.Activities.Presentation.WorkflowDesigner.Load> method, a <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=fullName> is thrown while saving the workflow.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9fc28-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="9fc28-104">Suggestion</span></span>

<span data-ttu-id="9fc28-105">이 버그는 Workflow Designer에서 .NET Framework 4.5를 대상으로 할 때에 매니페스트되므로 `WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName`를 .NET Framework 4.0로 설정하여 해결할 수 있습니다. 또는 <xref:System.Activities.Presentation.WorkflowDesigner.Load> 대신 <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> 메서드를 사용하여 워크플로를 로드하여 문제를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fc28-105">This bug only manifests when targeting .NET Framework 4.5 in the workflow designer, so it can be worked around by setting the `WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName` to the 4.0 .NET Framework.Alternatively, the issue may be avoided by using the <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> method to load the workflow, instead of <xref:System.Activities.Presentation.WorkflowDesigner.Load>.</span></span>

| <span data-ttu-id="9fc28-106">이름</span><span class="sxs-lookup"><span data-stu-id="9fc28-106">Name</span></span>    | <span data-ttu-id="9fc28-107">값</span><span class="sxs-lookup"><span data-stu-id="9fc28-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9fc28-108">Scope</span><span class="sxs-lookup"><span data-stu-id="9fc28-108">Scope</span></span>   | <span data-ttu-id="9fc28-109">주요함</span><span class="sxs-lookup"><span data-stu-id="9fc28-109">Major</span></span>       |
| <span data-ttu-id="9fc28-110">버전</span><span class="sxs-lookup"><span data-stu-id="9fc28-110">Version</span></span> | <span data-ttu-id="9fc28-111">4.5</span><span class="sxs-lookup"><span data-stu-id="9fc28-111">4.5</span></span>         |
| <span data-ttu-id="9fc28-112">형식</span><span class="sxs-lookup"><span data-stu-id="9fc28-112">Type</span></span>    | <span data-ttu-id="9fc28-113">대상 변경</span><span class="sxs-lookup"><span data-stu-id="9fc28-113">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="9fc28-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="9fc28-114">Affected APIs</span></span>

- <xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=nameWithType>

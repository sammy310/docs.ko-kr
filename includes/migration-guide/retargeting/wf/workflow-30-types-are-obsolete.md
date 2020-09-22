---
ms.openlocfilehash: 1f85b1ce95ca07329aff77af4ec894622e0818d1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606280"
---
### <a name="workflow-30-types-are-obsolete"></a><span data-ttu-id="4f35b-101">워크플로 3.0 형식이 사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="4f35b-101">WorkFlow 3.0 types are obsolete</span></span>

#### <a name="details"></a><span data-ttu-id="4f35b-102">설명</span><span class="sxs-lookup"><span data-stu-id="4f35b-102">Details</span></span>

<span data-ttu-id="4f35b-103">System.Workflow 네임스페이스의 Windows Workflow Foundation(WWF) 3.0 API는 이제 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f35b-103">Windows Workflow Foundation (WWF) 3.0 APIs (those from the System.Workflow namespace) are now obsolete.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4f35b-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="4f35b-104">Suggestion</span></span>

<span data-ttu-id="4f35b-105">System.Activities 새 WWF 4.0 API를 대신 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f35b-105">New WWF 4.0 APIs (in System.Activities) should be used instead.</span></span> <span data-ttu-id="4f35b-106">새 API를 사용하는 예제는 [여기](~/docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md)에서 찾을 수 있으며 추가 참고 자료은 [여기](/archive/blogs/workflowteam/wf3-types-marked-obsolete-in-net-4-5)에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f35b-106">An example of using the new APIs can be found [here](~/docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md) and further guidance is available [here](/archive/blogs/workflowteam/wf3-types-marked-obsolete-in-net-4-5).</span></span> <span data-ttu-id="4f35b-107">또는 WWF 3.0 API가 계속 지원되므로 사용할 수 있으며, 빌드 시간 경고는 표시되지 않거나 이전 컴파일러를 사용하여 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f35b-107">Alternatively, since the WWF 3.0 APIs are still supported, they may be used and the build-time warning avoided either by suppressing it or by using an older compiler.</span></span>

| <span data-ttu-id="4f35b-108">이름</span><span class="sxs-lookup"><span data-stu-id="4f35b-108">Name</span></span>    | <span data-ttu-id="4f35b-109">값</span><span class="sxs-lookup"><span data-stu-id="4f35b-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4f35b-110">Scope</span><span class="sxs-lookup"><span data-stu-id="4f35b-110">Scope</span></span>   | <span data-ttu-id="4f35b-111">주요함</span><span class="sxs-lookup"><span data-stu-id="4f35b-111">Major</span></span>       |
| <span data-ttu-id="4f35b-112">버전</span><span class="sxs-lookup"><span data-stu-id="4f35b-112">Version</span></span> | <span data-ttu-id="4f35b-113">4.5</span><span class="sxs-lookup"><span data-stu-id="4f35b-113">4.5</span></span>         |
| <span data-ttu-id="4f35b-114">형식</span><span class="sxs-lookup"><span data-stu-id="4f35b-114">Type</span></span>    | <span data-ttu-id="4f35b-115">대상 변경</span><span class="sxs-lookup"><span data-stu-id="4f35b-115">Retargeting</span></span> |

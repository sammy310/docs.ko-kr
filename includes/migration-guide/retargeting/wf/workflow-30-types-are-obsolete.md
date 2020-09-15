---
ms.openlocfilehash: 358103d5816eb61c88738e9626fb02c563b507f8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617248"
---
### <a name="workflow-30-types-are-obsolete"></a><span data-ttu-id="ab627-101">워크플로 3.0 형식이 사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="ab627-101">WorkFlow 3.0 types are obsolete</span></span>

#### <a name="details"></a><span data-ttu-id="ab627-102">설명</span><span class="sxs-lookup"><span data-stu-id="ab627-102">Details</span></span>

<span data-ttu-id="ab627-103">System.Workflow 네임스페이스의 Windows Workflow Foundation(WWF) 3.0 API는 이제 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab627-103">Windows Workflow Foundation (WWF) 3.0 APIs (those from the System.Workflow namespace) are now obsolete.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ab627-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="ab627-104">Suggestion</span></span>

<span data-ttu-id="ab627-105">System.Activities 새 WWF 4.0 API를 대신 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab627-105">New WWF 4.0 APIs (in System.Activities) should be used instead.</span></span> <span data-ttu-id="ab627-106">새 API를 사용하는 예제는 [여기](~/docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md)에서 찾을 수 있으며 추가 참고 자료은 [여기](https://docs.microsoft.com/archive/blogs/workflowteam/wf3-types-marked-obsolete-in-net-4-5)에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab627-106">An example of using the new APIs can be found [here](~/docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md) and further guidance is available [here](https://docs.microsoft.com/archive/blogs/workflowteam/wf3-types-marked-obsolete-in-net-4-5).</span></span> <span data-ttu-id="ab627-107">또는 WWF 3.0 API가 계속 지원되므로 사용할 수 있으며, 빌드 시간 경고는 표시되지 않거나 이전 컴파일러를 사용하여 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab627-107">Alternatively, since the WWF 3.0 APIs are still supported, they may be used and the build-time warning avoided either by suppressing it or by using an older compiler.</span></span>

| <span data-ttu-id="ab627-108">이름</span><span class="sxs-lookup"><span data-stu-id="ab627-108">Name</span></span>    | <span data-ttu-id="ab627-109">값</span><span class="sxs-lookup"><span data-stu-id="ab627-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ab627-110">Scope</span><span class="sxs-lookup"><span data-stu-id="ab627-110">Scope</span></span>   | <span data-ttu-id="ab627-111">주요함</span><span class="sxs-lookup"><span data-stu-id="ab627-111">Major</span></span>       |
| <span data-ttu-id="ab627-112">버전</span><span class="sxs-lookup"><span data-stu-id="ab627-112">Version</span></span> | <span data-ttu-id="ab627-113">4.5</span><span class="sxs-lookup"><span data-stu-id="ab627-113">4.5</span></span>         |
| <span data-ttu-id="ab627-114">형식</span><span class="sxs-lookup"><span data-stu-id="ab627-114">Type</span></span>    | <span data-ttu-id="ab627-115">대상 변경</span><span class="sxs-lookup"><span data-stu-id="ab627-115">Retargeting</span></span> |

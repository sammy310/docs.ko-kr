---
ms.openlocfilehash: b6cb7edcd6bed50efdf59f3321320ac8cd1b1ab8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617224"
---
### <a name="some-workflow-drag-and-drop-apis-are-obsolete"></a><span data-ttu-id="f0b16-101">일부 워크플로 끌어서 놓기 API가 사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="f0b16-101">Some WorkFlow drag-and-drop APIs are obsolete</span></span>

#### <a name="details"></a><span data-ttu-id="f0b16-102">설명</span><span class="sxs-lookup"><span data-stu-id="f0b16-102">Details</span></span>

<span data-ttu-id="f0b16-103">이 워크플로 끌어서 놓기 API는 사용되지 않으며 응용 프로그램이 4.5에 대해 다시 빌드하는 경우 컴파일러 경고가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b16-103">This WorkFlow drag-and-drop API is obsolete and will cause compiler warnings if the app is rebuilt against 4.5.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f0b16-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="f0b16-104">Suggestion</span></span>

<span data-ttu-id="f0b16-105">여러 개체에 대한 작업을 지원하는 새 <xref:System.Activities.Presentation.DragDropHelper?displayProperty=fullName> API를 대신 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b16-105">New <xref:System.Activities.Presentation.DragDropHelper?displayProperty=fullName> APIs that support operations with multiple objects should be used instead.</span></span> <span data-ttu-id="f0b16-106">또는 빌드 경고를 표시하지 않거나 이전 컴파일러를 사용하여 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b16-106">Alternatively, the build warnings can be suppressed or they can be avoided by using an older compiler.</span></span> <span data-ttu-id="f0b16-107">API는 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0b16-107">The APIs are still supported.</span></span>

| <span data-ttu-id="f0b16-108">이름</span><span class="sxs-lookup"><span data-stu-id="f0b16-108">Name</span></span>    | <span data-ttu-id="f0b16-109">값</span><span class="sxs-lookup"><span data-stu-id="f0b16-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f0b16-110">Scope</span><span class="sxs-lookup"><span data-stu-id="f0b16-110">Scope</span></span>   | <span data-ttu-id="f0b16-111">부</span><span class="sxs-lookup"><span data-stu-id="f0b16-111">Minor</span></span>       |
| <span data-ttu-id="f0b16-112">버전</span><span class="sxs-lookup"><span data-stu-id="f0b16-112">Version</span></span> | <span data-ttu-id="f0b16-113">4.5</span><span class="sxs-lookup"><span data-stu-id="f0b16-113">4.5</span></span>         |
| <span data-ttu-id="f0b16-114">형식</span><span class="sxs-lookup"><span data-stu-id="f0b16-114">Type</span></span>    | <span data-ttu-id="f0b16-115">대상 변경</span><span class="sxs-lookup"><span data-stu-id="f0b16-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="f0b16-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="f0b16-116">Affected APIs</span></span>

- <xref:System.Activities.Presentation.DragDropHelper.DoDragMove(System.Activities.Presentation.WorkflowViewElement,System.Windows.Point)?displayProperty=nameWithType>
- <xref:System.Activities.Presentation.DragDropHelper.GetCompositeView(System.Windows.DragEventArgs)?displayProperty=nameWithType>
- <xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItem(System.Windows.DragEventArgs)?displayProperty=nameWithType>
- <xref:System.Activities.Presentation.DragDropHelper.GetDroppedObject(System.Windows.DependencyObject,System.Windows.DragEventArgs,System.Activities.Presentation.EditingContext)?displayProperty=nameWithType>

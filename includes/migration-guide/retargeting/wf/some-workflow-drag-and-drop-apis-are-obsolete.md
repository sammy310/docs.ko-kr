---
ms.openlocfilehash: b6cb7edcd6bed50efdf59f3321320ac8cd1b1ab8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617224"
---
### <a name="some-workflow-drag-and-drop-apis-are-obsolete"></a>일부 워크플로 끌어서 놓기 API가 사용되지 않음

#### <a name="details"></a>설명

이 워크플로 끌어서 놓기 API는 사용되지 않으며 응용 프로그램이 4.5에 대해 다시 빌드하는 경우 컴파일러 경고가 발생합니다.

#### <a name="suggestion"></a>제안 해결 방법

여러 개체에 대한 작업을 지원하는 새 <xref:System.Activities.Presentation.DragDropHelper?displayProperty=fullName> API를 대신 사용해야 합니다. 또는 빌드 경고를 표시하지 않거나 이전 컴파일러를 사용하여 방지할 수 있습니다. API는 계속 지원됩니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   | 부       |
| 버전 | 4.5         |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Activities.Presentation.DragDropHelper.DoDragMove(System.Activities.Presentation.WorkflowViewElement,System.Windows.Point)?displayProperty=nameWithType>
- <xref:System.Activities.Presentation.DragDropHelper.GetCompositeView(System.Windows.DragEventArgs)?displayProperty=nameWithType>
- <xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItem(System.Windows.DragEventArgs)?displayProperty=nameWithType>
- <xref:System.Activities.Presentation.DragDropHelper.GetDroppedObject(System.Windows.DependencyObject,System.Windows.DragEventArgs,System.Activities.Presentation.EditingContext)?displayProperty=nameWithType>

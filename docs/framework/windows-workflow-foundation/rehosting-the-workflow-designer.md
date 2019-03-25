---
title: Workflow Designer 재호스팅
ms.date: 03/30/2017
ms.assetid: bec1fc28-f902-4edb-86c5-436cec802c2b
ms.openlocfilehash: 29b3a205e97ad84ef8d0ef878b41c02058a8e5dc
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703740"
---
# <a name="rehosting-the-workflow-designer"></a><span data-ttu-id="f2a93-102">Workflow Designer 재호스팅</span><span class="sxs-lookup"><span data-stu-id="f2a93-102">Rehosting the Workflow Designer</span></span>
<span data-ttu-id="f2a93-103">[!INCLUDE[wfd1](../../../includes/wfd1-md.md)] 만들기, 수정 및 모니터링 워크플로에의 목적에 대 한 Visual Studio 2012 외부 환경에서 다시 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2a93-103">The [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] can be rehosted in environments outside of Visual Studio 2012 for the purposes of creating, modifying, and monitoring workflows.</span></span>

 <span data-ttu-id="f2a93-104"><xref:System.Activities.Presentation.WorkflowDesigner> 형식은 캔버스, 속성표 및 기타 요소의 래퍼이며 기본 프로그래밍 모델을 노출하여 대부분의 디자이너 다시 호스팅 시나리오를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="f2a93-104">The <xref:System.Activities.Presentation.WorkflowDesigner> type is a wrapper of the canvas, property grid, and other elements, and exposes a basic programming model to handle the majority of designer rehosting scenarios.</span></span> <span data-ttu-id="f2a93-105">호스팅하는 <xref:System.Activities.Presentation.WorkflowDesigner> 는 Windows Presentation Foundation (WPF) 내에서 응용 프로그램에 대 한 일반적인 재호스팅 시나리오는 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="f2a93-105">Hosting the <xref:System.Activities.Presentation.WorkflowDesigner> inside a Windows Presentation Foundation (WPF) application is a common rehosting scenario for [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span>

## <a name="in-this-section"></a><span data-ttu-id="f2a93-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="f2a93-106">In This Section</span></span>
 [<span data-ttu-id="f2a93-107">작업 1: 새 Windows Presentation Foundation 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="f2a93-107">Task 1: Create a New Windows Presentation Foundation Application</span></span>](task-1-create-a-new-wpf-app.md)

 [<span data-ttu-id="f2a93-108">작업 2: 워크플로 디자이너 호스트</span><span class="sxs-lookup"><span data-stu-id="f2a93-108">Task 2: Host the Workflow Designer</span></span>](task-2-host-the-workflow-designer.md)

 [<span data-ttu-id="f2a93-109">작업 3: 도구 상자 및 PropertyGrid 창 만들기</span><span class="sxs-lookup"><span data-stu-id="f2a93-109">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](task-3-create-the-toolbox-and-propertygrid-panes.md)

 [<span data-ttu-id="f2a93-110">재호스트된 워크플로 디자이너에서 새 Workflow Foundation 4.5 기능에 대한 지원</span><span class="sxs-lookup"><span data-stu-id="f2a93-110">Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer</span></span>](wf-features-in-the-rehosted-workflow-designer.md)

## <a name="see-also"></a><span data-ttu-id="f2a93-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="f2a93-111">See also</span></span>
- [<span data-ttu-id="f2a93-112">워크플로 디자인 환경 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="f2a93-112">Customizing the Workflow Design Experience</span></span>](customizing-the-workflow-design-experience.md)

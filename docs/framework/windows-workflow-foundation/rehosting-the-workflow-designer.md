---
title: Workflow Designer 재호스팅
description: 워크플로를 생성, 수정 및 모니터링 하기 위해 Visual Studio 외부의 환경에서 Windows 워크플로 디자이너를 다시 호스팅할 수 있습니다.
ms.date: 03/30/2017
ms.assetid: bec1fc28-f902-4edb-86c5-436cec802c2b
ms.openlocfilehash: 34709b84d445b2bb07e32bfd3f34d06072f125bf
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421425"
---
# <a name="rehosting-the-workflow-designer"></a><span data-ttu-id="baedb-103">Workflow Designer 재호스팅</span><span class="sxs-lookup"><span data-stu-id="baedb-103">Rehosting the Workflow Designer</span></span>
<span data-ttu-id="baedb-104">워크플로를 생성, 수정 및 모니터링 하기 위해 Visual Studio 2012 외부의 환경에서 Windows 워크플로 디자이너를 다시 호스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baedb-104">The Windows Workflow Designer can be rehosted in environments outside of Visual Studio 2012 for the purposes of creating, modifying, and monitoring workflows.</span></span>

 <span data-ttu-id="baedb-105"><xref:System.Activities.Presentation.WorkflowDesigner> 형식은 캔버스, 속성표 및 기타 요소의 래퍼이며 기본 프로그래밍 모델을 노출하여 대부분의 디자이너 다시 호스팅 시나리오를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="baedb-105">The <xref:System.Activities.Presentation.WorkflowDesigner> type is a wrapper of the canvas, property grid, and other elements, and exposes a basic programming model to handle the majority of designer rehosting scenarios.</span></span> <span data-ttu-id="baedb-106"><xref:System.Activities.Presentation.WorkflowDesigner>Windows Presentation Foundation (WPF) 응용 프로그램 내부에서를 호스트 하는 것은 워크플로 디자이너에 대 한 일반적인 재호스팅 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="baedb-106">Hosting the <xref:System.Activities.Presentation.WorkflowDesigner> inside a Windows Presentation Foundation (WPF) application is a common rehosting scenario for Workflow Designer.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="baedb-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="baedb-107">In This Section</span></span>
 [<span data-ttu-id="baedb-108">작업 1: 새 Windows Presentation Foundation 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="baedb-108">Task 1: Create a New Windows Presentation Foundation Application</span></span>](task-1-create-a-new-wpf-app.md)

 [<span data-ttu-id="baedb-109">작업 2: 워크플로 디자이너 호스트</span><span class="sxs-lookup"><span data-stu-id="baedb-109">Task 2: Host the Workflow Designer</span></span>](task-2-host-the-workflow-designer.md)

 [<span data-ttu-id="baedb-110">작업 3: 도구 상자 및 PropertyGrid 창 만들기</span><span class="sxs-lookup"><span data-stu-id="baedb-110">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](task-3-create-the-toolbox-and-propertygrid-panes.md)

 [<span data-ttu-id="baedb-111">재호스팅된 워크플로 디자이너에서 새 Workflow Foundation 4.5 기능에 대한 지원</span><span class="sxs-lookup"><span data-stu-id="baedb-111">Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer</span></span>](wf-features-in-the-rehosted-workflow-designer.md)

## <a name="see-also"></a><span data-ttu-id="baedb-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="baedb-112">See also</span></span>

- [<span data-ttu-id="baedb-113">워크플로 디자인 환경 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="baedb-113">Customizing the Workflow Design Experience</span></span>](customizing-the-workflow-design-experience.md)

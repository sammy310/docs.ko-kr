---
description: '자세한 정보: 작업 1: 새 Windows Presentation Foundation 응용 프로그램 만들기'
title: '작업 1: 새 Windows Presentation Foundation 애플리케이션 만들기'
ms.date: 03/30/2017
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
ms.openlocfilehash: 7bbb49e3d663d1878b2b3e150a24f775eeca0135
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755241"
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a><span data-ttu-id="8e563-103">작업 1: 새 Windows Presentation Foundation 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="8e563-103">Task 1: Create a New Windows Presentation Foundation Application</span></span>

<span data-ttu-id="8e563-104">이 작업에서는 WPF 응용 프로그램 Visual Studio 템플릿을 사용 하 여 빈 Windows Presentation Foundation (WPF) 응용 프로그램을 만들고 해당 워크플로 어셈블리에 대 한 참조를 추가 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e563-104">In this task, you will create an empty Windows Presentation Foundation (WPF) application by using the WPF Application Visual Studio template and add references to the appropriate [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow assemblies.</span></span>  
  
## <a name="to-create-the-wpf-application-project"></a><span data-ttu-id="8e563-105">WPF 애플리케이션 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="8e563-105">To create the WPF Application project</span></span>

1. <span data-ttu-id="8e563-106">Visual Studio를 열고 **파일** 메뉴에서 **새로 만들기** 를 가리킨 다음 **프로젝트** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e563-106">Open Visual Studio and on the **File** menu, point to **New**, and then click **Project**.</span></span>

2. <span data-ttu-id="8e563-107">**새 프로젝트** 대화 상자의 왼쪽에 있는 **설치 된 템플릿** 창에서 **Visual c #** 또는 **Visual Basic** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e563-107">In the **New Project** dialog box, select either **Visual C#** or **Visual Basic** from the **Installed Templates** pane on the left side of the box.</span></span> <span data-ttu-id="8e563-108">선택한 언어가 표시 되지 않는 경우 **다른 언어** 아래를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e563-108">If the language of your choice does not appear, look under **Other Languages**.</span></span>

3. <span data-ttu-id="8e563-109">**설치 된 템플릿** 창에서 **Windows** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e563-109">Select **Windows** in the **Installed Templates** pane.</span></span>

4. <span data-ttu-id="8e563-110">위쪽 창의 드롭다운 목록 상자에서 (기본값) **.NET Framework 4** 가 선택 되어 있는지 확인 한 다음 **WPF 응용 프로그램** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e563-110">In the top pane, confirm that (the default value) **.NET Framework 4** has been selected in the drop-down list box, and then select **WPF Application**.</span></span>

5. <span data-ttu-id="8e563-111">창의 맨 아래에 프로젝트 이름을 **HostingApplication** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e563-111">Set the name of the project to **HostingApplication** at the bottom of the window.</span></span>

6. <span data-ttu-id="8e563-112">솔루션 이름을 **RehostingTheDesigner** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e563-112">Set the solution name to **RehostingTheDesigner**.</span></span>

7. <span data-ttu-id="8e563-113">**확인** 을 클릭 하 여 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8e563-113">Click **OK** to create the application project.</span></span> <span data-ttu-id="8e563-114">Visual Studio는 응용 프로그램에 대 한 기본 WPF UI를 만들고 적절 한 XAML 및 코드 숨김이 포함 된 파일을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e563-114">Visual Studio creates a basic WPF UI for your application and includes the appropriate XAML and code-behind files.</span></span>

8. <span data-ttu-id="8e563-115">**Workflowmodel** 어셈블리에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e563-115">Add references to **WorkflowModel** assemblies.</span></span> <span data-ttu-id="8e563-116">이렇게 하려면 **솔루션 탐색기** 에서 **HostingApplication** 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **참조 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e563-116">To do this, in **Solution Explorer**, right-click the **HostingApplication** project and select **Add Reference**.</span></span>

9. <span data-ttu-id="8e563-117">**참조 추가** 대화 상자에서 **.net** 탭을 클릭 하 고 CTRL 키를 누른 채 다음 어셈블리를 선택 하 고 **확인** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e563-117">In the **Add Reference** dialog box, click the **.NET** tab, hold down the CTRL key, select the following assemblies, and then click **OK**:</span></span>

    - <span data-ttu-id="8e563-118">System.Activities</span><span class="sxs-lookup"><span data-stu-id="8e563-118">System.Activities</span></span>
    - <span data-ttu-id="8e563-119">System.Activities.Presentation</span><span class="sxs-lookup"><span data-stu-id="8e563-119">System.Activities.Presentation</span></span>
    - <span data-ttu-id="8e563-120">System.Activities.Core.Presentation</span><span class="sxs-lookup"><span data-stu-id="8e563-120">System.Activities.Core.Presentation</span></span>

10. <span data-ttu-id="8e563-121">Workflow Designer 디자인 캔버스를 호스트 하는 방법에 대 한 자세한 내용은 [작업 2: 호스트 워크플로 디자이너](task-2-host-the-workflow-designer.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8e563-121">See [Task 2: Host the Workflow Designer](task-2-host-the-workflow-designer.md) to learn how to host the workflow designer design canvas.</span></span>

## <a name="see-also"></a><span data-ttu-id="8e563-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e563-122">See also</span></span>

- [<span data-ttu-id="8e563-123">Workflow Designer 재호스팅</span><span class="sxs-lookup"><span data-stu-id="8e563-123">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)
- [<span data-ttu-id="8e563-124">작업 2: 워크플로 디자이너 호스트</span><span class="sxs-lookup"><span data-stu-id="8e563-124">Task 2: Host the Workflow Designer</span></span>](task-2-host-the-workflow-designer.md)

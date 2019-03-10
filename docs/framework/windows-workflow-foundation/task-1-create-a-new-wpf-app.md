---
title: '작업 1: 새 Windows Presentation Foundation 응용 프로그램 만들기'
ms.date: 03/30/2017
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
ms.openlocfilehash: 533b4a1030ab5f47eb96ca62dc2805eae7933b9b
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711890"
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a><span data-ttu-id="398e8-102">작업 1: 새 Windows Presentation Foundation 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="398e8-102">Task 1: Create a New Windows Presentation Foundation Application</span></span>
<span data-ttu-id="398e8-103">이 태스크에서는 빈 Windows Presentation Foundation (WPF) 응용 프로그램을 WPF 응용 프로그램에 대 한 Visual Studio 템플릿을 사용 하 여 만들고 적절 한 참조를 추가 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 워크플로 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="398e8-103">In this task, you will create an empty Windows Presentation Foundation (WPF) application by using the WPF Application Visual Studio template and add references to the appropriate [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow assemblies.</span></span>  
  
### <a name="to-create-the-wpf-application-project"></a><span data-ttu-id="398e8-104">WPF 응용 프로그램 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="398e8-104">To create the WPF Application project</span></span>  
  
1.  <span data-ttu-id="398e8-105">Visual Studio를 열고 고는 **파일** 메뉴에서 **새로 만들기**를 클릭 하 고 **프로젝트**.</span><span class="sxs-lookup"><span data-stu-id="398e8-105">Open Visual Studio and on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="398e8-106">에 **새 프로젝트** 대화 상자 중 하나를 선택 합니다 **Visual C#**  또는 **Visual Basic** 에서 **설치 된 템플릿** 왼쪽 창 쪽 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="398e8-106">In the **New Project** dialog box, select either **Visual C#** or **Visual Basic** from the **Installed Templates** pane on the left side of the box.</span></span> <span data-ttu-id="398e8-107">사용자가 선택한 언어로 나타나지 않으면 아래를 봅니다 **다른 언어**합니다.</span><span class="sxs-lookup"><span data-stu-id="398e8-107">If the language of your choice does not appear, look under **Other Languages**.</span></span>  
  
3.  <span data-ttu-id="398e8-108">선택 **Windows** 에 **설치 된 템플릿** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="398e8-108">Select **Windows** in the **Installed Templates** pane.</span></span>  
  
4.  <span data-ttu-id="398e8-109">위쪽 창에 있는지를 확인 (기본값) **.NET Framework 4** 드롭다운 목록 상자에서 선택한 다음 선택 되었습니다 **WPF 응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="398e8-109">In the top pane, confirm that (the default value) **.NET Framework 4** has been selected in the drop-down list box, and then select **WPF Application**.</span></span>  
  
5.  <span data-ttu-id="398e8-110">프로젝트의 이름을 설정 **HostingApplication** 창의 맨 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="398e8-110">Set the name of the project to **HostingApplication** at the bottom of the window.</span></span>  
  
6.  <span data-ttu-id="398e8-111">솔루션 이름으로 설정할 **RehostingTheDesigner**합니다.</span><span class="sxs-lookup"><span data-stu-id="398e8-111">Set the solution name to **RehostingTheDesigner**.</span></span>  
  
7.  <span data-ttu-id="398e8-112">클릭 **확인** 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="398e8-112">Click **OK** to create the application project.</span></span> <span data-ttu-id="398e8-113">Visual Studio 응용 프로그램에 대 한 기본 WPF UI를 만들고 적절 한 XAML 및 코드 숨김 파일을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="398e8-113">Visual Studio creates a basic WPF UI for your application and includes the appropriate XAML and code-behind files.</span></span>  
  
8.  <span data-ttu-id="398e8-114">에 대 한 참조를 추가 **WorkflowModel** 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="398e8-114">Add references to **WorkflowModel** assemblies.</span></span> <span data-ttu-id="398e8-115">이렇게 하려면 **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 합니다 **HostingApplication** 프로젝트를 마우스 **참조 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="398e8-115">To do this, in **Solution Explorer**, right-click the **HostingApplication** project and select **Add Reference**.</span></span>  
  
9. <span data-ttu-id="398e8-116">에 **참조 추가** 대화 상자에서 클릭 합니다 **.NET** 탭, CTRL 키를 누른 하 고, 다음 어셈블리를 선택 하 고 클릭 **확인**:</span><span class="sxs-lookup"><span data-stu-id="398e8-116">In the **Add Reference** dialog box, click the **.NET** tab, hold down the CTRL key, select the following assemblies, and then click **OK**:</span></span>  
  
    -   <span data-ttu-id="398e8-117">System.Activities</span><span class="sxs-lookup"><span data-stu-id="398e8-117">System.Activities</span></span>  
  
    -   <span data-ttu-id="398e8-118">System.Activities.Presentation</span><span class="sxs-lookup"><span data-stu-id="398e8-118">System.Activities.Presentation</span></span>  
  
    -   <span data-ttu-id="398e8-119">System.Activities.Core.Presentation</span><span class="sxs-lookup"><span data-stu-id="398e8-119">System.Activities.Core.Presentation</span></span>  
  
10. <span data-ttu-id="398e8-120">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="398e8-120">Click **OK**.</span></span>  
  
11. <span data-ttu-id="398e8-121">참조 [작업 2: 워크플로 디자이너 호스트](task-2-host-the-workflow-designer.md) 을 workflow designer 디자인 캔버스를 호스트 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="398e8-121">See [Task 2: Host the Workflow Designer](task-2-host-the-workflow-designer.md) to learn how to host the workflow designer design canvas.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="398e8-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="398e8-122">See also</span></span>
- [<span data-ttu-id="398e8-123">워크플로 디자이너 재호스트</span><span class="sxs-lookup"><span data-stu-id="398e8-123">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)
- [<span data-ttu-id="398e8-124">작업 2: 워크플로 디자이너 호스트</span><span class="sxs-lookup"><span data-stu-id="398e8-124">Task 2: Host the Workflow Designer</span></span>](task-2-host-the-workflow-designer.md)

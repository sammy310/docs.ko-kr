---
title: '방법: Windows Form에 단순 바인딩된 컨트롤 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], simple data binding
- Windows Forms controls, data binding
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
ms.openlocfilehash: 79b31e61f4c7739a20765c9484db6a8cfd04b01b
ms.sourcegitcommit: 11deacc8ec9f229ab8ee3cd537515d4c2826515f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2019
ms.locfileid: "66003770"
---
# <a name="how-to-create-a-simple-bound-control-on-a-windows-form"></a><span data-ttu-id="27d3f-102">방법: Windows Form에 단순 바인딩된 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="27d3f-102">How to: Create a Simple-Bound Control on a Windows Form</span></span>
<span data-ttu-id="27d3f-103">사용 하 여 *단순 바인딩*, 컨트롤에서 데이터 집합 테이블에서 열 값과 같은 단일 데이터 요소를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27d3f-103">With *simple binding*, you can display a single data element, such as a column value from a dataset table, in a control.</span></span> <span data-ttu-id="27d3f-104">컨트롤의 모든 속성을 데이터 값에 간단한 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27d3f-104">You can simple-bind any property of a control to a data value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="27d3f-105">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27d3f-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="27d3f-106">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="27d3f-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="27d3f-107">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="27d3f-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-simple-bind-a-control"></a><span data-ttu-id="27d3f-108">단순 컨트롤을 바인딩</span><span class="sxs-lookup"><span data-stu-id="27d3f-108">To simple-bind a control</span></span>  
  
1. <span data-ttu-id="27d3f-109">데이터 소스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="27d3f-109">Connect to a data source.</span></span> <span data-ttu-id="27d3f-110">자세한 내용은 [데이터 원본에 연결할](../data/adonet/connecting-to-a-data-source.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="27d3f-110">For more information, see [Connecting to a Data Source](../data/adonet/connecting-to-a-data-source.md).</span></span>  
  
2. <span data-ttu-id="27d3f-111">폼에서 컨트롤을 선택 하 고 표시 합니다 **속성** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="27d3f-111">In the form, select the control and display the **Properties** window.</span></span>  
  
3. <span data-ttu-id="27d3f-112">확장 된 **(DataBindings)** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="27d3f-112">Expand the **(DataBindings)** property.</span></span>  
  
     <span data-ttu-id="27d3f-113">아래에 있는 대부분의 바인딩된 속성이 표시 됩니다는 **(DataBindings)** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="27d3f-113">The properties most often bound are displayed underneath the **(DataBindings)** property.</span></span> <span data-ttu-id="27d3f-114">예를 들어, 대부분의 컨트롤에서에서의 **텍스트** 속성은 가장 자주 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="27d3f-114">For example, in most controls, the **Text** property is most frequently bound.</span></span>  
  
4.  <span data-ttu-id="27d3f-115">않으려면 속성 바인딩이 아닙니다. 일반적으로 바인딩된 속성 중 하나를 클릭 합니다 **줄임표** 단추 (![의 줄임표 단추 (...)의 Visual Studio 속성 창에서](./media/how-to-create-a-simple-bound-control-on-a-windows-form/visual-studio-ellipsis-button.png))에 **( 고급)** 상자를 표시 합니다 **서식 지정 및 고급 바인딩** 해당 컨트롤에 대 한 속성의 전체 목록 사용 하 여 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="27d3f-115">If the property you want to bind is not one of the commonly bound properties, click the **Ellipsis** button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/how-to-create-a-simple-bound-control-on-a-windows-form/visual-studio-ellipsis-button.png)) in the **(Advanced)** box to display the **Formatting and Advanced Binding** dialog box with a complete list of properties for that control.</span></span>  
  
5. <span data-ttu-id="27d3f-116">아래의 드롭다운 화살표를 클릭 하 고 바인딩 속성을 선택 **바인딩**합니다.</span><span class="sxs-lookup"><span data-stu-id="27d3f-116">Select the property you want to bind and click the drop-down arrow under **Binding**.</span></span>  
  
     <span data-ttu-id="27d3f-117">사용 가능한 데이터 소스 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="27d3f-117">A list of available data sources is displayed.</span></span>  
  
6. <span data-ttu-id="27d3f-118">원하는 단일 데이터 요소를 찾을 때까지 바인딩할 데이터 소스를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="27d3f-118">Expand the data source you want to bind to until you find the single data element you want.</span></span> <span data-ttu-id="27d3f-119">예를 들어 데이터 집합의 테이블에서 열 값에 바인딩할 경우 데이터 집합 이름을 확장하고 나서 테이블을 이름을 확장하여 열 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="27d3f-119">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>  
  
7. <span data-ttu-id="27d3f-120">바인딩할 요소 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27d3f-120">Click the name of an element to bind to.</span></span>  
  
8. <span data-ttu-id="27d3f-121">작업할 경우는 **서식 지정 및 고급 바인딩** 대화 상자, 클릭 **확인** 돌아가려면 합니다 **속성** 창.</span><span class="sxs-lookup"><span data-stu-id="27d3f-121">If you were working in the **Formatting and Advanced Binding** dialog box, click **OK** to return to the **Properties** window.</span></span>  
  
9. <span data-ttu-id="27d3f-122">컨트롤의 추가 속성을 바인딩할 경우 3 ~ 7 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="27d3f-122">If you want to bind additional properties of the control, repeat steps 3 through 7.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="27d3f-123">있기 때문에 단순 바인딩된 컨트롤에는 하나의 데이터 요소만 표시, 전형적인 Windows Form을 단순 바인딩된 컨트롤에서 탐색 논리를 포함 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="27d3f-123">Because simple-bound controls show only a single data element, it is very typical to include navigation logic in a Windows Form with simple-bound controls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27d3f-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="27d3f-124">See also</span></span>

- <xref:System.Windows.Forms.Binding>
- [<span data-ttu-id="27d3f-125">Windows Forms 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="27d3f-125">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
- [<span data-ttu-id="27d3f-126">데이터 바인딩 및 Windows Forms</span><span class="sxs-lookup"><span data-stu-id="27d3f-126">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)

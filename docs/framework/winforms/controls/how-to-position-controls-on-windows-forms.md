---
title: '방법: Windows Forms에서 컨트롤 배치'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Location
- Location.Y
- Location.X
helpviewer_keywords:
- controls [Windows Forms]
- controls [Windows Forms], moving
- snaplines
- controls [Windows Forms], positioning
ms.assetid: 4693977e-34a4-4f19-8221-68c3120c2b2b
ms.openlocfilehash: a0b97073b2f9363a64bfc4a4ede7ffa69e2bce42
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59334005"
---
# <a name="how-to-position-controls-on-windows-forms"></a><span data-ttu-id="ef14c-102">방법: Windows Forms에서 컨트롤 배치</span><span class="sxs-lookup"><span data-stu-id="ef14c-102">How to: Position Controls on Windows Forms</span></span>
<span data-ttu-id="ef14c-103">컨트롤의 위치, Windows Forms 디자이너를 사용 하거나 지정 된 <xref:System.Windows.Forms.Control.Location%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ef14c-103">To position controls, use the Windows Forms Designer, or specify the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ef14c-104">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef14c-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ef14c-105">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ef14c-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ef14c-106">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ef14c-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a><span data-ttu-id="ef14c-107">Windows Forms 디자이너의 디자인 화면에서 컨트롤 위치</span><span class="sxs-lookup"><span data-stu-id="ef14c-107">To position a control on the design surface of the Windows Forms Designer</span></span>  
  
-   <span data-ttu-id="ef14c-108">컨트롤이 마우스를 사용 하 여 적절 한 위치로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="ef14c-108">Drag the control to the appropriate location with the mouse.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef14c-109">컨트롤을 선택 하 고 화살표를 사용 하 여 키를 보다 정확 하 게 위치를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef14c-109">Select the control and move it with the ARROW keys to position it more precisely.</span></span> <span data-ttu-id="ef14c-110">또한 *맞춤선* 정확 하 게 양식의 컨트롤을 배치 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef14c-110">Also, *snaplines* assist you in placing controls precisely on your form.</span></span> <span data-ttu-id="ef14c-111">자세한 내용은 [연습: Snaplines를 사용 하 여 Forms Windows에서 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ef14c-111">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>  
  
### <a name="to-position-a-control-using-the-properties-window"></a><span data-ttu-id="ef14c-112">속성 창을 사용 하 여 컨트롤 위치</span><span class="sxs-lookup"><span data-stu-id="ef14c-112">To position a control using the Properties window</span></span>  
  
1. <span data-ttu-id="ef14c-113">배치 하려는 컨트롤을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef14c-113">Click the control you want to position.</span></span>  
  
2. <span data-ttu-id="ef14c-114">에 **속성** 창에 대 한 형식 값을 <xref:System.Windows.Forms.Control.Location%2A> 속성을 해당 컨테이너 내의 컨트롤을 배치 하는 쉼표로 구분 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef14c-114">In the **Properties** window, type values for the <xref:System.Windows.Forms.Control.Location%2A> property, separated by a comma, to position the control within its container.</span></span>  
  
     <span data-ttu-id="ef14c-115">첫 번째 숫자 (X)가; 컨테이너의 왼쪽된 테두리의 거리 두 번째 숫자 (Y)는 픽셀 컨테이너 영역의 위쪽 테두리의 거리입니다.</span><span class="sxs-lookup"><span data-stu-id="ef14c-115">The first number (X) is the distance from the left border of the container; the second number (Y) is the distance from the upper border of the container area, measured in pixels.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ef14c-116">확장할 수 있습니다 합니다 <xref:System.Windows.Forms.Control.Location%2A> 속성을 입력 합니다 **X** 및 **Y** 값을 개별적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef14c-116">You can expand the <xref:System.Windows.Forms.Control.Location%2A> property to type the **X** and **Y** values individually.</span></span>  
  
### <a name="to-position-a-control-programmatically"></a><span data-ttu-id="ef14c-117">컨트롤을 프로그래밍 방식으로 배치 하려면</span><span class="sxs-lookup"><span data-stu-id="ef14c-117">To position a control programmatically</span></span>  
  
1. <span data-ttu-id="ef14c-118">설정 된 <xref:System.Windows.Forms.Control.Location%2A> 컨트롤의 속성을 <xref:System.Drawing.Point>입니다.</span><span class="sxs-lookup"><span data-stu-id="ef14c-118">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the control to a <xref:System.Drawing.Point>.</span></span>  
  
    ```vb  
    Button1.Location = New Point(100, 100)  
    ```  
  
    ```csharp  
    button1.Location = new Point(100, 100);  
    ```  
  
    ```cpp  
    button1->Location = Point(100, 100);  
    ```  
  
2. <span data-ttu-id="ef14c-119">컨트롤 위치의 X 좌표를 변경를 사용 하는 <xref:System.Windows.Forms.Control.Left%2A> 하위 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ef14c-119">Change the X coordinate of the control's location using the <xref:System.Windows.Forms.Control.Left%2A> subproperty.</span></span>  
  
    ```vb  
    Button1.Left = 300  
    ```  
  
    ```csharp  
    button1.Left = 300;  
    ```  
  
    ```cpp  
    button1->Left = 300;  
    ```  
  
### <a name="to-increment-a-controls-location-programmatically"></a><span data-ttu-id="ef14c-120">컨트롤의 위치를 프로그래밍 방식으로 증가</span><span class="sxs-lookup"><span data-stu-id="ef14c-120">To increment a control's location programmatically</span></span>  
  
1. <span data-ttu-id="ef14c-121">설정 된 <xref:System.Windows.Forms.Control.Left%2A> 하위 컨트롤의 X 좌표를 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="ef14c-121">Set the <xref:System.Windows.Forms.Control.Left%2A> subproperty to increment the X coordinate of the control.</span></span>  
  
    ```vb  
    Button1.Left += 200  
    ```  
  
    ```csharp  
    button1.Left += 200;  
    ```  
  
    ```cpp  
    button1->Left += 200;  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="ef14c-122">사용 하 여는 <xref:System.Windows.Forms.Control.Location%2A> 설정할 컨트롤의 X 및 Y 속성을 동시에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef14c-122">Use the <xref:System.Windows.Forms.Control.Location%2A> property to set a control's X and Y positions simultaneously.</span></span> <span data-ttu-id="ef14c-123">사용 하 여 컨트롤의 위치를 개별적으로 설정 하려면 <xref:System.Windows.Forms.Control.Left%2A> (**X**) 또는 <xref:System.Windows.Forms.Control.Top%2A> (**Y**) 하위 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ef14c-123">To set a position individually, use the control's <xref:System.Windows.Forms.Control.Left%2A> (**X**) or <xref:System.Windows.Forms.Control.Top%2A> (**Y**) subproperty.</span></span> <span data-ttu-id="ef14c-124">X 및 Y 좌표를 암시적으로 설정 하지 마십시오는 <xref:System.Drawing.Point> 이 구조는 단추의 좌표 복사본을 포함 하기 때문에 단추 위치를 나타내는 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="ef14c-124">Do not try to implicitly set the X and Y coordinates of the <xref:System.Drawing.Point> structure that represents the button's location, because this structure contains a copy of the button's coordinates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef14c-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="ef14c-125">See also</span></span>

- [<span data-ttu-id="ef14c-126">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ef14c-126">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="ef14c-127">연습: 맞춤선을 사용 하 여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="ef14c-127">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="ef14c-128">연습: TableLayoutPanel을 사용 하 여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="ef14c-128">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="ef14c-129">연습: FlowLayoutPanel을 사용 하 여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="ef14c-129">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="ef14c-130">Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="ef14c-130">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="ef14c-131">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="ef14c-131">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="ef14c-132">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ef14c-132">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="ef14c-133">기능별 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ef14c-133">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- <span data-ttu-id="ef14c-134">[방법: Windows Forms의 화면 위치 설정](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ef14c-134">[How to: Set the Screen Location of Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span></span>

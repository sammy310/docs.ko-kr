---
title: '방법: Windows Forms에 컨트롤 배치'
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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: bb57d14397a4626e01c41dd687dfed7331282a10
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458332"
---
# <a name="how-to-position-controls-on-windows-forms"></a><span data-ttu-id="49fe9-102">방법: Windows Forms에 컨트롤 배치</span><span class="sxs-lookup"><span data-stu-id="49fe9-102">How to: Position controls on Windows Forms</span></span>

<span data-ttu-id="49fe9-103">컨트롤의 위치를 지정 하려면 Visual Studio에서 Windows Forms 디자이너를 사용 하거나 <xref:System.Windows.Forms.Control.Location%2A> 속성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="49fe9-103">To position controls, use the Windows Forms Designer in Visual Studio or specify the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>

## <a name="position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a><span data-ttu-id="49fe9-104">Windows Forms 디자이너의 디자인 화면에 컨트롤 배치</span><span class="sxs-lookup"><span data-stu-id="49fe9-104">Position a control on the design surface of the Windows Forms Designer</span></span>

<span data-ttu-id="49fe9-105">Visual Studio에서 마우스를 사용 하 여 컨트롤을 적절 한 위치로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="49fe9-105">In Visual Studio, drag the control to the appropriate location with the mouse.</span></span>

> [!NOTE]
> <span data-ttu-id="49fe9-106">컨트롤을 선택 하 고 화살표 키로 이동 하 여 더 정확 하 게 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="49fe9-106">Select the control and move it with the ARROW keys to position it more precisely.</span></span> <span data-ttu-id="49fe9-107">또한 *맞춤선* 은 폼에 컨트롤을 정확 하 게 배치할 수 있도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="49fe9-107">Also, *snaplines* assist you in placing controls precisely on your form.</span></span> <span data-ttu-id="49fe9-108">자세한 내용은 [연습: 맞춤선을 사용 하 여 Windows Forms에서 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49fe9-108">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

## <a name="position-a-control-using-the-properties-window"></a><span data-ttu-id="49fe9-109">속성 창를 사용 하 여 컨트롤 배치</span><span class="sxs-lookup"><span data-stu-id="49fe9-109">Position a control using the Properties window</span></span>

1. <span data-ttu-id="49fe9-110">Visual Studio에서 배치 하려는 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="49fe9-110">In Visual Studio, select the control you want to position.</span></span>

2. <span data-ttu-id="49fe9-111">**속성** 창에서 쉼표로 구분 된 <xref:System.Windows.Forms.Control.Location%2A> 속성의 값을 입력 하 여 컨트롤을 컨테이너 내에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="49fe9-111">In the **Properties** window, enter values for the <xref:System.Windows.Forms.Control.Location%2A> property, separated by a comma, to position the control within its container.</span></span>

   <span data-ttu-id="49fe9-112">첫 번째 숫자 (X)는 컨테이너의 왼쪽 테두리에서의 거리입니다. 두 번째 숫자 (Y)는 컨테이너 영역의 위쪽 테두리에서 픽셀 단위로 측정 된 거리입니다.</span><span class="sxs-lookup"><span data-stu-id="49fe9-112">The first number (X) is the distance from the left border of the container; the second number (Y) is the distance from the upper border of the container area, measured in pixels.</span></span>

   > [!NOTE]
   > <span data-ttu-id="49fe9-113"><xref:System.Windows.Forms.Control.Location%2A> 속성을 확장 하 여 **X** 및 **Y** 값을 개별적으로 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49fe9-113">You can expand the <xref:System.Windows.Forms.Control.Location%2A> property to type the **X** and **Y** values individually.</span></span>

## <a name="position-a-control-programmatically"></a><span data-ttu-id="49fe9-114">프로그래밍 방식으로 컨트롤 배치</span><span class="sxs-lookup"><span data-stu-id="49fe9-114">Position a control programmatically</span></span>

1. <span data-ttu-id="49fe9-115">컨트롤의 <xref:System.Windows.Forms.Control.Location%2A> 속성을 <xref:System.Drawing.Point>설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="49fe9-115">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the control to a <xref:System.Drawing.Point>.</span></span>

    ```vb
    Button1.Location = New Point(100, 100)
    ```

    ```csharp
    button1.Location = new Point(100, 100);
    ```

    ```cpp
    button1->Location = Point(100, 100);
    ```

2. <span data-ttu-id="49fe9-116"><xref:System.Windows.Forms.Control.Left%2A> 하위 속성을 사용 하 여 컨트롤 위치의 X 좌표를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="49fe9-116">Change the X coordinate of the control's location using the <xref:System.Windows.Forms.Control.Left%2A> subproperty.</span></span>

    ```vb
    Button1.Left = 300
    ```

    ```csharp
    button1.Left = 300;
    ```

    ```cpp
    button1->Left = 300;
    ```

## <a name="increment-a-controls-location-programmatically"></a><span data-ttu-id="49fe9-117">컨트롤의 위치를 프로그래밍 방식으로 증가</span><span class="sxs-lookup"><span data-stu-id="49fe9-117">Increment a control's location programmatically</span></span>

<span data-ttu-id="49fe9-118"><xref:System.Windows.Forms.Control.Left%2A> 하위 속성을 설정 하 여 컨트롤의 X 좌표를 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="49fe9-118">Set the <xref:System.Windows.Forms.Control.Left%2A> subproperty to increment the X coordinate of the control.</span></span>

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
> <span data-ttu-id="49fe9-119"><xref:System.Windows.Forms.Control.Location%2A> 속성을 사용 하 여 컨트롤의 X 및 Y 위치를 동시에 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49fe9-119">Use the <xref:System.Windows.Forms.Control.Location%2A> property to set a control's X and Y positions simultaneously.</span></span> <span data-ttu-id="49fe9-120">위치를 개별적으로 설정 하려면 컨트롤의 <xref:System.Windows.Forms.Control.Left%2A> (**X**) 또는 <xref:System.Windows.Forms.Control.Top%2A> (**Y**) 하위 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="49fe9-120">To set a position individually, use the control's <xref:System.Windows.Forms.Control.Left%2A> (**X**) or <xref:System.Windows.Forms.Control.Top%2A> (**Y**) subproperty.</span></span> <span data-ttu-id="49fe9-121">단추 좌표를 포함 하는 <xref:System.Drawing.Point> 구조체의 X 좌표와 Y 좌표를 암시적으로 설정 하지 마십시오 .이 구조에는 단추의 좌표 복사본이 포함 되어 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="49fe9-121">Do not try to implicitly set the X and Y coordinates of the <xref:System.Drawing.Point> structure that represents the button's location, because this structure contains a copy of the button's coordinates.</span></span>

## <a name="see-also"></a><span data-ttu-id="49fe9-122">참조</span><span class="sxs-lookup"><span data-stu-id="49fe9-122">See also</span></span>

- [<span data-ttu-id="49fe9-123">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="49fe9-123">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="49fe9-124">연습: Windows Forms에서 맞춤선을 사용하여 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="49fe9-124">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="49fe9-125">연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="49fe9-125">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="49fe9-126">연습: FlowLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="49fe9-126">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="49fe9-127">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="49fe9-127">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="49fe9-128">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="49fe9-128">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="49fe9-129">기능별 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="49fe9-129">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- <span data-ttu-id="49fe9-130">[방법: Windows Forms의 화면 위치 설정](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="49fe9-130">[How to: Set the Screen Location of Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span></span>

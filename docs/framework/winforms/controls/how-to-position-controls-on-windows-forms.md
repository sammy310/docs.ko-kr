---
title: 컨트롤 배치
description: Visual Studio의 Windows Forms 디자이너 또는 Location 속성을 사용 하 여 컨트롤을 배치 하는 방법을 알아봅니다.
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
ms.openlocfilehash: 0aa3faade71e0f7e0a9d5e676327a80747524b8c
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904301"
---
# <a name="how-to-position-controls-on-windows-forms"></a><span data-ttu-id="f2ba3-103">방법: Windows Forms에 컨트롤 배치</span><span class="sxs-lookup"><span data-stu-id="f2ba3-103">How to: Position controls on Windows Forms</span></span>

<span data-ttu-id="f2ba3-104">컨트롤의 위치를 지정 하려면 Visual Studio에서 Windows Forms 디자이너를 사용 하거나 속성을 지정 합니다 <xref:System.Windows.Forms.Control.Location%2A> .</span><span class="sxs-lookup"><span data-stu-id="f2ba3-104">To position controls, use the Windows Forms Designer in Visual Studio or specify the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>

## <a name="position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a><span data-ttu-id="f2ba3-105">Windows Forms 디자이너의 디자인 화면에 컨트롤 배치</span><span class="sxs-lookup"><span data-stu-id="f2ba3-105">Position a control on the design surface of the Windows Forms Designer</span></span>

<span data-ttu-id="f2ba3-106">Visual Studio에서 마우스를 사용 하 여 컨트롤을 적절 한 위치로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba3-106">In Visual Studio, drag the control to the appropriate location with the mouse.</span></span>

> [!NOTE]
> <span data-ttu-id="f2ba3-107">컨트롤을 선택 하 고 화살표 키로 이동 하 여 더 정확 하 게 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba3-107">Select the control and move it with the ARROW keys to position it more precisely.</span></span> <span data-ttu-id="f2ba3-108">또한 *맞춤선* 은 폼에 컨트롤을 정확 하 게 배치할 수 있도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba3-108">Also, *snaplines* assist you in placing controls precisely on your form.</span></span> <span data-ttu-id="f2ba3-109">자세한 내용은 [연습: 맞춤선을 사용 하 여 Windows Forms에서 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f2ba3-109">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

## <a name="position-a-control-using-the-properties-window"></a><span data-ttu-id="f2ba3-110">속성 창를 사용 하 여 컨트롤 배치</span><span class="sxs-lookup"><span data-stu-id="f2ba3-110">Position a control using the Properties window</span></span>

1. <span data-ttu-id="f2ba3-111">Visual Studio에서 배치 하려는 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba3-111">In Visual Studio, select the control you want to position.</span></span>

2. <span data-ttu-id="f2ba3-112">**속성** 창에서 속성에 대 한 값을 <xref:System.Windows.Forms.Control.Location%2A> 쉼표로 구분 하 여 입력 하 여 해당 컨테이너 내에 컨트롤을 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba3-112">In the **Properties** window, enter values for the <xref:System.Windows.Forms.Control.Location%2A> property, separated by a comma, to position the control within its container.</span></span>

   <span data-ttu-id="f2ba3-113">첫 번째 숫자 (X)는 컨테이너의 왼쪽 테두리에서의 거리입니다. 두 번째 숫자 (Y)는 컨테이너 영역의 위쪽 테두리에서 픽셀 단위로 측정 된 거리입니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba3-113">The first number (X) is the distance from the left border of the container; the second number (Y) is the distance from the upper border of the container area, measured in pixels.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f2ba3-114">속성을 확장 <xref:System.Windows.Forms.Control.Location%2A> 하 여 **X** 및 **Y** 값을 개별적으로 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba3-114">You can expand the <xref:System.Windows.Forms.Control.Location%2A> property to type the **X** and **Y** values individually.</span></span>

## <a name="position-a-control-programmatically"></a><span data-ttu-id="f2ba3-115">프로그래밍 방식으로 컨트롤 배치</span><span class="sxs-lookup"><span data-stu-id="f2ba3-115">Position a control programmatically</span></span>

1. <span data-ttu-id="f2ba3-116"><xref:System.Windows.Forms.Control.Location%2A>컨트롤의 속성을로 설정 <xref:System.Drawing.Point> 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba3-116">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the control to a <xref:System.Drawing.Point>.</span></span>

    ```vb
    Button1.Location = New Point(100, 100)
    ```

    ```csharp
    button1.Location = new Point(100, 100);
    ```

    ```cpp
    button1->Location = Point(100, 100);
    ```

2. <span data-ttu-id="f2ba3-117">하위 속성을 사용 하 여 컨트롤 위치의 X 좌표를 변경 <xref:System.Windows.Forms.Control.Left%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba3-117">Change the X coordinate of the control's location using the <xref:System.Windows.Forms.Control.Left%2A> subproperty.</span></span>

    ```vb
    Button1.Left = 300
    ```

    ```csharp
    button1.Left = 300;
    ```

    ```cpp
    button1->Left = 300;
    ```

## <a name="increment-a-controls-location-programmatically"></a><span data-ttu-id="f2ba3-118">컨트롤의 위치를 프로그래밍 방식으로 증가</span><span class="sxs-lookup"><span data-stu-id="f2ba3-118">Increment a control's location programmatically</span></span>

<span data-ttu-id="f2ba3-119">하위 속성을 설정 <xref:System.Windows.Forms.Control.Left%2A> 하 여 컨트롤의 X 좌표를 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba3-119">Set the <xref:System.Windows.Forms.Control.Left%2A> subproperty to increment the X coordinate of the control.</span></span>

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
> <span data-ttu-id="f2ba3-120"><xref:System.Windows.Forms.Control.Location%2A>컨트롤의 X 및 Y 위치를 동시에 설정 하려면 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba3-120">Use the <xref:System.Windows.Forms.Control.Location%2A> property to set a control's X and Y positions simultaneously.</span></span> <span data-ttu-id="f2ba3-121">위치를 개별적으로 설정 하려면 컨트롤의 <xref:System.Windows.Forms.Control.Left%2A> (**X**) 또는 <xref:System.Windows.Forms.Control.Top%2A> (**Y**) 하위 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2ba3-121">To set a position individually, use the control's <xref:System.Windows.Forms.Control.Left%2A> (**X**) or <xref:System.Windows.Forms.Control.Top%2A> (**Y**) subproperty.</span></span> <span data-ttu-id="f2ba3-122"><xref:System.Drawing.Point>이 구조체는 단추의 좌표 복사본을 포함 하므로 단추의 위치를 나타내는 구조체의 X 및 Y 좌표를 암시적으로 설정 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="f2ba3-122">Do not try to implicitly set the X and Y coordinates of the <xref:System.Drawing.Point> structure that represents the button's location, because this structure contains a copy of the button's coordinates.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2ba3-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f2ba3-123">See also</span></span>

- [<span data-ttu-id="f2ba3-124">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f2ba3-124">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="f2ba3-125">연습: 맞춤선을 사용하여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="f2ba3-125">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="f2ba3-126">연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="f2ba3-126">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="f2ba3-127">연습: FlowLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="f2ba3-127">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="f2ba3-128">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="f2ba3-128">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="f2ba3-129">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f2ba3-129">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="f2ba3-130">기능별 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f2ba3-130">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- <span data-ttu-id="f2ba3-131">[방법: Windows Forms의 화면 위치 설정](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f2ba3-131">[How to: Set the Screen Location of Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span></span>

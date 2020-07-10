---
title: 개체 계층화
description: Windows Forms 컨트롤과 자식 폼에서 개체를 계층화 하 여 보다 복잡 한 사용자 인터페이스를 만드는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, layering
- controls [Windows Forms], layering
- z order
- controls [Windows Forms], positioning
- z-order
ms.assetid: 1acc4281-2976-4715-86f4-bda68134baaf
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 6269b09c56963fefd500b9e1e6c9d7f51f9619cf
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174512"
---
# <a name="how-to-layer-objects-on-windows-forms"></a><span data-ttu-id="b3770-103">방법: Windows Forms에서 개체 계층화</span><span class="sxs-lookup"><span data-stu-id="b3770-103">How to: Layer objects on Windows Forms</span></span>

<span data-ttu-id="b3770-104">복잡 한 사용자 인터페이스를 만들거나 MDI (다중 문서 인터페이스) 폼을 사용 하는 경우 더 복잡 한 UI (사용자 인터페이스)를 만들기 위해 컨트롤 및 자식 폼을 모두 계층화 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="b3770-104">When you create a complex user interface, or work with a multiple document interface (MDI) form, you will often want to layer both controls and child forms to create more complex user interfaces (UI).</span></span> <span data-ttu-id="b3770-105">그룹의 컨텍스트 내에서 컨트롤과 창을 이동 하 고 추적 하려면 *z 순서*를 조작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3770-105">To move and keep track of controls and windows within the context of a group, you manipulate their *z-order*.</span></span> <span data-ttu-id="b3770-106">Z 순서는 양식의 z 축 (깊이)을 따라 폼에 있는 컨트롤의 시각적 계층화입니다.</span><span class="sxs-lookup"><span data-stu-id="b3770-106">Z-order is the visual layering of controls on a form along the form's z-axis (depth).</span></span> <span data-ttu-id="b3770-107">Z 순서의 맨 위에 있는 창은 다른 모든 창과 겹칩니다.</span><span class="sxs-lookup"><span data-stu-id="b3770-107">The window at the top of the z-order overlaps all other windows.</span></span> <span data-ttu-id="b3770-108">다른 모든 창은 z 순서의 맨 아래에 있는 창과 겹칩니다.</span><span class="sxs-lookup"><span data-stu-id="b3770-108">All other windows overlap the window at the bottom of the z-order.</span></span>

## <a name="to-layer-controls-at-design-time"></a><span data-ttu-id="b3770-109">디자인 타임에 컨트롤을 계층화 하려면</span><span class="sxs-lookup"><span data-stu-id="b3770-109">To layer controls at design time</span></span>

1. <span data-ttu-id="b3770-110">Visual Studio에서 계층화 하려는 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3770-110">In Visual Studio, select a control that you want to layer.</span></span>

2. <span data-ttu-id="b3770-111">**서식** 메뉴에서 **순서**를 선택한 다음 맨 **앞으로 가져오기** 또는 **맨 뒤로 보내기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3770-111">On the **Format** menu, select **Order**, and then select **Bring To Front** or **Send To Back**.</span></span>

## <a name="to-layer-controls-programmatically"></a><span data-ttu-id="b3770-112">프로그래밍 방식으로 컨트롤을 계층화 하려면</span><span class="sxs-lookup"><span data-stu-id="b3770-112">To layer controls programmatically</span></span>

<span data-ttu-id="b3770-113"><xref:System.Windows.Forms.Control.BringToFront%2A>및 메서드를 사용 <xref:System.Windows.Forms.Control.SendToBack%2A> 하 여 컨트롤의 z 순서를 조작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3770-113">Use the <xref:System.Windows.Forms.Control.BringToFront%2A> and <xref:System.Windows.Forms.Control.SendToBack%2A> methods to manipulate the z-order of the controls.</span></span>

<span data-ttu-id="b3770-114">예를 들어, <xref:System.Windows.Forms.TextBox> 컨트롤이 `txtFirstName` 다른 컨트롤 아래에 있는 경우 맨 위에 표시 하려면 다음 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3770-114">For example, if a <xref:System.Windows.Forms.TextBox> control, `txtFirstName`, is underneath another control and you want to have it on top, use the following code:</span></span>

```vb
txtFirstName.BringToFront()
```

```csharp
txtFirstName.BringToFront();
```

```cpp
txtFirstName->BringToFront();
```

> [!NOTE]
> <span data-ttu-id="b3770-115">Windows Forms는 *제어 제약*을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3770-115">Windows Forms supports *control containment*.</span></span> <span data-ttu-id="b3770-116">컨트롤 포함에는 컨트롤 내의 많은 컨트롤과 같이 포함 하는 컨트롤 내에 많은 컨트롤을 배치 하는 작업이 포함 됩니다 <xref:System.Windows.Forms.RadioButton> <xref:System.Windows.Forms.GroupBox> .</span><span class="sxs-lookup"><span data-stu-id="b3770-116">Control containment involves placing a number of controls within a containing control, such as a number of <xref:System.Windows.Forms.RadioButton> controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="b3770-117">그런 다음 포함 하는 컨트롤 내에서 컨트롤을 계층화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3770-117">You can then layer the controls within the containing control.</span></span> <span data-ttu-id="b3770-118">그룹 상자를 이동 하면 컨트롤이 내부에 포함 되어 있기 때문에 컨트롤도 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3770-118">Moving the group box moves the controls as well, because they are contained inside it.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3770-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3770-119">See also</span></span>

- [<span data-ttu-id="b3770-120">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="b3770-120">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="b3770-121">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="b3770-121">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="b3770-122">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="b3770-122">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="b3770-123">기능별 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="b3770-123">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)

---
title: 개체 계층화
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
ms.openlocfilehash: 1615b9c4df222edd95cda9bceae622ba6f1d8d78
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736344"
---
# <a name="how-to-layer-objects-on-windows-forms"></a><span data-ttu-id="02d8c-102">방법: Windows Forms에서 개체 계층화</span><span class="sxs-lookup"><span data-stu-id="02d8c-102">How to: Layer objects on Windows Forms</span></span>

<span data-ttu-id="02d8c-103">복잡 한 사용자 인터페이스를 만들거나 MDI (다중 문서 인터페이스) 폼을 사용 하는 경우 더 복잡 한 UI (사용자 인터페이스)를 만들기 위해 컨트롤 및 자식 폼을 모두 계층화 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="02d8c-103">When you create a complex user interface, or work with a multiple document interface (MDI) form, you will often want to layer both controls and child forms to create more complex user interfaces (UI).</span></span> <span data-ttu-id="02d8c-104">그룹의 컨텍스트 내에서 컨트롤과 창을 이동 하 고 추적 하려면 *z 순서*를 조작 합니다.</span><span class="sxs-lookup"><span data-stu-id="02d8c-104">To move and keep track of controls and windows within the context of a group, you manipulate their *z-order*.</span></span> <span data-ttu-id="02d8c-105">Z 순서는 양식의 z 축 (깊이)을 따라 폼에 있는 컨트롤의 시각적 계층화입니다.</span><span class="sxs-lookup"><span data-stu-id="02d8c-105">Z-order is the visual layering of controls on a form along the form's z-axis (depth).</span></span> <span data-ttu-id="02d8c-106">Z 순서의 맨 위에 있는 창은 다른 모든 창과 겹칩니다.</span><span class="sxs-lookup"><span data-stu-id="02d8c-106">The window at the top of the z-order overlaps all other windows.</span></span> <span data-ttu-id="02d8c-107">다른 모든 창은 z 순서의 맨 아래에 있는 창과 겹칩니다.</span><span class="sxs-lookup"><span data-stu-id="02d8c-107">All other windows overlap the window at the bottom of the z-order.</span></span>

## <a name="to-layer-controls-at-design-time"></a><span data-ttu-id="02d8c-108">디자인 타임에 컨트롤을 계층화 하려면</span><span class="sxs-lookup"><span data-stu-id="02d8c-108">To layer controls at design time</span></span>

1. <span data-ttu-id="02d8c-109">Visual Studio에서 계층화 하려는 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02d8c-109">In Visual Studio, select a control that you want to layer.</span></span>

2. <span data-ttu-id="02d8c-110">**서식** 메뉴에서 **순서**를 선택한 다음 맨 **앞으로 가져오기** 또는 **맨 뒤로 보내기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="02d8c-110">On the **Format** menu, select **Order**, and then select **Bring To Front** or **Send To Back**.</span></span>

## <a name="to-layer-controls-programmatically"></a><span data-ttu-id="02d8c-111">프로그래밍 방식으로 컨트롤을 계층화 하려면</span><span class="sxs-lookup"><span data-stu-id="02d8c-111">To layer controls programmatically</span></span>

<span data-ttu-id="02d8c-112"><xref:System.Windows.Forms.Control.BringToFront%2A> 및 <xref:System.Windows.Forms.Control.SendToBack%2A> 메서드를 사용 하 여 컨트롤의 z 순서를 조작 합니다.</span><span class="sxs-lookup"><span data-stu-id="02d8c-112">Use the <xref:System.Windows.Forms.Control.BringToFront%2A> and <xref:System.Windows.Forms.Control.SendToBack%2A> methods to manipulate the z-order of the controls.</span></span>

<span data-ttu-id="02d8c-113">예를 들어 <xref:System.Windows.Forms.TextBox> 컨트롤 `txtFirstName`다른 컨트롤 아래에 있고 맨 위에 있는 경우 다음 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="02d8c-113">For example, if a <xref:System.Windows.Forms.TextBox> control, `txtFirstName`, is underneath another control and you want to have it on top, use the following code:</span></span>

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
> <span data-ttu-id="02d8c-114">Windows Forms는 *제어 제약*을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="02d8c-114">Windows Forms supports *control containment*.</span></span> <span data-ttu-id="02d8c-115">컨트롤 포함에는 포함 하는 컨트롤 내에 많은 컨트롤을 배치 하는 것이 포함 됩니다 (예: <xref:System.Windows.Forms.GroupBox> 컨트롤 내의 여러 <xref:System.Windows.Forms.RadioButton> 컨트롤).</span><span class="sxs-lookup"><span data-stu-id="02d8c-115">Control containment involves placing a number of controls within a containing control, such as a number of <xref:System.Windows.Forms.RadioButton> controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="02d8c-116">그런 다음 포함 하는 컨트롤 내에서 컨트롤을 계층화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d8c-116">You can then layer the controls within the containing control.</span></span> <span data-ttu-id="02d8c-117">그룹 상자를 이동 하면 컨트롤이 내부에 포함 되어 있기 때문에 컨트롤도 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="02d8c-117">Moving the group box moves the controls as well, because they are contained inside it.</span></span>

## <a name="see-also"></a><span data-ttu-id="02d8c-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="02d8c-118">See also</span></span>

- [<span data-ttu-id="02d8c-119">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="02d8c-119">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="02d8c-120">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="02d8c-120">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="02d8c-121">Windows Forms에서 사용할 컨트롤</span><span class="sxs-lookup"><span data-stu-id="02d8c-121">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="02d8c-122">기능별 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="02d8c-122">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)

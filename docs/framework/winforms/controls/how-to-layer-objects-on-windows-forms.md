---
title: '방법: Windows Forms에서 개체 계층화'
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
ms.openlocfilehash: 8d0abbf0f71ac176d17261a0ae863938c575bdaf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941078"
---
# <a name="how-to-layer-objects-on-windows-forms"></a><span data-ttu-id="9be61-102">방법: Windows Forms에서 개체 계층화</span><span class="sxs-lookup"><span data-stu-id="9be61-102">How to: Layer Objects on Windows Forms</span></span>
<span data-ttu-id="9be61-103">복잡 한 사용자 인터페이스를 만들거나 여러 문서 MDI (인터페이스) 폼을 사용할 때 더 복잡 한 UI (사용자 인터페이스) 자식 폼 및 컨트롤 계층 하려는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="9be61-103">When you create a complex user interface, or work with a multiple document interface (MDI) form, you will often want to layer both controls and child forms to create more complex user interfaces (UI).</span></span> <span data-ttu-id="9be61-104">이동 컨트롤 및 windows 그룹의 컨텍스트 내에서 한 추적을 z 순서 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be61-104">To move and keep track of controls and windows within the context of a group, you manipulate their z-order.</span></span> <span data-ttu-id="9be61-105">*Z 순서* 폼의 z 축 (깊이)에 따라 폼에서 컨트롤의 시각적 계층 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9be61-105">*Z-order* is the visual layering of controls on a form along the form's z-axis (depth).</span></span> <span data-ttu-id="9be61-106">Z-순서의 맨 위에 있는 창에는 다른 모든 windows 겹칩니다.</span><span class="sxs-lookup"><span data-stu-id="9be61-106">The window at the top of the z-order overlaps all other windows.</span></span> <span data-ttu-id="9be61-107">다른 모든 windows 겹치는 z-순서의 맨 아래에 있는 창입니다.</span><span class="sxs-lookup"><span data-stu-id="9be61-107">All other windows overlap the window at the bottom of the z-order.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9be61-108">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be61-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="9be61-109">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9be61-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="9be61-110">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9be61-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-layer-controls-at-design-time"></a><span data-ttu-id="9be61-111">디자인 타임에 컨트롤 계층</span><span class="sxs-lookup"><span data-stu-id="9be61-111">To layer controls at design time</span></span>  
  
1. <span data-ttu-id="9be61-112">계층에 있는 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9be61-112">Select a control that you want to layer.</span></span>  
  
2. <span data-ttu-id="9be61-113">에 **형식** 메뉴에서 **순서**를 클릭 하 고 **앞으로 가져오기** 또는 **맨 뒤로 보내기**합니다.</span><span class="sxs-lookup"><span data-stu-id="9be61-113">On the **Format** menu, point to **Order**, and then click **Bring To Front** or **Send To Back**.</span></span>  
  
### <a name="to-layer-controls-programmatically"></a><span data-ttu-id="9be61-114">컨트롤을 프로그래밍 방식으로 계층화</span><span class="sxs-lookup"><span data-stu-id="9be61-114">To layer controls programmatically</span></span>  
  
- <span data-ttu-id="9be61-115">사용 된 <xref:System.Windows.Forms.Control.BringToFront%2A> 및 <xref:System.Windows.Forms.Control.SendToBack%2A> 컨트롤의 z 순서를 조작 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="9be61-115">Use the <xref:System.Windows.Forms.Control.BringToFront%2A> and <xref:System.Windows.Forms.Control.SendToBack%2A> methods to manipulate the z-order of the controls.</span></span>  
  
     <span data-ttu-id="9be61-116">예를 들어 경우는 <xref:System.Windows.Forms.TextBox> 제어 `txtFirstName`는 아래 다른 제어 및 하려면 위쪽에 다음 코드를 사용:</span><span class="sxs-lookup"><span data-stu-id="9be61-116">For example, if a <xref:System.Windows.Forms.TextBox> control, `txtFirstName`, is underneath another control and you want to have it on top, use the following code:</span></span>  
  
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
>  <span data-ttu-id="9be61-117">Windows Forms에서 지 원하는 *컨트롤 포함*합니다.</span><span class="sxs-lookup"><span data-stu-id="9be61-117">Windows Forms supports *control containment*.</span></span> <span data-ttu-id="9be61-118">컨트롤 포함은 여러 다양 한 등을 포함 하는 컨트롤 내에서 컨트롤을 배치 <xref:System.Windows.Forms.RadioButton> 내에서 제어를 <xref:System.Windows.Forms.GroupBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9be61-118">Control containment involves placing a number of controls within a containing control, such as a number of <xref:System.Windows.Forms.RadioButton> controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="9be61-119">그런 다음 포함 하는 컨트롤 내에서 컨트롤을 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be61-119">You can then layer the controls within the containing control.</span></span> <span data-ttu-id="9be61-120">그 안에 포함 되므로 컨트롤을 이동 그룹 상자를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9be61-120">Moving the group box moves the controls as well, because they are contained inside it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9be61-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="9be61-121">See also</span></span>

- [<span data-ttu-id="9be61-122">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="9be61-122">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="9be61-123">Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="9be61-123">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="9be61-124">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="9be61-124">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="9be61-125">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="9be61-125">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="9be61-126">기능별 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="9be61-126">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)

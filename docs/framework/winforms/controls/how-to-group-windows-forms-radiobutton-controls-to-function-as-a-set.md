---
title: Set로 작동 하도록 RadioButton 컨트롤 그룹화
description: 다른 집합에 독립적으로 작동 하도록 Windows Forms RadioButton 컨트롤을 그룹화 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
ms.openlocfilehash: 9f6795330922e739cca1f2b5c11bb2ec68bb4e84
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325924"
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a><span data-ttu-id="6cb43-103">방법: Windows Forms RadioButton 컨트롤을 기능 집합으로 그룹화</span><span class="sxs-lookup"><span data-stu-id="6cb43-103">How to: Group Windows Forms RadioButton Controls to Function as a Set</span></span>
<span data-ttu-id="6cb43-104">Windows Forms <xref:System.Windows.Forms.RadioButton> 컨트롤은 사용자가 하나 이상의 설정 중에서 선택할 수 있도록 디자인 되었으며, 하나는 프로시저 또는 개체에 할당 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cb43-104">Windows Forms <xref:System.Windows.Forms.RadioButton> controls are designed to give users a choice among two or more settings, of which only one can be assigned to a procedure or object.</span></span> <span data-ttu-id="6cb43-105">예를 들어, 컨트롤 그룹이 <xref:System.Windows.Forms.RadioButton> 주문에 대 한 패키지 캐리어를 선택 하는 것으로 표시 될 수 있지만이 중 하나만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6cb43-105">For example, a group of <xref:System.Windows.Forms.RadioButton> controls may display a choice of package carriers for an order, but only one of the carriers will be used.</span></span> <span data-ttu-id="6cb43-106">따라서 <xref:System.Windows.Forms.RadioButton> 기능 그룹의 일부인 경우에도 한 번에 하나만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cb43-106">Therefore only one <xref:System.Windows.Forms.RadioButton> at a time can be selected, even if it is a part of a functional group.</span></span>  
  
 <span data-ttu-id="6cb43-107"><xref:System.Windows.Forms.Panel>컨트롤, 컨트롤, 폼 등의 컨테이너 내에서 라디오 단추를 그려서 그룹화 할 수 있습니다 <xref:System.Windows.Forms.GroupBox> .</span><span class="sxs-lookup"><span data-stu-id="6cb43-107">You group radio buttons by drawing them inside a container such as a <xref:System.Windows.Forms.Panel> control, a <xref:System.Windows.Forms.GroupBox> control, or a form.</span></span> <span data-ttu-id="6cb43-108">양식에 직접 추가 된 모든 라디오 단추는 하나의 그룹이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6cb43-108">All radio buttons that are added directly to a form become one group.</span></span> <span data-ttu-id="6cb43-109">별도의 그룹을 추가 하려면 패널 또는 그룹 상자 내에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb43-109">To add separate groups, you must place them inside panels or group boxes.</span></span> <span data-ttu-id="6cb43-110">패널 또는 그룹 상자에 대 한 자세한 내용은 [Panel 컨트롤 개요](panel-control-overview-windows-forms.md) 또는 [GroupBox 컨트롤 개요](groupbox-control-overview-windows-forms.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6cb43-110">For more information about panels or group boxes, see [Panel Control Overview](panel-control-overview-windows-forms.md) or [GroupBox Control Overview](groupbox-control-overview-windows-forms.md).</span></span>  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a><span data-ttu-id="6cb43-111">RadioButton 컨트롤을 다른 집합에 독립적으로 작동 하는 집합으로 그룹화 하려면</span><span class="sxs-lookup"><span data-stu-id="6cb43-111">To group RadioButton controls as a set to function independently of other sets</span></span>  
  
1. <span data-ttu-id="6cb43-112"><xref:System.Windows.Forms.GroupBox>또는 컨트롤을 <xref:System.Windows.Forms.Panel> **도구 상자** 의 **Windows Forms** 탭에서 폼으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="6cb43-112">Drag a <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab on the **Toolbox** onto the form.</span></span>  
  
2. <span data-ttu-id="6cb43-113"><xref:System.Windows.Forms.RadioButton>또는 컨트롤에 컨트롤을 그립니다 <xref:System.Windows.Forms.GroupBox> <xref:System.Windows.Forms.Panel> .</span><span class="sxs-lookup"><span data-stu-id="6cb43-113">Draw <xref:System.Windows.Forms.RadioButton> controls on the <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cb43-114">참조</span><span class="sxs-lookup"><span data-stu-id="6cb43-114">See also</span></span>

- <xref:System.Windows.Forms.RadioButton>
- [<span data-ttu-id="6cb43-115">RadioButton 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="6cb43-115">RadioButton Control Overview</span></span>](radiobutton-control-overview-windows-forms.md)
- [<span data-ttu-id="6cb43-116">Panel 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="6cb43-116">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="6cb43-117">GroupBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="6cb43-117">GroupBox Control Overview</span></span>](groupbox-control-overview-windows-forms.md)
- [<span data-ttu-id="6cb43-118">CheckBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="6cb43-118">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="6cb43-119">RadioButton 컨트롤</span><span class="sxs-lookup"><span data-stu-id="6cb43-119">RadioButton Control</span></span>](radiobutton-control-windows-forms.md)

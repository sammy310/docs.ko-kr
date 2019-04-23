---
title: '방법: Windows Forms RadioButton 컨트롤을 기능 집합으로 그룹화'
ms.date: 03/30/2017
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
ms.openlocfilehash: 857e61bc89e072aebcf34793d7e8504ece3318c7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59307268"
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a><span data-ttu-id="0a707-102">방법: Windows Forms RadioButton 컨트롤을 기능 집합으로 그룹화</span><span class="sxs-lookup"><span data-stu-id="0a707-102">How to: Group Windows Forms RadioButton Controls to Function as a Set</span></span>
<span data-ttu-id="0a707-103">Windows Forms <xref:System.Windows.Forms.RadioButton> 컨트롤은 사용자는 하나만 할당할 수는 프로시저 또는 개체 두 개 이상 설정 중에서 선택할 수 있도록 디자인 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0a707-103">Windows Forms <xref:System.Windows.Forms.RadioButton> controls are designed to give users a choice among two or more settings, of which only one can be assigned to a procedure or object.</span></span> <span data-ttu-id="0a707-104">예를 들어 그룹 <xref:System.Windows.Forms.RadioButton> 컨트롤을 주문에 대 한 패키지 운송 업체의을 표시할 수 있지만 운송 업체 중 하나에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a707-104">For example, a group of <xref:System.Windows.Forms.RadioButton> controls may display a choice of package carriers for an order, but only one of the carriers will be used.</span></span> <span data-ttu-id="0a707-105">따라서 하나의 <xref:System.Windows.Forms.RadioButton> 한 번에 선택할 수 있습니다, 기능 그룹의 일부인 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a707-105">Therefore only one <xref:System.Windows.Forms.RadioButton> at a time can be selected, even if it is a part of a functional group.</span></span>  
  
 <span data-ttu-id="0a707-106">와 같은 컨테이너 내에서 그려 라디오 단추 그룹을 <xref:System.Windows.Forms.Panel> 컨트롤을 <xref:System.Windows.Forms.GroupBox> 컨트롤 또는 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="0a707-106">You group radio buttons by drawing them inside a container such as a <xref:System.Windows.Forms.Panel> control, a <xref:System.Windows.Forms.GroupBox> control, or a form.</span></span> <span data-ttu-id="0a707-107">폼 될 하나의 그룹에 직접 추가 되는 모든 라디오 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="0a707-107">All radio buttons that are added directly to a form become one group.</span></span> <span data-ttu-id="0a707-108">별도 그룹을 추가 하려면 패널 이나 그룹 상자 안에 배치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a707-108">To add separate groups, you must place them inside panels or group boxes.</span></span> <span data-ttu-id="0a707-109">패널 이나 그룹 상자에 대 한 자세한 내용은 참조 하세요. [Panel 컨트롤 개요](panel-control-overview-windows-forms.md) 하거나 [GroupBox 컨트롤 개요](groupbox-control-overview-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0a707-109">For more information about panels or group boxes, see [Panel Control Overview](panel-control-overview-windows-forms.md) or [GroupBox Control Overview](groupbox-control-overview-windows-forms.md).</span></span>  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a><span data-ttu-id="0a707-110">다른 집합 독립적으로 함수 집합으로 그룹 RadioButton 컨트롤</span><span class="sxs-lookup"><span data-stu-id="0a707-110">To group RadioButton controls as a set to function independently of other sets</span></span>  
  
1. <span data-ttu-id="0a707-111">끌어서를 <xref:System.Windows.Forms.GroupBox> 또는 <xref:System.Windows.Forms.Panel> 에서 제어를 **Windows Forms** 탭의 **도구 상자** 폼 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a707-111">Drag a <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab on the **Toolbox** onto the form.</span></span>  
  
2. <span data-ttu-id="0a707-112">그릴 <xref:System.Windows.Forms.RadioButton> 컨트롤을 <xref:System.Windows.Forms.GroupBox> 또는 <xref:System.Windows.Forms.Panel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a707-112">Draw <xref:System.Windows.Forms.RadioButton> controls on the <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a707-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="0a707-113">See also</span></span>

- <xref:System.Windows.Forms.RadioButton>
- [<span data-ttu-id="0a707-114">RadioButton 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="0a707-114">RadioButton Control Overview</span></span>](radiobutton-control-overview-windows-forms.md)
- [<span data-ttu-id="0a707-115">Panel 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="0a707-115">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="0a707-116">GroupBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="0a707-116">GroupBox Control Overview</span></span>](groupbox-control-overview-windows-forms.md)
- [<span data-ttu-id="0a707-117">CheckBox 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="0a707-117">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="0a707-118">RadioButton 컨트롤</span><span class="sxs-lookup"><span data-stu-id="0a707-118">RadioButton Control</span></span>](radiobutton-control-windows-forms.md)

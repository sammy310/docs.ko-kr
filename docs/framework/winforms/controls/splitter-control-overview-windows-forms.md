---
title: Splitter 컨트롤 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- Splitter
helpviewer_keywords:
- Splitter control [Windows Forms], about Splitter control
ms.assetid: e2b6ab83-dfdd-40ec-9762-850702c82dcb
ms.openlocfilehash: 0477f68aaf67d4b29c491052999ff7784e736669
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176412"
---
# <a name="splitter-control-overview-windows-forms"></a><span data-ttu-id="ad4f9-102">Splitter 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="ad4f9-102">Splitter Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="ad4f9-103">하지만 <xref:System.Windows.Forms.SplitContainer> 대체 하 고 기능을 추가 합니다 <xref:System.Windows.Forms.Splitter> 이전 버전의 컨트롤 <xref:System.Windows.Forms.Splitter> 선택 하면 이전 버전과 호환성 및 향후 사용을 위해 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad4f9-103">Although <xref:System.Windows.Forms.SplitContainer> replaces and adds functionality to the <xref:System.Windows.Forms.Splitter> control of previous versions, <xref:System.Windows.Forms.Splitter> is retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="ad4f9-104">Windows Forms <xref:System.Windows.Forms.Splitter> 컨트롤은 런타임에 도킹 된 컨트롤의 크기를 조정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad4f9-104">Windows Forms <xref:System.Windows.Forms.Splitter> controls are used to resize docked controls at run time.</span></span> <span data-ttu-id="ad4f9-105"><xref:System.Windows.Forms.Splitter> 컨트롤은 Windows 탐색기와 데이터 창에는 서로 다른 시간에 다양 한 너비의 정보가 포함 되어 있는 데이터의 길이 다양 한 컨트롤과 폼에 자주 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad4f9-105">The <xref:System.Windows.Forms.Splitter> control is often used on forms with controls that have varying lengths of data to present, like Windows Explorer, whose data panes contain information of varying widths at different times.</span></span>  
  
## <a name="working-with-the-splitter-control"></a><span data-ttu-id="ad4f9-106">Splitter 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="ad4f9-106">Working with the Splitter Control</span></span>  
 <span data-ttu-id="ad4f9-107">Splitter 컨트롤을 크기를 조정할 수 있는 컨트롤의 도킹 되지 않은 가장자리 마우스 포인터를 가리키는 사용자, 포인터를 컨트롤의 크기를 조정할 수 있음을 나타내는 모양이 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4f9-107">When the user points the mouse pointer at the undocked edge of a control that can be resized by a splitter control, the pointer changes its appearance to indicate that the control can be resized.</span></span> <span data-ttu-id="ad4f9-108">Splitter 컨트롤을 사용 하 여 사용자의 크기를 바로 앞에 있는 도킹된 된 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="ad4f9-108">With the splitter control, the user can resize the docked control that is immediately before it.</span></span> <span data-ttu-id="ad4f9-109">따라서 런타임에 도킹된 된 컨트롤 크기를 조정 하려면 사용자를 사용 하려면 컨트롤 컨테이너의 가장자리에 도킹 하 고 해당 컨테이너의 같은 쪽에 splitter 컨트롤을 도킹 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4f9-109">Therefore, to enable the user to resize a docked control at run time, dock the control to be resized to an edge of a container, and then dock a splitter control to the same side of that container.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad4f9-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="ad4f9-110">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="ad4f9-111">방법: Windows Forms에서 컨트롤 도킹</span><span class="sxs-lookup"><span data-stu-id="ad4f9-111">How to: Dock Controls on Windows Forms</span></span>](how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="ad4f9-112">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ad4f9-112">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)

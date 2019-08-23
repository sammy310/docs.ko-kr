---
title: '방법: DockPanel 요소를 사용하여 공간 분할'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], partitioning space
- partitioning space [WPF]
ms.assetid: a219b9e5-b205-4438-89b5-0a137ac463ab
ms.openlocfilehash: d22a808ce3ab95e3b351408bf4cc372a335da553
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960195"
---
# <a name="how-to-partition-space-by-using-the-dockpanel-element"></a><span data-ttu-id="7cd7b-102">방법: DockPanel 요소를 사용하여 공간 분할</span><span class="sxs-lookup"><span data-stu-id="7cd7b-102">How to: Partition Space by Using the DockPanel Element</span></span>
<span data-ttu-id="7cd7b-103">다음 예제에서는 요소를 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] <xref:System.Windows.Controls.DockPanel> 사용 하 여 간단한 프레임 워크를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7cd7b-103">The following example creates a simple [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] framework using a <xref:System.Windows.Controls.DockPanel> element.</span></span> <span data-ttu-id="7cd7b-104">해당 자식 요소에 사용할 수 있는 파티션공간입니다.<xref:System.Windows.Controls.DockPanel></span><span class="sxs-lookup"><span data-stu-id="7cd7b-104">The <xref:System.Windows.Controls.DockPanel> partitions available space to its child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7cd7b-105">예제</span><span class="sxs-lookup"><span data-stu-id="7cd7b-105">Example</span></span>  
 <span data-ttu-id="7cd7b-106">이 예제에서는 연결 <xref:System.Windows.Controls.DockPanel.Dock%2A> 된 속성인 속성을 사용 하 여 분할 된 공간의에 <xref:System.Windows.Controls.Dock.Top> 동일한 <xref:System.Windows.Controls.Border> 두 개의 요소를 도킹 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cd7b-106">This example uses the <xref:System.Windows.Controls.DockPanel.Dock%2A> property, which is an attached property, to dock two identical <xref:System.Windows.Controls.Border> elements at the <xref:System.Windows.Controls.Dock.Top> of the partitioned space.</span></span> <span data-ttu-id="7cd7b-107">세 번째 <xref:System.Windows.Controls.Border> 요소는에 도킹 <xref:System.Windows.Controls.Dock.Left>되며 너비는 200 픽셀로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cd7b-107">A third <xref:System.Windows.Controls.Border> element is docked to the <xref:System.Windows.Controls.Dock.Left>, with its width set to 200 pixels.</span></span> <span data-ttu-id="7cd7b-108">네 번째 <xref:System.Windows.Controls.Border> 는 화면의에 도킹 <xref:System.Windows.Controls.Dock.Bottom> 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cd7b-108">A fourth <xref:System.Windows.Controls.Border> is docked to the <xref:System.Windows.Controls.Dock.Bottom> of the screen.</span></span> <span data-ttu-id="7cd7b-109">마지막 <xref:System.Windows.Controls.Border> 요소는 남은 공간을 자동으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="7cd7b-109">The last <xref:System.Windows.Controls.Border> element automatically fills the remaining space.</span></span>  
  
 [!code-cpp[DockPanelOvwSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
> <span data-ttu-id="7cd7b-110">기본적으로 <xref:System.Windows.Controls.DockPanel> 요소의 마지막 자식은 나머지 할당 되지 않은 공간을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="7cd7b-110">By default, the last child of a <xref:System.Windows.Controls.DockPanel> element fills the remaining unallocated space.</span></span> <span data-ttu-id="7cd7b-111">이 동작을 원하지 않으면 `LastChildFill="False"`을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7cd7b-111">If you do not want this behavior, set `LastChildFill="False"`.</span></span>  
  
 <span data-ttu-id="7cd7b-112">컴파일된 애플리케이션은 다음과 같은 새로운 UI를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7cd7b-112">The compiled application yields a new UI that looks like this.</span></span>  
  
 <span data-ttu-id="7cd7b-113">![일반적인 DockPanel 시나리오](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span><span class="sxs-lookup"><span data-stu-id="7cd7b-113">![A typical DockPanel scenario.](./media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cd7b-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="7cd7b-114">See also</span></span>

- <xref:System.Windows.Controls.DockPanel>
- [<span data-ttu-id="7cd7b-115">패널 개요</span><span class="sxs-lookup"><span data-stu-id="7cd7b-115">Panels Overview</span></span>](panels-overview.md)

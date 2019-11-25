---
title: '방법: StackPanel과 DockPanel 중 선택'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], StackPanel control compared to
- StackPanel control [WPF], DockPanel control compared to
- controls [WPF], StackPanel
ms.assetid: f9239086-451f-42e6-81f7-ef89ef349742
ms.openlocfilehash: bdf4b38e67a7856136224368e86609c135e5ad6f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976435"
---
# <a name="how-to-choose-between-stackpanel-and-dockpanel"></a><span data-ttu-id="2e9bb-102">방법: StackPanel과 DockPanel 중 선택</span><span class="sxs-lookup"><span data-stu-id="2e9bb-102">How to: Choose Between StackPanel and DockPanel</span></span>
<span data-ttu-id="2e9bb-103">이 예제에서는 <xref:System.Windows.Controls.Panel>에서 콘텐츠를 쌓을 때 <xref:System.Windows.Controls.StackPanel> 또는 <xref:System.Windows.Controls.DockPanel>를 사용 하도록 선택 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2e9bb-103">This example shows how to choose between using a <xref:System.Windows.Controls.StackPanel> or a <xref:System.Windows.Controls.DockPanel> when you stack content in a <xref:System.Windows.Controls.Panel>.</span></span>

## <a name="example"></a><span data-ttu-id="2e9bb-104">예제</span><span class="sxs-lookup"><span data-stu-id="2e9bb-104">Example</span></span>
 <span data-ttu-id="2e9bb-105"><xref:System.Windows.Controls.DockPanel> 또는 <xref:System.Windows.Controls.StackPanel>를 사용 하 여 자식 요소를 바인딩할 수 있지만 두 컨트롤이 항상 동일한 결과를 생성 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2e9bb-105">Although you can use either <xref:System.Windows.Controls.DockPanel> or <xref:System.Windows.Controls.StackPanel> to stack child elements, the two controls do not always produce the same results.</span></span> <span data-ttu-id="2e9bb-106">예를 들어 자식 요소를 배치한 순서는 <xref:System.Windows.Controls.DockPanel>의 자식 요소 크기에 영향을 줄 수 있지만 <xref:System.Windows.Controls.StackPanel>에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e9bb-106">For example, the order that you place child elements can affect the size of child elements in a <xref:System.Windows.Controls.DockPanel> but not in a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="2e9bb-107">이러한 다른 동작은 PositiveInfinity에서 스택 방향으로 측정 <xref:System.Windows.Controls.StackPanel> 때문에 발생 합니다 [.](xref:System.Double.PositiveInfinity) 그러나 <xref:System.Windows.Controls.DockPanel>는 사용 가능한 크기만 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e9bb-107">This different behavior occurs because <xref:System.Windows.Controls.StackPanel> measures in the direction of stacking at [Double.PositiveInfinity](xref:System.Double.PositiveInfinity); however, <xref:System.Windows.Controls.DockPanel> measures only the available size.</span></span>

 <span data-ttu-id="2e9bb-108">다음 예에서는 <xref:System.Windows.Controls.DockPanel>와 <xref:System.Windows.Controls.StackPanel>간의 이러한 주요 차이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2e9bb-108">The following example demonstrates this key difference between <xref:System.Windows.Controls.DockPanel> and <xref:System.Windows.Controls.StackPanel>.</span></span>

 [!code-cpp[StackPanelOvw4#1](~/samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](~/samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]

## <a name="see-also"></a><span data-ttu-id="2e9bb-109">참조</span><span class="sxs-lookup"><span data-stu-id="2e9bb-109">See also</span></span>

- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.DockPanel>
- [<span data-ttu-id="2e9bb-110">패널 개요</span><span class="sxs-lookup"><span data-stu-id="2e9bb-110">Panels Overview</span></span>](panels-overview.md)

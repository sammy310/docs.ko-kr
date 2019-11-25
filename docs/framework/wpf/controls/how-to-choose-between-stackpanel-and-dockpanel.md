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
# <a name="how-to-choose-between-stackpanel-and-dockpanel"></a>방법: StackPanel과 DockPanel 중 선택
이 예제에서는 <xref:System.Windows.Controls.Panel>에서 콘텐츠를 쌓을 때 <xref:System.Windows.Controls.StackPanel> 또는 <xref:System.Windows.Controls.DockPanel>를 사용 하도록 선택 하는 방법을 보여 줍니다.

## <a name="example"></a>예제
 <xref:System.Windows.Controls.DockPanel> 또는 <xref:System.Windows.Controls.StackPanel>를 사용 하 여 자식 요소를 바인딩할 수 있지만 두 컨트롤이 항상 동일한 결과를 생성 하는 것은 아닙니다. 예를 들어 자식 요소를 배치한 순서는 <xref:System.Windows.Controls.DockPanel>의 자식 요소 크기에 영향을 줄 수 있지만 <xref:System.Windows.Controls.StackPanel>에는 영향을 주지 않습니다. 이러한 다른 동작은 PositiveInfinity에서 스택 방향으로 측정 <xref:System.Windows.Controls.StackPanel> 때문에 발생 합니다 [.](xref:System.Double.PositiveInfinity) 그러나 <xref:System.Windows.Controls.DockPanel>는 사용 가능한 크기만 측정 합니다.

 다음 예에서는 <xref:System.Windows.Controls.DockPanel>와 <xref:System.Windows.Controls.StackPanel>간의 이러한 주요 차이점을 보여 줍니다.

 [!code-cpp[StackPanelOvw4#1](~/samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](~/samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]

## <a name="see-also"></a>참조

- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.DockPanel>
- [패널 개요](panels-overview.md)

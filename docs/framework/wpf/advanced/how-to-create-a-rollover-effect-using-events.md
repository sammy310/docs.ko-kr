---
title: '방법: 이벤트를 사용하여 롤오버 효과 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors of elements [WPF], changing
- rollover effect [WPF]
- element colors [WPF], changing
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
ms.openlocfilehash: 3996a3b9bb976dd5f2e5b675de3894bbaba7d9d3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960383"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a>방법: 이벤트를 사용하여 롤오버 효과 만들기
이 예제에서는 마우스 포인터가 들어가거나 요소가 차지 하는 영역을 벗어날 때 요소의 색을 변경 하는 방법을 보여 줍니다.  
  
 이 예제는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일과 코드 숨김으로 구성 되어 있습니다.  
  
> [!NOTE]
> 이 예제에서는 이벤트를 사용 하는 방법을 보여 주지만 동일한 효과를 얻기 위해 스타일에서를 <xref:System.Windows.Trigger> 사용 하는 것이 좋습니다. 자세한 내용은 [스타일 지정 및 템플릿](../controls/styling-and-templating.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] <xref:System.Windows.Input.Mouse.MouseEnter> 은를 <xref:System.Windows.Controls.Border> <xref:System.Windows.UIElement.MouseLeave> 기준 <xref:System.Windows.Controls.TextBlock>으로 구성 되는 사용자 인터페이스를 만들고 및 이벤트 처리기 <xref:System.Windows.Controls.Border>를에 연결 합니다.  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 다음 코드는 및 <xref:System.Windows.UIElement.MouseEnter> <xref:System.Windows.UIElement.MouseLeave> 이벤트 처리기를 만듭니다.  마우스 포인터가에 <xref:System.Windows.Controls.Border>들어가면의 배경이 <xref:System.Windows.Controls.Border> 빨강으로 변경 됩니다.  마우스 포인터가를 <xref:System.Windows.Controls.Border>벗어나면의 배경은 <xref:System.Windows.Controls.Border> 다시 흰색으로 변경 됩니다.  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]

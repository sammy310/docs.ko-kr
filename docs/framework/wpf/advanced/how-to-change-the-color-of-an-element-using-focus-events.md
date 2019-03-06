---
title: '방법: 포커스 이벤트를 사용하여 요소의 색 변경'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus events [WPF], changing element color for
- colors of elements [WPF], changing
- elements [WPF], changing color of
ms.assetid: 7e246802-3625-47a7-ae9d-c8a2a40fd040
ms.openlocfilehash: 0d2c297108da7af09e5f01551bdedc5f0ac5e9af
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361007"
---
# <a name="how-to-change-the-color-of-an-element-using-focus-events"></a>방법: 포커스 이벤트를 사용하여 요소의 색 변경
얻거나를 사용 하 여 포커스를 잃을 때 요소의 색을 변경 하는 방법을 보여 주는이 예제는 <xref:System.Windows.UIElement.GotFocus> 고 <xref:System.Windows.UIElement.LostFocus> 이벤트입니다.  
  
 이 예제는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일과 코드 숨김 파일입니다.  
  
## <a name="example"></a>예제  
 다음 [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] 두 개의 구성 된 사용자 인터페이스를 만들고 <xref:System.Windows.Controls.Button> 개체 및 연결에 대 한 이벤트 처리기를 <xref:System.Windows.UIElement.GotFocus> 및 <xref:System.Windows.UIElement.LostFocus> 이벤트는 <xref:System.Windows.Controls.Button> 개체입니다.  
  
 [!code-xaml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 다음 코드 숨김 만듭니다는 <xref:System.Windows.UIElement.GotFocus> 및 <xref:System.Windows.UIElement.LostFocus> 이벤트 처리기입니다.  경우는 <xref:System.Windows.Controls.Button> 키보드 포커스를 얻으면을 <xref:System.Windows.Controls.Control.Background%2A> 의 <xref:System.Windows.Controls.Button> 빨간색으로 변경 됩니다.  경우는 <xref:System.Windows.Controls.Button> 키보드 포커스를 잃을 합니다 <xref:System.Windows.Controls.Control.Background%2A> 의 <xref:System.Windows.Controls.Button> 흰색으로 다시 변경 됩니다.  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## <a name="see-also"></a>참고자료
- [입력 개요](input-overview.md)

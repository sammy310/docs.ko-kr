---
title: '방법: 탐지를 누른 키를 입력 합니다.'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: 1796127d33087a3fd4504d03f175f8afe5323630
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351864"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a>방법: 탐지를 누른 키를 입력 합니다.
시기를 감지 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Input.Key.Enter> 키보드의 키가 눌러져 있습니다.  
  
 이 예제는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일과 코드 숨김 파일입니다.  
  
## <a name="example"></a>예제  
 누를 때 합니다 <xref:System.Windows.Input.Key.Enter> 키를 <xref:System.Windows.Controls.TextBox>, 텍스트 상자에 입력의 다른 영역에 표시는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]합니다.  
  
 다음 [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] 구성 된 사용자 인터페이스를 만들고는 <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.TextBlock>, 및 <xref:System.Windows.Controls.TextBox>합니다.  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 다음 코드 숨김 만듭니다는 <xref:System.Windows.UIElement.KeyDown> 이벤트 처리기입니다.  키를 누를 경우는 <xref:System.Windows.Input.Key.Enter> 키를 메시지에 표시 됩니다는 <xref:System.Windows.Controls.TextBlock>합니다.  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a>참고자료
- [입력 개요](input-overview.md)
- [라우트된 이벤트 개요](routed-events-overview.md)

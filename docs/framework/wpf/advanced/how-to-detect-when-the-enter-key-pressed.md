---
title: '방법: Enter 키를 누르는 시점 감지'
description: Windows Presentation Foundation 키보드에서 Enter 키가 선택 된 경우를 검색 합니다. 이 예제는 XAML 및 코드 숨김으로 구성 되어 있습니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: a955f52ec7bf93b32c70259b27fb51747664ac2e
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163187"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a>방법: Enter 키를 누르는 시점 감지
이 예제에서는 키보드에서 키를 누르는 시기를 검색 하는 방법을 보여 줍니다 <xref:System.Windows.Input.Key.Enter> .  
  
 이 예제는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일과 코드 숨김으로 구성 되어 있습니다.  
  
## <a name="example"></a>예제  
 사용자가에서 키를 누르면 <xref:System.Windows.Input.Key.Enter> <xref:System.Windows.Controls.TextBox> 텍스트 상자의 입력이의 다른 영역에 나타납니다 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] .  
  
 다음 XAML은, 및로 구성 된 사용자 인터페이스를 만듭니다 <xref:System.Windows.Controls.StackPanel> <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Controls.TextBox> .  
  
 [!code-xaml[keydown#KeyDownUI](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 다음 코드는 <xref:System.Windows.UIElement.KeyDown> 이벤트 처리기를 만듭니다.  누른 키가 <xref:System.Windows.Input.Key.Enter> 키인 경우 메시지가에 표시 됩니다 <xref:System.Windows.Controls.TextBlock> .  
  
 [!code-csharp[keydown#KeyDownSample](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a>참고 항목

- [입력 개요](input-overview.md)
- [라우트된 이벤트 개요](routed-events-overview.md)

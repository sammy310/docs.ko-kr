---
title: '방법: 마우스 포인터를 따라 개체 크기 변경'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- following the mouse pointer (cursor)
- mouse pointer (cursor), making objects follow
- cursor (mouse pointer), making objects follow
ms.assetid: 50b20415-14bc-405c-baf3-2fb254fffde3
ms.openlocfilehash: b9b13b4eec3e42744ba2be6031ec841fb5f215e3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59107317"
---
# <a name="how-to-make-an-object-follow-the-mouse-pointer"></a>방법: 마우스 포인터를 따라 개체 크기 변경
이 예제에서는 화면에서 마우스 포인터를 움직이면 개체의 크기를 변경 하는 방법을 보여 줍니다.  
  
 예제에 포함 됩니다는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 만들어지는 파일의 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 및 이벤트 처리기를 만드는 코드 숨김 파일입니다.  
  
## <a name="example"></a>예제  
 다음 [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] 만듭니다는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], 구성 되는 <xref:System.Windows.Shapes.Ellipse> 내에 <xref:System.Windows.Controls.StackPanel>에 대 한 이벤트 처리기를 연결 하 고는 <xref:System.Windows.UIElement.MouseMove> 이벤트.  
  
 [!code-xaml[mouseMoveWithPointer#MouseMoveWithPointerXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 다음 코드 숨김 만듭니다는 <xref:System.Windows.UIElement.MouseMove> 이벤트 처리기입니다.  마우스 포인터를 이동 하면, 높이 및 너비는 <xref:System.Windows.Shapes.Ellipse> 증가 및 감소 됩니다.  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## <a name="see-also"></a>참고자료

- [입력 개요](input-overview.md)

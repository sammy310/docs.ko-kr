---
title: '방법: GridSplitter 표시'
ms.date: 03/30/2017
helpviewer_keywords:
- GridSplitter control [WPF], ensuring visibility of
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
ms.openlocfilehash: 0e1984241c07a69e2b350a61dc5873716c6fa5df
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375690"
---
# <a name="how-to-make-sure-that-a-gridsplitter-is-visible"></a>방법: GridSplitter 표시
있는지 확인 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.GridSplitter> 컨트롤에서 다른 컨트롤에 의해 숨겨지지 않은 <xref:System.Windows.Controls.Grid>합니다.  
  
## <a name="example"></a>예제  
 합니다 <xref:System.Windows.Controls.Panel.Children%2A> 의 한 <xref:System.Windows.Controls.Grid> 컨트롤 태그 또는 코드에서 정의 된 순서 대로 렌더링 됩니다. <xref:System.Windows.Controls.GridSplitter> 마지막 요소로 정의 하지 않는 경우 다른 컨트롤에서 컨트롤을 숨길 수 있습니다 합니다 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션 또는 다른를 제공 하는 경우 컨트롤에 더 높은 <xref:System.Windows.Controls.Panel.ZIndexProperty>합니다.  
  
 방지 하기 위해 숨겨진 <xref:System.Windows.Controls.GridSplitter> 컨트롤 중 하나를 수행 합니다.  
  
-   했는지 <xref:System.Windows.Controls.GridSplitter> 컨트롤은 마지막 <xref:System.Windows.Controls.Panel.Children%2A> 에 추가 된 <xref:System.Windows.Controls.Grid>합니다. 다음 예제와 <xref:System.Windows.Controls.GridSplitter> 에서 마지막 요소로 <xref:System.Windows.Controls.Panel.Children%2A> 의 컬렉션을 <xref:System.Windows.Controls.Grid>합니다.  
  
 [!code-xaml[GridSplitterSnips#GridSplitterLastChild](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
-   설정 된 <xref:System.Windows.Controls.Panel.ZIndexProperty> 에 <xref:System.Windows.Controls.GridSplitter> 숨길 수 있는 컨트롤 보다 높을 수. 다음 예제에서는 합니다 <xref:System.Windows.Controls.GridSplitter> 더 높은 제어 <xref:System.Windows.Controls.Panel.ZIndexProperty> 보다는 <xref:System.Windows.Controls.Button> 제어 합니다.  
  
 [!code-xaml[GridSplitterSnips#GridSplitterZIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
-   숨길 수 있는 컨트롤의 여백을 설정 합니다 <xref:System.Windows.Controls.GridSplitter> 있도록는 <xref:System.Windows.Controls.GridSplitter> 노출 됩니다. 다음 예제에서는 겹쳐져 컨트롤과 숨기기에 여백을 설정 하는 <xref:System.Windows.Controls.GridSplitter>합니다.  
  
 [!code-xaml[GridSplitterSnips#GridSplitterMargin](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Controls.GridSplitter>
- [방법 항목](gridsplitter-how-to-topics.md)

---
title: '방법: 요소의 높이 속성 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- height properties [WPF]
- Panel control [WPF], height properties of elements
ms.assetid: 5ab9e781-dbb8-469a-a3c8-cf38ce312647
ms.openlocfilehash: 6500af3c637092820e538d79894d600d617953bf
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124288"
---
# <a name="how-to-set-the-height-properties-of-an-element"></a>방법: 요소의 높이 속성 설정
## <a name="example"></a>예제  
 이 예제에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 4 개의 높이 관련 속성 간의 렌더링 동작 차이를 시각적으로 보여 줍니다.  
  
 <xref:System.Windows.FrameworkElement> 클래스는 요소의 높이 특성을 설명 하는 네 가지 속성을 노출 합니다. 이러한 네 가지 속성은 충돌할 수 있으며, 그에 따라 우선 순위를 설정 하는 값은 다음과 같이 결정 됩니다. <xref:System.Windows.FrameworkElement.MinHeight%2A> 값이 <xref:System.Windows.FrameworkElement.MaxHeight%2A> 값 보다 우선 하므로 <xref:System.Windows.FrameworkElement.Height%2A> 값 보다 우선적으로 적용 됩니다. 네 번째 속성인 <xref:System.Windows.FrameworkElement.ActualHeight%2A>은 읽기 전용 이며 레이아웃 프로세스와의 상호 작용에 따라 결정 되는 실제 높이를 보고 합니다.  
  
 다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 예제에서는 <xref:System.Windows.Shapes.Rectangle> 요소 (`rect1`)를 <xref:System.Windows.Controls.Canvas>의 자식으로 그립니다. <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>및 <xref:System.Windows.FrameworkElement.Height%2A>의 속성 값을 나타내는 일련의 <xref:System.Windows.Controls.ListBox> 요소를 사용 하 여 <xref:System.Windows.Shapes.Rectangle>의 높이 속성을 변경할 수 있습니다. 이러한 방식으로 각 속성의 우선 순위가 시각적으로 표시 됩니다.  
  
 [!code-xaml[HeightMinHeightMaxHeight#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xaml[HeightMinHeightMaxHeight#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 다음 코드 예제에서는 <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> 이벤트에서 발생 하는 이벤트를 처리 합니다. 각 처리기는 <xref:System.Windows.Controls.ListBox>의 입력을 사용 하 고, 값을 <xref:System.Double>로 구문 분석 하 고, 값을 지정 된 높이 관련 속성에 적용 합니다. 높이 값도 문자열로 변환 되 고 다양 한 <xref:System.Windows.Controls.TextBlock> 요소에 기록 됩니다 (해당 요소의 정의는 선택한 XAML에 표시 되지 않음).  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 전체 샘플은 [Height 속성 샘플](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties)을 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.ActualHeight%2A>
- <xref:System.Windows.FrameworkElement.MaxHeight%2A>
- <xref:System.Windows.FrameworkElement.MinHeight%2A>
- <xref:System.Windows.FrameworkElement.Height%2A>
- [요소의 너비 속성 설정](how-to-set-the-width-properties-of-an-element.md)
- [패널 개요](panels-overview.md)
- [Height 속성 샘플](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties)

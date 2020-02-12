---
title: '방법: 요소의 너비 속성 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- width properties [WPF]
- Panel control [WPF], width properties of elements
ms.assetid: 6ee04a9d-63f0-4f5b-a406-0a8cd4c35729
ms.openlocfilehash: 682929625612114d042e4619d8388617988b3c48
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124275"
---
# <a name="how-to-set-the-width-properties-of-an-element"></a>방법: 요소의 너비 속성 설정
## <a name="example"></a>예제  
 이 예제에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 4 개의 너비 관련 속성 간의 렌더링 동작 차이를 시각적으로 보여 줍니다.  
  
 <xref:System.Windows.FrameworkElement> 클래스는 요소의 너비 특성을 설명 하는 네 가지 속성을 노출 합니다. 이러한 네 가지 속성은 충돌할 수 있으며, 그에 따라 우선 순위를 설정 하는 값은 다음과 같이 결정 됩니다. <xref:System.Windows.FrameworkElement.MinWidth%2A> 값이 <xref:System.Windows.FrameworkElement.MaxWidth%2A> 값 보다 우선 하므로 <xref:System.Windows.FrameworkElement.Width%2A> 값 보다 우선적으로 적용 됩니다. 네 번째 속성인 <xref:System.Windows.FrameworkElement.ActualWidth%2A>은 읽기 전용 이며 레이아웃 프로세스와의 상호 작용에 따라 결정 되는 실제 너비를 보고 합니다.  
  
 다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 예제에서는 <xref:System.Windows.Shapes.Rectangle> 요소 (`rect1`)를 <xref:System.Windows.Controls.Canvas>의 자식으로 그립니다. <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>및 <xref:System.Windows.FrameworkElement.Width%2A>의 속성 값을 나타내는 일련의 <xref:System.Windows.Controls.ListBox> 요소를 사용 하 여 <xref:System.Windows.Shapes.Rectangle>의 너비 속성을 변경할 수 있습니다. 이러한 방식으로 각 속성의 우선 순위가 시각적으로 표시 됩니다.  
  
 [!code-xaml[WidthMinWidthMaxWidth#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#1)]  
[!code-xaml[WidthMinWidthMaxWidth#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#2)]  
  
 다음 코드 예제에서는 <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> 이벤트에서 발생 하는 이벤트를 처리 합니다. 각 사용자 지정 메서드는 <xref:System.Windows.Controls.ListBox>의 입력을 사용 하 고, 값을 <xref:System.Double>로 구문 분석 하 고, 값을 지정 된 너비와 관련 된 속성에 적용 합니다. 너비 값도 문자열로 변환 되 고 다양 한 <xref:System.Windows.Controls.TextBlock> 요소에 기록 됩니다 (해당 요소의 정의는 선택한 XAML에 표시 되지 않음).  
  
 [!code-csharp[WidthMinWidthMaxWidth#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml.cs#3)]
 [!code-vb[WidthMinWidthMaxWidth#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WidthMinWidthMaxWidth/VisualBasic/Window1.xaml.vb#3)]  
  
 전체 샘플은 [너비 속성 비교 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties)을 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.FrameworkElement.ActualWidth%2A>
- <xref:System.Windows.FrameworkElement.MaxWidth%2A>
- <xref:System.Windows.FrameworkElement.MinWidth%2A>
- <xref:System.Windows.FrameworkElement.Width%2A>
- [패널 개요](panels-overview.md)
- [요소의 높이 속성 설정](how-to-set-the-height-properties-of-an-element.md)
- [너비 속성 비교 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties)

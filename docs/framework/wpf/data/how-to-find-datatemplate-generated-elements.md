---
title: '방법: DataTemplate에서 생성된 요소 찾기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- finding DataTemplate elements [WPF]
- DataTemplate [WPF]
ms.assetid: bfcd564e-5e9e-451e-8641-a9b5c3cfac90
ms.openlocfilehash: 3b222880aa4eda32502e3dcece2fa5c0b57b7a51
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646429"
---
# <a name="how-to-find-datatemplate-generated-elements"></a>방법: DataTemplate에서 생성된 요소 찾기
이 예제에서는 <xref:System.Windows.DataTemplate>에서 생성되는 요소를 찾는 방법을 보여 주며 있습니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 일부 <xref:System.Windows.Controls.ListBox> XML 데이터에 바인딩된 a가 있습니다.  
  
 [!code-xaml[FindGeneratedItems#LB](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#lb)]  
  
 다음을 <xref:System.Windows.Controls.ListBox> <xref:System.Windows.DataTemplate>사용합니다.  
  
 [!code-xaml[FindGeneratedItems#DT](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#dt)]  
  
 <xref:System.Windows.DataTemplate> 특정 <xref:System.Windows.Controls.ListBoxItem>에 의해 <xref:System.Windows.Controls.TextBlock> 생성된 요소를 검색하려면 <xref:System.Windows.Controls.ListBoxItem>을 가져와서 <xref:System.Windows.Controls.ContentPresenter> 그 <xref:System.Windows.Controls.ListBoxItem>안에 있는 요소를 찾은 <xref:System.Windows.FrameworkTemplate.FindName%2A> 다음 <xref:System.Windows.DataTemplate> 에 설정된 <xref:System.Windows.Controls.ContentPresenter>에 대해 호출해야 합니다. 다음 예제에서는 이러한 단계를 수행하는 방법을 보여 주며 있습니다. 데모를 위해 이 예제에서는 <xref:System.Windows.DataTemplate>생성된 텍스트 블록의 텍스트 내용을 표시하는 메시지 상자를 만듭니다.  
  
 [!code-csharp[FindGeneratedItems#DTFindElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#dtfindelement)]
 [!code-vb[FindGeneratedItems#DTFindElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#dtfindelement)]  
  
 다음은 메서드를 사용하는 `FindVisualChild`의 구현입니다. <xref:System.Windows.Media.VisualTreeHelper>  
  
 [!code-csharp[FindGeneratedItems#FVC](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#fvc)]
 [!code-vb[FindGeneratedItems#FVC](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#fvc)]  
  
## <a name="see-also"></a>참고 항목

- [방법: ControlTemplate에서 생성된 요소 찾기](../controls/how-to-find-controltemplate-generated-elements.md)
- [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)
- [방법 도움말 항목](data-binding-how-to-topics.md)
- [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [WPF XAML 이름 범위](../advanced/wpf-xaml-namescopes.md)
- [WPF의 트리](../advanced/trees-in-wpf.md)

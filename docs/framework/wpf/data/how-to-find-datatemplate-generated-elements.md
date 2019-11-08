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
ms.openlocfilehash: 2cb3d73574cd207c0e06abe15f6a953a67cd5c78
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733432"
---
# <a name="how-to-find-datatemplate-generated-elements"></a>방법: DataTemplate에서 생성된 요소 찾기
이 예제에서는 <xref:System.Windows.DataTemplate>에서 생성 된 요소를 찾는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 일부 XML 데이터에 바인딩되는 <xref:System.Windows.Controls.ListBox> 있습니다.  
  
 [!code-xaml[FindGeneratedItems#LB](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#lb)]  
  
 <xref:System.Windows.Controls.ListBox>는 다음 <xref:System.Windows.DataTemplate>를 사용 합니다.  
  
 [!code-xaml[FindGeneratedItems#DT](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#dt)]  
  
 특정 <xref:System.Windows.Controls.ListBoxItem><xref:System.Windows.DataTemplate>에서 생성 된 <xref:System.Windows.Controls.TextBlock> 요소를 검색 하려면 <xref:System.Windows.Controls.ListBoxItem>를 가져오고 해당 <xref:System.Windows.Controls.ContentPresenter> 내의 <xref:System.Windows.Controls.ListBoxItem>을 찾은 다음에 설정 된 <xref:System.Windows.FrameworkTemplate.FindName%2A>에서 <xref:System.Windows.DataTemplate>를 호출 해야 합니다. <xref:System.Windows.Controls.ContentPresenter>입니다. 다음 예제에서는 이러한 단계를 수행 하는 방법을 보여 줍니다. 데모용으로이 예제에서는 <xref:System.Windows.DataTemplate>생성 된 텍스트 블록의 텍스트 내용을 표시 하는 메시지 상자를 만듭니다.  
  
 [!code-csharp[FindGeneratedItems#DTFindElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#dtfindelement)]
 [!code-vb[FindGeneratedItems#DTFindElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#dtfindelement)]  
  
 다음은 <xref:System.Windows.Media.VisualTreeHelper> 메서드를 사용 하는 `FindVisualChild`의 구현입니다.  
  
 [!code-csharp[FindGeneratedItems#FVC](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#fvc)]
 [!code-vb[FindGeneratedItems#FVC](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#fvc)]  
  
## <a name="see-also"></a>참조

- [방법: ControlTemplate에서 생성된 요소 찾기](../controls/how-to-find-controltemplate-generated-elements.md)
- [데이터 바인딩 개요](data-binding-overview.md)
- [방법 항목](data-binding-how-to-topics.md)
- [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [WPF XAML 이름 범위](../advanced/wpf-xaml-namescopes.md)
- [WPF의 트리](../advanced/trees-in-wpf.md)

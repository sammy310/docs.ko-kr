---
title: '방법: ListView의 사용자 지정 뷰 모드 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
ms.openlocfilehash: 3b9ca17bddcecb1895205fca76f0a489ecf25c4f
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243221"
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a>방법: ListView에 대한 사용자 지정 보기 모드 만들기

이 예제에서는 컨트롤에 <xref:System.Windows.Controls.ListView.View%2A> 대한 사용자 <xref:System.Windows.Controls.ListView> 지정 모드를 만드는 방법을 보여 주며 있습니다.  
  
## <a name="example"></a>예제  
 컨트롤에 대한 <xref:System.Windows.Controls.ViewBase> 사용자 지정 보기를 만들 <xref:System.Windows.Controls.ListView> 때 클래스를 사용해야 합니다. 다음 예제에서는 클래스에서 `PlainView` 파생 된 보기 모드라는 것을 보여 주며 <xref:System.Windows.Controls.ViewBase> 있습니다.  
  
 [!code-csharp[ListViewCustomView#PlainView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 사용자 지정 보기에 스타일을 적용하려면 <xref:System.Windows.Style> 클래스를 사용합니다. 다음 예제는 뷰 <xref:System.Windows.Style> 모드에 대한 a를 정의합니다. `PlainView` 이전 예제에서 이 스타일은 에 대해 <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> `PlainView`정의된 속성값으로 설정됩니다.  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 사용자 지정 뷰 모드에서 데이터 레이아웃을 정의하려면 개체를 정의합니다. <xref:System.Windows.DataTemplate> 다음 예제에서는 <xref:System.Windows.DataTemplate> `PlainView` 뷰 모드에서 데이터를 표시하는 데 사용할 수 있는 를 정의합니다.  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 다음 예제에서는 이전 예제에서 `PlainView` 정의된 뷰 모드를 <xref:System.Windows.DataTemplate> 사용하는 뷰 모드를 정의하는 <xref:System.Windows.ResourceKey> 방법을 보여 주습니다.  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 <xref:System.Windows.Controls.ListView> 속성을 리소스 키로 설정하는 경우 <xref:System.Windows.Controls.ListView.View%2A> 컨트롤은 사용자 지정 보기를 사용할 수 있습니다. 다음 예제에서는 `PlainView` <xref:System.Windows.Controls.ListView>에 대한 뷰 모드로 지정하는 방법을 보여 주며 있습니다.  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 전체 샘플은 [여러 뷰가 있는 ListView(C#)](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp) 또는 [여러 뷰가 있는 ListView(시각적 기본)를](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic)참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [방법 도움말 항목](listview-how-to-topics.md)
- [ListView 개요](listview-overview.md)
- [GridView 개요](gridview-overview.md)

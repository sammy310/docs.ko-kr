---
title: '방법: 선택에 따라 수집 및 표시 정보에 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], selecting data for views
- data binding [WPF], creating views of data collections
- data binding [WPF], selecting data for views
- data binding [WPF], binding to collections
ms.assetid: 952a7d76-dd29-49e5-86f5-32c4530e70eb
ms.openlocfilehash: 032a1d98e1aa80ea755f5922f79d43a796e9697e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459149"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a>방법: 선택에 따라 수집 및 표시 정보에 바인딩
간단한 마스터 세부 시나리오에서 <xref:System.Windows.Controls.ListBox>와 같은 데이터 바인딩된 <xref:System.Windows.Controls.ItemsControl> 있습니다. 사용자 선택에 따라 선택한 항목에 대 한 자세한 정보를 표시 합니다. 이 예제에서는이 시나리오를 구현 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 이 예제에서 `People`는 `Person` 클래스의 <xref:System.Collections.ObjectModel.ObservableCollection%601>입니다. 이 `Person` 클래스에는 세 가지 속성인 `FirstName`, `LastName`, `HomeTown``string`모든 형식이 포함 되어 있습니다.  
  
 [!code-xaml[CollectionBinding#Source](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 <xref:System.Windows.Controls.ContentControl>는 `Person` 정보를 표시 하는 방법을 정의 하는 다음 <xref:System.Windows.DataTemplate>를 사용 합니다.  
  
 [!code-xaml[CollectionBinding#DetailTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 다음은이 예제가 생성 하는 항목의 스크린샷입니다. <xref:System.Windows.Controls.ContentControl> 선택한 사용자의 다른 속성을 보여 줍니다.  
  
 ![컬렉션에 바인딩](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")  
  
 이 예에서는 다음과 같은 두 가지 사항을 확인 해야 합니다.  
  
1. <xref:System.Windows.Controls.ListBox> 및 <xref:System.Windows.Controls.ContentControl> 동일한 소스에 바인딩합니다. 두 컨트롤 모두 전체 컬렉션 개체에 바인딩되어 있기 때문에 두 바인딩의 <xref:System.Windows.Data.Binding.Path%2A> 속성이 지정 되지 않았습니다.  
  
2. 이 작업을 수행 하려면 <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> 속성을 `true`으로 설정 해야 합니다. 이 속성을 설정 하면 선택한 항목이 항상 <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>로 설정 됩니다. 또는 <xref:System.Windows.Controls.ListBox> <xref:System.Windows.Data.CollectionViewSource>에서 데이터를 가져오는 경우 선택 및 통화를 자동으로 동기화 합니다.  
  
 `Person` 클래스는 다음과 같은 방식으로 `ToString` 메서드를 재정의 합니다. 기본적으로 <xref:System.Windows.Controls.ListBox>는 `ToString`를 호출 하 고 바인딩된 컬렉션의 각 개체에 대 한 문자열 표현을 표시 합니다. 따라서 각 `Person` <xref:System.Windows.Controls.ListBox>에서 첫 번째 이름으로 표시 됩니다.  
  
 [!code-csharp[CollectionBinding#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a>참조

- [계층적 데이터에 마스터-세부 패턴 사용](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)
- [계층적 XML 데이터에 마스터-세부 패턴 사용](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)
- [데이터 템플릿 개요](data-templating-overview.md)
- [방법 항목](data-binding-how-to-topics.md)

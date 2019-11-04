---
title: '방법: 데이터 수집의 기본 뷰 가져오기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], creating views of
- data binding [WPF], creating views of data collections
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
ms.openlocfilehash: e82d252ed82e4d2e6d641e8b60e890cc93bb0427
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459123"
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a>방법: 데이터 수집의 기본 뷰 가져오기
뷰를 사용 하면 정렬, 필터링 또는 그룹화 기준에 따라 서로 다른 방식으로 동일한 데이터 컬렉션을 볼 수 있습니다. 모든 컬렉션에는 바인딩에서 컬렉션을 소스로 지정할 때 실제 바인딩 소스로 사용 되는 하나의 공유 기본 뷰가 있습니다. 이 예제에서는 컬렉션의 기본 뷰를 가져오는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 뷰를 만들려면 컬렉션에 대 한 개체 참조가 필요 합니다. 이 데이터 개체는 데이터 컨텍스트를 가져오거나, 데이터 소스의 속성을 가져오거나, 바인딩의 속성을 가져와서 사용자 고유의 코드 숨김이 지정 된 개체를 참조 하 여 가져올 수 있습니다. 이 예제에서는 데이터 개체의 <xref:System.Windows.FrameworkElement.DataContext%2A>을 가져오고이를 사용 하 여이 컬렉션에 대 한 기본 컬렉션 뷰를 직접 가져오는 방법을 보여 줍니다.  
  
 [!code-csharp[CollectionView#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 이 예제에서 root 요소는 <xref:System.Windows.Controls.StackPanel>입니다. <xref:System.Windows.FrameworkElement.DataContext%2A>는 *Mydatasource*로 설정 되며,이는 *Order* 개체의 <xref:System.Collections.ObjectModel.ObservableCollection%601> 데이터 공급자를 나타냅니다.  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 또는 <xref:System.Windows.Data.CollectionViewSource> 클래스를 사용 하 여 사용자 고유의 컬렉션 뷰를 인스턴스화하고 바인딩할 수 있습니다. 이 컬렉션 뷰는 직접 바인딩하는 컨트롤 에서만 공유 됩니다. 예제는 [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)에서 뷰를 만드는 방법 섹션을 참조 하세요.  
  
 컬렉션 뷰에서 제공 하는 기능에 대 한 예는 [뷰에서 데이터 정렬](how-to-sort-data-in-a-view.md), [뷰에서 데이터 필터링](how-to-filter-data-in-a-view.md)및 [데이터 CollectionView의 개체 탐색](how-to-navigate-through-the-objects-in-a-data-collectionview.md)을 참조 하세요.  
  
## <a name="see-also"></a>참조

- [XAML 데이터 정렬 및 그룹화](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [방법 항목](data-binding-how-to-topics.md)

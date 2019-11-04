---
title: '방법: 데이터 수집 뷰의 개체 탐색'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CollectionView [WPF], navigating through objects
- data binding [WPF], navigating through objects in data CollectionView
- navigating through objects in data CollectionView [WPF]
ms.assetid: fcd37590-bce1-4ac9-8b74-3b96c7458b8a
ms.openlocfilehash: 5ca386db89dcaa66d364d2ed7169c67393cebead
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459712"
---
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a>방법: 데이터 수집 뷰의 개체 탐색
뷰를 사용 하면 정렬, 필터링 또는 그룹화에 따라 서로 다른 방식으로 동일한 데이터 컬렉션을 볼 수 있습니다. 뷰는 또한 현재 레코드 포인터 개념을 제공 하 고 포인터 이동을 가능 하 게 합니다. 이 예제에서는 현재 개체를 가져오고 <xref:System.Windows.Data.CollectionView> 클래스에 제공 된 기능을 사용 하 여 데이터 컬렉션의 개체를 탐색 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 이 예제에서 `myCollectionView`은 바인딩된 컬렉션에 대 한 뷰입니다 <xref:System.Windows.Data.CollectionView> 개체입니다.  
  
 다음 예제에서 `OnButton`은 사용자가 데이터 컬렉션을 탐색할 수 있도록 하는 단추인 응용 프로그램의 `Previous` 및 `Next` 단추에 대 한 이벤트 처리기입니다. <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> 및 <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> 속성은 <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> 및 <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A>를 적절 하 게 호출할 수 있도록 현재 레코드 포인터가 목록의 시작 부분 및 끝 부분에 있는지 여부를 보고 합니다.  
  
 뷰의 <xref:System.Windows.Data.CollectionView.CurrentItem%2A> 속성은 컬렉션의 현재 순서 항목을 반환 하는 `Order` 캐스팅 됩니다.  
  
 [!code-csharp[CollectionView#OnButton](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a>참조

- [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)
- [뷰의 데이터 정렬](how-to-sort-data-in-a-view.md)
- [뷰에서 데이터 필터링](how-to-filter-data-in-a-view.md)
- [XAML 데이터 정렬 및 그룹화](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [방법 항목](data-binding-how-to-topics.md)

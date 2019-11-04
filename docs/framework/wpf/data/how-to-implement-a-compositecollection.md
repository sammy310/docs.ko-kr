---
title: '방법: CompositeCollection 구현'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
ms.openlocfilehash: b3450cdc476b7090251a06b5b2b2718d29e18209
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454032"
---
# <a name="how-to-implement-a-compositecollection"></a>방법: CompositeCollection 구현
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Data.CompositeCollection> 클래스를 사용 하 여 여러 컬렉션과 항목을 하나의 목록으로 표시 하는 방법을 보여 줍니다. 이 예제에서 `GreekGods`은 `GreekGod` 사용자 지정 개체의 <xref:System.Collections.ObjectModel.ObservableCollection%601>입니다. 데이터 템플릿을 정의 하 여 `GreekGod` 개체 및 `GreekHero` 개체가 각각 황금색 및 녹청 전경색으로 표시 되도록 합니다.  
  
 [!code-xaml[CompositeCollections#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Data.CollectionContainer>
- <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>
- <xref:System.Windows.Data.XmlDataProvider>
- <xref:System.Windows.DataTemplate>
- [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)
- [방법 항목](data-binding-how-to-topics.md)

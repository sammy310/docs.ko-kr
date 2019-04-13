---
title: '방법: CompositeCollection 구현'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
ms.openlocfilehash: 8361c2bfa9c125aeadf0a62ca86af1855e5c3dbc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091166"
---
# <a name="how-to-implement-a-compositecollection"></a>방법: CompositeCollection 구현
## <a name="example"></a>예제  
 다음 예제에서는 여러 컬렉션 및 항목을 사용 하 여 하나의 목록으로 표시 하는 방법의 <xref:System.Windows.Data.CompositeCollection> 클래스입니다. 이 예에서 `GreekGods` 되는 <xref:System.Collections.ObjectModel.ObservableCollection%601> 의 `GreekGod` 사용자 지정 개체입니다. 데이터 템플릿이 정의 되어 있도록 `GreekGod` 개체 및 `GreekHero` 개체 각각 황금색 및 녹청 전경색을 사용 하 여 표시 합니다.  
  
 [!code-xaml[CompositeCollections#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Data.CollectionContainer>
- <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>
- <xref:System.Windows.Data.XmlDataProvider>
- <xref:System.Windows.DataTemplate>
- [데이터 바인딩 개요](data-binding-overview.md)
- [방법 항목](data-binding-how-to-topics.md)

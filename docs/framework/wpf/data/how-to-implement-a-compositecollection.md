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
# <a name="how-to-implement-a-compositecollection"></a><span data-ttu-id="7cd97-102">방법: CompositeCollection 구현</span><span class="sxs-lookup"><span data-stu-id="7cd97-102">How to: Implement a CompositeCollection</span></span>
## <a name="example"></a><span data-ttu-id="7cd97-103">예제</span><span class="sxs-lookup"><span data-stu-id="7cd97-103">Example</span></span>  
 <span data-ttu-id="7cd97-104">다음 예제에서는 여러 컬렉션 및 항목을 사용 하 여 하나의 목록으로 표시 하는 방법의 <xref:System.Windows.Data.CompositeCollection> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="7cd97-104">The following example shows how to display multiple collections and items as one list using the <xref:System.Windows.Data.CompositeCollection> class.</span></span> <span data-ttu-id="7cd97-105">이 예에서 `GreekGods` 되는 <xref:System.Collections.ObjectModel.ObservableCollection%601> 의 `GreekGod` 사용자 지정 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="7cd97-105">In this example, `GreekGods` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `GreekGod` custom objects.</span></span> <span data-ttu-id="7cd97-106">데이터 템플릿이 정의 되어 있도록 `GreekGod` 개체 및 `GreekHero` 개체 각각 황금색 및 녹청 전경색을 사용 하 여 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cd97-106">Data templates are defined so that `GreekGod` objects and `GreekHero` objects appear with a gold and a cyan foreground color respectively.</span></span>  
  
 [!code-xaml[CompositeCollections#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7cd97-107">참고자료</span><span class="sxs-lookup"><span data-stu-id="7cd97-107">See also</span></span>

- <xref:System.Windows.Data.CollectionContainer>
- <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>
- <xref:System.Windows.Data.XmlDataProvider>
- <xref:System.Windows.DataTemplate>
- [<span data-ttu-id="7cd97-108">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="7cd97-108">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="7cd97-109">방법 항목</span><span class="sxs-lookup"><span data-stu-id="7cd97-109">How-to Topics</span></span>](data-binding-how-to-topics.md)

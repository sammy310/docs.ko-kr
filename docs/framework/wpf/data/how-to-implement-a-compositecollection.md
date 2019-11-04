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
# <a name="how-to-implement-a-compositecollection"></a><span data-ttu-id="6936e-102">방법: CompositeCollection 구현</span><span class="sxs-lookup"><span data-stu-id="6936e-102">How to: Implement a CompositeCollection</span></span>
## <a name="example"></a><span data-ttu-id="6936e-103">예제</span><span class="sxs-lookup"><span data-stu-id="6936e-103">Example</span></span>  
 <span data-ttu-id="6936e-104">다음 예제에서는 <xref:System.Windows.Data.CompositeCollection> 클래스를 사용 하 여 여러 컬렉션과 항목을 하나의 목록으로 표시 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6936e-104">The following example shows how to display multiple collections and items as one list using the <xref:System.Windows.Data.CompositeCollection> class.</span></span> <span data-ttu-id="6936e-105">이 예제에서 `GreekGods`은 `GreekGod` 사용자 지정 개체의 <xref:System.Collections.ObjectModel.ObservableCollection%601>입니다.</span><span class="sxs-lookup"><span data-stu-id="6936e-105">In this example, `GreekGods` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `GreekGod` custom objects.</span></span> <span data-ttu-id="6936e-106">데이터 템플릿을 정의 하 여 `GreekGod` 개체 및 `GreekHero` 개체가 각각 황금색 및 녹청 전경색으로 표시 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6936e-106">Data templates are defined so that `GreekGod` objects and `GreekHero` objects appear with a gold and a cyan foreground color respectively.</span></span>  
  
 [!code-xaml[CompositeCollections#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6936e-107">참조</span><span class="sxs-lookup"><span data-stu-id="6936e-107">See also</span></span>

- <xref:System.Windows.Data.CollectionContainer>
- <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>
- <xref:System.Windows.Data.XmlDataProvider>
- <xref:System.Windows.DataTemplate>
- [<span data-ttu-id="6936e-108">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="6936e-108">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="6936e-109">방법 항목</span><span class="sxs-lookup"><span data-stu-id="6936e-109">How-to Topics</span></span>](data-binding-how-to-topics.md)

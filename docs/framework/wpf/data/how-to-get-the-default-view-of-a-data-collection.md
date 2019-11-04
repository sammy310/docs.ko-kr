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
# <a name="how-to-get-the-default-view-of-a-data-collection"></a><span data-ttu-id="f18d0-102">방법: 데이터 수집의 기본 뷰 가져오기</span><span class="sxs-lookup"><span data-stu-id="f18d0-102">How to: Get the Default View of a Data Collection</span></span>
<span data-ttu-id="f18d0-103">뷰를 사용 하면 정렬, 필터링 또는 그룹화 기준에 따라 서로 다른 방식으로 동일한 데이터 컬렉션을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f18d0-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping criteria.</span></span> <span data-ttu-id="f18d0-104">모든 컬렉션에는 바인딩에서 컬렉션을 소스로 지정할 때 실제 바인딩 소스로 사용 되는 하나의 공유 기본 뷰가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f18d0-104">Every collection has one shared default view, which is used as the actual binding source when a binding specifies a collection as its source.</span></span> <span data-ttu-id="f18d0-105">이 예제에서는 컬렉션의 기본 뷰를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f18d0-105">This example shows how to get the default view of a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f18d0-106">예제</span><span class="sxs-lookup"><span data-stu-id="f18d0-106">Example</span></span>  
 <span data-ttu-id="f18d0-107">뷰를 만들려면 컬렉션에 대 한 개체 참조가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f18d0-107">To create the view, you need an object reference to the collection.</span></span> <span data-ttu-id="f18d0-108">이 데이터 개체는 데이터 컨텍스트를 가져오거나, 데이터 소스의 속성을 가져오거나, 바인딩의 속성을 가져와서 사용자 고유의 코드 숨김이 지정 된 개체를 참조 하 여 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f18d0-108">This data object can be obtained by referencing your own code-behind object, by getting the data context, by getting a property of the data source, or by getting a property of the binding.</span></span> <span data-ttu-id="f18d0-109">이 예제에서는 데이터 개체의 <xref:System.Windows.FrameworkElement.DataContext%2A>을 가져오고이를 사용 하 여이 컬렉션에 대 한 기본 컬렉션 뷰를 직접 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f18d0-109">This example shows how to get the <xref:System.Windows.FrameworkElement.DataContext%2A> of a data object and use it to directly obtain the default collection view for this collection.</span></span>  
  
 [!code-csharp[CollectionView#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 <span data-ttu-id="f18d0-110">이 예제에서 root 요소는 <xref:System.Windows.Controls.StackPanel>입니다.</span><span class="sxs-lookup"><span data-stu-id="f18d0-110">In this example, the root element is a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="f18d0-111"><xref:System.Windows.FrameworkElement.DataContext%2A>는 *Mydatasource*로 설정 되며,이는 *Order* 개체의 <xref:System.Collections.ObjectModel.ObservableCollection%601> 데이터 공급자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f18d0-111">The <xref:System.Windows.FrameworkElement.DataContext%2A> is set to *myDataSource*, which refers to a data provider that is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of *Order* objects.</span></span>  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 <span data-ttu-id="f18d0-112">또는 <xref:System.Windows.Data.CollectionViewSource> 클래스를 사용 하 여 사용자 고유의 컬렉션 뷰를 인스턴스화하고 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f18d0-112">Alternatively, you can instantiate and bind to your own collection view using the <xref:System.Windows.Data.CollectionViewSource> class.</span></span> <span data-ttu-id="f18d0-113">이 컬렉션 뷰는 직접 바인딩하는 컨트롤 에서만 공유 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f18d0-113">This collection view is only shared by controls that bind to it directly.</span></span> <span data-ttu-id="f18d0-114">예제는 [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)에서 뷰를 만드는 방법 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f18d0-114">For an example, see the How to Create a View section in the [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="f18d0-115">컬렉션 뷰에서 제공 하는 기능에 대 한 예는 [뷰에서 데이터 정렬](how-to-sort-data-in-a-view.md), [뷰에서 데이터 필터링](how-to-filter-data-in-a-view.md)및 [데이터 CollectionView의 개체 탐색](how-to-navigate-through-the-objects-in-a-data-collectionview.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f18d0-115">For examples of the functionality provided by a collection view, see [Sort Data in a View](how-to-sort-data-in-a-view.md), [Filter Data in a View](how-to-filter-data-in-a-view.md), and [Navigate Through the Objects in a Data CollectionView](how-to-navigate-through-the-objects-in-a-data-collectionview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f18d0-116">참조</span><span class="sxs-lookup"><span data-stu-id="f18d0-116">See also</span></span>

- [<span data-ttu-id="f18d0-117">XAML 데이터 정렬 및 그룹화</span><span class="sxs-lookup"><span data-stu-id="f18d0-117">Sort and Group Data Using a View in XAML</span></span>](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [<span data-ttu-id="f18d0-118">방법 항목</span><span class="sxs-lookup"><span data-stu-id="f18d0-118">How-to Topics</span></span>](data-binding-how-to-topics.md)

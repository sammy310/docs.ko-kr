---
title: '방법: 데이터 컬렉션의 기본 보기 가져오기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], creating views of
- data binding [WPF], creating views of data collections
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
ms.openlocfilehash: 746331e69ee1e5eee795a0e35202f4889b72c53f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61931523"
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a><span data-ttu-id="e59f6-102">방법: 데이터 컬렉션의 기본 보기 가져오기</span><span class="sxs-lookup"><span data-stu-id="e59f6-102">How to: Get the Default View of a Data Collection</span></span>
<span data-ttu-id="e59f6-103">뷰는 동일한 데이터 수집을 정렬, 필터링 또는 그룹화 기준에 따라 다른 방법으로 볼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e59f6-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping criteria.</span></span> <span data-ttu-id="e59f6-104">모든 컬렉션에 바인딩 소스로 컬렉션을 지정 하는 경우 실제 바인딩 소스로 사용 되는 하나의 공유 기본 보기를 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e59f6-104">Every collection has one shared default view, which is used as the actual binding source when a binding specifies a collection as its source.</span></span> <span data-ttu-id="e59f6-105">이 예제에는 컬렉션의 기본 보기를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e59f6-105">This example shows how to get the default view of a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e59f6-106">예제</span><span class="sxs-lookup"><span data-stu-id="e59f6-106">Example</span></span>  
 <span data-ttu-id="e59f6-107">보기를 만들려면 컬렉션에 개체 참조가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e59f6-107">To create the view, you need an object reference to the collection.</span></span> <span data-ttu-id="e59f6-108">데이터 원본의 속성 가져오기 또는 바인딩 속성을 가져오거나 데이터 컨텍스트를 가져와서 사용자 고유의 코드 숨김 개체를 참조 하 여이 데이터 개체를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e59f6-108">This data object can be obtained by referencing your own code-behind object, by getting the data context, by getting a property of the data source, or by getting a property of the binding.</span></span> <span data-ttu-id="e59f6-109">이 예제에서는 가져오는 방법을 보여 줍니다는 <xref:System.Windows.FrameworkElement.DataContext%2A> 데이터 개체 및 사용 하 여가이 컬렉션에 대 한 보기를 직접 기본 컬렉션을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e59f6-109">This example shows how to get the <xref:System.Windows.FrameworkElement.DataContext%2A> of a data object and use it to directly obtain the default collection view for this collection.</span></span>  
  
 [!code-csharp[CollectionView#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 <span data-ttu-id="e59f6-110">이 예제에서는 루트 요소는는 <xref:System.Windows.Controls.StackPanel>합니다.</span><span class="sxs-lookup"><span data-stu-id="e59f6-110">In this example, the root element is a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="e59f6-111"><xref:System.Windows.FrameworkElement.DataContext%2A> 로 설정 되어 *myDataSource*에 데이터 공급자를 참조 하는 <xref:System.Collections.ObjectModel.ObservableCollection%601> 의 *순서* 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e59f6-111">The <xref:System.Windows.FrameworkElement.DataContext%2A> is set to *myDataSource*, which refers to a data provider that is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of *Order* objects.</span></span>  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 <span data-ttu-id="e59f6-112">또는 인스턴스화할 수를 고유한 컬렉션 뷰를 사용 하 여 바인딩할는 <xref:System.Windows.Data.CollectionViewSource> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e59f6-112">Alternatively, you can instantiate and bind to your own collection view using the <xref:System.Windows.Data.CollectionViewSource> class.</span></span> <span data-ttu-id="e59f6-113">이 컬렉션 뷰에서 직접 바인딩되는 컨트롤에만 공유 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e59f6-113">This collection view is only shared by controls that bind to it directly.</span></span> <span data-ttu-id="e59f6-114">예를 들어 뷰 섹션 만들기 방법을 참조 합니다 [데이터 바인딩 개요](data-binding-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e59f6-114">For an example, see the How to Create a View section in the [Data Binding Overview](data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="e59f6-115">컬렉션 뷰에서 제공 하는 기능의 예제를 참조 하세요. [뷰에서 데이터 정렬](how-to-sort-data-in-a-view.md)를 [뷰에서 데이터 필터링](how-to-filter-data-in-a-view.md), 및 [개체 탐색 데이터 수집 뷰의](how-to-navigate-through-the-objects-in-a-data-collectionview.md).</span><span class="sxs-lookup"><span data-stu-id="e59f6-115">For examples of the functionality provided by a collection view, see [Sort Data in a View](how-to-sort-data-in-a-view.md), [Filter Data in a View](how-to-filter-data-in-a-view.md), and [Navigate Through the Objects in a Data CollectionView](how-to-navigate-through-the-objects-in-a-data-collectionview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e59f6-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="e59f6-116">See also</span></span>

- [<span data-ttu-id="e59f6-117">XAML 데이터 정렬 및 그룹화</span><span class="sxs-lookup"><span data-stu-id="e59f6-117">Sort and Group Data Using a View in XAML</span></span>](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [<span data-ttu-id="e59f6-118">방법 항목</span><span class="sxs-lookup"><span data-stu-id="e59f6-118">How-to Topics</span></span>](data-binding-how-to-topics.md)

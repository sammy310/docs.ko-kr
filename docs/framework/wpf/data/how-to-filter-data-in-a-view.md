---
title: '방법: 뷰에서 데이터 필터링'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [WPF], filtering data
- filtering data in views [WPF]
- data binding [WPF], filtering data in views
ms.assetid: c76e8606-4cc4-45a8-9110-e2ec66dc6afd
ms.openlocfilehash: f15bcfd1e3c4175f8b4b97244f120d5edbdec9b8
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453080"
---
# <a name="how-to-filter-data-in-a-view"></a><span data-ttu-id="cf704-102">방법: 뷰에서 데이터 필터링</span><span class="sxs-lookup"><span data-stu-id="cf704-102">How to: Filter Data in a View</span></span>
<span data-ttu-id="cf704-103">이 예제에서는 뷰에서 데이터를 필터링 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf704-103">This example shows how to filter data in a view.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf704-104">예제</span><span class="sxs-lookup"><span data-stu-id="cf704-104">Example</span></span>  
 <span data-ttu-id="cf704-105">필터를 만들려면 필터링 논리를 제공 하는 메서드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf704-105">To create a filter, define a method that provides the filtering logic.</span></span> <span data-ttu-id="cf704-106">메서드는 콜백으로 사용 되며 `object`형식의 매개 변수를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf704-106">The method is used as a callback and accepts a parameter of type `object`.</span></span> <span data-ttu-id="cf704-107">다음 메서드는 `filled` 속성이 "No"로 설정 된 모든 `Order` 개체를 반환 하 여 나머지 개체를 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf704-107">The following method returns all the `Order` objects with the `filled` property set to "No", filtering out the rest of the objects.</span></span>  
  
 [!code-csharp[SortFilter#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 <span data-ttu-id="cf704-108">그런 다음, 다음 예제와 같이 필터를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf704-108">You can then apply the filter, as shown in the following example.</span></span> <span data-ttu-id="cf704-109">이 예제에서 `myCollectionView`은 <xref:System.Windows.Data.ListCollectionView> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cf704-109">In this example, `myCollectionView` is a <xref:System.Windows.Data.ListCollectionView> object.</span></span>  
  
 [!code-csharp[SortFilter#Filter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 <span data-ttu-id="cf704-110">필터링을 실행 취소 하려면 <xref:System.Windows.Data.CollectionView.Filter%2A> 속성을 `null`로 설정 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf704-110">To undo filtering, you can set the <xref:System.Windows.Data.CollectionView.Filter%2A> property to `null`:</span></span>  
  
 [!code-csharp[SortFilter#Unfilter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 <span data-ttu-id="cf704-111">보기를 만들거나 가져오는 방법에 대 한 자세한 내용은 [데이터 컬렉션의 기본 뷰 가져오기](how-to-get-the-default-view-of-a-data-collection.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cf704-111">For information about how to create or obtain a view, see [Get the Default View of a Data Collection](how-to-get-the-default-view-of-a-data-collection.md).</span></span> <span data-ttu-id="cf704-112">전체 예제를 보려면 [뷰 샘플에서 항목 정렬 및 필터링](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/SortFilter)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cf704-112">For the complete example, see [Sorting and Filtering Items in a View Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/SortFilter).</span></span>  
  
 <span data-ttu-id="cf704-113">뷰 개체가 <xref:System.Windows.Data.CollectionViewSource> 개체에서 제공 되는 경우 <xref:System.Windows.Data.CollectionViewSource.Filter> 이벤트에 대 한 이벤트 처리기를 설정 하 여 필터링 논리를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf704-113">If your view object comes from a <xref:System.Windows.Data.CollectionViewSource> object, you apply filtering logic by setting an event handler for the <xref:System.Windows.Data.CollectionViewSource.Filter> event.</span></span> <span data-ttu-id="cf704-114">다음 예에서는 `listingDataView` <xref:System.Windows.Data.CollectionViewSource>의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="cf704-114">In the following example, `listingDataView` is an instance of <xref:System.Windows.Data.CollectionViewSource>.</span></span>  
  
 [!code-csharp[DataBindingLab#10](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 <span data-ttu-id="cf704-115">다음은 예제 `ShowOnlyBargainsFilter` 필터 이벤트 처리기의 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf704-115">The following shows the implementation of the example `ShowOnlyBargainsFilter` filter event handler.</span></span> <span data-ttu-id="cf704-116">이 이벤트 처리기는 <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> 속성을 사용 하 여 `CurrentPrice` $25 이상인 `AuctionItem` 개체를 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf704-116">This event handler uses the <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> property to filter out `AuctionItem` objects that have a `CurrentPrice` of $25 or greater.</span></span>  
  
 [!code-csharp[DataBindingLab#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="cf704-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf704-117">See also</span></span>

- <xref:System.Windows.Data.CollectionView.CanFilter%2A>
- <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>
- [<span data-ttu-id="cf704-118">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="cf704-118">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="cf704-119">뷰의 데이터 정렬</span><span class="sxs-lookup"><span data-stu-id="cf704-119">Sort Data in a View</span></span>](how-to-sort-data-in-a-view.md)
- [<span data-ttu-id="cf704-120">방법 항목</span><span class="sxs-lookup"><span data-stu-id="cf704-120">How-to Topics</span></span>](data-binding-how-to-topics.md)

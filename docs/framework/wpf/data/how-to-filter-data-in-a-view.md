---
title: '방법: 보기에서 데이터 필터링'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [WPF], filtering data
- filtering data in views [WPF]
- data binding [WPF], filtering data in views
ms.assetid: c76e8606-4cc4-45a8-9110-e2ec66dc6afd
ms.openlocfilehash: a31c07e6be26f67cc29813a14745ecf4a83ab98a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59147474"
---
# <a name="how-to-filter-data-in-a-view"></a><span data-ttu-id="ea0ec-102">방법: 보기에서 데이터 필터링</span><span class="sxs-lookup"><span data-stu-id="ea0ec-102">How to: Filter Data in a View</span></span>
<span data-ttu-id="ea0ec-103">이 예에서는 뷰에서 데이터를 필터링 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ea0ec-103">This example shows how to filter data in a view.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea0ec-104">예제</span><span class="sxs-lookup"><span data-stu-id="ea0ec-104">Example</span></span>  
 <span data-ttu-id="ea0ec-105">필터를 만들려면 필터링 논리를 제공 하는 메서드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea0ec-105">To create a filter, define a method that provides the filtering logic.</span></span> <span data-ttu-id="ea0ec-106">메서드는 콜백으로 사용 및 형식 매개 변수를 받아들이고 `object`합니다.</span><span class="sxs-lookup"><span data-stu-id="ea0ec-106">The method is used as a callback and accepts a parameter of type `object`.</span></span> <span data-ttu-id="ea0ec-107">다음 메서드는 모두 반환 합니다 `Order` 사용 하 여 개체를 `filled` 속성이 개체의 나머지 부분을 필터링 "아니요"로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea0ec-107">The following method returns all the `Order` objects with the `filled` property set to "No", filtering out the rest of the objects.</span></span>  
  
 [!code-csharp[SortFilter#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 <span data-ttu-id="ea0ec-108">다음 예제에 나와 있는 것 처럼 필터를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea0ec-108">You can then apply the filter, as shown in the following example.</span></span> <span data-ttu-id="ea0ec-109">이 예에서 `myCollectionView` 되는 <xref:System.Windows.Data.ListCollectionView> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ea0ec-109">In this example, `myCollectionView` is a <xref:System.Windows.Data.ListCollectionView> object.</span></span>  
  
 [!code-csharp[SortFilter#Filter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 <span data-ttu-id="ea0ec-110">필터링을 실행 취소 하려면 설정 합니다 <xref:System.Windows.Data.CollectionView.Filter%2A> 속성을 `null`:</span><span class="sxs-lookup"><span data-stu-id="ea0ec-110">To undo filtering, you can set the <xref:System.Windows.Data.CollectionView.Filter%2A> property to `null`:</span></span>  
  
 [!code-csharp[SortFilter#Unfilter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 <span data-ttu-id="ea0ec-111">또는 보고 하는 방법에 대 한 정보를 참조 하세요 [데이터 컬렉션의 기본 뷰 가져오기](how-to-get-the-default-view-of-a-data-collection.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ea0ec-111">For information about how to create or obtain a view, see [Get the Default View of a Data Collection](how-to-get-the-default-view-of-a-data-collection.md).</span></span> <span data-ttu-id="ea0ec-112">전체 예제를 참조 하세요 [정렬 및 필터링 항목 보기 샘플에서](https://go.microsoft.com/fwlink/?LinkID=160040)합니다.</span><span class="sxs-lookup"><span data-stu-id="ea0ec-112">For the complete example, see [Sorting and Filtering Items in a View Sample](https://go.microsoft.com/fwlink/?LinkID=160040).</span></span>  
  
 <span data-ttu-id="ea0ec-113">보기 개체에서 제공 되는 경우는 <xref:System.Windows.Data.CollectionViewSource> 개체에 대 한 이벤트 처리기를 설정 하 여 필터링 논리를 적용 합니다 <xref:System.Windows.Data.CollectionViewSource.Filter> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="ea0ec-113">If your view object comes from a <xref:System.Windows.Data.CollectionViewSource> object, you apply filtering logic by setting an event handler for the <xref:System.Windows.Data.CollectionViewSource.Filter> event.</span></span> <span data-ttu-id="ea0ec-114">다음 예에서 `listingDataView` 의 인스턴스가 <xref:System.Windows.Data.CollectionViewSource>합니다.</span><span class="sxs-lookup"><span data-stu-id="ea0ec-114">In the following example, `listingDataView` is an instance of <xref:System.Windows.Data.CollectionViewSource>.</span></span>  
  
 [!code-csharp[DataBindingLab#10](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 <span data-ttu-id="ea0ec-115">다음은 예제 구현의 `ShowOnlyBargainsFilter` 필터 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="ea0ec-115">The following shows the implementation of the example `ShowOnlyBargainsFilter` filter event handler.</span></span> <span data-ttu-id="ea0ec-116">이 이벤트 처리기에서 사용 합니다 <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> 속성을 필터링 `AuctionItem` 있는 개체는 `CurrentPrice` 25 달러 이상의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea0ec-116">This event handler uses the <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> property to filter out `AuctionItem` objects that have a `CurrentPrice` of $25 or greater.</span></span>  
  
 [!code-csharp[DataBindingLab#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="ea0ec-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="ea0ec-117">See also</span></span>

- <xref:System.Windows.Data.CollectionView.CanFilter%2A>
- <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>
- [<span data-ttu-id="ea0ec-118">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="ea0ec-118">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="ea0ec-119">뷰의 데이터 정렬</span><span class="sxs-lookup"><span data-stu-id="ea0ec-119">Sort Data in a View</span></span>](how-to-sort-data-in-a-view.md)
- [<span data-ttu-id="ea0ec-120">방법 항목</span><span class="sxs-lookup"><span data-stu-id="ea0ec-120">How-to Topics</span></span>](data-binding-how-to-topics.md)

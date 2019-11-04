---
title: '방법: 뷰의 데이터 정렬'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], sorting data in views
- data binding [WPF], grouping data in views
- grouping data in views [WPF]
- views [WPF], sorting data
- views [WPF], grouping data
- sorting data in views [WPF]
ms.assetid: f4c43578-01b7-4774-a953-acb95a13b94a
ms.openlocfilehash: 14314ed019f9194a657787bd767ae68615e94ac7
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454833"
---
# <a name="how-to-sort-data-in-a-view"></a><span data-ttu-id="952a7-102">방법: 뷰의 데이터 정렬</span><span class="sxs-lookup"><span data-stu-id="952a7-102">How to: Sort Data in a View</span></span>
<span data-ttu-id="952a7-103">이 예제에서는 뷰에서 데이터를 정렬 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="952a7-103">This example describes how to sort data in a view.</span></span>  
  
## <a name="example"></a><span data-ttu-id="952a7-104">예제</span><span class="sxs-lookup"><span data-stu-id="952a7-104">Example</span></span>  
 <span data-ttu-id="952a7-105">다음 예에서는 간단한 <xref:System.Windows.Controls.ListBox>와 <xref:System.Windows.Controls.Button>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="952a7-105">The following example creates a simple <xref:System.Windows.Controls.ListBox> and a <xref:System.Windows.Controls.Button>:</span></span>  
  
 [!code-xaml[ListBoxSort_snip#HowTo](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 <span data-ttu-id="952a7-106">단추의 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트 처리기에는 <xref:System.Windows.Controls.ListBox> 항목을 내림차순으로 정렬 하는 논리가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="952a7-106">The <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler of the button contains logic to sort the items in the <xref:System.Windows.Controls.ListBox> in the descending order.</span></span> <span data-ttu-id="952a7-107">이렇게 하려면 <xref:System.Windows.Controls.ListBox>에 항목을 추가 하 여 <xref:System.Windows.Controls.ListBox><xref:System.Windows.Controls.ItemCollection>에 추가 하 고 <xref:System.Windows.Controls.ItemCollection> <xref:System.Windows.Data.CollectionView> 클래스에서 파생 되므로이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="952a7-107">You can do this because adding items to a <xref:System.Windows.Controls.ListBox> this way adds them to the <xref:System.Windows.Controls.ItemCollection> of the <xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.ItemCollection> derives from the <xref:System.Windows.Data.CollectionView> class.</span></span> <span data-ttu-id="952a7-108"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 속성을 사용 하 여 <xref:System.Windows.Controls.ListBox>를 컬렉션에 바인딩하는 경우 동일한 기술을 사용 하 여 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="952a7-108">If you are binding your <xref:System.Windows.Controls.ListBox> to a collection using the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property, you can use the same technique to sort.</span></span>  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 <span data-ttu-id="952a7-109">View 개체에 대 한 참조가 있으면 동일한 기술을 사용 하 여 다른 컬렉션 뷰의 내용을 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="952a7-109">As long as you have a reference to the view object, you can use the same technique to sort the content of other collection views.</span></span> <span data-ttu-id="952a7-110">뷰를 가져오는 방법에 대 한 예제는 [데이터 컬렉션의 기본 뷰 가져오기](how-to-get-the-default-view-of-a-data-collection.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="952a7-110">For an example of how to obtain a view, see [Get the Default View of a Data Collection](how-to-get-the-default-view-of-a-data-collection.md).</span></span> <span data-ttu-id="952a7-111">또 다른 예를 보려면 [머리글을 클릭할 때 GridView 열 정렬](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="952a7-111">For another example, see [Sort a GridView Column When a Header Is Clicked](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).</span></span> <span data-ttu-id="952a7-112">보기에 대 한 자세한 내용은 [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)에서 컬렉션에 바인딩을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="952a7-112">For more information about views, see Binding to Collections in [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="952a7-113">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 정렬 논리를 적용 하는 방법에 대 한 예제는 [XAML에서 뷰를 사용 하 여 데이터 정렬 및 그룹화](how-to-sort-and-group-data-using-a-view-in-xaml.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="952a7-113">For an example of how to apply sorting logic in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], see [Sort and Group Data Using a View in XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="952a7-114">참조</span><span class="sxs-lookup"><span data-stu-id="952a7-114">See also</span></span>

- <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>
- [<span data-ttu-id="952a7-115">헤더를 클릭하면 GridView 열 정렬</span><span class="sxs-lookup"><span data-stu-id="952a7-115">Sort a GridView Column When a Header Is Clicked</span></span>](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)
- [<span data-ttu-id="952a7-116">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="952a7-116">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="952a7-117">뷰에서 데이터 필터링</span><span class="sxs-lookup"><span data-stu-id="952a7-117">Filter Data in a View</span></span>](how-to-filter-data-in-a-view.md)
- [<span data-ttu-id="952a7-118">방법 항목</span><span class="sxs-lookup"><span data-stu-id="952a7-118">How-to Topics</span></span>](data-binding-how-to-topics.md)

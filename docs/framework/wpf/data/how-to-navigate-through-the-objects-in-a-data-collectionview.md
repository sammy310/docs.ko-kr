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
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a><span data-ttu-id="5f200-102">방법: 데이터 수집 뷰의 개체 탐색</span><span class="sxs-lookup"><span data-stu-id="5f200-102">How to: Navigate Through the Objects in a Data CollectionView</span></span>
<span data-ttu-id="5f200-103">뷰를 사용 하면 정렬, 필터링 또는 그룹화에 따라 서로 다른 방식으로 동일한 데이터 컬렉션을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f200-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping.</span></span> <span data-ttu-id="5f200-104">뷰는 또한 현재 레코드 포인터 개념을 제공 하 고 포인터 이동을 가능 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f200-104">Views also provide a current record pointer concept and enable moving the pointer.</span></span> <span data-ttu-id="5f200-105">이 예제에서는 현재 개체를 가져오고 <xref:System.Windows.Data.CollectionView> 클래스에 제공 된 기능을 사용 하 여 데이터 컬렉션의 개체를 탐색 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5f200-105">This example shows how to get the current object as well as navigate through the objects in a data collection using the functionality provided in the <xref:System.Windows.Data.CollectionView> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f200-106">예제</span><span class="sxs-lookup"><span data-stu-id="5f200-106">Example</span></span>  
 <span data-ttu-id="5f200-107">이 예제에서 `myCollectionView`은 바인딩된 컬렉션에 대 한 뷰입니다 <xref:System.Windows.Data.CollectionView> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5f200-107">In this example, `myCollectionView` is a <xref:System.Windows.Data.CollectionView> object that is a view over a bound collection.</span></span>  
  
 <span data-ttu-id="5f200-108">다음 예제에서 `OnButton`은 사용자가 데이터 컬렉션을 탐색할 수 있도록 하는 단추인 응용 프로그램의 `Previous` 및 `Next` 단추에 대 한 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="5f200-108">In the following example, `OnButton` is an event handler for the `Previous` and `Next` buttons in an application, which are buttons that allow the user to navigate the data collection.</span></span> <span data-ttu-id="5f200-109"><xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> 및 <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> 속성은 <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> 및 <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A>를 적절 하 게 호출할 수 있도록 현재 레코드 포인터가 목록의 시작 부분 및 끝 부분에 있는지 여부를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f200-109">Note that the <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> and <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> properties report whether the current record pointer has come to the beginning and the end of the list respectively so that <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> and <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> can be called as appropriately.</span></span>  
  
 <span data-ttu-id="5f200-110">뷰의 <xref:System.Windows.Data.CollectionView.CurrentItem%2A> 속성은 컬렉션의 현재 순서 항목을 반환 하는 `Order` 캐스팅 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f200-110">The <xref:System.Windows.Data.CollectionView.CurrentItem%2A> property of the view is cast as an `Order` to return the current order item in the collection.</span></span>  
  
 [!code-csharp[CollectionView#OnButton](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a><span data-ttu-id="5f200-111">참조</span><span class="sxs-lookup"><span data-stu-id="5f200-111">See also</span></span>

- [<span data-ttu-id="5f200-112">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="5f200-112">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="5f200-113">뷰의 데이터 정렬</span><span class="sxs-lookup"><span data-stu-id="5f200-113">Sort Data in a View</span></span>](how-to-sort-data-in-a-view.md)
- [<span data-ttu-id="5f200-114">뷰에서 데이터 필터링</span><span class="sxs-lookup"><span data-stu-id="5f200-114">Filter Data in a View</span></span>](how-to-filter-data-in-a-view.md)
- [<span data-ttu-id="5f200-115">XAML 데이터 정렬 및 그룹화</span><span class="sxs-lookup"><span data-stu-id="5f200-115">Sort and Group Data Using a View in XAML</span></span>](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [<span data-ttu-id="5f200-116">방법 항목</span><span class="sxs-lookup"><span data-stu-id="5f200-116">How-to Topics</span></span>](data-binding-how-to-topics.md)

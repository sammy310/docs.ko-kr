---
title: '방법: 데이터 CollectionView에서 개체 탐색'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CollectionView [WPF], navigating through objects
- data binding [WPF], navigating through objects in data CollectionView
- navigating through objects in data CollectionView [WPF]
ms.assetid: fcd37590-bce1-4ac9-8b74-3b96c7458b8a
ms.openlocfilehash: 1507ab4db0c91b670d8bca754f6fd67d887c7041
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138179"
---
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a><span data-ttu-id="08c51-102">방법: 데이터 CollectionView에서 개체 탐색</span><span class="sxs-lookup"><span data-stu-id="08c51-102">How to: Navigate Through the Objects in a Data CollectionView</span></span>
<span data-ttu-id="08c51-103">뷰는 동일한 데이터 수집을 정렬, 필터링 또는 그룹화에 따라 다른 방법으로 볼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="08c51-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping.</span></span> <span data-ttu-id="08c51-104">뷰는 또한 현재 레코드 포인터 개념을 제공 하 고 포인터를 이동 하는 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="08c51-104">Views also provide a current record pointer concept and enable moving the pointer.</span></span> <span data-ttu-id="08c51-105">현재 개체를 가져올 수 있을 뿐만 아니라에서 제공 하는 기능을 사용 하 여 데이터 컬렉션의 개체를 통해 이동 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Data.CollectionView> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="08c51-105">This example shows how to get the current object as well as navigate through the objects in a data collection using the functionality provided in the <xref:System.Windows.Data.CollectionView> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08c51-106">예제</span><span class="sxs-lookup"><span data-stu-id="08c51-106">Example</span></span>  
 <span data-ttu-id="08c51-107">이 예에서 `myCollectionView` 는 <xref:System.Windows.Data.CollectionView> 개체 뷰를 바인딩 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="08c51-107">In this example, `myCollectionView` is a <xref:System.Windows.Data.CollectionView> object that is a view over a bound collection.</span></span>  
  
 <span data-ttu-id="08c51-108">다음 예에서 `OnButton` 에 대 한 이벤트 처리기는 `Previous` 및 `Next` 응용 프로그램에서 데이터 컬렉션을 탐색 하는 데 사용할 수 있는 단추는 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="08c51-108">In the following example, `OnButton` is an event handler for the `Previous` and `Next` buttons in an application, which are buttons that allow the user to navigate the data collection.</span></span> <span data-ttu-id="08c51-109"><xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> 하 고 <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> 속성이 있는지 여부를 현재 레코드 포인터에 제공 시작과 목록의 끝에 각각 하므로 보고서 <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> 및 <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> 으로 적절 하 게 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08c51-109">Note that the <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> and <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> properties report whether the current record pointer has come to the beginning and the end of the list respectively so that <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> and <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> can be called as appropriately.</span></span>  
  
 <span data-ttu-id="08c51-110"><xref:System.Windows.Data.CollectionView.CurrentItem%2A> 보기의 속성으로 캐스팅 됩니다는 `Order` 컬렉션의 현재 주문 항목을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="08c51-110">The <xref:System.Windows.Data.CollectionView.CurrentItem%2A> property of the view is cast as an `Order` to return the current order item in the collection.</span></span>  
  
 [!code-csharp[CollectionView#OnButton](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a><span data-ttu-id="08c51-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="08c51-111">See also</span></span>

- [<span data-ttu-id="08c51-112">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="08c51-112">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="08c51-113">보기에서 데이터 정렬</span><span class="sxs-lookup"><span data-stu-id="08c51-113">Sort Data in a View</span></span>](how-to-sort-data-in-a-view.md)
- [<span data-ttu-id="08c51-114">보기에서 데이터 필터링</span><span class="sxs-lookup"><span data-stu-id="08c51-114">Filter Data in a View</span></span>](how-to-filter-data-in-a-view.md)
- [<span data-ttu-id="08c51-115">XAML에서 보기를 사용하여 데이터 정렬 및 그룹화</span><span class="sxs-lookup"><span data-stu-id="08c51-115">Sort and Group Data Using a View in XAML</span></span>](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [<span data-ttu-id="08c51-116">방법 항목</span><span class="sxs-lookup"><span data-stu-id="08c51-116">How-to Topics</span></span>](data-binding-how-to-topics.md)

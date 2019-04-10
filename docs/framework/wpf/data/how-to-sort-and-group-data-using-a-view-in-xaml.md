---
title: '방법: XAML에서 보기를 사용하여 데이터 정렬 및 그룹화'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], grouping data in views in XAML
- XAML [WPF], sorting data in views
- grouping data in views in XAML [WPF]
- data binding [WPF], sorting data in views in XAML
- sorting data in views in XAML [WPF]
- XAML [WPF], grouping data in views
- views [WPF], sorting data
- views [WPF], grouping data
ms.assetid: 145c8c3f-dbdd-4d0d-816f-90b35eba7eda
ms.openlocfilehash: ca4439b574264ebebfda745f0765f750099bc95f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144523"
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a><span data-ttu-id="59ecd-102">방법: XAML에서 보기를 사용하여 데이터 정렬 및 그룹화</span><span class="sxs-lookup"><span data-stu-id="59ecd-102">How to: Sort and Group Data Using a View in XAML</span></span>
<span data-ttu-id="59ecd-103">이 예제에서 데이터 컬렉션의 뷰를 만드는 방법을 보여 줍니다 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="59ecd-103">This example shows how to create a view of a data collection in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="59ecd-104">뷰 그룹화, 정렬, 필터링의 기능 및 현재 항목의 개념을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="59ecd-104">Views allow for the functionalities of grouping, sorting, filtering, and the notion of a current item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59ecd-105">예제</span><span class="sxs-lookup"><span data-stu-id="59ecd-105">Example</span></span>  
 <span data-ttu-id="59ecd-106">다음 예제에서는 정적 리소스 이름이 *배치* 컬렉션으로 정의 됩니다 *장소* 개체를 각 *위치* 도시 이름으로 구성 된 개체 및 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="59ecd-106">In the following example, the static resource named *places* is defined as a collection of *Place* objects, in which each *Place* object is consisted of a city name and the state.</span></span> <span data-ttu-id="59ecd-107">접두사 *src* 네임 스페이스에 매핑되는 데이터 원본 *자릿수* 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59ecd-107">The prefix *src* is mapped to the namespace where the data source *Places* is defined.</span></span> <span data-ttu-id="59ecd-108">접두사 *scm* 매핑됩니다 `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` 하 고 *dat* 매핑됩니다 `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`합니다.</span><span class="sxs-lookup"><span data-stu-id="59ecd-108">The prefix *scm* maps to `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` and *dat* maps to `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.</span></span>  
  
 <span data-ttu-id="59ecd-109">다음 예제에서는 도시 이름별으로 정렬 되 고 상태별으로 그룹화 된 데이터 컬렉션의 뷰를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="59ecd-109">The following example creates a view of the data collection that is sorted by the city name and grouped by the state.</span></span>  
  
 [!code-xaml[CollectionViewSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 <span data-ttu-id="59ecd-110">뷰에는 바인딩 소스는 다음 예제와 같이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59ecd-110">The view can then be a binding source, as in the following example:</span></span>  
  
 [!code-xaml[CollectionViewSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 <span data-ttu-id="59ecd-111">에 정의 된 XML 데이터에 대 한 바인딩의 <xref:System.Windows.Data.XmlDataProvider> 리소스를 사용 하 여 XML 이름 앞에 @ 기호.</span><span class="sxs-lookup"><span data-stu-id="59ecd-111">For bindings to XML data defined in an <xref:System.Windows.Data.XmlDataProvider> resource, precede the XML name with an @ symbol.</span></span>  
  
 [!code-xaml[CollectionViewSource#XDPChunk](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a><span data-ttu-id="59ecd-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="59ecd-112">See also</span></span>

- <xref:System.Windows.Data.CollectionViewSource>
- [<span data-ttu-id="59ecd-113">데이터 컬렉션의 기본 보기 가져오기</span><span class="sxs-lookup"><span data-stu-id="59ecd-113">Get the Default View of a Data Collection</span></span>](how-to-get-the-default-view-of-a-data-collection.md)
- [<span data-ttu-id="59ecd-114">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="59ecd-114">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="59ecd-115">방법 항목</span><span class="sxs-lookup"><span data-stu-id="59ecd-115">How-to Topics</span></span>](data-binding-how-to-topics.md)

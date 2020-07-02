---
title: '방법: XAML에서 뷰를 사용하여 데이터 정렬 및 그룹화'
description: Windows Presentation Foundation (WPF)에서 그룹화, 정렬 및 필터링을 위해 데이터 컬렉션의 뷰를 만드는 방법에 대해 알아봅니다.
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
ms.openlocfilehash: a4f8e2de9345dba8e4ea0d3a16a32d57a9adb55c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621680"
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a><span data-ttu-id="02cec-103">방법: XAML에서 뷰를 사용하여 데이터 정렬 및 그룹화</span><span class="sxs-lookup"><span data-stu-id="02cec-103">How to: Sort and Group Data Using a View in XAML</span></span>
<span data-ttu-id="02cec-104">이 예에서는에서 데이터 컬렉션의 뷰를 만드는 방법을 보여 줍니다 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="02cec-104">This example shows how to create a view of a data collection in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="02cec-105">뷰를 사용 하면 그룹화, 정렬, 필터링 및 현재 항목의 개념에 대 한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02cec-105">Views allow for the functionalities of grouping, sorting, filtering, and the notion of a current item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02cec-106">예제</span><span class="sxs-lookup"><span data-stu-id="02cec-106">Example</span></span>  
 <span data-ttu-id="02cec-107">다음 예제에서는 정적 리소스 명명 된 *위치* *개체의 컬렉션* 으로 정의 됩니다. 여기서 각 *위치* 개체는 도시 이름과 상태로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02cec-107">In the following example, the static resource named *places* is defined as a collection of *Place* objects, in which each *Place* object is consisted of a city name and the state.</span></span> <span data-ttu-id="02cec-108">접두사 *src* 는 데이터 원본 *위치가* 정의 된 네임 스페이스에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="02cec-108">The prefix *src* is mapped to the namespace where the data source *Places* is defined.</span></span> <span data-ttu-id="02cec-109">*Scm* 은에 매핑되고 `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` *dat* 는로 매핑됩니다 `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"` .</span><span class="sxs-lookup"><span data-stu-id="02cec-109">The prefix *scm* maps to `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` and *dat* maps to `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.</span></span>  
  
 <span data-ttu-id="02cec-110">다음 예에서는 도시 이름을 기준으로 정렬 되 고 상태별로 그룹화 된 데이터 컬렉션 뷰를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="02cec-110">The following example creates a view of the data collection that is sorted by the city name and grouped by the state.</span></span>  
  
 [!code-xaml[CollectionViewSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 <span data-ttu-id="02cec-111">그러면 다음 예제와 같이 뷰가 바인딩 원본이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02cec-111">The view can then be a binding source, as in the following example:</span></span>  
  
 [!code-xaml[CollectionViewSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 <span data-ttu-id="02cec-112">리소스에 정의 된 XML 데이터에 대 한 바인딩의 경우 <xref:System.Windows.Data.XmlDataProvider> xml 이름 앞에 @ 기호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="02cec-112">For bindings to XML data defined in an <xref:System.Windows.Data.XmlDataProvider> resource, precede the XML name with an @ symbol.</span></span>  
  
 [!code-xaml[CollectionViewSource#XDPChunk](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a><span data-ttu-id="02cec-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="02cec-113">See also</span></span>

- <xref:System.Windows.Data.CollectionViewSource>
- [<span data-ttu-id="02cec-114">데이터 컬렉션의 기본 뷰 가져오기</span><span class="sxs-lookup"><span data-stu-id="02cec-114">Get the Default View of a Data Collection</span></span>](how-to-get-the-default-view-of-a-data-collection.md)
- [<span data-ttu-id="02cec-115">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="02cec-115">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="02cec-116">방법 도움말 항목</span><span class="sxs-lookup"><span data-stu-id="02cec-116">How-to Topics</span></span>](data-binding-how-to-topics.md)

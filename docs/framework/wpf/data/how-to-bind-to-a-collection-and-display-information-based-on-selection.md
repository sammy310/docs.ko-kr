---
title: '방법: 선택에 따라 수집 및 표시 정보에 바인딩'
description: 이 예제에 따라 Windows Presentation Foundation (WPF)에서 선택 항목을 기반으로 컬렉션에 바인딩하고 정보를 표시 하는 방법을 확인할 수 있습니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], selecting data for views
- data binding [WPF], creating views of data collections
- data binding [WPF], selecting data for views
- data binding [WPF], binding to collections
ms.assetid: 952a7d76-dd29-49e5-86f5-32c4530e70eb
ms.openlocfilehash: fb8757ee6818a2812308a0a132fa9d06951ad52e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619613"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a><span data-ttu-id="38aba-103">방법: 선택에 따라 수집 및 표시 정보에 바인딩</span><span class="sxs-lookup"><span data-stu-id="38aba-103">How to: Bind to a Collection and Display Information Based on Selection</span></span>
<span data-ttu-id="38aba-104">간단한 마스터 세부 시나리오에서는와 같은 데이터 바인딩된가 있습니다 <xref:System.Windows.Controls.ItemsControl> <xref:System.Windows.Controls.ListBox> .</span><span class="sxs-lookup"><span data-stu-id="38aba-104">In a simple master-detail scenario, you have a data-bound <xref:System.Windows.Controls.ItemsControl> such as a <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="38aba-105">사용자 선택에 따라 선택한 항목에 대 한 자세한 정보를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aba-105">Based on user selection, you display more information about the selected item.</span></span> <span data-ttu-id="38aba-106">이 예제에서는이 시나리오를 구현 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="38aba-106">This example shows how to implement this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38aba-107">예제</span><span class="sxs-lookup"><span data-stu-id="38aba-107">Example</span></span>  
 <span data-ttu-id="38aba-108">이 예제에서 `People` 는 <xref:System.Collections.ObjectModel.ObservableCollection%601> 클래스의입니다 `Person` .</span><span class="sxs-lookup"><span data-stu-id="38aba-108">In this example, `People` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `Person` classes.</span></span> <span data-ttu-id="38aba-109">이 `Person` 클래스에는 세 가지 속성인 `FirstName` , `LastName` 및 `HomeTown` 가 포함 되어 있습니다 `string` .</span><span class="sxs-lookup"><span data-stu-id="38aba-109">This `Person` class contains three properties: `FirstName`, `LastName`, and `HomeTown`, all of type `string`.</span></span>  
  
 [!code-xaml[CollectionBinding#Source](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 <span data-ttu-id="38aba-110">는 <xref:System.Windows.Controls.ContentControl> <xref:System.Windows.DataTemplate> 의 정보를 표시 하는 방법을 정의 하는 다음을 사용 합니다 `Person` .</span><span class="sxs-lookup"><span data-stu-id="38aba-110">The <xref:System.Windows.Controls.ContentControl> uses the following <xref:System.Windows.DataTemplate> that defines how the information of a `Person` is presented:</span></span>  
  
 [!code-xaml[CollectionBinding#DetailTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 <span data-ttu-id="38aba-111">다음은이 예제가 생성 하는 항목의 스크린샷입니다.</span><span class="sxs-lookup"><span data-stu-id="38aba-111">The following is a screenshot of what the example produces.</span></span> <span data-ttu-id="38aba-112">는 <xref:System.Windows.Controls.ContentControl> 선택한 사용자의 다른 속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="38aba-112">The <xref:System.Windows.Controls.ContentControl> shows the other properties of the person selected.</span></span>  
  
 <span data-ttu-id="38aba-113">![컬렉션에 바인딩](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span><span class="sxs-lookup"><span data-stu-id="38aba-113">![Binding to a collection](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span></span>  
  
 <span data-ttu-id="38aba-114">이 예에서는 다음과 같은 두 가지 사항을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aba-114">The two things to notice in this example are:</span></span>  
  
1. <span data-ttu-id="38aba-115"><xref:System.Windows.Controls.ListBox>및는 <xref:System.Windows.Controls.ContentControl> 동일한 소스에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="38aba-115">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.ContentControl> bind to the same source.</span></span> <span data-ttu-id="38aba-116">두 <xref:System.Windows.Data.Binding.Path%2A> 컨트롤 모두 전체 컬렉션 개체에 바인딩되어 있으므로 두 바인딩의 속성을 지정 하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="38aba-116">The <xref:System.Windows.Data.Binding.Path%2A> properties of both bindings are not specified because both controls are binding to the entire collection object.</span></span>  
  
2. <span data-ttu-id="38aba-117"><xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> `true` 이 작업을 수행 하려면 속성을로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aba-117">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` for this to work.</span></span> <span data-ttu-id="38aba-118">이 속성을 설정 하면 선택한 항목이 항상로 설정 됩니다 <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A> .</span><span class="sxs-lookup"><span data-stu-id="38aba-118">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="38aba-119">또는 <xref:System.Windows.Controls.ListBox> 에서 데이터를 가져오는 경우 <xref:System.Windows.Data.CollectionViewSource> 선택 및 통화를 자동으로 동기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aba-119">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="38aba-120">`Person`클래스는 `ToString` 다음과 같은 방식으로 메서드를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aba-120">Note that the `Person` class overrides the `ToString` method the following way.</span></span> <span data-ttu-id="38aba-121">기본적으로는를 <xref:System.Windows.Controls.ListBox> 호출 `ToString` 하 고 바인딩된 컬렉션의 각 개체에 대 한 문자열 표현을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="38aba-121">By default, the <xref:System.Windows.Controls.ListBox> calls `ToString` and displays a string representation of each object in the bound collection.</span></span> <span data-ttu-id="38aba-122">이러한 이유 때문 `Person` 에는 각각의 첫 번째 이름으로 표시 됩니다 <xref:System.Windows.Controls.ListBox> .</span><span class="sxs-lookup"><span data-stu-id="38aba-122">That is why each `Person` appears as a first name in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-csharp[CollectionBinding#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a><span data-ttu-id="38aba-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="38aba-123">See also</span></span>

- [<span data-ttu-id="38aba-124">계층적 데이터에 마스터-세부 패턴 사용</span><span class="sxs-lookup"><span data-stu-id="38aba-124">Use the Master-Detail Pattern with Hierarchical Data</span></span>](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)
- [<span data-ttu-id="38aba-125">계층적 XML 데이터에 마스터-세부 패턴 사용</span><span class="sxs-lookup"><span data-stu-id="38aba-125">Use the Master-Detail Pattern with Hierarchical XML Data</span></span>](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [<span data-ttu-id="38aba-126">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="38aba-126">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="38aba-127">데이터 템플릿 개요</span><span class="sxs-lookup"><span data-stu-id="38aba-127">Data Templating Overview</span></span>](data-templating-overview.md)
- [<span data-ttu-id="38aba-128">방법 도움말 항목</span><span class="sxs-lookup"><span data-stu-id="38aba-128">How-to Topics</span></span>](data-binding-how-to-topics.md)

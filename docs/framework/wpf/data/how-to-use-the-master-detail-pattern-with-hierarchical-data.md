---
title: '방법: 계층적 데이터에 마스터-세부 패턴 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
ms.openlocfilehash: e18bc7d60b47b083a0b102938634473d85b39882
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2019
ms.locfileid: "58463321"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a><span data-ttu-id="34a8d-102">방법: 계층적 데이터에 마스터-세부 패턴 사용</span><span class="sxs-lookup"><span data-stu-id="34a8d-102">How to: Use the Master-Detail Pattern with Hierarchical Data</span></span>
<span data-ttu-id="34a8d-103">이 예제에는 마스터-세부 시나리오를 구현 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="34a8d-103">This example shows how to implement the master-detail scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34a8d-104">예제</span><span class="sxs-lookup"><span data-stu-id="34a8d-104">Example</span></span>  
 <span data-ttu-id="34a8d-105">이 예에서 `LeagueList` 컬렉션인 `Leagues`합니다.</span><span class="sxs-lookup"><span data-stu-id="34a8d-105">In this example, `LeagueList` is a collection of `Leagues`.</span></span> <span data-ttu-id="34a8d-106">각 `League` 에 `Name` 의 컬렉션과 `Divisions`, 및 각 `Division` 에 이름 및 컬렉션 `Teams`합니다.</span><span class="sxs-lookup"><span data-stu-id="34a8d-106">Each `League` has a `Name` and a collection of `Divisions`, and each `Division` has a name and a collection of `Teams`.</span></span> <span data-ttu-id="34a8d-107">각 `Team` 팀 이름이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34a8d-107">Each `Team` has a team name.</span></span>  
  
 [!code-xaml[MasterDetail#HowTo1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 <span data-ttu-id="34a8d-108">예제 스크린샷은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="34a8d-108">The following is a screenshot of the example.</span></span> <span data-ttu-id="34a8d-109">합니다 `Divisions` <xref:System.Windows.Controls.ListBox> 자동으로 선택 항목을 추적 합니다 `Leagues` <xref:System.Windows.Controls.ListBox> 해당 데이터를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="34a8d-109">The `Divisions` <xref:System.Windows.Controls.ListBox> automatically tracks selections in the `Leagues` <xref:System.Windows.Controls.ListBox> and display the corresponding data.</span></span> <span data-ttu-id="34a8d-110">합니다 `Teams` <xref:System.Windows.Controls.ListBox> 다른 두에서 선택 항목을 추적 <xref:System.Windows.Controls.ListBox> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="34a8d-110">The `Teams` <xref:System.Windows.Controls.ListBox> tracks selections in the other two <xref:System.Windows.Controls.ListBox> controls.</span></span>  
  
 ![마스터를 보여주는 스크린 샷&#45;세부 정보 시나리오 예제입니다.](./media/how-to-use-the-master-detail-pattern-with-hierarchical-data/databinding-master-detail-scenario.png)  
  
 <span data-ttu-id="34a8d-112">이 예제에서 주의 해야 할 두 가지 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="34a8d-112">The two things to notice in this example are:</span></span>  
  
1.  <span data-ttu-id="34a8d-113">세 가지 <xref:System.Windows.Controls.ListBox> 컨트롤 같은 소스에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="34a8d-113">The three <xref:System.Windows.Controls.ListBox> controls bind to the same source.</span></span> <span data-ttu-id="34a8d-114">설정한 합니다 <xref:System.Windows.Data.Binding.Path%2A> 하려는 데이터의 수준을 지정에 대 한 바인딩 속성을 <xref:System.Windows.Controls.ListBox> 표시할 합니다.</span><span class="sxs-lookup"><span data-stu-id="34a8d-114">You set the <xref:System.Windows.Data.Binding.Path%2A> property of the binding to specify which level of data you want the <xref:System.Windows.Controls.ListBox> to display.</span></span>  
  
2.  <span data-ttu-id="34a8d-115">설정 해야 합니다는 <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> 속성을 `true` 에 <xref:System.Windows.Controls.ListBox> 컨트롤의 추적 하는 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="34a8d-115">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` on the <xref:System.Windows.Controls.ListBox> controls of which the selection you are tracking.</span></span> <span data-ttu-id="34a8d-116">이 속성을 설정 하면 선택한 항목으로 항상 설정 되어 있는지를 <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>입니다.</span><span class="sxs-lookup"><span data-stu-id="34a8d-116">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="34a8d-117">또는 경우는 <xref:System.Windows.Controls.ListBox> 에서 데이터를 가져오는 <xref:System.Windows.Data.CollectionViewSource>, 선택 및 통화 자동으로 동기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="34a8d-117">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="34a8d-118">때 사용 하는 방법은 약간 다른 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="34a8d-118">The technique is slightly different when you are using [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span> <span data-ttu-id="34a8d-119">예를 들어 참조 [계층적 XML 데이터에 마스터-세부 패턴 사용](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="34a8d-119">For an example, see [Use the Master-Detail Pattern with Hierarchical XML Data](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34a8d-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="34a8d-120">See also</span></span>
- <xref:System.Windows.HierarchicalDataTemplate>
- [<span data-ttu-id="34a8d-121">선택에 따라 수집 및 표시 정보에 바인딩</span><span class="sxs-lookup"><span data-stu-id="34a8d-121">Bind to a Collection and Display Information Based on Selection</span></span>](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [<span data-ttu-id="34a8d-122">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="34a8d-122">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="34a8d-123">데이터 템플릿 개요</span><span class="sxs-lookup"><span data-stu-id="34a8d-123">Data Templating Overview</span></span>](data-templating-overview.md)
- [<span data-ttu-id="34a8d-124">방법 항목</span><span class="sxs-lookup"><span data-stu-id="34a8d-124">How-to Topics</span></span>](data-binding-how-to-topics.md)

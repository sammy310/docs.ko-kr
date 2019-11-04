---
title: '방법: 계층적 데이터에 마스터-세부 패턴 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
ms.openlocfilehash: 2e7d9ceed3ab8385f07d87ecdb92c0a99d410b40
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459086"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a><span data-ttu-id="cc2a6-102">방법: 계층적 데이터에 마스터-세부 패턴 사용</span><span class="sxs-lookup"><span data-stu-id="cc2a6-102">How to: Use the Master-Detail Pattern with Hierarchical Data</span></span>
<span data-ttu-id="cc2a6-103">이 예제에서는 마스터-세부 시나리오를 구현 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc2a6-103">This example shows how to implement the master-detail scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc2a6-104">예제</span><span class="sxs-lookup"><span data-stu-id="cc2a6-104">Example</span></span>  
 <span data-ttu-id="cc2a6-105">이 예제에서 `LeagueList`은 `Leagues`컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="cc2a6-105">In this example, `LeagueList` is a collection of `Leagues`.</span></span> <span data-ttu-id="cc2a6-106">각 `League`에는 `Name` 및 `Divisions`컬렉션이 있으며 각 `Division`에는 이름 및 `Teams`컬렉션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc2a6-106">Each `League` has a `Name` and a collection of `Divisions`, and each `Division` has a name and a collection of `Teams`.</span></span> <span data-ttu-id="cc2a6-107">각 `Team`에는 팀 이름이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc2a6-107">Each `Team` has a team name.</span></span>  
  
 [!code-xaml[MasterDetail#HowTo1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 <span data-ttu-id="cc2a6-108">예제 스크린샷은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cc2a6-108">The following is a screenshot of the example.</span></span> <span data-ttu-id="cc2a6-109">`Divisions` <xref:System.Windows.Controls.ListBox> `Leagues` <xref:System.Windows.Controls.ListBox>에서 선택 항목을 자동으로 추적 하 고 해당 데이터를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc2a6-109">The `Divisions` <xref:System.Windows.Controls.ListBox> automatically tracks selections in the `Leagues` <xref:System.Windows.Controls.ListBox> and display the corresponding data.</span></span> <span data-ttu-id="cc2a6-110">`Teams` <xref:System.Windows.Controls.ListBox>는 다른 두 <xref:System.Windows.Controls.ListBox> 컨트롤의 선택 항목을 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc2a6-110">The `Teams` <xref:System.Windows.Controls.ListBox> tracks selections in the other two <xref:System.Windows.Controls.ListBox> controls.</span></span>  
  
 ![마스터&#45;세부 시나리오 예를 보여 주는 스크린샷](./media/how-to-use-the-master-detail-pattern-with-hierarchical-data/databinding-master-detail-scenario.png)  
  
 <span data-ttu-id="cc2a6-112">이 예에서는 다음과 같은 두 가지 사항을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc2a6-112">The two things to notice in this example are:</span></span>  
  
1. <span data-ttu-id="cc2a6-113">세 개의 <xref:System.Windows.Controls.ListBox> 컨트롤이 동일한 소스에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="cc2a6-113">The three <xref:System.Windows.Controls.ListBox> controls bind to the same source.</span></span> <span data-ttu-id="cc2a6-114">바인딩의 <xref:System.Windows.Data.Binding.Path%2A> 속성을 설정 하 여 <xref:System.Windows.Controls.ListBox> 표시할 데이터 수준을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc2a6-114">You set the <xref:System.Windows.Data.Binding.Path%2A> property of the binding to specify which level of data you want the <xref:System.Windows.Controls.ListBox> to display.</span></span>  
  
2. <span data-ttu-id="cc2a6-115"><xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> 속성을 추적 하려는 선택 항목의 <xref:System.Windows.Controls.ListBox> 컨트롤에서 `true`으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc2a6-115">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` on the <xref:System.Windows.Controls.ListBox> controls of which the selection you are tracking.</span></span> <span data-ttu-id="cc2a6-116">이 속성을 설정 하면 선택한 항목이 항상 <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc2a6-116">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="cc2a6-117">또는 <xref:System.Windows.Controls.ListBox> <xref:System.Windows.Data.CollectionViewSource>에서 데이터를 가져오는 경우 선택 및 통화를 자동으로 동기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc2a6-117">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="cc2a6-118">[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터를 사용 하는 경우 기술은 약간 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="cc2a6-118">The technique is slightly different when you are using [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span> <span data-ttu-id="cc2a6-119">예제는 [계층적 XML 데이터에 마스터-세부 패턴 사용](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cc2a6-119">For an example, see [Use the Master-Detail Pattern with Hierarchical XML Data](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc2a6-120">참조</span><span class="sxs-lookup"><span data-stu-id="cc2a6-120">See also</span></span>

- <xref:System.Windows.HierarchicalDataTemplate>
- [<span data-ttu-id="cc2a6-121">선택에 따라 수집 및 표시 정보에 바인딩</span><span class="sxs-lookup"><span data-stu-id="cc2a6-121">Bind to a Collection and Display Information Based on Selection</span></span>](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [<span data-ttu-id="cc2a6-122">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="cc2a6-122">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="cc2a6-123">데이터 템플릿 개요</span><span class="sxs-lookup"><span data-stu-id="cc2a6-123">Data Templating Overview</span></span>](data-templating-overview.md)
- [<span data-ttu-id="cc2a6-124">방법 항목</span><span class="sxs-lookup"><span data-stu-id="cc2a6-124">How-to Topics</span></span>](data-binding-how-to-topics.md)

---
title: '방법: PriorityBinding 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
ms.openlocfilehash: 343b0aca4736905f3a0cbff5a0f76b170da0c920
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459789"
---
# <a name="how-to-implement-prioritybinding"></a><span data-ttu-id="9b5e7-102">방법: PriorityBinding 구현</span><span class="sxs-lookup"><span data-stu-id="9b5e7-102">How to: Implement PriorityBinding</span></span>
<span data-ttu-id="9b5e7-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Data.PriorityBinding>는 바인딩 목록을 지정 하 여 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b5e7-103"><xref:System.Windows.Data.PriorityBinding> in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] works by specifying a list of bindings.</span></span> <span data-ttu-id="9b5e7-104">바인딩 목록은 우선 순위가 가장 높은 우선 순위로 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b5e7-104">The list of bindings is ordered from highest priority to lowest priority.</span></span> <span data-ttu-id="9b5e7-105">우선 순위가 가장 높은 바인딩이 처리 될 때 값을 성공적으로 반환 하는 경우 목록에서 다른 바인딩을 처리할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b5e7-105">If the highest priority binding returns a value successfully when it is processed then there is never a need to process the other bindings in the list.</span></span> <span data-ttu-id="9b5e7-106">우선 순위가 가장 높은 바인딩이 계산 되는 데 시간이 오래 걸릴 수 있습니다. 값을 반환 하는 다음으로 높은 우선 순위는 더 높은 우선 순위의 바인딩이 성공적으로 값을 반환할 때까지 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b5e7-106">It could be the case that the highest priority binding takes a long time to be evaluated, the next highest priority that returns a value successfully will be used until a binding of a higher priority returns a value successfully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b5e7-107">예제</span><span class="sxs-lookup"><span data-stu-id="9b5e7-107">Example</span></span>  
 <span data-ttu-id="9b5e7-108"><xref:System.Windows.Data.PriorityBinding> 작동 방식을 설명 하기 위해 `FastDP`, `SlowerDP`및 `SlowestDP`의 세 가지 속성을 사용 하 여 `AsyncDataSource` 개체를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="9b5e7-108">To demonstrate how <xref:System.Windows.Data.PriorityBinding> works, the `AsyncDataSource` object has been created with the following three properties: `FastDP`, `SlowerDP`, and `SlowestDP`.</span></span>  
  
 <span data-ttu-id="9b5e7-109">`FastDP`의 get 접근자는 `_fastDP` 데이터 멤버의 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b5e7-109">The get accessor of `FastDP` returns the value of the `_fastDP` data member.</span></span>  
  
 <span data-ttu-id="9b5e7-110">`SlowerDP`의 get 접근자는 `_slowerDP` 데이터 멤버의 값을 반환 하기 전에 3 초 동안 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b5e7-110">The get accessor of `SlowerDP` waits for 3 seconds before returning the value of the `_slowerDP` data member.</span></span>  
  
 <span data-ttu-id="9b5e7-111">`SlowestDP`의 get 접근자는 `_slowestDP` 데이터 멤버의 값을 반환 하기 전에 5 초 동안 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b5e7-111">The get accessor of `SlowestDP` waits for 5 seconds before returning the value of the `_slowestDP` data member.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9b5e7-112">이 예제는 데모용으로만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b5e7-112">This example is for demonstration purposes only.</span></span> <span data-ttu-id="9b5e7-113">.NET 지침은 필드 집합 보다 느린 크기의 속성을 정의 하는 것에 대해 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b5e7-113">The .NET guidelines recommend against defining properties that are orders of magnitude slower than a field set would be.</span></span> <span data-ttu-id="9b5e7-114">자세한 내용은 [속성 및 메서드 중에서 선택](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229054(v=vs.100))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9b5e7-114">For more information, see [Choosing Between Properties and Methods](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229054(v=vs.100)).</span></span>  
  
 [!code-csharp[PriorityBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 <span data-ttu-id="9b5e7-115"><xref:System.Windows.Controls.TextBlock.Text%2A> 속성은 <xref:System.Windows.Data.PriorityBinding>을 사용 하 여 위의 `AsyncDS`에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="9b5e7-115">The <xref:System.Windows.Controls.TextBlock.Text%2A> property binds to the above `AsyncDS` using <xref:System.Windows.Data.PriorityBinding>:</span></span>  
  
 [!code-xaml[PriorityBinding#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="9b5e7-116">바인딩 엔진은 <xref:System.Windows.Data.Binding> 개체를 처리할 때 `SlowestDP` 속성에 바인딩된 첫 번째 <xref:System.Windows.Data.Binding>으로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b5e7-116">When the binding engine processes the <xref:System.Windows.Data.Binding> objects, it starts with the first <xref:System.Windows.Data.Binding>, which is bound to the `SlowestDP` property.</span></span> <span data-ttu-id="9b5e7-117">이 <xref:System.Windows.Data.Binding> 처리 되 면 5 초 동안 절전 모드로 전환 되므로 값을 반환 하지 않으므로 다음 <xref:System.Windows.Data.Binding> 요소가 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b5e7-117">When this <xref:System.Windows.Data.Binding> is processed, it does not return a value successfully because it is sleeping for 5 seconds, so the next <xref:System.Windows.Data.Binding> element is processed.</span></span> <span data-ttu-id="9b5e7-118">다음 <xref:System.Windows.Data.Binding>은 3 초 동안 중지 되기 때문에 성공적으로 값을 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b5e7-118">The next <xref:System.Windows.Data.Binding> does not return a value successfully because it is sleeping for 3 seconds.</span></span> <span data-ttu-id="9b5e7-119">그러면 바인딩 엔진이 `FastDP` 속성에 바인딩된 다음 <xref:System.Windows.Data.Binding> 요소로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b5e7-119">The binding engine then moves onto the next <xref:System.Windows.Data.Binding> element, which is bound to the `FastDP` property.</span></span> <span data-ttu-id="9b5e7-120">이 <xref:System.Windows.Data.Binding> "Fast Value" 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b5e7-120">This <xref:System.Windows.Data.Binding> returns the value "Fast Value".</span></span> <span data-ttu-id="9b5e7-121">이제 <xref:System.Windows.Controls.TextBlock> "Fast Value" 값을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b5e7-121">The <xref:System.Windows.Controls.TextBlock> now displays the value "Fast Value".</span></span>  
  
 <span data-ttu-id="9b5e7-122">3 초가 경과 하면 `SlowerDP` 속성은 "느린 값" 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b5e7-122">After 3 seconds elapses, the `SlowerDP` property returns the value "Slower Value".</span></span> <span data-ttu-id="9b5e7-123">그런 다음 <xref:System.Windows.Controls.TextBlock> "느린 값" 값을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b5e7-123">The <xref:System.Windows.Controls.TextBlock> then displays the value "Slower Value".</span></span>  
  
 <span data-ttu-id="9b5e7-124">5 초 경과 후 `SlowestDP` 속성은 "가장 느린 값" 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b5e7-124">After 5 seconds elapses, the `SlowestDP` property returns the value "Slowest Value".</span></span> <span data-ttu-id="9b5e7-125">이 바인딩은 먼저 나열 되기 때문에 가장 높은 우선 순위를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="9b5e7-125">That binding has the highest priority because it is listed first.</span></span> <span data-ttu-id="9b5e7-126">이제 <xref:System.Windows.Controls.TextBlock> "가장 느린 값" 값이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b5e7-126">The <xref:System.Windows.Controls.TextBlock> now displays the value "Slowest Value".</span></span>  
  
 <span data-ttu-id="9b5e7-127">바인딩에서 성공한 반환 값으로 간주 되는 항목에 대 한 자세한 내용은 <xref:System.Windows.Data.PriorityBinding>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9b5e7-127">See <xref:System.Windows.Data.PriorityBinding> for information about what is considered a successful return value from a binding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b5e7-128">참조</span><span class="sxs-lookup"><span data-stu-id="9b5e7-128">See also</span></span>

- <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>
- [<span data-ttu-id="9b5e7-129">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="9b5e7-129">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="9b5e7-130">방법 항목</span><span class="sxs-lookup"><span data-stu-id="9b5e7-130">How-to Topics</span></span>](data-binding-how-to-topics.md)

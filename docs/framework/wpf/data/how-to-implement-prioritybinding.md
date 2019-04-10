---
title: '방법: PriorityBinding 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
ms.openlocfilehash: aaf2caff1e2684e08c7eb65125536f1070203d70
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207567"
---
# <a name="how-to-implement-prioritybinding"></a><span data-ttu-id="8c412-102">방법: PriorityBinding 구현</span><span class="sxs-lookup"><span data-stu-id="8c412-102">How to: Implement PriorityBinding</span></span>
<xref:System.Windows.Data.PriorityBinding> <span data-ttu-id="8c412-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 바인딩 목록을 지정 하 여 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c412-103">in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] works by specifying a list of bindings.</span></span> <span data-ttu-id="8c412-104">바인딩 목록은 가장 낮은 우선 순위를 높은 우선 순위에서 정렬 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c412-104">The list of bindings is ordered from highest priority to lowest priority.</span></span> <span data-ttu-id="8c412-105">가장 높은 우선 순위 바인딩 값을 반환 하는 경우 성공적으로 처리 될 때 다음 있습니다 되지 목록에 다른 바인딩을 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c412-105">If the highest priority binding returns a value successfully when it is processed then there is never a need to process the other bindings in the list.</span></span> <span data-ttu-id="8c412-106">우선 순위가 높은 바인딩이 평가할 오래 걸리는 경우 수, 더 높은 우선 순위의 바인딩 값을 성공적으로 반환 될 때까지 다음 우선 순위가 가장 높은 값을 성공적으로 반환 하는 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c412-106">It could be the case that the highest priority binding takes a long time to be evaluated, the next highest priority that returns a value successfully will be used until a binding of a higher priority returns a value successfully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c412-107">예제</span><span class="sxs-lookup"><span data-stu-id="8c412-107">Example</span></span>  
 <span data-ttu-id="8c412-108">보여 주기 위해 어떻게 <xref:System.Windows.Data.PriorityBinding> 작동 합니다 `AsyncDataSource` 다음 세 가지 속성을 사용 하 여 개체가 생성 되었음을: `FastDP`를 `SlowerDP`, 및 `SlowestDP`합니다.</span><span class="sxs-lookup"><span data-stu-id="8c412-108">To demonstrate how <xref:System.Windows.Data.PriorityBinding> works, the `AsyncDataSource` object has been created with the following three properties: `FastDP`, `SlowerDP`, and `SlowestDP`.</span></span>  
  
 <span data-ttu-id="8c412-109">get 접근자 `FastDP` 의 값을 반환 합니다 `_fastDP` 데이터 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="8c412-109">The get accessor of `FastDP` returns the value of the `_fastDP` data member.</span></span>  
  
 <span data-ttu-id="8c412-110">get 접근자 `SlowerDP` 의 값을 반환 하기 전에 3 초간 대기 합니다 `_slowerDP` 데이터 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="8c412-110">The get accessor of `SlowerDP` waits for 3 seconds before returning the value of the `_slowerDP` data member.</span></span>  
  
 <span data-ttu-id="8c412-111">get 접근자 `SlowestDP` 의 값을 반환 하기 전에 5 초간 대기 합니다 `_slowestDP` 데이터 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="8c412-111">The get accessor of `SlowestDP` waits for 5 seconds before returning the value of the `_slowestDP` data member.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c412-112">이 예제는 데모용으로만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c412-112">This example is for demonstration purposes only.</span></span> <span data-ttu-id="8c412-113">[!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] 크기가 커져 느린 필드 집합 보다 속성을 정의 하는 것에 대 한 지침을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c412-113">The [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] guidelines recommend against defining properties that are orders of magnitude slower than a field set would be.</span></span> <span data-ttu-id="8c412-114">자세한 내용은 [메서드와 속성 간의 선택](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229054(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="8c412-114">For more information, see [Choosing Between Properties and Methods](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229054(v=vs.100)).</span></span>  
  
 [!code-csharp[PriorityBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 <span data-ttu-id="8c412-115">합니다 <xref:System.Windows.Controls.TextBlock.Text%2A> 위의 속성이 바인딩된 `AsyncDS` 사용 하 여 <xref:System.Windows.Data.PriorityBinding>:</span><span class="sxs-lookup"><span data-stu-id="8c412-115">The <xref:System.Windows.Controls.TextBlock.Text%2A> property binds to the above `AsyncDS` using <xref:System.Windows.Data.PriorityBinding>:</span></span>  
  
 [!code-xaml[PriorityBinding#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="8c412-116">바인딩 엔진에서 처리 하는 경우는 <xref:System.Windows.Data.Binding> 개체를 첫 번째를 사용 하 여 시작 <xref:System.Windows.Data.Binding>에 바인딩된는 `SlowestDP` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="8c412-116">When the binding engine processes the <xref:System.Windows.Data.Binding> objects, it starts with the first <xref:System.Windows.Data.Binding>, which is bound to the `SlowestDP` property.</span></span> <span data-ttu-id="8c412-117">때이 <xref:System.Windows.Data.Binding> 는 처리를 반환 하지 않습니다을 성공적으로 대기 하기 5 초간 하므로 다음 때문에 <xref:System.Windows.Data.Binding> 요소가 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c412-117">When this <xref:System.Windows.Data.Binding> is processed, it does not return a value successfully because it is sleeping for 5 seconds, so the next <xref:System.Windows.Data.Binding> element is processed.</span></span> <span data-ttu-id="8c412-118">다음 <xref:System.Windows.Data.Binding> 값 반환 하지는 성공적으로 3 초 동안 대기 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="8c412-118">The next <xref:System.Windows.Data.Binding> does not return a value successfully because it is sleeping for 3 seconds.</span></span> <span data-ttu-id="8c412-119">바인딩 엔진은 다음으로 이동 <xref:System.Windows.Data.Binding> 요소에 바인딩되는 `FastDP` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="8c412-119">The binding engine then moves onto the next <xref:System.Windows.Data.Binding> element, which is bound to the `FastDP` property.</span></span> <span data-ttu-id="8c412-120">이 <xref:System.Windows.Data.Binding> 값 "빠른"를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c412-120">This <xref:System.Windows.Data.Binding> returns the value "Fast Value".</span></span> <span data-ttu-id="8c412-121"><xref:System.Windows.Controls.TextBlock> 이제 값 "빠른"를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c412-121">The <xref:System.Windows.Controls.TextBlock> now displays the value "Fast Value".</span></span>  
  
 <span data-ttu-id="8c412-122">3 초 경과 후는 `SlowerDP` 속성 "느립니다 Value" 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c412-122">After 3 seconds elapses, the `SlowerDP` property returns the value "Slower Value".</span></span> <span data-ttu-id="8c412-123"><xref:System.Windows.Controls.TextBlock> 다음 "느립니다 Value" 값을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c412-123">The <xref:System.Windows.Controls.TextBlock> then displays the value "Slower Value".</span></span>  
  
 <span data-ttu-id="8c412-124">5 초 경과 후는 `SlowestDP` 속성 "가장 느린 값" 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c412-124">After 5 seconds elapses, the `SlowestDP` property returns the value "Slowest Value".</span></span> <span data-ttu-id="8c412-125">해당 바인딩을 먼저 나열 되므로 가장 높은 우선 순위를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="8c412-125">That binding has the highest priority because it is listed first.</span></span> <span data-ttu-id="8c412-126"><xref:System.Windows.Controls.TextBlock> 이제 "가장 느린 값" 값을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c412-126">The <xref:System.Windows.Controls.TextBlock> now displays the value "Slowest Value".</span></span>  
  
 <span data-ttu-id="8c412-127">참조 <xref:System.Windows.Data.PriorityBinding> 바인딩에서 성공적인 반환 값 간주 되는 항목에 대 한 정보에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c412-127">See <xref:System.Windows.Data.PriorityBinding> for information about what is considered a successful return value from a binding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c412-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="8c412-128">See also</span></span>

- <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>
- [<span data-ttu-id="8c412-129">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="8c412-129">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="8c412-130">방법 항목</span><span class="sxs-lookup"><span data-stu-id="8c412-130">How-to Topics</span></span>](data-binding-how-to-topics.md)

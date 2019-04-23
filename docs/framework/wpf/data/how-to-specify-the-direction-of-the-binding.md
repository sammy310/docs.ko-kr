---
title: '방법: 바인딩 방향 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 4334ed178e7f2ed90928db6b434eb8c9fee77bf7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206436"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a><span data-ttu-id="65c46-102">방법: 바인딩 방향 지정</span><span class="sxs-lookup"><span data-stu-id="65c46-102">How to: Specify the Direction of the Binding</span></span>
<span data-ttu-id="65c46-103">이 예제에서는 바인딩으로 바인딩 대상(대상) 속성만 업데이트되는지, 바인딩 소스(소스) 속성만 업데이트되는지 아니면 대상 속성과 소스 속성이 모두 업데이트되는지 여부를 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="65c46-103">This example shows how to specify whether the binding updates only the binding target (target) property, the binding source (source) property, or both the target property and the source property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65c46-104">예제</span><span class="sxs-lookup"><span data-stu-id="65c46-104">Example</span></span>  
 <span data-ttu-id="65c46-105">사용 된 <xref:System.Windows.Data.Binding.Mode%2A> 바인딩 방향을 지정 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="65c46-105">You use the <xref:System.Windows.Data.Binding.Mode%2A> property to specify the direction of the binding.</span></span> <span data-ttu-id="65c46-106">다음 열거 목록에서는 바인딩 업데이트에 사용할 수 있는 옵션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="65c46-106">The following enumeration list shows the available options for binding updates:</span></span>  
  
-   <span data-ttu-id="65c46-107"><xref:System.Windows.Data.BindingMode.TwoWay> 대상 속성 또는 소스 속성이 변경 될 때마다 대상 속성이 나 속성을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c46-107"><xref:System.Windows.Data.BindingMode.TwoWay> updates the target property or the property whenever either the target property or the source property changes.</span></span>  
  
-   <span data-ttu-id="65c46-108"><xref:System.Windows.Data.BindingMode.OneWay> source 속성을 변경 하는 경우에 대상 속성을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c46-108"><xref:System.Windows.Data.BindingMode.OneWay> updates the target property only when the source property changes.</span></span>  
  
-   <span data-ttu-id="65c46-109"><xref:System.Windows.Data.BindingMode.OneTime> 응용 프로그램을 시작 하는 경우에 되거나 대상 속성을 업데이트 합니다 <xref:System.Windows.FrameworkElement.DataContext%2A> 가 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c46-109"><xref:System.Windows.Data.BindingMode.OneTime> updates the target property only when the application starts or when the <xref:System.Windows.FrameworkElement.DataContext%2A> undergoes a change.</span></span>  
  
-   <span data-ttu-id="65c46-110"><xref:System.Windows.Data.BindingMode.OneWayToSource> 대상 속성이 변경 되 면 소스 속성을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c46-110"><xref:System.Windows.Data.BindingMode.OneWayToSource> updates the source property when the target property changes.</span></span>  
  
-   <span data-ttu-id="65c46-111"><xref:System.Windows.Data.BindingMode.Default> 그러면 기본 <xref:System.Windows.Data.Binding.Mode%2A> 사용할 대상 속성의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="65c46-111"><xref:System.Windows.Data.BindingMode.Default> causes the default <xref:System.Windows.Data.Binding.Mode%2A> value of target property to be used.</span></span>  
  
 <span data-ttu-id="65c46-112">자세한 내용은 <xref:System.Windows.Data.BindingMode> 열거형을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="65c46-112">For more information, see the <xref:System.Windows.Data.BindingMode> enumeration.</span></span>  
  
 <span data-ttu-id="65c46-113">다음 예제에서는 <xref:System.Windows.Data.Binding.Mode%2A> 속성을 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="65c46-113">The following example shows how to set the <xref:System.Windows.Data.Binding.Mode%2A> property.</span></span>  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 <span data-ttu-id="65c46-114">소스 변경 내용을 검색 하려면 (적용할 <xref:System.Windows.Data.BindingMode.OneWay> 하 고 <xref:System.Windows.Data.BindingMode.TwoWay> 바인딩), 소스와 같은 적절 한 속성 변경 알림 메커니즘을 구현 해야 합니다 <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="65c46-114">To detect source changes (applicable to <xref:System.Windows.Data.BindingMode.OneWay> and <xref:System.Windows.Data.BindingMode.TwoWay> bindings), the source must implement a suitable property change notification mechanism such as <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span> <span data-ttu-id="65c46-115">참조 [속성 변경 알림 구현](how-to-implement-property-change-notification.md) 의 예는 <xref:System.ComponentModel.INotifyPropertyChanged> 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="65c46-115">See [Implement Property Change Notification](how-to-implement-property-change-notification.md) for an example of an <xref:System.ComponentModel.INotifyPropertyChanged> implementation.</span></span>  
  
 <span data-ttu-id="65c46-116">에 대 한 <xref:System.Windows.Data.BindingMode.TwoWay> 또는 <xref:System.Windows.Data.BindingMode.OneWayToSource> 바인딩을 설정 하 여 소스 업데이트의 타이밍을 제어할 수는 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="65c46-116">For <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings, you can control the timing of the source updates by setting the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property.</span></span> <span data-ttu-id="65c46-117">자세한 내용은 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="65c46-117">See <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65c46-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="65c46-118">See also</span></span>

- <xref:System.Windows.Data.Binding>
- [<span data-ttu-id="65c46-119">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="65c46-119">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="65c46-120">방법 항목</span><span class="sxs-lookup"><span data-stu-id="65c46-120">How-to Topics</span></span>](data-binding-how-to-topics.md)

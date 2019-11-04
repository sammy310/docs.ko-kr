---
title: '방법: 바인딩 방향 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 8f7d843382ee3409047d7cf9549267d582883984
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459102"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a><span data-ttu-id="f8e55-102">방법: 바인딩 방향 지정</span><span class="sxs-lookup"><span data-stu-id="f8e55-102">How to: Specify the direction of the binding</span></span>

<span data-ttu-id="f8e55-103">이 예제에서는 바인딩으로 바인딩 대상(대상) 속성만 업데이트되는지, 바인딩 소스(소스) 속성만 업데이트되는지 아니면 대상 속성과 소스 속성이 모두 업데이트되는지 여부를 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8e55-103">This example shows how to specify whether the binding updates only the binding target (target) property, the binding source (source) property, or both the target property and the source property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8e55-104">예제</span><span class="sxs-lookup"><span data-stu-id="f8e55-104">Example</span></span>  
 <span data-ttu-id="f8e55-105"><xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType> 속성을 사용 하 여 바인딩의 방향을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e55-105">You use the <xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType> property to specify the direction of the binding.</span></span> <span data-ttu-id="f8e55-106">바인딩 업데이트에 사용할 수 있는 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f8e55-106">The following are the available options for binding updates:</span></span>  
  
- <span data-ttu-id="f8e55-107">대상 속성이 나 원본 속성이 변경 될 때마다 대상 속성이 나 속성을 업데이트 <xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType> 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e55-107"><xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType> updates the target property or the property whenever either the target property or the source property changes.</span></span>  
  
- <span data-ttu-id="f8e55-108"><xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType> 소스 속성이 변경 될 때만 대상 속성을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e55-108"><xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType> updates the target property only when the source property changes.</span></span>  
  
- <span data-ttu-id="f8e55-109"><xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType>는 응용 프로그램이 시작 되거나 <xref:System.Windows.FrameworkElement.DataContext%2A> 변경 될 때만 대상 속성을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e55-109"><xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType> updates the target property only when the application starts or when the <xref:System.Windows.FrameworkElement.DataContext%2A> undergoes a change.</span></span>  
  
- <span data-ttu-id="f8e55-110"><xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType> 대상 속성이 변경 될 때 원본 속성을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e55-110"><xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType> updates the source property when the target property changes.</span></span>  
  
- <span data-ttu-id="f8e55-111"><xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType>를 사용 하면 대상 속성의 기본 <xref:System.Windows.Data.Binding.Mode%2A> 값이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8e55-111"><xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType> causes the default <xref:System.Windows.Data.Binding.Mode%2A> value of target property to be used.</span></span>  
  
 <span data-ttu-id="f8e55-112">자세한 내용은 <xref:System.Windows.Data.BindingMode> 열거형을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8e55-112">For more information, see the <xref:System.Windows.Data.BindingMode> enumeration.</span></span>  
  
 <span data-ttu-id="f8e55-113">다음 예제에서는 <xref:System.Windows.Data.Binding.Mode%2A> 속성을 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8e55-113">The following example shows how to set the <xref:System.Windows.Data.Binding.Mode%2A> property.</span></span>  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 <span data-ttu-id="f8e55-114">원본 변경 내용 (<xref:System.Windows.Data.BindingMode.OneWay> 및 <xref:System.Windows.Data.BindingMode.TwoWay> 바인딩에 적용 됨)을 검색 하려면 소스가 <xref:System.ComponentModel.INotifyPropertyChanged>와 같은 적절 한 속성 변경 알림 메커니즘을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8e55-114">To detect source changes (applicable to <xref:System.Windows.Data.BindingMode.OneWay> and <xref:System.Windows.Data.BindingMode.TwoWay> bindings), the source must implement a suitable property change notification mechanism such as <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span> <span data-ttu-id="f8e55-115"><xref:System.ComponentModel.INotifyPropertyChanged> 구현의 예제는 [속성 변경 알림 구현](how-to-implement-property-change-notification.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f8e55-115">See [Implement Property Change Notification](how-to-implement-property-change-notification.md) for an example of an <xref:System.ComponentModel.INotifyPropertyChanged> implementation.</span></span>  
  
 <span data-ttu-id="f8e55-116"><xref:System.Windows.Data.BindingMode.TwoWay> 또는 <xref:System.Windows.Data.BindingMode.OneWayToSource> 바인딩의 경우 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성을 설정 하 여 원본 업데이트의 타이밍을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8e55-116">For <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings, you can control the timing of the source updates by setting the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property.</span></span> <span data-ttu-id="f8e55-117">자세한 내용은 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8e55-117">See <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8e55-118">참조</span><span class="sxs-lookup"><span data-stu-id="f8e55-118">See also</span></span>

- <xref:System.Windows.Data.Binding>
- [<span data-ttu-id="f8e55-119">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="f8e55-119">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="f8e55-120">방법 항목</span><span class="sxs-lookup"><span data-stu-id="f8e55-120">How-to Topics</span></span>](data-binding-how-to-topics.md)

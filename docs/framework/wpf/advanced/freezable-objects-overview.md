---
title: Freezable 개체 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], description
- unfreezing Freezable objects [WPF]
- classes [WPF], Freezable
ms.assetid: 89c71692-4f43-4057-b611-67c6a8a863a2
ms.openlocfilehash: b1887afd19407898d8de1d92252e29778899fb89
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095192"
---
# <a name="freezable-objects-overview"></a><span data-ttu-id="38a5c-102">Freezable 개체 개요</span><span class="sxs-lookup"><span data-stu-id="38a5c-102">Freezable Objects Overview</span></span>

<span data-ttu-id="38a5c-103">이 항목에서는 응용 프로그램 성능을 개선 하는 데 도움이 될 수 있는 특별 한 기능을 제공 하는 <xref:System.Windows.Freezable> 개체를 효과적으로 사용 하 고 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-103">This topic describes how to effectively use and create <xref:System.Windows.Freezable> objects, which provide special features that can help improve application performance.</span></span> <span data-ttu-id="38a5c-104">Freezable 개체의 예로는 브러시, 펜, 변환, 기 하 도형 및 애니메이션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-104">Examples of freezable objects include brushes, pens, transformations, geometries, and animations.</span></span>

<a name="whatisafreezable"></a>

## <a name="what-is-a-freezable"></a><span data-ttu-id="38a5c-105">Freezable 이란?</span><span class="sxs-lookup"><span data-stu-id="38a5c-105">What Is a Freezable?</span></span>

<span data-ttu-id="38a5c-106"><xref:System.Windows.Freezable>은 고정 되지 않음 및 고정의 두 가지 상태를 가진 특수 한 형식의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-106">A <xref:System.Windows.Freezable> is a special type of object that has two states: unfrozen and frozen.</span></span> <span data-ttu-id="38a5c-107">고정 되지 않은 경우 다른 개체 처럼 동작 하는 <xref:System.Windows.Freezable> 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-107">When unfrozen, a <xref:System.Windows.Freezable> appears to behave like any other object.</span></span> <span data-ttu-id="38a5c-108">고정 된 경우에는 <xref:System.Windows.Freezable> 더 이상 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-108">When frozen, a <xref:System.Windows.Freezable> can no longer be modified.</span></span>

<span data-ttu-id="38a5c-109"><xref:System.Windows.Freezable>는 관찰자에 게 개체에 대 한 수정 사항을 알리기 위한 <xref:System.Windows.Freezable.Changed> 이벤트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-109">A <xref:System.Windows.Freezable> provides a <xref:System.Windows.Freezable.Changed> event to notify observers of any modifications to the object.</span></span> <span data-ttu-id="38a5c-110"><xref:System.Windows.Freezable> 고정 하면 변경 알림에서 리소스를 더 이상 사용할 필요가 없기 때문에 성능이 향상 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-110">Freezing a <xref:System.Windows.Freezable> can improve its performance, because it no longer needs to spend resources on change notifications.</span></span> <span data-ttu-id="38a5c-111">고정 된 <xref:System.Windows.Freezable>는 스레드 간에 공유 될 수 있지만 고정 되지 않은 <xref:System.Windows.Freezable>는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-111">A frozen <xref:System.Windows.Freezable> can also be shared across threads, while an unfrozen <xref:System.Windows.Freezable> cannot.</span></span>

<span data-ttu-id="38a5c-112"><xref:System.Windows.Freezable> 클래스에는 많은 응용 프로그램이 있지만 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 <xref:System.Windows.Freezable> 개체 대부분은 그래픽 하위 시스템과 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-112">Although the <xref:System.Windows.Freezable> class has many applications, most <xref:System.Windows.Freezable> objects in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] are related to the graphics sub-system.</span></span>

<span data-ttu-id="38a5c-113"><xref:System.Windows.Freezable> 클래스를 사용 하면 특정 그래픽 시스템 개체를 쉽게 사용 하 고 응용 프로그램 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-113">The <xref:System.Windows.Freezable> class makes it easier to use certain graphics system objects and can help improve application performance.</span></span> <span data-ttu-id="38a5c-114"><xref:System.Windows.Freezable>에서 상속 되는 형식의 예로는 <xref:System.Windows.Media.Brush>, <xref:System.Windows.Media.Transform>및 <xref:System.Windows.Media.Geometry> 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-114">Examples of types that inherit from <xref:System.Windows.Freezable> include the <xref:System.Windows.Media.Brush>, <xref:System.Windows.Media.Transform>, and <xref:System.Windows.Media.Geometry> classes.</span></span> <span data-ttu-id="38a5c-115">관리 되지 않는 리소스가 포함 되어 있기 때문에 시스템은 이러한 개체를 수정 하기 위해 모니터링 한 다음 원래 개체가 변경 될 때 해당 관리 되지 않는 리소스를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-115">Because they contain unmanaged resources, the system must monitor these objects for modifications, and then update their corresponding unmanaged resources when there is a change to the original object.</span></span> <span data-ttu-id="38a5c-116">실제로 그래픽 시스템 개체를 수정 하지 않는 경우에도 시스템은 개체를 변경 하는 경우에도 개체를 모니터링 하는 리소스의 일부를 소비 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-116">Even if you don't actually modify a graphics system object, the system must still spend some of its resources monitoring the object, in case you do change it.</span></span>

<span data-ttu-id="38a5c-117">예를 들어 <xref:System.Windows.Media.SolidColorBrush> 브러시를 만들어 단추의 배경을 칠하는 데 사용 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-117">For example, suppose you create a <xref:System.Windows.Media.SolidColorBrush> brush and use it to paint the background of a button.</span></span>

[!code-csharp[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart1)]
[!code-vb[freezablesample_procedural#FrozenExamplePart1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart1)]

<span data-ttu-id="38a5c-118">단추가 렌더링 되 면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 그래픽 하위 시스템은 사용자가 제공한 정보를 사용 하 여 픽셀 그룹을 페인트 하 여 단추의 모양을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-118">When the button is rendered, the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] graphics sub-system uses the information you provided to paint a group of pixels to create the appearance of a button.</span></span> <span data-ttu-id="38a5c-119">단색 브러시를 사용 하 여 단추를 그려야 하는 방식을 설명 했지만 단색 브러시는 실제로 그리기를 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-119">Although you used a solid color brush to describe how the button should be painted, your solid color brush doesn't actually do the painting.</span></span> <span data-ttu-id="38a5c-120">그래픽 시스템은 단추와 브러시에 대해 빠르고 낮은 수준의 개체를 생성 하 고 실제로 화면에 표시 되는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-120">The graphics system generates fast, low-level objects for the button and the brush, and it is those objects that actually appear on the screen.</span></span>

<span data-ttu-id="38a5c-121">브러시를 수정 하려면 해당 하위 수준 개체를 다시 생성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-121">If you were to modify the brush, those low-level objects would have to be regenerated.</span></span> <span data-ttu-id="38a5c-122">Freezable 클래스는 해당 하는 생성 된 하위 수준 개체를 찾고 변경 될 때이를 업데이트 하는 기능을 브러시에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-122">The freezable class is what gives a brush the ability to find its corresponding generated, low-level objects and to update them when it changes.</span></span> <span data-ttu-id="38a5c-123">이 기능을 사용 하도록 설정 하면 브러시가 "고정 되지 않음"으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-123">When this ability is enabled, the brush is said to be "unfrozen."</span></span>

<span data-ttu-id="38a5c-124">Freezable의 <xref:System.Windows.Freezable.Freeze%2A> 메서드를 사용 하면이 자동 업데이트 기능을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-124">A freezable's <xref:System.Windows.Freezable.Freeze%2A> method enables you to disable this self-updating ability.</span></span> <span data-ttu-id="38a5c-125">이 메서드를 사용 하 여 브러시가 "고정" 또는 수정할 수 없게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-125">You can use this method to make the brush become "frozen," or unmodifiable.</span></span>

> [!NOTE]
> <span data-ttu-id="38a5c-126">모든 Freezable 개체를 고정할 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-126">Not every Freezable object can be frozen.</span></span> <span data-ttu-id="38a5c-127"><xref:System.InvalidOperationException>발생 하지 않도록 하려면 Freezable 개체의 <xref:System.Windows.Freezable.CanFreeze%2A> 속성 값을 확인 하 여 고정을 시도 하기 전에 고정 될 수 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-127">To avoid throwing an <xref:System.InvalidOperationException>, check the value of the Freezable object's <xref:System.Windows.Freezable.CanFreeze%2A> property to determine whether it can be frozen before attempting to freeze it.</span></span>

[!code-csharp[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart2)]
[!code-vb[freezablesample_procedural#FrozenExamplePart2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart2)]

<span data-ttu-id="38a5c-128">더 이상 freezable을 수정할 필요가 없는 경우 고정 하면 성능상의 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-128">When you no longer need to modify a freezable, freezing it provides performance benefits.</span></span> <span data-ttu-id="38a5c-129">이 예에서 브러시를 고정 하는 경우 그래픽 시스템에서 더 이상 변경 내용을 모니터링할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-129">If you were to freeze the brush in this example, the graphics system would no longer need to monitor it for changes.</span></span> <span data-ttu-id="38a5c-130">또한 그래픽 시스템은 브러시가 변경 되지 않는다는 것을 알고 있으므로 다른 최적화를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-130">The graphics system can also make other optimizations, because it knows the brush won't change.</span></span>

> [!NOTE]
> <span data-ttu-id="38a5c-131">편의상 freezable 개체는 명시적으로 고정 하지 않는 한 고정 되지 않은 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-131">For convenience, freezable objects remain unfrozen unless you explicitly freeze them.</span></span>

<a name="frozenfreezables"></a>

## <a name="using-freezables"></a><span data-ttu-id="38a5c-132">Freezable 사용</span><span class="sxs-lookup"><span data-stu-id="38a5c-132">Using Freezables</span></span>

<span data-ttu-id="38a5c-133">고정 되지 않은 freezable을 사용 하는 것은 다른 유형의 개체를 사용 하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-133">Using an unfrozen freezable is like using any other type of object.</span></span> <span data-ttu-id="38a5c-134">다음 예제에서는 단추의 배경을 칠하는 데 사용한 후에는 <xref:System.Windows.Media.SolidColorBrush> 색을 노랑에서 빨강으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-134">In the following example, the color of a <xref:System.Windows.Media.SolidColorBrush> is changed from yellow to red after it's used to paint the background of a button.</span></span> <span data-ttu-id="38a5c-135">그래픽 시스템은 백그라운드에서 작동 하 여 다음에 화면을 새로 고칠 때 단추를 노랑에서 빨강으로 자동으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-135">The graphics system works behind the scenes to automatically change the button from yellow to red the next time the screen is refreshed.</span></span>

[!code-csharp[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#unfrozenexampleshort)]
[!code-vb[freezablesample_procedural#UnFrozenExampleShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#unfrozenexampleshort)]

### <a name="freezing-a-freezable"></a><span data-ttu-id="38a5c-136">Freezable 고정</span><span class="sxs-lookup"><span data-stu-id="38a5c-136">Freezing a Freezable</span></span>

<span data-ttu-id="38a5c-137"><xref:System.Windows.Freezable> 수정할 수 없도록 설정 하려면 해당 <xref:System.Windows.Freezable.Freeze%2A> 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-137">To make a <xref:System.Windows.Freezable> unmodifiable, you call its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span> <span data-ttu-id="38a5c-138">Freezable 개체가 포함 된 개체를 고정 하는 경우 해당 개체도 고정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-138">When you freeze an object that contains freezable objects, those objects are frozen as well.</span></span> <span data-ttu-id="38a5c-139">예를 들어 <xref:System.Windows.Media.PathGeometry>고정 하면 포함 된 도형과 세그먼트만 고정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-139">For example, if you freeze a <xref:System.Windows.Media.PathGeometry>, the figures and segments it contains would be frozen too.</span></span>

<span data-ttu-id="38a5c-140">다음 조건 중 하나에 해당 하는 경우 Freezable을 고정할 수 **없습니다** .</span><span class="sxs-lookup"><span data-stu-id="38a5c-140">A Freezable **can't** be frozen if any of the following are true:</span></span>

- <span data-ttu-id="38a5c-141">애니메이션 또는 데이터 바인딩된 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-141">It has animated or data bound properties.</span></span>

- <span data-ttu-id="38a5c-142">동적 리소스에 의해 설정 된 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-142">It has properties set by a dynamic resource.</span></span> <span data-ttu-id="38a5c-143">동적 리소스에 대 한 자세한 내용은 [XAML 리소스](../../../desktop-wpf/fundamentals/xaml-resources-define.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="38a5c-143">(See the [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md) for more information about dynamic resources.)</span></span>

- <span data-ttu-id="38a5c-144">고정할 수 없는 <xref:System.Windows.Freezable> 하위 개체가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-144">It contains <xref:System.Windows.Freezable> sub-objects that can't be frozen.</span></span>

<span data-ttu-id="38a5c-145">이러한 조건이 false 인 경우 <xref:System.Windows.Freezable>를 수정 하지 않으려는 경우에는 이전에 설명한 성능 이점을 얻기 위해 고정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-145">If these conditions are false, and you don't intend to modify the <xref:System.Windows.Freezable>, then you should freeze it to gain the performance benefits described earlier.</span></span>

<span data-ttu-id="38a5c-146">Freezable의 <xref:System.Windows.Freezable.Freeze%2A> 메서드를 호출한 후에는 더 이상 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-146">Once you call a freezable's <xref:System.Windows.Freezable.Freeze%2A> method, it can no longer be modified.</span></span> <span data-ttu-id="38a5c-147">고정 된 개체를 수정 하려고 하면 <xref:System.InvalidOperationException> throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-147">Attempting to modify a frozen object causes an <xref:System.InvalidOperationException> to be thrown.</span></span> <span data-ttu-id="38a5c-148">다음 코드는 고정 된 후에 브러시를 수정 하려고 하기 때문에 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-148">The following code throws an exception, because we attempt to modify the brush after it's been frozen.</span></span>

[!code-csharp[freezablesample_procedural#ExceptionExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#exceptionexample)]
[!code-vb[freezablesample_procedural#ExceptionExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#exceptionexample)]

<span data-ttu-id="38a5c-149">이 예외가 throw 되지 않도록 <xref:System.Windows.Freezable.IsFrozen%2A> 메서드를 사용 하 여 <xref:System.Windows.Freezable> 고정 되어 있는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-149">To avoid throwing this exception, you can use the <xref:System.Windows.Freezable.IsFrozen%2A> method to determine whether a <xref:System.Windows.Freezable> is frozen.</span></span>

[!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
[!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]

<span data-ttu-id="38a5c-150">위의 코드 예제에서 <xref:System.Windows.Freezable.Clone%2A> 메서드를 사용 하 여 고정 된 개체의 수정 가능한 복사본을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-150">In the preceding code example, a modifiable copy was made of a frozen object using the <xref:System.Windows.Freezable.Clone%2A> method.</span></span> <span data-ttu-id="38a5c-151">다음 섹션에서는 복제에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-151">The next section discusses cloning in more detail.</span></span>

> [!NOTE]
> <span data-ttu-id="38a5c-152">고정 freezable에 애니메이션을 적용할 수 없으므로 <xref:System.Windows.Media.Animation.Storyboard>를 사용 하 여 애니메이션을 적용 하려고 할 때 애니메이션 시스템은 고정 <xref:System.Windows.Freezable> 개체의 수정 가능한 복제본을 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-152">Because a frozen freezable cannot be animated, the animation system will automatically create modifiable clones of frozen <xref:System.Windows.Freezable> objects when you try to animate them with a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="38a5c-153">복제로 인 한 성능 오버 헤드를 없애려면 개체에 애니메이션 효과를 적용 하려는 경우 개체를 고정 되지 않은 상태로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-153">To eliminate the performance overhead caused by cloning, leave an object unfrozen if you intend to animate it.</span></span> <span data-ttu-id="38a5c-154">Storyboard에 애니메이션을 적용 하는 방법에 대 한 자세한 내용은 [Storyboard 개요](../graphics-multimedia/storyboards-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="38a5c-154">For more information about animating with storyboards, see the [Storyboards Overview](../graphics-multimedia/storyboards-overview.md).</span></span>

### <a name="freezing-from-markup"></a><span data-ttu-id="38a5c-155">태그에서 고정</span><span class="sxs-lookup"><span data-stu-id="38a5c-155">Freezing from Markup</span></span>

<span data-ttu-id="38a5c-156">태그에 선언 된 <xref:System.Windows.Freezable> 개체를 고정 하려면 `PresentationOptions:Freeze` 특성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-156">To freeze a <xref:System.Windows.Freezable> object declared in markup, you use the `PresentationOptions:Freeze` attribute.</span></span> <span data-ttu-id="38a5c-157">다음 예제에서는 <xref:System.Windows.Media.SolidColorBrush>을 페이지 리소스로 선언 하 고 고정 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-157">In the following example, a <xref:System.Windows.Media.SolidColorBrush> is declared as a page resource and frozen.</span></span> <span data-ttu-id="38a5c-158">그런 다음 단추의 배경을 설정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-158">It is then used to set the background of a button.</span></span>

[!code-xaml[FreezableSample#FreezeFromMarkupWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/FreezableSample/CS/FreezeFromMarkupExample.xaml#freezefrommarkupwholepage)]

<span data-ttu-id="38a5c-159">`Freeze` 특성을 사용 하려면 `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`프레젠테이션 옵션 네임 스페이스에 매핑해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-159">To use the `Freeze` attribute, you must map to the presentation options namespace: `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`.</span></span> <span data-ttu-id="38a5c-160">이 네임 스페이스를 매핑하기 위한 권장 접두사는 `PresentationOptions`입니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-160">`PresentationOptions` is the recommended prefix for mapping this namespace:</span></span>

```xaml
xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"
```

<span data-ttu-id="38a5c-161">모든 XAML 판독기는이 특성을 인식 하지 않으므로 [mc: Ignorable 특성](mc-ignorable-attribute.md) 을 사용 하 여 `Presentation:Freeze` 특성을 무시할 수 있는 것으로 표시 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-161">Because not all XAML readers recognize this attribute, it's recommended that you use the [mc:Ignorable Attribute](mc-ignorable-attribute.md) to mark the `Presentation:Freeze` attribute as ignorable:</span></span>

```xaml
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
mc:Ignorable="PresentationOptions"
```

<span data-ttu-id="38a5c-162">자세한 내용은 [mc: Ignorable 특성](mc-ignorable-attribute.md) 페이지를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="38a5c-162">For more information, see the [mc:Ignorable Attribute](mc-ignorable-attribute.md) page.</span></span>

### <a name="unfreezing-a-freezable"></a><span data-ttu-id="38a5c-163">Freezable을 "고정 해제" 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-163">"Unfreezing" a Freezable</span></span>

<span data-ttu-id="38a5c-164">고정 되 면 <xref:System.Windows.Freezable>를 수정 하거나 고정 취소할 수 없습니다. 그러나 <xref:System.Windows.Freezable.Clone%2A> 또는 <xref:System.Windows.Freezable.CloneCurrentValue%2A> 메서드를 사용 하 여 고정 되지 않은 클론을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-164">Once frozen, a <xref:System.Windows.Freezable> can never be modified or unfrozen; however, you can create an unfrozen clone using the <xref:System.Windows.Freezable.Clone%2A> or <xref:System.Windows.Freezable.CloneCurrentValue%2A> method.</span></span>

<span data-ttu-id="38a5c-165">다음 예제에서 단추의 배경은 브러시로 설정 되 고 브러시는 고정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-165">In the following example, the button's background is set with a brush and that brush is then frozen.</span></span> <span data-ttu-id="38a5c-166"><xref:System.Windows.Freezable.Clone%2A> 메서드를 사용 하 여 브러시의 고정 되지 않은 복사본이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-166">An unfrozen copy is made of the brush using the <xref:System.Windows.Freezable.Clone%2A> method.</span></span> <span data-ttu-id="38a5c-167">복제본이 수정 되 고 단추의 배경을 노란색에서 빨강으로 변경 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-167">The clone is modified and used to change the button's background from yellow to red.</span></span>

[!code-csharp[freezablesample_procedural#CloneExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
[!code-vb[freezablesample_procedural#CloneExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]

> [!NOTE]
> <span data-ttu-id="38a5c-168">어떤 복제 방법이 사용 되는지에 관계 없이 애니메이션은 새 <xref:System.Windows.Freezable>에 복사 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-168">Regardless of which clone method you use, animations are never copied to the new <xref:System.Windows.Freezable>.</span></span>

<span data-ttu-id="38a5c-169"><xref:System.Windows.Freezable.Clone%2A> 및 <xref:System.Windows.Freezable.CloneCurrentValue%2A> 메서드는 freezable의 전체 복사본을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-169">The <xref:System.Windows.Freezable.Clone%2A> and <xref:System.Windows.Freezable.CloneCurrentValue%2A> methods produce deep copies of the freezable.</span></span> <span data-ttu-id="38a5c-170">Freezable에 고정 된 다른 freezable 개체가 포함 되어 있으면 해당 개체도 복제 되 고 수정할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-170">If the freezable contains other frozen freezable objects, they are also cloned and made modifiable.</span></span> <span data-ttu-id="38a5c-171">예를 들어 고정 된 <xref:System.Windows.Media.PathGeometry>를 복제 하 여 수정할 수 있도록 하는 경우 포함 된 도형과 세그먼트만 복사 되 고 수정할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-171">For example, if you clone a frozen <xref:System.Windows.Media.PathGeometry> to make it modifiable, the figures and segments it contains are also copied and made modifiable.</span></span>

<a name="createyourownfreezableclass"></a>

## <a name="creating-your-own-freezable-class"></a><span data-ttu-id="38a5c-172">사용자 고유의 Freezable 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="38a5c-172">Creating Your Own Freezable Class</span></span>

<span data-ttu-id="38a5c-173"><xref:System.Windows.Freezable>에서 파생 되는 클래스는 다음과 같은 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-173">A class that derives from <xref:System.Windows.Freezable> gains the following features.</span></span>

- <span data-ttu-id="38a5c-174">특수 상태: 읽기 전용 (고정) 및 쓰기 가능 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-174">Special states: a read-only (frozen) and a writable state.</span></span>

- <span data-ttu-id="38a5c-175">스레드 보안: 고정 된 <xref:System.Windows.Freezable> 스레드 간에 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-175">Thread safety: a frozen <xref:System.Windows.Freezable> can be shared across threads.</span></span>

- <span data-ttu-id="38a5c-176">자세한 변경 알림: 다른 <xref:System.Windows.DependencyObject>s와 달리 Freezable 개체는 하위 속성 값이 변경 될 때 변경 알림을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-176">Detailed change notification: Unlike other <xref:System.Windows.DependencyObject>s, Freezable objects provide change notifications when sub-property values change.</span></span>

- <span data-ttu-id="38a5c-177">쉬운 복제: Freezable 클래스가 이미 전체 복제를 만드는 여러 메서드를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-177">Easy cloning: the Freezable class has already implemented several methods that produce deep clones.</span></span>

<span data-ttu-id="38a5c-178"><xref:System.Windows.Freezable>은 <xref:System.Windows.DependencyObject>형식 이므로 종속성 속성 시스템을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-178">A <xref:System.Windows.Freezable> is a type of <xref:System.Windows.DependencyObject>, and therefore uses the dependency property system.</span></span> <span data-ttu-id="38a5c-179">클래스 속성은 종속성 속성이 될 필요는 없지만 종속성 속성을 사용 하면 <xref:System.Windows.Freezable> 클래스가 종속성 속성을 염두에 두면 디자인 되었으므로 작성 해야 하는 코드의 양이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-179">Your class properties don't have to be dependency properties, but using dependency properties will reduce the amount of code you have to write, because the <xref:System.Windows.Freezable> class was designed with dependency properties in mind.</span></span> <span data-ttu-id="38a5c-180">종속성 속성 시스템에 대 한 자세한 내용은 [종속성 속성 개요](dependency-properties-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="38a5c-180">For more information about the dependency property system, see the [Dependency Properties Overview](dependency-properties-overview.md).</span></span>

<span data-ttu-id="38a5c-181">모든 <xref:System.Windows.Freezable> 서브 클래스는 <xref:System.Windows.Freezable.CreateInstanceCore%2A> 메서드를 재정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-181">Every <xref:System.Windows.Freezable> subclass must override the <xref:System.Windows.Freezable.CreateInstanceCore%2A> method.</span></span> <span data-ttu-id="38a5c-182">클래스에서 모든 데이터에 대 한 종속성 속성을 사용 하면 작업이 완료 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-182">If your class uses dependency properties for all its data, you're finished.</span></span>

<span data-ttu-id="38a5c-183">클래스에 종속성이 아닌 속성 데이터 멤버가 포함 된 경우에는 다음 메서드도 재정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-183">If your class contains non-dependency property data members, you must also override the following methods:</span></span>

- <xref:System.Windows.Freezable.CloneCore%2A>

- <xref:System.Windows.Freezable.CloneCurrentValueCore%2A>

- <xref:System.Windows.Freezable.GetAsFrozenCore%2A>

- <xref:System.Windows.Freezable.GetCurrentValueAsFrozenCore%2A>

- <xref:System.Windows.Freezable.FreezeCore%2A>

<span data-ttu-id="38a5c-184">또한 종속성 속성이 아닌 데이터 멤버에 액세스 하 고 쓰려면 다음 규칙을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-184">You must also observe the following rules for accessing and writing to data members that are not dependency properties:</span></span>

- <span data-ttu-id="38a5c-185">비 종속성 속성 데이터 멤버를 읽는 API의 시작 부분에서 <xref:System.Windows.Freezable.ReadPreamble%2A> 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-185">At the beginning of any API that reads non-dependency property data members, call the <xref:System.Windows.Freezable.ReadPreamble%2A> method.</span></span>

- <span data-ttu-id="38a5c-186">비 종속성 속성 데이터 멤버를 작성 하는 API의 시작 부분에서 <xref:System.Windows.Freezable.WritePreamble%2A> 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-186">At the beginning of any API that writes non-dependency property data members, call the <xref:System.Windows.Freezable.WritePreamble%2A> method.</span></span> <span data-ttu-id="38a5c-187">API에서 <xref:System.Windows.Freezable.WritePreamble%2A>를 호출한 후에는 종속성이 아닌 속성 데이터 멤버도 읽을 경우 <xref:System.Windows.Freezable.ReadPreamble%2A>에 대 한 추가 호출을 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-187">(Once you've called <xref:System.Windows.Freezable.WritePreamble%2A> in an API, you don't need to make an additional call to <xref:System.Windows.Freezable.ReadPreamble%2A> if you also read non-dependency property data members.)</span></span>

- <span data-ttu-id="38a5c-188">비 종속성 속성 데이터 멤버에 쓰는 메서드를 종료 하기 전에 <xref:System.Windows.Freezable.WritePostscript%2A> 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-188">Call the <xref:System.Windows.Freezable.WritePostscript%2A> method before exiting methods that write to non-dependency property data members.</span></span>

<span data-ttu-id="38a5c-189">클래스에 <xref:System.Windows.DependencyObject> 개체를 포함 하는 비 종속성 속성 데이터 멤버가 포함 된 경우 멤버를 `null`로 설정 하더라도 해당 값 중 하나를 변경할 때마다 <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-189">If your class contains non-dependency-property data members that are <xref:System.Windows.DependencyObject> objects, you must also call the <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> method each time you change one of their values, even if you're setting the member to `null`.</span></span>

> [!NOTE]
> <span data-ttu-id="38a5c-190">기본 구현에 대 한 호출을 사용 하 여 재정의 하는 각 <xref:System.Windows.Freezable> 메서드를 시작 하는 것이 매우 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a5c-190">It's very important that you begin each <xref:System.Windows.Freezable> method you override with a call to the base implementation.</span></span>

<span data-ttu-id="38a5c-191">사용자 지정 <xref:System.Windows.Freezable> 클래스에 대 한 예제는 [사용자 지정 애니메이션 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="38a5c-191">For an example of a custom <xref:System.Windows.Freezable> class, see the [Custom Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation).</span></span>

## <a name="see-also"></a><span data-ttu-id="38a5c-192">참고 항목</span><span class="sxs-lookup"><span data-stu-id="38a5c-192">See also</span></span>

- <xref:System.Windows.Freezable>
- [<span data-ttu-id="38a5c-193">사용자 지정 애니메이션 샘플</span><span class="sxs-lookup"><span data-stu-id="38a5c-193">Custom Animation Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation)
- [<span data-ttu-id="38a5c-194">종속성 속성 개요</span><span class="sxs-lookup"><span data-stu-id="38a5c-194">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="38a5c-195">사용자 지정 종속성 속성</span><span class="sxs-lookup"><span data-stu-id="38a5c-195">Custom Dependency Properties</span></span>](custom-dependency-properties.md)

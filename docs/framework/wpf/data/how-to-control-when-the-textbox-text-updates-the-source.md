---
title: '방법: TextBox 텍스트의 소스를 업데이트하는 시점 제어'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source updates [WPF], timing of
- data binding [WPF], timing of source updates
- timing of source updates [WPF]
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
ms.openlocfilehash: b211eb67e3bac95f74255935a39cc0d6aec61531
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974790"
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a><span data-ttu-id="44726-102">방법: TextBox 텍스트의 소스를 업데이트하는 시점 제어</span><span class="sxs-lookup"><span data-stu-id="44726-102">How to: Control When the TextBox Text Updates the Source</span></span>
<span data-ttu-id="44726-103">이 항목에서는 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성을 사용 하 여 바인딩 소스 업데이트의 타이밍을 제어 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="44726-103">This topic describes how to use the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property to control the timing of binding source updates.</span></span> <span data-ttu-id="44726-104">이 항목에서는 <xref:System.Windows.Controls.TextBox> 컨트롤을 예로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="44726-104">The topic uses the <xref:System.Windows.Controls.TextBox> control as an example.</span></span>

## <a name="example"></a><span data-ttu-id="44726-105">예제</span><span class="sxs-lookup"><span data-stu-id="44726-105">Example</span></span>
 <span data-ttu-id="44726-106"><xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> 속성에는 <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>의 기본 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44726-106">The <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> property has a default <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value of <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>.</span></span> <span data-ttu-id="44726-107">즉, 응용 프로그램에 데이터 바인딩된 <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> 속성의 <xref:System.Windows.Controls.TextBox> 있는 경우 <xref:System.Windows.Controls.TextBox>에 입력 하는 텍스트는 <xref:System.Windows.Controls.TextBox> 포커스를 잃을 때까지 (예를 들어 <xref:System.Windows.Controls.TextBox>에서 떨어진 곳을 클릭 하는 경우) 원본을 업데이트 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44726-107">This means if an application has a <xref:System.Windows.Controls.TextBox> with a data-bound <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> property, the text you type into the <xref:System.Windows.Controls.TextBox> does not update the source until the <xref:System.Windows.Controls.TextBox> loses focus (for instance, when you click away from the <xref:System.Windows.Controls.TextBox>).</span></span>

 <span data-ttu-id="44726-108">입력할 때 소스를 업데이트 하려면 바인딩의 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="44726-108">If you want the source to be updated as you type, set the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> of the binding to <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span> <span data-ttu-id="44726-109">다음 예제에서 강조 표시 된 코드 줄은 <xref:System.Windows.Controls.TextBox> 및 <xref:System.Windows.Controls.TextBlock>의 `Text` 속성이 동일한 소스 속성에 바인딩되어 있음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="44726-109">In the following example, the highlighted lines of code show that the `Text` properties of both the <xref:System.Windows.Controls.TextBox> and the <xref:System.Windows.Controls.TextBlock> are bound to the same source property.</span></span> <span data-ttu-id="44726-110"><xref:System.Windows.Controls.TextBox> 바인딩의 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성이 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44726-110">The <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property of the <xref:System.Windows.Controls.TextBox> binding is set to <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span>

 [!code-xaml[SimpleBinding#USTHowTo](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=33-39,41-42)]

 <span data-ttu-id="44726-111">따라서 샘플의 다음 스크린샷에 표시 된 것 처럼 사용자가 <xref:System.Windows.Controls.TextBox>에 텍스트를 입력 하면 소스가 변경 되므로 <xref:System.Windows.Controls.TextBlock>는 동일한 텍스트를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="44726-111">As a result, the <xref:System.Windows.Controls.TextBlock> shows the same text (because the source changes) as the user enters text into the <xref:System.Windows.Controls.TextBox>, as illustrated by the following screenshot of the sample:</span></span>

 ![간단한 데이터 바인딩을 보여 주는 스크린샷](./media/how-to-control-when-the-textbox-text-updates-the-source/data-binding-simple-binding-sample.png)

 <span data-ttu-id="44726-113">대화 상자 또는 사용자가 편집할 수 있는 폼이 있고 사용자가 필드 편집을 마치고 "확인"을 클릭할 때까지 원본 업데이트를 지연 하려는 경우 다음 예제와 같이 바인딩의 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값을 <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44726-113">If you have a dialog or a user-editable form and you want to defer source updates until the user is finished editing the fields and clicks "OK", you can set the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value of your bindings to <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, as in the following example:</span></span>

 [!code-xaml[UpdateSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]

 <span data-ttu-id="44726-114"><xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값을 <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>로 설정 하면 응용 프로그램에서 <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> 메서드를 호출 하는 경우에만 소스 값이 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44726-114">When you set the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value to <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, the source value only changes when the application calls the <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> method.</span></span> <span data-ttu-id="44726-115">다음 예제에서는 `itemNameTextBox`에 대해 <xref:System.Windows.Data.BindingExpression.UpdateSource%2A>를 호출 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="44726-115">The following example shows how to call <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> for `itemNameTextBox`:</span></span>

 [!code-csharp[UpdateSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]

> [!NOTE]
> <span data-ttu-id="44726-116">다른 컨트롤의 속성에 동일한 기법을 사용할 수 있지만 대부분의 다른 속성에는 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>의 기본 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44726-116">You can use the same technique for properties of other controls, but keep in mind that most other properties have a default <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value of <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span> <span data-ttu-id="44726-117">자세한 내용은 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성 페이지를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="44726-117">For more information, see the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property page.</span></span>

> [!NOTE]
> <span data-ttu-id="44726-118"><xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성은 원본 업데이트를 처리 하므로 <xref:System.Windows.Data.BindingMode.TwoWay> 또는 <xref:System.Windows.Data.BindingMode.OneWayToSource> 바인딩과만 관련 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44726-118">The <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property deals with source updates and therefore is only relevant for <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings.</span></span> <span data-ttu-id="44726-119"><xref:System.Windows.Data.BindingMode.TwoWay> 및 <xref:System.Windows.Data.BindingMode.OneWayToSource> 바인딩이 작동 하려면 원본 개체에서 속성 변경 알림을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44726-119">For <xref:System.Windows.Data.BindingMode.TwoWay> and <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings to work, the source object needs to provide property change notifications.</span></span> <span data-ttu-id="44726-120">자세한 내용은 이 항목에 제시된 샘플을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44726-120">You can refer to the samples cited in this topic for more information.</span></span> <span data-ttu-id="44726-121">또한 [속성 변경 알림 구현](how-to-implement-property-change-notification.md)을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44726-121">In addition, you can look at [Implement Property Change Notification](how-to-implement-property-change-notification.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="44726-122">참조</span><span class="sxs-lookup"><span data-stu-id="44726-122">See also</span></span>

- [<span data-ttu-id="44726-123">방법 항목</span><span class="sxs-lookup"><span data-stu-id="44726-123">How-to Topics</span></span>](data-binding-how-to-topics.md)

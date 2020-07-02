---
title: '방법: 바인딩 유효성 검사 구현'
description: Windows Presentation Foundation (WPF)에 잘못 된 값이 입력 된 경우 바인딩 유효성 검사를 사용 하 여 사용자에 게 시각적 피드백을 제공 하는 방법을 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validation of binding [WPF]
- data binding [WPF], validation of binding
- binding [WPF], validation of
ms.assetid: eb98b33d-9866-49ae-b981-bc5ff20d607a
ms.openlocfilehash: 0813be9f79a83a9dae26db1dadb58b5e973339fd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617884"
---
# <a name="how-to-implement-binding-validation"></a><span data-ttu-id="1ff61-103">방법: 바인딩 유효성 검사 구현</span><span class="sxs-lookup"><span data-stu-id="1ff61-103">How to: Implement Binding Validation</span></span>

<span data-ttu-id="1ff61-104">이 예제에서는 및 스타일 트리거를 사용 하 여 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 사용자 지정 유효성 검사 규칙을 기반으로 잘못 된 값이 입력 될 때 사용자에 게 알리는 시각적 피드백을 제공 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1ff61-104">This example shows how to use an <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> and a style trigger to provide visual feedback to inform the user when an invalid value is entered, based on a custom validation rule.</span></span>

## <a name="example"></a><span data-ttu-id="1ff61-105">예제</span><span class="sxs-lookup"><span data-stu-id="1ff61-105">Example</span></span>

<span data-ttu-id="1ff61-106">다음 예제에서의 텍스트 콘텐츠는 <xref:System.Windows.Controls.TextBox> `Age` 이라는 바인딩 소스 개체의 속성 (int 형식의 속성)에 바인딩됩니다 `ods` .</span><span class="sxs-lookup"><span data-stu-id="1ff61-106">The text content of the <xref:System.Windows.Controls.TextBox> in the following example is bound to the `Age` property (of type int) of a binding source object named `ods`.</span></span> <span data-ttu-id="1ff61-107">바인딩이 `AgeRangeRule`이라는 유효성 검사 규칙을 사용하도록 설정되어 있으므로 숫자가 아닌 문자 또는 21보다 작거나 130보다 큰 값을 입력하면 빨간색 느낌표가 텍스트 상자 옆에 나타나고 텍스트 상자 위로 마우스를 이동하면 오류 메시지가 포함된 도구 설명이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="1ff61-107">The binding is set up to use a validation rule named `AgeRangeRule` so that if the user enters non-numeric characters or a value that is smaller than 21 or greater than 130, a red exclamation mark appears next to the text box and a tool tip with the error message appears when the user moves the mouse over the text box.</span></span>

[!code-xaml[BindValidation#2](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]

<span data-ttu-id="1ff61-108">다음 예제에서는 `AgeRangeRule` 에서 상속 되 고 메서드를 재정의 하는의 구현을 보여 줍니다 <xref:System.Windows.Controls.ValidationRule> <xref:System.Windows.Controls.ValidationRule.Validate%2A> .</span><span class="sxs-lookup"><span data-stu-id="1ff61-108">The following example shows the implementation of `AgeRangeRule`, which inherits from <xref:System.Windows.Controls.ValidationRule> and overrides the <xref:System.Windows.Controls.ValidationRule.Validate%2A> method.</span></span> <span data-ttu-id="1ff61-109">`Int32.Parse`값에 대해 메서드를 호출 하 여 잘못 된 문자를 포함 하지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ff61-109">The `Int32.Parse` method is called on the value to make sure that it does not contain any invalid characters.</span></span> <span data-ttu-id="1ff61-110"><xref:System.Windows.Controls.ValidationRule.Validate%2A>메서드는 <xref:System.Windows.Controls.ValidationResult> 구문 분석 중에 예외가 catch 되는지 여부와 사용 기간 값이 하 한과 상한 범위 밖에 있는지 여부에 따라 값이 유효한 지 여부를 나타내는을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ff61-110">The <xref:System.Windows.Controls.ValidationRule.Validate%2A> method returns a <xref:System.Windows.Controls.ValidationResult> that indicates if the value is valid based on whether an exception is caught during the parsing and whether the age value is outside of the lower and upper bounds.</span></span>

[!code-csharp[BindValidation#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]
[!code-vb[BindValidation#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindValidation/VisualBasic/AgeRangeRule.vb#3)]

<span data-ttu-id="1ff61-111">다음 예제에서는 <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` 사용자에 게 유효성 검사 오류를 알리는 빨간색 느낌표를 만드는 사용자 지정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1ff61-111">The following example shows the custom <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` that creates a red exclamation mark to notify the user of a validation error.</span></span> <span data-ttu-id="1ff61-112">컨트롤 템플릿을 사용하여 컨트롤의 모양을 다시 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1ff61-112">Control templates are used to redefine the appearance of a control.</span></span>

[!code-xaml[BindValidation#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]

<span data-ttu-id="1ff61-113">다음 예제와 같이 <xref:System.Windows.Controls.ToolTip> 오류 메시지를 표시 하는는 이라는 스타일을 사용 하 여 생성 됩니다 `textBoxInError` .</span><span class="sxs-lookup"><span data-stu-id="1ff61-113">As shown in the following example, the <xref:System.Windows.Controls.ToolTip> that shows the error message is created using the style named `textBoxInError`.</span></span> <span data-ttu-id="1ff61-114">의 값이 이면 <xref:System.Windows.Controls.Validation.HasError%2A> `true` 트리거는 현재의 도구 설명을 <xref:System.Windows.Controls.TextBox> 첫 번째 유효성 검사 오류로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ff61-114">If the value of <xref:System.Windows.Controls.Validation.HasError%2A> is `true`, the trigger sets the tool tip of the current <xref:System.Windows.Controls.TextBox> to its first validation error.</span></span> <span data-ttu-id="1ff61-115">는 <xref:System.Windows.Data.Binding.RelativeSource%2A> 현재 요소를 참조 하는로 설정 됩니다 <xref:System.Windows.Data.RelativeSourceMode.Self> .</span><span class="sxs-lookup"><span data-stu-id="1ff61-115">The <xref:System.Windows.Data.Binding.RelativeSource%2A> is set to <xref:System.Windows.Data.RelativeSourceMode.Self>, referring to the current element.</span></span>

[!code-xaml[BindValidation#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]

<span data-ttu-id="1ff61-116">전체 예제는 [바인딩 유효성 검사 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ff61-116">For the complete example, see [Bind Validation sample](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation).</span></span>
  
<span data-ttu-id="1ff61-117">사용자 지정을 제공 하지 않으면 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 유효성 검사 오류가 있을 때 사용자에 게 시각적 피드백을 제공 하는 기본 오류 템플릿이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ff61-117">Note that if you do not provide a custom <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> the default error template appears to provide visual feedback to the user when there is a validation error.</span></span> <span data-ttu-id="1ff61-118">자세한 내용은 [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)의 “데이터 유효성 검사”를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1ff61-118">See "Data Validation" in [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md) for more information.</span></span> <span data-ttu-id="1ff61-119">또한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]은 바인딩 소스 속성을 업데이트하는 동안 throw된 예외를 catch하는 기본 제공 유효성 검사 규칙을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1ff61-119">Also, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] provides a built-in validation rule that catches exceptions that are thrown during the update of the binding source property.</span></span> <span data-ttu-id="1ff61-120">자세한 내용은 <xref:System.Windows.Controls.ExceptionValidationRule>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1ff61-120">For more information, see <xref:System.Windows.Controls.ExceptionValidationRule>.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ff61-121">참조</span><span class="sxs-lookup"><span data-stu-id="1ff61-121">See also</span></span>

- [<span data-ttu-id="1ff61-122">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="1ff61-122">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="1ff61-123">방법 도움말 항목</span><span class="sxs-lookup"><span data-stu-id="1ff61-123">How-to Topics</span></span>](data-binding-how-to-topics.md)

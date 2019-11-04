---
title: '방법: 바인딩 유효성 검사 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validation of binding [WPF]
- data binding [WPF], validation of binding
- binding [WPF], validation of
ms.assetid: eb98b33d-9866-49ae-b981-bc5ff20d607a
ms.openlocfilehash: 245b05d9cfa7ca66dec310bd9a5291def0101d19
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459114"
---
# <a name="how-to-implement-binding-validation"></a><span data-ttu-id="3fbf2-102">방법: 바인딩 유효성 검사 구현</span><span class="sxs-lookup"><span data-stu-id="3fbf2-102">How to: Implement Binding Validation</span></span>

<span data-ttu-id="3fbf2-103">이 예제에서는 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 및 스타일 트리거를 사용 하 여 사용자 지정 유효성 검사 규칙에 따라 잘못 된 값이 입력 될 때 사용자에 게 알리는 시각적 피드백을 제공 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3fbf2-103">This example shows how to use an <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> and a style trigger to provide visual feedback to inform the user when an invalid value is entered, based on a custom validation rule.</span></span>

## <a name="example"></a><span data-ttu-id="3fbf2-104">예제</span><span class="sxs-lookup"><span data-stu-id="3fbf2-104">Example</span></span>

<span data-ttu-id="3fbf2-105">다음 예제에서 <xref:System.Windows.Controls.TextBox> 텍스트 콘텐츠는 `ods`이라는 바인딩 소스 개체의 `Age` 속성 (int 형식)에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fbf2-105">The text content of the <xref:System.Windows.Controls.TextBox> in the following example is bound to the `Age` property (of type int) of a binding source object named `ods`.</span></span> <span data-ttu-id="3fbf2-106">바인딩이 `AgeRangeRule`이라는 유효성 검사 규칙을 사용하도록 설정되어 있으므로 숫자가 아닌 문자 또는 21보다 작거나 130보다 큰 값을 입력하면 빨간색 느낌표가 텍스트 상자 옆에 나타나고 텍스트 상자 위로 마우스를 이동하면 오류 메시지가 포함된 도구 설명이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="3fbf2-106">The binding is set up to use a validation rule named `AgeRangeRule` so that if the user enters non-numeric characters or a value that is smaller than 21 or greater than 130, a red exclamation mark appears next to the text box and a tool tip with the error message appears when the user moves the mouse over the text box.</span></span>

[!code-xaml[BindValidation#2](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]

<span data-ttu-id="3fbf2-107">다음 예제에서는 <xref:System.Windows.Controls.ValidationRule>에서 상속 되 고 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 메서드를 재정의 하는 `AgeRangeRule`의 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3fbf2-107">The following example shows the implementation of `AgeRangeRule`, which inherits from <xref:System.Windows.Controls.ValidationRule> and overrides the <xref:System.Windows.Controls.ValidationRule.Validate%2A> method.</span></span> <span data-ttu-id="3fbf2-108">값에 대해 `Int32.Parse` 메서드를 호출 하 여 잘못 된 문자를 포함 하지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbf2-108">The `Int32.Parse` method is called on the value to make sure that it does not contain any invalid characters.</span></span> <span data-ttu-id="3fbf2-109"><xref:System.Windows.Controls.ValidationRule.Validate%2A> 메서드는 구문 분석 중에 예외가 catch 되는지 여부와 사용 기간 값이 하한값과 상한 인지 여부를 기준으로 값이 유효한 지 여부를 나타내는 <xref:System.Windows.Controls.ValidationResult>을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbf2-109">The <xref:System.Windows.Controls.ValidationRule.Validate%2A> method returns a <xref:System.Windows.Controls.ValidationResult> that indicates if the value is valid based on whether an exception is caught during the parsing and whether the age value is outside of the lower and upper bounds.</span></span>

[!code-csharp[BindValidation#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]
[!code-vb[BindValidation#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindValidation/VisualBasic/AgeRangeRule.vb#3)]

<span data-ttu-id="3fbf2-110">다음 예제에서는 사용자에 게 유효성 검사 오류를 알리기 위해 빨간색 느낌표를 만드는 사용자 지정 <xref:System.Windows.Controls.ControlTemplate> `validationTemplate`을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3fbf2-110">The following example shows the custom <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` that creates a red exclamation mark to notify the user of a validation error.</span></span> <span data-ttu-id="3fbf2-111">컨트롤 템플릿을 사용하여 컨트롤의 모양을 다시 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbf2-111">Control templates are used to redefine the appearance of a control.</span></span>

[!code-xaml[BindValidation#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]

<span data-ttu-id="3fbf2-112">다음 예제와 같이 오류 메시지를 표시 하는 <xref:System.Windows.Controls.ToolTip> `textBoxInError`이라는 스타일을 사용 하 여 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fbf2-112">As shown in the following example, the <xref:System.Windows.Controls.ToolTip> that shows the error message is created using the style named `textBoxInError`.</span></span> <span data-ttu-id="3fbf2-113"><xref:System.Windows.Controls.Validation.HasError%2A> 값이 `true`되는 경우 트리거는 현재 <xref:System.Windows.Controls.TextBox>의 도구 설명을 첫 번째 유효성 검사 오류로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbf2-113">If the value of <xref:System.Windows.Controls.Validation.HasError%2A> is `true`, the trigger sets the tool tip of the current <xref:System.Windows.Controls.TextBox> to its first validation error.</span></span> <span data-ttu-id="3fbf2-114"><xref:System.Windows.Data.Binding.RelativeSource%2A> 현재 요소를 참조 하는 <xref:System.Windows.Data.RelativeSourceMode.Self>로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fbf2-114">The <xref:System.Windows.Data.Binding.RelativeSource%2A> is set to <xref:System.Windows.Data.RelativeSourceMode.Self>, referring to the current element.</span></span>

[!code-xaml[BindValidation#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]

<span data-ttu-id="3fbf2-115">전체 예제는 [바인딩 유효성 검사 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3fbf2-115">For the complete example, see [Bind Validation sample](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation).</span></span>
  
<span data-ttu-id="3fbf2-116">사용자 지정 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 제공 하지 않으면 유효성 검사 오류가 있을 때 사용자에 게 시각적 피드백을 제공 하는 기본 오류 템플릿이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fbf2-116">Note that if you do not provide a custom <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> the default error template appears to provide visual feedback to the user when there is a validation error.</span></span> <span data-ttu-id="3fbf2-117">자세한 내용은 [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)의 “데이터 유효성 검사”를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3fbf2-117">See "Data Validation" in [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md) for more information.</span></span> <span data-ttu-id="3fbf2-118">또한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]은 바인딩 소스 속성을 업데이트하는 동안 throw된 예외를 catch하는 기본 제공 유효성 검사 규칙을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3fbf2-118">Also, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] provides a built-in validation rule that catches exceptions that are thrown during the update of the binding source property.</span></span> <span data-ttu-id="3fbf2-119">자세한 내용은 <xref:System.Windows.Controls.ExceptionValidationRule>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3fbf2-119">For more information, see <xref:System.Windows.Controls.ExceptionValidationRule>.</span></span>

## <a name="see-also"></a><span data-ttu-id="3fbf2-120">참조</span><span class="sxs-lookup"><span data-stu-id="3fbf2-120">See also</span></span>

- [<span data-ttu-id="3fbf2-121">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="3fbf2-121">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="3fbf2-122">방법 항목</span><span class="sxs-lookup"><span data-stu-id="3fbf2-122">How-to Topics</span></span>](data-binding-how-to-topics.md)

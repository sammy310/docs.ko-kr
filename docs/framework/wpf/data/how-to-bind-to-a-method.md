---
title: '방법: 메서드 바인딩'
description: 다음 예제에 따라 Windows Presentation Foundation (WPF)에서 개체의 메서드에 바인딩하는 방법을 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding to methods using ObjectDataProvider
- binding [WPF], to methods
- methods [WPF], binding to
ms.assetid: 5f55e71e-2182-42a0-88d1-700cc1427a7a
ms.openlocfilehash: 9501e6357203c21651e85f1d65059be1d70becf2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619600"
---
# <a name="how-to-bind-to-a-method"></a><span data-ttu-id="00635-103">방법: 메서드 바인딩</span><span class="sxs-lookup"><span data-stu-id="00635-103">How to: Bind to a Method</span></span>
<span data-ttu-id="00635-104">다음 예제에서는를 사용 하 여 메서드에 바인딩하는 방법을 보여 줍니다 <xref:System.Windows.Data.ObjectDataProvider> .</span><span class="sxs-lookup"><span data-stu-id="00635-104">The following example shows how to bind to a method using <xref:System.Windows.Data.ObjectDataProvider>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00635-105">예제</span><span class="sxs-lookup"><span data-stu-id="00635-105">Example</span></span>  
 <span data-ttu-id="00635-106">이 예에서 `TemperatureScale`는 `ConvertTemp` 메서드가 있는 클래스입니다. 이 메서드에서는 두 개의 매개 변수(`double` 중 하나와 `enum` 형식 `TempType)` 중 하나)를 사용하고 지정된 값을 한 온도 눈금에서 다른 눈금으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="00635-106">In this example, `TemperatureScale` is a class that has a method `ConvertTemp`, which takes two parameters (one of `double` and one of the `enum` type `TempType)` and converts the given value from one temperature scale to another.</span></span> <span data-ttu-id="00635-107">다음 예제에서는 개체를 <xref:System.Windows.Data.ObjectDataProvider> 인스턴스화하는 데 사용 됩니다 `TemperatureScale` .</span><span class="sxs-lookup"><span data-stu-id="00635-107">In the following example, an <xref:System.Windows.Data.ObjectDataProvider> is used to instantiate the `TemperatureScale` object.</span></span> <span data-ttu-id="00635-108">`ConvertTemp` 메서드는 지정된 두 매개 변수를 사용하여 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="00635-108">The `ConvertTemp` method is called with two specified parameters.</span></span>  
  
 [!code-xaml[BindToMethod#WindowResources](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#windowresources)]  
  
 <span data-ttu-id="00635-109">이제 메서드를 리소스로 사용할 수 있으므로, 해당 결과에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00635-109">Now that the method is available as a resource, you can bind to its results.</span></span> <span data-ttu-id="00635-110">다음 예제에서의 및의 <xref:System.Windows.Controls.TextBox.Text%2A> 속성은 <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> <xref:System.Windows.Controls.ComboBox> 메서드의 두 매개 변수에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="00635-110">In the following example, the <xref:System.Windows.Controls.TextBox.Text%2A> property of the <xref:System.Windows.Controls.TextBox> and the <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> of the <xref:System.Windows.Controls.ComboBox> are bound to the two parameters of the method.</span></span> <span data-ttu-id="00635-111">그러면 변환될 대상 온도와 변환될 소스 온도 눈금을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00635-111">This allows users to specify the temperature to convert and the temperature scale to convert from.</span></span> <span data-ttu-id="00635-112">는 <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A> `true` <xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A> 인스턴스의 속성에 바인딩하고 <xref:System.Windows.Data.ObjectDataProvider> <xref:System.Windows.Data.ObjectDataProvider> (개체)로 래핑된 개체의 속성이 아닌로 설정 됩니다 `TemperatureScale` .</span><span class="sxs-lookup"><span data-stu-id="00635-112">Note that <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A> is set to `true` because we are binding to the <xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A> property of the <xref:System.Windows.Data.ObjectDataProvider> instance and not properties of the object wrapped by the <xref:System.Windows.Data.ObjectDataProvider> (the `TemperatureScale` object).</span></span>  
  
 <span data-ttu-id="00635-113"><xref:System.Windows.Controls.ContentControl.Content%2A> <xref:System.Windows.Controls.Label> 사용자가의 콘텐츠 또는 선택 항목을 수정할 때 마지막으로 업데이트 한의입니다 <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.ComboBox> .</span><span class="sxs-lookup"><span data-stu-id="00635-113">The <xref:System.Windows.Controls.ContentControl.Content%2A> of the last <xref:System.Windows.Controls.Label> updates when the user modifies the content of the <xref:System.Windows.Controls.TextBox> or the selection of the <xref:System.Windows.Controls.ComboBox>.</span></span>  
  
 [!code-xaml[BindToMethod#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#ui)]  
  
 <span data-ttu-id="00635-114">변환기는 `DoubleToString` double을 사용 하 여 <xref:System.Windows.Data.IValueConverter.Convert%2A> 방향의 문자열 (바인딩 소스에서 바인딩 대상까지 <xref:System.Windows.Controls.TextBox.Text%2A> 속성)로 변환 하 고를 `string` `double` 방향으로 변환 합니다 <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> .</span><span class="sxs-lookup"><span data-stu-id="00635-114">The converter `DoubleToString` takes a double and turns it into a string in the <xref:System.Windows.Data.IValueConverter.Convert%2A> direction (from the binding source to binding target, which is the <xref:System.Windows.Controls.TextBox.Text%2A> property) and converts a `string` to a `double` in the <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> direction.</span></span>  
  
 <span data-ttu-id="00635-115">는 `InvalidationCharacterRule` <xref:System.Windows.Controls.ValidationRule> 잘못 된 문자를 확인 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="00635-115">The `InvalidationCharacterRule` is a <xref:System.Windows.Controls.ValidationRule> that checks for invalid characters.</span></span> <span data-ttu-id="00635-116">의 빨간색 테두리 인 기본 오류 템플릿은 <xref:System.Windows.Controls.TextBox> 입력 값이 double 값이 아닌 경우 사용자에 게 알리는 것으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="00635-116">The default error template, which is a red border around the <xref:System.Windows.Controls.TextBox>, appears to notify users when the input value is not a double value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00635-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="00635-117">See also</span></span>

- [<span data-ttu-id="00635-118">방법 도움말 항목</span><span class="sxs-lookup"><span data-stu-id="00635-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
- [<span data-ttu-id="00635-119">열거형에 바인딩</span><span class="sxs-lookup"><span data-stu-id="00635-119">Bind to an Enumeration</span></span>](how-to-bind-to-an-enumeration.md)

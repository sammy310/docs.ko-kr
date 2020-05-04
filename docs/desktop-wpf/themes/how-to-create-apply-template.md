---
title: WPF에서 템플릿 만들기 - .NET Desktop
description: Windows Presentation Foundation 및 .NET Core에서 컨트롤 템플릿을 만들고 참조하는 방법을 알아봅니다.
author: thraka
ms.author: adegeo
ms.date: 11/15/2019
no-loc:
- <Window>
- <ControlTemplate>
- <Ellipse>
- <ContentPresenter>
- <Trigger>
- <Setter>
- <PropertyTrigger>
- <Grid>
- <VisualStateManager.VisualStateGroups>
- <VisualStateGroup>
- <VisualState>
- <Storyboard>
- SizeToContent
- MinWidth
- TargetType
- Title
helpviewer_keywords:
- control contract [WPF]
- controls [WPF], visual structure changes
- ControlTemplate [WPF], customizing for existing controls
- skinning controls [WPF]
- controls [WPF], appearance specified by state
- templates [WPF], custom for existing controls
ms.openlocfilehash: c901864d387b8de976bbfa9a9b3c14a7d5a0b4d8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "81432541"
---
# <a name="create-a-template-for-a-control"></a><span data-ttu-id="9fef1-103">컨트롤의 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="9fef1-103">Create a template for a control</span></span>

<span data-ttu-id="9fef1-104">WPF(Windows Presentation Foundation)를 사용하면 다시 사용할 수 있는 템플릿을 사용하여 기존 컨트롤의 시각적 구조 및 동작을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-104">With Windows Presentation Foundation (WPF), you can customize an existing control's visual structure and behavior with your own reusable template.</span></span> <span data-ttu-id="9fef1-105">템플릿은 애플리케이션, 창 및 페이지에 전역적으로 또는 컨트롤에 직접 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-105">Templates can be applied globally to your application, windows and pages, or directly to controls.</span></span> <span data-ttu-id="9fef1-106">새 컨트롤을 만들어야 하는 대부분의 시나리오는 이 방법 대신 기존 컨트롤의 새 템플릿을 만드는 방법으로 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-106">Most scenarios that require you to create a new control can be covered by instead creating a new template for an existing control.</span></span>

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="9fef1-107">이 문서에서는 <xref:System.Windows.Controls.Button> 컨트롤의 새 <xref:System.Windows.Controls.ControlTemplate>을 만드는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-107">In this article, you'll explore creating a new <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>

## <a name="when-to-create-a-controltemplate"></a><span data-ttu-id="9fef1-108">ControlTemplate을 만들어야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="9fef1-108">When to create a ControlTemplate</span></span>

<span data-ttu-id="9fef1-109">컨트롤에는 <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, <xref:System.Windows.Controls.Control.FontFamily%2A> 등의 여러 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-109">Controls have many properties, such as <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, and <xref:System.Windows.Controls.Control.FontFamily%2A>.</span></span> <span data-ttu-id="9fef1-110">이러한 속성은 컨트롤의 여러 모양을 제어하지만, 이러한 속성을 설정하여 변경할 수 있는 부분은 제한되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-110">These properties control different aspects of the control's appearance, but the changes that you can make by setting these properties are limited.</span></span> <span data-ttu-id="9fef1-111">예를 들어 <xref:System.Windows.Controls.CheckBox>에서 <xref:System.Windows.Controls.Control.Foreground%2A> 속성을 파란색으로 설정하고 <xref:System.Windows.Controls.Control.FontStyle%2A>을 기울임꼴로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-111">For example, you can set the <xref:System.Windows.Controls.Control.Foreground%2A> property to blue and <xref:System.Windows.Controls.Control.FontStyle%2A> to italic on a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="9fef1-112">컨트롤의 모양을 컨트롤의 다른 속성에서 할 수 있는 이상으로 사용자 지정하려면 <xref:System.Windows.Controls.ControlTemplate>을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-112">When you want to customize the control's appearance beyond what setting the other properties on the control can do, you create a <xref:System.Windows.Controls.ControlTemplate>.</span></span>

<span data-ttu-id="9fef1-113">대부분의 사용자 인터페이스에서 단추의 모양은 일반적으로 약간의 텍스트가 있는 사각형으로 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-113">In most user interfaces, a button has the same general appearance: a rectangle with some text.</span></span> <span data-ttu-id="9fef1-114">모서리가 둥근 단추를 만들려면 단추에서 상속하는 새 컨트롤을 만들거나 단추의 기능을 다시 만들면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-114">If you wanted to create a rounded button, you could create a new control that inherits from the button or recreates the functionality of the button.</span></span> <span data-ttu-id="9fef1-115">또한 새로운 사용자 컨트롤은 원형 시각적 개체를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-115">In addition, the new user control would provide the circular visual.</span></span>

<span data-ttu-id="9fef1-116">기존 컨트롤의 시각적 레이아웃을 사용자 지정하면 새 컨트롤을 만들지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-116">You can avoid creating new controls by customizing the visual layout of an existing control.</span></span> <span data-ttu-id="9fef1-117">모서리가 둥근 단추를 사용하여 원하는 시각적 레이아웃으로 <xref:System.Windows.Controls.ControlTemplate>을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-117">With a rounded button, you create a <xref:System.Windows.Controls.ControlTemplate> with the desired visual layout.</span></span>

<span data-ttu-id="9fef1-118">반면, 새 기능, 다른 속성, 새 설정이 포함된 컨트롤이 필요한 경우 새 <xref:System.Windows.Controls.UserControl>을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-118">On the other hand, if you need a control with new functionality, different properties, and new settings, you would create a new <xref:System.Windows.Controls.UserControl>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9fef1-119">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="9fef1-119">Prerequisites</span></span>

<span data-ttu-id="9fef1-120">새 WPF 애플리케이션을 만들고, *MainWindow.xaml*(또는 원하는 다른 창)에서 **\<Window>** 요소에 대한 다음 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-120">Create a new WPF application and in *MainWindow.xaml* (or another window of your choice) set the following properties on the **\<Window>** element:</span></span>

|     |     |
| --- | --- |
| **[!OP.NO-LOC(Title)]**         | `Template Intro Sample` |
| **[!OP.NO-LOC(SizeToContent)]** | `WidthAndHeight` |
| **[!OP.NO-LOC(MinWidth)]**      | `250` |

<span data-ttu-id="9fef1-121">**\<Window>** 요소의 콘텐츠를 다음 XAML로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-121">Set the content of the **\<Window>** element to the following XAML:</span></span>

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

<span data-ttu-id="9fef1-122">최종적으로 *MainWindow.xaml* 파일의 모양은 다음과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-122">In the end, the *MainWindow.xaml* file should look similar to the following:</span></span>

[!code-xaml[InitialWhole](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#InitialWhole)]

<span data-ttu-id="9fef1-123">애플리케이션을 실행하면 다음과 비슷한 모양입니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-123">If you run the application, it looks like the following:</span></span>

![스타일이 지정되지 않은 두 개의 단추가 있는 WPF 창](media/create-apply-template/unstyled-button.png)

## <a name="create-a-controltemplate"></a><span data-ttu-id="9fef1-125">ControlTemplate 만들기</span><span class="sxs-lookup"><span data-stu-id="9fef1-125">Create a ControlTemplate</span></span>

<span data-ttu-id="9fef1-126"><xref:System.Windows.Controls.ControlTemplate>을 선언하는 가장 일반적인 방법은 XAML 파일에 있는 `Resources` 섹션의 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-126">The most common way to declare a <xref:System.Windows.Controls.ControlTemplate> is as a resource in the `Resources` section in a XAML file.</span></span> <span data-ttu-id="9fef1-127">템플릿은 리소스이므로 모든 리소스에 적용되는 동일한 범위 지정 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-127">Because templates are resources, they obey the same scoping rules that apply to all resources.</span></span> <span data-ttu-id="9fef1-128">간단히 말해서, 템플릿을 선언하는 위치는 템플릿을 적용할 수 있는 위치에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-128">Put simply, where you declare a template affects where the template can be applied.</span></span> <span data-ttu-id="9fef1-129">예를 들어 애플리케이션 정의 XAML 파일의 루트 요소에서 컨트롤을 선언하면 애플리케이션의 모든 위치에서 템플릿을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-129">For example, if you declare the template in the root element of your application definition XAML file, the template can be used anywhere in your application.</span></span> <span data-ttu-id="9fef1-130">창에서 템플릿을 정의하면 해당 창의 컨트롤만 템플릿을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-130">If you define the template in a window, only the controls in that window can use the template.</span></span>

<span data-ttu-id="9fef1-131">먼저 `Window.Resources` 요소를 *MainWindow.xaml* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-131">To start with, add a `Window.Resources` element to your *MainWindow.xaml* file:</span></span>

[!code-xaml[WindowResStart](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window2.xaml#WindowResStart)]

<span data-ttu-id="9fef1-132">다음 속성 세트를 사용하여 새 **\<ControlTemplate>** 을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-132">Create a new **\<ControlTemplate>** with the following properties set:</span></span>

|     |     |
| --- | --- |
| <span data-ttu-id="9fef1-133">**x:Key**</span><span class="sxs-lookup"><span data-stu-id="9fef1-133">**x:Key**</span></span>         | `roundbutton` |
| **TargetType**    | `Button` |

<span data-ttu-id="9fef1-134">이 컨트롤 템플릿은 간단하게 다음 중 하나가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-134">This control template will be simple:</span></span>

- <span data-ttu-id="9fef1-135">컨트롤의 루트 요소인 <xref:System.Windows.Controls.Grid></span><span class="sxs-lookup"><span data-stu-id="9fef1-135">a root element for the control, a <xref:System.Windows.Controls.Grid></span></span>
- <span data-ttu-id="9fef1-136">단추의 둥근 모서리 모양을 그리는 <xref:System.Windows.Shapes.Ellipse></span><span class="sxs-lookup"><span data-stu-id="9fef1-136">an <xref:System.Windows.Shapes.Ellipse> to draw the rounded appearance of the button</span></span>
- <span data-ttu-id="9fef1-137">사용자 지정 단추 콘텐츠를 표시하는 <xref:System.Windows.Controls.ContentPresenter></span><span class="sxs-lookup"><span data-stu-id="9fef1-137">a <xref:System.Windows.Controls.ContentPresenter> to display the user-specified button content</span></span>

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#ControlTemplate)]

### <a name="templatebinding"></a><span data-ttu-id="9fef1-138">TemplateBinding</span><span class="sxs-lookup"><span data-stu-id="9fef1-138">TemplateBinding</span></span>

<span data-ttu-id="9fef1-139">새 <xref:System.Windows.Controls.ControlTemplate>을 만들 때에도 여전히 public 속성을 사용하여 컨트롤의 모양을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-139">When you create a new <xref:System.Windows.Controls.ControlTemplate>, you still might want to use the public properties to change the control's appearance.</span></span> <span data-ttu-id="9fef1-140">[TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) 태그 확장은 <xref:System.Windows.Controls.ControlTemplate>에 있는 요소의 속성을 컨트롤이 정의하는 public 속성에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-140">The [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) markup extension binds a property of an element that is in the <xref:System.Windows.Controls.ControlTemplate> to a public property that is defined by the control.</span></span> <span data-ttu-id="9fef1-141">[TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md)을 사용하면 컨트롤의 속성이 템플릿의 매개 변수로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-141">When you use a [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md), you enable properties on the control to act as parameters to the template.</span></span> <span data-ttu-id="9fef1-142">즉, 컨트롤의 속성을 설정하면 해당 값은 [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md)이 있는 요소로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-142">That is, when a property on a control is set, that value is passed on to the element that has the [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) on it.</span></span>

### <a name="ellipse"></a><span data-ttu-id="9fef1-143">타원</span><span class="sxs-lookup"><span data-stu-id="9fef1-143">Ellipse</span></span>

<span data-ttu-id="9fef1-144">**\<Ellipse>** 요소의 **:::no-loc text="Fill":::** 및 **:::no-loc text="Stroke":::** 속성은 컨트롤의 <xref:System.Windows.Controls.Control.Foreground> 및 <xref:System.Windows.Controls.Control.Background> 속성에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-144">Notice that the **:::no-loc text="Fill":::** and **:::no-loc text="Stroke":::** properties of the **\<Ellipse>** element are bound to the control's <xref:System.Windows.Controls.Control.Foreground> and <xref:System.Windows.Controls.Control.Background> properties.</span></span>

### <a name="contentpresenter"></a><span data-ttu-id="9fef1-145">ContentPresenter</span><span class="sxs-lookup"><span data-stu-id="9fef1-145">ContentPresenter</span></span>

<span data-ttu-id="9fef1-146">[\<ContentPresenter>](xref:System.Windows.Controls.ContentPresenter) 요소도 템플릿에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-146">A [\<ContentPresenter>](xref:System.Windows.Controls.ContentPresenter) element is also added to the template.</span></span> <span data-ttu-id="9fef1-147">이 템플릿은 단추용으로 디자인되었으므로 단추가 <xref:System.Windows.Controls.ContentControl>에서 상속한다는 점을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-147">Because this template is designed for a button, take into consideration that the button inherits from <xref:System.Windows.Controls.ContentControl>.</span></span> <span data-ttu-id="9fef1-148">단추는 요소의 콘텐츠를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-148">The button presents the content of the element.</span></span> <span data-ttu-id="9fef1-149">단추 내에 일반 텍스트, 다른 컨트롤 등의 모든 것을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-149">You can set anything inside of the button, such as plain text or even another control.</span></span> <span data-ttu-id="9fef1-150">다음 두 단추 모두 유효한 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-150">Both of the following are valid buttons:</span></span>

```xaml
<Button>My Text</Button>

<!-- and -->

<Button>
    <CheckBox>Checkbox in a button</CheckBox>
</Button>
```

<span data-ttu-id="9fef1-151">위의 두 예제에서 텍스트와 확인란은 [Button.Content](xref:System.Windows.Controls.ContentControl.Content) 속성으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-151">In both of the previous examples, the text and the checkbox are set as the [Button.Content](xref:System.Windows.Controls.ContentControl.Content) property.</span></span> <span data-ttu-id="9fef1-152">콘텐츠로 설정된 것은 그 무엇이든 **\<ContentPresenter>** 를 통해 표시할 수 있으며, 이것이 바로 템플릿이 하는 일입니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-152">Whatever is set as the content can be presented through a **\<ContentPresenter>**, which is what the template does.</span></span>

<span data-ttu-id="9fef1-153"><xref:System.Windows.Controls.ControlTemplate>이 `Button` 같은 <xref:System.Windows.Controls.ContentControl> 형식에 적용되면 요소 트리에서 <xref:System.Windows.Controls.ContentPresenter>가 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-153">If the <xref:System.Windows.Controls.ControlTemplate> is applied to a <xref:System.Windows.Controls.ContentControl> type, such as a `Button`, a <xref:System.Windows.Controls.ContentPresenter> is searched for in the element tree.</span></span> <span data-ttu-id="9fef1-154">`ContentPresenter`가 발견되면 템플릿에서 자동으로 컨트롤의 <xref:System.Windows.Controls.ContentControl.Content> 속성을 `ContentPresenter`에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-154">If the `ContentPresenter` is found, the template automatically binds the control's <xref:System.Windows.Controls.ContentControl.Content> property to the `ContentPresenter`.</span></span>

## <a name="use-the-template"></a><span data-ttu-id="9fef1-155">템플릿 사용</span><span class="sxs-lookup"><span data-stu-id="9fef1-155">Use the template</span></span>

<span data-ttu-id="9fef1-156">이 문서의 시작 부분에서 선언한 단추를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-156">Find the buttons that were declared at the start of this article.</span></span>

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

<span data-ttu-id="9fef1-157">두 번째 단추의 <xref:System.Windows.Controls.Control.Template> 속성을 `roundbutton` 리소스로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-157">Set the second button's <xref:System.Windows.Controls.Control.Template> property to the `roundbutton` resource:</span></span>

[!code-xaml[StyledButton](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButton)]

<span data-ttu-id="9fef1-158">프로젝트를 실행하고 결과를 살펴보면 단추의 배경이 둥근 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-158">If you run the project and look at the result, you'll see that the button has a rounded background.</span></span>

![템플릿 타원 단추가 하나 있는 WPF 창](media/create-apply-template/styled-button.png)

<span data-ttu-id="9fef1-160">단추가 원이 아니라 타원인 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-160">You may have noticed that the button isn't a circle but is skewed.</span></span> <span data-ttu-id="9fef1-161">**\<Ellipse>** 요소는 그 작동 방식 때문에 항상 사용 가능한 공간을 채우도록 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-161">Because of the way the **\<Ellipse>** element works, it always expands to fill the available space.</span></span> <span data-ttu-id="9fef1-162">단추의 **:::no-loc text="width":::** 및 **:::no-loc text="height":::** 속성을 동일한 값으로 변경하여 원을 균일하게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-162">Make the circle uniform by changing the button's  **:::no-loc text="width":::** and **:::no-loc text="height":::** properties to the same value:</span></span>

[!code-xaml[StyledButtonSize](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButtonSize)]

![템플릿 원형 단추가 하나 있는 WPF 창](media/create-apply-template/styled-uniform-button.png)

## <a name="add-a-trigger"></a><span data-ttu-id="9fef1-164">트리거 추가</span><span class="sxs-lookup"><span data-stu-id="9fef1-164">Add a Trigger</span></span>

<span data-ttu-id="9fef1-165">템플릿이 적용된 단추가 다르게 보이더라도 다른 단추와 동일하게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-165">Even though a button with a template applied looks different, it behaves the same as any other button.</span></span> <span data-ttu-id="9fef1-166">단추를 누르면 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-166">If you press the button, the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event fires.</span></span> <span data-ttu-id="9fef1-167">그러나 마우스를 단추 위로 이동하면 단추의 시각적 개체가 변하지 않는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-167">However, you may have noticed that when you move your mouse over the button, the button's visuals don't change.</span></span> <span data-ttu-id="9fef1-168">이러한 시각적 개체 상호 작용은 모두 템플릿에서 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-168">These visual interactions are all defined by the template.</span></span>

<span data-ttu-id="9fef1-169">WPF에서 제공하는 동적 이벤트 및 속성 시스템을 사용하면 값의 특정 속성을 살펴본 후 적시에 템플릿 스타일을 다시 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-169">With the dynamic event and property systems that WPF provides, you can watch a specific property for a value and then restyle the template when appropriate.</span></span> <span data-ttu-id="9fef1-170">이 예제에서는 단추의 <xref:System.Windows.UIElement.IsMouseOver> 속성을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-170">In this example, you'll watch the button's <xref:System.Windows.UIElement.IsMouseOver> property.</span></span> <span data-ttu-id="9fef1-171">마우스가 컨트롤 위에 있을 때 **\<Ellipse>** 스타일을 새로운 색으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-171">When the mouse is over the control, style the **\<Ellipse>** with a new color.</span></span> <span data-ttu-id="9fef1-172">이러한 유형의 트리거를 *PropertyTrigger*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-172">This type of trigger is known as a *PropertyTrigger*.</span></span>

<span data-ttu-id="9fef1-173">이 방법이 작동하려면 참조할 수 있는 **\<Ellipse>** 에 이름을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-173">For this to work, you'll need to add a name to the **\<Ellipse>** that you can reference.</span></span> <span data-ttu-id="9fef1-174">**backgroundElement**라는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-174">Give it the name of **backgroundElement**.</span></span>

[!code-xaml[EllipseName](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml#EllipseName)]

<span data-ttu-id="9fef1-175">다음으로, [ControlTemplate.Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers) 컬렉션에 새 <xref:System.Windows.Trigger>를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-175">Next, add a new <xref:System.Windows.Trigger> to the [ControlTemplate.Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers) collection.</span></span> <span data-ttu-id="9fef1-176">이 트리거는 `IsMouseOver` 이벤트의 `true` 값을 감시합니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-176">The trigger will watch the `IsMouseOver` event for the value `true`.</span></span>

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml?name=ControlTemplate&highlight=6-10)]

<span data-ttu-id="9fef1-177">다음으로, **\<Ellipse>** 의 **Fill** 속성을 새로운 색으로 변경하는 **\<Trigger>** 에 **\<Setter>** 를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-177">Next, add a **\<Setter>** to the **\<Trigger>** that changes the **Fill** property of the **\<Ellipse>** to a new color.</span></span>

[!code-xaml[MouseOver](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#MouseOver)]

<span data-ttu-id="9fef1-178">프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-178">Run the project.</span></span> <span data-ttu-id="9fef1-179">마우스를 단추 위로 이동하면 **\<Ellipse>** 의 색이 변합니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-179">Notice that when you move the mouse over the button, the color of the **\<Ellipse>** changes.</span></span>

![마우스를 WPF 단추 위로 이동하면 채우기 색이 변함](media/create-apply-template/mouse-move-over-button.gif)

## <a name="use-a-visualstate"></a><span data-ttu-id="9fef1-181">VisualState 사용</span><span class="sxs-lookup"><span data-stu-id="9fef1-181">Use a VisualState</span></span>

<span data-ttu-id="9fef1-182">시각적 상태는 컨트롤을 통해 정의하고 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-182">Visual states are defined and triggered by a control.</span></span> <span data-ttu-id="9fef1-183">예를 들어 마우스를 컨트롤 위로 이동하면 `CommonStates.MouseOver` 상태가 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-183">For example, when the mouse is moved on top of the control, the `CommonStates.MouseOver` state is triggered.</span></span> <span data-ttu-id="9fef1-184">컨트롤의 현재 상태에 따라 속성 변경에 애니메이션 효과를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-184">You can animate property changes based on the current state of the control.</span></span> <span data-ttu-id="9fef1-185">이전 섹션에서는 **\<PropertyTrigger>** 를 사용하여 `IsMouseOver` 속성이 `true`일 때 단추의 전경을 `AliceBlue`로 변경하도록 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-185">In the previous section, a **\<PropertyTrigger>** was used to change the foreground of the button to `AliceBlue` when the `IsMouseOver` property was `true`.</span></span> <span data-ttu-id="9fef1-186">여기서는 그 대신 색의 변화에 애니메이션 효과를 적용하는 시각적 상태를 만들어 부드럽게 전환하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-186">Instead, create a visual state that animates the change of this color, providing a smooth transition.</span></span> <span data-ttu-id="9fef1-187">*VisualStates*에 대한 자세한 내용은 [WPF의 스타일 및 템플릿](../fundamentals/styles-templates-overview.md#visual-states)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9fef1-187">For more information about *VisualStates*, see [Styles and templates in WPF](../fundamentals/styles-templates-overview.md#visual-states).</span></span>

<span data-ttu-id="9fef1-188">**\<PropertyTrigger>** 를 애니메이션 시각적 상태로 변환하려면 템플릿에서 **\<ControlTemplate.Triggers>** 요소를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-188">To convert the **\<PropertyTrigger>** to an animated visual state, First, remove the **\<ControlTemplate.Triggers>** element from your template.</span></span>

[!code-xaml[CleanTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#CleanTemplate)]

<span data-ttu-id="9fef1-189">다음으로, 컨트롤 템플릿의 **\<Grid>** 루트에서 `CommonStates`에 대한 **\<VisualStateGroup>** 을 사용하여 **\<VisualStateManager.VisualStateGroups>** 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-189">Next, in the **\<Grid>** root of the control template, add the **\<VisualStateManager.VisualStateGroups>** element with a **\<VisualStateGroup>** for `CommonStates`.</span></span> <span data-ttu-id="9fef1-190">두 가지 상태 `Normal` 및 `MouseOver`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-190">Define two states, `Normal` and `MouseOver`.</span></span>

[!code-xaml[VisualState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#VisualState)]

<span data-ttu-id="9fef1-191">**\<VisualState>** 에 정의된 애니메이션은 이 상태가 트리거될 때 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-191">Any animations defined in a **\<VisualState>** are applied when that state is triggered.</span></span> <span data-ttu-id="9fef1-192">각 상태에 대한 애니메이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-192">Create animations for each state.</span></span> <span data-ttu-id="9fef1-193">애니메이션은 **\<Storyboard>** 요소 내에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-193">Animations are put inside of a **\<Storyboard>** element.</span></span> <span data-ttu-id="9fef1-194">스토리보드에 대한 자세한 내용은 [스토리보드 개요](../../framework/wpf/graphics-multimedia/storyboards-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9fef1-194">For more information about storyboards, see [Storyboards Overview](../../framework/wpf/graphics-multimedia/storyboards-overview.md).</span></span>

- <span data-ttu-id="9fef1-195">보통</span><span class="sxs-lookup"><span data-stu-id="9fef1-195">Normal</span></span>

  <span data-ttu-id="9fef1-196">이 상태는 타원 채우기에 애니메이션 효과를 적용하여 컨트롤의 `Background` 색으로 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-196">This state animates the ellipse fill, restoring it to the control's `Background` color.</span></span>

  [!code-xaml[NormalState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#NormalState)]

- <span data-ttu-id="9fef1-197">MouseOver</span><span class="sxs-lookup"><span data-stu-id="9fef1-197">MouseOver</span></span>

  <span data-ttu-id="9fef1-198">이 상태는 타원 `Background` 색에 애니메이션 효과를 적용하여 새로운 `Yellow` 색으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-198">This state animates the ellipse `Background` color to a new color: `Yellow`.</span></span>

  [!code-xaml[MouseOverState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#MouseOverState)]

<span data-ttu-id="9fef1-199">**\<ControlTemplate>** 은 이제 다음과 비슷하게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-199">The **\<ControlTemplate>** should now look like the following.</span></span>

[!code-xaml[FinalTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window7.xaml#FinalTemplate)]

<span data-ttu-id="9fef1-200">프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-200">Run the project.</span></span> <span data-ttu-id="9fef1-201">마우스를 단추 위로 이동하면 **\<Ellipse>** 의 색에 애니메이션 효과가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fef1-201">Notice that when you move the mouse over the button, the color of the **\<Ellipse>** animates.</span></span>

![마우스를 WPF 단추 위로 이동하면 채우기 색이 변함](media/create-apply-template/mouse-move-over-button-visualstate.gif)

## <a name="next-steps"></a><span data-ttu-id="9fef1-203">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9fef1-203">Next steps</span></span>

- [<span data-ttu-id="9fef1-204">WPF에서 컨트롤의 스타일 만들기</span><span class="sxs-lookup"><span data-stu-id="9fef1-204">Create a style for a control in WPF</span></span>](../fundamentals/styles-templates-create-apply-style.md)
- [<span data-ttu-id="9fef1-205">WPF의 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="9fef1-205">Styles and templates in WPF</span></span>](../fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="9fef1-206">XAML 리소스 개요</span><span class="sxs-lookup"><span data-stu-id="9fef1-206">Overview of XAML Resources</span></span>](../fundamentals/xaml-resources-define.md)

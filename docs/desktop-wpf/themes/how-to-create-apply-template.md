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
# <a name="create-a-template-for-a-control"></a>컨트롤의 템플릿 만들기

WPF(Windows Presentation Foundation)를 사용하면 다시 사용할 수 있는 템플릿을 사용하여 기존 컨트롤의 시각적 구조 및 동작을 사용자 지정할 수 있습니다. 템플릿은 애플리케이션, 창 및 페이지에 전역적으로 또는 컨트롤에 직접 적용할 수 있습니다. 새 컨트롤을 만들어야 하는 대부분의 시나리오는 이 방법 대신 기존 컨트롤의 새 템플릿을 만드는 방법으로 해결할 수 있습니다.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

이 문서에서는 <xref:System.Windows.Controls.Button> 컨트롤의 새 <xref:System.Windows.Controls.ControlTemplate>을 만드는 방법을 살펴봅니다.

## <a name="when-to-create-a-controltemplate"></a>ControlTemplate을 만들어야 하는 경우

컨트롤에는 <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, <xref:System.Windows.Controls.Control.FontFamily%2A> 등의 여러 속성이 있습니다. 이러한 속성은 컨트롤의 여러 모양을 제어하지만, 이러한 속성을 설정하여 변경할 수 있는 부분은 제한되어 있습니다. 예를 들어 <xref:System.Windows.Controls.CheckBox>에서 <xref:System.Windows.Controls.Control.Foreground%2A> 속성을 파란색으로 설정하고 <xref:System.Windows.Controls.Control.FontStyle%2A>을 기울임꼴로 설정할 수 있습니다. 컨트롤의 모양을 컨트롤의 다른 속성에서 할 수 있는 이상으로 사용자 지정하려면 <xref:System.Windows.Controls.ControlTemplate>을 만듭니다.

대부분의 사용자 인터페이스에서 단추의 모양은 일반적으로 약간의 텍스트가 있는 사각형으로 동일합니다. 모서리가 둥근 단추를 만들려면 단추에서 상속하는 새 컨트롤을 만들거나 단추의 기능을 다시 만들면 됩니다. 또한 새로운 사용자 컨트롤은 원형 시각적 개체를 제공합니다.

기존 컨트롤의 시각적 레이아웃을 사용자 지정하면 새 컨트롤을 만들지 않아도 됩니다. 모서리가 둥근 단추를 사용하여 원하는 시각적 레이아웃으로 <xref:System.Windows.Controls.ControlTemplate>을 만듭니다.

반면, 새 기능, 다른 속성, 새 설정이 포함된 컨트롤이 필요한 경우 새 <xref:System.Windows.Controls.UserControl>을 만듭니다.

## <a name="prerequisites"></a>사전 요구 사항

새 WPF 애플리케이션을 만들고, *MainWindow.xaml*(또는 원하는 다른 창)에서 **\<Window>** 요소에 대한 다음 속성을 설정합니다.

|     |     |
| --- | --- |
| **[!OP.NO-LOC(Title)]**         | `Template Intro Sample` |
| **[!OP.NO-LOC(SizeToContent)]** | `WidthAndHeight` |
| **[!OP.NO-LOC(MinWidth)]**      | `250` |

**\<Window>** 요소의 콘텐츠를 다음 XAML로 설정합니다.

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

최종적으로 *MainWindow.xaml* 파일의 모양은 다음과 비슷합니다.

[!code-xaml[InitialWhole](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#InitialWhole)]

애플리케이션을 실행하면 다음과 비슷한 모양입니다.

![스타일이 지정되지 않은 두 개의 단추가 있는 WPF 창](media/create-apply-template/unstyled-button.png)

## <a name="create-a-controltemplate"></a>ControlTemplate 만들기

<xref:System.Windows.Controls.ControlTemplate>을 선언하는 가장 일반적인 방법은 XAML 파일에 있는 `Resources` 섹션의 리소스입니다. 템플릿은 리소스이므로 모든 리소스에 적용되는 동일한 범위 지정 규칙을 따릅니다. 간단히 말해서, 템플릿을 선언하는 위치는 템플릿을 적용할 수 있는 위치에 영향을 줍니다. 예를 들어 애플리케이션 정의 XAML 파일의 루트 요소에서 컨트롤을 선언하면 애플리케이션의 모든 위치에서 템플릿을 사용할 수 있습니다. 창에서 템플릿을 정의하면 해당 창의 컨트롤만 템플릿을 사용할 수 있습니다.

먼저 `Window.Resources` 요소를 *MainWindow.xaml* 파일에 추가합니다.

[!code-xaml[WindowResStart](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window2.xaml#WindowResStart)]

다음 속성 세트를 사용하여 새 **\<ControlTemplate>** 을 만듭니다.

|     |     |
| --- | --- |
| **x:Key**         | `roundbutton` |
| **TargetType**    | `Button` |

이 컨트롤 템플릿은 간단하게 다음 중 하나가 됩니다.

- 컨트롤의 루트 요소인 <xref:System.Windows.Controls.Grid>
- 단추의 둥근 모서리 모양을 그리는 <xref:System.Windows.Shapes.Ellipse>
- 사용자 지정 단추 콘텐츠를 표시하는 <xref:System.Windows.Controls.ContentPresenter>

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#ControlTemplate)]

### <a name="templatebinding"></a>TemplateBinding

새 <xref:System.Windows.Controls.ControlTemplate>을 만들 때에도 여전히 public 속성을 사용하여 컨트롤의 모양을 변경할 수 있습니다. [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) 태그 확장은 <xref:System.Windows.Controls.ControlTemplate>에 있는 요소의 속성을 컨트롤이 정의하는 public 속성에 바인딩합니다. [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md)을 사용하면 컨트롤의 속성이 템플릿의 매개 변수로 작동합니다. 즉, 컨트롤의 속성을 설정하면 해당 값은 [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md)이 있는 요소로 전달됩니다.

### <a name="ellipse"></a>타원

**\<Ellipse>** 요소의 **:::no-loc text="Fill":::** 및 **:::no-loc text="Stroke":::** 속성은 컨트롤의 <xref:System.Windows.Controls.Control.Foreground> 및 <xref:System.Windows.Controls.Control.Background> 속성에 바인딩됩니다.

### <a name="contentpresenter"></a>ContentPresenter

[\<ContentPresenter>](xref:System.Windows.Controls.ContentPresenter) 요소도 템플릿에 추가됩니다. 이 템플릿은 단추용으로 디자인되었으므로 단추가 <xref:System.Windows.Controls.ContentControl>에서 상속한다는 점을 고려해야 합니다. 단추는 요소의 콘텐츠를 표시합니다. 단추 내에 일반 텍스트, 다른 컨트롤 등의 모든 것을 설정할 수 있습니다. 다음 두 단추 모두 유효한 단추입니다.

```xaml
<Button>My Text</Button>

<!-- and -->

<Button>
    <CheckBox>Checkbox in a button</CheckBox>
</Button>
```

위의 두 예제에서 텍스트와 확인란은 [Button.Content](xref:System.Windows.Controls.ContentControl.Content) 속성으로 설정됩니다. 콘텐츠로 설정된 것은 그 무엇이든 **\<ContentPresenter>** 를 통해 표시할 수 있으며, 이것이 바로 템플릿이 하는 일입니다.

<xref:System.Windows.Controls.ControlTemplate>이 `Button` 같은 <xref:System.Windows.Controls.ContentControl> 형식에 적용되면 요소 트리에서 <xref:System.Windows.Controls.ContentPresenter>가 검색됩니다. `ContentPresenter`가 발견되면 템플릿에서 자동으로 컨트롤의 <xref:System.Windows.Controls.ContentControl.Content> 속성을 `ContentPresenter`에 바인딩합니다.

## <a name="use-the-template"></a>템플릿 사용

이 문서의 시작 부분에서 선언한 단추를 찾습니다.

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

두 번째 단추의 <xref:System.Windows.Controls.Control.Template> 속성을 `roundbutton` 리소스로 설정합니다.

[!code-xaml[StyledButton](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButton)]

프로젝트를 실행하고 결과를 살펴보면 단추의 배경이 둥근 것을 볼 수 있습니다.

![템플릿 타원 단추가 하나 있는 WPF 창](media/create-apply-template/styled-button.png)

단추가 원이 아니라 타원인 것을 볼 수 있습니다. **\<Ellipse>** 요소는 그 작동 방식 때문에 항상 사용 가능한 공간을 채우도록 확장됩니다. 단추의 **:::no-loc text="width":::** 및 **:::no-loc text="height":::** 속성을 동일한 값으로 변경하여 원을 균일하게 만듭니다.

[!code-xaml[StyledButtonSize](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButtonSize)]

![템플릿 원형 단추가 하나 있는 WPF 창](media/create-apply-template/styled-uniform-button.png)

## <a name="add-a-trigger"></a>트리거 추가

템플릿이 적용된 단추가 다르게 보이더라도 다른 단추와 동일하게 작동합니다. 단추를 누르면 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트가 발생합니다. 그러나 마우스를 단추 위로 이동하면 단추의 시각적 개체가 변하지 않는 것을 볼 수 있습니다. 이러한 시각적 개체 상호 작용은 모두 템플릿에서 정의합니다.

WPF에서 제공하는 동적 이벤트 및 속성 시스템을 사용하면 값의 특정 속성을 살펴본 후 적시에 템플릿 스타일을 다시 지정할 수 있습니다. 이 예제에서는 단추의 <xref:System.Windows.UIElement.IsMouseOver> 속성을 살펴보겠습니다. 마우스가 컨트롤 위에 있을 때 **\<Ellipse>** 스타일을 새로운 색으로 지정합니다. 이러한 유형의 트리거를 *PropertyTrigger*라고 합니다.

이 방법이 작동하려면 참조할 수 있는 **\<Ellipse>** 에 이름을 추가해야 합니다. **backgroundElement**라는 이름을 지정합니다.

[!code-xaml[EllipseName](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml#EllipseName)]

다음으로, [ControlTemplate.Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers) 컬렉션에 새 <xref:System.Windows.Trigger>를 추가합니다. 이 트리거는 `IsMouseOver` 이벤트의 `true` 값을 감시합니다.

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml?name=ControlTemplate&highlight=6-10)]

다음으로, **\<Ellipse>** 의 **Fill** 속성을 새로운 색으로 변경하는 **\<Trigger>** 에 **\<Setter>** 를 추가합니다.

[!code-xaml[MouseOver](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#MouseOver)]

프로젝트를 실행합니다. 마우스를 단추 위로 이동하면 **\<Ellipse>** 의 색이 변합니다.

![마우스를 WPF 단추 위로 이동하면 채우기 색이 변함](media/create-apply-template/mouse-move-over-button.gif)

## <a name="use-a-visualstate"></a>VisualState 사용

시각적 상태는 컨트롤을 통해 정의하고 트리거됩니다. 예를 들어 마우스를 컨트롤 위로 이동하면 `CommonStates.MouseOver` 상태가 트리거됩니다. 컨트롤의 현재 상태에 따라 속성 변경에 애니메이션 효과를 적용할 수 있습니다. 이전 섹션에서는 **\<PropertyTrigger>** 를 사용하여 `IsMouseOver` 속성이 `true`일 때 단추의 전경을 `AliceBlue`로 변경하도록 했습니다. 여기서는 그 대신 색의 변화에 애니메이션 효과를 적용하는 시각적 상태를 만들어 부드럽게 전환하겠습니다. *VisualStates*에 대한 자세한 내용은 [WPF의 스타일 및 템플릿](../fundamentals/styles-templates-overview.md#visual-states)을 참조하세요.

**\<PropertyTrigger>** 를 애니메이션 시각적 상태로 변환하려면 템플릿에서 **\<ControlTemplate.Triggers>** 요소를 제거합니다.

[!code-xaml[CleanTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#CleanTemplate)]

다음으로, 컨트롤 템플릿의 **\<Grid>** 루트에서 `CommonStates`에 대한 **\<VisualStateGroup>** 을 사용하여 **\<VisualStateManager.VisualStateGroups>** 요소를 추가합니다. 두 가지 상태 `Normal` 및 `MouseOver`를 정의합니다.

[!code-xaml[VisualState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#VisualState)]

**\<VisualState>** 에 정의된 애니메이션은 이 상태가 트리거될 때 적용됩니다. 각 상태에 대한 애니메이션을 만듭니다. 애니메이션은 **\<Storyboard>** 요소 내에 배치됩니다. 스토리보드에 대한 자세한 내용은 [스토리보드 개요](../../framework/wpf/graphics-multimedia/storyboards-overview.md)를 참조하세요.

- 보통

  이 상태는 타원 채우기에 애니메이션 효과를 적용하여 컨트롤의 `Background` 색으로 복원합니다.

  [!code-xaml[NormalState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#NormalState)]

- MouseOver

  이 상태는 타원 `Background` 색에 애니메이션 효과를 적용하여 새로운 `Yellow` 색으로 변경합니다.

  [!code-xaml[MouseOverState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#MouseOverState)]

**\<ControlTemplate>** 은 이제 다음과 비슷하게 표시됩니다.

[!code-xaml[FinalTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window7.xaml#FinalTemplate)]

프로젝트를 실행합니다. 마우스를 단추 위로 이동하면 **\<Ellipse>** 의 색에 애니메이션 효과가 적용됩니다.

![마우스를 WPF 단추 위로 이동하면 채우기 색이 변함](media/create-apply-template/mouse-move-over-button-visualstate.gif)

## <a name="next-steps"></a>다음 단계

- [WPF에서 컨트롤의 스타일 만들기](../fundamentals/styles-templates-create-apply-style.md)
- [WPF의 스타일 및 템플릿](../fundamentals/styles-templates-overview.md)
- [XAML 리소스 개요](../fundamentals/xaml-resources-define.md)

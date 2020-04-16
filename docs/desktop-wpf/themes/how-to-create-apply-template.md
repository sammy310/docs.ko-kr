---
title: WPF - .NET 데스크톱에서 템플릿 만들기
description: Windows 프레젠테이션 재단 및 .NET Core에서 컨트롤 템플릿을 만들고 참조하는 방법을 알아봅니다.
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
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "81432541"
---
# <a name="create-a-template-for-a-control"></a>컨트롤용 템플릿 만들기

WPF(Windows 프레젠테이션 파운데이션)를 사용하면 재사용 가능한 템플릿을 통해 기존 컨트롤의 시각적 구조와 동작을 사용자 지정할 수 있습니다. 템플릿은 응용 프로그램, 창 및 페이지에 전역적으로 적용하거나 컨트롤에 직접 적용할 수 있습니다. 새 컨트롤을 만들어야 하는 대부분의 시나리오는 기존 컨트롤에 대한 새 템플릿을 만드는 대신 적용될 수 있습니다.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

이 문서에서는 컨트롤에 대 한 <xref:System.Windows.Controls.ControlTemplate> 새 <xref:System.Windows.Controls.Button> 만들기를 살펴보겠습니다.

## <a name="when-to-create-a-controltemplate"></a>컨트롤 템플릿을 만드는 시기

컨트롤에는 및 및 <xref:System.Windows.Controls.Border.Background%2A>와 <xref:System.Windows.Controls.Control.Foreground%2A>같은 <xref:System.Windows.Controls.Control.FontFamily%2A>많은 속성이 있습니다. 이러한 속성은 컨트롤 의 모양의 다른 측면을 제어하지만 이러한 속성을 설정하여 수행할 수 있는 변경 사항은 제한됩니다. 예를 들어 <xref:System.Windows.Controls.Control.Foreground%2A> 속성을 파란색으로 <xref:System.Windows.Controls.Control.FontStyle%2A> 설정하고 <xref:System.Windows.Controls.CheckBox>에 기울임꼴로 설정할 수 있습니다. 컨트롤의 다른 속성을 설정하는 것 이상으로 컨트롤의 모양을 사용자 지정하려는 경우 <xref:System.Windows.Controls.ControlTemplate>를 만듭니다.

대부분의 사용자 인터페이스에서 단추는 일부 텍스트가 있는 사각형과 같은 일반적인 모양을 가립니다. 둥근 단추를 만들려면 단추에서 상속되거나 단추의 기능을 다시 만드는 새 컨트롤을 만들 수 있습니다. 또한 새 사용자 컨트롤은 원형 시각적 개체를 제공합니다.

기존 컨트롤의 시각적 레이아웃을 사용자 지정하여 새 컨트롤을 만들지 않도록 할 수 있습니다. 둥근 단추를 사용하여 원하는 <xref:System.Windows.Controls.ControlTemplate> 시각적 레이아웃으로 를 만듭니다.

반면에 새 기능, 다른 속성 및 새 설정이 있는 컨트롤이 필요한 <xref:System.Windows.Controls.UserControl>경우 새 을 만듭니다.

## <a name="prerequisites"></a>사전 요구 사항

새 WPF 응용 프로그램을 만들고 *MainWindow.xaml(또는* 선택한 다른 창)에서 ** \<창>** 요소에서 다음 속성을 설정합니다.

|     |     |
| --- | --- |
| **[!OP.NO-LOC(Title)]**         | `Template Intro Sample` |
| **[!OP.NO-LOC(SizeToContent)]** | `WidthAndHeight` |
| **[!OP.NO-LOC(MinWidth)]**      | `250` |

창>요소의 내용을 다음 XAML로 설정합니다. ** \<**

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

결국 *MainWindow.xaml* 파일은 다음과 유사해야 합니다.

[!code-xaml[InitialWhole](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#InitialWhole)]

응용 프로그램을 실행하면 다음과 같습니다.

![스타일이 없는 두 개의 버튼이 있는 WPF 창](media/create-apply-template/unstyled-button.png)

## <a name="create-a-controltemplate"></a>ControlTemplate 만들기

a를 <xref:System.Windows.Controls.ControlTemplate> 선언하는 가장 일반적인 방법은 XAML 파일의 `Resources` 섹션에서 리소스로 사용됩니다. 템플릿은 리소스이므로 모든 리소스에 적용되는 동일한 범위 지정 규칙을 준수합니다. 간단히 말해 템플릿을 선언하는 위치가 템플릿을 적용할 수 있는 위치에 영향을 줍니다. 예를 들어 응용 프로그램 정의 XAML 파일의 루트 요소에 템플릿을 선언하는 경우 응용 프로그램의 어느 위치에서나 템플릿을 사용할 수 있습니다. 창에서 템플릿을 정의하는 경우 해당 창의 컨트롤만 템플릿을 사용할 수 있습니다.

먼저 `Window.Resources` *MainWindow.xaml* 파일에 요소를 추가합니다.

[!code-xaml[WindowResStart](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window2.xaml#WindowResStart)]

다음 속성 집합을 사용하여 새 ** \<ControlTemplate>** 만듭니다.

|     |     |
| --- | --- |
| **X:key**         | `roundbutton` |
| **TargetType**    | `Button` |

이 컨트롤 템플릿은 간단합니다.

- 컨트롤의 루트 요소,<xref:System.Windows.Controls.Grid>
- 단추의 둥근 모양을 그릴 수 있습니다. <xref:System.Windows.Shapes.Ellipse>
- 사용자가 <xref:System.Windows.Controls.ContentPresenter> 지정한 단추 콘텐츠를 표시할 수 있습니다.

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#ControlTemplate)]

### <a name="templatebinding"></a>TemplateBinding

새 <xref:System.Windows.Controls.ControlTemplate>을 만들 때 공용 속성을 사용하여 컨트롤의 모양을 변경할 수 있습니다. [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) 태그 확장컨트롤에 의해 정의 되는 공용 <xref:System.Windows.Controls.ControlTemplate> 속성에 있는 요소의 속성을 바인딩합니다. [TemplateBinding을](../../framework/wpf/advanced/templatebinding-markup-extension.md)사용하는 경우 컨트롤의 속성을 사용하여 템플릿의 매개 변수 역할을 할 수 있습니다. 즉, 컨트롤의 속성을 설정하면 해당 값은 [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md)이 있는 요소로 전달됩니다.

### <a name="ellipse"></a>타원

**:::no-loc text="Fill":::** **:::no-loc text="Stroke":::** <xref:System.Windows.Controls.Control.Foreground> <xref:System.Windows.Controls.Control.Background> **타원>요소의 속성은 컨트롤 \<** 및 속성에 바인딩됩니다.

### <a name="contentpresenter"></a>ContentPresenter

콘텐츠 발표자>요소도 템플릿에 추가됩니다. [ \<](xref:System.Windows.Controls.ContentPresenter) 이 템플릿은 단추용으로 설계되었기 때문에 단추에서 상속하는 것을 고려해야 <xref:System.Windows.Controls.ContentControl>합니다. 단추는 요소의 내용을 제공합니다. 일반 텍스트 나 다른 컨트롤과 같은 단추 내부에 무엇이든 설정할 수 있습니다. 다음 두 단추 모두 유효한 단추입니다.

```xaml
<Button>My Text</Button>

<!-- and -->

<Button>
    <CheckBox>Checkbox in a button</CheckBox>
</Button>
```

이전 예제 모두에서 텍스트와 확인란은 [Button.Content](xref:System.Windows.Controls.ContentControl.Content) 속성으로 설정됩니다. 콘텐츠로 설정 되는 모든 ** \<콘텐츠 는 ContentPresenter>** 통해 표시 될 수 있습니다., 템플릿은 무엇을.

의 <xref:System.Windows.Controls.ControlTemplate> 가 형식에 <xref:System.Windows.Controls.ContentControl> 적용되는 경우 `Button`(예: ) a <xref:System.Windows.Controls.ContentPresenter> 요소 트리에서 검색됩니다. 이 `ContentPresenter` 파일이 발견되면 템플릿은 컨트롤의 <xref:System.Windows.Controls.ContentControl.Content> 속성을 `ContentPresenter`에 자동으로 바인딩합니다.

## <a name="use-the-template"></a>템플릿 사용

이 문서의 시작 부분에 선언 된 단추를 찾습니다.

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

두 번째 단추의 <xref:System.Windows.Controls.Control.Template> 속성을 `roundbutton` 리소스로 설정합니다.

[!code-xaml[StyledButton](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButton)]

프로젝트를 실행하고 결과를 보면 단추에 둥근 배경이 있는 것을 볼 수 있습니다.

![하나의 템플릿 타원형 버튼이 있는 WPF 창](media/create-apply-template/styled-button.png)

버튼이 원이 아니라 기울어져 있는 것을 발견했을 수 있습니다. ** \<타원>** 요소의 작동 방식으로 인해 항상 사용 가능한 공간을 채우기 위해 확장됩니다. **:::no-loc text="width":::** 단추와 **:::no-loc text="height":::** 속성을 동일한 값으로 변경하여 원을 균일하게 만듭니다.

[!code-xaml[StyledButtonSize](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButtonSize)]

![하나의 템플릿 원형 버튼이 있는 WPF 창](media/create-apply-template/styled-uniform-button.png)

## <a name="add-a-trigger"></a>트리거 추가

템플릿이 적용된 단추는 다르게 보이지만 다른 단추와 동일하게 작동합니다. 버튼을 누르면 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트가 발생합니다. 그러나 단추 위로 마우스를 이동하면 단추의 시각적 개체가 변경되지 않는다는 것을 알았을 수 있습니다. 이러한 시각적 상호 작용은 모두 템플릿에 의해 정의됩니다.

WPF가 제공하는 동적 이벤트 및 속성 시스템을 사용하면 값에 대한 특정 속성을 보고 적절한 경우 템플릿의 스타일을 다시 선택할 수 있습니다. 이 예제에서는 단추의 <xref:System.Windows.UIElement.IsMouseOver> 속성을 볼 수 있습니다. 마우스가 컨트롤 위에 있으면 ** \<타원의**>새 색상으로 스타일을 정합니다. 이 유형의 트리거를 *PropertyTrigger*로 알려져 있습니다.

이 작업을 수행하려면 참조할 수 ** \<있는 타원>** 이름을 추가해야 합니다. 배경의 이름을 **지정요소**.

[!code-xaml[EllipseName](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml#EllipseName)]

다음으로 <xref:System.Windows.Trigger> [ControlTemplate.Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers) 컬렉션에 새 파일을 추가합니다. 트리거는 값에 `IsMouseOver` `true`대한 이벤트를 볼 수 있습니다.

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml?name=ControlTemplate&highlight=6-10)]

그런 다음 ** \<타원의** **채우기** 속성을 새 색상으로 변경하는 ** \<트리거>** ** \<setter>**>추가합니다.

[!code-xaml[MouseOver](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#MouseOver)]

프로젝트를 실행합니다. 단추 위로 마우스를 이동하면 ** \<타원의** 색상이>변경됩니다.

![마우스가 WPF 버튼을 통해 이동하여 채우기 색상을 변경합니다.](media/create-apply-template/mouse-move-over-button.gif)

## <a name="use-a-visualstate"></a>비주얼 스테이트 사용

시각적 상태는 컨트롤에 의해 정의되고 트리거됩니다. 예를 들어 마우스가 컨트롤 위로 이동하면 `CommonStates.MouseOver` 상태가 트리거됩니다. 컨트롤의 현재 상태에 따라 속성 변경 내용을 애니메이션할 수 있습니다. 이전 섹션에서는 ** \<PropertyTrigger>** 사용하여 단추의 전경을 `IsMouseOver` `true`속성이 `AliceBlue` 있을 때로 변경했습니다. 대신 이 색상의 변경내용을 애니메이션하는 시각적 상태를 만들어 부드러운 전환을 제공합니다. *VisualStates에*대한 자세한 내용은 [WPF의 스타일 및 템플릿을](../fundamentals/styles-templates-overview.md#visual-states)참조하십시오.

PropertyTrigger>애니메이션된 시각적 상태로 변환하려면 먼저 ** \<Template에서 ControlTemplate.Triggers>** 요소를 제거합니다. ** \<**

[!code-xaml[CleanTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#CleanTemplate)]

다음으로 컨트롤 ** \<** 템플릿의 그리드>루트에서 에 대한 `CommonStates` ** \<** ** \<VisualStateGroup>VisualStateGroup이 있는 VisualStateManager.VisualStateGroup>** 요소를 추가합니다. 두 상태를 `Normal` 정의하고 `MouseOver`.

[!code-xaml[VisualState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#VisualState)]

VisualState>정의된 모든 애니메이션은 해당 상태가 트리거될 때 적용됩니다. ** \<** 각 상태에 대한 애니메이션을 만듭니다. 애니메이션은 ** \<스토리보드>** 요소 안에 배치됩니다. 스토리보드에 대한 자세한 내용은 [스토리보드 개요를](../../framework/wpf/graphics-multimedia/storyboards-overview.md)참조하십시오.

- 정상

  이 상태는 타원 채우기를 애니메이션하여 컨트롤의 `Background` 색상으로 복원합니다.

  [!code-xaml[NormalState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#NormalState)]

- MouseOver

  이 상태는 타원 `Background` 색상을 새 색상으로 애니메이션합니다. `Yellow`

  [!code-xaml[MouseOverState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#MouseOverState)]

**이제 컨트롤 템플릿>다음과 같이 보입니다. \<**

[!code-xaml[FinalTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window7.xaml#FinalTemplate)]

프로젝트를 실행합니다. 단추 위로 마우스를 이동하면 ** \<타원의** 색상이>애니메이션됩니다.

![마우스가 WPF 버튼을 통해 이동하여 채우기 색상을 변경합니다.](media/create-apply-template/mouse-move-over-button-visualstate.gif)

## <a name="next-steps"></a>다음 단계

- [WPF에서 컨트롤에 대한 스타일 만들기](../fundamentals/styles-templates-create-apply-style.md)
- [WPF의 스타일 및 템플릿](../fundamentals/styles-templates-overview.md)
- [XAML 리소스 개요](../fundamentals/xaml-resources-define.md)

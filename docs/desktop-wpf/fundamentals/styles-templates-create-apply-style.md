---
title: 컨트롤에 대한 스타일 만들기
description: Windows 프레젠테이션 기반 및 .NET Core에서 컨트롤 스타일을 만들고 참조하는 방법을 알아봅니다.
author: thraka
ms.author: adegeo
ms.date: 09/12/2019
dev_langs:
- csharp
- vb
ms.openlocfilehash: 2956dbf93a1d34feca31d3ab10536f5089010189
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "81432559"
---
# <a name="create-a-style-for-a-control-in-wpf"></a>WPF에서 컨트롤에 대한 스타일 만들기

WPF(Windows 프레젠테이션 파운데이션)를 사용하면 재사용 가능한 스타일로 기존 컨트롤의 모양을 사용자 지정할 수 있습니다. 스타일은 앱, 창 및 페이지에 전역적으로 적용하거나 컨트롤에 직접 적용할 수 있습니다.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="create-a-style"></a>스타일 만들기

하나 이상의 요소에 <xref:System.Windows.Style> 속성 값 집합을 적용하는 편리한 방법으로 생각할 수 있습니다. <xref:System.Windows.FrameworkElement> 에서 파생되었거나 <xref:System.Windows.FrameworkContentElement> <xref:System.Windows.Window> <xref:System.Windows.Controls.Button>또는 a와 같은 모든 요소에서 스타일을 사용할 수 있습니다.

스타일을 선언하는 가장 일반적인 방법은 XAML `Resources` 파일의 섹션에 있는 리소스입니다. 스타일은 리소스이므로 모든 리소스에 적용되는 동일한 범위 지정 규칙을 준수합니다. 간단히 말해서 스타일을 선언하는 위치가 스타일을 적용할 수 있는 위치에 영향을 줍니다. 예를 들어 앱 정의 XAML 파일의 루트 요소에서 스타일을 선언하는 경우 앱의 어느 곳에서나 스타일을 사용할 수 있습니다.

[!code-xaml[AppResources](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/App.xaml#AppResources)]

앱의 XAML 파일 중 하나에서 스타일을 선언하는 경우 스타일은 해당 XAML 파일에서만 사용할 수 있습니다. 리소스 범위 지정 규칙에 대한 자세한 내용은 [XAML 리소스](xaml-resources-define.md)를 참조하세요.

[!code-xaml[AppResources](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowSingleResource.xaml#WindowResources)]

스타일은 스타일이 적용되는 `<Setter>` 요소에 속성을 설정하는 자식 요소로 구성됩니다. 위의 예에서 스타일이 `TextBlock` `TargetType` 특성을 통해 형식에 적용되도록 설정되어 있습니다. <xref:System.Windows.Controls.Control.FontSize%2A> 스타일은 `15` 을 및 에 <xref:System.Windows.Controls.Control.FontWeight%2A> 설정합니다. `ExtraBold` 스타일이 `<Setter>` 변경되는 각 속성에 대해 a를 추가합니다.

## <a name="apply-a-style-implicitly"></a>암시적으로 스타일 적용

A는 <xref:System.Windows.Style> 두 개 이상의 요소에 속성 값 집합을 적용하는 편리한 방법입니다. 예를 들어 다음 <xref:System.Windows.Controls.TextBlock> 요소와 창의 기본 모양을 고려합니다.

[!code-xaml[TextBlocks](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window1.xaml#SnippetTextBlocks)]

![샘플 스크린샷 스타일링](./media/styles-and-templates-overview/stylingintro-textblocksbefore.png "StylingIntro_TextBlocksBefore")

각 <xref:System.Windows.Controls.TextBlock> 요소에 대해 및 <xref:System.Windows.Controls.Control.FontFamily%2A>및 의 <xref:System.Windows.Controls.Control.FontSize%2A> 속성을 직접 설정하여 기본 모양을 변경할 수 있습니다. 그러나 <xref:System.Windows.Controls.TextBlock> 요소가 일부 속성을 공유하도록 하려면 여기에 표시된 <xref:System.Windows.Style> 대로 `Resources` XAML 파일의 섹션에서 a를 만들 수 있습니다.

[!code-xaml[DefaultTextBlockStyle](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window1.xaml#SnippetDefaultTextBlockStyle)]

<xref:System.Windows.Style.TargetType%2A> 스타일을 <xref:System.Windows.Controls.TextBlock> 형식으로 설정하고 특성을 `x:Key` 생략하면 스타일이 스타일에 적용된 모든 <xref:System.Windows.Controls.TextBlock> 요소에 적용되며, 일반적으로 XAML 파일 자체입니다.

이제 <xref:System.Windows.Controls.TextBlock> 요소는 다음과 같이 나타납니다.

![샘플 스크린샷 스타일링](./media/styles-and-templates-overview/stylingintro-textblocksbasestyle.png "StylingIntro_TextBlocksBaseStyle")

## <a name="apply-a-style-explicitly"></a>스타일을 명시적으로 적용

스타일에 값이 `x:Key` 있는 특성을 추가하면 스타일이 더 이상 <xref:System.Windows.Style.TargetType%2A>의 모든 요소에 암시적으로 적용되지 않습니다. 스타일을 명시적으로 참조하는 요소만 스타일이 적용됩니다.

다음은 이전 섹션의 스타일이지만 특성으로 `x:Key` 선언된 스타일입니다.

[!code-xaml[ExplicitStyleDeclare](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowExplicitStyle.xaml#ExplicitStyleDeclare)]

스타일을 적용하려면 여기에 <xref:System.Windows.FrameworkElement.Style%2A> 표시된 대로 [StaticResource 태그 확장을](../../framework/wpf/advanced/staticresource-markup-extension.md)사용하여 요소에 있는 속성을 `x:Key` 값으로 설정합니다.

[!code-xaml[ExplicitStyleReference](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowExplicitStyle.xaml#ExplicitStyleReference)]

첫 번째 <xref:System.Windows.Controls.TextBlock> 요소에는 스타일이 적용되었지만 두 번째 TextBlock 요소는 변경되지 않습니다. 이전 섹션의 암시적 스타일이 `x:Key` 특성을 선언하는 스타일로 변경되었습니다.

![샘플 스크린샷 스타일링](./media/styles-and-templates-overview/create-a-style-explicit-textblock.png "스타일-명시적 텍스트 블록 만들기")

스타일이 명시적으로 또는 암시적으로 적용되면 봉인되고 변경할 수 없습니다. 적용된 스타일을 변경하려면 새 스타일을 만들어 기존 스타일을 대체합니다. 자세한 내용은 <xref:System.Windows.Style.IsSealed%2A> 속성을 참조하세요.

사용자 지정 논리에 따라 적용할 스타일을 선택하는 개체를 만들 수 있습니다. 예를 들어 클래스에 대해 제공된 <xref:System.Windows.Controls.StyleSelector> 예제를 참조하십시오.

## <a name="apply-a-style-programmatically"></a>프로그래밍 방식으로 스타일 적용

명명된 스타일을 프로그래밍 방식으로 요소에 할당하려면 리소스 컬렉션에서 스타일을 가져옵니다. <xref:System.Windows.FrameworkElement.Style%2A> 리소스 컬렉션의 항목은 형식입니다. <xref:System.Object> 따라서 `Style` 속성에 할당 하기 전에 <xref:System.Windows.Style?displayProperty=fullName> 검색 된 스타일을 캐스팅 해야 합니다. 예를 들어 다음 코드는 `TextBlock` 명명된 `textblock1` 스타일을 정의된 `TitleText`스타일로 설정합니다.

[!code-csharp[SetStyleCode](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml.cs#SnippetSetStyleCode)]
[!code-vb[SetStyleCode](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/vb/MainWindow.xaml.vb#SnippetSetStyleCode)]

## <a name="extend-a-style"></a>스타일 확장

아마도 두 <xref:System.Windows.Controls.TextBlock> 요소가 <xref:System.Windows.Controls.Control.FontFamily%2A> 의 속성 값과 가운데를 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>공유하도록 할 수 있습니다. 그러나 **내 그림텍스트에** 몇 가지 추가 속성이 있기를 원합니다. 여기에 표시된 것처럼 첫 번째 스타일을 기반으로 하는 새 스타일을 만들어 이 작업을 수행할 수 있습니다.

[!code-xaml[DefaultTextBlockStyleBasedOn](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetDefaultTextBlockStyleBasedOn)]

[!code-xaml[TextBlocksExplicit](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetTextBlocksExplicit)]

이제 `TextBlock` 이 스타일은 가운데에 `Comic Sans MS` `26`위치하며, 의 크기가 있는 글꼴을 <xref:System.Windows.Media.LinearGradientBrush> 사용하고, 전경 색은 예제에 표시된 것으로 설정됩니다. 기본 스타일의 <xref:System.Windows.Controls.Control.FontSize%2A> 값을 재정의합니다. 에 동일한 속성을 가리키는 <xref:System.Windows.Setter> 것이 두 개 <xref:System.Windows.Style>이상 `Setter` 있는 경우 마지막으로 선언된 속성이 우선합니다.

다음은 <xref:System.Windows.Controls.TextBlock> 이제 요소가 어떻게 생겼는지 보여줍니다.

![스타일 적용된 TextBlocks](./media/styles-and-templates-overview/stylingintro-textblocks.png "StylingIntro_TextBlocks")

이 `TitleText` 스타일은 <xref:System.Windows.Controls.TextBlock> `BasedOn="{StaticResource {x:Type TextBlock}}"`에서 참조되는 형식에 대해 작성된 스타일을 확장합니다. 스타일을 사용하여 `x:Key` `x:Key` 있는 스타일을 확장할 수도 있습니다. 예를 들어 명명된 `Header1` 스타일이 있고 해당 스타일을 확장하려는 경우 `BasedOn="{StaticResource Header1}"`을 사용합니다.

## <a name="relationship-of-the-targettype-property-and-the-xkey-attribute"></a>TargetType 속성 및 x:Key 특성의 관계

앞서 보여 드시면 <xref:System.Windows.Style.TargetType%2A> `TextBlock` 스타일을 지정하지 않고 `x:Key` 속성을 설정하면 스타일이 <xref:System.Windows.Controls.TextBlock> 모든 요소에 적용됩니다. 이 경우 `x:Key`는 암시적으로 `{x:Type TextBlock}`으로 설정됩니다. `x:Key` 즉, `{x:Type TextBlock}`값을 제외한 다른 요소로 명시적으로 설정하면 모든 <xref:System.Windows.Style> `TextBlock` 요소에 자동으로 적용되지 않습니다. 대신 `x:Key` 스타일을 명시적으로 요소에 적용해야 합니다(값을 `TextBlock` 사용 하 여). 스타일이 리소스 섹션에 있고 `TargetType` 스타일에 속성을 설정하지 않은 경우 특성을 `x:Key` 설정해야 합니다.

`x:Key`에 대한 기본값을 제공하는 것 `TargetType` 외에도 속성은 setter 속성이 적용되는 형식을 지정합니다. 을 `TargetType`지정하지 않으면 구문을 <xref:System.Windows.Setter> `Property="ClassName.Property"`사용하여 클래스 이름으로 개체의 속성을 한정해야 합니다. 예를 들어 `Property="FontSize"`설정 대신 에 <xref:System.Windows.Setter.Property%2A> 설정하거나 `"TextBlock.FontSize"` `"Control.FontSize"`로 설정해야 합니다.

또한 많은 WPF 컨트롤은 다른 WPF 컨트롤의 조합으로 구성됩니다. 한 형식의 모든 컨트롤에 적용되는 스타일을 만들 경우 예기치 않은 결과가 발생할 수 있습니다. 예를 들어 에서 <xref:System.Windows.Controls.TextBlock> 형식을 대상으로 하는 스타일을 <xref:System.Windows.Window>만드는 경우 는 `TextBlock` `TextBlock` <xref:System.Windows.Controls.ListBox>의 다른 컨트롤의 일부인 경우에도 이 스타일이 창의 모든 컨트롤에 적용됩니다.

## <a name="see-also"></a>참조

<!-- - [Create a style for a control](styles-templates-create-apply-template.md) -->
- [XAML 리소스 개요](xaml-resources-define.md)
- [XAML 개요(WPF & .NET 코어)](xaml.md)

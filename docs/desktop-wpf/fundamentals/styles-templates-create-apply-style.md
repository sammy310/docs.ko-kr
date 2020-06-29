---
title: 컨트롤의 스타일 만들기
description: Windows Presentation Foundation 및 .NET Core에서 컨트롤의 스타일을 만들고 참조하는 방법을 알아봅니다.
author: adegeo
ms.author: adegeo
ms.date: 09/12/2019
dev_langs:
- csharp
- vb
ms.openlocfilehash: de186cd6da83ffef8a5cd59df581e88b24bc474d
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325788"
---
# <a name="create-a-style-for-a-control-in-wpf"></a>WPF에서 컨트롤의 스타일 만들기

WPF(Windows Presentation Foundation)를 사용하면 재사용 가능한 스타일로 기존 컨트롤의 모양을 사용자 지정할 수 있습니다. 스타일은 앱, 창 및 페이지에 전역적으로 또는 컨트롤에 직접 적용할 수 있습니다.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="create-a-style"></a>스타일 만들기

<xref:System.Windows.Style>를 하나 이상의 요소에 속성 값 집합을 적용하는 편리한 방법으로 생각할 수 있습니다. <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>에서 파생되는 모든 요소(예: <xref:System.Windows.Window> 또는 <xref:System.Windows.Controls.Button>)에 스타일을 사용할 수 있습니다.

스타일을 선언하는 가장 일반적인 방법은 XAML 파일의 `Resources` 섹션에 있는 리소스입니다. 스타일은 리소스이므로 모든 리소스에 적용되는 동일한 범위 지정 규칙을 따릅니다. 간단히 말해서 스타일을 선언하는 경우 스타일을 적용할 수 있는 위치에 영향을 줍니다. 예를 들어 스타일을 앱 정의 XAML 파일의 루트 요소에서 선언하면 앱의 모든 곳에서 스타일을 사용할 수 있습니다.

[!code-xaml[AppResources](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/App.xaml#AppResources)]

앱의 XAML 파일 중 하나에서 스타일을 선언하는 경우 해당 XAML 파일에만 스타일을 사용할 수 있습니다. 리소스 범위 지정 규칙에 대한 자세한 내용은 [XAML 리소스](xaml-resources-define.md)를 참조하세요.

[!code-xaml[AppResources](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowSingleResource.xaml#WindowResources)]

스타일은 스타일이 적용되는 요소에 속성을 설정하는 `<Setter>` 자식 요소로 구성됩니다. 위의 예제에서는 `TargetType` 특성을 통해 `TextBlock` 형식에 적용되도록 스타일이 설정되어 습니다. 이 스타일은 <xref:System.Windows.Controls.Control.FontSize%2A>를 `15`로 설정하고 <xref:System.Windows.Controls.Control.FontWeight%2A>를 `ExtraBold`로 설정합니다. 스타일이 변경하는 각 속성에 대해 `<Setter>`를 추가합니다.

## <a name="apply-a-style-implicitly"></a>암시적으로 스타일 적용

<xref:System.Windows.Style>은 여러 요소에 속성 값 집합을 적용하는 편리한 방법입니다. 예를 들어 창에서 다음 <xref:System.Windows.Controls.TextBlock> 요소와 기본 모양을 생각해 보겠습니다.

[!code-xaml[TextBlocks](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window1.xaml#SnippetTextBlocks)]

![스타일 지정 샘플 스크린샷](./media/styles-and-templates-overview/stylingintro-textblocksbefore.png "StylingIntro_TextBlocksBefore")

각 <xref:System.Windows.Controls.TextBlock> 요소에서 직접 <xref:System.Windows.Controls.Control.FontSize%2A> 및 <xref:System.Windows.Controls.Control.FontFamily%2A> 같은 속성을 설정하여 기본 모양을 변경할 수 있습니다. 그러나 <xref:System.Windows.Controls.TextBlock> 요소가 일부 속성을 공유하도록 하려면 여기에 나와 있는 것처럼 XAML 파일의 `Resources` 섹션에서 <xref:System.Windows.Style>을 만들 수 있습니다.

[!code-xaml[DefaultTextBlockStyle](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window1.xaml#SnippetDefaultTextBlockStyle)]

스타일의 <xref:System.Windows.Style.TargetType%2A>를 <xref:System.Windows.Controls.TextBlock> 형식으로 설정하고 `x:Key` 특성을 생략하면 스타일은 해당 스타일로 범위가 지정된 모든 <xref:System.Windows.Controls.TextBlock> 요소에 적용됩니다. 이 범위는 일반적으로 XAML 파일 자체입니다.

이제 <xref:System.Windows.Controls.TextBlock> 요소가 다음과 같이 표시됩니다.

![스타일 지정 샘플 스크린샷](./media/styles-and-templates-overview/stylingintro-textblocksbasestyle.png "StylingIntro_TextBlocksBaseStyle")

## <a name="apply-a-style-explicitly"></a>명시적으로 스타일 적용

값을 포함하는 `x:Key` 특성을 스타일에 추가하면 스타일은 더 이상 <xref:System.Windows.Style.TargetType%2A>의 모든 요소에 암시적으로 적용되지 않습니다. 스타일을 명시적으로 참조하는 요소에만 스타일이 적용됩니다.

다음은 이전 섹션의 스타일이지만 `x:Key` 특성을 사용하여 선언되었습니다.

[!code-xaml[ExplicitStyleDeclare](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowExplicitStyle.xaml#ExplicitStyleDeclare)]

스타일을 적용하려면 아래와 같이 [StaticResource 태그 확장](../../framework/wpf/advanced/staticresource-markup-extension.md)을 사용하여 요소의 <xref:System.Windows.FrameworkElement.Style%2A> 속성을 `x:Key` 값으로 설정합니다.

[!code-xaml[ExplicitStyleReference](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/WindowExplicitStyle.xaml#ExplicitStyleReference)]

첫 번째 <xref:System.Windows.Controls.TextBlock> 요소는 두 번째 TextBlock 요소가 변경되지 않은 상태에서 스타일을 적용합니다. 이전 섹션의 암시적 스타일이 `x:Key` 특성을 선언하는 스타일로 변경되었습니다. 즉, 스타일의 영향을 받는 유일한 요소는 스타일을 직접 참조한 요소입니다.

![스타일 지정 샘플 스크린샷](./media/styles-and-templates-overview/create-a-style-explicit-textblock.png "create-a-style-explicit-textblock")

스타일은 명시적으로 또는 암시적으로 적용한 후에는 봉인되며 변경할 수 없습니다. 적용된 스타일을 변경하려면 새 스타일을 만들어 기존 스타일을 바꿉니다. 자세한 내용은 <xref:System.Windows.Style.IsSealed%2A> 속성을 참조하세요.

사용자 지정 논리에 따라 적용할 스타일을 선택하는 개체를 만들 수 있습니다. 예제는 <xref:System.Windows.Controls.StyleSelector> 클래스에 제공된 예제를 참조하세요.

## <a name="apply-a-style-programmatically"></a>프로그래밍 방식으로 스타일 적용

명명된 스타일을 요소에 프로그래밍 방식으로 할당하려면 리소스 컬렉션에서 스타일을 가져오고 요소의 <xref:System.Windows.FrameworkElement.Style%2A> 속성에 할당합니다. 리소스 컬렉션의 항목은 <xref:System.Object> 형식입니다. 따라서 `Style` 속성에 할당하기 전에 검색된 스타일을 <xref:System.Windows.Style?displayProperty=fullName>에 캐스팅해야 합니다. 예를 들어 다음 코드는 `textblock1`이라는 `TextBlock`의 스타일을 정의된 스타일 `TitleText`로 설정합니다.

[!code-csharp[SetStyleCode](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml.cs#SnippetSetStyleCode)]
[!code-vb[SetStyleCode](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/vb/MainWindow.xaml.vb#SnippetSetStyleCode)]

## <a name="extend-a-style"></a>스타일 확장

예를 들어 두 개의 <xref:System.Windows.Controls.TextBlock> 요소에서 <xref:System.Windows.Controls.Control.FontFamily%2A> 및 가운데 맞춤 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 같은 일부 속성 값을 공유하도록 하려고 합니다. 그러나 텍스트 **내 그림**도 일부 추가 속성을 포함해야 합니다. 이 작업을 수행하려면 다음과 같이 첫 번째 스타일을 기반으로 새 스타일을 만듭니다.

[!code-xaml[DefaultTextBlockStyleBasedOn](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetDefaultTextBlockStyleBasedOn)]

[!code-xaml[TextBlocksExplicit](~/samples/snippets/desktop-guide/wpf/styles-and-templates-intro/csharp/Window2.xaml#SnippetTextBlocksExplicit)]

이 `TextBlock` 스타일은 이제 가운데 맞춤되고 `26` 크기의 `Comic Sans MS` 글꼴을 사용하며 전경색은 예제에 표시된 <xref:System.Windows.Media.LinearGradientBrush>로 설정됩니다. 기본 스타일의 <xref:System.Windows.Controls.Control.FontSize%2A> 값은 재정의됩니다. <xref:System.Windows.Style>의 동일한 속성을 가리키는 <xref:System.Windows.Setter>가 두 개 이상 있는 경우 마지막으로 선언된 `Setter`가 우선적으로 적용됩니다.

<xref:System.Windows.Controls.TextBlock> 요소는 이제 다음과 같이 표시됩니다.

![스타일 적용된 TextBlock](./media/styles-and-templates-overview/stylingintro-textblocks.png "StylingIntro_TextBlocks")

이 `TitleText` 스타일은 `BasedOn="{StaticResource {x:Type TextBlock}}"`으로 참조되는 <xref:System.Windows.Controls.TextBlock> 형식에 대해 만들어진 스타일을 확장합니다. 스타일의 `x:Key`를 사용하여 `x:Key`가 포함된 스타일을 확장할 수도 있습니다. 예를 들어 `Header1`이라는 스타일을 확장하려는 경우 `BasedOn="{StaticResource Header1}"`를 사용합니다.

## <a name="relationship-of-the-targettype-property-and-the-xkey-attribute"></a>TargetType 속성과 x:Key 특성의 관계

앞서 설명한 것처럼 `x:Key` 스타일을 할당하지 않고 <xref:System.Windows.Style.TargetType%2A> 속성을 `TextBlock`로 설정하면 스타일이 모든 <xref:System.Windows.Controls.TextBlock> 요소에 적용됩니다. 이 경우 `x:Key`는 암시적으로 `{x:Type TextBlock}`으로 설정됩니다. 즉, `x:Key` 값을 `{x:Type TextBlock}` 이외의 값으로 명시적으로 설정하면 <xref:System.Windows.Style>이 자동으로 모든 `TextBlock` 요소에 적용되지 않습니다. 대신 `x:Key` 값을 사용하여 `TextBlock` 요소에 스타일을 명시적으로 적용해야 합니다. 스타일이 리소스 섹션에 있고 스타일에 `TargetType` 속성을 설정하지 않은 경우 `x:Key` 특성을 설정해야 합니다.

`TargetType` 속성은 `x:Key`의 기본값을 제공할 뿐 아니라 setter 속성이 적용되는 형식을 지정합니다. `TargetType`을 지정하지 않으면 구문 `Property="ClassName.Property"`를 사용하여 클래스 이름으로 <xref:System.Windows.Setter> 개체의 속성을 정규화해야 합니다. 예를 들어 `Property="FontSize"`를 설정하는 대신 <xref:System.Windows.Setter.Property%2A>를 `"TextBlock.FontSize"` 또는 `"Control.FontSize"`로 설정해야 합니다.

또한 WPF 컨트롤은 대부분 다른 WPF 컨트롤의 조합으로 구성된다는 점을 알아야 합니다. 한 형식의 모든 컨트롤에 적용되는 스타일을 만들 경우 예기치 않은 결과가 발생할 수 있습니다. 예를 들어 <xref:System.Windows.Window>에서 <xref:System.Windows.Controls.TextBlock> 형식을 대상으로 하는 스타일을 만드는 경우 `TextBlock`이 <xref:System.Windows.Controls.ListBox> 같은 다른 컨트롤의 일부인 경우에도 해당 스타일이 창의 모든 `TextBlock` 컨트롤에 적용됩니다.

## <a name="see-also"></a>참조

<!-- - [Create a style for a control](styles-templates-create-apply-template.md) -->
- [XAML 리소스 개요](xaml-resources-define.md)
- [XAML 개요(WPF 및 .NET Core)](xaml.md)

---
title: XAML 개요
description: .NET 코어에 대한 WPF(Windows 프레젠테이션 재단)에서 XAML 언어를 어떻게 구성하고 구현하는지 알아봅니다.
author: thraka
ms.date: 08/08/2019
ms.author: adegeo
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user interfaces [XAML]
- classes [XAML]
- root element [XAML]
- XAML [WPF], about XAML
- base classes [XAML]
- routed events [WPF]
- code-behind files [WPF], XAML
- collection properties [XAML]
- events [XAML]
- property element [XAML]
- content models [XAML]
- Extensible Application Markup Language (see XAML)
- attribute syntax [XAML]
ms.openlocfilehash: b0a9357b623fbde08731a5b1ddb8fee3a93824c2
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2020
ms.locfileid: "81433003"
---
# <a name="xaml-overview-in-wpf"></a>WPF의 XAML 개요

이 문서에서는 XAML 언어의 기능에 대해 설명하고 XAML을 사용하여 WPF(Windows 프레젠테이션 파운데이션) 앱을 작성하는 방법을 보여 줍니다. 이 문서에서는 WPF에서 구현한 XAML에 대해 구체적으로 설명합니다. XAML 자체는 WPF보다 더 큰 언어 개념입니다.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="what-is-xaml"></a>XAML이란 무엇입니까?

XAML은 선언적 태그 언어입니다. .NET Core 프로그래밍 모델에 적용된 XAML은 .NET Core 앱에 대한 UI 만들기를 간소화합니다. 선언적 XAML 태그에 표시되는 UI 요소를 만든 다음 부분 클래스 정의를 통해 태그에 조인된 코드 숨김 파일을 사용하여 UI 정의를 런타임 논리와 구분할 수 있습니다. XAML은 어셈블리에 정의된 특정 지원 형식 집합으로 개체의 인스턴스화를 직접 나타냅니다. 이는 지원 형식 시스템에 직접 연결되지 않고 해석되는 언어인 대부분의 다른 태그 언어와의 차이점입니다. XAML을 사용하면 잠재적으로 다른 도구를 사용하여 별도의 당사자가 UI 및 앱 논리에서 작업할 수 있는 워크플로를 사용할 수 있습니다.

텍스트로 나타내는 경우 XAML 파일은 일반적으로 확장명이 `.xaml`인 XML 파일입니다. 이 파일은 모든 XML 인코딩 방식으로 인코딩될 수 있지만 일반적으로 UTF-8로 인코딩됩니다.

다음 예제에서는 UI의 일부로 단추를 만드는 방법을 보여 주입니다. 이 예제는 XAML이 일반적인 UI 프로그래밍 비유를 나타내는 방법을 설명하기 위한 것입니다(전체 샘플이 아님).

[!code-xaml[XAMLOvwSupport#DirtSimple](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#dirtsimple)]

## <a name="xaml-syntax-in-brief"></a>간략한 XAML 구문

다음 섹션에서는 XAML 구문의 기본 형식에 대해 설명하고 간단한 태그 예제를 제공합니다. 각 구문 형식에 대해 자세하게 설명하지는 않습니다. 예를 들어, 지원 형식 시스템에서 이러한 구문을 어떻게 나타내는지에 대해서는 설명하지 않습니다. XAML 구문의 세부 사항에 대한 자세한 내용은 [XAML 구문 세부 정보를](../../framework/wpf/advanced/xaml-syntax-in-detail.md)참조하십시오.

XML 언어에 익숙한 경우 다음 몇 섹션의 많은 자료가 기본이 될 것입니다. 이는 XAML의 기본적 설계 원칙 중 하나에 따른 결과입니다. XAML 언어는 자체 개념을 정의하지만 이러한 개념은 XML 언어 및 태그 양식 내에서 작동합니다.

### <a name="xaml-object-elements"></a>XAML 오브젝트 요소

일반적으로 개체 요소는 특정 형식의 인스턴스를 선언합니다. 이 형식은 XAML을 언어로 사용하는 기술에서 참조하는 어셈블리에 정의됩니다.

개체 요소 구문은 항상 여는 꺾쇠 괄호(`<`)로 시작합니다. 괄호 뒤에 인스턴스를 만들려는 형식의 이름이 나옵니다. 이름에는 나중에 설명할 접두사 개념이 포함될 수 있습니다. 그런 다음 개체 요소에 속성을 선택적으로 선언할 수 있습니다. 오브젝트 요소 태그를 완성하려면 닫는 각도`>`대괄호()로 끝을 맺습니다. 대신 정방향 슬래시와 클로징 앵글 브래킷을 연속적으로`/>`사용하여 태그를 완료하여 콘텐츠가 없는 자체 닫는 양식을 사용할 수 있습니다. 예를 들어 이전에 표시된 태그 스니펫을 다시 살펴봅니다.

[!code-xaml[XAMLOvwSupport#DirtSimple](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#dirtsimple)]

이 코드는 `<StackPanel>`(콘텐츠 및 나중에 닫는 태그 있음) 및 `<Button .../>`(자체 닫는 형식, 여러 특성이 있음)이라는 두 개의 개체 요소를 지정합니다. WPF에 `StackPanel` `Button` 의해 정의되고 WPF 어셈블리의 일부인 클래스의 이름으로 오브젝트 요소와 각 맵을 매핑합니다. 개체 요소 태그를 지정할 때 XAML 처리에 대 한 명령을 만들어 기본 형식의 새 인스턴스를 만듭니다. 각 인스턴스는 XAML을 구문 분석하고 로드할 때 기본 형식의 매개 변수 없는 생성자호출을 통해 만들어집니다.

### <a name="attribute-syntax-properties"></a>특성 구문(속성)

개체 속성은 개체 요소의 특성으로 표현되는 경우가 많습니다. 특성 구문은 설정 중인 개체 속성의 이름을 지정한 다음 할당 연산자(=)를 지정합니다. 특성 값은 항상 따옴표 안에 포함된 문자열로 지정됩니다.

특성 구문은 가장 효율적인 속성 설정 구문이며 과거에 태그 언어를 사용한 적이 있는 개발자에게 가장 직관적인 구문입니다. 예를 들어, 다음 태그는 빨간색 텍스트와 파란색 배경이 있으며 `Content`로 지정된 표시 텍스트가 있는 단추를 만듭니다.

[!code-xaml[XAMLOvwSupport#BlueRedButton](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#blueredbutton)]

### <a name="property-element-syntax"></a>속성 요소 구문

개체 요소의 일부 속성의 경우에는 속성 값을 제공하기 위해 필요한 개체나 정보를 특성 구문의 문자열 제한에 맞춰 따옴표 안에 적절하게 표현할 수 없기 때문에 특성 구문을 사용할 수 없습니다. 이러한 경우에는 속성 요소 구문이라고 하는 다른 구문을 사용할 수 있습니다.

속성 요소 시작 태그에 대한 `<TypeName.PropertyName>`구문은 . 일반적으로 해당 태그의 내용은 속성이 해당 값으로 걸리는 형식의 개체 요소입니다. 콘텐츠를 지정한 후에는 끝 태그를 통해 속성 요소를 닫아야 합니다. 끝 태그에 대한 구문은 `</TypeName.PropertyName>`.

특성 구문이 지원되는 경우에는 특성 구문을 사용하는 것이 일반적으로 편리하며 태그를 간결하게 만들 수 있지만 이것은 기술적으로 제한이 있다는 것을 의미하는 것이 아니라 대체로 스타일의 문제입니다. 다음 예제에서는 앞의 특성 구문 예제에서와 같이 동일한 속성을 설정하는 것을 보여 주지만 이번에는 `Button`의 모든 속성에 대해 속성 요소 구문을 사용합니다.

[!code-xaml[XAMLOvwSupport#BlueRedButtonPE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#blueredbuttonpe)]

### <a name="collection-syntax"></a>컬렉션 구문

XAML 언어에는 보다 읽기 쉬운 태그를 생성하는 몇 가지 최적화 기능이 포함되어 있습니다. 이러한 최적화 중 하나는 특정 속성이 컬렉션 형식을 사용하는 경우 태그에서 해당 속성 값 내에 자식 요소로 선언하는 항목이 컬렉션에 포함되는 것입니다. 이 경우 자식 개체 요소의 컬렉션이 컬렉션 속성에 설정되는 값입니다.

다음 예제에서는 <xref:System.Windows.Media.GradientBrush.GradientStops%2A> 속성의 값을 설정 하기 위한 컬렉션 구문을 보여 주며 있습니다.

```xaml
<LinearGradientBrush>
  <LinearGradientBrush.GradientStops>
    <!-- no explicit new GradientStopCollection, parser knows how to find or create -->
    <GradientStop Offset="0.0" Color="Red" />
    <GradientStop Offset="1.0" Color="Blue" />
  </LinearGradientBrush.GradientStops>
</LinearGradientBrush>
```

### <a name="xaml-content-properties"></a>XAML 콘텐츠 속성

XAML은 클래스가 해당 속성 중 하나를 XAML _콘텐츠_ 속성으로 정확히 지정할 수 있는 언어 기능을 지정합니다. 개체 요소의 자식 요소가 해당 콘텐츠 속성의 값을 설정하는 데 사용됩니다. 즉, 콘텐츠 속성이 고유한 경우에는 XAML 태그에서 해당 속성을 설정할 때 속성 요소를 생략하고 태그 내에 보다 가시적인 부모/자식 비유를 생성할 수 있습니다.

예를 들어 <xref:System.Windows.Controls.Border> 의 _콘텐츠_ 속성을 <xref:System.Windows.Controls.Decorator.Child%2A>지정합니다. 다음 두 <xref:System.Windows.Controls.Border> 요소는 동일하게 처리됩니다. 첫 번째 요소는 콘텐츠 속성 구문을 이용하고 `Border.Child` 속성 요소를 생략합니다. 두 번째 요소는 명시적으로 `Border.Child`를 표시합니다.

```xaml
<Border>
  <TextBox Width="300"/>
</Border>
<!--explicit equivalent-->
<Border>
  <Border.Child>
    <TextBox Width="300"/>
  </Border.Child>
</Border>
```

XAML 언어의 규칙에 따라 XAML 콘텐츠 속성의 값은 해당 개체 요소의 다른 모든 속성 요소의 맨 앞 또는 맨 뒤에 지정해야 합니다. 예를 들어 다음 태그는 컴파일되지 않습니다.

```xaml
<Button>I am a
  <Button.Background>Blue</Button.Background>
  blue button</Button>
```

XAML 구문의 세부 사항에 대한 자세한 내용은 [XAML 구문 세부 정보를](../../framework/wpf/advanced/xaml-syntax-in-detail.md)참조하십시오.

### <a name="text-content"></a>텍스트 콘텐츠

일부 XAML 요소는 텍스트를 자신의 콘텐츠로 직접 처리할 수 있습니다. 이렇게 하려면 다음 경우 중 하나에 해당해야 합니다.

- 클래스는 content 속성을 선언해야 하며 해당 콘텐츠 속성은 문자열에 할당한 형식이어야 <xref:System.Object>합니다(형식은 형식일 수 있음). 예를 들어, <xref:System.Windows.Controls.ContentControl> <xref:System.Windows.Controls.ContentControl.Content%2A> 모든 콘텐츠 속성으로 사용 <xref:System.Object>하 고 그것은 type <xref:System.Windows.Controls.ContentControl> , 그리고 <xref:System.Windows.Controls.Button> `<Button>Hello</Button>`이 와 같은 에 다음과 같은 사용을 지원 합니다.

- 형식에서 형식 변환기를 선언해야 합니다. 이 경우 텍스트 콘텐츠가 이 형식 변환기의 초기화 텍스트로 사용됩니다. 예를 들어 `<Brush>Blue</Brush>` 콘텐츠 `Blue` 값을 브러시로 변환합니다. 이러한 경우는 실제로 그다지 일반적이지 않습니다.

- 형식은 알려진 XAML 언어 기본 형식이어야 합니다.

### <a name="content-properties-and-collection-syntax-combined"></a>콘텐츠 속성 및 컬렉션 구문 결합

이 예제를 고려하십시오.

```xaml
<StackPanel>
  <Button>First Button</Button>
  <Button>Second Button</Button>
</StackPanel>
```

여기서 각 <xref:System.Windows.Controls.Button> 요소는 의 <xref:System.Windows.Controls.StackPanel>자식 요소입니다. 이는 두 가지 서로 다른 이유로 두 태그를 생략하는 효율적이며 직관적인 태그입니다.

- **생략된 스택패널.자식 속성 요소:** <xref:System.Windows.Controls.StackPanel> 에서 <xref:System.Windows.Controls.Panel>파생됩니다. <xref:System.Windows.Controls.Panel>XAML 콘텐츠 속성으로 정의됩니다. <xref:System.Windows.Controls.Panel.Children%2A?displayProperty=nameWithType>

- **생략된 UIElementCollection 개체 요소:** 속성은 <xref:System.Windows.Controls.Panel.Children%2A?displayProperty=nameWithType> 을 <xref:System.Windows.Controls.UIElementCollection>구현하는 형식을 <xref:System.Collections.IList>취합니다. 컬렉션과 같은 컬렉션을 처리하기 위한 XAML 규칙에 따라 컬렉션의 요소 태그를 <xref:System.Collections.IList>생략할 수 있습니다. 이 경우 매개 <xref:System.Windows.Controls.UIElementCollection> 변수 없는 생성자가 노출되지 않으므로 실제로 인스턴스화할 수 없으므로 <xref:System.Windows.Controls.UIElementCollection> 개체 요소가 주석 주석이 표시됩니다.

```xaml
<StackPanel>
  <StackPanel.Children>
    <!--<UIElementCollection>-->
    <Button>First Button</Button>
    <Button>Second Button</Button>
    <!--</UIElementCollection>-->
  </StackPanel.Children>
</StackPanel>
```

### <a name="attribute-syntax-events"></a>특성 구문(이벤트)

속성이 아니라 이벤트인 멤버에 대해서도 특성 구문을 사용할 수 있습니다. 이 경우 특성 이름은 이벤트의 이름입니다. XAML 이벤트에 대한 WPF 구현에서 특성 값은 해당 이벤트의 대리자를 구현하는 처리기의 이름입니다. 예를 들어 다음 태그는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트에 대한 처리기를 <xref:System.Windows.Controls.Button> 태그에서 만든 에 할당합니다.

[!code-xaml[XAMLOvwSupport#ButtonWithCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml#buttonwithcodebehind)]

WPF의 XAML 및 이벤트에는 이 특성 구문 예제보다 훨씬 더 많은 기능이 있습니다. 예를 들어, 여기서 참조된 `ClickHandler`가 무엇을 나타내며 어떻게 정의되는지가 궁금할 수 있습니다. 이 문서는 이 문서의 향후 [이벤트 및 XAML 코드 숨김](#events-and-xaml-code-behind) 섹션에서 설명합니다.

## <a name="case-and-white-space-in-xaml"></a>XAML의 케이스 및 공백

일반적으로 XAML은 대/소문자를 구분합니다. 백업 형식을 해결하기 위해 WPF XAML은 CLR이 대/소문자를 구분하는 것과 동일한 규칙에 따라 대/소문자를 구분합니다. 개체 요소, 속성 요소 및 특성 이름은 모두 어셈블리의 기본 형식 또는 형식 멤버의 이름과 비교해 대/소문자를 사용하여 지정해야 합니다. XAML 언어 키워드와 기본 어휘도 대/소문자를 구분합니다. 값이 항상 대/소문자를 구분하는 것은 아닙니다. 값의 대/소문자 구분은 값 또는 속성 값 형식을 사용하는 속성과 연결된 형식 변환기의 동작에 따라 다릅니다. 예를 <xref:System.Boolean> 들어 형식을 취하는 속성은 `true` 동일한 `True` 값으로 걸릴 수 있지만 문자열에 대한 기본 WPF XAML 파서 형식 변환이 <xref:System.Boolean> 이미 이러한 값을 등가값으로 허용하기 때문입니다.

WPF XAML 프로세서와 직렬화기는 중요하지 않은 모든 공백을 무시하거나 삭제하며 중요한 공백을 정규화합니다. 이는 XAML 사양의 기본 공백 동작 권장 사항과 일치합니다. 이 동작은 XAML 콘텐츠 속성 내에서 문자열을 지정할 때만 이 동작이 가져옵니다. 간단히 말해서 XAML은 공간, 줄 바침 및 탭 문자를 공백으로 변환한 다음 연속 문자열의 양쪽 끝에 있는 경우 하나의 공백을 유지합니다. XAML 공백 처리에 대한 전체 설명은 이 문서에서 다루지 않습니다. 자세한 내용은 [XAML의 공백 처리를](../xaml-services/white-space-processing.md)참조하십시오.

## <a name="markup-extensions"></a>태그 확장

태그 확장은 XAML 언어 개념입니다. 특성 구문의 값을 제공하기 위해 사용할 때 중괄호(`{` 및 `}`)는 태그 확장 사용을 나타냅니다. 이 사용에서는 특성 값의 일반적인 처리를 리터럴 문자열이나 문자열 변환 가능 값으로 이스케이프하도록 XAML에 지시합니다.

WPF 앱 프로그래밍에 사용되는 가장 일반적인 [`Binding`](../../framework/wpf/advanced/binding-markup-extension.md)태그 확장은 데이터 바인딩 식 및 [`StaticResource`](../../framework/wpf/advanced/staticresource-markup-extension.md) [`DynamicResource`](../../framework/wpf/advanced/dynamicresource-markup-extension.md)리소스 참조 및 에 사용됩니다. 태그 확장을 사용하면 일반적으로 속성이 특성 구문을 지원하지 않더라도 특성 구문을 사용하여 속성 값을 제공할 수 있으며, 태그 확장은 종종 중간 식 형식을 사용하여 값을 연기하거나 런타임에만 존재하는 다른 개체를 참조하는 등의 기능을 활성화합니다.

예를 들어 다음 태그는 특성 구문을 사용하여 <xref:System.Windows.FrameworkElement.Style%2A> 속성의 값을 설정합니다. 속성은 <xref:System.Windows.FrameworkElement.Style%2A> <xref:System.Windows.Style> 기본적으로 특성 구문 문자열에 의해 인스턴스화 할 수없는 클래스의 인스턴스를 합니다. 그러나 이 경우 특성은 특정 태그 확장을 `StaticResource`참조합니다. 해당 태그 확장이 처리되면 이전에 리소스 사전에서 키가 지정된 리소스로 인스턴스화된 스타일에 대한 참조를 반환합니다.

[!code-xaml[FEResourceSH_snip#XAMLOvwShortResources](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xamlovwshortresources)]
[!code-xaml[FEResourceSH_snip#XAMLOvwShortResources2](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xamlovwshortresources2)]
[!code-xaml[FEResourceSH_snip#XAMLOvwShortResources3](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xamlovwshortresources3)]

WPF에 구체적으로 구현된 XAML에 대한 모든 태그 확장의 참조 목록을 보려면 [WPF XAML 확장](../../framework/wpf/advanced/wpf-xaml-extensions.md)을 참조하세요. System.Xaml에서 정의하고 .NET Core XAML 구현에 더 널리 사용할 수 있는 태그 확장에 대한 참조 목록은 [XAML 네임스페이스(x:) 참조를 참조하십시오. 언어 기능](../xaml-services/namespace-language-features.md). 태그 확장 개념에 대한 자세한 내용은 [태그 확장 및 WPF XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)을 참조하세요.

## <a name="type-converters"></a>유형 변환기

이 [XAML 구문 개요](#xaml-syntax-in-brief) 섹션에서는 문자열로 특성 값을 설정할 수 있어야 한다고 설명했습니다. 문자열을 다른 개체 형식 또는 기본 값으로 변환하는 방법의 기본 기본 <xref:System.String> 처리는 <xref:System.DateTime> 또는 와 <xref:System.Uri>같은 특정 형식에 대한 기본 처리 외에도 형식 자체를 기반으로 합니다. 그러나 이러한 형식의 많은 WPF 형식 또는 멤버는 보다 복잡한 개체 형식의 인스턴스를 문자열 및 특성으로 지정할 수 있도록 기본 문자열 특성 처리 동작을 확장합니다.

구조는 <xref:System.Windows.Thickness> XAML 사용에 대해 형식 변환이 활성화된 형식의 예입니다. <xref:System.Windows.Thickness>중첩된 사각형 내에서 측정값을 나타내며 와 같은 <xref:System.Windows.FrameworkElement.Margin%2A>속성의 값으로 사용됩니다. <xref:System.Windows.Thickness>에 형식 변환기를 배치 하면 특성으로 <xref:System.Windows.Thickness> 지정할 수 있으므로 XAML에서 지정하기 가 더 쉽습니다. 다음 예제에서는 형식 변환 및 특성 구문을 사용하여 <xref:System.Windows.FrameworkElement.Margin%2A>다음에 대한 값을 제공합니다.

[!code-xaml[XAMLOvwSupport#MarginTCE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#margintce)]

이전 특성 구문 예제는 <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.Thickness> 개체 요소를 포함하는 속성 요소 구문을 통해 설정되는 다음과 같은 자세한 구문 예제와 동일합니다. 의 <xref:System.Windows.Thickness> 네 가지 주요 속성은 새 인스턴스의 특성으로 설정됩니다.

[!code-xaml[XAMLOvwSupport#MarginVerbose](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#marginverbose)]

> [!NOTE]
> 또한 형식 자체에 매개 변수 없는 생성자가 없기 때문에 형식 변환이 하위 클래스를 포함하지 않고 해당 형식에 속성을 설정하는 유일한 공용 방법입니다. 예제는 <xref:System.Windows.Input.Cursor>입니다.

형식 변환에 대한 자세한 내용은 [TypeConverters 및 XAML](../../framework/wpf/advanced/typeconverters-and-xaml.md)을 참조하십시오.

## <a name="xaml-root-elements-and-xaml-namespaces"></a>XAML 루트 요소 및 XAML 네임스페이스

XAML 파일에는 잘 구성된 XML 파일과 유효한 XAML 파일이 모두 되기 위해서는 루트 요소가 하나만 있어야 합니다. <xref:System.Windows.Window> 일반적인 WPF 시나리오의 경우 WPF 앱 모델(예: <xref:System.Windows.Controls.Page> 또는 페이지, <xref:System.Windows.ResourceDictionary> 외부 사전 또는 <xref:System.Windows.Application> 앱 정의)에서 두드러진 의미를 가진 루트 요소를 사용합니다. 다음 예제에서는 WPF 페이지에 대한 일반적인 XAML 파일의 루트 요소와 <xref:System.Windows.Controls.Page>의 루트 요소를 보여 주며 의 루트 요소를 보여 주면 됩니다.

[!code-xaml[XAMLOvwSupport#RootOnly](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#rootonly)]
[!code-xaml[XAMLOvwSupport#RootOnly2](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#rootonly2)]

루트 요소에는 `xmlns`와 `xmlns:x` 특성도 포함됩니다. 이러한 특성은 태그가 요소로 참조할 요소의 지원 형식에 대한 형식 정의가 포함된 XAML 네임스페이스를 XAML 프로세서에 나타냅니다. `xmlns` 특성은 특히 기본 XAML 네임스페이스를 나타냅니다. 기본 XAML 네임스페이스 안에서는 태그의 개체 요소를 접두사 없이 지정할 수 있습니다. 대부분의 WPF 앱 시나리오와 SDK의 WPF 섹션에 제공된 거의 모든 예제의 경우 기본 XAML 네임스페이스가 `http://schemas.microsoft.com/winfx/2006/xaml/presentation`WPF 네임스페이스에 매핑됩니다. `xmlns:x` 특성은 XAML 언어 네임스페이스`http://schemas.microsoft.com/winfx/2006/xaml`를 매핑하는 추가적인 XAML 네임스페이스를 나타냅니다.

`xmlns`를 사용하여 이름 범위의 사용 및 매핑 범위를 정의하는 방식은 XML 1.0 사양과 일치합니다. XAML 이름 범위는 형식 확인 및 XAML 구문 분석에 적용할 경우 형식이 이름 범위의 요소를 지원하는 방법도 암시한다는 점에서 XML 이름 범위와는 다릅니다.

특성은 `xmlns` 각 XAML 파일의 루트 요소에만 필요합니다. `xmlns` 정의는 루트 요소의 모든 하위 요소에 적용됩니다(이 동작은 `xmlns`에 대한 XML 1.0 사양과 일치함). `xmlns` 특성은 루트 아래의 다른 요소에서도 허용되며, 정의 요소의 모든 하위 요소에 적용됩니다. 그러나 XAML 네임스페이스를 자주 정의하거나 재정의할 경우 XAML 태그 스타일을 읽기 어렵게 될 수 있습니다.

XAML 프로세서의 WPF 구현에는 WPF 코어 어셈블리에 대한 인식이 있는 인프라가 포함되어 있습니다. WPF 코어 어셈블리에는 기본 XAML 네임스페이스에 대한 WPF 매핑을 지원하는 형식이 포함되어 있는 것으로 알려져 있습니다. 이 어셈블리는 프로젝트 빌드 파일과 WPF 빌드 및 프로젝트 시스템에 속하는 구성을 통해 사용할 수 있습니다. 따라서 기본 XAML 네임스페이스를 기본값으로 `xmlns` 선언하는 것은 WPF 어셈블리에서 온 XAML 요소를 참조하는 데 필요한 모든 것입니다.

### <a name="the-x-prefix"></a>x: 접두사

앞의 루트 요소 예제에서는 접두사 `x:`를 사용하여 XAML 언어 구문을 지원하는 전용 XAML 네임스페이스인 XAML 네임스페이스 `http://schemas.microsoft.com/winfx/2006/xaml`를 매핑했습니다. 이 `x:` 접두사는 프로젝트, 예제 및 이 SDK 전체의 설명서에 대한 템플릿에서 이 XAML 네임스페이스를 매핑하는 데 사용됩니다. XAML 언어의 XAML 네임스페이스에는 XAML에서 자주 사용하는 여러 프로그래밍 구문이 포함되어 있습니다. 다음은 가장 많이 사용하게 될 `x:` 접두사 네임스페이스 프로그래밍 구문의 목록입니다.

- [x:Key](../xaml-services/xkey-directive.md): (또는 다른 프레임 <xref:System.Windows.ResourceDictionary> 워크에서 유사한 사전 개념)의 각 리소스에 대한 고유 키를 설정합니다. `x:Key`일반적인 WPF 앱의 태그에 표시되는 `x:` 사용량의 90%를 차지할 것입니다.

- [x:Class](../xaml-services/xclass-directive.md): XAML 페이지에 대한 코드 숨결을 제공하는 클래스의 CLR 네임스페이스 및 클래스 이름을 지정합니다. 이러한 클래스가 WPF 프로그래밍 모델에 대해 코드 숨김을 지원하도록 해야 하므로 리소스가 없는 경우에도 `x:`가 매핑된 것을 자주 보게 됩니다.

- [x:Name](../xaml-services/xname-directive.md): 개체 요소가 처리된 후 런타임 코드에 있는 인스턴스에 대한 런타임 개체 이름을 지정합니다. 일반적으로는 [x:Name](../xaml-services/xname-directive.md)에 대응하여 WPF에 정의된 속성을 자주 사용하게 됩니다. 이러한 속성은 특히 CLR 백업 속성에 매핑되므로 런타임 코드를 자주 사용하여 초기화된 XAML에서 명명된 요소를 찾는 앱 프로그래밍에 더 편리합니다. 이러한 속성이 가장 <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>일반적인 속성은 . 동일한 WPF 프레임워크 수준 <xref:System.Windows.FrameworkElement.Name%2A> 속성이 특정 형식에서 지원되지 않는 경우에도 [x:Name을](../xaml-services/xname-directive.md) 사용할 수 있습니다. 이는 특정 애니메이션 시나리오에서 볼 수 있는 상황입니다.

- [x:Static](../xaml-services/xstatic-markup-extension.md): XAML 호환 속성이 아닌 정적 값을 반환하는 참조를 사용할 수 있게 합니다.

- [x:Type](../xaml-services/xtype-markup-extension.md): 형식 <xref:System.Type> 이름을 기반으로 참조를 생성합니다. 이는 속성에 <xref:System.Type>기본 <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType><xref:System.Type> 문자열-변환이 있는 경우가 많지만 [x:Type](../xaml-services/xtype-markup-extension.md) 태그 확장 사용이 선택 사항인 경우와 같이 수행되는 특성을 지정하는 데 사용됩니다.

`x:` 접두사/XAML 네임스페이스에는 일반적으로는 사용되지 않는 추가적인 프로그래밍 구문이 있습니다. 자세한 내용은 [XAML 네임스페이스(x:) 언어 기능](../xaml-services/namespace-language-features.md)을 참조하세요.

## <a name="custom-prefixes-and-custom-types-in-xaml"></a>XAML의 사용자 지정 접두사 및 사용자 지정 형식

사용자 지정 어셈블리의 경우 또는 **프레젠테이션 코어,** 프레젠테이션 **프레임워크** 및 **WindowsBase의**WPF 코어 외부의 `xmlns` 어셈블리의 경우 사용자 지정 매핑의 일부로 어셈블리를 지정할 수 있습니다. 현재 시도 중인 XAML 사용을 지원하도록 해당 형식이 제대로 구현되어 있으면 XAML에서 해당 어셈블리의 형식을 참조할 수 있습니다.

다음은 XAML 태그에서 사용자 지정 접두사가 작동하는 방식의 기본 예입니다. 접두사는 `custom` 루트 요소 태그에 정의되며 앱에서 패키징되고 사용할 수 있는 특정 어셈블리에 매핑됩니다. 이 어셈블리에는 일반적인 XAML 사용뿐 아니라 WPF XAML 콘텐츠 모델의 이 특정 시점에 삽입될 수 있는 클래스 상속 사용을 지원하도록 구현된 `NumericUpDown` 형식이 들어 있습니다. 이 `NumericUpDown` 컨트롤 인스턴스는 접두사를 사용하여 개체 요소로 선언되므로 XAML 파서에서 형식이 포함된 XAML 네임스페이스 및 형식 정의가 들어 있는 지원 어셈블리가 있는 위치를 알 수 있습니다.

```xaml
<Page
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:custom="clr-namespace:NumericUpDownCustomControl;assembly=CustomLibrary"
    >
  <StackPanel Name="LayoutRoot">
    <custom:NumericUpDown Name="numericCtrl1" Width="100" Height="60"/>
...
  </StackPanel>
</Page>
```

XAML의 사용자 지정 형식에 대한 자세한 내용은 [WPF에 대한 XAML 및 사용자 지정 클래스](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)를 참조하세요.

어셈블리의 XML 네임스페이스 및 코드 네임스페이스가 어떻게 관련되는지에 대한 자세한 내용은 [XAML 네임스페이스 및 WPF XAML에 대한 네임스페이스 매핑을](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)참조하십시오.

## <a name="events-and-xaml-code-behind"></a>이벤트 및 XAML 코드 숨결

대부분의 WPF 앱은 XAML 태그와 코드 숨미는 앱으로 구성됩니다. 프로젝트 내에서 XAML은 `.xaml` 파일로 작성되고 Microsoft Visual Basic 또는 C#과 같은 CLR 언어는 코드 숨결 파일을 작성하는 데 사용됩니다. XAML 파일이 WPF 프로그래밍 및 애플리케이션 모델의 일부로 태그 컴파일될 때 XAML 파일에 대한 XAML 코드 숨김 파일의 위치는 네임스페이스와 클래스를 XAML 루트 요소의 `x:Class` 특성으로 지정하여 식별합니다.

지금까지의 예제에서 몇 개의 단추를 살펴보았지만 아직 논리적 동작이 연결된 단추는 없었습니다. 개체 요소에 대한 동작을 추가하기 위한 기본 응용 프로그램 수준 메커니즘은 element 클래스의 기존 이벤트를 사용하고 런타임에 해당 이벤트가 발생할 때 호출되는 해당 이벤트에 대한 특정 처리기를 작성하는 것입니다. 사용할 이벤트 이름과 처리기 이름은 태그에서 지정하고 처리기를 구현하는 코드는 코드 숨김에서 정의합니다.

[!code-xaml[XAMLOvwSupport#ButtonWithCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml#buttonwithcodebehind)]

[!code-csharp[XAMLOvwSupport#ButtonWithCodeBehindHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml.cs#buttonwithcodebehindhandler)]
[!code-vb[XAMLOvwSupport#ButtonWithCodeBehindHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XAMLOvwSupport/VisualBasic/Page1.xaml.vb#buttonwithcodebehindhandler)]

코드 숨김 파일은 CLR 네임스페이스 `ExampleNamespace`를 사용하며 `ExamplePage`를 해당 네임스페이스 안에서 partial 클래스로 선언합니다. 이는 태그 루트에 제공되는 `ExampleNamespace`.`ExamplePage`의 `x:Class` 특성 값과 유사합니다. WPF 태그 컴파일러는 루트 요소 형식에서 클래스를 파생하여 모든 컴파일된 XAML 파일에 대한 partial 클래스를 만듭니다. 동일한 부분 클래스를 정의하는 코드 숨결을 제공하면 결과 코드가 컴파일된 앱의 동일한 네임스페이스 및 클래스 내에서 결합됩니다.

WPF의 코드 숨김 프로그래밍에 대한 요구 사항에 대한 자세한 내용은 [WPF의 코드 숨김, 이벤트 처리기 및 부분 클래스 요구 사항을](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md#code-behind-event-handler-and-partial-class-requirements-in-wpf)참조하십시오.

별도의 코드 숨김 파일을 만들지 않으려면 코드를 XAML 파일 안에 인라인으로 넣을 수도 있습니다. 하지만 인라인 코드는 제한이 많은 기술입니다. 자세한 내용은 [WPF의 코드 숨미 및 XAML을](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)참조하십시오.

### <a name="routed-events"></a>라우팅된 이벤트

WPF의 기본인 특정 이벤트 기능은 라우트된 이벤트입니다. 라우트된 이벤트를 사용하면 요소가 다른 요소에 의해 발생한 이벤트를 처리할 수 있습니다. 단, 요소들이 트리 관계를 통해 연결되어 있어야 합니다. XAML 특성을 사용하여 이벤트 처리를 지정할 때 라우트된 이벤트는 클래스 멤버 테이블에서 해당 이벤트를 나열하지 않는 요소를 포함하여 모든 요소에서 수신되고 처리될 수 있습니다. 이렇게 하려면 소유 클래스 이름으로 이벤트 이름 특성을 정규화합니다. 예를 들어 진행 `StackPanel` `StackPanel`  /  `Button` 중인 예제의 부모는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> `Button.Click` `StackPanel` 개체 요소의 특성을 지정하여 처리기 이름을 특성 값으로 지정하여 자식 요소 단추의 이벤트에 대한 처리기를 등록할 수 있습니다. 자세한 내용은 [라우트된 이벤트 개요](../../framework/wpf/advanced/routed-events-overview.md)합니다.

## <a name="xaml-named-elements"></a>XAML 명명된 요소

기본적으로 XAML 개체 요소 처리를 통해 개체 그래프에서 만들어진 개체 인스턴스는 고유한 식별자 또는 개체 참조를 가지지 않습니다. 이와 달리 코드에서 생성자를 호출할 때는 나중에 코드에서 인스턴스를 참조할 수 있도록 대개는 생성자 결과를 사용하여 변수를 생성된 인스턴스로 설정합니다. 태그 정의를 통해 만들어진 개체에 대한 표준화된 액세스를 제공하기 위해 XAML은 [x:Name 특성](../xaml-services/xname-directive.md)을 정의합니다. 모든 개체 요소에 대해 `x:Name` 특성의 값을 설정할 수 있습니다. 코드 숨김에서 선택한 식별자는 구성된 인스턴스를 참조하는 인스턴스 변수와 같습니다. 모든 면에서 명명된 요소는 개체 인스턴스(해당 인스턴스의 이름 참조)인 것처럼 작동하며 코드 뒤에 는 명명된 요소를 참조하여 앱 내에서 런타임 상호 작용을 처리할 수 있습니다. 인스턴스와 변수 간의 이러한 연결은 WPF XAML 태그 컴파일러에 의해 수행되며 이 <xref:System.Windows.Markup.IComponentConnector.InitializeComponent%2A> 문서에서 자세히 설명하지 않는 기능 및 패턴이 보다 구체적으로 포함됩니다.

WPF 프레임워크 수준 XAML <xref:System.Windows.FrameworkElement.Name%2A> 요소는 XAML 정의 `x:Name` 특성과 동일한 속성을 상속합니다. 다른 특정 클래스에서도 `x:Name`에 해당하는 속성 수준 속성을 제공하며 이것은 일반적으로 `Name` 속성으로도 정의됩니다. 일반적으로, 멤버 테이블에서 선택한 요소/형식의 `Name` 속성을 찾을 수 없는 경우 `x:Name`을 대신 사용합니다. 이 `x:Name` 값은 특정 하위 시스템 또는 와 같은 <xref:System.Windows.FrameworkElement.FindName%2A>유틸리티 메서드에서 런타임에 사용할 수 있는 XAML 요소에 식별자를 제공합니다.

다음 예제는 <xref:System.Windows.FrameworkElement.Name%2A> 요소에 <xref:System.Windows.Controls.StackPanel> 설정합니다. 그런 <xref:System.Windows.Controls.Button> 다음 해당 <xref:System.Windows.Controls.StackPanel> 내부의 처리기는 에 의해 <xref:System.Windows.Controls.StackPanel> `buttonContainer` <xref:System.Windows.FrameworkElement.Name%2A>설정된 대로 의 인스턴스 참조를 참조합니다.

[!code-xaml[XAMLOvwSupport#NamedE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#namede)]
[!code-xaml[XAMLOvwSupport#NamedE2](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#namede2)]

[!code-csharp[XAMLOvwSupport#NameCode](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml.cs#namecode)]
[!code-vb[XAMLOvwSupport#NameCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XAMLOvwSupport/VisualBasic/Page1.xaml.vb#namecode)]

변수와 마찬가지로 인스턴스의 XAML 이름도 범위라는 개념으로 제어됩니다. 즉, 예측 가능한 특정 범위 내에서 이름이 고유해야 합니다. 페이지를 정의하는 기본 태그는 해당 페이지의 루트 요소인 XAML 이름 범위 경계를 사용하여 하나의 고유한 XAML 이름 범위를 지정합니다. 그러나 다른 태그 원본은 스타일 내의 스타일이나 템플릿과 같이 런타임에 페이지와 상호 작용할 수 있으며 이러한 태그 원본에는 페이지의 XAML 네임스코프와 반드시 연결되지 않는 자체 XAML 네임스코프가 있는 경우가 많습니다. 및 XAML 네임스코프에 `x:Name` 대한 <xref:System.Windows.FrameworkElement.Name%2A>자세한 내용은 [" x:Name 지시문](../xaml-services/xname-directive.md)또는 [WPF XAML 내명 경을](../../framework/wpf/advanced/wpf-xaml-namescopes.md)참조하십시오.

## <a name="attached-properties-and-attached-events"></a>첨부된 속성 및 첨부된 이벤트

XAML에서는 속성이나 이벤트가 설정되는 요소의 형식 정의에 존재하는지 여부에 관계없이 임의의 요소에 특정 속성이나 이벤트를 지정할 수 있도록 하는 언어 기능을 지정합니다. 이 기능의 속성 버전을 연결된 속성이라고 하고 이벤트 버전을 연결된 이벤트라고 합니다. 개념적으로 볼 때 연결된 속성과 연결된 이벤트는 모든 XAML 요소/개체 인스턴스에 설정할 수 있는 전역 멤버로 생각할 수 있습니다. 그러나 해당 요소/클래스 또는 보다 큰 인프라는 연결된 값에 대해 지원 속성 저장소를 지원해야 합니다.

XAML의 연결된 속성은 일반적으로 특성 구문을 통해 사용합니다. 특성 구문에서 양식에서 `ownerType.propertyName`연결된 속성을 지정합니다.

피상적으로 이것은 속성 요소 사용과 유사하지만 이 `ownerType` 경우 지정한 속성은 항상 연결된 속성이 설정되는 개체 요소와 다른 형식입니다. `ownerType`는 연결된 속성 값을 얻거나 설정하기 위해 XAML 프로세서에 필요한 접근자 메서드를 제공하는 형식입니다.

연결된 속성에 대한 가장 일반적인 시나리오는 자식 요소가 부모 요소에 속성 값을 보고하도록 하는 것입니다.

다음 예제에서는 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> 연결된 속성을 보여 줍니다. 클래스는 <xref:System.Windows.Controls.DockPanel> 에 대한 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> 접근자 정의를 내므로 연결된 속성을 소유합니다. 클래스에는 <xref:System.Windows.Controls.DockPanel> 자식 요소를 이기하고 각 요소를 에서 설정된 값에 대해 특별히 확인하는 논리도 포함되어 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>있습니다. 값이 발견되면 레이아웃 도중 이 값을 사용하여 자식 요소를 배치합니다. <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> 연결된 속성과 이 위치 지정 기능을 사용하는 것은 사실 클래스에 <xref:System.Windows.Controls.DockPanel> 대한 동기 부여 시나리오입니다.

[!code-xaml[XAMLOvwSupport#DockAP](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#dockap)]

WPF에서 연결된 속성의 대부분 또는 전부는 종속성 속성으로도 구현됩니다. 자세한 내용은 [연결된 속성 개요](../../framework/wpf/advanced/attached-properties-overview.md)를 참조하세요.

연결된 이벤트는 유사한 `ownerType.eventName` 형태의 특성 구문을 사용합니다. 연결되지 않은 이벤트와 마찬가지로 XAML의 연결된 이벤트에 대한 특성 값은 이벤트가 요소에서 처리될 때 호출되는 처리기 메서드의 이름을 지정합니다. WPF XAML에서 연결된 이벤트를 사용하는 것은 상대적으로 일반적이지 않습니다. 자세한 내용은 [연결된 이벤트 개요](../../framework/wpf/advanced/attached-events-overview.md)를 참조하세요.

## <a name="base-types-and-xaml"></a>기본 유형 및 XAML

기본 WPF XAML 및 XAML 네임스페이스는 XAML의 태그 요소 외에 CLR 개체에 해당하는 형식의 컬렉션입니다. 하지만 모든 클래스를 요소에 매핑할 수 있는 것은 아닙니다. 와 같은 <xref:System.Windows.Controls.Primitives.ButtonBase>추상 클래스 및 특정 비추상 기본 클래스는 CLR 개체 모델의 상속에 사용됩니다. 각각의 구체적인 XAML 요소는 계층 구조의 일부 기본 클래스에서 멤버를 상속하기 때문에 추상 클래스를 포함한 기본 클래스는 여전히 XAML 개발에 있어서 중요합니다. 이러한 멤버에는 대개 요소에서 특성으로 설정할 수 있는 속성 또는 처리될 수 있는 이벤트가 포함됩니다. <xref:System.Windows.FrameworkElement>는 WPF 프레임워크 수준에서 WPF의 구체적인 기본 UI 클래스입니다. UI를 디자인할 때 는 모든 에서 파생되는 다양한 모양, 패널, <xref:System.Windows.FrameworkElement>데코레이터 또는 컨트롤 클래스를 사용합니다. 관련 기본 클래스는 <xref:System.Windows.FrameworkContentElement>에서 API를 의도적으로 미러하는 API를 사용하여 흐름 레이아웃 프레젠테이션에 <xref:System.Windows.FrameworkElement>잘 작동하는 문서 지향 요소를 지원합니다. 요소 수준에서 특성과 CLR 개체 모델의 조합은 특정 XAML 요소 및 기본 형식에 관계없이 대부분의 구체적인 XAML 요소에 설정할 수 있는 공통 속성 집합을 제공합니다.

## <a name="xaml-security"></a>XAML 보안

XAML은 개체 인스턴스화 및 실행을 직접적으로 나타내는 태그 언어입니다. 따라서 XAML에서 만든 요소에는 생성된 해당 코드가 수행하는 것과 마찬가지로 시스템 리소스(예: 네트워크 액세스, 파일 시스템 IO)와 상호 작용하는 동일한 기능이 있습니다. 완전히 신뢰할 수 있는 앱에 로드된 XAML은 호스팅 앱과 동일한 시스템 리소스에 액세스할 수 있습니다.

### <a name="code-access-security-cas-in-wpf"></a>WPF의 코드 액세스 보안(CAS)

**이 섹션은 .NET 프레임워크에만 적용됩니다. .NET 코어에 대한 WPF는 CAS를 지원하지 않습니다. 자세한 내용은 [코드 액세스 보안 차이점을](../migration/differences-from-net-framework.md#code-access-security)참조하십시오.**

.NET 프레임워크용 WPF는 CAS(코드 액세스 보안)를 지원합니다. 즉, 인터넷 영역에서 실행 중인 WPF 콘텐츠가 실행 권한을 줄입니다. "느슨한 XAML"(XAML 뷰어에 의해 로드 시 해석된 비컴파일된 XAML 페이지) 및 XBAP는 일반적으로 이 인터넷 영역에서 실행되며 동일한 권한 집합을 사용합니다. 하지만 완전히 신뢰할 수 있는 애플리케이션으로 로드된 XAML은 시스템 리소스에 대해 호스팅 애플리케이션과 동일한 액세스 권한을 가집니다. 자세한 내용은 [WPF 부분 신뢰 보안](../../framework/wpf/wpf-partial-trust-security.md)을 참조하세요.

## <a name="loading-xaml-from-code"></a>코드에서 XAML 로드

XAML을 사용하여 전체 UI를 정의할 수 있지만 XAML에서 UI의 일부만 정의하는 것이 적합할 때도 있습니다. 이 기능을 통해 부분 사용자 지정, 정보의 로컬 스토리지, XAML을 사용한 비즈니스 개체 제공을 비롯한 가능한 다양한 시나리오를 지원할 수 있습니다. 이러한 시나리오의 핵심은 <xref:System.Windows.Markup.XamlReader> 클래스와 <xref:System.Windows.Markup.XamlReader.Load%2A> 해당 메서드입니다. 입력은 XAML 파일이며 출력은 해당 태그에서 만들어진 개체의 전체 런타임 트리를 나타내는 개체입니다. 그런 다음 앱에 이미 있는 다른 개체의 속성으로 개체를 삽입할 수 있습니다. 속성이 최종 표시 기능을 가지고 있고 실행 엔진에 새 콘텐츠가 앱에 추가되었음을 알리는 콘텐츠 모델의 적절한 속성인 경우 XAML에서 로드하여 실행 중인 앱의 내용을 쉽게 수정할 수 있습니다. .NET Framework의 경우 이 기능은 일반적으로 파일을 실행할 때 응용 프로그램에 파일을 로드하는 것이 명백히 보안에 영향을 미치기 때문에 완전 신뢰 응용 프로그램에서만 사용할 수 있습니다.

## <a name="see-also"></a>참조

- [XAML 구문 정보](../../framework/wpf/advanced/xaml-syntax-in-detail.md)
- [WPF에 대한 XAML 및 사용자 지정 클래스](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [XAML 네임스페이스(x:) 언어 기능](../xaml-services/namespace-language-features.md)
- [WPF XAML 확장](../../framework/wpf/advanced/wpf-xaml-extensions.md)
- [기본 요소 개요](../../framework/wpf/advanced/base-elements-overview.md)
- [WPF의 트리](../../framework/wpf/advanced/trees-in-wpf.md)

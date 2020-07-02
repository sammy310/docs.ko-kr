---
title: 데이터 템플릿 개요
description: Windows Presentation Foundation (WPF)에서 데이터의 표시를 정의 하는 데이터 템플릿 모델 유연성을 탐색 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], templates
- binding data [WPF], templates
- templates [WPF], data
- data templates [WPF]
ms.assetid: 0f4d9f8c-0230-4013-bd7b-e8e7fed01b4a
ms.openlocfilehash: 0226085a82cf97ea799a5a2d38e879b239d9b52a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619652"
---
# <a name="data-templating-overview"></a>데이터 템플릿 개요
WPF 데이터 템플릿 모델을 사용하면 데이터 표시를 매우 유연하게 정의할 수 있습니다. WPF 컨트롤에는 데이터 표시의 사용자 지정을 지원하는 기본 제공 기능이 있습니다. 이 항목에서는 먼저를 정의한 <xref:System.Windows.DataTemplate> 다음 사용자 지정 논리를 기반으로 템플릿 선택, 계층적 데이터 표시에 대 한 지원 등의 기타 데이터 템플릿 기능을 소개 하는 방법을 보여 줍니다.

<a name="Prerequisites"></a>
## <a name="prerequisites"></a>전제 조건
 이 항목에서는 데이터 템플릿 기능을 집중적으로 살펴보고 데이터 바인딩 개념은 소개하지 않습니다. 기본 데이터 바인딩 개념에 대한 자세한 내용은 [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)를 참조하세요.

 <xref:System.Windows.DataTemplate>는 데이터의 표시에 대 한 것 이며 WPF 스타일 지정 및 템플릿 모델에서 제공 하는 다양 한 기능 중 하나입니다. 을 사용 하 여 컨트롤에 대 한 속성을 설정 하는 방법과 같은 WPF 스타일 지정 및 템플릿 모델에 대 한 소개는 <xref:System.Windows.Style> [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md) 항목을 참조 하세요.

 또한, 및와 같은 개체를 다시 사용할 수 있도록 하는 것을 이해 하는 것이 중요 `Resources` <xref:System.Windows.Style> <xref:System.Windows.DataTemplate> 합니다. 리소스에 대한 자세한 내용은 [XAML 리소스](../../../desktop-wpf/fundamentals/xaml-resources-define.md)를 참조하세요.

<a name="DataTemplating_Basic"></a>
## <a name="data-templating-basics"></a>데이터 템플릿 기본 사항

 가 중요 한 이유를 보여 주기 위해 <xref:System.Windows.DataTemplate> 데이터 바인딩 예제를 살펴보겠습니다. 이 예제에서는 <xref:System.Windows.Controls.ListBox> 개체 목록에 바인딩된가 있습니다 `Task` . 각 `Task` 개체에는 `TaskName`(string), `Description`(string), `Priority`(int)와 함께 값이 `Home` 및 `Work`인 `Enum`을 나타내는 `TaskType` 형식 속성이 있습니다.

 [!code-xaml[DataTemplatingIntro_snip#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#resources)]
[!code-xaml[DataTemplatingIntro_snip#UI1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui1)]
[!code-xaml[DataTemplatingIntro_snip#UI2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui2)]

<a name="without_a_datatemplate"></a>
### <a name="without-a-datatemplate"></a>DataTemplate 사용 안 함
 가 없으면 <xref:System.Windows.DataTemplate> 현재는 <xref:System.Windows.Controls.ListBox> 다음과 같습니다.

 ![데이터 템플릿 샘플 스크린샷](./media/datatemplatingintro-fig1.png "DataTemplatingIntro_fig1")

 특정 지침이 없으면 <xref:System.Windows.Controls.ListBox> 기본적으로 `ToString` 컬렉션의 개체를 표시 하려고 할 때가 호출 됩니다. 따라서 개체가 메서드를 재정의 하는 경우 `Task` `ToString` 는 <xref:System.Windows.Controls.ListBox> 기본 컬렉션에 있는 각 소스 개체의 문자열 표현을 표시 합니다.

 예를 들어 `Task` 클래스가 이 방식으로 `ToString` 메서드를 재정의하면 `name`은 `TaskName` 속성에 대한 필드입니다.

 [!code-csharp[DataTemplatingIntro_snip#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Data.cs#tostring)]
 [!code-vb[DataTemplatingIntro_snip#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/data.vb#tostring)]

 그러면는 <xref:System.Windows.Controls.ListBox> 다음과 같습니다.

 ![데이터 템플릿 샘플 스크린샷](./media/datatemplatingintro-fig2.png "DataTemplatingIntro_fig2")

 하지만 이 방법은 제한적이고 유연하지 않습니다. 또한 XML 데이터에 바인딩하는 경우에는를 재정의할 수 없습니다 `ToString` .

<a name="defining_simple_datatemplate"></a>
### <a name="defining-a-simple-datatemplate"></a>간단한 DataTemplate 정의
 이 솔루션은을 정의 하는 것입니다 <xref:System.Windows.DataTemplate> . 이 작업을 수행 하는 한 가지 방법은의 속성을로 설정 하는 것입니다 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> <xref:System.Windows.Controls.ListBox> <xref:System.Windows.DataTemplate> . 에서 지정 하는 항목 <xref:System.Windows.DataTemplate> 은 데이터 개체의 시각적 구조가 됩니다. 다음은 <xref:System.Windows.DataTemplate> 매우 간단 합니다. 각 항목이 내에 세 개의 요소로 표시 되는 지침을 제공 <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Controls.StackPanel> 합니다. 각 <xref:System.Windows.Controls.TextBlock> 요소는 클래스의 속성에 바인딩됩니다 `Task` .

 [!code-xaml[DataTemplatingIntro_snip#Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#inline)]

 이 항목의 예제에 대 한 기본 데이터는 CLR 개체의 컬렉션입니다. XML 데이터에 바인딩하는 경우 기본 개념은 동일 하지만 약간의 구문상 차이가 있습니다. 예를 들어를로 설정 하는 대신를 `Path=TaskName` <xref:System.Windows.Data.Binding.XPath%2A> 로 설정 `@TaskName` `TaskName` 합니다 .이 XML 노드의 특성인 경우입니다.

 이제 <xref:System.Windows.Controls.ListBox> 는 다음과 같습니다.

 ![데이터 템플릿 샘플 스크린샷](./media/datatemplatingintro-fig3.png "DataTemplatingIntro_fig3")

<a name="defining_datatemplate_as_a_resource"></a>
### <a name="creating-the-datatemplate-as-a-resource"></a>DataTemplate을 리소스로 만들기
 위의 예제에서는 인라인을 정의 했습니다 <xref:System.Windows.DataTemplate> . 더 일반적인 방법은 다음 예제와 같이 재사용 가능한 개체가 될 수 있도록 리소스 섹션에서 데이터 템플릿을 정의하는 것입니다.

 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]
[!code-xaml[DataTemplatingIntro_snip#AsResource](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#asresource)]
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]

 이제 다음 예제와 같이 `myTaskTemplate`을 리소스로 사용할 수 있습니다.

 [!code-xaml[DataTemplatingIntro_snip#MyTaskTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#mytasktemplate)]

 `myTaskTemplate`는 리소스 이므로 이제 형식을 사용 하는 속성을 가진 다른 컨트롤에서 사용할 수 있습니다 <xref:System.Windows.DataTemplate> . 위와 같이 개체의 경우에는 <xref:System.Windows.Controls.ItemsControl> <xref:System.Windows.Controls.ListBox> 속성입니다 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> . 개체의 경우 <xref:System.Windows.Controls.ContentControl> <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 속성입니다.

<a name="Styling_DataType"></a>
### <a name="the-datatype-property"></a>DataType 속성
 클래스에는 <xref:System.Windows.DataTemplate> <xref:System.Windows.DataTemplate.DataType%2A> <xref:System.Windows.Style.TargetType%2A> 클래스의 속성과 매우 유사한 속성이 있습니다 <xref:System.Windows.Style> . 따라서 위의 예제에서에 대해를 지정 하는 대신 `x:Key` <xref:System.Windows.DataTemplate> 다음을 수행할 수 있습니다.

 [!code-xaml[DataTemplatingIntro_snip#DataType](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#datatype)]

 이는 <xref:System.Windows.DataTemplate> 모든 개체에 자동으로 적용 `Task` 됩니다. 이 경우 `x:Key`는 암시적으로 설정됩니다. 따라서이 값을 할당 하는 경우 <xref:System.Windows.DataTemplate> `x:Key` 암시적인를 재정의 하 고가 `x:Key` <xref:System.Windows.DataTemplate> 자동으로 적용 되지 않습니다.

 <xref:System.Windows.Controls.ContentControl>개체의 컬렉션에를 바인딩하는 경우 `Task` 는 위의을 <xref:System.Windows.Controls.ContentControl> 자동으로 사용 하지 않습니다 <xref:System.Windows.DataTemplate> . 이는에 대 한 바인딩에서 <xref:System.Windows.Controls.ContentControl> 전체 컬렉션 또는 개별 개체를 바인딩할 지 여부를 구분 하기 위해 더 많은 정보를 요구 하기 때문입니다. 에서 <xref:System.Windows.Controls.ContentControl> 특정 형식의 선택 항목을 추적 하는 경우 <xref:System.Windows.Controls.ItemsControl> <xref:System.Windows.Data.Binding.Path%2A> <xref:System.Windows.Controls.ContentControl> `/` 현재 항목에 관심이 있음을 나타내기 위해 바인딩의 속성을 ""로 설정할 수 있습니다. 예제를 보려면 [선택에 따라 수집 및 표시 정보에 바인딩](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)을 참조하세요. 그렇지 않으면 속성을 설정 하 여을 명시적으로 지정 해야 합니다 <xref:System.Windows.DataTemplate> <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> .

 <xref:System.Windows.DataTemplate.DataType%2A>속성은 <xref:System.Windows.Data.CompositeCollection> 데이터 개체의 형식이 서로 다른 경우에 특히 유용 합니다. 예제를 보려면 [CompositeCollection 구현](how-to-implement-a-compositecollection.md)을 참조하세요.

<a name="adding_more_to_datatemplate"></a>
## <a name="adding-more-to-the-datatemplate"></a>DataTemplate에 자세히 추가
 현재 데이터에는 필요한 정보가 함께 표시되지만 분명히 개선의 여지가 있습니다. <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Grid> 및 표시 되는 데이터를 설명 하는 몇 가지 요소를 추가 하 여 프레젠테이션을 살펴보겠습니다 <xref:System.Windows.Controls.TextBlock> .

 [!code-xaml[DataTemplatingIntro#AddingMore](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore)]
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]

 다음 스크린샷은 <xref:System.Windows.Controls.ListBox> 이 수정 된을 보여 줍니다 <xref:System.Windows.DataTemplate> .

 ![데이터 템플릿 샘플 스크린샷](./media/datatemplatingintro-fig4.png "DataTemplatingIntro_fig4")

 에서 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> 을로 설정 <xref:System.Windows.HorizontalAlignment.Stretch> 하 여 <xref:System.Windows.Controls.ListBox> 항목의 너비가 전체 공간을 차지 하는지 확인할 수 있습니다.

 [!code-xaml[DataTemplatingIntro_snip#Stretch](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#stretch)]

 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>속성이로 설정 된 경우 <xref:System.Windows.HorizontalAlignment.Stretch> 이제는 <xref:System.Windows.Controls.ListBox> 다음과 같습니다.

 ![데이터 템플릿 샘플 스크린샷](./media/datatemplatingintro-fig5.png "DataTemplatingIntro_fig5")

<a name="DataTrigger_to_Apply_Property_Values"></a>
### <a name="use-datatriggers-to-apply-property-values"></a>DataTrigger를 사용하여 속성 값 적용
 현재 표시로는 `Task`가 홈 작업 또는 사무실 작업인지 알 수 없습니다. 다시 말하지만, `Task` 개체에는 값이 `Home` 및 `Work`인 열거형을 나타내는 `TaskType` 형식의 `TaskType` 속성이 있습니다.

 다음 예제에서는 <xref:System.Windows.DataTrigger> <xref:System.Windows.Controls.Border.BorderBrush%2A> `border` `Yellow` 속성이 인 경우 요소의을로 설정 합니다 `TaskType` `TaskType.Home` .

 [!code-xaml[DataTemplatingIntro#DT](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#dt)]
[!code-xaml[DataTemplatingIntro#DataTrigger](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#datatrigger)]
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]

 이제 애플리케이션은 다음과 같이 표시됩니다. 홈 작업에는 노란색 테두리가 표시되고 사무실 작업에는 바다색 테두리가 표시됩니다.

 ![데이터 템플릿 샘플 스크린샷](./media/datatemplatingintro-fig6.png "DataTemplatingIntro_fig6")

 이 예제에서는를 사용 하 여 <xref:System.Windows.DataTrigger> <xref:System.Windows.Setter> 속성 값을 설정 합니다. 트리거 클래스에는 <xref:System.Windows.TriggerBase.EnterActions%2A> <xref:System.Windows.TriggerBase.ExitActions%2A> 애니메이션과 같은 작업 집합을 시작할 수 있는 및 속성도 있습니다. 또한 <xref:System.Windows.MultiDataTrigger> 여러 데이터 바인딩된 속성 값에 따라 변경 내용을 적용할 수 있는 클래스도 있습니다.

 동일한 효과를 얻는 또 다른 방법은 속성 <xref:System.Windows.Controls.Border.BorderBrush%2A> 을 속성에 바인딩하고 `TaskType` 값 변환기를 사용 하 여 값을 기준으로 색을 반환 하는 것입니다 `TaskType` . 변환기를 사용하여 위 효과를 만드는 방법이 성능 면에서 약간 더 효율적입니다. 또한 자체 변환기를 만들면 자체 논리를 제공할 수 있으므로 더 유연하게 작업할 수 있습니다. 결국 선택하는 방법은 시나리오와 기본 설정에 따라 결정됩니다. 변환기를 작성 하는 방법에 대 한 자세한 내용은을 참조 하십시오 <xref:System.Windows.Data.IValueConverter> .

<a name="what_belongs_in_datatemplate"></a>
### <a name="what-belongs-in-a-datatemplate"></a>DataTemplate은 무엇으로 구성되나요?

이전 예제에서는 속성을 사용 하 여 내에 트리거를 배치 했습니다 <xref:System.Windows.DataTemplate> <xref:System.Windows.DataTemplate.Triggers%2A?displayProperty=nameWithType> . <xref:System.Windows.Setter>트리거의는 내에 있는 요소 (요소)의 속성 값을 설정 합니다 <xref:System.Windows.Controls.Border> <xref:System.Windows.DataTemplate> . 그러나가 관련 된 속성이 `Setters` 현재 내에 있는 요소의 속성이 아닌 경우에는 <xref:System.Windows.DataTemplate> 클래스에 대 한를 사용 하 여 속성을 설정 하는 것이 더 적합할 수 있습니다 <xref:System.Windows.Style> <xref:System.Windows.Controls.ListBoxItem> (바인딩할 컨트롤이 인 경우 <xref:System.Windows.Controls.ListBox> ). 예를 들어 <xref:System.Windows.Trigger> <xref:System.Windows.UIElement.Opacity%2A> 마우스로 항목을 가리킬 때 항목의 값에 애니메이션 효과를 주려면 스타일 내에서 트리거를 정의 합니다 <xref:System.Windows.Controls.ListBoxItem> . 예제를 보려면 [Introduction to Styling and Templating Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(스타일 지정 및 템플릿 샘플 소개)을 참조하세요.

 일반적으로는 <xref:System.Windows.DataTemplate> 생성 된 각에 적용 됩니다 <xref:System.Windows.Controls.ListBoxItem> . 실제로 적용 되는 방법과 위치에 대 한 자세한 내용은 페이지를 참조 하십시오 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> . 는 <xref:System.Windows.DataTemplate> 데이터 개체의 표시 및 모양에만 관심이 있습니다. 대부분의 경우 항목을 선택 하거나 항목을 레이아웃 하는 방법 등의 다른 모든 측면은 <xref:System.Windows.Controls.ListBox> 의 정의에 속하지 않습니다 <xref:System.Windows.DataTemplate> . 예제를 보려면 [ItemsControl 스타일 지정 및 템플릿 만들기](#DataTemplating_ItemsControl) 섹션을 참조하세요.

<a name="Styling_StyleSelection"></a>
## <a name="choosing-a-datatemplate-based-on-properties-of-the-data-object"></a>데이터 개체의 속성에 따라 DataTemplate 선택
 [DataType 속성](#Styling_DataType) 섹션에서 다양한 데이터 개체에 대한 서로 다른 데이터 템플릿을 정의할 수 있음을 설명했습니다. 이는 다양 한 형식의 항목이 나 다른 형식의 항목이 있는 경우 특히 유용 <xref:System.Windows.Data.CompositeCollection> 합니다. [Datatrigger를 사용 하 여 속성 값 적용](#DataTrigger_to_Apply_Property_Values) 섹션에서 동일한 유형의 데이터 개체 컬렉션이 있는 경우를 만든 <xref:System.Windows.DataTemplate> 다음 트리거를 사용 하 여 각 데이터 개체의 속성 값에 따라 변경 내용을 적용할 수 있습니다. 그러나 트리거를 사용하여 속성 값을 적용하거나 애니메이션을 시작할 수 있지만 트리거는 데이터 개체의 구조를 재구성할 수 있는 유연성이 없습니다. 일부 시나리오에서는 <xref:System.Windows.DataTemplate> 유형이 같지만 속성은 다른 데이터 개체에 대해 다른를 만들어야 할 수 있습니다.

 예를 들어 `Task` 개체의 `Priority` 값이 `1`일 경우 스스로 주의할 수 있도록 완전히 다른 모양을 지정해야 할 수 있습니다. 이 경우 <xref:System.Windows.DataTemplate> 우선 순위가 높은 개체를 표시 하기 위한를 만듭니다 `Task` . 리소스 섹션에 다음을 추가 해 보겠습니다 <xref:System.Windows.DataTemplate> .

 [!code-xaml[DataTemplatingIntro_snip#ImportantTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#importanttemplate)]

이 예제에서는 [DataTemplate](xref:System.Windows.FrameworkTemplate.Resources%2A) 속성을 사용 합니다. 해당 섹션에 정의 된 리소스는 내의 요소에서 공유 됩니다 <xref:System.Windows.DataTemplate> .

 선택 하는 논리를 제공 <xref:System.Windows.DataTemplate> 에 따라 사용 하는 `Priority` 값 데이터 개체의 서브 클래스를 만든 <xref:System.Windows.Controls.DataTemplateSelector> 재정의 <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> 메서드. 다음 예제에서는 <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> 의 값을 기반으로 적절 한 템플릿을 반환 하는 논리를 제공 하는 메서드는 `Priority` 속성입니다. 반환할 템플릿은 상위의 리소스에 위치한 <xref:System.Windows.Window> 요소입니다.

 [!code-csharp[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/TaskListDataTemplateSelector.cs#dtsclass)]
 [!code-vb[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/tasklistdatatemplateselector.vb#dtsclass)]

 그런 다음 `TaskListDataTemplateSelector`를 리소스로 선언할 수 있습니다.

 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]
[!code-xaml[DataTemplatingIntro_snip#DTS](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#dts)]
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]

 템플릿 선택기 리소스를 사용 하려면 할당에 <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> 의 속성을 <xref:System.Windows.Controls.ListBox>. <xref:System.Windows.Controls.ListBox> 호출을 <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> 메서드의 `TaskListDataTemplateSelector` 각 내부 컬렉션에서 항목에 대 한 합니다. 이 호출은 데이터 개체를 항목 매개 변수로 전달합니다. <xref:System.Windows.DataTemplate> 에서 반환 하는 메서드가 데이터 개체에 적용 됩니다.

 [!code-xaml[DataTemplatingIntro_snip#ItemTemplateSelector](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemtemplateselector)]

 템플릿 선택기를 사용 하면 이제이 다음과 같이 <xref:System.Windows.Controls.ListBox> 표시 됩니다.

 ![데이터 템플릿 샘플 스크린샷](./media/datatemplatingintro-fig7.png "DataTemplatingIntro_fig7")

이것으로 이 예제에 대한 설명을 마칩니다. 전체 샘플을 보려면 [Introduction to Data Templating Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/DataTemplatingIntro)(데이터 템플릿 샘플 소개)을 참조하세요.

<a name="DataTemplating_ItemsControl"></a>
## <a name="styling-and-templating-an-itemscontrol"></a>ItemsControl 스타일 지정 및 템플릿 만들기
 <xref:System.Windows.Controls.ItemsControl>가와 함께 사용할 수 있는 유일한 컨트롤 형식이 아닌 경우에도를 <xref:System.Windows.DataTemplate> 컬렉션에 바인딩하는 것이 매우 일반적인 시나리오입니다 <xref:System.Windows.Controls.ItemsControl> . [DataTemplate](#what_belongs_in_datatemplate) 섹션에서의 정의는 데이터 표시에만 관심이 있다고 설명 했습니다 <xref:System.Windows.DataTemplate> . 를 사용 하는 데 적합 하지 않은 것을 확인 하려면에서 <xref:System.Windows.DataTemplate> 제공 하는 다양 한 스타일 및 템플릿 속성을 이해 하는 것이 중요 합니다 <xref:System.Windows.Controls.ItemsControl> . 다음 예제는 이러한 각 속성의 기능을 설명하도록 디자인되어 있습니다. <xref:System.Windows.Controls.ItemsControl>이 예제의는 `Tasks` 이전 예제와 동일한 컬렉션에 바인딩됩니다. 설명을 위해 이 예제의 스타일 및 템플릿은 모두 인라인으로 선언됩니다.

 [!code-xaml[DataTemplatingIntro_snip#ItemsControlProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemscontrolproperties)]

 렌더링될 때 예제의 스크린샷은 다음과 같습니다.

 ![ItemsControl 예제 스크린샷](./media/databinding-itemscontrolproperties.png "DataBinding_ItemsControlProperties")

 를 사용 하는 대신을 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 사용할 수 있습니다 <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> . 예제를 보려면 이전 섹션을 참조하세요. 마찬가지로를 사용 하는 대신를 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 사용 하는 옵션이 있습니다 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyleSelector%2A> .

 여기에 표시 되지 않은의 다른 두 가지 스타일 관련 속성 <xref:System.Windows.Controls.ItemsControl> 은 <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> 및 <xref:System.Windows.Controls.ItemsControl.GroupStyleSelector%2A> 입니다.

<a name="DataTemplating_HeirarchicalDataTemplate"></a>
## <a name="support-for-hierarchical-data"></a>계층적 데이터 지원
 지금까지는 단일 컬렉션에 바인딩하고 단일 컬렉션을 표시하는 방법만 살펴봤습니다. 경우에 따라 다른 컬렉션이 포함된 컬렉션이 있을 수 있습니다. <xref:System.Windows.HierarchicalDataTemplate>클래스는 <xref:System.Windows.Controls.HeaderedItemsControl> 이러한 데이터를 표시 하기 위해 형식과 함께 사용 하도록 설계 되었습니다. 다음 예제에서 `ListLeagueList`는 `League` 개체 목록입니다. 각 `League` 개체에는 `Name` 및 `Division` 개체 컬렉션이 포함됩니다. 각 `Division` 에는 `Name` 및 `Team` 개체 컬렉션이 포함되고 각 `Team` 개체에는 `Name`이 포함됩니다.

 [!code-xaml[HierarchicalDataTemplateSnippet#HDT](~/samples/snippets/csharp/VS_Snippets_Wpf/HierarchicalDataTemplateSnippet/CS/window1.xaml#hdt)]

 이 예제에서는 사용 하 여 보여 줍니다 <xref:System.Windows.HierarchicalDataTemplate>, 다른 목록이 포함 된 목록 데이터를 쉽게 표시할 수 있습니다. 예제 스크린샷은 다음과 같습니다.

 ![HierarchicalDataTemplate 샘플 스크린 샷](./media/databinding-hierarchicaldatatemplate.png "DataBinding_HierarchicalDataTemplate")

## <a name="see-also"></a>참고 항목

- [데이터 바인딩](../advanced/optimizing-performance-data-binding.md)
- [DataTemplate에서 생성된 요소 찾기](how-to-find-datatemplate-generated-elements.md)
- [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)
- [GridView 열 머리글 스타일 및 템플릿 개요](../controls/gridview-column-header-styles-and-templates-overview.md)

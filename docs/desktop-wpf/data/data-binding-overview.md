---
title: 데이터 바인딩 개요
description: .NET Core용 Windows Presentation Foundation에서 프로젝트에 추가할 수 있는 다양한 데이터 소스에 관해 알아봅니다. 데이터 소스를 XAML 요소에 바인딩하여 동적 앱을 만들 수 있습니다.
author: adegeo
ms.date: 09/19/2019
ms.author: adegeo
dev_langs:
- csharp
- vb
ms.openlocfilehash: 3c9615d7d79b5da1c180bb505f5f37b99aeae775
ms.sourcegitcommit: e0803b8975d3eb12e735a5d07637020dd6dac5ef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2020
ms.locfileid: "89271999"
---
# <a name="data-binding-overview-in-wpf"></a>WPF의 데이터 바인딩 개요

WPF(Windows Presentation Foundation)의 데이터 바인딩은 앱이 데이터를 제공하고 상호 작용할 수 있는 간단하고 일관된 방법을 제공합니다. 다양한 데이터 소스에서 .NET 개체 및 XML의 형식으로 데이터에 요소를 바인딩할 수 있습니다. 모든 <xref:System.Windows.Controls.ContentControl>(예: <xref:System.Windows.Controls.Button>) 및 모든 <xref:System.Windows.Controls.ItemsControl>(예: <xref:System.Windows.Controls.ListBox> 및 <xref:System.Windows.Controls.ListView>)에는 단일 데이터 항목이나 데이터 항목 수집의 스타일을 유연하게 지정할 수 있는 기본 제공 기능이 있습니다. 데이터를 기반으로 정렬, 필터 및 그룹 보기를 생성할 수 있습니다.

WPF의 데이터 바인딩 기능은 광범위한 속성을 통한 기본적인 데이터 바인딩 지원, 데이터의 유연한 UI 표현 및 UI와 비즈니스 논리의 분명한 분리와 같은 기존 모델에 비해 여러 가지 이점이 있습니다.

이 문서에서는 먼저 WPF 데이터 바인딩의 기초 개념을 살펴본 다음, <xref:System.Windows.Data.Binding> 클래스 및 기타 데이터 바인딩 기능을 사용하는 방법을 다룹니다.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="what-is-data-binding"></a>데이터 바인딩이란?

데이터 바인딩은 앱 UI와 해당 UI가 표시하는 데이터를 연결하는 프로세스입니다. 바인딩 설정이 올바르고 데이터가 적절한 알림을 제공하는 경우 데이터 값이 변경될 때 데이터에 바인딩된 요소에 변경 사항이 자동으로 반영됩니다. 또한 요소에서 데이터의 외부 표현이 변경되면 내부 데이터가 자동으로 업데이트되어 변경 내용이 반영될 수 있습니다. 예를 들어 사용자가 `TextBox` 요소의 값을 편집하면 내부 데이터 값이 자동으로 업데이트되어 해당 변경 내용이 반영됩니다.

데이터 바인딩은 일반적으로 서버 또는 로컬 구성 데이터를 양식이나 기타 UI 컨트롤에 배치하는 데 사용됩니다. WPF에서 이 개념은 광범위한 속성을 다양한 데이터 소스에 바인딩하는 기능을 포함하도록 확장됩니다. WPF에서 요소의 종속성 속성은 .NET 개체(ADO.NET 개체 또는 웹 서비스와 웹 속성에 연결된 개체 포함) 및 XML 데이터에 바인딩될 수 있습니다.

데이터 바인딩의 예는 경매 항목을 표시하는 [Data binding demo][data-binding-demo](데이터 바인딩 데모)에서 다음 앱 UI를 살펴봅니다.

![데이터 바인딩 샘플 스크린샷](./media/data-binding-overview/demo.png "DataBinding_DataBindingDemo")

앱은 데이터 바인딩의 다음 기능을 보여 줍니다.

- ListBox의 콘텐츠는 *AuctionItem* 개체 컬렉션에 바인딩됩니다. *AuctionItem* 개체에는 *Description*, *StartPrice*, *StartDate*, *Category*, *SpecialFeatures* 등의 속성이 있습니다.

- `ListBox`에 표시된 데이터(*AuctionItem* 개체)는 각 항목에 관한 설명과 현재 위치가 표시되도록 템플릿으로 만들어집니다. 템플릿은 <xref:System.Windows.DataTemplate>을 사용하여 만듭니다. 또한 각 항목의 모양은 표시되는 *AuctionItem*의 *SpecialFeatures* 값에 따라 달라집니다. *AuctionItem*의 *SpecialFeatures* 값이 *Color*이면 항목에는 파란색 테두리가 포함됩니다. *Highlight* 값이면 항목에는 주황색 테두리와 별모양이 포함됩니다. [데이터 템플릿](#data-templating) 섹션에서는 데이터 템플릿을 살펴봅니다.

- 사용자는 제공된 `CheckBoxes`를 사용하여 데이터를 그룹화, 필터링 또는 정렬할 수 있습니다. 위 이미지에는 **Group by category** 및 **Sort by category and date** `CheckBoxes`가 선택되어 있습니다. 데이터가 제품 범주에 따라 그룹화되고 범주 이름이 사전순으로 표시되어 있음을 알 수 있습니다. 그림에서 확인하기는 어렵지만 항목은 각 범주 내에서 시작 날짜별로 정렬됩니다. 정렬에는 ‘컬렉션 뷰’가 사용됩니다. [컬렉션에 바인딩](#binding-to-collections) 섹션에서는 컬렉션 뷰를 살펴봅니다.

- 사용자가 항목을 선택하면 <xref:System.Windows.Controls.ContentControl>은 선택한 항목의 세부 정보를 표시합니다. 이 환경을 ‘마스터-세부 시나리오’라고 합니다. [마스터-세부 시나리오](#master-detail-binding-scenario) 섹션에서는 이 바인딩 유형을 살펴봅니다.

- *StartDate* 속성 형식은 밀리초까지 시간이 포함된 날짜를 반환하는 <xref:System.DateTime>입니다. 이 앱에는 더 짧은 날짜 문자열이 표시되도록 사용자 지정 변환기가 사용되었습니다. [데이터 변환](#data-conversion) 섹션에서는 변환기를 살펴봅니다.

사용자가 *Add Product* 단추를 클릭하면 다음 양식이 표시됩니다.

![Add Product Listing 페이지](./media/data-binding-overview/demo-addproductlisting.png "DataBinding_Demo_AddProductListing")

사용자는 양식에 있는 필드를 편집하고, 간단한 미리 보기 및 자세한 미리 보기 창을 사용하여 제품 목록을 미리 보고, `Submit`을 선택하여 새 제품 목록을 추가할 수 있습니다. 기존 그룹화, 필터링 및 정렬 설정이 새 항목에 적용됩니다. 이 경우 위 그림에 입력된 항목은 *Computer* 범주에서 두 번째 항목으로 표시됩니다.

*Start Date* <xref:System.Windows.Controls.TextBox>에 제공된 유효성 검사 논리는 이 이미지에 표시되지 않습니다. 사용자가 잘못된 날짜(형식이 잘못되거나 지난 날짜)를 입력하면 <xref:System.Windows.Controls.ToolTip>이 표시되고 <xref:System.Windows.Controls.TextBox> 옆에 빨간색 느낌표가 나타납니다. [데이터 유효성 검사](#data-validation) 섹션에서는 유효성 검사 논리를 만드는 방법을 설명합니다.

위에서 간략히 설명한 데이터 바인딩의 다른 기능을 살펴보기 전에 먼저 WPF 데이터 바인딩 이해에 필수적인 기본 개념을 설명합니다.

## <a name="basic-data-binding-concepts"></a>기본 데이터 바인딩 개념

바인딩할 요소 및 데이터 소스의 특성에 관계없이 각 바인딩은 항상 다음 그림에 나와 있는 모델을 따릅니다.

![기본 데이터 바인딩 모델을 보여 주는 다이어그램.](./media/data-binding-overview/basic-data-binding-diagram.png)

그림과 같이 데이터 바인딩은 기본적으로 바인딩 대상과 바인딩 소스를 연결합니다. 그림에서는 다음 기본 WPF 데이터 바인딩 개념을 보여 줍니다.

- 일반적으로 각 바인딩에는 다음 네 가지 구성 요소가 있습니다.

  - 바인딩 대상 개체.
  - 대상 속성.
  - 바인딩 소스.
  - 사용할 바인딩 소스에 있는 값 경로.
  
  > 예를 들어 `TextBox`의 콘텐츠를 `Employee.Name` 속성에 바인딩하려면 대상 개체는 `TextBox`이고, 대상 속성은 <xref:System.Windows.Controls.TextBox.Text%2A> 속성이고, 사용할 값은 *Name*이고, 소스 개체는 *Employee* 개체입니다.

- 대상 속성은 종속성 속성이어야 합니다. 대부분 <xref:System.Windows.UIElement> 속성은 종속성 속성이고 읽기 전용 속성을 제외한 대부분 종속성 속성은 기본적으로 데이터 바인딩을 지원합니다. <xref:System.Windows.DependencyObject>에서 파생된 형식만 종속성 속성을 정의할 수 있으며 모든 <xref:System.Windows.UIElement> 형식은 `DependencyObject`에서 파생됩니다.

- 그림에는 표시되지 않았지만 바인딩 소스 개체는 사용자 지정 .NET 개체로 제한되지 않습니다. WPF 데이터 바인딩은 .NET 개체 및 XML 형식의 데이터를 지원합니다. 예를 들어 바인딩 소스는 <xref:System.Windows.UIElement>, 목록 개체, ADO.NET 개체, Web Services 개체 또는 XML 데이터가 포함된 XmlNode일 수 있습니다. 자세한 내용은 [바인딩 소스 개요](../../framework/wpf/data/binding-sources-overview.md)를 참조하세요.

바인딩을 설정하고 있다면 바인딩 소스’에’ 바인딩 대상을 바인딩하고 있다는 것을 기억하세요. 예를 들어 데이터 바인딩을 사용하여 몇몇 기본 XML 데이터를 <xref:System.Windows.Controls.ListBox>에 표시하고 있다면 XML 데이터에 `ListBox`를 바인딩하는 것입니다.

바인딩을 설정하려면 <xref:System.Windows.Data.Binding> 개체를 사용합니다. 이 문서의 나머지 부분에서는 `Binding` 개체와 연결된 다양한 개념과 개체의 일부 속성 및 사용법을 살펴봅니다.

### <a name="direction-of-the-data-flow"></a>데이터 흐름 방향

이전 그림에서 화살표가 가리키는 대로 바인딩의 데이터 흐름은 바인딩 대상에서 바인딩 소스로 이동하거나(예: 사용자가 `TextBox`를 편집하면 소스 값이 변경됨), 바인딩 소스가 적절한 알림을 제공할 경우 바인딩 소스에서 바인딩 대상으로 이동합니다(예: 바인딩 소스가 변경되면 `TextBox` 콘텐츠가 업데이트됨).

앱에서 사용자가 데이터를 변경하고 다시 소스 개체에 전파할 수 있도록 해야 할 수 있습니다. 또는 사용자가 소스 데이터를 업데이트할 수 없도록 해야 할 수 있습니다. <xref:System.Windows.Data.Binding.Mode?displayProperty=nameWithType>를 설정하여 데이터 흐름을 제어할 수 있습니다.

이 그림은 다양한 유형의 데이터 흐름을 보여 줍니다.

![데이터 바인딩 데이터 흐름](./media/data-binding-overview/databinding-dataflow.png "DataBinding_DataFlow")

- <xref:System.Windows.Data.BindingMode.OneWay> 바인딩을 사용하면 소스 속성이 변경될 경우 대상 속성이 자동으로 업데이트되지만 대상 속성이 변경될 경우 변경 내용이 다시 소스 속성으로 전파되지 않습니다. 이 바인딩 유형은 바인드되는 컨트롤이 암시적으로 읽기 전용인 경우에 적합합니다. 예를 들어 주식 시세표시기와 같은 소스에 바인딩할 수 있거나 대상 속성에는 테이블의 데이터 바인딩된 배경색과 같이 변경을 위해 제공된 컨트롤 인터페이스가 없을 수 있습니다. 대상 속성의 변경 내용을 모니터링할 필요가 없는 경우 <xref:System.Windows.Data.BindingMode.OneWay> 바인딩 모드를 사용하면 <xref:System.Windows.Data.BindingMode.TwoWay> 바인딩 모드의 오버헤드가 방지됩니다.

- <xref:System.Windows.Data.BindingMode.TwoWay> 바인딩으로 인해 소스 속성 또는 대상 속성이 변경되어 다른 항목이 자동으로 업데이트됩니다. 이 바인딩 유형은 편집 가능한 형식이나 기타 완전한 대화형 UI 시나리오에 적합합니다. 대부분의 속성은 기본적으로 <xref:System.Windows.Data.BindingMode.OneWay> 바인딩으로 설정되지만, 일부 종속성 속성(일반적으로 <xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType> 및 [CheckBox.IsChecked](xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked)와 같이 사용자가 편집할 수 있는 컨트롤의 속성)은 기본적으로 <xref:System.Windows.Data.BindingMode.TwoWay> 바인딩으로 설정됩니다. 종속성 속성이 기본적으로 단방향 또는 양방향으로 바인딩되는지를 프로그래밍 방식으로 결정하려면 <xref:System.Windows.DependencyProperty.GetMetadata%2A?displayProperty=nameWithType>를 사용하여 속성 메타데이터를 가져온 후 <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A?displayProperty=nameWithType> 속성의 부울 값을 확인합니다.

- <xref:System.Windows.Data.BindingMode.OneWayToSource>는 <xref:System.Windows.Data.BindingMode.OneWay> 바인딩의 반대로, 대상 속성이 변경되면 소스 속성을 업데이트합니다. UI에서 소스 값을 다시 평가하면 되는 경우가 한 가지 예제 시나리오입니다.

- 그림에는 나타나지 않지만 <xref:System.Windows.Data.BindingMode.OneTime> 바인딩을 사용하면 소스 속성이 대상 속성을 초기화하지만 이후 변경 내용을 전파하지 않습니다. 데이터 컨텍스트가 변경되거나 데이터 컨텍스트의 개체가 변경될 경우 변경 내용이 대상 속성에 반영되지 ‘않습니다’. 이 바인딩 유형은 현재 상태의 스냅샷이 적절하거나 데이터가 실제로 정적인 경우에 적합합니다. 또한 이 바인딩 유형은 원본 속성의 일부 값으로 대상 속성을 초기화하려고 하며 데이터 컨텍스트가 사전에 알려지지 않은 경우에도 유용합니다. 이 모드는 기본적으로 소스 값이 변경되지 않은 경우에 더 나은 성능을 제공하는 <xref:System.Windows.Data.BindingMode.OneWay> 바인딩의 더 간단한 형식입니다.

소스 변경 내용을 검색하려면(<xref:System.Windows.Data.BindingMode.OneWay> 및 <xref:System.Windows.Data.BindingMode.TwoWay> 바인딩에 적용 가능) 소스에서 <xref:System.ComponentModel.INotifyPropertyChanged>와 같은 적절한 속성 변경 알림 메커니즘을 구현해야 합니다. [방법: 속성 변경 알림 구현](../../framework/wpf/data/how-to-implement-property-change-notification.md)에서 <xref:System.ComponentModel.INotifyPropertyChanged> 구현의 예제를 참조하세요.

<xref:System.Windows.Data.Binding.Mode?displayProperty=nameWithType> 속성은 바인딩 모드에 관한 자세한 설명과 바인딩 방향을 지정하는 방법의 예제를 제공합니다.

### <a name="what-triggers-source-updates"></a>소스 업데이트를 트리거하는 항목

<xref:System.Windows.Data.BindingMode.TwoWay> 또는 <xref:System.Windows.Data.BindingMode.OneWayToSource>인 바인딩은 대상 속성의 변경 내용을 수신하고 다시 소스에 전파합니다. 이를 소스 업데이트라고 합니다. 예를 들어 TextBox의 텍스트를 편집하여 기본 소스 값을 변경할 수 있습니다.

하지만 텍스트를 편집하는 동안이나 텍스트 편집을 마치고 컨트롤이 포커스를 잃은 후 소스 값이 업데이트될까요? <xref:System.Windows.Data.Binding.UpdateSourceTrigger?displayProperty=nameWithType> 속성은 소스 업데이트를 트리거하는 항목을 결정합니다. 다음 그림에서 오른쪽 화살표의 점은 <xref:System.Windows.Data.Binding.UpdateSourceTrigger?displayProperty=nameWithType> 속성의 역할을 보여 줍니다.

![UpdateSourceTrigger 속성의 역할을 보여 주는 다이어그램.](./media/data-binding-overview/data-binding-updatesource-trigger.png)

`UpdateSourceTrigger` 값이 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged?displayProperty=nameWithType>이면 대상 속성이 변경되는 즉시 <xref:System.Windows.Data.BindingMode.TwoWay> 또는 <xref:System.Windows.Data.BindingMode.OneWayToSource> 바인딩의 오른쪽 화살표가 가리키는 값이 업데이트됩니다. 하지만 `UpdateSourceTrigger` 값이 <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>이면 대상 속성이 포커스를 잃을 경우에만 이 값이 새 값으로 업데이트됩니다.

<xref:System.Windows.Data.Binding.Mode%2A> 속성과 비슷하게 종속성 속성에 따라 기본 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값이 다릅니다. 대부분의 종속성 속성에 대한 기본값이 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>인 반면 `TextBox.Text` 속성의 기본값은 <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>입니다. `PropertyChanged`는 대개 대상 속성이 변경될 때마다 소스 업데이트가 수행됨을 의미합니다. 즉각적인 변경 내용은 CheckBoxes 및 기타 간단한 컨트롤에 적합합니다. 하지만 텍스트 필드의 경우 키 입력이 있을 때마다 업데이트하면 성능이 저하될 수 있고 새 값으로 커밋하기 전에 사용자가 백스페이스 키를 누르고 입력 오류를 수정할 수 있는 기회가 사라집니다.

종속성 속성의 기본값을 찾는 방법에 관한 자세한 내용은 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성 페이지를 참조하세요.

다음 표에는 <xref:System.Windows.Controls.TextBox>를 예제로 사용하는 각 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값의 예제 시나리오가 나와 있습니다.

| UpdateSourceTrigger 값 | 소스 값이 업데이트될 때 | TextBox의 예제 시나리오 |
| ------------------------- | ---------------------------------- | ---------------------------- |
| `LostFocus`(<xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>의 기본값) | TextBox 컨트롤이 포커스를 잃을 때. | 유효성 검사 논리와 연결된 TextBox(아래 [데이터 유효성 검사](#data-validation) 참조). |
| `PropertyChanged` | <xref:System.Windows.Controls.TextBox>에 입력할 때. | 대화방 창의 TextBox 컨트롤. |
| `Explicit` | 앱이 <xref:System.Windows.Data.BindingExpression.UpdateSource%2A>를 호출할 때. | 편집 가능한 양식의 TextBox 컨트롤(사용자가 제출 단추를 클릭할 경우에만 소스 값 업데이트). |

예는 [방법: TextBox 텍스트의 소스를 업데이트하는 시점 제어](../../framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md)를 참조하세요.

## <a name="creating-a-binding"></a>바인딩 만들기

이전 섹션에서 설명한 일부 개념을 다시 설명하면, <xref:System.Windows.Data.Binding> 개체를 사용하여 바인딩을 설정하고 각 바인딩에는 일반적으로 네 가지 구성 요소인 바인딩 대상, 대상 속성, 바인딩 소스 및 사용할 소스 값이 포함됩니다. 이 섹션에서는 바인딩을 설정하는 방법을 설명합니다.

바인딩 소스 개체가 *SDKSample* 네임스페이스에 정의된 *MyData* 클래스인 다음 예제를 살펴볼 수 있습니다. 설명을 위해 *MyData*에는 값이 “Red”로 설정된 *ColorName* 문자열 속성이 있습니다. 따라서 이 예제에서는 빨간색 배경이 있는 단추를 생성합니다.

[!code-xaml[BindNonTextProperty](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/AutoConvertPropertyToColor.xaml#BindAutoConvertColor)]

바인딩 선언 구문에 관한 자세한 설명과 코드에서 바인딩을 설정하는 방법의 예제는 [바인딩 선언 개요](../../framework/wpf/data/binding-declarations-overview.md)를 참조하세요.

이 예제를 기본 다이어그램에 적용하면 결과 그림은 다음과 같이 표시됩니다. Background 속성이 기본적으로 <xref:System.Windows.Data.BindingMode.OneWay> 바인딩을 지원하므로 이 그림에서는 <xref:System.Windows.Data.BindingMode.OneWay> 바인딩을 설명합니다.

![데이터 바인딩 Background 속성을 보여 주는 다이어그램.](./media/data-binding-overview/data-binding-button-background-example.png)

<xref:System.Windows.Controls.Control.Background%2A> 속성이 <xref:System.Windows.Media.Brush> 형식인데 *ColorName* 속성이 형식 문자열인 경우에도 이 바인딩이 작동하는 이유가 궁금할 수 있습니다. 이 바인딩은 기본 형식 변환을 사용하며 이 기능은 [데이터 변환](#data-conversion) 섹션에서 설명합니다.

### <a name="specifying-the-binding-source"></a>바인딩 소스 지정

이전 예제에서는 [DockPanel.DataContext](xref:System.Windows.FrameworkElement.DataContext) 속성을 설정하여 바인딩 소스를 지정합니다. 그런 다음, <xref:System.Windows.Controls.Button>은 부모 요소인 <xref:System.Windows.Controls.DockPanel>에서 <xref:System.Windows.FrameworkElement.DataContext%2A> 값을 상속합니다. 다시 말하지만, 바인딩 소스 개체는 바인딩의 네 가지 필수 구성 요소 중 하나입니다. 따라서 바인딩 소스 개체를 지정하지 않으면 바인딩은 아무 작업도 하지 않습니다.

바인딩 소스 개체를 지정하는 여러 가지 방법이 있습니다. 여러 속성을 같은 소스에 바인딩할 경우 부모 요소에서 <xref:System.Windows.FrameworkElement.DataContext%2A> 속성을 사용하는 방법이 유용합니다. 하지만 개별 바인딩 선언에서 바인딩 소스를 지정하는 방법이 더 적절한 경우도 있습니다. 이전 예제에서는 <xref:System.Windows.FrameworkElement.DataContext%2A> 속성을 사용하지 않고 다음 예제와 같이 단추의 바인딩 선언에서 직접 <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> 속성을 설정하여 바인딩 소스를 지정할 수 있습니다.

[!code-xaml[BindNonTextPropertyCompactBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/AutoConvertPropertyToColor.xaml#BindAutoConvertColorCompactBinding)]

요소에서 직접 <xref:System.Windows.FrameworkElement.DataContext%2A> 속성을 설정하지 않고, 상위 항목(예: 첫 번째 예제의 단추)에서 <xref:System.Windows.FrameworkElement.DataContext%2A> 값을 상속하고 바인딩에서 <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> 속성(예: 마지막 예제의 단추)을 설정하여 바인딩 소스를 명시적으로 지정하면 <xref:System.Windows.Data.Binding.ElementName?displayProperty=nameWithType> 속성이나 <xref:System.Windows.Data.Binding.RelativeSource?displayProperty=nameWithType> 속성을 사용하여 바인딩 소스를 지정할 수도 있습니다. 슬라이더를 사용하여 단추 너비를 조정하는 경우와 같이 앱에서 다른 요소에 바인딩할 경우에는 <xref:System.Windows.Data.Binding.ElementName%2A> 속성이 유용합니다. 바인딩이 <xref:System.Windows.Controls.ControlTemplate> 또는 <xref:System.Windows.Style>에서 지정되는 경우 <xref:System.Windows.Data.Binding.RelativeSource%2A> 속성이 유용합니다. 자세한 내용은 [방법: 바인딩 소스 지정](../../framework/wpf/data/how-to-specify-the-binding-source.md)을 참조하세요.

### <a name="specifying-the-path-to-the-value"></a>값 경로 지정

바인딩 소스가 개체이면 <xref:System.Windows.Data.Binding.Path?displayProperty=nameWithType> 속성을 사용하여 바인딩에 사용할 값을 지정합니다. XML 데이터에 바인딩할 경우에는 <xref:System.Windows.Data.Binding.XPath?displayProperty=nameWithType> 속성을 사용하여 값을 지정합니다. 경우에 따라 데이터가 XML이더라도 <xref:System.Windows.Data.Binding.Path%2A> 속성을 사용하는 것이 좋을 수 있습니다. 예를 들어 XPath 쿼리의 결과로 반환된 XmlNode의 Name 속성에 액세스하려면 <xref:System.Windows.Data.Binding.XPath%2A> 속성 외에 <xref:System.Windows.Data.Binding.Path%2A> 속성을 사용해야 합니다.

자세한 내용은 <xref:System.Windows.Data.Binding.Path%2A> 및 <xref:System.Windows.Data.Binding.XPath%2A> 속성을 참조하세요.

사용할 값의 <xref:System.Windows.Data.Binding.Path%2A>가 네 가지 필수 구성 요소 중 하나임을 강조했지만, 전체 개체에 바인딩하려는 시나리오에서는 사용할 값이 바인딩 소스 개체와 같습니다. 이 경우에는 <xref:System.Windows.Data.Binding.Path%2A>를 지정하지 않는 것이 좋을 수 없습니다. 다음 예제를 살펴보십시오.

[!code-xaml[EmptyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/EmptyBinding.xaml#EmptyBinding)]

위의 예제에서는 빈 바인딩 구문인 {Binding}을 사용합니다. 이 경우 <xref:System.Windows.Controls.ListBox>는 부모 DockPanel 요소(이 예제에는 표시되지 않음)에서 DataContext를 상속합니다. 경로를 지정하지 않으면 기본적으로 전체 개체에 바인딩됩니다. 즉, 이 예제에서는 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 속성을 전체 개체에 바인딩하므로 경로가 비어 있습니다. 자세한 내용은 [컬렉션에 바인딩](#binding-to-collections) 섹션을 참조하세요.

컬렉션에 바인딩 외에 개체의 단일 속성만이 아닌 전체 개체에 바인딩하려는 경우에도 이 시나리오가 유용합니다. 예를 들면 소스 개체가 <xref:System.String> 형식이고 문자열 자체에 바인딩하려는 경우일 수 있습니다. 또 다른 일반적인 시나리오는 여러 속성이 있는 개체에 요소를 바인딩하려는 경우입니다.

바인딩된 대상 속성에서 데이터가 의미를 가지려면 사용자 지정 논리를 적용해야 할 수 있습니다. 기본 형식 변환이 없는 경우 사용자 지정 논리는 사용자 지정 변환기 형식일 수 있습니다. 변환기에 관한 자세한 내용은 [데이터 변환](#data-conversion)을 참조하세요.

### <a name="binding-and-bindingexpression"></a>Binding 및 BindingExpression

데이터 바인딩의 다른 기능과 사용법을 살펴보기 전에 <xref:System.Windows.Data.BindingExpression> 클래스를 알아보는 것이 도움이 됩니다. 이전 섹션에서 살펴본 대로 <xref:System.Windows.Data.Binding> 클래스는 바인딩 선언의 상위 수준 클래스입니다. 이 클래스는 바인딩의 특징을 지정할 수 있는 다양한 속성을 제공합니다. 관련 클래스인 <xref:System.Windows.Data.BindingExpression>은 소스와 대상 간에 연결을 유지 관리하는 기본 개체입니다. 바인딩에는 여러 바인딩 식에서 공유될 수 있는 모든 정보가 포함됩니다. <xref:System.Windows.Data.BindingExpression>은 공유될 수 없는 인스턴스 식이고 <xref:System.Windows.Data.Binding>의 모든 인스턴스 정보를 포함합니다.

다음 예제를 참조하세요. 여기서 `myDataObject`는 `MyData` 클래스의 인스턴스이고, `myBinding`은 소스 <xref:System.Windows.Data.Binding> 개체이며, `MyData`는 `ColorName` 문자열 속성을 포함하는 정의된 클래스입니다. 이 예제에서는 <xref:System.Windows.Controls.TextBlock>의 인스턴스인 `myText`의 텍스트 콘텐츠를 `ColorName`에 바인딩합니다.

[!code-csharp[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/ManualBinding.cs#CodeOnlyBinding)]
[!code-vb[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/ManualBinding.vb#CodeOnlyBinding)]

같은 *myBinding* 개체를 사용하여 다른 바인딩을 만들 수 있습니다. 예를 들어 *myBinding* 개체를 사용하여 확인란의 텍스트 콘텐츠를 *ColorName*에 바인딩할 수 있습니다. 이 시나리오에는 *myBinding* 개체를 공유하는 두 개의 <xref:System.Windows.Data.BindingExpression> 인스턴스가 있습니다.

<xref:System.Windows.Data.BindingExpression> 개체는 데이터에 바인딩된 개체에서 <xref:System.Windows.Data.BindingOperations.GetBindingExpression%2A>을 호출하여 반환됩니다. 다음 문서에서는 <xref:System.Windows.Data.BindingExpression> 클래스를 사용하는 몇 가지 방법을 설명합니다.

- [바인딩된 대상 속성에서 바인딩 개체 가져오기](../../framework/wpf/data/how-to-get-the-binding-object-from-a-bound-target-property.md)

- [TextBox 텍스트의 소스를 업데이트하는 시점 제어](../../framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md)

## <a name="data-conversion"></a>데이터 변환

[바인딩 만들기](#creating-a-binding) 섹션에서는 <xref:System.Windows.Controls.Control.Background%2A> 속성이 값이 "Red"인 문자열 속성에 바인딩되므로 단추가 빨간색입니다. 이 문자열 값은 문자열 값을 <xref:System.Windows.Media.Brush>로 변환하는 <xref:System.Windows.Media.Brush> 형식에 대한 형식 변환기가 있기 때문에 가능합니다.

이 정보를 그림에 추가하면 [바인딩 만들기](#creating-a-binding) 섹션은 다음과 같이 표시됩니다.

![데이터 바인딩 Default 속성을 보여 주는 다이어그램.](./media/data-binding-overview/data-binding-button-default-conversion.png)

하지만 바인딩 소스 개체에 문자열 형식의 속성이 아닌 <xref:System.Windows.Media.Color> 형식의 *Color* 속성이 있으면 어떻게 될까요? 이 경우 바인딩을 적용하려면 먼저 *Color* 속성 값을 <xref:System.Windows.Controls.Control.Background%2A> 속성이 사용하는 어떤 것으로 변환해야 합니다. 다음 예제와 같이 <xref:System.Windows.Data.IValueConverter> 인터페이스를 구현하여 사용자 지정 변환기를 만들어야 합니다.

[!code-csharp[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/ColorBrushConverter.cs#ColorBrushConverter)]
[!code-vb[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/ColorBrushConverter.vb#ColorBrushConverter)]

자세한 내용은 <xref:System.Windows.Data.IValueConverter>를 참조하세요.

이제 기본 변환 대신 사용자 지정 변환기가 사용되고 다이어그램이 다음과 같이 표시됩니다.

![데이터 바인딩 사용자 지정 변환기를 보여 주는 다이어그램.](./media/data-binding-overview/data-binding-converter-color-example.png)

다시 말하지만, 바인딩되는 형식에 있는 형식 변환기 때문에 기본 변환을 사용할 수 있습니다. 이 동작은 대상에서 사용할 수 있는 형식 변환기에 따라 결정됩니다. 확실하지 않으면 사용자 지정 변환기를 만듭니다.

데이터 변환기를 구현하는 것이 좋은 몇 가지 일반적인 시나리오는 다음과 같습니다.

- 데이터를 문화권에 따라 다르게 표시해야 하는 경우. 예를 들어 특정 문화권에서 사용되는 규칙에 따라 통화 변환기 또는 달력 날짜/시간 변환기를 구현해야 할 수 있습니다.

- 사용되는 데이터가 반드시 속성의 텍스트 값을 변경하는 데 사용될 필요는 없지만, 이미지의 소스 또는 표시 텍스트의 색이나 스타일과 같은 몇 가지 다른 값을 변경하는 데 사용되는 경우. 텍스트 필드를 표 셀의 Background 속성에 바인딩하는 것과 같이 적절해 보이지 않는 속성의 바인딩을 변환하는 방식으로 이 인스턴스에서 변환기를 사용할 수 있습니다.

- 두 개 이상의 컨트롤 또는 컨트롤의 여러 속성이 같은 데이터에 바인딩됩니다. 이 경우 기본 바인딩은 텍스트만 표시할 수 있는 반면, 기타 바인딩은 특정 표시 문제를 처리하지만 소스 정보와 같은 바인딩을 사용합니다.

- 대상 속성에는 <xref:System.Windows.Data.MultiBinding>이라는 바인딩 컬렉션이 있습니다. <xref:System.Windows.Data.MultiBinding>의 경우 사용자 지정 <xref:System.Windows.Data.IMultiValueConverter>를 사용하여 바인딩의 값에서 최종 값을 생성합니다. 예를 들어 빨간색, 파란색 및 녹색 값을 기준으로 색을 계산할 수 있고 이러한 값은 같거나 다른 바인딩 소스 개체의 값일 수 있습니다. 예제와 자세한 내용은 <xref:System.Windows.Data.MultiBinding>을 참조하세요.

## <a name="binding-to-collections"></a>컬렉션에 바인딩

바인딩 소스는 속성에 데이터가 포함된 단일 개체로 처리되거나 종종 함께 그룹화되는 다형 개체의 데이터 수집(예: 데이터베이스에 대한 쿼리의 결과)으로 처리될 수 있습니다. 지금까지 단일 개체에 대한 바인딩만 설명했습니다. 그러나 일반적인 시나리오는 데이터 수집에 대한 바인딩입니다. 예를 들어 일반적인 시나리오는 <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.ListView> 또는 <xref:System.Windows.Controls.TreeView>와 같은 <xref:System.Windows.Controls.ItemsControl>을 사용하여 [데이터 바인딩이란?](#what-is-data-binding) 섹션에 나와 있는 앱과 같이 데이터 수집을 표시하는 것입니다.

다행히도 기본 다이어그램이 적용됩니다. <xref:System.Windows.Controls.ItemsControl>을 컬렉션에 바인딩할 경우 다이어그램은 다음과 같이 표시됩니다.

![데이터 바인딩 ItemsControl 개체를 보여 주는 다이어그램.](./media/data-binding-overview/data-binding-itemscontrol.png)

이 다이어그램과 같이 <xref:System.Windows.Controls.ItemsControl>을 컬렉션 개체에 바인딩하는 데 사용할 속성은 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A?displayProperty=nameWithType> 속성입니다. `ItemsSource`를 <xref:System.Windows.Controls.ItemsControl>의 콘텐츠로 간주할 수 있습니다. `ItemsSource` 속성은 기본적으로 `OneWay` 바인딩을 지원하므로 바인딩은 <xref:System.Windows.Data.BindingMode.OneWay>입니다.

### <a name="how-to-implement-collections"></a>컬렉션을 구현하는 방법

<xref:System.Collections.IEnumerable> 인터페이스를 구현하는 컬렉션을 열거할 수 있습니다. 그러나 컬렉션에서 삽입 또는 삭제가 발생할 때마다 UI가 자동으로 업데이트되도록 동적 바인딩을 설정하려면 컬렉션이 <xref:System.Collections.Specialized.INotifyCollectionChanged> 인터페이스를 구현해야 합니다. 이 인터페이스는 기본 컬렉션이 변경될 때마다 발생해야 하는 이벤트를 노출합니다.

WPF는 <xref:System.Collections.ObjectModel.ObservableCollection%601> 클래스를 제공하고 이 클래스는 <xref:System.Collections.Specialized.INotifyCollectionChanged> 인터페이스를 노출하는 데이터 수집의 기본 구현입니다. 소스 개체에서 대상으로 데이터 값을 전송하는 기능을 완전히 지원하려면 바인딩 가능 속성을 지원하는 컬렉션의 각 개체도 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스를 구현해야 합니다. 자세한 내용은 [바인딩 소스 개요](../../framework/wpf/data/binding-sources-overview.md)를 참조하세요.

고유한 컬렉션을 구현하기 전에 <xref:System.Collections.ObjectModel.ObservableCollection%601>을 사용하거나 <xref:System.Collections.Generic.List%601>, <xref:System.Collections.ObjectModel.Collection%601> 및 <xref:System.ComponentModel.BindingList%601>와 같은 기존 컬렉션 클래스 중 하나를 사용하는 것이 좋습니다. 고급 시나리오가 있고 사용자 지정 컬렉션을 구현하려면 인덱스를 통해 개별적으로 액세스할 수 있는 제네릭이 아닌 컬렉션을 제공하므로 최고의 성능을 제공하는 <xref:System.Collections.IList>를 사용하는 것이 좋습니다.

### <a name="collection-views"></a>컬렉션 뷰

<xref:System.Windows.Controls.ItemsControl>이 데이터 수집에 바인딩된 후 데이터를 정렬, 필터링 또는 그룹화해야 할 수 있습니다. 이 작업을 수행하는 데는 <xref:System.ComponentModel.ICollectionView> 인터페이스를 구현하는 클래스인 컬렉션 뷰를 사용합니다.

#### <a name="what-are-collection-views"></a>컬렉션 뷰란?

컬렉션 뷰는 기본 소스 컬렉션 자체를 변경할 필요 없이 정렬, 필터 및 그룹화 쿼리에 따라 소스 컬렉션을 탐색하고 표시할 수 있는 바인딩 소스 컬렉션의 최상위에 있는 레이어입니다. 컬렉션 뷰에서는 컬렉션의 현재 항목에 대한 포인터도 유지 관리합니다. 소스 컬렉션이 <xref:System.Collections.Specialized.INotifyCollectionChanged> 인터페이스를 구현하면 <xref:System.Collections.Specialized.INotifyCollectionChanged.CollectionChanged> 이벤트를 통해 변경된 내용이 뷰에 전파됩니다.

뷰는 기본 소스 컬렉션을 변경하지 않으므로 각 소스 컬렉션에는 연결된 여러 뷰가 있을 수 있습니다. 예를 들어 *Task* 개체의 컬렉션이 있을 수 있습니다. 뷰를 사용하여 같은 데이터를 다양한 방식으로 표시할 수 있습니다. 예를 들어 페이지 왼쪽에는 우선 순위별로 정렬된 작업을 표시하고 오른쪽에는 영역별로 그룹화된 작업을 표시해야 할 수 있습니다.

#### <a name="how-to-create-a-view"></a>뷰를 만드는 방법

뷰를 만들고 사용하는 한 가지 방법은 뷰 개체를 인스턴스화하고 이를 바인딩 소스로 사용하는 것입니다. 예를 들어 [데이터 바인딩이란?](#what-is-data-binding) 섹션에 나와 있는 [Data binding demo][data-binding-demo](데이터 바인딩 데모) 앱을 살펴보겠습니다. 이 앱은 <xref:System.Windows.Controls.ListBox>가 데이터 수집에 직접 바인딩되지 않고 데이터 수집을 통해 뷰에 바인딩되도록 구현됩니다. 다음 예제는 [Data Binding Demo][data-binding-demo](데이터 바인딩 데모) 앱에서 추출됩니다. <xref:System.Windows.Data.CollectionViewSource> 클래스는 <xref:System.Windows.Data.CollectionView>에서 상속되는 클래스의 XAML 프록시입니다. 이 특정 예제에서 뷰의 <xref:System.Windows.Data.CollectionViewSource.Source%2A>는 현재 앱 개체의 *AuctionItems* 컬렉션(<xref:System.Collections.ObjectModel.ObservableCollection%601> 형식)에 바인딩됩니다.

[!code-xaml[CollectionView](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#CollectionView)]

리소스 *listingDataView*는 앱에 있는 <xref:System.Windows.Controls.ListBox>와 같은 요소의 바인딩 소스로 사용됩니다.

[!code-xaml[ListBoxCollectionView](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#ListBoxCollectionView)]

같은 컬렉션에 대한 또 다른 뷰를 만들려면 또 다른 <xref:System.Windows.Data.CollectionViewSource> 인스턴스를 만들고 다른 `x:Key` 이름을 지정할 수 있습니다.

다음 표에서는 기본 컬렉션 뷰로 만들어지거나 소스 컬렉션 형식에 따라 <xref:System.Windows.Data.CollectionViewSource>를 통해 만들어지는 뷰 데이터 형식을 보여 줍니다.

| 소스 컬렉션 형식                    | 컬렉션 뷰 형식 | 참고 |
| ----------------------------------------- | -------------------- | ----- |
| <xref:System.Collections.IEnumerable>     | <xref:System.Windows.Data.CollectionView>를 기반으로 하는 내부 형식 | 항목을 그룹화할 수 없습니다. |
| <xref:System.Collections.IList>           | <xref:System.Windows.Data.ListCollectionView> | 가장 빠릅니다. |
| <xref:System.ComponentModel.IBindingList> | <xref:System.Windows.Data.BindingListCollectionView> | |

#### <a name="using-a-default-view"></a>기본 뷰 사용

컬렉션 뷰를 만들고 사용하는 한 가지 방법은 컬렉션 뷰를 바인딩 소스로 지정하는 것입니다. WPF에서도 바인딩 소스로 사용되는 모든 컬렉션에 대한 기본 컬렉션 뷰를 만듭니다. 컬렉션에 직접 바인딩할 경우 WPF는 기본 뷰에 바인딩됩니다. 같은 컬렉션에 대한 모든 바인딩이 이 기본 뷰를 공유하므로 하나의 바인딩된 컨트롤이나 코드(예: 뒷부분에 설명되는 현재 항목 포인터에 대한 정렬 또는 변경)를 통해 기본 뷰에 적용된 변경 내용은 같은 컬렉션에 대한 모든 다른 바인딩에 반영됩니다.

기본 뷰를 가져오려면 <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> 메서드를 사용합니다. 예제를 보려면 [데이터 수집의 기본 뷰 가져오기](../../framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md)를 참조하세요.

#### <a name="collection-views-with-adonet-datatables"></a>ADO.NET DataTable이 있는 컬렉션 뷰

성능을 개선하기 위해 ADO.NET <xref:System.Data.DataTable> 또는 <xref:System.Data.DataView> 개체의 컬렉션 뷰는 정렬 및 필터링을 <xref:System.Data.DataView>에 위임하며, 이로 인해 정렬 및 필터링이 데이터 소스의 모든 컬렉션 뷰에서 공유됩니다. 각 컬렉션 뷰를 개별적으로 정렬 및 필터링하려면 자체 <xref:System.Data.DataView> 개체를 사용하여 각 컬렉션 뷰를 초기화합니다.

#### <a name="sorting"></a>정렬

앞에서 설명한 대로 뷰에서는 컬렉션에 정렬 순서를 적용할 수 있습니다. 기본 컬렉션에 있는 데이터에는 관련 상속 순서가 있거나 없을 수도 있습니다. 컬렉션에 대한 뷰를 통해 제공한 비교 기준에 따라 순서를 적용하거나 기본 순서를 변경할 수 있습니다. 이는 데이터의 클라이언트 기반 뷰이므로 일반적으로 열과 일치하는 값에 따라 표 형식 데이터의 열을 정렬해야 할 수 있습니다. 뷰를 사용하면 기본 컬렉션을 변경하거나 컬렉션 콘텐츠를 다시 쿼리할 필요 없이 이 사용자 기반 정렬을 적용할 수 있습니다. 예제를 보려면 [머리글을 클릭할 때 GridView 열 정렬](../../framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)을 참조하세요.

다음 예제에서는 [데이터 바인딩이란?](#what-is-data-binding) 섹션에 있는 앱 UI의 "Sort by category and date" <xref:System.Windows.Controls.CheckBox>에 관한 정렬 논리를 보여 줍니다.

[!code-csharp[AddSortChecked](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#AddSortChecked)]
[!code-vb[AddSortChecked](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#AddSortChecked)]

#### <a name="filtering"></a>필터링

뷰에서 컬렉션에 필터를 적용할 수 있으므로 뷰에는 전체 컬렉션의 특정 하위 집합만 표시됩니다. 데이터에서 조건에 따라 필터링할 수 있습니다. 예를 들어 [데이터 바인딩이란?](#what-is-data-binding) 섹션의 앱이 수행하는 것처럼 "Show only bargains" <xref:System.Windows.Controls.CheckBox>에는 가격이 $25 이상인 항목을 필터링하는 논리가 포함됩니다. 다음 코드는 <xref:System.Windows.Data.CollectionViewSource.Filter>를 선택할 때 *ShowOnlyBargainsFilter*를 <xref:System.Windows.Controls.CheckBox> 이벤트 처리기로 설정하기 위해 실행됩니다.

[!code-csharp[ListingViewFilter](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#ListingViewFilter)]
[!code-vb[ListingViewFilter](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#ListingViewFilter)]

*ShowOnlyBargainsFilter* 이벤트 처리기에는 다음과 같은 구현이 있습니다.

[!code-csharp[FilterEvent](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#FilterEvent)]
[!code-vb[FilterEvent](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#FilterEvent)]

<xref:System.Windows.Data.CollectionViewSource> 대신 <xref:System.Windows.Data.CollectionView> 클래스 중 하나를 사용하는 경우 <xref:System.Windows.Data.CollectionView.Filter%2A> 속성을 사용하여 콜백을 지정합니다. 예제를 보려면 [뷰에서 데이터 필터링](../../framework/wpf/data/how-to-filter-data-in-a-view.md)을 참조하세요.

#### <a name="grouping"></a>그룹화

<xref:System.Collections.IEnumerable> 컬렉션을 보는 내부 클래스를 제외하고 모든 컬렉션 뷰는 사용자가 컬렉션 뷰의 컬렉션을 논리 그룹으로 분할할 수 있는 ‘그룹화’를 지원합니다. 그룹은 사용자가 그룹 목록을 제공하는 경우 명시적 그룹이고 데이터에 따라 그룹이 동적으로 생성되는 경우 암시적 그룹입니다.

다음 예제에서는 "Group by category" <xref:System.Windows.Controls.CheckBox>의 논리를 보여 줍니다.

[!code-csharp[ListingGroupCheck](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#ListingGroupCheck)]
[!code-vb[ListingGroupCheck](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#ListingGroupCheck)]

다른 그룹화 예제를 보려면 [GridView를 구현하는 ListView의 항목 그룹화](../../framework/wpf/controls/how-to-group-items-in-a-listview-that-implements-a-gridview.md)를 참조하세요.

#### <a name="current-item-pointers"></a>현재 항목 포인터

뷰는 현재 항목의 개념도 지원합니다. 컬렉션 뷰에서 개체를 탐색할 수 있습니다. 탐색할 때 컬렉션의 특정 위치에 있는 개체를 검색할 수 있는 항목 포인터를 이동합니다. 예제를 보려면 [데이터 CollectionView의 개체 탐색](../../framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md)을 참조하세요.

WPF는 뷰(지정한 뷰 또는 컬렉션의 기본 뷰)를 통해 컬렉션에 바인딩되므로 컬렉션에 대한 모든 바인딩에는 현재 항목 포인터가 포함됩니다. 뷰에 바인딩할 때 `Path` 값의 슬래시("/") 문자는 뷰의 현재 항목을 지정합니다. 다음 예제에서 데이터 컨텍스트는 컬렉션 뷰입니다. 첫 줄은 컬렉션에 바인딩됩니다. 두 번째 줄은 컬렉션의 현재 항목에 바인딩됩니다. 세 번째 줄은 컬렉션에 있는 현재 항목의 `Description` 속성에 바인딩됩니다.

```xaml
<Button Content="{Binding }" />
<Button Content="{Binding Path=/}" />
<Button Content="{Binding Path=/Description}" />
```

컬렉션 계층 구조를 트래버스하도록 슬래시와 속성 구문을 쌓을 수도 있습니다. 다음 예제에서는 소스 컬렉션의 현재 항목 속성인 `Offices`라는 컬렉션의 현재 항목에 바인딩합니다.

```xaml
<Button Content="{Binding /Offices/}" />
```

컬렉션에 적용되는 정렬이나 필터링이 현재 항목 포인터에 영향을 미칠 수 있습니다. 정렬은 현재 항목 포인터를 선택된 마지막 항목에 유지하지만 이제 컬렉션 뷰는 포인터를 중심으로 재구성됩니다. 이전에는 선택된 항목이 목록의 시작 부분에 있었을 수 있지만 이제 선택된 항목이 가운데 부분에 있을 수 있습니다. 필터링은 필터링한 후 선택 항목이 뷰에 남아 있으면 선택된 항목을 유지합니다. 남아 있지 않으면 현재 항목 포인터는 필터링된 컬렉션 뷰의 첫 번째 항목으로 설정됩니다.

#### <a name="master-detail-binding-scenario"></a>마스터-세부 바인딩 시나리오

현재 항목의 개념은 컬렉션에서 항목을 탐색하는 경우뿐 아니라 마스터-세부 바인딩 시나리오에도 유용합니다. 다시 [데이터 바인딩이란?](#what-is-data-binding) 섹션의 앱 UI를 살펴보겠습니다. 해당 앱에서 <xref:System.Windows.Controls.ListBox> 내의 선택 항목에 따라 <xref:System.Windows.Controls.ContentControl>에 표시되는 콘텐츠가 결정됩니다. 다르게 설명하자면, <xref:System.Windows.Controls.ListBox> 항목이 선택될 때 <xref:System.Windows.Controls.ContentControl>은 선택된 항목의 세부 정보를 표시합니다.

간단히 두 개 이상의 컨트롤을 같은 뷰에 바인딩하여 마스터-세부 시나리오를 구현할 수 있습니다. [Data Binding Demo][data-binding-demo](데이터 바인딩 데모)의 다음 예제에서는 [데이터 바인딩이란?](#what-is-data-binding) 섹션의 앱 UI에 표시되는 <xref:System.Windows.Controls.ListBox> 및 <xref:System.Windows.Controls.ContentControl>의 태그를 보여 줍니다.

[!code-xaml[ListBoxContentControl](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#ListBoxContentControl)]

컨트롤이 둘 다 같은 소스인 *listingDataView* 정적 리소스에 바인딩되어 있습니다([뷰를 만드는 방법 섹션](#how-to-create-a-view)에서 이 리소스의 정의 참조). 이 바인딩은 singleton 개체(이 경우 <xref:System.Windows.Controls.ContentControl>)가 컬렉션에 바인딩될 경우 자동으로 뷰의 <xref:System.Windows.Data.CollectionView.CurrentItem%2A>에 바인딩되기 때문에 가능합니다. <xref:System.Windows.Data.CollectionViewSource> 개체는 통화 및 선택 항목을 자동으로 동기화합니다. 이 예제에서 목록 컨트롤이 <xref:System.Windows.Data.CollectionViewSource> 개체에 바인딩되지 않은 경우에는 <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> 속성을 `true`로 설정해야 이 기능이 작동합니다.

다른 예제를 보려면 [선택에 따라 컬렉션 및 표시 정보에 바인딩](../../framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md) 및 [계층적 데이터에 마스터-세부 패턴 사용](../../framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)을 참조하세요.

위 예제에서는 템플릿을 사용합니다. 실제로 템플릿(<xref:System.Windows.Controls.ContentControl>에서 명시적으로 사용되는 템플릿 및 <xref:System.Windows.Controls.ListBox>에서 암시적으로 사용되는 템플릿)을 사용하지 않으면 데이터가 원하는 방식으로 표시되지 않습니다. 이제 다음 섹션에서 데이터 템플릿을 살펴보겠습니다.

## <a name="data-templating"></a>데이터 템플릿

데이터 템플릿을 사용하지 않으면 [데이터 바인딩이란?](#what-is-data-binding) 섹션의 앱 UI가 다음과 같이 표시됩니다.

![데이터 템플릿을 사용하지 않는 데이터 바인딩 데모](./media/data-binding-overview/demo-no-template.png)

이전 섹션의 예제와 같이 <xref:System.Windows.Controls.ListBox> 컨트롤과 <xref:System.Windows.Controls.ContentControl>이 둘 다 *AuctionItem*의 전체 컬렉션 개체(또는 더 구체적으로는 컬렉션 개체에 대한 뷰)에 바인딩됩니다. 데이터 수집을 표시하는 방법에 대한 구체적인 명령이 없으면 <xref:System.Windows.Controls.ListBox>는 기본 컬렉션에 있는 각 개체의 문자열 표현을 표시하고 <xref:System.Windows.Controls.ContentControl>은 바인딩된 개체의 문자열 표현을 표시합니다.

이 문제를 해결하기 위해 앱은 <xref:System.Windows.DataTemplate?text=DataTemplates>를 정의합니다. 이전 섹션의 예제와 같이 <xref:System.Windows.Controls.ContentControl>은 *detailsProductListingTemplate* 데이터 템플릿을 명시적으로 사용합니다. <xref:System.Windows.Controls.ListBox> 컨트롤은 컬렉션의 *AuctionItem* 개체를 표시할 때 다음 데이터 템플릿을 암시적으로 사용합니다.

[!code-xaml[AuctionItemDataTemplate](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#AuctionItemDataTemplate)]

DataTemplates를 둘 다 사용하면 결과 UI는 [데이터 바인딩이란?](#what-is-data-binding) 섹션의 UI와 같이 표시됩니다. 스크린샷에 표시된 것처럼 DataTemplates를 사용하면 컨트롤에 데이터를 배치할 수 있을 뿐 아니라 데이터에 대한 눈에 띄는 시각적 개체를 정의할 수도 있습니다. 예를 들어 <xref:System.Windows.DataTrigger>는 위의 <xref:System.Windows.DataTemplate>에서 사용되므로 *HighLight* 값이 *SpecialFeatures*인 *AuctionItem*에는 주황색 테두리와 별모양이 함께 표시됩니다.

데이터 템플릿에 관한 자세한 내용은 [데이터 템플릿 개요](../../framework/wpf/data/data-templating-overview.md)를 참조하세요.

## <a name="data-validation"></a>데이터 유효성 검사

사용자 입력을 사용하는 대부분 앱에는 사용자가 필요한 정보를 입력했는지 확인할 수 있는 유효성 검사 논리가 있어야 합니다. 유효성 검사는 형식, 범위, 서식 또는 기타 앱별 요구 사항에 따라 달라질 수 있습니다. 이 섹션에서는 WPF에서 데이터 유효성 검사를 사용하는 방법을 설명합니다.

### <a name="associating-validation-rules-with-a-binding"></a>유효성 검사 규칙과 바인딩 연결

WPF 데이터 바인딩 모델을 사용하면 <xref:System.Windows.Data.Binding.ValidationRules%2A>를 <xref:System.Windows.Data.Binding> 개체와 연결할 수 있습니다. 예를 들어 다음 예제에서는 <xref:System.Windows.Controls.TextBox>를 `StartPrice` 속성에 바인딩하고 <xref:System.Windows.Controls.ExceptionValidationRule> 개체를 <xref:System.Windows.Data.Binding.ValidationRules%2A?displayProperty=nameWithType> 속성에 추가합니다.

[!code-xaml[TextboxStartPrice](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#TextboxStartPrice)]

<xref:System.Windows.Controls.ValidationRule> 개체는 속성 값이 유효한지 확인합니다. WPF에는 두 가지 형식의 기본 제공 <xref:System.Windows.Controls.ValidationRule> 개체가 있습니다.

- <xref:System.Windows.Controls.ExceptionValidationRule>은 바인딩 소스 속성을 업데이트하는 동안 throw된 예외가 있는지 확인합니다. 이전 예제에서 `StartPrice`는 정수 형식입니다. 사용자가 정수로 변환될 수 없는 값을 입력하면 예외가 throw되어 바인딩이 잘못된 것으로 표시됩니다. <xref:System.Windows.Controls.ExceptionValidationRule>을 명시적으로 설정하는 대체 구문은 <xref:System.Windows.Data.Binding> 또는 <xref:System.Windows.Data.MultiBinding> 개체에서 <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> 속성을 `true`로 설정하는 것입니다.

- <xref:System.Windows.Controls.DataErrorValidationRule> 개체는 <xref:System.ComponentModel.IDataErrorInfo> 인터페이스를 구현하는 개체에서 발생한 오류를 확인합니다. 이 유효성 검사 규칙을 사용하는 예제는 <xref:System.Windows.Controls.DataErrorValidationRule>을 참조하세요. <xref:System.Windows.Controls.DataErrorValidationRule>을 명시적으로 설정하는 대체 구문은 <xref:System.Windows.Data.Binding> 또는 <xref:System.Windows.Data.MultiBinding> 개체에서 <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> 속성을 `true`로 설정하는 것입니다.

<xref:System.Windows.Controls.ValidationRule> 클래스에서 파생시키고 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 메서드를 구현하는 방식으로 자체 유효성 검사 규칙을 만들 수도 있습니다. 다음 예제에서는 [데이터 바인딩이란?](#what-is-data-binding) 섹션의 *Add Product Listing* "Start Date" <xref:System.Windows.Controls.TextBox>에서 사용되는 규칙을 보여 줍니다.

[!code-csharp[FutureDateRule](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/FutureDateRule.cs#FutureDateRule)]
[!code-vb[FutureDateRule](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/FutureDateRule.vb#FutureDateRule)]

다음 예제와 같이 *StartDateEntryForm* <xref:System.Windows.Controls.TextBox>는 이 *FutureDateRule*을 사용합니다.

[!code-xaml[TextboxStartDate](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#TextboxStartDate)]

<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값은 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>이므로 바인딩 엔진은 키 입력이 있을 때마다 소스 값을 업데이트합니다. 즉, 키 입력이 있을 때마다 <xref:System.Windows.Data.Binding.ValidationRules%2A> 컬렉션에서 모든 규칙을 확인합니다. 이 내용은 유효성 검사 프로세스 섹션에서 자세히 설명합니다.

### <a name="providing-visual-feedback"></a>시각적 피드백 제공

사용자가 잘못된 값을 입력할 경우 앱 UI에 오류에 관한 피드백을 표시해야 할 수 있습니다. 해당 피드백을 제공하는 한 가지 방법은 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> 연결된 속성을 <xref:System.Windows.Controls.ControlTemplate>으로 설정하는 것입니다. 이전 하위 섹션과 같이 *StartDateEntryForm* <xref:System.Windows.Controls.TextBox>는 *validationTemplate*이라는 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A>을 사용합니다. 다음 예제에서는 *validationTemplate*의 정의를 보여 줍니다.

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#ControlTemplate)]

<xref:System.Windows.Controls.AdornedElementPlaceholder> 요소는 표시되는 컨트롤을 배치할 위치를 지정합니다.

또한 <xref:System.Windows.Controls.ToolTip>을 사용하여 오류 메시지를 표시할 수도 있습니다. *StartDateEntryForm* 및 *StartPriceEntryForm* <xref:System.Windows.Controls.TextBox>는 둘 다 오류 메시지를 표시하는 <xref:System.Windows.Controls.ToolTip>을 만드는 *textStyleTextBox* 스타일을 사용합니다. 다음 예제에서는 *textStyleTextBox*의 정의를 보여 줍니다. 바인딩된 요소의 속성에 대한 바인딩 중 하나 이상에서 오류가 발생할 경우 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>은 `true`입니다.

[!code-xaml[TextBoxStyle](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#TextBoxStyle)]

사용자 지정 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 및 <xref:System.Windows.Controls.ToolTip>을 사용하면 *StartDateEntryForm* <xref:System.Windows.Controls.TextBox>는 유효성 검사 오류가 있는 경우 다음과 같이 표시됩니다.

![데이터 바인딩 유효성 검사 오류](./media/data-binding-overview/demo-validation-date.png "DataBindingDemo_Validation")

<xref:System.Windows.Data.Binding>에 연결된 유효성 검사 규칙이 있지만 바인딩된 컨트롤에서 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A>을 지정하지 않으면 유효성 검사 오류가 있을 경우 이를 사용자에게 알리는 데 기본 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A>이 사용됩니다. 기본 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A>은 표시기 레이어에서 빨간색 테두리를 정의하는 컨트롤 템플릿입니다. 기본 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 및 <xref:System.Windows.Controls.ToolTip>을 사용하면 *StartPriceEntryForm* <xref:System.Windows.Controls.TextBox>의 UI는 유효성 검사 오류가 발생하는 경우 다음과 같이 표시됩니다.

![데이터 바인딩 유효성 검사 오류](./media/data-binding-overview/demo-validation-price.png "DataBindingDemo_ValidationDefault")

대화 상자에서 모든 컨트롤의 유효성을 검사하는 논리를 제공하는 방법의 예제를 보려면 [대화 상자 개요](../../framework/wpf/app-development/dialog-boxes-overview.md)에서 사용자 지정 대화 상자 섹션을 참조하세요.

### <a name="validation-process"></a>유효성 검사 프로세스

유효성 검사는 대개 대상 값이 바인딩 소스 속성에 전송될 때 수행됩니다. 이 전송은 <xref:System.Windows.Data.BindingMode.TwoWay> 및 <xref:System.Windows.Data.BindingMode.OneWayToSource> 바인딩에서 발생합니다. 다시 말하지만, [소스 업데이트를 트리거하는 항목](#what-triggers-source-updates) 섹션에서 설명한 대로 소스 업데이트는 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성의 값에 따라 결정됩니다.

다음 항목은 ‘유효성 검사’ 프로세스를 설명합니다. 이 프로세스 중에 유효성 검사 오류나 기타 오류가 발생하면 프로세스가 중단됩니다.

1. 바인딩 엔진은 해당 <xref:System.Windows.Data.Binding>에 대해 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>이 <xref:System.Windows.Controls.ValidationStep.RawProposedValue>로 설정된 사용자 지정 <xref:System.Windows.Controls.ValidationRule> 개체가 정의되어 있는지 확인합니다. 이 경우 개체 중 하나에서 오류가 발생하거나 모든 개체가 통과할 때까지 각 <xref:System.Windows.Controls.ValidationRule>에서 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 메서드를 호출합니다.

2. 그런 다음 바인딩 엔진은 변환기를 호출합니다(있는 경우).

3. 변환기가 성공하면 바인딩 엔진은 해당 <xref:System.Windows.Data.Binding>에 대해 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>이 <xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue>로 설정된 사용자 지정 <xref:System.Windows.Controls.ValidationRule> 개체가 정의되어 있는지 확인합니다. 이 경우 개체 중 하나에서 오류가 발생하거나 모든 개체가 통과할 때까지 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>이 <xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue>로 설정된 각 <xref:System.Windows.Controls.ValidationRule>에서 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 메서드를 호출합니다.

4. 바인딩 엔진은 소스 속성을 설정합니다.

5. 바인딩 엔진은 해당 <xref:System.Windows.Data.Binding>에 대해 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>이 <xref:System.Windows.Controls.ValidationStep.UpdatedValue>로 설정된 사용자 지정 <xref:System.Windows.Controls.ValidationRule> 개체가 정의되어 있는지 확인합니다. 이 경우 개체 중 하나에서 오류가 발생하거나 모든 개체가 통과할 때까지 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>이 <xref:System.Windows.Controls.ValidationStep.UpdatedValue>로 설정된 각 <xref:System.Windows.Controls.ValidationRule>에서 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 메서드를 호출합니다. <xref:System.Windows.Controls.DataErrorValidationRule>이 바인딩과 연결되고 해당 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>이 기본값 <xref:System.Windows.Controls.ValidationStep.UpdatedValue>로 설정된 경우 이때 <xref:System.Windows.Controls.DataErrorValidationRule>이 확인됩니다. 이때 <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>가 `true`로 설정된 모든 바인딩이 선택됩니다.

6. 바인딩 엔진은 해당 <xref:System.Windows.Data.Binding>에 대해 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>이 <xref:System.Windows.Controls.ValidationStep.CommittedValue>로 설정된 사용자 지정 <xref:System.Windows.Controls.ValidationRule> 개체가 정의되어 있는지 확인합니다. 이 경우 개체 중 하나에서 오류가 발생하거나 모든 개체가 통과할 때까지 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>이 <xref:System.Windows.Controls.ValidationStep.CommittedValue>로 설정된 각 <xref:System.Windows.Controls.ValidationRule>에서 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 메서드를 호출합니다.

이 프로세스 중에 <xref:System.Windows.Controls.ValidationRule>이 통과하지 못하면 바인딩 엔진은 <xref:System.Windows.Controls.ValidationError> 개체를 만들고 바인딩된 요소의 <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> 컬렉션에 추가합니다. 바인딩 엔진은 특정 단계에서 <xref:System.Windows.Controls.ValidationRule> 개체를 실행하기 전에 해당 단계 중에 바인딩된 요소의 <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> 연결된 속성에 추가된 모든 <xref:System.Windows.Controls.ValidationError>를 제거합니다. 예를 들어 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>이 <xref:System.Windows.Controls.ValidationStep.UpdatedValue>로 설정된 <xref:System.Windows.Controls.ValidationRule>이 실패한 경우 다음에 유효성 검사 프로세스가 수행될 때 바인딩 엔진은 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>이 <xref:System.Windows.Controls.ValidationStep.UpdatedValue>로 설정된 <xref:System.Windows.Controls.ValidationRule>을 호출하기 직전에 해당 <xref:System.Windows.Controls.ValidationError>를 제거합니다.

<xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType>가 비어 있지 않으면 요소의 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결된 속성은 `true`로 설정됩니다. 또한 <xref:System.Windows.Data.Binding>의 <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A> 속성이 `true`로 설정된 경우 바인딩 엔진은 요소에서 <xref:System.Windows.Controls.Validation.Error?displayProperty=nameWithType> 연결된 이벤트를 발생시킵니다.

한쪽 방향으로(대상에서 소스로 또는 소스에서 대상으로) 유효한 값이 전송되면 <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> 연결된 속성이 지워집니다.

바인딩에 연결된 <xref:System.Windows.Controls.ExceptionValidationRule>이 있거나 <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> 속성이 `true`로 설정되고 바인딩 엔진이 소스를 설정할 때 예외가 throw된 경우 바인딩 엔진은 <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>가 있는지 확인합니다. <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> 콜백을 사용하여 예외를 처리하기 위한 사용자 지정 처리기를 제공하는 옵션이 있습니다. <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>가 <xref:System.Windows.Data.Binding>에 지정되지 않은 경우 바인딩 엔진은 예외가 있는 <xref:System.Windows.Controls.ValidationError>를 만들고 바인딩된 요소의 <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> 컬렉션에 추가합니다.

## <a name="debugging-mechanism"></a>디버깅 메커니즘

바인딩 관련 개체에서 <xref:System.Diagnostics.PresentationTraceSources.TraceLevel%2A?displayProperty=nameWithType> 연결된 속성을 설정하여 특정 바인딩 상태에 대한 정보를 받을 수 있습니다.

## <a name="see-also"></a>참조

- <xref:System.Windows.Controls.DataErrorValidationRule>
- [LINQ 쿼리 결과에 바인딩](../../framework/wpf/data/how-to-bind-to-the-results-of-a-linq-query.md)
- [데이터 바인딩](../../framework/wpf/advanced/optimizing-performance-data-binding.md)
- [Data Binding Demo][data-binding-demo](데이터 바인딩 데모)
- [방법 문서](../../framework/wpf/data/data-binding-how-to-topics.md)
- [ADO.NET 데이터 소스 바인딩](../../framework/wpf/data/how-to-bind-to-an-ado-net-data-source.md)

[data-binding-demo]: https://github.com/microsoft/WPF-Samples/tree/master/Sample%20Applications/DataBindingDemo "데이터 바인딩 데모 앱"

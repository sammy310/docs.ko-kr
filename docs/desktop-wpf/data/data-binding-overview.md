---
title: 데이터 바인딩 개요
description: .NET 코어용 Windows 프레젠테이션 재단에서 프로젝트에 추가할 수 있는 다양한 데이터 원본에 대해 알아봅니다. 데이터 원본을 XAML 요소에 바인딩하여 동적 앱을 만들 수 있습니다.
author: thraka
ms.date: 09/19/2019
ms.author: adegeo
dev_langs:
- csharp
- vb
ms.openlocfilehash: 7f17ff094a35c04ba880c87c6966d7d249817516
ms.sourcegitcommit: b75a45f0cfe012b71b45dd9bf723adf32369d40c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "81433255"
---
# <a name="data-binding-overview-in-wpf"></a>WPF의 데이터 바인딩 개요

WPF(Windows 프레젠테이션 재단)의 데이터 바인딩은 앱이 데이터를 표시하고 상호 작용할 수 있는 간단하고 일관된 방법을 제공합니다. 요소는 .NET 개체 및 XML 의 형태로 다양한 데이터 원본의 데이터에 바인딩할 수 있습니다. <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.ItemsControl> <xref:System.Windows.Controls.ContentControl> <xref:System.Windows.Controls.ListView>와 같은 모든 및 및 는 단일 데이터 항목 또는 데이터 항목 의 컬렉션을 유연하게 스타일링할 수 있도록 기본 제공 기능이 내장되어 <xref:System.Windows.Controls.ListBox> 있습니다. 데이터를 기반으로 정렬, 필터 및 그룹 보기를 생성할 수 있습니다.

WPF의 데이터 바인딩 기능은 광범위한 속성에 의한 데이터 바인딩에 대한 고유 지원, 유연한 데이터 UI 표현, UI에서 비즈니스 논리의 깔끔한 분리 를 포함하여 기존 모델에 비해 몇 가지 장점이 있습니다.

이 문서에서는 먼저 WPF 데이터 바인딩의 기본 개념에 <xref:System.Windows.Data.Binding> 대해 설명한 다음 클래스의 사용 및 데이터 바인딩의 다른 기능에 대해 설명합니다.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="what-is-data-binding"></a>데이터 바인딩이란?

데이터 바인딩은 앱 UI와 표시되는 데이터 간의 연결을 설정하는 프로세스입니다. 바인딩 설정이 올바르고 데이터가 적절한 알림을 제공하는 경우 데이터 값이 변경될 때 데이터에 바인딩된 요소에 변경 사항이 자동으로 반영됩니다. 또한 요소에서 데이터의 외부 표현이 변경되면 내부 데이터가 자동으로 업데이트되어 변경 내용이 반영될 수 있습니다. 예를 들어 사용자가 `TextBox` 요소에서 값을 편집하는 경우 기본 데이터 값이 자동으로 업데이트되어 해당 변경 을 반영합니다.

데이터 바인딩의 일반적인 용도는 서버 또는 로컬 구성 데이터를 폼 또는 기타 UI 컨트롤에 배치하는 것입니다. WPF에서 이 개념은 다양한 데이터 원본에 광범위한 특성바인딩을 포함하도록 확장됩니다. WPF에서 요소의 종속성 속성은 .NET 개체(웹 서비스 및 웹 속성과 연결된 개체 또는 ADO.NET 개체 포함) 및 XML 데이터에 바인딩할 수 있습니다.

데이터 바인딩의 예를 들어 경매 항목 목록을 표시하는 [데이터 바인딩 데모에서][data-binding-demo]다음 앱 UI를 살펴봅니다.

![데이터 바인딩 샘플 스크린샷](./media/data-binding-overview/demo.png "DataBinding_DataBindingDemo")

응용 프로그램은 데이터 바인딩의 다음과 같은 기능을 보여 줍니다.

- ListBox의 콘텐츠는 *경매항목* 개체의 컬렉션에 바인딩됩니다. *AuctionItem* 개체에는 *설명,* *시작 가격,* *시작 날짜,* *범주,* 특수 기능 등과 같은 속성이 *있습니다.*

- 에 표시되는 데이터(AuctionItem*AuctionItem* `ListBox` 객체)는 각 항목에 대한 설명과 현재 가격이 표시되도록 템플릿으로 표시됩니다. 템플릿은 <xref:System.Windows.DataTemplate>을 사용하여 만들어집니다. 또한 각 항목의 모양은 표시되는 *AuctionItem*의 *SpecialFeatures* 값에 따라 달라집니다. *AuctionItem*의 *SpecialFeatures* 값이 *Color*이면 항목에는 파란색 테두리가 포함됩니다. *Highlight* 값이면 항목에는 주황색 테두리와 별모양이 포함됩니다. [데이터 템플릿](#data-templating) 섹션에서는 데이터 템플릿을 살펴봅니다.

- 사용자는 제공된 데이터를 사용하여 데이터를 그룹화, `CheckBoxes` 필터링 또는 정렬할 수 있습니다. 위의 이미지에서 **범주별 그룹** 및 **범주 및 날짜별** `CheckBoxes` 정렬이 선택됩니다. 데이터가 제품 범주에 따라 그룹화되고 범주 이름이 사전순으로 표시되어 있음을 알 수 있습니다. 그림에서 확인하기는 어렵지만 항목은 각 범주 내에서 시작 날짜별로 정렬됩니다. 정렬은 *컬렉션 보기를*사용하여 수행됩니다. 컬렉션 바인딩 섹션에서컬렉션 뷰에 대해 [설명합니다.](#binding-to-collections)

- 사용자가 항목을 선택하면 선택한 항목의 세부 정보가 <xref:System.Windows.Controls.ContentControl> 표시됩니다. 이 환경을 *마스터 세부 정보 시나리오라고*합니다. [마스터 세부 정보 시나리오](#master-detail-binding-scenario) 섹션에서는 이러한 유형의 바인딩에 대한 정보를 제공합니다.

- *StartDate* 속성의 형식은 <xref:System.DateTime>밀리초까지의 시간을 포함하는 날짜를 반환하는 것입니다. 이 앱에서는 짧은 날짜 문자열이 표시되도록 사용자 지정 변환기가 사용되었습니다. [데이터 변환](#data-conversion) 섹션에서는 변환에 대한 정보를 제공합니다.

사용자가 *제품 추가* 단추를 선택하면 다음 양식이 표시됩니다.

![제품 목록 추가 페이지](./media/data-binding-overview/demo-addproductlisting.png "DataBinding_Demo_AddProductListing")

사용자는 양식에서 필드를 편집하고, 짧거나 상세한 미리 보기 창을 사용하여 제품 `Submit` 목록을 미리 보고, 새 제품 목록을 추가하도록 선택할 수 있습니다. 기존 그룹화, 필터링 및 정렬 설정은 새 항목에 적용됩니다. 이 경우 위 그림에 입력된 항목은 *Computer* 범주에서 두 번째 항목으로 표시됩니다.

이 이미지에는 *시작 날짜에* <xref:System.Windows.Controls.TextBox>제공된 유효성 검사 논리가 표시되지 않습니다. 사용자가 잘못된 날짜(잘못된 서식 또는 지난 날짜)를 입력하면 사용자에게 <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Controls.TextBox>에 대한 빨간색 느낌표 옆에 알림이 표시됩니다. [데이터 유효성 검사](#data-validation) 섹션에서는 유효성 검사 논리를 만드는 방법을 설명합니다.

위에서 설명한 데이터 바인딩의 다양한 기능에 대해 먼저 WPF 데이터 바인딩을 이해하는 데 중요한 기본 개념에 대해 설명합니다.

## <a name="basic-data-binding-concepts"></a>기본 데이터 바인딩 개념

바인딩하는 요소와 데이터 원본의 특성에 관계없이 각 바인딩은 항상 다음 그림에 표시된 모델을 따릅니다.

![기본 데이터 바인딩 모델을 보여 주는 다이어그램입니다.](./media/data-binding-overview/basic-data-binding-diagram.png)

그림에서 볼 수 있듯이 데이터 바인딩은 기본적으로 바인딩 대상과 바인딩 원본 간의 브리지입니다. 이 그림은 다음과 같은 기본 WPF 데이터 바인딩 개념을 보여 줍니다.

- 일반적으로 각 바인딩에는 다음 네 가지 구성 요소가 있습니다.

  - 바인딩 대상 개체입니다.
  - 대상 속성입니다.
  - 바인딩 소스입니다.
  - 사용할 바인딩 소스의 값에 대한 경로입니다.
  
  > 예를 `TextBox` 들어 a의 콘텐츠를 `Employee.Name` 속성에 바인딩하려는 경우 대상 개체는 `TextBox`에서 를 ,대상 속성은 <xref:System.Windows.Controls.TextBox.Text%2A> 속성이고 사용할 값은 *Name*이며 소스 개체는 *Employee* 개체입니다.

- 대상 속성은 종속성 속성이어야 합니다. 대부분의 <xref:System.Windows.UIElement> 속성은 종속성 속성이며 읽기 전용 속성을 제외한 대부분의 종속성 속성은 기본적으로 데이터 바인딩을 지원합니다. (에서 <xref:System.Windows.DependencyObject> 파생된 형식만 종속성 속성을 정의할 수 있으며 모든 <xref:System.Windows.UIElement> 형식은 `DependencyObject`.)

- 그림에는 표시되지 않지만 바인딩 소스 개체가 사용자 지정 .NET 개체로 제한되지 않는다는 점에 유의해야 합니다. WPF 데이터 바인딩은 .NET 개체 및 XML 형식의 데이터를 지원합니다. 몇 가지 예를 제공하기 위해 바인딩 <xref:System.Windows.UIElement>소스는 목록 개체, ADO.NET 또는 웹 서비스 개체 또는 XML 데이터가 포함된 XmlNode일 수 있습니다. 자세한 내용은 [바인딩 소스 개요를](../../framework/wpf/data/binding-sources-overview.md)참조하십시오.

바인딩을 설정하는 경우 바인딩 원본에 바인딩 대상을 바인딩한다는 점을 *기억해야* 합니다. 예를 <xref:System.Windows.Controls.ListBox> 들어, 사용 데이터 바인딩에 일부 기본 XML 데이터를 표시하는 `ListBox` 경우 XML 데이터에 바인딩됩니다.

바인딩을 설정하려면 개체를 <xref:System.Windows.Data.Binding> 사용합니다. 이 문서의 나머지 부분에서는 개체의 일부 속성 및 사용과 관련된 `Binding` 개념과 관련된 개념에 대해 설명합니다.

### <a name="direction-of-the-data-flow"></a>데이터 흐름의 방향

이전 그림의 화살표로 표시된 것처럼 바인딩의 데이터 흐름은 바인딩 대상에서 바인딩 소스로 이동(예: 사용자가 a)의 `TextBox`값을 편집할 때 및/또는 바인딩 소스에서 바인딩 대상으로 의 한 바인딩 소스로 변경될 때(예: `TextBox` 바인딩 소스의 변경으로 콘텐츠가 업데이트되는 경우) 바인딩 소스가 적절한 알림을 제공하는 경우 바인딩 대상으로 이동합니다.

앱에서 사용자가 데이터를 변경하고 원본 개체로 다시 전파할 수 있도록 할 수 있습니다. 또는 사용자가 소스 데이터를 업데이트할 수 없도록 해야 할 수 있습니다. <xref:System.Windows.Data.Binding.Mode?displayProperty=nameWithType>을 설정하여 데이터 흐름을 제어할 수 있습니다.

이 그림은 다양한 유형의 데이터 흐름을 보여 줍니다.

![데이터 바인딩 데이터 흐름](./media/data-binding-overview/databinding-dataflow.png "DataBinding_DataFlow")

- <xref:System.Windows.Data.BindingMode.OneWay>바인딩을 사용하면 원본 속성이 변경되어 대상 속성이 자동으로 업데이트되지만 대상 속성에 대한 변경 내용은 원본 속성으로 다시 전파되지 않습니다. 이 바인딩 유형은 바인드되는 컨트롤이 암시적으로 읽기 전용인 경우에 적합합니다. 예를 들어 주식 시세 표와 같은 원본에 바인딩하거나 대상 속성에 테이블의 데이터 바인딩 된 배경 색과 같은 변경을 위해 제공된 제어 인터페이스가 없을 수 있습니다. 대상 속성의 변경 내용을 모니터링할 필요가 없는 경우 <xref:System.Windows.Data.BindingMode.OneWay> 바인딩 모드를 사용하면 <xref:System.Windows.Data.BindingMode.TwoWay> 바인딩 모드의 오버헤드가 방지됩니다.

- <xref:System.Windows.Data.BindingMode.TwoWay>바인딩을 사용하면 소스 속성 또는 대상 속성이 자동으로 업데이트됩니다. 이러한 유형의 바인딩은 편집 가능한 양식 또는 기타 완전 대화형 UI 시나리오에 적합합니다. 대부분의 속성은 <xref:System.Windows.Data.BindingMode.OneWay> 바인딩으로 기본값이지만 일부 종속성 속성(일반적으로 <xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType> [는 및 CheckBox.IsChecked](xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked) 기본값과 같은 사용자 편집 가능한 컨트롤의 속성)을 바인딩으로 설정합니다. <xref:System.Windows.Data.BindingMode.TwoWay> 종속성 속성이 기본적으로 단방향 또는 양방향 바인딩여부를 결정하는 프로그래밍 방식의 방법은 속성 메타데이터를 가져온 <xref:System.Windows.DependencyProperty.GetMetadata%2A?displayProperty=nameWithType> 다음 <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A?displayProperty=nameWithType> 속성의 부울 값을 확인하는 것입니다.

- <xref:System.Windows.Data.BindingMode.OneWayToSource>바인딩의 <xref:System.Windows.Data.BindingMode.OneWay> 반대입니다. 대상 속성이 변경될 때 소스 속성을 업데이트합니다. 한 가지 예의 시나리오는 UI에서 원본 값만 다시 평가해야 하는 경우입니다.

- 그림에 나와 있지 <xref:System.Windows.Data.BindingMode.OneTime> 않은 바인딩은 소스 속성이 대상 속성을 초기화하도록 하지만 후속 변경 내용을 전파하지 않습니다. 데이터 컨텍스트가 변경하거나 데이터 컨텍스트의 개체가 변경되면 변경 내용이 대상 속성에 *반영되지 않습니다.* 이러한 유형의 바인딩은 현재 상태의 스냅숏이 적절하거나 데이터가 실제로 정적인 경우에 적합합니다. 또한 이 바인딩 유형은 원본 속성의 일부 값으로 대상 속성을 초기화하려고 하며 데이터 컨텍스트가 사전에 알려지지 않은 경우에도 유용합니다. 이 모드는 기본적으로 소스 <xref:System.Windows.Data.BindingMode.OneWay> 값이 변경되지 않는 경우에 더 나은 성능을 제공하는 더 간단한 바인딩 형식입니다.

원본 변경(적용 가능 <xref:System.Windows.Data.BindingMode.OneWay> <xref:System.Windows.Data.BindingMode.TwoWay> 및 바인딩)을 검색하려면 소스에서 와 같은 <xref:System.ComponentModel.INotifyPropertyChanged>적절한 속성 변경 알림 메커니즘을 구현해야 합니다. [방법:](../../framework/wpf/data/how-to-implement-property-change-notification.md) <xref:System.ComponentModel.INotifyPropertyChanged> 구현의 예에 대 한 속성 변경 알림을 구현 합니다.

이 <xref:System.Windows.Data.Binding.Mode?displayProperty=nameWithType> 속성은 바인딩 모드에 대한 자세한 정보와 바인딩 방향을 지정하는 방법의 예를 제공합니다.

### <a name="what-triggers-source-updates"></a>소스 업데이트를 트리거하는 내용

대상 속성의 <xref:System.Windows.Data.BindingMode.TwoWay> <xref:System.Windows.Data.BindingMode.OneWayToSource> 변경 내용을 수신하거나 수신을 듣고 소스 업데이트라고 하는 원본으로 다시 전파하는 바인딩입니다. 예를 들어 TextBox의 텍스트를 편집하여 기본 소스 값을 변경할 수 있습니다.

그러나 텍스트를 편집하는 동안 또는 텍스트 편집을 완료하고 컨트롤에 포커스가 손실된 후에 소스 값이 업데이트되나요? 속성은 <xref:System.Windows.Data.Binding.UpdateSourceTrigger?displayProperty=nameWithType> 소스의 업데이트를 트리거하는 것을 결정합니다. 다음 그림의 오른쪽 화살표 점은 <xref:System.Windows.Data.Binding.UpdateSourceTrigger?displayProperty=nameWithType> 속성의 역할을 보여 줍니다.

![UpdateSourceTrigger 속성의 역할을 보여 주는 다이어그램입니다.](./media/data-binding-overview/data-binding-updatesource-trigger.png)

`UpdateSourceTrigger` 값이 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged?displayProperty=nameWithType>있는 경우 오른쪽 화살표로 가리키는 값 <xref:System.Windows.Data.BindingMode.TwoWay> 또는 <xref:System.Windows.Data.BindingMode.OneWayToSource> 바인딩은 대상 속성이 변경되는 즉시 업데이트됩니다. 그러나 `UpdateSourceTrigger` 값이 <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>있는 경우 은 대상 속성이 포커스를 잃을 때만 해당 값이 새 값으로 업데이트됩니다.

속성과 <xref:System.Windows.Data.Binding.Mode%2A> 마찬가지로 종속성 속성마다 기본값이 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 다릅니다. 대부분의 종속성 속성에 대한 기본값이 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>인 반면 `TextBox.Text` 속성의 기본값은 <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>입니다. `PropertyChanged`즉, 일반적으로 대상 속성이 변경될 때마다 소스 업데이트가 발생합니다. 확인란 및 기타 간단한 컨트롤의 경우 즉시 변경해도 괜찮습니다. 그러나 텍스트 필드의 경우 모든 키 입력 후에 업데이트하면 성능이 저하되고 새 값으로 커밋하기 전에 백스페이스및 입력 오류를 수정할 수 있는 일반적인 기회를 거부할 수 있습니다.

종속성 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성의 기본값을 찾는 방법에 대한 자세한 내용은 속성 페이지를 참조하십시오.

다음 표에서는 를 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> <xref:System.Windows.Controls.TextBox> 사용하여 각 값에 대한 예제 시나리오를 제공합니다.

| UpdateSourceTrigger 값 | 소스 값이 업데이트되는 경우 | 텍스트 상자에 대한 예제 시나리오 |
| ------------------------- | ---------------------------------- | ---------------------------- |
| `LostFocus`<xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>(기본값) | 텍스트 상자 컨트롤이 포커스를 잃는 경우. | 유효성 검사 논리와 연결된 텍스트 상자입니다(아래 [데이터 유효성 검사](#data-validation) 참조). |
| `PropertyChanged` | 을 입력할 <xref:System.Windows.Controls.TextBox>때 . | 텍스트 상자는 채팅방 창에서 제어합니다. |
| `Explicit` | 앱이 호출할 <xref:System.Windows.Data.BindingExpression.UpdateSource%2A>때 . | TextBox는 편집 가능한 형태로 제어합니다(사용자가 제출 단추를 클릭할 때만 소스 값을 업데이트합니다). |

예를 들어 [텍스트 상자 텍스트가 소스를 업데이트하는 시기를 제어하는 방법: 을](../../framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md)참조하십시오.

## <a name="creating-a-binding"></a>바인딩 만들기

이전 섹션에서 설명한 개념 중 일부를 다시 지정하려면 <xref:System.Windows.Data.Binding> 개체를 사용하여 바인딩을 설정하고 각 바인딩에는 일반적으로 바인딩 대상, 대상 속성, 바인딩 소스 및 사용할 소스 값에 대한 경로의 네 가지 구성 요소가 있습니다. 이 섹션에서는 바인딩을 설정하는 방법을 설명합니다.

바인딩 소스 개체가 *SDKSample* 네임스페이스에 정의된 *MyData* 클래스인 다음 예제를 살펴볼 수 있습니다. 데모를 위해 *MyData에는* 값이 "빨간색"으로 설정된 *ColorName이라는* 문자열 속성이 있습니다. 따라서 이 예제에서는 빨간색 배경이 있는 단추를 생성합니다.

[!code-xaml[BindNonTextProperty](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/AutoConvertPropertyToColor.xaml#BindAutoConvertColor)]

바인딩 선언 구문 및 코드에서 바인딩을 설정하는 방법에 대한 자세한 내용은 [바인딩 선언 개요를](../../framework/wpf/data/binding-declarations-overview.md)참조하십시오.

이 예제를 기본 다이어그램에 적용하면 결과 그림은 다음과 같이 표시됩니다. 이 그림은 Background <xref:System.Windows.Data.BindingMode.OneWay> 속성이 기본적으로 <xref:System.Windows.Data.BindingMode.OneWay> 바인딩을 지원하기 때문에 바인딩을 설명합니다.

![데이터 바인딩 Background 속성을 보여 주는 다이어그램입니다.](./media/data-binding-overview/data-binding-button-background-example.png)

*ColorName* 속성은 형식 문자열이지만 <xref:System.Windows.Controls.Control.Background%2A> 속성은 형식입니다. <xref:System.Windows.Media.Brush> 이 바인딩은 데이터 변환 섹션에서 설명하는 기본 형식 [변환을](#data-conversion) 사용합니다.

### <a name="specifying-the-binding-source"></a>바인딩 소스 지정

이전 예제에서는 [DockPanel.DataContext](xref:System.Windows.FrameworkElement.DataContext) 속성을 설정하여 바인딩 원본을 지정합니다. 그런 <xref:System.Windows.Controls.Button> 다음 <xref:System.Windows.Controls.DockPanel>의 <xref:System.Windows.FrameworkElement.DataContext%2A> 부모 요소인 에서 값을 상속합니다. 다시 말하지만, 바인딩 소스 개체는 바인딩의 네 가지 필수 구성 요소 중 하나입니다. 따라서 바인딩 소스 개체를 지정하지 않으면 바인딩은 아무 작업도 하지 않습니다.

바인딩 소스 개체를 지정하는 여러 가지 방법이 있습니다. 상위 <xref:System.Windows.FrameworkElement.DataContext%2A> 요소에서 속성을 사용하면 동일한 원본에 여러 속성을 바인딩할 때 유용합니다. 하지만 개별 바인딩 선언에서 바인딩 소스를 지정하는 방법이 더 적절한 경우도 있습니다. 이전 예제의 경우 <xref:System.Windows.FrameworkElement.DataContext%2A> 다음 예제와 같이 속성을 단추의 바인딩 <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> 선언에 직접 설정하여 바인딩 소스를 지정할 수 있습니다.

[!code-xaml[BindNonTextPropertyCompactBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/AutoConvertPropertyToColor.xaml#BindAutoConvertColorCompactBinding)]

요소에 <xref:System.Windows.FrameworkElement.DataContext%2A> 속성을 직접 설정하고, 상위 항목(예: 첫 번째 예제의 단추)에서 <xref:System.Windows.FrameworkElement.DataContext%2A> 값을 상속하고 바인딩에 <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> 속성을 설정하여 바인딩 소스를 명시적으로 지정하는 것 이외에 <xref:System.Windows.Data.Binding.ElementName?displayProperty=nameWithType> 속성 또는 <xref:System.Windows.Data.Binding.RelativeSource?displayProperty=nameWithType> 속성을 사용하여 바인딩 소스를 지정할 수도 있습니다. 이 <xref:System.Windows.Data.Binding.ElementName%2A> 속성은 슬라이더를 사용하여 단추의 너비를 조정하는 경우와 같이 앱의 다른 요소에 바인딩할 때 유용합니다. 이 <xref:System.Windows.Data.Binding.RelativeSource%2A> 속성은 바인딩이 a <xref:System.Windows.Controls.ControlTemplate> 또는 <xref:System.Windows.Style>에 지정된 경우에 유용합니다. 자세한 내용은 [방법: 바인딩 소스 지정을](../../framework/wpf/data/how-to-specify-the-binding-source.md)참조하십시오.

### <a name="specifying-the-path-to-the-value"></a>값에 대한 경로 지정

바인딩 소스가 개체인 경우 <xref:System.Windows.Data.Binding.Path?displayProperty=nameWithType> 속성을 사용하여 바인딩에 사용할 값을 지정합니다. XML 데이터에 바인딩하는 경우 <xref:System.Windows.Data.Binding.XPath?displayProperty=nameWithType> 속성을 사용하여 값을 지정합니다. 경우에 따라 데이터가 XML인 경우에도 <xref:System.Windows.Data.Binding.Path%2A> 속성을 사용할 수 있습니다. 예를 들어 반환된 XmlNode의 Name 속성에 액세스하려면(XPath 쿼리의 결과로) <xref:System.Windows.Data.Binding.Path%2A> <xref:System.Windows.Data.Binding.XPath%2A> 속성 외에 속성을 사용해야 합니다.

자세한 내용은 참조는 <xref:System.Windows.Data.Binding.Path%2A> 및 <xref:System.Windows.Data.Binding.XPath%2A> 속성입니다.

사용할 값이 바인딩의 <xref:System.Windows.Data.Binding.Path%2A> 네 가지 필수 구성 요소 중 하나임을 강조했지만 전체 개체에 바인딩하려는 시나리오에서는 사용할 값이 바인딩 원본 개체와 동일합니다. 이러한 경우 <xref:System.Windows.Data.Binding.Path%2A>을 지정하지 않는 것이 적용됩니다. 아래 예제를 고려해 보세요.

[!code-xaml[EmptyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/EmptyBinding.xaml#EmptyBinding)]

위의 예제에서는 빈 바인딩 구문인 {Binding}을 사용합니다. 이 경우 상위 <xref:System.Windows.Controls.ListBox> DockPanel 요소에서 DataContext를 상속합니다(이 예제에는 표시되지 않음). 경로를 지정하지 않으면 기본적으로 전체 개체에 바인딩됩니다. 즉, 이 예제에서는 속성을 전체 개체에 바인딩하기 때문에 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 경로가 제외되었습니다. 자세한 내용은 [컬렉션 바인딩](#binding-to-collections) 섹션을 참조하십시오.

컬렉션에 바인딩 외에 개체의 단일 속성만이 아닌 전체 개체에 바인딩하려는 경우에도 이 시나리오가 유용합니다. 예를 들어 소스 개체가 형식인 <xref:System.String>경우 문자열 자체에 바인딩할 수 있습니다. 또 다른 일반적인 시나리오는 여러 속성이 있는 개체에 요소를 바인딩하려는 경우입니다.

데이터가 바인딩된 대상 속성에 의미가 있도록 사용자 지정 논리를 적용해야 할 수 있습니다. 기본 형식 변환이 없는 경우 사용자 지정 논리는 사용자 지정 변환기의 형식일 수 있습니다. 변환에 대한 자세한 내용은 [데이터 변환을](#data-conversion) 참조하십시오.

### <a name="binding-and-bindingexpression"></a>Binding 및 BindingExpression

데이터 바인딩의 다른 기능과 사용법에 들어가기 전에 클래스를 <xref:System.Windows.Data.BindingExpression> 소개하는 것이 유용합니다. 이전 섹션에서 보았듯이 <xref:System.Windows.Data.Binding> 클래스는 바인딩 선언에 대한 상위 클래스입니다. 바인딩의 특성을 지정할 수 있는 많은 속성을 제공합니다. 관련 클래스는 <xref:System.Windows.Data.BindingExpression>소스와 대상 간의 연결을 유지하는 기본 개체입니다. 바인딩에는 여러 바인딩 식에서 공유될 수 있는 모든 정보가 포함됩니다. A는 <xref:System.Windows.Data.BindingExpression> 공유할 수 없고 <xref:System.Windows.Data.Binding>의 모든 인스턴스 정보를 포함하는 인스턴스 식입니다.

다음 `myDataObject` 예제를 고려 `MyData` 합니다. 클래스의 `myBinding` 인스턴스는 <xref:System.Windows.Data.Binding> 소스 `MyData` `MyDataProperty`개체이며. 이 예제에서는 `myText`의 텍스트 내용을 에 <xref:System.Windows.Controls.TextBlock>바인딩합니다. `MyDataProperty`

[!code-csharp[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/ManualBinding.cs#CodeOnlyBinding)]
[!code-vb[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/ManualBinding.vb#CodeOnlyBinding)]

같은 *myBinding* 개체를 사용하여 다른 바인딩을 만들 수 있습니다. 예를 들어 *myBinding* 개체를 사용하여 확인란의 텍스트 내용을 *MyDataProperty*에 바인딩할 수 있습니다. 이 시나리오에서는 *myBinding* 개체를 <xref:System.Windows.Data.BindingExpression> 공유 하는 두 개의 인스턴스가 있을 것입니다.

<xref:System.Windows.Data.BindingExpression> 개체는 데이터 바인딩된 개체를 호출하여 <xref:System.Windows.Data.BindingOperations.GetBindingExpression%2A> 반환됩니다. 다음 문서에서는 클래스의 일부 사용법중 <xref:System.Windows.Data.BindingExpression> 일부를 보여 줍니다.

- [바인딩된 대상 속성에서 바인딩 개체 가져오기](../../framework/wpf/data/how-to-get-the-binding-object-from-a-bound-target-property.md)

- [텍스트 상자 텍스트가 소스를 업데이트하는 경우 제어](../../framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md)

## <a name="data-conversion"></a>데이터 변환

바인딩 [만들기](#creating-a-binding) 섹션에서 해당 <xref:System.Windows.Controls.Control.Background%2A> 속성이 "Red" 값을 가진 문자열 속성에 바인딩되므로 단추는 빨간색입니다. 이 문자열 값은 문자열 값을 <xref:System.Windows.Media.Brush> <xref:System.Windows.Media.Brush>로 변환하는 형식 변환기가 형식에 있기 때문에 작동합니다.

이 정보를 그림에 추가하면 [바인딩 만들기](#creating-a-binding) 섹션이 다음과 같습니다.

![데이터 바인딩 기본 속성을 보여 주는 다이어그램입니다.](./media/data-binding-overview/data-binding-button-default-conversion.png)

그러나 바인딩 소스 개체에 형식 문자열의 속성이 있는 *Color* 대신 Color <xref:System.Windows.Media.Color>형식의 속성이 있는 경우? 이 경우 바인딩이 작동하려면 먼저 *Color* 속성 값을 속성에서 <xref:System.Windows.Controls.Control.Background%2A> 허용하는 것으로 바꿔야 합니다. 다음 예제와 같이 <xref:System.Windows.Data.IValueConverter> 인터페이스를 구현하여 사용자 지정 변환기를 만들어야 합니다.

[!code-csharp[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/ColorBrushConverter.cs#ColorBrushConverter)]
[!code-vb[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/ColorBrushConverter.vb#ColorBrushConverter)]

자세한 내용은 <xref:System.Windows.Data.IValueConverter>을 참조하세요.

이제 사용자 지정 변환기가 기본 변환 대신 사용되며 다이어그램은 다음과 같습니다.

![데이터 바인딩 사용자 지정 변환기를 보여 주는 다이어그램입니다.](./media/data-binding-overview/data-binding-converter-color-example.png)

다시 말하지만, 바인딩되는 형식에 있는 형식 변환기 때문에 기본 변환을 사용할 수 있습니다. 이 동작은 대상에서 사용할 수 있는 형식 변환기에 따라 결정됩니다. 확실하지 않으면 사용자 지정 변환기를 만듭니다.

다음은 데이터 변환기를 구현하는 것이 적합한 몇 가지 일반적인 시나리오입니다.

- 데이터를 문화권에 따라 다르게 표시해야 하는 경우. 예를 들어 특정 문화권에서 사용되는 규칙을 기반으로 통화 변환기 또는 달력 날짜/시간 변환기를 구현할 수 있습니다.

- 사용되는 데이터가 반드시 속성의 텍스트 값을 변경하는 데 사용될 필요는 없지만, 이미지의 소스 또는 표시 텍스트의 색이나 스타일과 같은 몇 가지 다른 값을 변경하는 데 사용되는 경우. 텍스트 필드를 표 셀의 Background 속성에 바인딩하는 것과 같이 적절해 보이지 않는 속성의 바인딩을 변환하는 방식으로 이 인스턴스에서 변환기를 사용할 수 있습니다.

- 둘 이상의 컨트롤 또는 컨트롤의 여러 속성이 동일한 데이터에 바인딩됩니다. 이 경우 기본 바인딩은 텍스트만 표시할 수 있는 반면, 기타 바인딩은 특정 표시 문제를 처리하지만 소스 정보와 같은 바인딩을 사용합니다.

- 대상 속성에는 바인딩 컬렉션이 <xref:System.Windows.Data.MultiBinding>있습니다. 의 <xref:System.Windows.Data.MultiBinding>경우 사용자 <xref:System.Windows.Data.IMultiValueConverter> 지정을 사용하여 바인딩 값에서 최종 값을 생성합니다. 예를 들어 빨간색, 파란색 및 녹색 값을 기준으로 색을 계산할 수 있고 이러한 값은 같거나 다른 바인딩 소스 개체의 값일 수 있습니다. 예제 <xref:System.Windows.Data.MultiBinding> 및 정보를 참조하십시오.

## <a name="binding-to-collections"></a>컬렉션에 바인딩

바인딩 소스 개체는 속성에 데이터가 포함된 단일 개체또는 데이터베이스에 대한 쿼리의 결과와 같이 종종 함께 그룹화되는 다형성 개체의 데이터 컬렉션으로 처리될 수 있습니다. 지금까지 단일 개체에 대한 바인딩에 대해서만 설명했습니다. 그러나 데이터 수집에 바인딩하는 것은 일반적인 시나리오입니다. 예를 들어, 일반적인 시나리오는 <xref:System.Windows.Controls.ItemsControl> <xref:System.Windows.Controls.ListBox>를 사용 <xref:System.Windows.Controls.ListView>하 <xref:System.Windows.Controls.TreeView> 여 를 사용 하는 것입니다 ., 또는 데이터 컬렉션을 표시 하는, 데이터 [바인딩](#what-is-data-binding) 섹션에 표시 된 응용 프로그램에 와 같은.

다행히도 기본 다이어그램이 적용됩니다. 컬렉션에 바인딩하는 <xref:System.Windows.Controls.ItemsControl> 경우 다이어그램은 다음과 같습니다.

![데이터 바인딩을 보여 주는 다이어그램 ItemsControl 개체입니다.](./media/data-binding-overview/data-binding-itemscontrol.png)

이 다이어그램에 표시된 <xref:System.Windows.Controls.ItemsControl> 것처럼 컬렉션 개체에 바인딩할 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A?displayProperty=nameWithType> 속성은 사용할 속성입니다. 의 `ItemsSource` 콘텐츠로 생각할 수 <xref:System.Windows.Controls.ItemsControl>있습니다. 바인딩은 <xref:System.Windows.Data.BindingMode.OneWay> 속성이 `ItemsSource` 기본적으로 `OneWay` 바인딩을 지원하기 때문입니다.

### <a name="how-to-implement-collections"></a>컬렉션을 구현하는 방법

인터페이스를 <xref:System.Collections.IEnumerable> 구현하는 모든 컬렉션을 열거할 수 있습니다. 그러나 컬렉션의 삽입 또는 삭제가 UI를 자동으로 업데이트하도록 동적 바인딩을 설정하려면 컬렉션에서 <xref:System.Collections.Specialized.INotifyCollectionChanged> 인터페이스를 구현해야 합니다. 이 인터페이스는 기본 컬렉션이 변경될 때마다 발생해야 하는 이벤트를 노출합니다.

WPF는 <xref:System.Collections.ObjectModel.ObservableCollection%601> 인터페이스를 노출하는 데이터 컬렉션의 기본 제공 구현인 <xref:System.Collections.Specialized.INotifyCollectionChanged> 클래스를 제공합니다. 원본 개체에서 대상으로 데이터 값 전송을 완벽하게 지원하려면 바인딩가능한 속성을 지원하는 컬렉션의 각 개체도 인터페이스를 <xref:System.ComponentModel.INotifyPropertyChanged> 구현해야 합니다. 자세한 내용은 [바인딩 소스 개요를](../../framework/wpf/data/binding-sources-overview.md)참조하십시오.

사용자 고유의 컬렉션을 구현하기 <xref:System.Collections.ObjectModel.ObservableCollection%601> 전에 <xref:System.Collections.Generic.List%601>에서와 <xref:System.Collections.ObjectModel.Collection%601>같은 기존 컬렉션 <xref:System.ComponentModel.BindingList%601>클래스 중 하나를 사용하거나 다른 많은 컬렉션 중 에서 사용하는 것이 좋습니다. 고급 시나리오가 있고 사용자 고유의 컬렉션을 구현하려는 <xref:System.Collections.IList>경우 인덱스에서 개별적으로 액세스할 수 있는 비일반 개체 컬렉션을 제공하는 을 사용하여 최상의 성능을 제공하는 것이 좋습니다.

### <a name="collection-views"></a>컬렉션 뷰

데이터 <xref:System.Windows.Controls.ItemsControl> 수집에 바인딩된 후에는 데이터를 정렬, 필터링 또는 그룹화할 수 있습니다. 이렇게 하려면 인터페이스를 구현하는 클래스인 컬렉션 뷰를 <xref:System.ComponentModel.ICollectionView> 사용합니다.

#### <a name="what-are-collection-views"></a>컬렉션 보기란 무엇입니까?

컬렉션 뷰는 기본 소스 컬렉션 자체를 변경할 필요 없이 정렬, 필터 및 그룹화 쿼리에 따라 소스 컬렉션을 탐색하고 표시할 수 있는 바인딩 소스 컬렉션의 최상위에 있는 레이어입니다. 컬렉션 뷰에서는 컬렉션의 현재 항목에 대한 포인터도 유지 관리합니다. 원본 컬렉션이 인터페이스를 <xref:System.Collections.Specialized.INotifyCollectionChanged> 구현하는 경우 이벤트에서 <xref:System.Collections.Specialized.INotifyCollectionChanged.CollectionChanged> 발생하는 변경 내용이 뷰에 전파됩니다.

뷰는 기본 소스 컬렉션을 변경하지 않으므로 각 소스 컬렉션에는 연결된 여러 뷰가 있을 수 있습니다. 예를 들어 *Task* 개체의 컬렉션이 있을 수 있습니다. 뷰를 사용하여 같은 데이터를 다양한 방식으로 표시할 수 있습니다. 예를 들어 페이지 왼쪽에는 우선 순위별로 정렬된 작업을 표시하고 오른쪽에는 영역별로 그룹화된 작업을 표시해야 할 수 있습니다.

#### <a name="how-to-create-a-view"></a>보기를 만드는 방법

뷰를 만들고 사용하는 한 가지 방법은 뷰 개체를 인스턴스화하고 이를 바인딩 소스로 사용하는 것입니다. 예를 들어 데이터 바인딩 섹션에 표시된 [데이터](#what-is-data-binding) [바인딩 데모][data-binding-demo] 앱을 고려합니다. 앱이 구현되어 데이터 <xref:System.Windows.Controls.ListBox> 수집 대신 데이터 수집을 통해 뷰에 직접 바인딩됩니다. 다음 예제는 [데이터 바인딩 데모][data-binding-demo] 앱에서 추출됩니다. 클래스는 <xref:System.Windows.Data.CollectionViewSource> <xref:System.Windows.Data.CollectionView>에서 상속되는 클래스의 XAML 프록시입니다. 이 특정 예제에서는 <xref:System.Windows.Data.CollectionViewSource.Source%2A> 뷰가 현재 앱 개체의 *AuctionItems* 컬렉션(형식)에 <xref:System.Collections.ObjectModel.ObservableCollection%601>바인딩됩니다.

[!code-xaml[CollectionView](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#CollectionView)]

그런 다음 리소스 *목록DataView는* 에서와 같은 앱의 요소에 <xref:System.Windows.Controls.ListBox>대한 바인딩 소스 역할을 합니다.

[!code-xaml[ListBoxCollectionView](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#ListBoxCollectionView)]

동일한 컬렉션에 대한 다른 뷰를 만들려면 다른 <xref:System.Windows.Data.CollectionViewSource> 인스턴스를 `x:Key` 만들고 다른 이름을 지정할 수 있습니다.

다음 표에서는 기본 컬렉션 보기또는 소스 컬렉션 형식에 <xref:System.Windows.Data.CollectionViewSource> 따라 생성되는 뷰 데이터 형식을 보여 주며 있습니다.

| 소스 컬렉션 형식                    | 컬렉션 뷰 형식 | 참고 |
| ----------------------------------------- | -------------------- | ----- |
| <xref:System.Collections.IEnumerable>     | 에 기반한 내부 형식<xref:System.Windows.Data.CollectionView> | 항목을 그룹화할 수 없습니다. |
| <xref:System.Collections.IList>           | <xref:System.Windows.Data.ListCollectionView> | 가장 빠릅니다. |
| <xref:System.ComponentModel.IBindingList> | <xref:System.Windows.Data.BindingListCollectionView> | |

#### <a name="using-a-default-view"></a>기본 보기 사용

컬렉션 뷰를 만들고 사용하는 한 가지 방법은 컬렉션 뷰를 바인딩 소스로 지정하는 것입니다. WPF에서도 바인딩 소스로 사용되는 모든 컬렉션에 대한 기본 컬렉션 뷰를 만듭니다. 컬렉션에 직접 바인딩할 경우 WPF는 기본 뷰에 바인딩됩니다. 이 기본 보기는 동일한 컬렉션에 대한 모든 바인딩에서 공유되므로 하나의 바인딩 된 컨트롤 또는 코드(예: 정렬 또는 나중에 설명한 현재 항목 포인터 변경)에 의해 기본 뷰에 대한 변경이 동일한 컬렉션의 다른 모든 바인딩에 반영됩니다.

기본 보기를 얻으려면 메서드를 <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> 사용합니다. 예를 들어 [데이터 컬렉션의 기본 보기 받기를](../../framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md)참조하십시오.

#### <a name="collection-views-with-adonet-datatables"></a>ADO.NET 데이터 테이블을 사용하여 컬렉션 보기

성능을 향상시키기 위해 ADO.NET <xref:System.Data.DataTable> 또는 <xref:System.Data.DataView> 개체에 대한 컬렉션 뷰는 데이터 원본의 모든 컬렉션 뷰에서 정렬 및 필터링을 공유하도록 하는 <xref:System.Data.DataView>에 대한 정렬 및 필터링을 위임합니다. 각 컬렉션 뷰가 독립적으로 정렬 및 필터링할 수 있도록 <xref:System.Data.DataView> 하려면 고유한 개체를 사용하여 각 컬렉션 뷰를 초기화합니다.

#### <a name="sorting"></a>정렬

앞에서 설명한 대로 뷰에서는 컬렉션에 정렬 순서를 적용할 수 있습니다. 기본 컬렉션에 있는 데이터에는 관련 상속 순서가 있거나 없을 수도 있습니다. 컬렉션에 대한 뷰를 통해 제공한 비교 기준에 따라 순서를 적용하거나 기본 순서를 변경할 수 있습니다. 이는 데이터의 클라이언트 기반 뷰이므로 일반적으로 열과 일치하는 값에 따라 표 형식 데이터의 열을 정렬해야 할 수 있습니다. 뷰를 사용하면 기본 컬렉션을 변경하거나 컬렉션 콘텐츠를 다시 쿼리할 필요 없이 이 사용자 기반 정렬을 적용할 수 있습니다. 예를 들어 [헤더를 클릭할 때 GridView 열 정렬을 참조하세요.](../../framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)

다음 예제에서는 데이터 <xref:System.Windows.Controls.CheckBox> [바인딩](#what-is-data-binding) 섹션에서 앱 UI의 "범주별 및 날짜별로 정렬"의 정렬 논리를 보여 주며 있습니다.

[!code-csharp[AddSortChecked](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#AddSortChecked)]
[!code-vb[AddSortChecked](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#AddSortChecked)]

#### <a name="filtering"></a>필터링

뷰는 전체 컬렉션의 특정 하위 집합만 표시되도록 컬렉션에 필터를 적용할 수도 있습니다. 데이터에서 조건에 따라 필터링할 수 있습니다. 예를 들어 데이터 [바인딩](#what-is-data-binding) 섹션의 앱에서 수행하는 것처럼 "거래만 표시"에는 <xref:System.Windows.Controls.CheckBox> $25 이상의 비용이 드는 항목을 필터링하는 논리가 포함되어 있습니다. 다음 코드는 *ShowOnlyBargainsFilter를* 선택된 <xref:System.Windows.Data.CollectionViewSource.Filter> <xref:System.Windows.Controls.CheckBox> 경우 이벤트 처리기로 설정하기 위해 실행됩니다.

[!code-csharp[ListingViewFilter](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#ListingViewFilter)]
[!code-vb[ListingViewFilter](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#ListingViewFilter)]

*ShowOnlyBargainsFilter* 이벤트 처리기에는 다음과 같은 구현이 있습니다.

[!code-csharp[FilterEvent](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#FilterEvent)]
[!code-vb[FilterEvent](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#FilterEvent)]

의 <xref:System.Windows.Data.CollectionView> 클래스 중 하나를 직접 사용하는 경우 속성을 <xref:System.Windows.Data.CollectionView.Filter%2A> 사용하여 콜백을 지정합니다. <xref:System.Windows.Data.CollectionViewSource> 예제를 보려면 [뷰에서 데이터 필터링](../../framework/wpf/data/how-to-filter-data-in-a-view.md)을 참조하세요.

#### <a name="grouping"></a>Grouping(그룹화)

<xref:System.Collections.IEnumerable> 컬렉션을 보는 내부 클래스를 제외하고 모든 컬렉션 뷰는 컬렉션 뷰에서 컬렉션을 논리 그룹으로 분할할 수 있는 지원 *그룹화입니다.* 그룹은 사용자가 그룹 목록을 제공하는 경우 명시적 그룹이고 데이터에 따라 그룹이 동적으로 생성되는 경우 암시적 그룹입니다.

다음 예제에서는 "범주별 그룹"의 <xref:System.Windows.Controls.CheckBox>논리를 보여 주며 있습니다.

[!code-csharp[ListingGroupCheck](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#ListingGroupCheck)]
[!code-vb[ListingGroupCheck](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#ListingGroupCheck)]

다른 그룹화 예제를 보려면 [GridView를 구현하는 ListView의 항목 그룹화](../../framework/wpf/controls/how-to-group-items-in-a-listview-that-implements-a-gridview.md)를 참조하세요.

#### <a name="current-item-pointers"></a>현재 항목 포인터

뷰는 현재 항목의 개념도 지원합니다. 컬렉션 뷰에서 개체를 탐색할 수 있습니다. 탐색할 때 컬렉션의 특정 위치에 있는 개체를 검색할 수 있는 항목 포인터를 이동합니다. 예를 들어 [데이터 CollectionView의 개체 탐색을](../../framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md)참조하십시오.

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

컬렉션에 적용되는 정렬이나 필터링이 현재 항목 포인터에 영향을 미칠 수 있습니다. 정렬은 현재 항목 포인터를 선택된 마지막 항목에 유지하지만 이제 컬렉션 뷰는 포인터를 중심으로 재구성됩니다. 선택한 항목이 이전에 목록의 시작 부분에 있었지만 이제 선택한 항목이 중간 어딘가에 있을 수 있습니다. 필터링은 필터링 후 해당 선택이 뷰에 남아 있는 경우 선택한 항목을 유지합니다. 남아 있지 않으면 현재 항목 포인터는 필터링된 컬렉션 뷰의 첫 번째 항목으로 설정됩니다.

#### <a name="master-detail-binding-scenario"></a>마스터 세부 바인딩 시나리오

현재 항목의 개념은 컬렉션에서 항목을 탐색하는 경우뿐 아니라 마스터-세부 바인딩 시나리오에도 유용합니다. 데이터 바인딩 섹션에서 [앱](#what-is-data-binding) UI를 다시 고려합니다. 해당 앱에서 선택 영역은 <xref:System.Windows.Controls.ListBox> <xref:System.Windows.Controls.ContentControl>에 표시된 내용을 결정합니다. 다른 방법으로 항목을 선택하면 <xref:System.Windows.Controls.ListBox> 선택한 항목의 <xref:System.Windows.Controls.ContentControl> 세부 정보가 표시됩니다.

간단히 두 개 이상의 컨트롤을 같은 뷰에 바인딩하여 마스터-세부 시나리오를 구현할 수 있습니다. [데이터 바인딩 데모의][data-binding-demo] 다음 예제에서는 데이터 <xref:System.Windows.Controls.ListBox> 바인딩 <xref:System.Windows.Controls.ContentControl> 섹션에서 앱 UI에 표시되는 태그와 의 태그를 보여 주며, 이 [태그는 다음과 같은](#what-is-data-binding) 내용을 보여 주며,

[!code-xaml[ListBoxContentControl](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#ListBoxContentControl)]

두 컨트롤모두 동일한 소스인 *listingDataView* 정적 리소스에 바인딩되어 있습니다(뷰 를 [만드는 방법 섹션에서](#how-to-create-a-view)이 리소스의 정의 참조). 이 바인딩은 단일 <xref:System.Windows.Controls.ContentControl> 개체(이 경우)가 컬렉션 뷰에 바인딩될 때 <xref:System.Windows.Data.CollectionView.CurrentItem%2A> 뷰의 에 자동으로 바인딩되기 때문에 작동합니다. 개체는 <xref:System.Windows.Data.CollectionViewSource> 자동으로 통화 및 선택 항목을 동기화합니다. 목록 컨트롤이 이 예제와 <xref:System.Windows.Data.CollectionViewSource> 같이 개체에 바인딩되지 않은 경우 <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> 이 `true` 작업을 수행하도록 해당 속성을 설정해야 합니다.

다른 예에서는 [컬렉션에 바인딩하고 선택을 기반으로 정보를 표시하고](../../framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md) [계층 적 데이터와 마스터 세부 정보 패턴을 사용합니다.](../../framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)

위 예제에서는 템플릿을 사용합니다. 실제로 데이터는 템플릿(명시적으로 사용되는 <xref:System.Windows.Controls.ContentControl> 템플릿과 암시적으로 사용되는 <xref:System.Windows.Controls.ListBox>템플릿)을 사용하지 않고는 원하는 방식으로 표시되지 않습니다. 이제 다음 섹션에서 데이터 템플릿을 살펴보겠습니다.

## <a name="data-templating"></a>데이터 템플릿

데이터 템플릿을 사용하지 않으면 [데이터 바인딩](#what-is-data-binding) 섹션의 앱 UI가 다음과 같습니다.

![데이터 템플릿을 사용하지 않는 데이터 바인딩 데모](./media/data-binding-overview/demo-no-template.png)

이전 섹션의 예제와 같이 <xref:System.Windows.Controls.ListBox> 컨트롤과 <xref:System.Windows.Controls.ContentControl> 컨트롤은 *AuctionItem*s의 전체 컬렉션 개체(또는 보다 구체적으로 는 컬렉션 개체에 대한 뷰)에 바인딩됩니다. 데이터 컬렉션을 표시하는 방법에 대한 구체적인 <xref:System.Windows.Controls.ListBox> 지침이 없으면 기본 컬렉션에 각 개체의 문자열 표현이 표시되고 바인딩된 개체의 문자열 표현이 <xref:System.Windows.Controls.ContentControl> 표시됩니다.

이 문제를 해결하기 위해 앱은 을 정의합니다. <xref:System.Windows.DataTemplate?text=DataTemplates> 이전 섹션의 예제와 같이 명시적으로 <xref:System.Windows.Controls.ContentControl> 세부 *정보를 사용합니다ProductListingTemplate* 데이터 템플릿. 컨트롤은 <xref:System.Windows.Controls.ListBox> 컬렉션에 *AuctionItem* 개체를 표시할 때 다음 데이터 템플릿을 암시적으로 사용합니다.

[!code-xaml[AuctionItemDataTemplate](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#AuctionItemDataTemplate)]

이 두 데이터 템플릿을 사용하면 결과 UI가 [데이터 바인딩](#what-is-data-binding) 섹션에 표시됩니다. 이 스크린샷에서 볼 수 있듯이 DataTemplate를 사용하면 컨트롤에 데이터를 배치할 수 있을 뿐만 아니라 데이터에 대한 강력한 시각적 개체를 정의할 수 있습니다. <xref:System.Windows.DataTrigger>예를 들어, s는 위에서 <xref:System.Windows.DataTemplate> 사용되므로 SpecialFeatures 값인 *HighLight값이* 있는 *SpecialFeatures* *경매항목*s가 주황색 테두리와 별색으로 표시됩니다.

데이터 템플릿에 대한 자세한 내용은 [데이터 템플릿 개요를](../../framework/wpf/data/data-templating-overview.md)참조하십시오.

## <a name="data-validation"></a>데이터 유효성 검사

사용자 입력을 받는 대부분의 앱에는 사용자가 예상정보를 입력했는지 확인하기 위해 유효성 검사 논리가 있어야 합니다. 유효성 검사는 유형, 범위, 형식 또는 기타 앱별 요구 사항을 기반으로 할 수 있습니다. 이 섹션에서는 WPF에서 데이터 유효성 검사가 작동하는 방식에 대해 설명합니다.

### <a name="associating-validation-rules-with-a-binding"></a>유효성 검사 규칙과 바인딩 연결

WPF 데이터 바인딩 모델을 사용하면 <xref:System.Windows.Data.Binding.ValidationRules%2A> 개체와 연결할 수 있습니다. <xref:System.Windows.Data.Binding> 예를 들어 다음 예제에서는 <xref:System.Windows.Controls.TextBox> a를 명명된 `StartPrice` 속성에 바인딩하고 <xref:System.Windows.Controls.ExceptionValidationRule> <xref:System.Windows.Data.Binding.ValidationRules%2A?displayProperty=nameWithType> 속성에 개체를 추가합니다.

[!code-xaml[TextboxStartPrice](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#TextboxStartPrice)]

개체는 <xref:System.Windows.Controls.ValidationRule> 속성값이 유효한지 여부를 확인합니다. WPF에는 두 가지 유형의 기본 제공 <xref:System.Windows.Controls.ValidationRule> 개체가 있습니다.

- 바인딩 <xref:System.Windows.Controls.ExceptionValidationRule> 소스 속성을 업데이트하는 동안 throw된 예외를 검사합니다. 이전 예제에서 `StartPrice`는 정수 형식입니다. 사용자가 정수로 변환될 수 없는 값을 입력하면 예외가 throw되어 바인딩이 잘못된 것으로 표시됩니다. 설정 하는 대체 구문은 <xref:System.Windows.Controls.ExceptionValidationRule> 명시적으로 설정 하는 것을 <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> 속성을 `true` 에서 프로그램 <xref:System.Windows.Data.Binding> 또는 <xref:System.Windows.Data.MultiBinding> 개체입니다.

- 개체는 <xref:System.Windows.Controls.DataErrorValidationRule> <xref:System.ComponentModel.IDataErrorInfo> 인터페이스를 구현하는 개체에서 발생하는 오류를 확인합니다. 이 유효성 검사 규칙을 사용하는 <xref:System.Windows.Controls.DataErrorValidationRule>예제는 을 참조하십시오. 설정 하는 대체 구문은 <xref:System.Windows.Controls.DataErrorValidationRule> 명시적으로 설정 하는 것을 <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> 속성을 `true` 에서 프로그램 <xref:System.Windows.Data.Binding> 또는 <xref:System.Windows.Data.MultiBinding> 개체입니다.

클래스에서 파생 하 고 메서드를 <xref:System.Windows.Controls.ValidationRule> <xref:System.Windows.Controls.ValidationRule.Validate%2A> 구현 하 여 사용자 고유의 유효성 검사 규칙을 만들 수도 있습니다. 다음 예제에서는 데이터 바인딩 섹션에서 *제품 목록* 추가 <xref:System.Windows.Controls.TextBox> "시작 날짜"에서 사용하는 규칙을 보여 주며 [있습니다.](#what-is-data-binding)

[!code-csharp[FutureDateRule](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/FutureDateRule.cs#FutureDateRule)]
[!code-vb[FutureDateRule](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/FutureDateRule.vb#FutureDateRule)]

*StartDateEntryForm은* <xref:System.Windows.Controls.TextBox> 다음 예제와 같이 이 *FutureDateRule을*사용합니다.

[!code-xaml[TextboxStartDate](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#TextboxStartDate)]

<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값이 이기 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>때문에 바인딩 엔진은 모든 키 입력에 대한 소스 값을 업데이트하므로 모든 키 입력에서 컬렉션의 <xref:System.Windows.Data.Binding.ValidationRules%2A> 모든 규칙을 검사합니다. 이 내용은 유효성 검사 프로세스 섹션에서 자세히 설명합니다.

### <a name="providing-visual-feedback"></a>시각적 피드백 제공

사용자가 잘못된 값을 입력하는 경우 앱 UI의 오류에 대한 몇 가지 피드백을 제공할 수 있습니다. 이러한 피드백을 제공하는 한 가지 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> 방법은 연결된 속성을 <xref:System.Windows.Controls.ControlTemplate>사용자 지정으로 설정하는 것입니다. 이전 하위 섹션에 표시된 것처럼 *StartDateEntryForm은* <xref:System.Windows.Controls.TextBox> 유효성 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> *검사*템플릿이라는 것을 사용합니다. 다음 예제에서는 유효성 검사의 정의를 보여 *주다Template*.

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#ControlTemplate)]

요소는 <xref:System.Windows.Controls.AdornedElementPlaceholder> 장식할 컨트롤을 배치할 위치를 지정합니다.

또한 a를 <xref:System.Windows.Controls.ToolTip> 사용하여 오류 메시지를 표시할 수도 있습니다. *StartDateEntryForm* 및 *StartPriceEntryForm*<xref:System.Windows.Controls.TextBox>es 스타일 *텍스트스타일텍스트박스를*사용하여 오류 메시지를 표시하는 을 <xref:System.Windows.Controls.ToolTip> 만듭니다. 다음 예제에서는 *textStyleTextBox*의 정의를 보여 줍니다. 연결된 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 속성은 `true` 바인딩된 요소의 속성에 대한 하나 이상의 바인딩에 오류가 있는 경우입니다.

[!code-xaml[TextBoxStyle](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#TextBoxStyle)]

사용자 지정 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 및 <xref:System.Windows.Controls.ToolTip>를 사용하면 *StartDateEntryForm* <xref:System.Windows.Controls.TextBox> 유효성 검사 오류가 있을 때 다음과 같이 표시됩니다.

![데이터 바인딩 유효성 검사 오류](./media/data-binding-overview/demo-validation-date.png "DataBindingDemo_Validation")

<xref:System.Windows.Data.Binding> 연결된 유효성 검사 규칙이 있지만 바인딩된 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 컨트롤을 지정하지 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 않은 경우 유효성 검사 오류가 있을 때 사용자에게 알리는 기본값이 사용됩니다. 기본값은 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 표시기 레이어에서 빨간색 테두리를 정의하는 컨트롤 템플릿입니다. 기본값과 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> <xref:System.Windows.Controls.ToolTip>에서 는 유효성 검사 오류가 있을 때 *StartPriceEntryForm의* <xref:System.Windows.Controls.TextBox> UI는 다음과 같습니다.

![데이터 바인딩 유효성 검사 오류](./media/data-binding-overview/demo-validation-price.png "DataBindingDemo_ValidationDefault")

대화 상자의 모든 컨트롤의 유효성을 검사하는 논리를 제공하는 방법의 예는 대화 [상자 개요의](../../framework/wpf/app-development/dialog-boxes-overview.md)사용자 지정 대화 상자 섹션을 참조하십시오.

### <a name="validation-process"></a>유효성 검사 프로세스

유효성 검사는 대개 대상 값이 바인딩 소스 속성에 전송될 때 수행됩니다. 이 전송은 <xref:System.Windows.Data.BindingMode.TwoWay> <xref:System.Windows.Data.BindingMode.OneWayToSource> 켜지고 바인딩됩니다. 다시 말해서 소스 업데이트의 원인은 소스 업데이트 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 를 [트리거하는 정보](#what-triggers-source-updates) 섹션에 설명된 대로 속성값에 따라 달라집니다.

다음 항목은 *유효성 검사* 프로세스를 설명합니다. 이 프로세스 중에 언제든지 유효성 검사 오류 또는 다른 유형의 오류가 발생하면 프로세스가 중지됩니다.

1. 바인딩 <xref:System.Windows.Controls.ValidationRule> 엔진은 정의된 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> <xref:System.Windows.Controls.ValidationStep.RawProposedValue> 사용자 지정 개체가 있는지 <xref:System.Windows.Data.Binding>확인하며, 이 경우 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 둘 중 <xref:System.Windows.Controls.ValidationRule> 하나가 오류가 발생하거나 모든 개체가 통과될 때까지 각각에 대한 메서드를 호출합니다.

2. 그런 다음 바인딩 엔진은 변환기를 호출합니다(있는 경우).

3. 변환기가 성공하면 바인딩 엔진은 <xref:System.Windows.Controls.ValidationRule> 정의된 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> <xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue> <xref:System.Windows.Data.Binding>사용자 지정 개체가 있는지 확인하며, 이 경우 해당 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 개체 <xref:System.Windows.Controls.ValidationRule> 중 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> 하나가 오류가 발생하거나 모든 개체가 통과될 때까지 설정된 각 메서드에 대한 메서드를 <xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue> 호출합니다.

4. 바인딩 엔진은 소스 속성을 설정합니다.

5. 바인딩 <xref:System.Windows.Controls.ValidationRule> 엔진은 정의된 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> <xref:System.Windows.Controls.ValidationStep.UpdatedValue> 사용자 지정 개체가 있는지 <xref:System.Windows.Data.Binding>확인하며, 이 경우 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 해당 개체 <xref:System.Windows.Controls.ValidationRule> 중 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> 하나가 오류가 발생하거나 모든 개체가 통과될 때까지 설정된 각 메서드에 메서드를 <xref:System.Windows.Controls.ValidationStep.UpdatedValue> 호출합니다. a가 <xref:System.Windows.Controls.DataErrorValidationRule> 바인딩과 연결되고 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> 바인딩이 기본값으로 <xref:System.Windows.Controls.ValidationStep.UpdatedValue>설정된 <xref:System.Windows.Controls.DataErrorValidationRule> 경우 이 시점에서 확인됩니다. 이 시점에서 집합이 <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> 있는 모든 `true` 바인딩이 검사됩니다.

6. 바인딩 <xref:System.Windows.Controls.ValidationRule> 엔진은 정의된 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> <xref:System.Windows.Controls.ValidationStep.CommittedValue> 사용자 지정 개체가 있는지 <xref:System.Windows.Data.Binding>확인하며, 이 경우 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 해당 개체 <xref:System.Windows.Controls.ValidationRule> 중 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> 하나가 오류가 발생하거나 모든 개체가 통과될 때까지 설정된 각 메서드에 메서드를 <xref:System.Windows.Controls.ValidationStep.CommittedValue> 호출합니다.

이 <xref:System.Windows.Controls.ValidationRule> 프로세스 전체에서 a가 언제든지 통과하지 못하면 바인딩 <xref:System.Windows.Controls.ValidationError> 엔진은 개체를 <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> 만들고 바인딩된 요소의 컬렉션에 추가합니다. 바인딩 엔진이 지정된 <xref:System.Windows.Controls.ValidationRule> 단계에서 개체를 실행하기 전에 <xref:System.Windows.Controls.ValidationError> 해당 단계에서 <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> 바인딩된 요소의 연결된 속성에 추가된 모든 개체를 제거합니다. 예를 들어, <xref:System.Windows.Controls.ValidationRule> 실패로 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> <xref:System.Windows.Controls.ValidationStep.UpdatedValue> 설정된 a가 다음에 유효성 검사 프로세스가 발생할 때 <xref:System.Windows.Controls.ValidationError> 바인딩 엔진은 <xref:System.Windows.Controls.ValidationRule> <xref:System.Windows.Controls.ValidationStep.UpdatedValue>로 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> 설정된 것을 호출하기 직전에 제거합니다.

때 <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> 비어 있지 않으며이 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 요소의 속성이 `true`합니다. 또한 경우를 <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A> 의 속성을 <xref:System.Windows.Data.Binding> 로 설정 되어 `true`, 바인딩 엔진을 <xref:System.Windows.Controls.Validation.Error?displayProperty=nameWithType> 요소에서 연결 된 이벤트.

또한 어느 방향으로든 유효한 값 전송(원본에서 대상으로 또는 대상에 대한 대상)은 <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> 연결된 속성을 지웁니다.

바인딩에 연결되었거나 <xref:System.Windows.Controls.ExceptionValidationRule> 속성이 <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> 설정되어 `true` 있고 바인딩 엔진이 소스를 설정할 때 예외가 throw된 경우 바인딩 엔진은 <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>을 참조하여 이 가 있는지 확인합니다. <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> 콜백을 사용하여 예외 처리를 위한 사용자 지정 처리기를 제공할 수 있습니다. 경우는 <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> 에 지정 되어 있지는 <xref:System.Windows.Data.Binding>, 바인딩 엔진에서 만드는 <xref:System.Windows.Controls.ValidationError> 예외를 사용 하 여에 추가 <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> 바인딩된 요소의 컬렉션입니다.

## <a name="debugging-mechanism"></a>디버깅 메커니즘

바인딩 관련 개체에 <xref:System.Diagnostics.PresentationTraceSources.TraceLevel%2A?displayProperty=nameWithType> 연결된 속성을 설정하여 특정 바인딩의 상태에 대한 정보를 받을 수 있습니다.

## <a name="see-also"></a>참조

- <xref:System.Windows.Controls.DataErrorValidationRule>
- [LINQ 쿼리결과에 바인딩](../../framework/wpf/data/how-to-bind-to-the-results-of-a-linq-query.md)
- [데이터 바인딩](../../framework/wpf/advanced/optimizing-performance-data-binding.md)
- [데이터 바인딩 데모][data-binding-demo]
- [방법 기사](../../framework/wpf/data/data-binding-how-to-topics.md)
- [ADO.NET 데이터 원본 바인딩](../../framework/wpf/data/how-to-bind-to-an-ado-net-data-source.md)

[data-binding-demo]: https://github.com/microsoft/WPF-Samples/tree/master/Sample%20Applications/DataBindingDemo "데이터 바인딩 데모 앱"

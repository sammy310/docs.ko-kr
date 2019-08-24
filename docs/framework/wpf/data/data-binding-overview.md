---
title: 데이터 바인딩 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data conversion for binding [WPF]
- binding data [WPF], about data binding
- data binding [WPF], about data binding
- conversion for data binding [WPF]
ms.assetid: c707c95f-7811-401d-956e-2fffd019a211
ms.openlocfilehash: 44a35131273c6f191ab5da5bc1639d97bd961ff1
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567519"
---
# <a name="data-binding-overview"></a>데이터 바인딩 개요
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 데이터 바인딩은 응용 프로그램이 데이터를 제공하고 상호 작용할 수 있는 간단하고 일관된 방법을 제공합니다. 요소는 CLR (공용 언어 런타임) 개체 및 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]의 형식으로 다양 한 데이터 소스의 데이터에 바인딩될 수 있습니다. <xref:System.Windows.Controls.ContentControl>및와 같은 및에는 단일 데이터 항목 또는 데이터 항목 컬렉션의 유연한 스타일을 사용할 수 있도록 하는 기본 제공 기능이 포함되어있습니다.<xref:System.Windows.Controls.ListView> <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.ItemsControl> <xref:System.Windows.Controls.ListBox> 데이터를 기반으로 정렬, 필터 및 그룹 보기를 생성할 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 데이터 바인딩 기능은 기본적으로 데이터 바인딩을 지원하는 광범위한 속성, 데이터의 유연한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 표현 및 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]와 비즈니스 논리의 분명한 분리와 같은 기존 모델에 비해 여러 가지 이점이 있습니다.  
  
 이 항목에서는 먼저 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 데이터 바인딩의 기본 개념에 대해 설명한 다음 <xref:System.Windows.Data.Binding> 클래스 및 데이터 바인딩의 다른 기능을 사용 하는 방법에 대해 설명 합니다.  

<a name="what_is_data_binding"></a>   
## <a name="what-is-data-binding"></a>데이터 바인딩이란?  
 데이터 바인딩은 애플리케이션 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]와 비즈니스 논리를 연결하는 프로세스입니다. 바인딩 설정이 올바르고 데이터가 적절한 알림을 제공하는 경우에는 데이터의 값이 변경될 때 데이터에 바인딩된 요소에 변경 내용이 자동으로 반영됩니다. 또한 요소에서 데이터의 외부 표현이 변경되면 내부 데이터가 자동으로 업데이트되어 변경 내용이 반영될 수 있습니다. 예를 들어 사용자가 <xref:System.Windows.Controls.TextBox> 요소에서 값을 편집 하는 경우 해당 변경 내용을 반영 하도록 기본 데이터 값이 자동으로 업데이트 됩니다.  
  
 데이터 바인딩은 일반적으로 서버 또는 로컬 구성 데이터를 폼이나 기타 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 컨트롤에 배치하는 데 사용됩니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 이 개념은 광범위한 속성을 다양한 데이터 소스에 바인딩하는 기능을 포함하도록 확장됩니다. 에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]요소의 종속성 속성은 CLR 개체 (ADO.NET 개체 또는 웹 서비스와 웹 속성과 연결 된 개체 포함) 및 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터에 바인딩될 수 있습니다.  
  
 데이터 바인딩의 예는 [Data Binding Demo](https://go.microsoft.com/fwlink/?LinkID=163703)(데이터 바인딩 데모)에서 다음 애플리케이션 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 살펴보세요.  
  
 ![데이터 바인딩 샘플 스크린샷](./media/databinding-databindingdemo.png "DataBinding_DataBindingDemo")  
  
 위 그림은 작업 항목 목록을 표시하는 애플리케이션의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]입니다. 애플리케이션은 데이터 바인딩의 다음 기능을 보여 줍니다.  
  
- 의 <xref:System.Windows.Controls.ListBox> 콘텐츠는 *AuctionItem* 개체의 컬렉션에 바인딩됩니다. *AuctionItem* 개체에는 *Description*, *StartPrice*, *StartDate*, *Category*, *SpecialFeatures* 등의 속성이 있습니다.  
  
- 에<xref:System.Windows.Controls.ListBox> 표시 되는 데이터 (*AuctionItem* 개체)는 템플릿 기반 이므로 각 항목에 대 한 설명 및 현재 가격은 표시 됩니다. 을 <xref:System.Windows.DataTemplate>사용 하 여이 작업을 수행 합니다. 또한 각 항목의 모양은 표시되는 *AuctionItem*의 *SpecialFeatures* 값에 따라 달라집니다. *AuctionItem*의 *SpecialFeatures* 값이 *Color*이면 항목에는 파란색 테두리가 포함됩니다. *Highlight* 값이면 항목에는 주황색 테두리와 별모양이 포함됩니다. [데이터 템플릿](#data_templating) 섹션에서는 데이터 템플릿을 살펴봅니다.  
  
- 사용자는 제공 된 <xref:System.Windows.Controls.CheckBox>es를 사용 하 여 데이터를 그룹화, 필터링 또는 정렬할 수 있습니다. 위의 이미지에서는 "범주별로 그룹화" 및 "범주 및 날짜별 정렬" <xref:System.Windows.Controls.CheckBox>es가 선택 됩니다. 데이터가 제품 범주에 따라 그룹화되고 범주 이름이 사전순으로 표시되어 있음을 알 수 있습니다. 그림에서 확인하기는 어렵지만 항목은 각 범주 내에서 시작 날짜별로 정렬됩니다. 이 작업에는 *컬렉션 뷰*가 사용됩니다. [컬렉션에 바인딩](#binding_to_collections) 섹션에서는 컬렉션 뷰를 살펴봅니다.  
  
- 사용자가 항목을 선택 하면에서 <xref:System.Windows.Controls.ContentControl> 선택한 항목의 세부 정보를 표시 합니다. 이를 *마스터-세부 시나리오*라고 합니다. [마스터-세부 시나리오Scenario](#master_detail_scenario) 섹션에서는 바인딩 시나리오 유형을 살펴봅니다.  
  
- 날짜/시간 속성 의 형식은 밀리초 <xref:System.DateTime>에 대 한 시간을 포함 하는 날짜를 반환 하는입니다. 이 애플리케이션에는 더 짧은 날짜 문자열이 표시되도록 사용자 지정 변환기가 사용되었습니다. [데이터 변환](#data_conversion) 섹션에서는 변환기를 살펴봅니다.  
  
 사용자가 *Add Product* 단추를 클릭하면 다음과 같이 표시됩니다.  
  
 ![제품 목록 추가 페이지](./media/databinding-demo-addproductlisting.png "DataBinding_Demo_AddProductListing")  
  
 사용자는 폼에 있는 필드를 편집하고, 짧은 미리 보기와 더 자세한 미리 보기 창을 사용하여 제품 목록을 미리 보고, *submit*을 클릭하여 새 제품 목록을 추가할 수 있습니다. 기존 그룹화, 필터링 및 정렬 기능이 새 항목에 적용됩니다. 이 경우 위 그림에 입력된 항목은 *Computer* 범주에서 두 번째 항목으로 표시됩니다.  
  
 이 이미지에 표시 되지 않는 유효성 검사 논리는 *시작 날짜* <xref:System.Windows.Controls.TextBox>에 제공 됩니다. 사용자가 잘못 된 날짜 (잘못 된 형식 또는 과거 날짜)를 입력 하는 경우 사용자 <xref:System.Windows.Controls.ToolTip> 에 <xref:System.Windows.Controls.TextBox>게 및 옆에 빨간색 느낌표가 표시 됩니다. [데이터 유효성 검사](#data_validation) 섹션에서는 유효성 검사 논리를 만드는 방법을 설명합니다.  
  
 위에서 간략히 설명한 데이터 바인딩의 다른 기능을 살펴보기 전에 먼저 다음 섹션에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 데이터 바인딩 이해에 필수적인 기본 개념을 설명합니다.  
  
## <a name="basic-data-binding-concepts"></a>기본 데이터 바인딩 개념  
  
 바인딩할 요소 및 데이터 소스의 특성에 관계없이 각 바인딩은 항상 다음 그림에 나와 있는 모델을 따릅니다.  
  
 ![기본 데이터 바인딩 모델을 보여 주는 다이어그램입니다.](./media/data-binding-overview/basic-data-binding-diagram.png)  
  
 위 그림과 같이 데이터 바인딩은 기본적으로 바인딩 대상과 바인딩 소스를 연결합니다. 그림에서는 다음 기본 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 데이터 바인딩 개념을 보여 줍니다.  
  
- 일반적으로 각 바인딩에는 네 가지 구성 요소인 바인딩 대상 개체, 대상 속성, 바인딩 소스 및 사용할 바인딩 소스의 값 경로가 있습니다. 예를 들어의 <xref:System.Windows.Controls.TextBox> 콘텐츠를 *Employee* 개체의 <xref:System.Windows.Controls.TextBox> *Name* 속성에 바인딩하려는 경우 대상 개체는이 고, target 속성 <xref:System.Windows.Controls.TextBox.Text%2A> 은 속성, 사용할 값은 *Name*및입니다. 원본 개체는 *Employee* 개체입니다.  
  
- 대상 속성은 종속성 속성이어야 합니다. 대부분 <xref:System.Windows.UIElement> 의 속성은 종속성 속성 이며 읽기 전용 속성을 제외 하 고 대부분의 종속성 속성은 기본적으로 데이터 바인딩을 지원 합니다. 형식만 종속성 속성을 정의할 수 있으며 모든 <xref:System.Windows.UIElement>는에서 <xref:System.Windows.DependencyObject>파생 됩니다. <xref:System.Windows.DependencyObject>  
  
- 그림에는 지정 되지 않았지만 바인딩 소스 개체는 사용자 지정 CLR 개체로 제한 되지 않습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]데이터 바인딩은 CLR 개체 및 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]형식의 데이터를 지원 합니다. 몇 가지 예를 제공 하기 위해 바인딩 소스는 <xref:System.Windows.UIElement>, 모든 목록 개체, ADO.NET 데이터 또는 웹 서비스와 연결 된 CLR 개체 또는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터를 포함 하는 XmlNode 일 수 있습니다. 자세한 내용은 [바인딩 소스 개요](binding-sources-overview.md)를 참조하세요.  
  
 다른 SDK 항목을 읽을 때 바인딩을 설정 하는 경우 바인딩 대상을 바인딩 소스 *에* 바인딩하는 것을 기억해 야 합니다. 예 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 를 들어 데이터 바인딩을 <xref:System.Windows.Controls.ListBox> 사용 하 여에 일부 기본 데이터를 표시 하는 경우를 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터 <xref:System.Windows.Controls.ListBox> 에 바인딩합니다.  
  
 바인딩을 설정 하려면 <xref:System.Windows.Data.Binding> 개체를 사용 합니다. 이 항목의 나머지 부분에서는와 관련 된 몇 가지 개념과 <xref:System.Windows.Data.Binding> 개체의 속성 및 사용에 대해 설명 합니다.  
  
<a name="direction_of_data_flow"></a>   
### <a name="direction-of-the-data-flow"></a>데이터 흐름 방향  
 앞에서 설명한 것 처럼 위의 그림에 표시 된 것 처럼 바인딩의 데이터 흐름은 바인딩 대상에서 바인딩 소스로 이동할 수 있습니다. 예를 들어, 사용자가의 <xref:System.Windows.Controls.TextBox>값을 편집 하면 소스 값이 변경 되 고, 바인딩 소스에서 또는 바인딩 소스에서 적절 한 알림을 제공 하는 <xref:System.Windows.Controls.TextBox> 경우 바인딩 대상으로 콘텐츠를 업데이트 합니다. 예를 들어 콘텐츠는 바인딩 소스의 변경 내용으로 업데이트 됩니다.  
  
 애플리케이션에서 사용자가 데이터를 변경하고 다시 소스 개체에 전파할 수 있도록 해야 할 수 있습니다. 또는 사용자가 소스 데이터를 업데이트할 수 없도록 해야 할 수 있습니다. 개체의 속성을 <xref:System.Windows.Data.Binding.Mode%2A> 설정 하 여이를 제어할 수 있습니다. <xref:System.Windows.Data.Binding> 다음 그림은 다양한 유형의 데이터 흐름을 보여 줍니다.  
  
 ![데이터 바인딩 데이터 흐름](./media/databinding-dataflow.png "DataBinding_DataFlow")  
  
- <xref:System.Windows.Data.BindingMode.OneWay>바인딩하면 소스 속성의 변경으로 인해 대상 속성이 자동으로 업데이트 되지만 대상 속성의 변경 내용은 원본 속성에 다시 전파 되지 않습니다. 이 바인딩 유형은 바인드되는 컨트롤이 암시적으로 읽기 전용인 경우에 적합합니다. 예를 들어 주식 시세표시기와 같은 원본에 바인드할 수 있거나 대상 속성에는 테이블의 데이터 바인딩된 배경색과 같이 변경을 위해 제공된 컨트롤 인터페이스가 없을 수 있습니다. 대상 속성의 변경 내용을 모니터링할 필요가 없는 경우 <xref:System.Windows.Data.BindingMode.OneWay> 바인딩 모드를 사용하면 <xref:System.Windows.Data.BindingMode.TwoWay> 바인딩 모드의 오버헤드가 방지됩니다.  
  
- <xref:System.Windows.Data.BindingMode.TwoWay>바인딩하면 원본 속성 또는 대상 속성이 변경 되 면 다른가 자동으로 업데이트 됩니다. 이 바인딩 유형은 편집 가능한 폼이나 기타 완전한 대화형 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 시나리오에 적합합니다. 대부분의 속성은 <xref:System.Windows.Data.BindingMode.OneWay> 기본적으로 바인딩 되지만 일부 종속성 속성 (일반적으로 <xref:System.Windows.Controls.CheckBox>의 <xref:System.Windows.Controls.TextBox.Text%2A> <xref:System.Windows.Controls.TextBox> 속성 및 <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 의 속성과 같은 사용자가 편집 가능한 컨트롤의 속성)은로 기본사용됩니다.<xref:System.Windows.Data.BindingMode.TwoWay> 바인딩입니다. 종속성 속성이 기본적으로 단방향 또는 양방향으로 바인드되는지를 프로그래밍 방식으로 결정하려면 <xref:System.Windows.DependencyProperty.GetMetadata%2A>를 사용하여 속성의 속성 메타데이터를 가져온 후 <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A> 속성의 부울 값을 확인합니다.  
  
- <xref:System.Windows.Data.BindingMode.OneWayToSource>는 <xref:System.Windows.Data.BindingMode.OneWay> 바인딩의 반대 이며, 대상 속성이 변경 될 때 소스 속성을 업데이트 합니다. [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]에서 소스 값을 다시 평가하면 되는 경우가 한 가지 예제 시나리오입니다.  
  
- 이 그림에는 표시 되지 <xref:System.Windows.Data.BindingMode.OneTime> 않습니다 .이는 원본 속성이 대상 속성을 초기화 하는 것을 유발 하지만 후속 변경 내용은 전파 되지 않습니다. 이는 데이터 컨텍스트가 변경되고 있거나 데이터 컨텍스트의 개체가 변경될 경우 변경 내용이 대상 속성에 반영되지 않습니다. 이 바인딩 유형은 현재 상태의 스냅샷이 사용하기에 적절하거나 데이터가 실제로 정적인 상황에서 데이터를 사용하는 경우에 적합합니다. 또한 이 바인딩 유형은 원본 속성의 일부 값으로 대상 속성을 초기화하려고 하며 데이터 컨텍스트가 사전에 알려지지 않은 경우에도 유용합니다. 이는 기본적으로 원본 값이 변경되지 않은 경우에 더 나은 성능을 제공하는 <xref:System.Windows.Data.BindingMode.OneWay> 바인딩의 더 간단한 형태입니다.  
  
 원본 변경 내용 ( <xref:System.Windows.Data.BindingMode.OneWay> 및 <xref:System.Windows.Data.BindingMode.TwoWay> 바인딩에 적용 됨)을 검색 하려면 소스가와 <xref:System.ComponentModel.INotifyPropertyChanged>같은 적절 한 속성 변경 알림 메커니즘을 구현 해야 합니다. <xref:System.ComponentModel.INotifyPropertyChanged> 구현에 대 한 예제는 [속성 변경 알림 구현](how-to-implement-property-change-notification.md) 을 참조 하세요.  
  
 <xref:System.Windows.Data.Binding.Mode%2A> 속성 페이지에서는 바인딩 모드 및 바인딩 방향을 지정 하는 방법의 예제에 대해 자세히 설명 합니다.  
  
<a name="what_triggers_source_updates"></a>   
### <a name="what-triggers-source-updates"></a>소스 업데이트를 트리거하는 항목  
 바인딩 <xref:System.Windows.Data.BindingMode.TwoWay> 또는 <xref:System.Windows.Data.BindingMode.OneWayToSource> 대상 속성의 변경 내용을 수신 대기 하 고 소스에 다시 전파 합니다. 이를 소스 업데이트라고 합니다. 예를 들어 TextBox의 텍스트를 편집하여 기본 소스 값을 변경할 수 있습니다. 마지막 섹션에서 설명한 것 처럼 데이터 흐름의 방향은 바인딩의 <xref:System.Windows.Data.Binding.Mode%2A> 속성 값에 따라 결정 됩니다.  
  
 하지만 텍스트를 편집하는 동안이나 텍스트 편집을 마치고 마우스를 TextBox 외부로 이동한 후 소스 값이 업데이트될까요? 바인딩의 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성은 원본 업데이트를 트리거하는 항목을 결정 합니다. 다음 그림의 오른쪽 화살표 점이 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성의 역할을 보여 줍니다.  
  
 ![System.windows.data.binding.updatesourcetrigger 속성의 역할을 보여 주는 다이어그램입니다.](./media/data-binding-overview/data-binding-updatesource-trigger.png)  
  
 값이 이면 대상 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>속성이 변경 되는 즉시 <xref:System.Windows.Data.BindingMode.TwoWay> 또는 <xref:System.Windows.Data.BindingMode.OneWayToSource> 바인딩의 오른쪽 화살표가 가리키는 값이 업데이트 됩니다. <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 그러나 값이 이면 대상 속성이 포커스를 잃을 때만 해당 값이 새 값으로 업데이트 됩니다 <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>. <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>  
  
 속성과 마찬가지로 다른 종속성 속성에는 기본값이 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 다릅니다. <xref:System.Windows.Data.Binding.Mode%2A> 대부분의 종속성 속성에 대한 기본값이 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>인 반면 <xref:System.Windows.Controls.TextBox.Text%2A> 속성의 기본값은 <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>입니다. 즉, 일반적으로 소스 업데이트는 대상 속성이 변경 될 때마다 발생 하며,이는 <xref:System.Windows.Controls.CheckBox>es 및 기타 간단한 컨트롤에는 적합 하지 않습니다. 하지만 텍스트 필드의 경우 키 입력이 있을 때마다 업데이트하면 성능이 저하될 수 있고 새 값으로 커밋하기 전에 사용자가 백스페이스 키를 누르고 입력 오류를 수정할 수 있는 기회가 사라집니다. 그 이유 <xref:System.Windows.Controls.TextBox.Text%2A> 때문에 속성의 기본값 <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> 은 대신 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>입니다.  
  
 종속성 속성 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 의 기본값 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 을 찾는 방법에 대 한 자세한 내용은 속성 페이지를 참조 하세요.  
  
 다음 표에서는를 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> <xref:System.Windows.Controls.TextBox> 예로 사용 하는 각 값에 대 한 예제 시나리오를 제공 합니다.  
  
|UpdateSourceTrigger 값|소스 값이 업데이트될 때|TextBox의 예제 시나리오|  
|-------------------------------|----------------------------------------|----------------------------------|  
|LostFocus (의 <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>기본값)|TextBox 컨트롤이 포커스를 잃을 때|유효성 검사 논리와 연결 된 입니다(데이터유효성검사섹션참조).<xref:System.Windows.Controls.TextBox>|  
|PropertyChanged|에 입력할 때<xref:System.Windows.Controls.TextBox>|<xref:System.Windows.Controls.TextBox>대화방 창의 컨트롤|  
|명시적 방법|응용 프로그램에서를 호출 하는 경우<xref:System.Windows.Data.BindingExpression.UpdateSource%2A>|<xref:System.Windows.Controls.TextBox>편집 가능한 폼의 컨트롤 (사용자가 제출 단추를 클릭 하는 경우에만 소스 값 업데이트)|  
  
 예제를 보려면 [TextBox 텍스트의 소스를 업데이트하는 시점 제어](how-to-control-when-the-textbox-text-updates-the-source.md)를 참조하세요.  
  
<a name="creating_a_binding"></a>   
## <a name="creating-a-binding"></a>바인딩 만들기  
  
 이전 섹션에서 설명 하는 몇 가지 개념을 recapitulate <xref:System.Windows.Data.Binding> 개체를 사용 하 여 바인딩을 설정 하 고 각 바인딩에는 일반적으로 바인딩 대상, 대상 속성, 바인딩 소스 및 사용할 소스 값의 경로 라는 네 가지 구성 요소가 있습니다. 이 섹션에서는 바인딩을 설정하는 방법을 설명합니다.  
  
 바인딩 소스 개체가 *SDKSample* 네임스페이스에 정의된 *MyData* 클래스인 다음 예제를 살펴볼 수 있습니다. 설명을 위해 *MyData* 클래스에는 값이 "Red"로 설정된 *ColorName* 문자열 속성이 있습니다. 따라서 이 예제에서는 빨간색 배경이 있는 단추를 생성합니다.  
  
 [!code-xaml[BindNonTextProperty#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindNonTextProperty/CS/Page1.xaml#1)]  
  
 바인딩 선언 구문에 대한 자세한 설명과 코드에서 바인딩을 설정하는 방법의 예제는 [바인딩 선언 개요](binding-declarations-overview.md)를 참조하세요.  
  
 이 예제를 기본 다이어그램에 적용하면 결과 그림은 다음과 같이 표시됩니다. 이는 Background 속성이 기본적으로 바인딩을 지원 <xref:System.Windows.Data.BindingMode.OneWay> 하기 때문에 바인딩입니다.<xref:System.Windows.Data.BindingMode.OneWay>  
  
 ![데이터 바인딩 배경 속성을 보여 주는 다이어그램입니다.](./media/data-binding-overview/data-binding-button-background-example.png)  
  
 Colorname 속성이 형식이 <xref:System.Windows.Media.Brush>면 서 <xref:System.Windows.Controls.Control.Background%2A> *colorname* 속성이 string 형식 이더라도이 방법이 작동 하는 이유를 궁금할 수 있습니다. 기본 형식 변환이 작동하기 때문이고 이 기능은 [데이터 변환](#data_conversion) 섹션에서 설명합니다.  
  
<a name="specifying_the_binding_source"></a>   
### <a name="specifying-the-binding-source"></a>바인딩 소스 지정  
 이전 예제에서는 <xref:System.Windows.FrameworkElement.DataContext%2A> <xref:System.Windows.Controls.DockPanel> 요소에 대 한 속성을 설정 하 여 바인딩 소스를 지정 합니다. 그런 다음는 부모 <xref:System.Windows.FrameworkElement.DataContext%2A> 요소인에서 값 <xref:System.Windows.Controls.DockPanel>을 상속 합니다. <xref:System.Windows.Controls.Button> 다시 말하지만, 바인딩 소스 개체는 바인딩의 네 가지 필수 구성 요소 중 하나입니다. 따라서 바인딩 소스 개체를 지정하지 않으면 바인딩은 아무 작업도 하지 않습니다.  
  
 바인딩 소스 개체를 지정하는 여러 가지 방법이 있습니다. 부모 요소에 대해 속성을사용하는것은여러속성을동일한소스에바인딩하는경우에유용합니다.<xref:System.Windows.FrameworkElement.DataContext%2A> 하지만 개별 바인딩 선언에서 바인딩 소스를 지정하는 방법이 더 적절한 경우도 있습니다. 이전 예제에서는 <xref:System.Windows.FrameworkElement.DataContext%2A> 속성을 사용 하는 대신, 다음 예제와 같이 단추의 바인딩 선언에서 직접 <xref:System.Windows.Data.Binding.Source%2A> 속성을 설정 하 여 바인딩 소스를 지정할 수 있습니다.  
  
 [!code-xaml[BindNonTextProperty#BackgroundBindingCompact](~/samples/snippets/csharp/VS_Snippets_Wpf/BindNonTextProperty/CS/Page2.xaml#backgroundbindingcompact)]  
  
 요소에 대 한 <xref:System.Windows.FrameworkElement.DataContext%2A> 속성을 직접 설정 하는 것 외 <xref:System.Windows.FrameworkElement.DataContext%2A> 에, 상위 항목의 값 (예: 첫 번째 예제의 단추)을 상속 하 고,의 속성 <xref:System.Windows.Data.Binding.Source%2A> 을설정하여바인딩소스를명시적으로지정합니다.<xref:System.Windows.Data.Binding> (마지막 예제 단추와 같은) <xref:System.Windows.Data.Binding.ElementName%2A> 속성 <xref:System.Windows.Data.Binding.RelativeSource%2A> 또는 속성을 사용 하 여 바인딩 소스를 지정할 수도 있습니다. 속성 <xref:System.Windows.Data.Binding.ElementName%2A> 은 슬라이더를 사용 하 여 단추의 너비를 조정 하는 경우와 같이 응용 프로그램의 다른 요소에 바인딩하는 경우에 유용 합니다. 속성은 바인딩이 <xref:System.Windows.Controls.ControlTemplate> 또는<xref:System.Windows.Style>에 지정 된 경우에 유용 합니다. <xref:System.Windows.Data.Binding.RelativeSource%2A> 자세한 내용은 [바인딩 소스 지정](how-to-specify-the-binding-source.md)을 참조하세요.  
  
<a name="specifying_the_path_to_the_value"></a>   
### <a name="specifying-the-path-to-the-value"></a>값 경로 지정  
 바인딩 소스가 개체 이면 <xref:System.Windows.Data.Binding.Path%2A> 속성을 사용 하 여 바인딩에 사용할 값을 지정 합니다. 데이터에 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 바인딩하는 경우에는 <xref:System.Windows.Data.Binding.XPath%2A> 속성을 사용 하 여 값을 지정 합니다. 데이터가 인 <xref:System.Windows.Data.Binding.Path%2A> [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]경우에도 속성을 사용 하는 것이 적합 한 경우도 있습니다. 예를 들어 XPath 쿼리의 결과로 반환 된 XmlNode의 Name 속성에 액세스 하려면 속성 외에 속성 <xref:System.Windows.Data.Binding.Path%2A> <xref:System.Windows.Data.Binding.XPath%2A> 을 사용 해야 합니다.  
  
 구문 정보 및 예제는 <xref:System.Windows.Data.Binding.Path%2A> 및 <xref:System.Windows.Data.Binding.XPath%2A> 속성 페이지를 참조 하세요.  
  
 사용할 값 <xref:System.Windows.Data.Binding.Path%2A> 에 대 한가 바인딩의 네 가지 필수 구성 요소 중 하나 이며, 전체 개체에 바인딩하려는 시나리오에서 사용할 값은 바인딩 소스 개체와 동일 합니다. 이러한 경우를 지정 <xref:System.Windows.Data.Binding.Path%2A>하지 않는 것이 좋습니다. 다음 예제를 참조하세요.  
  
 [!code-xaml[MasterDetail#EmptyBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetail/CSharp/Page1.xaml#emptybinding)]  
  
 위의 예제에서는 빈 바인딩 구문인 {Binding}을 사용합니다. 이 경우는 부모 DockPanel <xref:System.Windows.Controls.ListBox> 요소에서 DataContext를 상속 합니다 (이 예제에는 표시 되지 않음). 경로를 지정하지 않으면 기본적으로 전체 개체에 바인딩됩니다. 즉,이 예제에서는 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 속성을 전체 개체에 바인딩하기 때문에 경로가 남아 있습니다. 자세한 내용은 [컬렉션에 바인딩](#binding_to_collections) 섹션을 참조하세요.  
  
 컬렉션에 바인딩 외에 개체의 단일 속성만이 아닌 전체 개체에 바인딩하려는 경우에도 이 시나리오가 유용합니다. 예를 들면 소스 개체가 문자열 형식이고 문자열 자체에 바인딩하려는 경우입니다. 또 다른 일반적인 시나리오는 여러 속성이 있는 개체에 요소를 바인딩하려는 경우입니다.  
  
 바인딩된 대상 속성에서 데이터가 의미를 가지려면 사용자 지정 논리를 적용해야 할 수 있습니다. 사용자 지정 논리는 사용자 지정 변환기 형식일 수 있습니다(기본 형식 변환이 없는 경우). 변환기에 대한 자세한 내용은 [데이터 변환](#data_conversion)을 참조하세요.  
  
<a name="binding_bindingexpression"></a>   
### <a name="binding-and-bindingexpression"></a>Binding 및 BindingExpression  
 데이터 바인딩의 다른 기능 및 사용을 가져오기 전에 클래스를 도입 하는 <xref:System.Windows.Data.BindingExpression> 것이 유용 합니다. 이전 단원 <xref:System.Windows.Data.Binding> 에서 살펴본 것 처럼 클래스는 바인딩의 선언에 대 한 상위 수준 클래스입니다. 클래스는 <xref:System.Windows.Data.Binding> 바인딩의 특성을 지정할 수 있는 다양 한 속성을 제공 합니다. 관련 클래스인 <xref:System.Windows.Data.BindingExpression>는 소스와 대상 간의 연결을 유지 관리 하는 기본 개체입니다. 바인딩에는 여러 바인딩 식에서 공유될 수 있는 모든 정보가 포함됩니다. 는 공유할 수 없고 <xref:System.Windows.Data.Binding>의 모든 인스턴스 정보를 포함 하는 인스턴스 식입니다. <xref:System.Windows.Data.BindingExpression>  
  
 예를 들어 다음을 고려 하십시오. 여기서 *mydataobject* 는 *MyData* 클래스의 인스턴스이고, *mydataobject* 은 원본 <xref:System.Windows.Data.Binding> 개체이 고, *MyData* 클래스는 이름이 인 *문자열 속성을 포함 하는 정의 된 클래스입니다. MyDataProperty*. 이 예에서는 *mytext* <xref:System.Windows.Controls.TextBlock>의 텍스트 콘텐츠를 *mydataproperty*에 바인딩합니다.  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 같은 *myBinding* 개체를 사용하여 다른 바인딩을 만들 수 있습니다. 예를 들어 *myBinding* 개체를 사용하여 확인란의 텍스트 컨텍스트를 *MyDataProperty*에 바인딩할 수 있습니다. 이 시나리오에는 <xref:System.Windows.Data.BindingExpression> *mybinding* 개체를 공유 하는 두 개의 인스턴스가 있습니다.  
  
 데이터 <xref:System.Windows.Data.BindingExpression> 바인딩된 개체에서를 호출 <xref:System.Windows.Data.BindingOperations.GetBindingExpression%2A> 하는의 반환 값을 통해 개체를 가져올 수 있습니다. 다음 항목에서는 <xref:System.Windows.Data.BindingExpression> 클래스를 사용 하는 몇 가지 방법을 보여 줍니다.  
  
- [바인딩된 대상 속성에서 바인딩 개체 가져오기](how-to-get-the-binding-object-from-a-bound-target-property.md)  
  
- [TextBox 텍스트의 소스를 업데이트하는 시점 제어](how-to-control-when-the-textbox-text-updates-the-source.md)  
  
<a name="data_conversion"></a>   
## <a name="data-conversion"></a>데이터 변환  
 이전 예제에서 해당 <xref:System.Windows.Controls.Control.Background%2A> 속성은 값이 "red" 인 문자열 속성에 바인딩되므로 단추가 빨간색입니다. 이는 형식에 <xref:System.Windows.Media.Brush> 형식 변환기가 있어 문자열 값 <xref:System.Windows.Media.Brush>을로 변환 하기 때문에 작동 합니다.  
  
 [바인딩 만들기](#creating_a_binding) 섹션의 그림에 이 정보를 추가하려는 경우 다이어그램은 다음과 같이 표시됩니다.  
  
 ![데이터 바인딩 기본 속성을 보여 주는 다이어그램입니다.](./media/data-binding-overview/data-binding-button-default-conversion.png)  
  
 그러나 형식 문자열의 속성을 포함 하는 대신 바인딩 소스 개체에 형식의 <xref:System.Windows.Media.Color> *Color* 속성이 있나요? 이 경우 바인딩이 작동 하려면 먼저 *Color* 속성 값을 <xref:System.Windows.Controls.Control.Background%2A> 속성이 허용 하는 값으로 변환 해야 합니다. 다음 예제와 같이 <xref:System.Windows.Data.IValueConverter> 인터페이스를 구현 하 여 사용자 지정 변환기를 만들어야 합니다.  
  
 [!code-csharp[ColorPicker_snip#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ColorPicker_snip/CSharp/ColorPickerLib/ColorPicker.cs#16)]
 [!code-vb[ColorPicker_snip#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ColorPicker_snip/visualbasic/colorpickerlib/colorpicker.vb#16)]  
  
 참조 <xref:System.Windows.Data.IValueConverter> 페이지에 자세한 정보가 나와 있습니다.  
  
 이제 기본 변환 대신 사용자 지정 변환기가 사용되고 다이어그램이 다음과 같이 표시됩니다.  
  
 ![데이터 바인딩 사용자 지정 변환기를 표시 하는 다이어그램입니다.](./media/data-binding-overview/data-binding-converter-color-example.png)  
  
 다시 말하지만, 바인딩되는 형식에 있는 형식 변환기 때문에 기본 변환을 사용할 수 있습니다. 이 동작은 대상에서 사용할 수 있는 형식 변환기에 따라 결정됩니다. 확실하지 않으면 사용자 지정 변환기를 만듭니다.  
  
 데이터 변환기를 구현하는 것이 좋은 몇 가지 일반적인 시나리오는 다음과 같습니다.  
  
- 데이터를 문화권에 따라 다르게 표시해야 하는 경우. 예를 들어 특정 문화권에서 사용되는 값 또는 표준에 따라 통화 변환기 또는 달력 날짜/시간 변환기를 구현해야 할 수 있습니다.  
  
- 사용되는 데이터가 반드시 속성의 텍스트 값을 변경하는 데 사용될 필요는 없지만, 이미지의 소스 또는 표시 텍스트의 색이나 스타일과 같은 몇 가지 다른 값을 변경하는 데 사용되는 경우. 텍스트 필드를 표 셀의 Background 속성에 바인딩하는 것과 같이 적절해 보이지 않는 속성의 바인딩을 변환하는 방식으로 이 인스턴스에서 변환기를 사용할 수 있습니다.  
  
- 두 개 이상의 컨트롤 또는 컨트롤의 여러 속성이 같은 데이터에 바인딩됩니다. 이 경우 기본 바인딩은 텍스트만 표시할 수 있는 반면, 기타 바인딩은 특정 표시 문제를 처리하지만 소스 정보와 같은 바인딩을 사용합니다.  
  
- 지금까지 대상 속성에 바인딩 컬렉션이 <xref:System.Windows.Data.MultiBinding>있는 경우를 아직 설명 하지 않았습니다. 의 <xref:System.Windows.Data.MultiBinding>경우 사용자 지정 <xref:System.Windows.Data.IMultiValueConverter> 를 사용 하 여 바인딩의 값에서 최종 값을 생성 합니다. 예를 들어 빨간색, 파란색 및 녹색 값을 기준으로 색을 계산할 수 있고 이러한 값은 같거나 다른 바인딩 소스 개체의 값일 수 있습니다. 예제 및 <xref:System.Windows.Data.MultiBinding> 정보는 클래스 페이지를 참조 하세요.  
  
<a name="binding_to_collections"></a>   
## <a name="binding-to-collections"></a>컬렉션에 바인딩  
  
 바인딩 소스는 속성에 데이터가 포함된 단일 개체로 처리되거나 종종 함께 그룹화되는 다형 개체의 데이터 컬렉션(예: 데이터베이스에 대한 쿼리의 결과)으로 처리될 수 있습니다. 지금까지 단일 개체에 대한 바인딩만 설명했지만 일반적인 시나리오는 데이터 컬렉션에 대한 바인딩입니다. 예를 들어 <xref:System.Windows.Controls.ItemsControl> 일반적인 시나리오는 <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.ListView>또는 <xref:System.Windows.Controls.TreeView> 와 같은을 사용 하 여 데이터 [바인딩 이란?](#what_is_data_binding) 섹션에 표시 된 응용 프로그램에서와 같은 데이터 컬렉션을 표시 하는 것입니다.  
  
 다행히도 기본 다이어그램이 적용됩니다. 을 컬렉션 <xref:System.Windows.Controls.ItemsControl> 에 바인딩하는 경우 다이어그램은 다음과 같습니다.  
  
 ![데이터 바인딩 ItemsControl 개체를 표시 하는 다이어그램입니다.](./media/data-binding-overview/data-binding-itemscontrol.png)  
  
 이 다이어그램에 표시 된 <xref:System.Windows.Controls.ItemsControl> 것 처럼를 컬렉션 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 개체에 바인딩하려면 속성은 사용할 속성입니다. <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 속성은의 콘텐츠로 <xref:System.Windows.Controls.ItemsControl>생각할 수 있습니다. 바인딩은 속성은 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 기본적으로 <xref:System.Windows.Data.BindingMode.OneWay> 바인딩을 지원 <xref:System.Windows.Data.BindingMode.OneWay> 하기 때문입니다.  
  
<a name="how_to_implement_collections"></a>   
### <a name="how-to-implement-collections"></a>컬렉션을 구현하는 방법  
 구현 하는 컬렉션을 열거할 수 있습니다는 <xref:System.Collections.IEnumerable> 인터페이스입니다. 그러나 컬렉션에서 삽입 또는 삭제가 업데이트 되도록 동적 바인딩을 설정 하는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 자동으로 구현 해야 합니다 <xref:System.Collections.Specialized.INotifyCollectionChanged> 인터페이스. 이 인터페이스는 기본 컬렉션이 변경될 때마다 발생해야 하는 이벤트를 노출합니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 제공 된 <xref:System.Collections.ObjectModel.ObservableCollection%601> 노출 하는 데이터 컬렉션의 기본 구현 클래스는 <xref:System.Collections.Specialized.INotifyCollectionChanged> 인터페이스. 원본 개체에서 대상으로 데이터 값 전송을 완벽 하 게 지원 하려면 바인딩 가능한 속성을 지 원하는 컬렉션의 각 개체도 인터페이스를 <xref:System.ComponentModel.INotifyPropertyChanged> 구현 해야 합니다. 자세한 내용은 [바인딩 소스 개요](binding-sources-overview.md)를 참조하세요.  
  
 고유한 컬렉션을 구현 하기 전에 사용해 <xref:System.Collections.ObjectModel.ObservableCollection%601> 또는 같은 기존 컬렉션 중 하나가 클래스 <xref:System.Collections.Generic.List%601>를 <xref:System.Collections.ObjectModel.Collection%601>, 및 <xref:System.ComponentModel.BindingList%601>, 다양 한 기타. 고급 시나리오에서 고유한 컬렉션을 구현 하려는 경우 인덱스를 통해 개별적으로 액세스할 수 <xref:System.Collections.IList>있는 개체의 제네릭이 아닌 컬렉션을 제공 하는를 사용 하 여 최상의 성능을 제공 합니다.  
  
<a name="collection_views"></a>   
### <a name="collection-views"></a>컬렉션 뷰  
 <xref:System.Windows.Controls.ItemsControl> 가 데이터 컬렉션에 바인딩되면 데이터를 정렬, 필터링 또는 그룹화 하는 것이 좋습니다. 이렇게 하려면 인터페이스를 <xref:System.ComponentModel.ICollectionView> 구현 하는 클래스인 컬렉션 뷰를 사용 합니다.  

#### <a name="what-are-collection-views"></a>컬렉션 뷰란?  
 컬렉션 뷰는 기본 소스 컬렉션 자체를 변경할 필요 없이 정렬, 필터 및 그룹화 쿼리에 따라 소스 컬렉션을 탐색하고 표시할 수 있는 바인딩 소스 컬렉션의 최상위에 있는 레이어입니다. 컬렉션 뷰에서는 컬렉션의 현재 항목에 대한 포인터도 유지 관리합니다. 소스 컬렉션에 구현 하는 경우는 <xref:System.Collections.Specialized.INotifyCollectionChanged> 인터페이스를 변경 된 내용이 <xref:System.Collections.Specialized.INotifyCollectionChanged.CollectionChanged> 이벤트 보기에 전파 됩니다.  
  
 뷰는 기본 소스 컬렉션을 변경하지 않으므로 각 소스 컬렉션에는 연결된 여러 뷰가 있을 수 있습니다. 예를 들어 *Task* 개체의 컬렉션이 있을 수 있습니다. 뷰를 사용하여 같은 데이터를 다양한 방식으로 표시할 수 있습니다. 예를 들어 페이지 왼쪽에는 우선 순위별로 정렬된 작업을 표시하고 오른쪽에는 영역별로 그룹화된 작업을 표시해야 할 수 있습니다.  
  
<a name="how_to_create_a_view"></a>   
#### <a name="how-to-create-a-view"></a>뷰를 만드는 방법  
 뷰를 만들고 사용하는 한 가지 방법은 뷰 개체를 인스턴스화하고 이를 바인딩 소스로 사용하는 것입니다. 예를 들어 [데이터 바인딩이란?](#what_is_data_binding) 섹션에 나와 있는 [Data Binding Demo](https://go.microsoft.com/fwlink/?LinkID=163703)(데이터 바인딩 데모) 애플리케이션을 살펴보겠습니다. 응용 프로그램은가 <xref:System.Windows.Controls.ListBox> 데이터 컬렉션 대신 데이터 컬렉션에 대해 직접 뷰에 바인딩되기 때문에 구현 됩니다. 다음 예제는 [Data Binding Demo](https://go.microsoft.com/fwlink/?LinkID=163703)(데이터 바인딩 데모) 애플리케이션에서 추출됩니다. 클래스는 에서<xref:System.Windows.Data.CollectionView>상속 되는 클래스의 프록시입니다.[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] <xref:System.Windows.Data.CollectionViewSource> 이 특정 예제에서 뷰의는 <xref:System.Windows.Data.CollectionViewSource.Source%2A> 현재 응용 프로그램 개체의 *AuctionItems* 컬렉션 (형식 <xref:System.Collections.ObjectModel.ObservableCollection%601>)에 바인딩됩니다.  
  
 [!code-xaml[DataBindingLab#WindowResources1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#windowresources1)]  
[!code-xaml[DataBindingLab#CollectionViewSource](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#collectionviewsource)]  
[!code-xaml[DataBindingLab#WindowResources2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#windowresources2)]  
  
 그런 다음 리소스 *Listingdataview* 는 <xref:System.Windows.Controls.ListBox>다음과 같은 응용 프로그램의 요소에 대 한 바인딩 소스 역할을 합니다.  
  
 [!code-xaml[DataBindingLab#Master1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master1)]  
[!code-xaml[DataBindingLab#Master2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master2)]  
  
 동일한 컬렉션에 대해 다른 뷰를 만들려면 다른 <xref:System.Windows.Data.CollectionViewSource> 인스턴스를 만들고 다른 `x:Key` 이름을 지정 하면 됩니다.  
  
 다음 표에서는 기본 컬렉션 뷰 또는 <xref:System.Windows.Data.CollectionViewSource> 원본 컬렉션 유형에 따라 생성 되는 뷰 데이터 유형을 보여 줍니다.  
  
|소스 컬렉션 형식|컬렉션 뷰 형식|노트|  
|----------------------------|--------------------------|-----------|  
|<xref:System.Collections.IEnumerable>|다음을 기반으로 하는 내부 형식<xref:System.Windows.Data.CollectionView>|항목을 그룹화할 수 없습니다.|  
|<xref:System.Collections.IList>|<xref:System.Windows.Data.ListCollectionView>|가장 빠릅니다.|  
|<xref:System.ComponentModel.IBindingList>|<xref:System.Windows.Data.BindingListCollectionView>||  
  
##### <a name="using-a-default-view"></a>기본 뷰 사용  
 컬렉션 뷰를 만들고 사용하는 한 가지 방법은 컬렉션 뷰를 바인딩 소스로 지정하는 것입니다. WPF에서도 바인딩 소스로 사용되는 모든 컬렉션에 대한 기본 컬렉션 뷰를 만듭니다. 컬렉션에 직접 바인딩할 경우 WPF는 기본 뷰에 바인딩됩니다. 같은 컬렉션에 대한 모든 바인딩이 이 기본 뷰를 공유하므로 하나의 바인딩된 컨트롤이나 코드(예: 뒷부분에 설명되는 현재 항목 포인터에 대한 정렬 또는 변경)를 통해 기본 뷰에 적용된 변경 내용은 같은 컬렉션에 대한 모든 다른 바인딩에 반영됩니다.  
  
 사용할 기본 뷰를 가져오려면는 <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> 메서드. 예제를 보려면 [데이터 수집의 기본 뷰 가져오기](how-to-get-the-default-view-of-a-data-collection.md)를 참조하세요.  
  
##### <a name="collection-views-with-adonet-datatables"></a>ADO.NET DataTable이 있는 컬렉션 뷰  
 성능을 향상 시키기 위해 ADO.NET <xref:System.Data.DataTable> 또는 <xref:System.Data.DataView> 개체에 대 한 컬렉션 뷰는 <xref:System.Data.DataView>로 정렬 및 필터링을 위임 합니다. 이렇게 하면 정렬 및 필터링이 데이터 소스의 모든 컬렉션 뷰에서 공유됩니다. 각 컬렉션 뷰에서 독립적으로 정렬 및 필터링 할 수 있도록 하려면 해당 <xref:System.Data.DataView> 개체를 사용 하 여 각 컬렉션 뷰를 초기화 합니다.  
  
#### <a name="sorting"></a>정렬  
 앞에서 설명한 대로 뷰에서는 컬렉션에 정렬 순서를 적용할 수 있습니다. 기본 컬렉션에 있는 데이터에는 관련 상속 순서가 있거나 없을 수도 있습니다. 컬렉션에 대한 뷰를 통해 제공한 비교 기준에 따라 순서를 적용하거나 기본 순서를 변경할 수 있습니다. 이는 데이터의 클라이언트 기반 뷰이므로 일반적으로 열과 일치하는 값에 따라 표 형식 데이터의 열을 정렬해야 할 수 있습니다. 뷰를 사용하면 기본 컬렉션을 변경하거나 컬렉션 콘텐츠를 다시 쿼리할 필요 없이 이 사용자 기반 정렬을 적용할 수 있습니다. 예제를 보려면 [머리글을 클릭할 때 GridView 열 정렬](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)을 참조하세요.  
  
 다음 예제에서는 [데이터 바인딩 이란?](#what_is_data_binding) 섹션에 있는 응용 프로그램 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 의 "범주 및 <xref:System.Windows.Controls.CheckBox> 날짜별 정렬"의 정렬 논리를 보여 줍니다.  
  
 [!code-csharp[DataBindingLab#8](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#8)]
 [!code-vb[DataBindingLab#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#8)]  
  
#### <a name="filtering"></a>필터링  
 컬렉션에 필터를 적용할 수도 있습니다. 이는 항목이 컬렉션에 있을 수 있지만 이 특정 뷰는 전체 컬렉션의 특정 하위 집합만 표시하는 데 사용됨을 의미합니다. 데이터에서 조건에 따라 필터링할 수 있습니다. 예를 들어, [데이터 바인딩 이란?](#what_is_data_binding) 섹션의 응용 프로그램에서 수행 하는 것 처럼 "Show only bargains" <xref:System.Windows.Controls.CheckBox> 에는 비용 $25 이상인 항목을 필터링 하는 논리가 포함 되어 있습니다. 다음 코드를 실행 하 여 *ShowOnlyBargainsFilter* 를 선택 하면 <xref:System.Windows.Data.CollectionViewSource.Filter> <xref:System.Windows.Controls.CheckBox> 이벤트 처리기로 설정 합니다.  
  
 [!code-csharp[DataBindingLab#10](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 *ShowOnlyBargainsFilter* 이벤트 처리기에는 다음과 같은 구현이 있습니다.  
  
 [!code-csharp[DataBindingLab#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
 <xref:System.Windows.Data.CollectionView> 대신클래스<xref:System.Windows.Data.CollectionView.Filter%2A> 중 하나를 직접 사용 하는 경우에는 속성을 사용 하 여 콜백을 지정 합니다. <xref:System.Windows.Data.CollectionViewSource> 예제를 보려면 [뷰에서 데이터 필터링](how-to-filter-data-in-a-view.md)을 참조하세요.  
  
#### <a name="grouping"></a>그룹화  
 <xref:System.Collections.IEnumerable> 컬렉션을 표시 하는 내부 클래스를 제외 하 고, 모든 컬렉션 뷰에서 그룹화 기능을 지원 하므로 사용자는 컬렉션 뷰의 컬렉션을 논리 그룹으로 분할할 수 있습니다. 그룹은 사용자가 그룹 목록을 제공하는 경우 명시적 그룹이고 데이터에 따라 그룹이 동적으로 생성되는 경우 암시적 그룹입니다.  
  
 다음 예제에서는 "Group by category" <xref:System.Windows.Controls.CheckBox>의 논리를 보여 줍니다.  
  
 [!code-csharp[DataBindingLab#6](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#6)]
 [!code-vb[DataBindingLab#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#6)]  
  
 다른 그룹화 예제를 보려면 [GridView를 구현하는 ListView의 항목 그룹화](../controls/how-to-group-items-in-a-listview-that-implements-a-gridview.md)를 참조하세요.  
  
#### <a name="current-item-pointers"></a>현재 항목 포인터  
 뷰는 현재 항목의 개념도 지원합니다. 컬렉션 뷰에서 개체를 탐색할 수 있습니다. 탐색할 때 컬렉션의 특정 위치에 있는 개체를 검색할 수 있는 항목 포인터를 이동합니다. 예제를 보려면 [데이터 수집 뷰의 개체 탐색](how-to-navigate-through-the-objects-in-a-data-collectionview.md)을 참조하세요.  
  
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
  
<a name="master_detail_scenario"></a>   
#### <a name="master-detail-binding-scenario"></a>마스터-세부 바인딩 시나리오  
 현재 항목의 개념은 컬렉션에서 항목을 탐색하는 경우뿐 아니라 마스터-세부 바인딩 시나리오에도 유용합니다. 다시 [데이터 바인딩이란?](#what_is_data_binding) 섹션의 애플리케이션 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 살펴보겠습니다. 해당 응용 프로그램에서 내의 <xref:System.Windows.Controls.ListBox> 선택은에 표시 되 <xref:System.Windows.Controls.ContentControl>는 내용을 결정 합니다. 다른 방식으로 배치 하기 위해 <xref:System.Windows.Controls.ListBox> 항목을 선택 하면에서 <xref:System.Windows.Controls.ContentControl> 선택한 항목의 세부 정보를 표시 합니다.  
  
 간단히 두 개 이상의 컨트롤을 같은 뷰에 바인딩하여 마스터-세부 시나리오를 구현할 수 있습니다. [데이터 바인딩 데모](https://go.microsoft.com/fwlink/?LinkID=163703) 의 다음 예제에서는 [데이터 바인딩 이란?](#what_is_data_binding) 섹션의 <xref:System.Windows.Controls.ListBox> 응용 프로그램 <xref:System.Windows.Controls.ContentControl> [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 에 표시 되는 및의 태그를 보여 줍니다.  
  
 [!code-xaml[DataBindingLab#Master1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master1)]  
[!code-xaml[DataBindingLab#Master2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master2)]  
[!code-xaml[DataBindingLab#Detail](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#detail)]  
  
 컨트롤이 둘 다 같은 소스인 *listingDataView* 정적 리소스에 바인딩되어 있습니다([뷰를 만드는 방법 섹션](#how_to_create_a_view)에서 이 리소스의 정의 참조). Singleton 개체 ( <xref:System.Windows.Controls.ContentControl> 이 경우)가 컬렉션 뷰에 바인딩되면 자동으로 뷰의에 <xref:System.Windows.Data.CollectionView.CurrentItem%2A> 바인딩되기 때문에 이러한 방식이 적용 됩니다. 개체는 <xref:System.Windows.Data.CollectionViewSource> 통화와 선택 항목을 자동으로 동기화 합니다. 이 예제와 같이 목록 컨트롤이 <xref:System.Windows.Data.CollectionViewSource> 개체에 바인딩되지 않은 경우에는 해당 <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> 속성을로 `true` 설정 하 여이 작업을 수행 해야 합니다.  
  
 다른 예제를 보려면 [선택에 따라 수집 및 표시 정보에 바인딩](how-to-bind-to-a-collection-and-display-information-based-on-selection.md) 및 [계층적 데이터에 마스터-세부 패턴 사용](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)을 참조하세요.  
  
 위 예제에서는 템플릿을 사용합니다. 실제로는 템플릿을 사용 하지 않고 데이터를 표시 하지 않습니다 (에서 명시적으로 사용 <xref:System.Windows.Controls.ContentControl> 하는 방법과에서 암시적 <xref:System.Windows.Controls.ListBox>으로 사용 되는 항목). 이제 다음 섹션에서 데이터 템플릿을 살펴보겠습니다.  
  
<a name="data_templating"></a>   
## <a name="data-templating"></a>데이터 템플릿  
 데이터 템플릿을 사용하지 않으면 [데이터 바인딩이란?](#what_is_data_binding) 섹션의 애플리케이션 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]가 다음과 같이 표시됩니다.  
  
 ![데이터 템플릿을 사용하지 않는 데이터 바인딩 데모](./media/data-binding-overview/data-binding-demo-templates.png)  
  
 이전 섹션의 예제에 표시 된 것 처럼 <xref:System.Windows.Controls.ListBox> 컨트롤과는 <xref:System.Windows.Controls.ContentControl> 모두 *AuctionItem*s의 전체 컬렉션 개체 (또는 컬렉션 개체에 대 한 뷰)에 바인딩됩니다. 데이터 컬렉션을 표시 하는 방법에 대 한 구체적인 지침이 <xref:System.Windows.Controls.ListBox> 없으면에서 기본 컬렉션에 있는 각 개체의 문자열 표현을 표시 <xref:System.Windows.Controls.ContentControl> 하 고가 바인딩된 개체의 문자열 표현을 표시 합니다.  
  
 이 문제를 해결 하기 위해 응용 프로그램 <xref:System.Windows.DataTemplate>은를 정의 합니다. 이전 섹션의 예제와 같이에서는 <xref:System.Windows.Controls.ContentControl> 명시적으로 *detailsProductListingTemplate*<xref:System.Windows.DataTemplate>을 사용 합니다. 컨트롤 <xref:System.Windows.Controls.ListBox> 은 컬렉션에서 *AuctionItem* 개체 <xref:System.Windows.DataTemplate> 를 표시할 때 다음을 암시적으로 사용 합니다.  
  
 [!code-xaml[DataBindingLab#AuctionItemDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#auctionitemdatatemplate)]  
  
 이러한 두 가지 <xref:System.Windows.DataTemplate>를 사용 하 여 결과 UI는 [데이터 바인딩 이란?](#what_is_data_binding) 섹션에 나와 있습니다. 이 스크린샷에서 볼 수 있듯이, 컨트롤 <xref:System.Windows.DataTemplate>에 데이터를 추가 하는 것 외에도 데이터에 대 한 멋진 시각적 개체를 정의할 수 있습니다. 예를 들어 <xref:System.Windows.DataTrigger>위의 <xref:System.Windows.DataTemplate> 있도록 *AuctionItem*s *SpecialFeatures* 의 값 *강조 표시* 으로 표시 되는 주황색 테두리와 별입니다.  
  
 데이터 템플릿에 대한 자세한 내용은 [데이터 템플릿 개요](data-templating-overview.md)를 참조하세요.  
  
<a name="data_validation"></a>   
## <a name="data-validation"></a>데이터 유효성 검사  
  
 사용자 입력을 사용하는 대부분 애플리케이션에는 사용자가 필요한 정보를 입력했는지 확인할 수 있는 유효성 검사 논리가 있어야 합니다. 유효성 검사는 형식, 범위, 서식 또는 기타 애플리케이션별 요구 사항에 따라 달라질 수 있습니다. 이 섹션에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 데이터 유효성 검사를 사용하는 방법을 설명합니다.  
  
### <a name="associating-validation-rules-with-a-binding"></a>유효성 검사 규칙과 바인딩 연결  
 합니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 데이터 바인딩 모델에 연결할 수 있습니다 <xref:System.Windows.Data.Binding.ValidationRules%2A> 사용 하 여 프로그램 <xref:System.Windows.Data.Binding> 개체입니다. 예를 들어, 다음 예제에서는를 <xref:System.Windows.Controls.TextBox> 이라는 `StartPrice` 속성에 바인딩하고 <xref:System.Windows.Controls.ExceptionValidationRule> 개체를 <xref:System.Windows.Data.Binding.ValidationRules%2A?displayProperty=nameWithType> 속성에 추가 합니다.  
  
 [!code-xaml[DataBindingLab#DefaultValidation](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#defaultvalidation)]  
  
 개체 <xref:System.Windows.Controls.ValidationRule> 는 속성의 값이 유효한 지 여부를 확인 합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에는 다음과 같은 두 가지 유형의 기본 제공 <xref:System.Windows.Controls.ValidationRule> 개체가 있습니다.  
  
- 는 <xref:System.Windows.Controls.ExceptionValidationRule> 바인딩 소스 속성을 업데이트 하는 동안 throw 된 예외를 확인 합니다. 이전 예제에서 `StartPrice`는 정수 형식입니다. 사용자가 정수로 변환될 수 없는 값을 입력하면 예외가 throw되어 바인딩이 잘못된 것으로 표시됩니다. 설정 하는 대체 구문은 <xref:System.Windows.Controls.ExceptionValidationRule> 명시적으로 설정 하는 것을 <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> 속성을 `true` 에서 프로그램 <xref:System.Windows.Data.Binding> 또는 <xref:System.Windows.Data.MultiBinding> 개체입니다.  
  
- 개체 <xref:System.Windows.Controls.DataErrorValidationRule> 는 인터페이스를 <xref:System.ComponentModel.IDataErrorInfo> 구현 하는 개체에서 발생 한 오류를 확인 합니다. 이 유효성 검사 규칙을 사용 하는 예제는 <xref:System.Windows.Controls.DataErrorValidationRule>를 참조 하십시오. 설정 하는 대체 구문은 <xref:System.Windows.Controls.DataErrorValidationRule> 명시적으로 설정 하는 것을 <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> 속성을 `true` 에서 프로그램 <xref:System.Windows.Data.Binding> 또는 <xref:System.Windows.Data.MultiBinding> 개체입니다.  
  
 <xref:System.Windows.Controls.ValidationRule> 클래스에서 파생 하 고 메서드를 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 구현 하 여 사용자 고유의 유효성 검사 규칙을 만들 수도 있습니다. 다음 예에서는 [데이터 바인딩 이란?](#what_is_data_binding) 섹션의 *제품 추가 목록* "시작 날짜" <xref:System.Windows.Controls.TextBox> 에 사용 되는 규칙을 보여 줍니다.  
  
 [!code-csharp[DataBindingLab#2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/FutureDateRule.cs#2)]
 [!code-vb[DataBindingLab#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/FutureDateRule.vb#2)]  
  
 *Startdateentryform* <xref:System.Windows.Controls.TextBox> 은 다음 예제와 같이이 *FutureDateRule*를 사용 합니다.  
  
 [!code-xaml[DataBindingLab#CustomValidation](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#customvalidation)]  
  
 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값 <xref:System.Windows.Data.Binding.ValidationRules%2A> 이 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>이기 때문에 바인딩 엔진은 모든 키 입력에 대 한 소스 값을 업데이트 합니다. 즉, 모든 키 입력에 대해 컬렉션의 모든 규칙을 검사 합니다. 이 내용은 유효성 검사 프로세스 섹션에서 자세히 설명합니다.  
  
<a name="invalidation_feedback"></a>   
### <a name="providing-visual-feedback"></a>시각적 피드백 제공  
 사용자가 잘못된 값을 입력할 경우 애플리케이션 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]에 오류에 대한 피드백을 표시해야 할 수 있습니다. 이러한 피드백을 제공 하는 한 가지 방법은 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> 연결 된 속성을 사용자 지정 <xref:System.Windows.Controls.ControlTemplate>으로 설정 하는 것입니다. 이전 하위 섹션에 표시 된 것 처럼 *startdateentryform* <xref:System.Windows.Controls.TextBox> 은 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> *validationtemplate*이라는를 사용 합니다. 다음 예제에서는 *validationTemplate*의 정의를 보여 줍니다.  
  
 [!code-xaml[DataBindingLab#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#1)]  
  
 요소 <xref:System.Windows.Controls.AdornedElementPlaceholder> 는 표시 되는 컨트롤을 배치할 위치를 지정 합니다.  
  
 또한를 사용 <xref:System.Windows.Controls.ToolTip> 하 여 오류 메시지를 표시할 수도 있습니다. *Startdateentryform* 과 *StartPriceEntryForm*<xref:System.Windows.Controls.TextBox>es는 모두 *textStyleTextBox*스타일을 사용 하 여 오류 메시지를 <xref:System.Windows.Controls.ToolTip> 표시 하는을 만듭니다. 다음 예제에서는 *textStyleTextBox*의 정의를 보여 줍니다. 연결 된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 은 `true` 바인딩된 요소의 속성에 대 한 하나 이상의 바인딩에서 오류가 발생 한 경우입니다.  
  
 [!code-xaml[DataBindingLab#14](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#14)]  
  
 사용자 지정 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> <xref:System.Windows.Controls.TextBox> 및를 사용 하는 경우 유효성 검사 오류가 발생 하면 *startdateentryform* 은 다음과 같이 표시 됩니다. <xref:System.Windows.Controls.ToolTip>  
  
 ![데이터 바인딩 유효성 검사 오류](./media/databindingdemo-validation.PNG "DataBindingDemo_Validation")  
  
 에 <xref:System.Windows.Data.Binding> 연결 된 유효성 검사 규칙이 있지만 바인딩된 컨트롤 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 에를 지정 하지 않은 경우 유효성 검사 오류가 있을 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 때 사용자에 게 알리는 기본값이 사용 됩니다. 기본값 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 은 표시기 계층에서 빨간색 테두리를 정의 하는 컨트롤 템플릿입니다. 기본 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] <xref:System.Windows.Controls.TextBox> 및를 사용 하는 경우 유효성 검사 오류가 발생 하면 StartPriceEntryForm의는 다음과 같습니다. <xref:System.Windows.Controls.ToolTip>  
  
 ![데이터 바인딩 유효성 검사 오류](./media/databindingdemo-validationdefault.PNG "DataBindingDemo_ValidationDefault")  
  
 대화 상자에서 모든 컨트롤의 유효성을 검사하는 논리를 제공하는 방법의 예제를 보려면 [대화 상자 개요](../app-development/dialog-boxes-overview.md)에서 사용자 지정 대화 상자 섹션을 참조하세요.  
  
### <a name="validation-process"></a>유효성 검사 프로세스  
 유효성 검사는 대개 대상 값이 바인딩 소스 속성에 전송될 때 수행됩니다. 이는 <xref:System.Windows.Data.BindingMode.TwoWay> 및 <xref:System.Windows.Data.BindingMode.OneWayToSource> 바인딩에서 발생 합니다. 반복 하기 위해 원본 업데이트를 [트리거하는 대상 트리거](#what_triggers_source_updates) 섹션에 설명 된 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 대로 원본 업데이트의 원인은 속성의 값에 따라 달라 집니다.  
  
 *유효성 검사* 프로세스에 대한 설명은 다음과 같습니다. 이 프로세스 중에 유효성 검사 오류나 기타 오류가 발생하면 프로세스가 중단됩니다.  
  
1. 바인딩 엔진 <xref:System.Windows.Controls.ValidationRule> 은 해당 <xref:System.Windows.Controls.ValidationStep.RawProposedValue> <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> <xref:System.Windows.Controls.ValidationRule> <xref:System.Windows.Controls.ValidationRule.Validate%2A> 에 대해가로 설정 된 사용자 지정 개체가 있는지 확인 합니다 .이 경우 해당 개체 중 하나가 오류로 실행 될 때까지 메서드를 호출 합니다. <xref:System.Windows.Data.Binding> 모든 해당 항목을 통과 해야 합니다.  
  
2. 그런 다음 바인딩 엔진은 변환기를 호출합니다(있는 경우).  
  
3. 변환기가 성공 하면 바인딩 <xref:System.Windows.Controls.ValidationRule> 엔진은 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> <xref:System.Windows.Data.Binding>이에 대해가로 <xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue> 설정 된 사용자 지정 개체가 있는지 확인 합니다 .이 경우에는가 포함 된 각 <xref:System.Windows.Controls.ValidationRule.Validate%2A> <xref:System.Windows.Controls.ValidationRule> 개체에 대해 메서드를 호출 합니다. 둘 중 <xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue> 하나가 오류가 발생 하거나 모두 통과 될 때까지로 설정 됩니다. <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>  
  
4. 바인딩 엔진은 소스 속성을 설정합니다.  
  
5. <xref:System.Windows.Controls.ValidationRule> 바인딩 엔진은 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> <xref:System.Windows.Controls.ValidationRule> <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> 이에 <xref:System.Windows.Controls.ValidationStep.UpdatedValue> 대해 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 가로 설정 된 사용자 지정 개체가 있는지 확인 합니다 .이 경우는로 설정 된 각에 대해 메서드를 호출 합니다. <xref:System.Windows.Data.Binding> <xref:System.Windows.Controls.ValidationStep.UpdatedValue> 이러한 항목 중 하나를 오류가 발생 하거나 모두 통과 될 때까지. 이 바인딩과 연결 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> <xref:System.Windows.Controls.ValidationStep.UpdatedValue> <xref:System.Windows.Controls.DataErrorValidationRule> 되어 있고 해당이 기본값로 설정 되어 있으면이 시점에서이 확인 됩니다. <xref:System.Windows.Controls.DataErrorValidationRule> 이는가로 <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> `true` 설정 된 바인딩을 확인 하는 경우 이기도 합니다.  
  
6. <xref:System.Windows.Controls.ValidationRule> 바인딩 엔진은 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> <xref:System.Windows.Controls.ValidationRule> <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> 이에 <xref:System.Windows.Controls.ValidationStep.CommittedValue> 대해 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 가로 설정 된 사용자 지정 개체가 있는지 확인 합니다 .이 경우는로 설정 된 각에 대해 메서드를 호출 합니다. <xref:System.Windows.Data.Binding> <xref:System.Windows.Controls.ValidationStep.CommittedValue> 이러한 항목 중 하나를 오류가 발생 하거나 모두 통과 될 때까지.  
  
 이 프로세스 <xref:System.Windows.Controls.ValidationRule> 를 통해 언제 든 지를 전달 하지 않으면 바인딩 엔진은 개체를 <xref:System.Windows.Controls.ValidationError> 만들어 바인딩된 요소의 <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> 컬렉션에 추가 합니다. 바인딩 엔진은 지정 된 단계 <xref:System.Windows.Controls.ValidationRule> 에서 개체를 실행 하기 전에 해당 단계에서 <xref:System.Windows.Controls.ValidationError> 바인딩된 요소의 <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> 연결 된 속성에 추가 된 모든를 제거 합니다. 예를 들어 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> 가 failed <xref:System.Windows.Controls.ValidationRule> 로 <xref:System.Windows.Controls.ValidationStep.UpdatedValue> 설정 된 경우 다음에 유효성 검사 <xref:System.Windows.Controls.ValidationError> 프로세스가 발생 하면 바인딩 <xref:System.Windows.Controls.ValidationRule> 엔진은가로 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> 설정 된를 호출 하기 직전에이를 제거 합니다. <xref:System.Windows.Controls.ValidationStep.UpdatedValue>.  
  
 때 <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> 비어 있지 않으며이 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 요소의 속성이 `true`합니다. 또한 경우를 <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A> 의 속성을 <xref:System.Windows.Data.Binding> 로 설정 되어 `true`, 바인딩 엔진을 <xref:System.Windows.Controls.Validation.Error?displayProperty=nameWithType> 요소에서 연결 된 이벤트.  
  
 또한 한 방향 (대상에서 원본으로 또는 원본에서 대상으로)으로 유효한 값을 전송 하면 <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> 연결 된 속성이 지워집니다.  
  
 바인딩에 <xref:System.Windows.Controls.ExceptionValidationRule> 연결 `true` <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>된가 있거나 속성이로설정되어있고바인딩엔진이소스를설정하는경우예외가throw되는경우바인딩엔진은가있는지확인합니다.<xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> 사용 하는 옵션이 있습니다를 <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> 예외 처리에 대 한 사용자 지정 처리기를 제공 하는 콜백 합니다. 경우는 <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> 에 지정 되어 있지는 <xref:System.Windows.Data.Binding>, 바인딩 엔진에서 만드는 <xref:System.Windows.Controls.ValidationError> 예외를 사용 하 여에 추가 <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> 바인딩된 요소의 컬렉션입니다.  
  
## <a name="debugging-mechanism"></a>디버깅 메커니즘  
 바인딩 관련 개체에 연결 된 <xref:System.Diagnostics.PresentationTraceSources.TraceLevel%2A?displayProperty=nameWithType> 속성을 설정 하 여 특정 바인딩의 상태에 대 한 정보를 받을 수 있습니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Controls.DataErrorValidationRule>
- [WPF 버전 4.5의 새로운 기능](../getting-started/whats-new.md)
- [LINQ 쿼리 결과에 바인딩](how-to-bind-to-the-results-of-a-linq-query.md)
- [데이터 바인딩](../advanced/optimizing-performance-data-binding.md)
- [데이터 바인딩 데모](https://go.microsoft.com/fwlink/?LinkID=163703)
- [방법 항목](data-binding-how-to-topics.md)
- [ADO.NET 데이터 소스 바인딩](how-to-bind-to-an-ado-net-data-source.md)
